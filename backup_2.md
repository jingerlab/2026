---
theme: default
# --- 1. System Font Mappings ---
fonts:
  sans: 'Century Gothic'
  serif: 'Alegreya'
  display: 'Catchy Mager'
  weights: '400,700'

# --- 2. Global Presentation Setup ---
title: Slidev Structural Blueprint
info: |
  ## Design Showcase Monograph
  Demonstrating local font rendering, custom transition mathematics, 
  and interactive layout components.
highlighter: shiki
drawings:
  persist: false

# Force global engine to prioritize UnoCSS compilation
css: unocss

# Set the default global transition to the continuous horizontal scroll
transition: scroll-left
mdc: true
---

<!-- SLIDE 1: Title & Typography Initialization -->
<div class="h-full flex flex-col justify-between p-8">
  <div class="mt-12">
    <!-- Using the Catchy Mager Display Font -->
    <h1 class="font-display text-6xl text-emerald-400 tracking-wide lowercase">
      architectural.spec
    </h1>
    <!-- Using Alegreya Serif Font -->
    <p class="font-serif text-2xl italic opacity-60 mt-2">
      An exploration of custom transitions, layout engines, and typographic control.
    </p>
  </div>

  <div class="flex justify-between items-end border-t border-white/10 pt-4 font-sans text-xs tracking-widest opacity-40">
    <div>COMPUTATIONAL METRICS PRESENTATION</div>
    <div>[ PRESS SPACE TO SCROLL RIGHT ]</div>
  </div>
</div>

---
transition: scroll-left
layout: default
---

<!-- SLIDE 2: Typography & Ligature Showcase -->
<div class="grid grid-cols-2 gap-8 h-full items-center">
  <div>
    <span class="font-sans text-xs font-bold tracking-widest text-emerald-500 uppercase block mb-2">01 / Typographic Layer</span>
    <h2 class="font-display text-4xl mb-4">Ligature & Hierarchy Test</h2>
    
    <p class="font-serif text-lg leading-relaxed text-gray-300">
      This block uses the local <strong>Alegreya</strong> serif family. Notice the automatic implementation of standard and contextual ligatures when handling math or programmatic text blocks. 
    </p>
  </div>

  <!-- Code execution block showcasing crisp modern font layout with clean tracking -->
  <div class="bg-black/30 border border-white/5 rounded-lg p-5 font-sans">
    <div class="text-xs text-emerald-400/70 font-mono mb-3">// Evaluating ligature operators: ->  !=  ==  <=</div>
    
    <p class="text-sm text-gray-400 leading-relaxed font-sans mb-4">
      The body wrapper and headings use <strong>Century Gothic</strong> natively. Bold, italic, and bold-italic variants inherit structural file weights cleanly.
    </p>
    
    <div class="text-[11px] font-mono opacity-40 bg-white/5 p-2 rounded">
      Style Flag: font-variant-ligatures: common-ligatures;
    </div>
  </div>
</div>

---
transition: zoom-depth
layout: center
class: text-center
---

<!-- SLIDE 3: The Gateway into the Deep Zoom -->
<div class="max-w-2xl mx-auto">
  <span class="font-sans text-xs font-bold tracking-widest text-purple-400 uppercase block mb-3">02 / Cinematic Viewport</span>
  <h2 class="font-display text-5xl text-white mb-6 leading-tight">
    Entering the Scalar Layer
  </h2>
  <p class="font-serif text-xl opacity-70">
    The standard horizontal reading plane breaks here. The next transition executes an immediate <strong>Z-axis plunge</strong> directly into the center core.
  </p>
  <div class="mt-8 animate-pulse text-purple-400 font-mono text-sm">
    ▼ Click next to descend deep inside
  </div>
</div>

---
transition: zoom-depth
layout: default
---

<!-- SLIDE 4: Inside the Nested Depth Matrix -->
<div class="h-full flex flex-col justify-center max-w-4xl mx-auto">
  <span class="font-sans text-xs font-bold tracking-widest text-purple-400 uppercase block mb-2">Deep Core State</span>
  <h2 class="font-display text-3xl mb-4 text-purple-300">Technical Sovereignty & Control</h2>
  
  <p class="font-serif text-lg text-gray-300 mb-8 max-w-2xl">
    You have descended down an entire order of scale. When navigating backward (<kbd>Left Arrow</kbd>), Slidev intercepts the stack, reversing the transform parameters to pull you back up to the parent slide seamlessly.
  </p>
  
  <div class="grid grid-cols-3 gap-4 font-sans text-xs">
    <div class="p-4 bg-purple-500/5 border border-purple-500/20 rounded-lg">
      <div class="font-bold text-purple-400 mb-1">Matrix Zoom-In</div>
      Scale expands from $0.3 \to 1.0$ while opacity hits baseline parameters.
    </div>
    <div class="p-4 bg-purple-500/5 border border-purple-500/20 rounded-lg">
      <div class="font-bold text-purple-400 mb-1">Matrix Zoom-Out</div>
      Scale expands out from $1.0 \to 3.0$ on forward exit, clearing the screen view.
    </div>
    <div class="p-4 bg-purple-500/5 border border-purple-500/20 rounded-lg">
      <div class="font-bold text-purple-400 mb-1">Symmetrical Return</div>
      Reversed animation classes handle the reverse physical descent vector.
    </div>
  </div>
