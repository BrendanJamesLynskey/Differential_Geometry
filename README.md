# Differential Geometry Visualiser

An interactive single-file HTML application for exploring the geometry of curves and surfaces — curvature, geodesics, parallel transport, and the Gauss-Bonnet theorem — through real-time 3D visualisation.

### [Launch App](https://brendanjameslynskey.github.io/Differential_Geometry/)

---

## Mathematical Background

Differential geometry studies the geometry of smooth manifolds, curves, and surfaces using the tools of calculus and linear algebra. Where classical Euclidean geometry treats rigid figures in flat space, differential geometry asks: what geometric properties can be defined on a curved surface, and which of those properties are intrinsic — detectable by inhabitants of the surface who cannot perceive the ambient space? The central objects of study are smooth manifolds equipped with a Riemannian metric, which assigns an inner product to each tangent space and thereby defines lengths, angles, areas, and curvature. For surfaces embedded in ℝ³, the theory is particularly concrete: every smooth parametric surface r(u, v) carries two fundamental forms that encode its full local geometry.

The **first fundamental form** I = E du² + 2F du dv + G dv² is the restriction of the Euclidean inner product to the tangent plane. Its coefficients E = rᵤ · rᵤ, F = rᵤ · rᵥ, G = rᵥ · rᵥ encode the intrinsic metric — all measurements of arc length and area depend only on I. The **second fundamental form** II = L du² + 2M du dv + N dv² captures how the surface bends in the ambient space: its coefficients L = rᵤᵤ · n̂, M = rᵤᵥ · n̂, N = rᵥᵥ · n̂ are the components of the surface's acceleration projected onto the unit normal n̂. Together, I and II determine the surface's shape up to rigid motion (Bonnet's theorem). The eigenvalues of the shape operator dN = −II · I⁻¹ are the **principal curvatures** κ₁ and κ₂, the maximum and minimum normal curvatures at a point. From these follow the two scalar curvature invariants: the **Gaussian curvature** K = κ₁κ₂ = (LN − M²)/(EG − F²), and the **mean curvature** H = (κ₁ + κ₂)/2. Gaussian curvature classifies local shape: K > 0 at elliptic points (sphere-like, where the surface curves the same way in all directions), K < 0 at hyperbolic points (saddle-like, with opposing principal curvatures), and K = 0 at parabolic or flat points (cylinders, cones, planes). Mean curvature has variational significance: surfaces with H = 0 everywhere are **minimal surfaces**, critical points of the area functional — the mathematical idealisations of soap films.

Gauss's **Theorema Egregium** (1827) is the founding insight of intrinsic geometry: the Gaussian curvature K depends only on the first fundamental form and its derivatives. It is therefore an intrinsic invariant, preserved under any isometric deformation — any bending of the surface that does not stretch or compress it. A flat sheet of paper (K = 0 everywhere) can be rolled into a cylinder (still K = 0) but can never be wrapped smoothly onto a sphere (K > 0) without distortion; this is why every flat map of the Earth necessarily introduces metric distortions. **Geodesics** are the intrinsic analogue of straight lines: curves that are locally length-minimising and have zero geodesic curvature. In coordinates, they satisfy the geodesic equation d²xⁱ/dt² + Γⁱⱼₖ (dxʲ/dt)(dxᵏ/dt) = 0, where the Christoffel symbols Γⁱⱼₖ are computed from the metric coefficients. On a sphere, geodesics are great circles; on a cylinder, they are helices; on a saddle, they diverge apart.

**Parallel transport** moves a tangent vector along a curve while keeping it "as parallel as possible" relative to the surface — formally, the covariant derivative of the vector along the curve vanishes. On a flat surface, parallel transport around a closed loop returns the vector to its original orientation. On a curved surface, it does not: the vector rotates by the **holonomy angle**, which equals the integral of Gaussian curvature over the enclosed region. This connects directly to the **Gauss-Bonnet theorem**, one of the deepest results in differential geometry: for a compact oriented surface M with boundary ∂M, ∫∫_M K dA + ∫_∂M κ_g ds = 2πχ(M), where κ_g is the geodesic curvature of the boundary and χ(M) is the Euler characteristic. The theorem links local differential-geometric data (curvature) to global topological data (the Euler characteristic), establishing that the total curvature of a closed surface is a topological invariant. For a closed surface without boundary: ∫∫_M K dA = 2πχ(M). Every closed orientable surface of genus g has χ = 2 − 2g, so a sphere (g = 0) has total curvature 4π, a torus (g = 1) has total curvature 0, and a two-holed torus (g = 2) has total curvature −4π, regardless of how the surface is deformed.

## History

The origins of differential geometry lie in Leonhard Euler's work on the curvature of surfaces in the 1760s. Euler introduced the concept of **normal curvature** — the curvature of a normal section of a surface — and showed that at each point the normal curvature varies as a function of direction, attaining a maximum κ₁ and minimum κ₂ in two orthogonal directions (the principal directions). He also discovered the **Euler characteristic** for convex polyhedra, V − E + F = 2, an early topological invariant that would later find its deepest expression in the Gauss-Bonnet theorem. In the decades that followed, Monge and his students (notably Dupin) developed the theory of surface families, lines of curvature, and the classification of surface points as elliptic, hyperbolic, or parabolic.

The subject was transformed by Carl Friedrich **Gauss** in his 1827 treatise *Disquisitiones generales circa superficies curvas*. Working from the needs of geodesy — the precise measurement of the Earth's surface — Gauss introduced the first and second fundamental forms, derived the expression K = (LN − M²)/(EG − F²), and proved the Theorema Egregium: that K is computable from the intrinsic metric alone, without reference to the ambient space. This was a profound conceptual shift, establishing that certain geometric properties belong to the surface itself rather than to its embedding. Gauss also proved an early version of the Gauss-Bonnet theorem for geodesic triangles on surfaces: the angular excess of a geodesic triangle equals the integral of K over its interior. The global theorem for closed surfaces was established by Bonnet (1848) and later generalised.

The decisive generalisation came from Bernhard **Riemann**, whose 1854 Habilitationsschrift *Über die Hypothesen, welche der Geometrie zu Grunde liegen* ("On the Hypotheses which lie at the Foundations of Geometry") extended Gauss's intrinsic surface theory to manifolds of arbitrary dimension n. Riemann introduced what we now call the **Riemannian metric tensor** gᵢⱼ and the **Riemann curvature tensor** Rⁱⱼₖₗ, a four-index object that encodes all the information about intrinsic curvature in n dimensions. For surfaces, the Riemann tensor reduces to a single scalar — the Gaussian curvature. Riemann's framework remained somewhat formal until the Italian geometers **Gregorio Ricci-Curbastro** and his student **Tullio Levi-Civita** developed the **absolute differential calculus** (tensor calculus) in their landmark 1900 paper. Levi-Civita later (1917) gave a geometric interpretation of Christoffel's algebraic connection coefficients as the rule for **parallel transport** of vectors along curves, making the notion of connection concrete and geometric. Their colleague **Luigi Bianchi** contributed the Bianchi identities, fundamental algebraic symmetries of the curvature tensor.

**Élie Cartan**, working from the 1920s through the 1940s, reformulated the entire subject using the **method of moving frames** (*repères mobiles*) and the language of differential forms. Cartan introduced the general concept of a **connection on a fibre bundle**, vastly extending the Levi-Civita connection and opening the way to gauge theory in physics. His structural equations express curvature and torsion as exterior derivatives of connection forms — an approach that is simultaneously more general and more computationally elegant than index-based tensor calculus. **Shiing-Shen Chern** brought Cartan's methods to bear on global problems: his 1944 intrinsic proof of the **generalised Gauss-Bonnet theorem** for closed Riemannian manifolds of any even dimension was a landmark, and his introduction of **Chern classes** (characteristic classes of complex vector bundles) became foundational in modern topology and geometry. In the twentieth and twenty-first centuries, Riemannian geometry became the mathematical language of **general relativity** — Einstein adopted the Riemann-Ricci framework directly, with the Einstein field equation Gᵢⱼ = 8πTᵢⱼ expressed in terms of the Ricci curvature tensor. Beyond physics, Riemannian and differential-geometric methods now permeate **geometric analysis** (Hamilton's Ricci flow programme, Perelman's 2003 proof of the Poincaré conjecture), **string theory** (Calabi-Yau manifolds), **computer graphics** (mesh processing, surface reconstruction), and **machine learning on manifolds** (geometric deep learning, optimisation on Riemannian manifolds).

## Key Formulas

| Formula | Expression |
|---------|------------|
| First fundamental form | I = E du² + 2F du dv + G dv², where E = rᵤ · rᵤ, F = rᵤ · rᵥ, G = rᵥ · rᵥ |
| Second fundamental form | II = L du² + 2M du dv + N dv², where L = rᵤᵤ · n̂, M = rᵤᵥ · n̂, N = rᵥᵥ · n̂ |
| Gaussian curvature | K = (LN − M²) / (EG − F²) = κ₁κ₂ |
| Mean curvature | H = (EN − 2FM + GL) / 2(EG − F²) = (κ₁ + κ₂) / 2 |
| Geodesic equation | d²xⁱ/dt² + Γⁱⱼₖ (dxʲ/dt)(dxᵏ/dt) = 0 |
| Gauss-Bonnet theorem | ∫∫_M K dA + ∫_∂M κ_g ds = 2πχ(M) |
| Holonomy (parallel transport) | Δθ = ∫∫_Ω K dA, for a vector parallel-transported around ∂Ω |

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

## Fonts

Uses Google Fonts (DM Sans + JetBrains Mono) loaded via CDN. Falls back to system fonts if offline.
