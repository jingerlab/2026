<script setup>
import { onMounted, onUnmounted, ref, computed } from 'vue'

const props = defineProps({
  speed: { type: Number, default: 0.01 },       // Primary rotation speed
  opacity: { type: Number, default: 0.8 },      // Max opacity of the orb lines
  complexity: { type: Number, default: 18 },     // Density of the grid lines
  baseColorA: { type: String, default: '#6366f1' }, // Default modern indigo
  baseColorB: { type: String, default: '#ec4899' }  // Standard modern magenta/pink
})

const canvasRef = ref(null)
const containerRef = ref(null)
let animationId = null

onMounted(() => {
  const canvas = canvasRef.value, ctx = canvas.getContext('2d'), container = containerRef.value;
  
  const resize = () => {
    // 1. Get container dimensions (standard 980x552)
    const w = container.clientWidth || 980, h = container.clientHeight || 552;
    const dpr = window.devicePixelRatio || 1;
    
    // 2. Adjust drawing buffer and CSS scale for Retina/HighDPI
    canvas.width = w * dpr; canvas.height = h * dpr;
    canvas.style.width = `${w}px`; canvas.style.height = `${h}px`;
    ctx.scale(dpr, dpr);
  };

  resize();
  window.addEventListener('resize', resize);
  
  let time = 0;

  // The main drawing loop - 60 FPS purely mathematical render
  const draw = () => {
    const w = container.clientWidth, h = container.clientHeight;
    
    // Smooth frame clear (allows for subtle bloom trails)
    ctx.fillStyle = 'rgba(0, 0, 0, 0.1)'; 
    ctx.fillRect(0, 0, w, h);
    
    const cx = w / 2; // Center X
    const cy = h / 2; // Center Y
    const sphereRadius = h * 0.45; // Scales globe based on slide height
    
    // Rotation angles defined by math equations
    const rotX = time * 0.7; // Constant slow X rotation
    const rotY = time;       // Slightly faster Y rotation
    const rotZ = Math.sin(time * 0.3) * 0.2; // Undulating Z axis tilt (magical drift)

    // A. Generate points on a sphere (UV Grid)
    const points = [];
    const steps = props.complexity;
    for (let u = 0; u <= steps; u++) {
      const phi = (u / steps) * Math.PI; // Latitude
      for (let v = 0; v <= steps; v++) {
        const theta = (v / steps) * Math.PI * 2; // Longitude
        
        // Pure parametric math formulas
        const rx = Math.sin(phi) * Math.cos(theta);
        const ry = Math.cos(phi);
        const rz = Math.sin(phi) * Math.sin(theta);
        
        // 3D Rotation Transformations (matrix math applied linearly)
        // Rotate X
        let y1 = ry * Math.cos(rotX) - rz * Math.sin(rotX);
        let z1 = ry * Math.sin(rotX) + rz * Math.cos(rotX);
        let x1 = rx;
        // Rotate Y
        let x2 = x1 * Math.cos(rotY) + z1 * Math.sin(rotY);
        let z2 = -x1 * Math.sin(rotY) + z1 * Math.cos(rotY);
        let y2 = y1;
        // Rotate Z (Tilt)
        let x3 = x2 * Math.cos(rotZ) - y2 * Math.sin(rotZ);
        let y3 = x2 * Math.sin(rotZ) + y2 * Math.cos(rotZ);
        let z3 = z2;

        points.push({ x: x3, y: y3, z: z3 });
      }
    }

    // B. Draw connections (Pulsing, Mathematical Color Shifting)
    const pointsPerRow = steps + 1;
    for (let i = 0; i < points.length; i++) {
      // Find neighbors in the UV grid
      const neighbors = [];
      if ((i + 1) % pointsPerRow !== 0) neighbors.push(i + 1); // Connect right
      if (i + pointsPerRow < points.length) neighbors.push(i + pointsPerRow); // Connect down

      const p1 = points[i];

      // Mathematical Color Mix based on slow breathing sin wave (time variable)
      // This creates a smooth shift between Cool Indigo and Modern Pink
      const colorMixFactor = (Math.sin(time * 0.2) + 1) / 2; // Range 0.0 to 1.0
      
      // Interpolate colors manually in JS
      const rgbA = hexToRgb(props.baseColorA);
      const rgbB = hexToRgb(props.baseColorB);
      const r = Math.round(lerp(rgbA.r, rgbB.r, colorMixFactor));
      const g = Math.round(lerp(rgbA.g, rgbB.g, colorMixFactor));
      const b = Math.round(lerp(rgbA.b, rgbB.b, colorMixFactor));
      
      for (const j of neighbors) {
        const p2 = points[j];
        
        // 3D Perspective Projection (Flatten to 2D)
        const perspective = (sphereRadius * 0.7) / (2 - p1.z); // Math perspective shift
        
        ctx.beginPath();
        
        // Move to P1 (2D Projected point)
        ctx.moveTo(cx + p1.x * sphereRadius + p1.x * perspective, cy + p1.y * sphereRadius + p1.y * perspective);
        // Line to P2 (2D Projected point)
        const perspective2 = (sphereRadius * 0.7) / (2 - p2.z);
        ctx.lineTo(cx + p2.x * sphereRadius + p2.x * perspective2, cy + p2.y * sphereRadius + p2.y * perspective2);

        // Mathematical depth and pulse calculations:
        // 1. Line opacity fades based on Z depth (creating 3D illusion)
        const zOpacity = (p1.z + 1.2) / 2.2 * props.opacity; 
        
        // 2. Line width pulses subtly based on math waves (magical shimmer)
        const pulse = 1.0 + Math.sin(time * 3 + p1.x * 2) * 0.3;
        
        ctx.strokeStyle = `rgba(${r}, ${g}, ${b}, ${zOpacity})`;
        ctx.lineWidth = 0.8 * pulse; // Apply math shimmer pulse
        ctx.stroke();
      }
    }

    time += props.speed;
    animationId = requestAnimationFrame(draw);
  };

  // --- Core Utility Math Functions ---
  const lerp = (v0, v1, t) => v0 * (1 - t) + v1 * t;
  const hexToRgb = (hex) => {
    var result = /^#?([a-f\d]{2})([a-f\d]{2})([a-f\d]{2})$/i.exec(hex);
    return result ? { r: parseInt(result[1], 16), g: parseInt(result[2], 16), b: parseInt(result[3], 16) } : { r: 100, g: 100, b: 241 };
  };

  draw();

  onUnmounted(() => {
    cancelAnimationFrame(animationId);
    window.removeEventListener('resize', resize);
  })
})
</script>

<template>
  <div ref="containerRef" class="absolute inset-0 w-full h-full pointer-events-none z-[-1] flex items-center justify-center">
    <canvas ref="canvasRef" class="block" style="mix-blend-mode: screen;" />
  </div>
</template>
