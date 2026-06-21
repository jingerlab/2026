---
theme: default
title: Data Analysis Using Python | Preliminaries
info: |
  ## Just some preliminaries about the course.
highlighter: shiki
drawings:
  persist: false
css: unocss
favicon: "/favicon-light.png"
addons:
  - stem
  - python-runner
  - window-mockup
  - fancy-arrow

transition: slide-left | slide-right
mdc: true
layout: center
class: text-center
id: 1
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#10b981" />
# Data Analysis Using Python
<span class='text-xs'> *by* </span> <br>
<span class="font-display">Harsh Jinger</span>
## The Preliminaries
<div @click="$slidev.nav.next" class="mt-12 py-1" hover:bg="white op-10">
  Let's Begin <carbon:arrow-right />
</div>

---
layout: center
class: text-center
id: 2
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#10b981" />

<h2 class="text-5xl font-semibold mb-12">Why Programming?</h2>

<div class="grid grid-cols-2 gap-x-24 text-left max-w-2xl mx-auto text-xl">
  <div>
    <ul class="space-y-4 list-circle-force">
      <li v-click>Automation</li>
      <li v-click>Reproducibility</li>
      <li v-click>Customisability</li>
    </ul>
  </div>
  <div>
    <ul class="space-y-4 list-circle-force">
      <li v-click>Data Clean Up</li>
      <li v-click>Imputation</li>
      <li v-click>Scalability</li>
    </ul>
  </div>
</div>

<style>
.list-circle-force {
  list-style-type: circle !important;
  padding-left: 1.25rem;
}
.list-circle-force li {
  display: list-item !important;
}
</style>

---
layout: center
class: text-center
id: 3
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#10b981" />

<h2 class="text-5xl font-semibold mb-12">Why Python?</h2>

<div class="grid grid-cols-2 gap-x-24 text-left max-w-2xl mx-auto text-xl mb-12">
  <div>
    <ul class="space-y-4 list-circle-force">
      <li v-click>Human Readability</li>
      <li v-click>Community & Documentation</li>
    </ul>
  </div>
  <div>
    <ul class="space-y-4 list-circle-force">
      <li v-click>Versatility Because of extensive libraries</li>
      <li v-click>AI & ML Standard</li>
    </ul>
  </div>
</div>

<div v-click class="inline-block mx-auto text-xl mt-4 py-1 px-4 cursor-pointer" hover:bg="white op-10">
  ∴ Good Career ROI
</div>

<style>
.list-circle-force {
  list-style-type: circle !important;
  padding-left: 1.25rem;
}
.list-circle-force li {
  display: list-item !important;
}
</style>

---
layout: center
class: text-center
id: 4
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#10b981" />

<h2 class="text-5xl font-semibold mb-6">What is Data?</h2>

<div class="max-w-xl mx-auto mb-4">
  <div v-click class="border border-white/10 bg-white/5 rounded-xl px-8 py-6 backdrop-blur-sm shadow-xl">
    <p class="text-3xl font-serif italic text-emerald-400">
      "The digital footprints of reality."
    </p>
    <p class="text-lg opacity-60 mt-4 leading-relaxed">
      Raw, unorganized facts, symbols, and observations waiting to be translated into meaning.
    </p>
  </div>
</div>

<div class="grid grid-cols-2 gap-x-16 text-left max-w-2xl mx-auto text-lg mt-6">
  <div>
    <ul class="space-y-3 list-circle-force">
      <li v-click>Numbers & Metrics</li>
      <li v-click>Text & Code Blocks</li>
    </ul>
  </div>
  <div>
    <ul class="space-y-3 list-circle-force">
      <li v-click>Images & Signals</li>
      <li v-click>System Logs</li>
    </ul>
  </div>
</div>

<style>
.list-circle-force {
  list-style-type: circle !important;
  padding-left: 1.25rem;
}
.list-circle-force li {
  display: list-item !important;
}
</style>

---
layout: center
class: text-center
id: 5
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#10b981" />

