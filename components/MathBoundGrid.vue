<!-- components/MathBoundGrid.vue -->
<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const props = defineProps({
  speed: { type: Number, default: 0.25 },        // Overall particle movement speed
  thickness: { type: Number, default: 70 },     // Width of the border corridor (in pixels)
  particleCount: { type: Number, default: 110 }, // Total nodes running along the walls
  connectionDist: { type: Number, default: 50 },// Proximity threshold to snap a glowing line
  colorA: { type: String, default: '#06b6d4' },  // Neon Cyan
  colorB: { type: String, default: '#ec4899' }   // Cyber Pink
})

const canvasRef = ref(null)
const containerRef = ref(null)
let animationId = null

onMounted(() => {
  const canvas = canvasRef.value, ctx = canvas.getContext('2d'), container = containerRef.value
  let nodes = []
  let time = 0

  const resize = () => {
    const w = container.clientWidth || 980, h = container.clientHeight || 552
    const dpr = window.devicePixelRatio || 1
    canvas.width = w * dpr; canvas.height = h * dpr
    canvas.style.width = `${w}px`; canvas.style.height = `${h}px`
    ctx.scale(dpr, dpr)
    initNodes(w, h)
  };

  const initNodes = (w, h) => {
    nodes = []
    const t = props.thickness
    
    for (let i = 0; i < props.particleCount; i++) {
      let x, y
      // Mathematically isolate spawning positions specifically to the perimeter layout bands
      const edge = Math.floor(Math.random() * 4)
      if (edge === 0) { // Top Wall Corridor
        x = Math.random() * w
        y = Math.random() * t
      } else if (edge === 1) { // Bottom Wall Corridor
        x = Math.random() * w
        y = h - (Math.random() * t)
      } else if (edge === 2) { // Left Wall Corridor
        x = Math.random() * t
        y = Math.random() * h
      } else { // Right Wall Corridor
        x = w - (Math.random() * t)
        y = Math.random() * h
      }

      nodes.push({
        x: x, y: y,
        vx: (Math.random() - 0.5) * props.speed,
        vy: (Math.random() - 0.5) * props.speed,
        seed: Math.random() * 100
      })
    }
  }

  resize()
  window.addEventListener('resize', resize)

  const draw = () => {
    const w = container.clientWidth, h = container.clientHeight
    const t = props.thickness

    ctx.fillStyle = '#000000'
    ctx.fillRect(0, 0, w, h)

    // Master Color Shifting Loop
    const mixFactor = (Math.sin(time * 0.01) + 1) / 2
    const currentRGB = lerpHex(props.colorA, props.colorB, mixFactor)

    // A. Update Position Coordinates & Enforce Border Corridors
    for (const n of nodes) {
      n.x += n.vx + Math.sin(time * 0.02 + n.seed) * 0.04
      n.y += n.vy + Math.cos(time * 0.02 + n.seed) * 0.04

      // Enforce Spatial Bounds: Identify if a particle has broken inward or outward
      const nearLeft = n.x < t
      const nearRight = n.x > w - t
      const nearTop = n.y < t
      const nearBottom = n.y > h - t

      // If a particle is inside the central safe text zone, gently turn its velocity vector back around
      if (!nearLeft && !nearRight && !nearTop && !nearBottom) {
        // Find closest wall to bounce toward
        const distL = n.x, distR = w - n.x, distT = n.y, distB = h - n.y
        const minDist = Math.min(distL, distR, distT, distB)
        if (minDist === distL) n.vx -= 0.02
        else if (minDist === distR) n.vx += 0.02
        else if (minDist === distT) n.vy -= 0.02
        else n.vy += 0.02
      }

      // Keep particles inside the screen limits entirely (Hard bounce outer canvas bounds)
      if (n.x < 2 || n.x > w - 2) n.vx *= -1
      if (n.y < 2 || n.y > h - 2) n.vy *= -1
    }

    // B. Proximity Scanning & Bridge Render Matrix
    for (let i = 0; i < nodes.length; i++) {
      const n1 = nodes[i]

      for (let j = i + 1; j < nodes.length; j++) {
        const n2 = nodes[j]

        const lx = n1.x - n2.x
        const ly = n1.y - n2.y
        const distance = Math.sqrt(lx * lx + ly * ly)

        if (distance < props.connectionDist) {
          const alpha = (1 - distance / props.connectionDist) * 0.4
          
          ctx.beginPath()
          ctx.moveTo(n1.x, n1.y)
          ctx.lineTo(n2.x, n2.y)
          
          ctx.strokeStyle = `rgba(${currentRGB.r}, ${currentRGB.g}, ${currentRGB.b}, ${alpha})`
          ctx.lineWidth = (1 - distance / props.connectionDist) * 0.7
          ctx.stroke()
        }
      }

      // C. Draw Geometric Node Points
      // Calculate closeness to the absolute edge to fade out stray interior stragglers
      const distX = Math.min(n1.x, w - n1.x)
      const distY = Math.min(n1.y, h - n1.y)
      const currentMinDist = Math.min(distX, distY)
      const edgeFade = currentMinDist > t ? 0.1 : (1 - currentMinDist / t) * 0.6 + 0.2

      ctx.beginPath()
      ctx.arc(n1.x, n1.y, 1.1, 0, Math.PI * 2)
      ctx.fillStyle = `rgba(${currentRGB.r}, ${currentRGB.g}, ${currentRGB.b}, ${edgeFade})`
      ctx.fill()
    }

    time += 1
    animationId = requestAnimationFrame(draw)
  }

  // --- Color Interpolation Helper ---
  function lerpHex(hexA, hexB, t) {
    const parse = (h) => /^#?([a-f\d]{2})([a-f\d]{2})([a-f\d]{2})$/i.exec(h).slice(1, 4).map(x => parseInt(x, 16))
    const [r1, g1, b1] = parse(hexA), [r2, g2, b2] = parse(hexB)
    return { r: Math.round(r1 + (r2 - r1) * t), g: Math.round(g1 + (g2 - g1) * t), b: Math.round(b1 + (b2 - b1) * t) }
  }

  draw()

  onUnmounted(() => {
    cancelAnimationFrame(animationId)
    window.removeEventListener('resize', resize)
  })
})
</script>

<template>
  <div ref="containerRef" class="absolute inset-0 w-full h-full pointer-events-none z-[-1]">
    <canvas ref="canvasRef" class="block w-full h-full select-none" style="mix-blend-mode: screen;" />
  </div>
</template>
