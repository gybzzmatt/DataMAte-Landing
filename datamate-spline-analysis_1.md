# DataMate — Reactive Orb Spline Analysis
## scene__1_.splinecode · Decoded Structure Report

---

## 1. ARCHIVO: ESTRUCTURA INTERNA

**Formato:** MessagePack binary (no JSON)  
**Tamaño:** 65,720 bytes  
**Versión Spline:** schema con frames + shared objects

---

## 2. OBJETOS DE LA ESCENA

```
Scene 1
├── Page (root container)
│   ├── CTA (Empty group)
│   │   ├── Rectangle → "Rectangle Material" (botón JOIN US NOW)
│   │   ├── Text  → "Text Material"   ("Effortless")
│   │   ├── Text 2 → "Text 2 Material" ("for business")
│   │   ├── Text 3 → "Text 3 Material" ("No extra setup...")
│   │   └── Text 4 → "Text 4 Material" ("AI integration")
│   ├── Clones (Empty group — rotación continua animada)
│   │   ├── Clone 0  ─┐
│   │   ├── Clone 1   │
│   │   ├── Clone 2   │  Todos instancian el mismo
│   │   ├── ...       │  componente esfera:
│   │   └── Clone 39 ─┘  $c9011857-70d3-418b-9339-1515357d1604
│   └── Cursor (Mesh SphereGeometry — sigue al mouse)
│       └── "ursor Material" (Cursor Material)
└── Personal Camera (Perspective + Orthographic)
```

**Total clones:** 40 instancias del mismo componente esfera  
**Fonts:** Manrope_700 (CTA), Manrope_regular (body text)

---

## 3. SISTEMA DE MATERIALES

### Componente esfera (Clone component)
```
Material layers:
├── phongQ     → base shading type
├── light      → color base: #333333 (muy oscuro)
├── layer1     → depth gradient (dark → black, efecto profundidad)
├── layer2     → gradient con color stops (aquí vive el verde/teal)
│               near/far → interpolación de colores 3D
├── depth      → depth-based color blending
└── fresnelF   → rim light / edge glow effect
```

### BG Material (fondo plano)
```
├── layer2 (gradient)
│   ├── colors + steps
│   ├── near / far
└── phongQ + light #333333
```

### Rectangle Material (botón CTA)
```
├── layer2h (gradient highlight)
├── phongQ + light #333333
└── layer1 (depth)
    near/far color stops: >RnK / /9*@ / S%2I
```

### Text Materials (x4)
```
├── colorQ → color principal del texto
├── phongQ + light #333333
└── layer1h + depth
    fresnelF → "for business" (color teal)
```

---

## 4. ANIMACIONES Y COMPORTAMIENTOS

```
Clones group:
  └── Rotation animation → State: pingpong-rewind + Once
      Tween: duration continua, easing suave

Cursor object:
  └── Follow behavior → plane XY
      resetOnPointerLeave: false
      Follow cursor → custom target

Events detectados:
  ├── Start (trigger: página carga)
  ├── Transition
  └── Conditional (Toggle state en hover)
```

---

## 5. POST-PROCESSING ACTIVO

```
├── bloom         → glow en edges iluminados
├── chromaticAberration → fringe color en bordes
├── vignette      → oscurecimiento en esquinas
├── depthOfField  → bokeh/blur en profundidad
├── hueSaturation → control de saturación global
├── brightnessContrast → contraste
└── noise         → grain sutil
```

---

## 6. CÓMO EDITAR A BRAND DATAMATE EN SPLINE

### Cambios de color exactos:

**Paso 1: Esfera principal**
```
Objects panel → Clones → any Clone → "Go to component"

Layer 2 (gradient):
  Color stop 1: #00FFB3 (mint — frente/lit side)
  Color stop 2: #746AFC (violet — mid)
  Color stop 3: #000000 (black — back/dark side)

Layer 1 (depth):
  near: #00FFB3 at 8% opacity
  far:  #000000

fresnelF (rim):
  color: #00FFB3
  intensity: keep at 100
  bias: keep at current
```

**Paso 2: Fondo (BG Material)**
```
Background color → #000000
BG Material layer2 → gradient full black
```

**Paso 3: CTA botón**
```
Rectangle Material → color: #00FFB3
Text "JOIN US NOW" → color: #000000
```

**Paso 4: Textos**
```
Text "for business" colorQ → #00FFB3 (ya era teal — solo ajustar hex)
Text "Effortless / AI integration" colorQ → #FFFFFF
```

**Paso 5: Post-processing**
```
hueSaturation → hue shift: +148 (para empujar verde → mint)
bloom intensity → 0.4 (más glow en mint)
```

Después de editar: **Export → Public URL → Update → copiar .splinecode URL**

---

## 7. GOOGLE ANTIGRAVITY PROMPT

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PROMPT: DATAMATE REACTIVE ORB — BRAND ADAPTATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Create a 3D interactive data sphere for DataMate, 
an enterprise AI company. The sphere is composed 
of 40 smaller spherical nodes arranged in a 
geodesic/icosahedral pattern, forming one large 
reactive orb that rotates continuously and responds 
to mouse/cursor movement.

━━ GEOMETRY ━━
- Main structure: ~40 sphere instances arranged 
  in a 3D spherical formation (geodesic distribution)
- Each node: smooth sphere, diameter ~0.8 units
- Small gap between nodes (~0.05 units)
- The whole orb rotates slowly on Y axis, 
  animation: pingpong with smooth easing