<h2 class="text-5xl font-semibold mb-4">What is Analysis?</h2>

<div class="max-w-xl mx-auto mb-4">
  <div v-click class="border border-white/10 bg-white/5 rounded-xl px-8 py-6 backdrop-blur-sm shadow-xl">
    <p class="text-3xl font-serif italic text-emerald-400">
      "The lens that extracts clarity from chaos."
    </p>
    <p class="text-lg opacity-60 mt-4 leading-relaxed">
      The systematic process of breaking down complex datasets to discover patterns, tell stories, and drive decisions.
    </p>
  </div>
</div>

<div class="grid grid-cols-2 gap-x-16 text-left max-w-2xl mx-auto text-lg mt-6">
  <div>
    <ul class="space-y-3 list-circle-force">
      <li v-click>Finding Hidden Trends</li>
      <li v-click>Cleaning the Noise</li>
    </ul>
  </div>
  <div>
    <ul class="space-y-3 list-circle-force">
      <li v-click>Testing Hypotheses</li>
      <li v-click>Predicting Outcomes</li>
    </ul>
  </div>
</div>

<style>
.list-circle-force {
  list-style-type: circle !important;
  padding-left: 1.25rem;
}
.list-circle-force li {
  display: list-item !important;
}
</style>

---
layout: center
class: text-center
id: 6
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#06b6d4" />

<h2 class="text-5xl font-semibold mb-12 text-white">Course Objective</h2>

<div class="max-w-3xl mx-auto px-10 py-8 rounded-xl bg-[#041b1e] border border-cyan-500/10 backdrop-blur-sm">
  <p v-click class="text-2xl font-serif italic leading-relaxed text-cyan-100">
    "Master advanced NumPy and Pandas workflows to clean, transform, and analyze multi-format data pipelines, executing complex wrangling tasks to deliver actionable insights from real-world datasets."
  </p>
</div>

<style>
.slidev-page {
  background-color: #041b1e !important;
}
</style>

---
layout: center
class: text-center
id: 7
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#06b6d4" />

<h2 class="text-5xl font-semibold mb-16 text-white">Necessary Tools</h2>

<div class="grid grid-cols-3 gap-x-12 max-w-3xl mx-auto items-start">
  
  <div v-click class="flex flex-col items-center">
    <div class="mb-6 h-16 w-16 flex items-center justify-center">
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/anaconda/anaconda-original.svg" class="h-16 w-16" alt="Miniconda Logo" />
    </div>
    <h3 class="text-2xl font-bold text-white mb-2">Miniconda</h3>
    <p class="text-sm opacity-60 leading-relaxed">Package & Environment Management</p>
  </div>

  <div v-click class="flex flex-col items-center">
    <div class="mb-6 h-16 w-16 flex items-center justify-center">
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" class="h-16 w-16" alt="pip Logo" />
    </div>
    <h3 class="text-2xl font-bold text-white mb-2">pip</h3>
    <p class="text-sm opacity-60 leading-relaxed">Python Package Index Installer</p>
  </div>

  <div v-click class="flex flex-col items-center">
    <div class="mb-6 h-16 w-16 flex items-center justify-center">
      <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spyder/spyder-original.svg" class="h-16 w-16" alt="Spyder Logo" />
    </div>
    <h3 class="text-2xl font-bold text-white mb-2">Spyder</h3>
    <p class="text-sm opacity-60 leading-relaxed">Scientific Integrated Development Environment</p>
  </div>

</div>

<style>
.slidev-page {
  background-color: #041b1e !important;
}
</style>

---
layout: center
class: text-center
id: 8
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#06b6d4" />

<div class="flex flex-col items-center mb-4">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/anaconda/anaconda-original.svg" class="h-20 w-20 mb-3" alt="Miniconda Logo" />
  <h2 class="text-4xl font-semibold text-white">Miniconda</h2>
</div>

