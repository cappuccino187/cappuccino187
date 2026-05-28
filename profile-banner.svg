<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
     viewBox="0 0 860 620" width="860" height="620">
  <defs>
    <style>
      @import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&amp;family=Bebas+Neue&amp;display=swap');

      .mono { font-family: 'Share Tech Mono', 'Courier New', monospace; }
      .display { font-family: 'Bebas Neue', 'Arial Narrow', sans-serif; }

      /* scanline flicker */
      @keyframes flicker {
        0%,100% { opacity:1 } 92% { opacity:1 } 93% { opacity:0.85 } 94% { opacity:1 } 96% { opacity:0.9 } 97% { opacity:1 }
      }
      @keyframes dash-move {
        to { stroke-dashoffset: -40; }
      }
      @keyframes bar1 {
        0%   { width: 0px; }
        60%  { width: 0px; }
        100% { width: 505px; }
      }
      @keyframes bar2 {
        0%   { width: 0px; }
        68%  { width: 0px; }
        100% { width: 300px; }
      }
      @keyframes bar3 {
        0%   { width: 0px; }
        76%  { width: 0px; }
        100% { width: 198px; }
      }
      @keyframes glow-pulse {
        0%,100% { filter: drop-shadow(0 0 6px #FF6A00); }
        50%      { filter: drop-shadow(0 0 18px #FF6A00) drop-shadow(0 0 40px #FF6A00AA); }
      }
      @keyframes title-in {
        from { opacity:0; letter-spacing: 0.4em; }
        to   { opacity:1; letter-spacing: 0.15em; }
      }
      @keyframes fade-up {
        from { opacity:0; transform: translateY(12px); }
        to   { opacity:1; transform: translateY(0); }
      }
      @keyframes scan {
        0%   { transform: translateY(-100%); opacity:0.07; }
        100% { transform: translateY(660px); opacity:0.07; }
      }
      @keyframes corner-draw {
        from { stroke-dashoffset: 120; }
        to   { stroke-dashoffset: 0; }
      }
      @keyframes blink {
        0%,100% { opacity:1 } 50% { opacity:0 }
      }
      @keyframes orbit {
        from { transform: rotate(0deg) translateX(28px) rotate(0deg); }
        to   { transform: rotate(360deg) translateX(28px) rotate(-360deg); }
      }
    </style>

    <!-- background grid pattern -->
    <pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse">
      <path d="M 40 0 L 0 0 0 40" fill="none" stroke="#1a1a1a" stroke-width="0.5"/>
    </pattern>

    <!-- orange glow filter -->
    <filter id="glow" x="-30%" y="-30%" width="160%" height="160%">
      <feGaussianBlur stdDeviation="4" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="glow-strong" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="8" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="text-glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>

    <!-- clipping for progress bars -->
    <clipPath id="clip-bar1"><rect x="0" y="0" width="640" height="14" rx="2"/></clipPath>
    <clipPath id="clip-bar2"><rect x="0" y="0" width="640" height="14" rx="2"/></clipPath>
    <clipPath id="clip-bar3"><rect x="0" y="0" width="640" height="14" rx="2"/></clipPath>

    <!-- noise texture overlay -->
    <filter id="noise">
      <feTurbulence type="fractalNoise" baseFrequency="0.65" numOctaves="3" stitchTiles="stitch"/>
      <feColorMatrix type="saturate" values="0"/>
      <feBlend in="SourceGraphic" mode="overlay" result="blend"/>
      <feComposite in="blend" in2="SourceGraphic" operator="in"/>
    </filter>

    <!-- diagonal hatch pattern -->
    <pattern id="hatch" width="8" height="8" patternUnits="userSpaceOnUse" patternTransform="rotate(45)">
      <line x1="0" y1="0" x2="0" y2="8" stroke="#FF6A00" stroke-width="0.4" stroke-opacity="0.15"/>
    </pattern>

    <linearGradient id="bg-grad" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0%" stop-color="#0a0a0a"/>
      <stop offset="100%" stop-color="#111008"/>
    </linearGradient>
    <linearGradient id="orange-grad" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0%" stop-color="#FF6A00"/>
      <stop offset="100%" stop-color="#FF9D00"/>
    </linearGradient>
    <linearGradient id="bar-grad" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0%" stop-color="#FF6A00"/>
      <stop offset="70%" stop-color="#FF9D00"/>
      <stop offset="100%" stop-color="#FFD000"/>
    </linearGradient>
    <linearGradient id="side-grad" x1="0" y1="0" x2="0" y2="1">
      <stop offset="0%" stop-color="#FF6A00" stop-opacity="0"/>
      <stop offset="50%" stop-color="#FF6A00" stop-opacity="0.8"/>
      <stop offset="100%" stop-color="#FF6A00" stop-opacity="0"/>
    </linearGradient>
  </defs>

  <!-- ── BASE ── -->
  <rect width="860" height="620" fill="url(#bg-grad)"/>
  <rect width="860" height="620" fill="url(#grid)"/>
  <rect width="860" height="620" fill="url(#hatch)"/>

  <!-- scanline sweep -->
  <rect x="0" y="0" width="860" height="60" fill="url(#orange-grad)" opacity="0.04">
    <animateTransform attributeName="transform" type="translate" from="0,-60" to="0,680"
      dur="4s" repeatCount="indefinite"/>
  </rect>

  <!-- ── BORDER FRAME ── -->
  <!-- outer border -->
  <rect x="10" y="10" width="840" height="600" fill="none" stroke="#FF6A00" stroke-width="1" stroke-opacity="0.3"/>
  <!-- inner border -->
  <rect x="16" y="16" width="828" height="588" fill="none" stroke="#FF6A00" stroke-width="0.4" stroke-opacity="0.15"/>

  <!-- animated dashed border -->
  <rect x="10" y="10" width="840" height="600" fill="none" stroke="#FF6A00" stroke-width="0.8"
        stroke-dasharray="6 14" stroke-opacity="0.5">
    <animate attributeName="stroke-dashoffset" from="0" to="-80" dur="3s" repeatCount="indefinite"/>
  </rect>

  <!-- corner decorations — top-left -->
  <polyline points="10,50 10,10 50,10" fill="none" stroke="#FF6A00" stroke-width="2.5"
            stroke-dasharray="120" stroke-dashoffset="120">
    <animate attributeName="stroke-dashoffset" from="120" to="0" dur="0.8s" fill="freeze" begin="0.1s"/>
  </polyline>
  <polyline points="10,50 10,10 50,10" fill="none" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
  <!-- corner — top-right -->
  <polyline points="810,10 850,10 850,50" fill="none" stroke="#FF6A00" stroke-width="2.5"
            stroke-dasharray="120" stroke-dashoffset="120">
    <animate attributeName="stroke-dashoffset" from="120" to="0" dur="0.8s" fill="freeze" begin="0.2s"/>
  </polyline>
  <!-- corner — bottom-left -->
  <polyline points="10,570 10,610 50,610" fill="none" stroke="#FF6A00" stroke-width="2.5"
            stroke-dasharray="120" stroke-dashoffset="120">
    <animate attributeName="stroke-dashoffset" from="120" to="0" dur="0.8s" fill="freeze" begin="0.3s"/>
  </polyline>
  <!-- corner — bottom-right -->
  <polyline points="810,610 850,610 850,570" fill="none" stroke="#FF6A00" stroke-width="2.5"
            stroke-dasharray="120" stroke-dashoffset="120">
    <animate attributeName="stroke-dashoffset" from="120" to="0" dur="0.8s" fill="freeze" begin="0.4s"/>
  </polyline>

  <!-- side accent lines -->
  <line x1="10" y1="200" x2="10" y2="420" stroke="url(#side-grad)" stroke-width="2"/>
  <line x1="850" y1="200" x2="850" y2="420" stroke="url(#side-grad)" stroke-width="2"/>

  <!-- top-left label -->
  <text x="24" y="9" class="mono" font-size="8" fill="#FF6A00" opacity="0.5">SYS.PROFILE</text>
  <!-- top-right label -->
  <text x="700" y="9" class="mono" font-size="8" fill="#FF6A00" opacity="0.5">VER.2.1 // ACTIVE</text>
  <!-- bottom-left -->
  <text x="24" y="619" class="mono" font-size="8" fill="#FF6A00" opacity="0.4">CAPPUCCINO_17</text>
  <!-- bottom-right -->
  <text x="750" y="619" class="mono" font-size="8" fill="#FF6A00" opacity="0.4">2024</text>

  <!-- ── DECORATIVE LEFT COLUMN ── -->
  <!-- vertical dotted line -->
  <line x1="60" y1="30" x2="60" y2="590" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.2"
        stroke-dasharray="3 6"/>
  <!-- small squares -->
  <rect x="54" y="105" width="12" height="12" fill="none" stroke="#FF6A00" stroke-width="1" stroke-opacity="0.4"/>
  <rect x="57" y="108" width="6" height="6" fill="#FF6A00" opacity="0.3"/>
  <rect x="54" y="290" width="12" height="12" fill="none" stroke="#FF6A00" stroke-width="1" stroke-opacity="0.4"/>
  <rect x="57" y="293" width="6" height="6" fill="#FF6A00" opacity="0.3"/>
  <rect x="54" y="475" width="12" height="12" fill="none" stroke="#FF6A00" stroke-width="1" stroke-opacity="0.4"/>
  <rect x="57" y="478" width="6" height="6" fill="#FF6A00" opacity="0.3"/>

  <!-- ── DECORATIVE RIGHT COLUMN ── -->
  <line x1="800" y1="30" x2="800" y2="590" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.2"
        stroke-dasharray="3 6"/>
  <!-- hex-ish markers -->
  <polygon points="800,180 807,184 807,192 800,196 793,192 793,184" fill="none" stroke="#FF6A00"
           stroke-width="0.8" stroke-opacity="0.5"/>
  <polygon points="800,380 807,384 807,392 800,396 793,392 793,384" fill="none" stroke="#FF6A00"
           stroke-width="0.8" stroke-opacity="0.5">
    <animate attributeName="stroke-opacity" values="0.5;1;0.5" dur="2s" repeatCount="indefinite"/>
  </polygon>

  <!-- ── HEADER AREA ── -->
  <!-- horizontal divider lines top -->
  <line x1="80" y1="130" x2="780" y2="130" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.25"/>
  <line x1="80" y1="132" x2="780" y2="132" stroke="#FF6A00" stroke-width="0.2" stroke-opacity="0.1"/>

  <!-- dot-row decoration above title -->
  <g opacity="0.35">
    <circle cx="90"  cy="65" r="1.5" fill="#FF6A00"/>
    <circle cx="98"  cy="65" r="1.5" fill="#FF6A00"/>
    <circle cx="106" cy="65" r="1.5" fill="#FF6A00"/>
    <rect x="114" y="63" width="8" height="4" rx="1" fill="#FF6A00"/>
    <rect x="126" y="63" width="20" height="4" rx="1" fill="#FF6A00"/>
    <rect x="150" y="63" width="12" height="4" rx="1" fill="#FF6A00"/>
  </g>

  <!-- STATUS BADGE -->
  <rect x="680" y="52" width="110" height="22" rx="2" fill="#FF6A00" opacity="0.12"/>
  <rect x="680" y="52" width="110" height="22" rx="2" fill="none" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.6"/>
  <circle cx="694" cy="63" r="3.5" fill="#FF6A00">
    <animate attributeName="opacity" values="1;0.3;1" dur="1.5s" repeatCount="indefinite"/>
  </circle>
  <text x="702" y="67" class="mono" font-size="9" fill="#FF6A00">ONLINE</text>

  <!-- MAIN TITLE -->
  <text x="90" y="118" class="display" font-size="64" fill="url(#orange-grad)" filter="url(#text-glow)"
        letter-spacing="0.15em" opacity="0">
    CAPPUCCINO_17
    <animate attributeName="opacity" from="0" to="1" dur="0.6s" fill="freeze" begin="0.3s"/>
    <animate attributeName="letter-spacing" from="0.4em" to="0.15em" dur="0.6s" fill="freeze" begin="0.3s"/>
  </text>
  <!-- title underscore glow line -->
  <rect x="90" y="122" width="680" height="2" fill="url(#orange-grad)" opacity="0">
    <animate attributeName="width" from="0" to="680" dur="0.5s" fill="freeze" begin="0.8s"/>
    <animate attributeName="opacity" from="0" to="0.7" dur="0.5s" fill="freeze" begin="0.8s"/>
  </rect>
  <rect x="90" y="124" width="680" height="1" fill="url(#orange-grad)" opacity="0">
    <animate attributeName="width" from="0" to="680" dur="0.5s" fill="freeze" begin="0.9s"/>
    <animate attributeName="opacity" from="0" to="0.2" dur="0.5s" fill="freeze" begin="0.9s"/>
  </rect>

  <!-- SUBTITLE -->
  <text x="92" y="148" class="mono" font-size="11" fill="#888" letter-spacing="0.2em" opacity="0">
    DEVELOPER  /  PIXEL ARTIST  /  3D ARTIST
    <animate attributeName="opacity" from="0" to="1" dur="0.5s" fill="freeze" begin="1s"/>
  </text>

  <!-- EXPERIENCE BADGE -->
  <rect x="92" y="158" width="130" height="18" rx="1" fill="#FF6A00" opacity="0.08"/>
  <rect x="92" y="158" width="130" height="18" rx="1" fill="none" stroke="#FF6A00" stroke-width="0.6" stroke-opacity="0.5"/>
  <text x="157" y="170" class="mono" font-size="9" fill="#FF6A00" text-anchor="middle" opacity="0">
    EXP: 2+ YEARS
    <animate attributeName="opacity" from="0" to="1" dur="0.4s" fill="freeze" begin="1.1s"/>
  </text>

  <!-- ── SECTION DIVIDER ── -->
  <line x1="80" y1="194" x2="780" y2="194" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.25"/>
  <text x="90" y="191" class="mono" font-size="8" fill="#FF6A00" opacity="0.4">// SKILLS</text>
  <text x="750" y="191" class="mono" font-size="8" fill="#FF6A00" opacity="0.4" text-anchor="end">03</text>

  <!-- ── SKILLS BLOCK ── -->

  <!-- SKILL 1: WEBSITE DEVELOPMENT -->
  <g opacity="0">
    <animate attributeName="opacity" from="0" to="1" dur="0.4s" fill="freeze" begin="1.2s"/>

    <!-- label row -->
    <text x="90" y="226" class="mono" font-size="10" fill="#CCC" letter-spacing="0.12em">WEBSITE DEVELOPMENT</text>
    <text x="770" y="226" class="mono" font-size="10" fill="#FF6A00" text-anchor="end" filter="url(#glow)">79%</text>

    <!-- tick marks -->
    <line x1="90"  y1="232" x2="90"  y2="238" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.4"/>
    <line x1="250" y1="232" x2="250" y2="238" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="410" y1="232" x2="410" y2="238" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="570" y1="232" x2="570" y2="238" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="770" y1="232" x2="770" y2="238" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.4"/>

    <!-- track -->
    <rect x="90" y="238" width="680" height="10" rx="2" fill="#1a1a1a"/>
    <rect x="90" y="238" width="680" height="10" rx="2" fill="none" stroke="#333" stroke-width="0.8"/>

    <!-- fill bar -->
    <rect x="90" y="238" height="10" rx="2" fill="url(#bar-grad)" width="0">
      <animate attributeName="width" from="0" to="537" dur="1s" fill="freeze" begin="1.4s" calcMode="spline"
               keySplines="0.4 0 0.2 1" keyTimes="0;1"/>
    </rect>
    <!-- bar shimmer -->
    <rect x="90" y="239" height="3" rx="1" fill="white" opacity="0.15" width="0">
      <animate attributeName="width" from="0" to="537" dur="1s" fill="freeze" begin="1.4s"/>
    </rect>
    <!-- bar end glow -->
    <rect x="90" y="237" width="6" height="12" rx="1" fill="#FFD000" filter="url(#glow)" opacity="0">
      <animate attributeName="x" from="90" to="621" dur="1s" fill="freeze" begin="1.4s"/>
      <animate attributeName="opacity" from="0" to="0.9" dur="0.1s" fill="freeze" begin="1.4s"/>
    </rect>

    <!-- sub-label -->
    <text x="90" y="262" class="mono" font-size="7.5" fill="#555" letter-spacing="0.08em">0%</text>
    <text x="770" y="262" class="mono" font-size="7.5" fill="#555" letter-spacing="0.08em" text-anchor="end">100%</text>
  </g>

  <!-- SKILL 2: PIXEL ART -->
  <g opacity="0">
    <animate attributeName="opacity" from="0" to="1" dur="0.4s" fill="freeze" begin="1.5s"/>

    <text x="90" y="302" class="mono" font-size="10" fill="#CCC" letter-spacing="0.12em">PIXEL ART  16x16</text>
    <text x="770" y="302" class="mono" font-size="10" fill="#FF6A00" text-anchor="end" filter="url(#glow)">47%</text>

    <line x1="90"  y1="308" x2="90"  y2="314" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.4"/>
    <line x1="250" y1="308" x2="250" y2="314" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="410" y1="308" x2="410" y2="314" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="570" y1="308" x2="570" y2="314" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="770" y1="308" x2="770" y2="314" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.4"/>

    <rect x="90" y="314" width="680" height="10" rx="2" fill="#1a1a1a"/>
    <rect x="90" y="314" width="680" height="10" rx="2" fill="none" stroke="#333" stroke-width="0.8"/>

    <rect x="90" y="314" height="10" rx="2" fill="url(#bar-grad)" width="0">
      <animate attributeName="width" from="0" to="320" dur="1s" fill="freeze" begin="1.7s" calcMode="spline"
               keySplines="0.4 0 0.2 1" keyTimes="0;1"/>
    </rect>
    <rect x="90" y="315" height="3" rx="1" fill="white" opacity="0.15" width="0">
      <animate attributeName="width" from="0" to="320" dur="1s" fill="freeze" begin="1.7s"/>
    </rect>
    <rect x="90" y="313" width="6" height="12" rx="1" fill="#FFD000" filter="url(#glow)" opacity="0">
      <animate attributeName="x" from="90" to="404" dur="1s" fill="freeze" begin="1.7s"/>
      <animate attributeName="opacity" from="0" to="0.9" dur="0.1s" fill="freeze" begin="1.7s"/>
    </rect>

    <text x="90" y="338" class="mono" font-size="7.5" fill="#555" letter-spacing="0.08em">0%</text>
    <text x="770" y="338" class="mono" font-size="7.5" fill="#555" letter-spacing="0.08em" text-anchor="end">100%</text>
  </g>

  <!-- SKILL 3: BLENDER -->
  <g opacity="0">
    <animate attributeName="opacity" from="0" to="1" dur="0.4s" fill="freeze" begin="1.8s"/>

    <text x="90" y="378" class="mono" font-size="10" fill="#CCC" letter-spacing="0.12em">BLENDER RENDERS</text>
    <text x="770" y="378" class="mono" font-size="10" fill="#FF6A00" text-anchor="end" filter="url(#glow)">31%</text>

    <line x1="90"  y1="384" x2="90"  y2="390" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.4"/>
    <line x1="250" y1="384" x2="250" y2="390" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="410" y1="384" x2="410" y2="390" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="570" y1="384" x2="570" y2="390" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.3"/>
    <line x1="770" y1="384" x2="770" y2="390" stroke="#FF6A00" stroke-width="0.8" stroke-opacity="0.4"/>

    <rect x="90" y="390" width="680" height="10" rx="2" fill="#1a1a1a"/>
    <rect x="90" y="390" width="680" height="10" rx="2" fill="none" stroke="#333" stroke-width="0.8"/>

    <rect x="90" y="390" height="10" rx="2" fill="url(#bar-grad)" width="0">
      <animate attributeName="width" from="0" to="211" dur="1s" fill="freeze" begin="2s" calcMode="spline"
               keySplines="0.4 0 0.2 1" keyTimes="0;1"/>
    </rect>
    <rect x="90" y="391" height="3" rx="1" fill="white" opacity="0.15" width="0">
      <animate attributeName="width" from="0" to="211" dur="1s" fill="freeze" begin="2s"/>
    </rect>
    <rect x="90" y="389" width="6" height="12" rx="1" fill="#FFD000" filter="url(#glow)" opacity="0">
      <animate attributeName="x" from="90" to="295" dur="1s" fill="freeze" begin="2s"/>
      <animate attributeName="opacity" from="0" to="0.9" dur="0.1s" fill="freeze" begin="2s"/>
    </rect>

    <text x="90" y="414" class="mono" font-size="7.5" fill="#555" letter-spacing="0.08em">0%</text>
    <text x="770" y="414" class="mono" font-size="7.5" fill="#555" letter-spacing="0.08em" text-anchor="end">100%</text>
  </g>

  <!-- ── SECTION DIVIDER ── -->
  <line x1="80" y1="440" x2="780" y2="440" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.25"/>
  <text x="90" y="437" class="mono" font-size="8" fill="#FF6A00" opacity="0.4">// CONTACT</text>
  <text x="750" y="437" class="mono" font-size="8" fill="#FF6A00" opacity="0.4" text-anchor="end">02</text>

  <!-- ── CONTACT BLOCK ── -->

  <!-- DISCORD BADGE -->
  <g opacity="0">
    <animate attributeName="opacity" from="0" to="1" dur="0.5s" fill="freeze" begin="2.3s"/>
    <a href="https://discord.com/users/cappuccino_17">
      <!-- outer glow rect -->
      <rect x="160" y="460" width="200" height="50" rx="3" fill="#FF6A00" opacity="0.04" filter="url(#glow)"/>
      <!-- main badge -->
      <rect x="160" y="460" width="200" height="50" rx="3" fill="#0f0f0f"/>
      <rect x="160" y="460" width="200" height="50" rx="3" fill="none" stroke="#FF6A00" stroke-width="1" stroke-opacity="0.6"/>
      <!-- top accent line -->
      <rect x="160" y="460" width="200" height="2" rx="1" fill="url(#orange-grad)" opacity="0.7"/>
      <!-- left accent -->
      <rect x="160" y="460" width="3" height="50" rx="1" fill="url(#orange-grad)" opacity="0.5"/>

      <!-- discord icon — simplified SVG path -->
      <g transform="translate(178, 479) scale(0.85)">
        <path d="M18.59 5.89C17.18 5.23 15.67 4.74 14.1 4.5c-.18.32-.38.75-.52 1.09-1.66-.25-3.3-.25-4.93 0-.14-.34-.35-.77-.53-1.09C6.55 4.74 5.04 5.23 3.63 5.9 .52 10.65-.32 15.28.1 19.85c2.01 1.47 3.96 2.37 5.88 2.96.48-.64.9-1.32 1.27-2.04-.7-.26-1.37-.58-2-.96.17-.12.33-.25.49-.37 3.86 1.77 8.04 1.77 11.86 0 .16.13.32.25.49.37-.63.38-1.3.7-2 .96.37.72.79 1.4 1.27 2.04 1.92-.59 3.87-1.49 5.88-2.96.49-5.27-.83-9.85-3.75-13.96zM8.01 16.96c-1.14 0-2.08-1.04-2.08-2.32s.91-2.32 2.08-2.32 2.1 1.04 2.08 2.32c0 1.28-.92 2.32-2.08 2.32zm7.98 0c-1.14 0-2.08-1.04-2.08-2.32s.91-2.32 2.08-2.32c1.16 0 2.1 1.04 2.08 2.32 0 1.28-.92 2.32-2.08 2.32z" fill="#FF6A00" opacity="0.9"/>
      </g>

      <text x="216" y="481" class="mono" font-size="8" fill="#FF6A00" opacity="0.5" letter-spacing="0.1em">DISCORD</text>
      <text x="216" y="499" class="mono" font-size="11" fill="#EEE" letter-spacing="0.08em">cappuccino_17</text>
    </a>
  </g>

  <!-- TELEGRAM BADGE -->
  <g opacity="0">
    <animate attributeName="opacity" from="0" to="1" dur="0.5s" fill="freeze" begin="2.5s"/>
    <a href="https://t.me/cappuccino_17">
      <rect x="500" y="460" width="200" height="50" rx="3" fill="#FF6A00" opacity="0.04" filter="url(#glow)"/>
      <rect x="500" y="460" width="200" height="50" rx="3" fill="#0f0f0f"/>
      <rect x="500" y="460" width="200" height="50" rx="3" fill="none" stroke="#FF6A00" stroke-width="1" stroke-opacity="0.6"/>
      <rect x="500" y="460" width="200" height="2" rx="1" fill="url(#orange-grad)" opacity="0.7"/>
      <rect x="500" y="460" width="3" height="50" rx="1" fill="url(#orange-grad)" opacity="0.5"/>

      <!-- telegram icon -->
      <g transform="translate(518, 477) scale(0.85)">
        <path d="M22.26 2.01L1.36 10.25c-1.42.57-1.41 1.36-.26 1.71l5.27 1.65 12.18-7.68c.57-.35 1.1-.16.67.22L8.74 17.23l-.39 5.58c.57 0 .82-.26 1.14-.57l2.73-2.65 5.68 4.19c1.05.58 1.8.28 2.06-.97L23.93 3.6c.38-1.52-.58-2.21-1.67-1.59z" fill="#FF6A00" opacity="0.9"/>
      </g>

      <text x="554" y="481" class="mono" font-size="8" fill="#FF6A00" opacity="0.5" letter-spacing="0.1em">TELEGRAM</text>
      <text x="554" y="499" class="mono" font-size="11" fill="#EEE" letter-spacing="0.08em">@cappuccino_17</text>
    </a>
  </g>

  <!-- connector line between badges -->
  <line x1="362" y1="485" x2="498" y2="485" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.3"
        stroke-dasharray="3 4" opacity="0">
    <animate attributeName="opacity" from="0" to="1" dur="0.3s" fill="freeze" begin="2.6s"/>
  </line>
  <circle cx="430" cy="485" r="2" fill="#FF6A00" opacity="0">
    <animate attributeName="opacity" from="0" to="0.5" dur="0.3s" fill="freeze" begin="2.7s"/>
    <animate attributeName="r" values="2;3;2" dur="2s" repeatCount="indefinite" begin="3s"/>
  </circle>

  <!-- ── BOTTOM DECORATIVE ROW ── -->
  <line x1="80" y1="540" x2="780" y2="540" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.2"/>

  <!-- bottom dots -->
  <g opacity="0.3">
    <circle cx="90"  cy="560" r="1.2" fill="#FF6A00"/>
    <circle cx="100" cy="560" r="1.2" fill="#FF6A00"/>
    <circle cx="110" cy="560" r="1.2" fill="#FF6A00"/>
    <circle cx="120" cy="560" r="1.2" fill="#FF6A00"/>
    <circle cx="130" cy="560" r="1.2" fill="#FF6A00">
      <animate attributeName="opacity" values="0.3;1;0.3" dur="1.2s" repeatCount="indefinite"/>
    </circle>
  </g>

  <!-- bottom center text -->
  <text x="430" y="562" class="mono" font-size="8" fill="#444" text-anchor="middle" letter-spacing="0.2em">
    BUILT WITH PRECISION
  </text>

  <!-- right dots -->
  <g opacity="0.3" transform="scale(-1,1) translate(-770,0)">
    <circle cx="90"  cy="560" r="1.2" fill="#FF6A00"/>
    <circle cx="100" cy="560" r="1.2" fill="#FF6A00"/>
    <circle cx="110" cy="560" r="1.2" fill="#FF6A00"/>
    <circle cx="120" cy="560" r="1.2" fill="#FF6A00"/>
    <circle cx="130" cy="560" r="1.2" fill="#FF6A00"/>
  </g>

  <!-- ── BACKGROUND DECORATIVE ELEMENTS ── -->
  <!-- large faint circle top-right -->
  <circle cx="790" cy="80" r="60" fill="none" stroke="#FF6A00" stroke-width="0.4" stroke-opacity="0.08"
          stroke-dasharray="4 8"/>
  <circle cx="790" cy="80" r="40" fill="none" stroke="#FF6A00" stroke-width="0.3" stroke-opacity="0.06"/>

  <!-- large faint circle bottom-left -->
  <circle cx="70" cy="540" r="50" fill="none" stroke="#FF6A00" stroke-width="0.4" stroke-opacity="0.08"
          stroke-dasharray="4 8"/>

  <!-- cross-hair top-right -->
  <line x1="770" y1="70" x2="810" y2="70" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.2"/>
  <line x1="790" y1="50" x2="790" y2="90" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.2"/>
  <circle cx="790" cy="70" r="4" fill="none" stroke="#FF6A00" stroke-width="0.5" stroke-opacity="0.25"/>

  <!-- flicker overlay (very subtle) -->
  <rect width="860" height="620" fill="transparent" opacity="0.03"
        style="animation: flicker 8s infinite;"/>

</svg>