</div>

---
transition: scroll-left
layout: default
---

<!-- SLIDE 5: The Interactive Flywheel Assembly -->
<!-- clicks: 2 ensures we have three distinct states inside this slide environment -->
<!--   -->
<div class="relative h-full w-full overflow-hidden">

  <!-- Left Content Anchor (Occupies left 50% of screen) -->
  <div class="w-1/2 h-full flex flex-col justify-center z-10 relative pr-8">
    <span class="font-sans text-xs font-bold tracking-widest text-amber-500 uppercase block mb-2">03 / Rotational System</span>
    <h2 class="font-display text-4xl text-amber-400 mb-4">The Flywheel Mechanism</h2>
    
    <!-- Dynamic State Manager dependent on active slide interaction clicks -->
    <div class="h-44 font-serif text-lg text-gray-300 relative">
      
      <!-- Click State 0 -->
      <div v-if="$clicks === 0" class="absolute inset-0">
        <h4 class="font-sans font-bold text-xs uppercase tracking-wider text-amber-500/60 mb-2">Phase Alpha / Anchor Index 1</h4>
        <p class="leading-relaxed">
          The flywheel alignment ring initializes at $0^\circ$. Content workspace quadrant registers standard data flows and schedules background asset collection pipelines.
        </p>
      </div>
      
      <!-- Click State 1 -->
      <div v-if="$clicks === 1" class="absolute inset-0">
        <h4 class="font-sans font-bold text-xs uppercase tracking-wider text-amber-500/60 mb-2">Phase Beta / Anchor Index 2</h4>
        <p class="leading-relaxed text-amber-100">
          First incremental click triggers a $-45^\circ$ torque vector rotation. The geometric matrix aligns node marker 2 squarely into the active left tracking boundary.
        </p>
      </div>
      
      <!-- Click State 2 -->
      <div v-if="$clicks >= 2" class="absolute inset-0">
        <h4 class="font-sans font-bold text-xs uppercase tracking-wider text-amber-500/60 mb-2">Phase Gamma / Anchor Index 3</h4>
        <p class="leading-relaxed text-amber-200">
          The system advances to $-90^\circ$ rotation. Maximum compression velocity achieved. Structural elements have completed their orbital tracking loop.
        </p>
      </div>
      
    </div>
    
    <div class="mt-4 font-sans text-[11px] opacity-40 uppercase tracking-widest">
      Click state: {{ $clicks }} of 2
    </div>
  </div>

  <!-- The Flywheel Geometric Ring Element (Fixed on Right Half) -->
  <!-- CSS transform binding uses current $clicks count to dynamically alter inline rotation values -->
  <div 
    class="flywheel-bg bg-gradient-to-br from-amber-500/5 via-transparent to-transparent border border-amber-500/20 shadow-2xl shadow-amber-950/20"
    :style="{ transform: `rotate(${$clicks * -45}deg)` }"
  >
    <div class="flywheel-ring"></div>
    
    <!-- Node Marker 1 -->
    <div class="absolute left-4 top-1/2 -translate-y-1/2 w-6 h-6 bg-amber-400 rounded-full flex items-center justify-center text-xs text-black font-bold font-sans shadow-lg">
      01
    </div>
    
    <!-- Node Marker 2 -->
    <div class="absolute left-[14.6%] top-[14.6%] w-6 h-6 bg-amber-400 rounded-full flex items-center justify-center text-xs text-black font-bold font-sans transform -rotate-45 shadow-lg">
      02
    </div>

    <!-- Node Marker 3 -->
    <div class="absolute top-4 left-1/2 -translate-x-1/2 w-6 h-6 bg-amber-400 rounded-full flex items-center justify-center text-xs text-black font-bold font-sans shadow-lg">
      03
    </div>
  </div>

</div>

---
layout: end
---

<!-- SLIDE 6: Presentation Outro Terminal -->
<div class="text-left max-w-xl">
  <h2 class="font-display text-5xl text-emerald-400 mb-4">execution.complete</h2>
  <p class="font-serif text-xl opacity-60 mb-8">
    All rendering tests, geometry anchors, and spatial layout frames loaded successfully.
  </p>
  
  <div class="font-mono text-xs opacity-40 border-t border-white/10 pt-4">
    Slidev Pipeline Engine v2026 // Node Workspace Active
  </div>
</div>