<p class="max-w-2xl mx-auto text-base opacity-75 mb-6 leading-relaxed">
  A minimal, lightweight bootstrap distribution of Python that includes only <strong>conda</strong>, its dependencies, and a small number of useful packages—making it the ideal choice for creating isolated, lightweight scientific environments.
</p>

<div class="max-w-2xl mx-auto border border-white/5 bg-black/20 p-5 rounded-xl backdrop-blur-sm text-left">
  
  <div class="flex justify-center gap-x-6 mb-4 border-b border-white/10 pb-2">
    <button 
      @click="currentOs = 'win'" 
      :class="currentOs === 'win' ? 'text-emerald-400 border-b-2 border-emerald-400 font-bold' : 'text-gray-400 opacity-60'"
      class="pb-1 px-2 text-sm transition-all focus:outline-none"
    >
      Windows (PowerShell)
    </button>
    <button 
      @click="currentOs = 'mac'" 
      :class="currentOs === 'mac' ? 'text-emerald-400 border-b-2 border-emerald-400 font-bold' : 'text-gray-400 opacity-60'"
      class="pb-1 px-2 text-sm transition-all focus:outline-none"
    >
      macOS (Bash / Zsh)
    </button>
  </div>

  <div class="bg-black/40 p-4 rounded font-mono text-sm text-gray-300 min-h-16 flex items-center">
    <pre v-if="currentOs === 'win'" class="w-full overflow-x-auto whitespace-pre-wrap leading-relaxed m-0">Invoke-WebRequest -Uri "https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe" -OutFile ".\Miniconda3-latest-Windows-x86_64.exe"; Start-Process -FilePath ".\Miniconda3-latest-Windows-x86_64.exe" -ArgumentList "/S" -Wait</pre>
    <pre v-if="currentOs === 'mac'" class="w-full overflow-x-auto whitespace-pre-wrap leading-relaxed m-0">curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh && bash Miniconda3-latest-MacOSX-arm64.sh -b -p $HOME/miniconda3</pre>
  </div>

</div>

<script setup lang="ts">
import { ref } from 'vue'
const currentOs = ref('win')
</script>

<style>
.slidev-page {
  background-color: #041b1e !important;
}
</style>

---
layout: center
class: text-center
id: 9
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#8b5cf6" />

<h2 class="text-5xl font-semibold mb-6 text-white">Environment Creation</h2>

<div class="max-w-xl mx-auto mb-6">
  <div v-click class="border border-purple-500/10 bg-purple-950/20 rounded-xl px-8 py-4 backdrop-blur-sm shadow-xl">
    <p class="text-2xl font-serif italic text-purple-300">
      "Why separate environments?"
    </p>
    <p class="text-base opacity-70 mt-2 leading-relaxed">
      To prevent dependency conflicts and shield your projects from breaking when external libraries upgrade.
    </p>
  </div>
</div>

<div class="max-w-2xl mx-auto border border-purple-500/10 bg-black/30 p-5 rounded-xl backdrop-blur-sm text-left font-mono text-sm text-gray-300 space-y-3">
  <div v-click class="flex items-center justify-between border-b border-white/5 pb-2">
    <span class="text-purple-400">1. Initialize Workspace:</span>
    <span class="bg-black/40 px-3 py-1 rounded text-xs select-all">conda create -n daup -y</span>
  </div>
  <div v-click class="flex items-center justify-between">
    <span class="text-purple-400">2. Activate Environment:</span>
    <span class="bg-black/40 px-3 py-1 rounded text-xs select-all">conda activate daup</span>
  </div>
</div>

<style>
.slidev-page {
  background-color: #0b071e !important;
}
</style>

---
layout: center
class: text-center
id: 10
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#8b5cf6" />

<div class="flex flex-col items-center mb-6">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" class="h-16 w-16 mb-2" alt="pip Logo" />
  <h2 class="text-4xl font-semibold text-white">Installing pip</h2>
</div>

<p class="max-w-xl mx-auto text-base opacity-75 mb-6 leading-relaxed">
  Ensure the Python Package Index installer is securely bound to your isolated project environment workspace.