- On hover/mouse proximity: orb reacts, 
  nearest nodes push or glow

━━ MATERIAL SYSTEM — DATAMATE BRAND ━━

Node base material (Phong):
  - Base color: #000000 (pure black)
  - Light color: #0A0A0A (almost black)

Node gradient layer (depth-based):
  - Near (front-facing): #00FFB3 (neon mint)
  - Mid: rgba(116, 106, 252, 0.6) (electric violet)
  - Far (back-facing): #000000 (pure black)
  - Interpolation: smooth cubic

Fresnel rim effect:
  - Color: #00FFB3 (mint)
  - Intensity: 100%
  - Bias: 0.1 (thin but sharp rim)
  - Creates neon edge glow on front spheres

Depth layer:
  - Near: #00FFB3 at 15% opacity
  - Far: transparent black
  - Creates "data node" depth illusion

━━ BACKGROUND ━━
  - Pure black: #000000
  - No gradients, no ambient fog visible
  - Slight radial vignette (darkness → edges)

━━ LIGHTING ━━
  - Ambient: very low, #0A0A0A, intensity 0.1
  - No direct lights (material-driven shading)
  - Post-processing bloom: intensity 0.4, 
    luminance threshold 0.6 (glows only on mint)

━━ POST-PROCESSING ━━
  - Bloom: ON — makes mint edges glow neon
  - Chromatic aberration: subtle (0.2) — 
    sci-fi edge fringe
  - Vignette: darkness 0.5 — corners go black
  - Depth of field: subtle bokeh on back nodes
  - Brightness/Contrast: contrast +0.15
  - No noise/grain

━━ CAMERA ━━
  - Perspective camera, FOV ~45°
  - Orb centered at (0, 0, 0)
  - Camera at Z +500, looking at center
  - Slight auto-orbit or parallax on mouse

━━ INTERACTION ━━
  - Cursor follow: orb tilts toward cursor (XY plane)
  - Reset on pointer leave: false (stays tilted)
  - On hover state: bloom intensity increases,
    front nodes brighten to full #00FFB3

━━ SCALE & COMPOSITION ━━
  - Orb occupies right 45% of viewport
  - Slight overflow beyond viewport right edge
  - Dark background bleeds into page background
  - No hard edges — soft vignette fade-out

━━ BRAND CONTEXT ━━
  Company: DataMate
  Primary: #00FFB3 (neon mint)
  Secondary: #746AFC (electric violet)
  Background: #000000 (pure black)
  Font: Roboto Mono (not part of 3D scene)
  Tagline: "Inteligencia Artificial centrada 
            en datos confiables"
  
  The sphere represents: a network of validated 
  human data nodes — each small sphere is one 
  expert data point contributing to a trustworthy 
  AI model. The mint glow = data confidence. 
  The violet depth = the hidden complexity 
  being resolved.

━━ STYLE REFERENCE ━━
  Base: Spline "Reactive Orb" template
  Color direction: Vercel/Linear dark + 
  neon mint accent
  Mood: enterprise AI, premium, trustworthy,
  data intelligence
  NOT: playful, colorful, warm, gradient-heavy

━━ OUTPUT FORMAT ━━
  - Spline scene (.splinecode)
  - Alternatively: Three.js scene with 
    InstancedMesh + custom ShaderMaterial
  - Embed-ready for hero section (right column)
  - Responsive: hide on mobile < 768px
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## 8. THREE.JS FALLBACK (Sin Spline)

Si prefieres construir la esfera directamente en Three.js
sin dependencia de Spline, aquí está el approach:

```javascript
// DataMate Reactive Orb — Three.js implementation
// Reemplaza el spline-viewer con este canvas nativo

const MINT = new THREE.Color(0x00FFB3);
const VIOLET = new THREE.Color(0x746AFC);
const BLACK = new THREE.Color(0x000000);

// Fibonacci sphere distribution (40 nodes)
function fibonacciSphere(count, radius) {
  const points = [];
  const phi = Math.PI * (3 - Math.sqrt(5));
  for (let i = 0; i < count; i++) {
    const y = 1 - (i / (count - 1)) * 2;
    const r = Math.sqrt(1 - y * y);
    const theta = phi * i;
    points.push(new THREE.Vector3(
      Math.cos(theta) * r * radius,
      y * radius,
      Math.sin(theta) * r * radius
    ));
  }
  return points;
}

// Instanced mesh for performance
const geometry = new THREE.SphereGeometry(18, 32, 32);
const material = new THREE.MeshPhongMaterial({
  color: 0x050505,
  emissive: 0x00FFB3,
  emissiveIntensity: 0.05,
  shininess: 120,
});

const mesh = new THREE.InstancedMesh(geometry, material, 40);
const positions = fibonacciSphere(40, 120);
const matrix = new THREE.Matrix4();

positions.forEach((pos, i) => {
  matrix.setPosition(pos);
  mesh.setMatrixAt(i, matrix);
  // Color gradient by Z depth
  const t = (pos.z + 120) / 240; // 0 = back, 1 = front
  const color = VIOLET.clone().lerp(MINT, t);
  mesh.setColorAt(i, color);
});

scene.add(mesh);

// Animate rotation + mouse follow
function animate() {
  mesh.rotation.y += 0.003;
  mesh.rotation.x += mouseY * 0.0008;
  mesh.rotation.z += mouseX * 0.0008;
}
```
