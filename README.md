# Differential Geometry Visualiser

An interactive single-file HTML application for exploring key concepts in differential geometry through real-time 3D visualisation.

## Features

### 1. Surface Viewer with Curvature
- **7 parametric surfaces**: Sphere, torus, saddle (hyperbolic paraboloid), cone, cylinder, monkey saddle, and Enneper's surface
- Wireframe coloured by **Gaussian curvature K**: warm colours for positive (elliptic), cool for negative (hyperbolic), neutral for zero (parabolic/flat)
- Hover over the surface to read **K, H, principal curvatures** at any point
- Toggle **principal curvature directions** (teal/rose crosses) and **surface normals** (amber)
- Mouse drag to rotate, scroll to zoom

### 2. Geodesic Tracer
- Numerically integrates the **geodesic equation** using Christoffel symbols computed from the first fundamental form
- Set start point and direction via sliders, then shoot a geodesic
- **Fan mode**: shoot 8 geodesics in all directions to visualise convergence (positive K) or divergence (negative K)
- Works on sphere (great circles), torus, cylinder, cone, and saddle

### 3. Parallel Transport
- Animates **parallel transport** of a tangent vector along a latitude circle on the unit sphere
- Displays the **holonomy angle** after a full loop
- Shows the connection to the **Gauss-Bonnet theorem**: holonomy equals the integral of Gaussian curvature over the enclosed region
- Adjustable latitude to explore how holonomy varies

### 4. Gauss-Bonnet Theorem
- Interactive demonstration of the theorem: the integral of K dA plus the integral of geodesic curvature kappa_g ds equals 2 pi times the Euler characteristic
- Real-time numerical computation of both sides
- Adjustable region size
- Preset examples for sphere (spherical cap) and torus

## Technical Details

- **Pure vanilla JavaScript** with HTML5 Canvas (no libraries)
- All differential geometry quantities (first/second fundamental forms, Christoffel symbols, curvatures) computed numerically via finite differences
- 3D projection via rotation matrices with orthographic projection
- Geodesic integration uses Euler method with Christoffel symbols derived from metric tensor derivatives
- Parallel transport on sphere computed analytically for accuracy

## Usage

Open `index.html` in any modern web browser. No build step or server required.

## Fonts

Uses Google Fonts (DM Sans + JetBrains Mono) loaded via CDN. Falls back to system fonts if offline.

## Colour Palette

| Colour | Hex | Usage |
|--------|-----|-------|
| Teal | `#64ffda` | Primary accent, positive values |
| Amber | `#d4a053` | Secondary accent, mean curvature |
| Rose | `#ff6b9d` | Tertiary accent, principal curvatures |
| Background | `#0f0f13` | Dark theme base |
| Surface | `#1a1a24` | Card backgrounds |