</p>

<div class="max-w-xl mx-auto border border-purple-500/10 bg-black/30 p-5 rounded-xl backdrop-blur-sm text-left">
  <div class="bg-black/40 p-4 rounded font-mono text-sm text-gray-300">
    <div class="text-xs opacity-40 mb-2"># Execute inside your active daup environment</div>
    <pre v-click class="m-0 text-purple-300 font-bold select-all">conda install pip -y</pre>
  </div>
</div>

<style>
.slidev-page {
  background-color: #0b071e !important;
}
</style>

---
layout: center
class: text-center
id: 11
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#8b5cf6" />

<div class="flex flex-col items-center mb-6">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spyder/spyder-original.svg" class="h-16 w-16 mb-2" alt="Spyder Logo" />
  <h2 class="text-4xl font-semibold text-white">Installing Spyder IDE</h2>
</div>

<p class="max-w-xl mx-auto text-base opacity-75 mb-6 leading-relaxed">
  Deploy the scientific environment workspace directly from the Anaconda channel mapping.
</p>

<div class="max-w-xl mx-auto border border-purple-500/10 bg-black/30 p-5 rounded-xl backdrop-blur-sm text-left">
  <div class="bg-black/40 p-4 rounded font-mono text-sm text-gray-300">
    <div class="text-xs opacity-40 mb-2"># Pull and install via explicit namespace pipeline</div>
    <pre v-click class="m-0 text-purple-300 font-bold select-all">conda install anaconda::spyder -y</pre>
  </div>
</div>

<style>
.slidev-page {
  background-color: #0b071e !important;
}
</style>

---
layout: center
class: text-center
id: 12
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#ef4444" />

<h2 class="text-5xl font-semibold mb-12 text-white">Break & Attendance</h2>

<div class="grid grid-cols-2 gap-x-12 items-center justify-center max-w-3xl mx-auto">
  
  <div class="flex justify-end pr-4">
    <div class="border border-red-500/20 bg-black/30 p-4 rounded-2xl backdrop-blur-sm shadow-xl">
      <img src="/at.png" class="h-56 w-auto rounded-lg object-contain" alt="Attendance Link" />
    </div>
  </div>

  <div class="flex flex-col items-start justify-center pl-4 text-left">
    <div class="px-8 py-4 bg-red-950/40 border border-red-500/20 rounded-xl font-mono text-5xl font-bold text-red-400 tracking-wider shadow-inner min-w-[200px] text-center">
      <div v-if="timeLeft > 0" class="flex justify-center items-center">
        <span v-text="minutes"></span>:<span v-text="seconds < 10 ? '0' + seconds : seconds"></span>
      </div>
      <span v-else class="text-white animate-pulse text-3xl">Time's Up!</span>
    </div>
    <p class="text-sm text-red-400/60 mt-3 font-sans tracking-wide pl-2">Minutes remaining</p>
  </div>

</div>

<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue'

const timeLeft = ref(600)
let timerInterval: any = null

const minutes = computed(() => Math.floor(timeLeft.value / 60))
const seconds = computed(() => timeLeft.value % 60)

onMounted(() => {
  timerInterval = setInterval(() => {
    if (timeLeft.value > 0) timeLeft.value--
  }, 1000)
})

onUnmounted(() => {
  clearInterval(timerInterval)
})
</script>

<style>
.slidev-page {
  background-color: #1a0505 !important;
}
</style>

---
layout: center
class: text-center
id: 13
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#38bdf8" />

<h2 class="text-5xl font-semibold mb-8 text-white">Quick Recap</h2>

<p class="max-w-xl mx-auto text-base opacity-75 mb-8 leading-relaxed">
  Before we jump into calculations, let's make sure everyone has their environment launched and ready to go.
</p>

<div class="grid grid-cols-3 gap-x-6 max-w-3xl mx-auto text-center">
  
  <div v-click class="border border-sky-500/10 bg-black/20 p-5 rounded-xl backdrop-blur-sm">
    <div class="text-xs font-bold text-sky-400 uppercase tracking-wider mb-2">Step 1</div>
    <p class="text-lg font-semibold text-white mb-2">Open Navigator</p>
    <p class="text-xs opacity-50">Launch your terminal or Miniconda prompt</p>
  </div>

  <div v-click class="border border-sky-500/10 bg-black/20 p-5 rounded-xl backdrop-blur-sm">
    <div class="text-xs font-bold text-sky-400 uppercase tracking-wider mb-2">Step 2</div>
    <p class="text-lg font-semibold text-white mb-2">Activate Env</p>
    <p class="text-xs opacity-50 font-mono text-sky-200/70">conda activate daup</p>
  </div>

  <div v-click class="border border-sky-500/10 bg-black/20 p-5 rounded-xl backdrop-blur-sm">
    <div class="text-xs font-bold text-sky-400 uppercase tracking-wider mb-2">Step 3</div>
    <p class="text-lg font-semibold text-white mb-2">Open Spyder</p>
    <p class="text-xs opacity-50">Type <code>spyder</code> and press Enter</p>
  </div>

</div>

<style>
.slidev-page {
  background-color: #0b1120 !important;
}
</style>

---
layout: center
class: text-center
id: 14
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#38bdf8" />

<h2 class="text-5xl font-semibold mb-10 text-white">Mathematical Operations</h2>

<div class="grid grid-cols-2 gap-x-24 gap-y-6 text-left max-w-2xl mx-auto text-xl font-medium">
  <div>
    <ul class="space-y-4 list-circle-force">
      <li v-click>Addition (<code>+</code>)</li>
      <li v-click>Subtraction (<code>-</code>)</li>
      <li v-click>Multiplication (<code>*</code>)</li>
    </ul>
  </div>
  <div>
    <ul class="space-y-4 list-circle-force">
      <li v-click>Division (<code>/</code>)</li>
      <li v-click>Exponentiation (<code>**</code>)</li>
    </ul>
  </div>
</div>

<style>
.list-circle-force {
  list-style-type: circle !important;
  padding-left: 1.5rem;
}
.list-circle-force li {
  display: list-item !important;
}
.slidev-page {
  background-color: #0b1120 !important;
}
</style>

---
layout: center
class: text-center
id: 15
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#8b5cf6" />

<h2 class="text-4xl font-semibold mb-8 text-white">Practice Problem 1</h2>

<p class="text-xl text-white mb-6">
  Compute the following expression using Python arithmetic operators:
</p>

<div class="text-3xl font-bold text-purple-400 mb-8">

$$ y = 12 \times (5^3 - 45) + \frac{180}{4} $$

</div>

<div class="max-w-xl mx-auto text-left">
  <div v-click class="bg-black/40 p-4 rounded-xl font-mono text-sm border border-white/5">
    <div class="text-xs opacity-40 mb-2"># Python Implementation</div>
    <pre class="m-0 text-violet-300 font-bold">y = 12 * (5 ** 3 - 45) + 180 / 4
print(y)  # Output: 1005.0</pre>
  </div>
</div>

<style>
.slidev-page {
  background-color: #111317 !important;
}
</style>

---
layout: center
class: text-center
id: 16
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#8b5cf6" />

<h2 class="text-4xl font-semibold mb-8 text-white">Practice Problem 2</h2>

<p class="text-xl text-white mb-6">
  Compute the following expression using Python arithmetic operators:
</p>

<div class="text-3xl font-bold text-purple-400 mb-8">

$$ z = \sqrt{144} \times 2.5^2 - \frac{250}{5} $$

</div>

<div class="max-w-xl mx-auto text-left">
  <div v-click class="bg-black/40 p-4 rounded-xl font-mono text-sm border border-white/5">
    <div class="text-xs opacity-40 mb-2"># Python Implementation</div>
    <pre class="m-0 text-violet-300 font-bold">z = (144 ** 0.5) * (2.5 ** 2) - 250 / 5
print(z)  # Output: 25.0</pre>
  </div>
</div>

<style>
.slidev-page {
  background-color: #111317 !important;
}
</style>

---
layout: center
class: text-center
id: 17
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#8b5cf6" />

<h2 class="text-4xl font-semibold mb-8 text-white">Practice Problem 3</h2>

<p class="text-xl text-white mb-6">
  Find both the <strong>floor division</strong> value and the <strong>remainder</strong> for:
</p>

<div class="text-3xl font-bold text-purple-400 mb-8">

$$ \frac{3^8}{7} $$

</div>

<div class="max-w-xl mx-auto text-left">
  <div v-click class="bg-black/40 p-4 rounded-xl font-mono text-sm border border-white/5">
    <div class="text-xs opacity-40 mb-2"># Python Implementation</div>
    <pre class="m-0 text-violet-300 font-bold">floor_div = 3 ** 8 // 7  # Output: 937
remainder = 3 ** 8 % 7   # Output: 2
print(floor_div, remainder)</pre>
  </div>
</div>

<style>
.slidev-page {
  background-color: #111317 !important;
}
</style>

---
layout: center
class: text-center
id: 18
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#8b5cf6" />

<h2 class="text-4xl font-semibold mb-6 text-white">Practice Problem 4</h2>

<div class="max-w-2xl mx-auto mb-8 text-left border border-white/5 bg-black/20 p-6 rounded-xl backdrop-blur-sm text-xl text-white leading-relaxed">
  A database contains <span class="text-purple-400 font-semibold">1,200 records</span>. Over an hour, the dataset grows by <span class="text-purple-400 font-semibold">15%</span>. If a maintenance script immediately deletes <span class="text-purple-400 font-semibold">80 invalid rows</span> right after, what is the final record count?
</div>

<div class="max-w-2xl mx-auto text-left">
  <div v-click class="bg-black/40 p-4 rounded-xl font-mono text-sm border border-white/5">
    <div class="text-xs opacity-40 mb-2"># Python Implementation</div>
    <pre class="m-0 text-violet-300 font-bold">final_count = (1200 * 1.15) - 80
print(final_count)  # Output: 1300.0</pre>
  </div>
</div>

<style>
.slidev-page {
  background-color: #111317 !important;
}
</style>

---
layout: center
class: text-center
id: 19
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.003" :thickness="100" baseColor="#8b5cf6" />

<h2 class="text-4xl font-semibold mb-6 text-white">Practice Problem 5</h2>

<div class="max-w-2xl mx-auto mb-8 text-left border border-white/5 bg-black/20 p-6 rounded-xl backdrop-blur-sm text-xl text-white leading-relaxed">
  A remote telemetry system logs a primary sensor frequency reading of <span class="text-purple-400 font-semibold">45.2 Hz</span>. Write a script to square this reading, multiply it by <span class="text-purple-400 font-semibold">3</span>, and distribute the final outcome evenly among <span class="text-purple-400 font-semibold">4 storage pipelines</span>.
</div>

<div class="max-w-2xl mx-auto text-left">
  <div v-click class="bg-black/40 p-4 rounded-xl font-mono text-sm border border-white/5">
    <div class="text-xs opacity-40 mb-2"># Python Implementation</div>
    <pre class="m-0 text-violet-300 font-bold">pipeline_value = ((45.2 ** 2) * 3) / 4
print(pipeline_value)  # Output: 1532.28</pre>
  </div>
</div>

<style>
.slidev-page {
  background-color: #111317 !important;
}
</style>

---
layout: center
class: text-center
id: 20
---
<MathFrame v-if="$slidev.nav.currentPage === $frontmatter.id" :speed="0.005" :thickness="150" baseColor="#10b981" />

# Thank You
<span class='text-xs'> *Presented by* </span> <br>
<span class="font-display">Harsh Jinger</span>

## Data Analysis Using Python

<div @click="$slidev.nav.next" class="mt-12 py-1 text-xs opacity-40">
  End of Presentation
</div>
