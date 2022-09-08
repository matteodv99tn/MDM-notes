# Permanent Joints: Welds
For such joints separation is not forseen and to separate the parts it's neessary to break or deform the joint, irreversibly damaging the parts. Type of permament joints are **riveting**, brazing, adhesive bonding, but we will mainly focus on **welding**. Permanent joints can also be manufactured by plastic deformation, generating particular geometries in the memebers.

In **welds** parts are jointed byu means of **heat** with(out) addition of **filler material**, so realising physical continuity of the memebers. Such connections can be realized to **carry load** and/or **seal** the surface.

There are different types of weld joints, such **butt, corner, lap, edge** and **tee**; welds are alternative to foundry and forging in the production of complex shapes. 

The main advantages are
- 20% weigth saving with respect to riveting; the final result is aesthetically better and has a lower execution time;
- it has higher resistance at sealing (w.r.t. riveting) and it's faster;
- it's cost saving for small-series production and can be also automatized;
- allows for large freedom in shape definition.

However there are some cons' like
- not all materials are weldable;
- welds requires hand-on oversight, stricter manufacturing controls, implying more training and expertise requirement;
- is uneconomical for high-series production;
- mechanical resistance is lowered and is hardly predictable due to defects, residual stresses, metallurgical modification (as parts are heated and then cooled down), complex geometry...

Welding can be:
- **autogenous** if the torch melts the parts and the filler might be added; in this case torch can use acetylene, hydrogen or propane depending on the weld type and the member thickness;
- **eterogeneous** if only the filler material is melted and placed on the parts.

We observe that near the **welding edges** we have the so called **heat affected zones** (HAZ) where the increase of temperature changes the microstructural properties (usually worsening them).
The effect of HAZ depends on the **weldeability**, value tabled based on the **base material** and the welding process used. 
Usually weld defects are particularry decremental in fatigue resistance and might lead to brittle failure at low temperatures.

Proper counter-measures to reduce the creation of residual stresses are: pre-heat and/or pre-from the edges, perform a multi-step welding, apply a stress relief process.

Welds **control quality** can be:
- indirect: requiring UNI certification for the welders, tests of the filler materials or welding procedures, good design techniques;
- inspection: performed during fabrication by trained inspectors;
- direct: performin (non/half-) destructive analysis.

Design measures that can improve welded joints are:
- weld pieces of comparable thickness;
- place the weldings depending on the direction where load is applied;
- don't weld multiple times close to the same point;
- use simple geometry/shapes for the parts close to welding edges to better transmitt loads and also to have easier access to the welding point.

Welded joints, according to the italian standard, are classified according to the mutual position of the joint members; usually plates edges should be prepared for welding with proper chamfers. It is important to define proper welding depth, edge distance and rectilinear should values. Moreover we can denote the final cross section of the weld fillet as convex, planar or concave; another classification criteria is based on the continuity or the (opposed/staggered) block welding type.

## Verification criterias
Design and verifications criterias are affected by **large uncertainties** in both stress-state (due to the high and unpredictable notch effects) and material mechanical resistance.
Practical solution to this problem is by exploiting conservative assumption to favoure safety.

Fatigue won't be analysed in detail here, but it's shown that the endurance limit for welded joints depends both on material and joint type (butt joints have higher fatigue limit than corner ones); in general $\sigma_{lim}$ is a very small value.

### Full penetration joints
This joint restores the structural continuity of the memebers, thus it's easier to defined a proper resisting cross-sectional area.

The main component acting on full-penetration joints are $\sigma_\parallel, \sigma_perp$ and a shear $\tau$; exploiting the Von-Mises criterion we define the equivalent stress
$$ \sigma_{eq} = \sqrt{\sigma_\parallel^2+ \sigma_\perp^2 + \sigma_\parallel\sigma_\perp + 3\tau^2} \leq \sigma_{weld, all} = \nu \sigma_{all} $$
In this case $\nu$ is a **weakening coefficient** that's equal to 1 for _first class_ welds (higher quality) and 0.85 for _second class_ (lower quality) welds; $\sigma_{all}$ is instead the allowable strength that's tabled depending on the material used for the members.

For the material designation, following the EUROCODE3 standard, structural steel designation are described as
$$\texttt{S235 J0 G3}$$
where 235 is the minimum yield strength in $MPa$ for a specimen thickness of $16mm$, the designation J0 describes the testing strength and the associated testint temperature, while lastly G3 provides information regardin the delivery state (in this case the surface should be deoxidized).

### Fillet joints
This joint do not guarantee the structural continuity of the members, thus it's necessary to define a proper resiting cross section. In this case the stress-state is very complex with high notch effects, however analysing static loading we assume that some plasticization might occur, uniforming so the stress-state.

For verification purpouses, we refer the stress components to the **overturned throat area**. In this case we have two failure critation verification: one determined by a Von-Mises equivalent stress, and another equation truncating the associated sphere
$$ \begin{cases} 
	\sqrt{\sigma_\perp^2 + \tau_\perp^2 + \tau_\parallel^2} \leq \nu_1 \sigma_{all} \\
	|\sigma_\perp| + |\tau_\perp| \leq \nu_2 \sigma_{all}
\end{cases}$$
with coefficients $\nu_1 < \nu_2$ that are tabled based on the material designation.

### Fatigue
For fatigue verification the uniform stress assumption is no more acceptable; notch factor are hard to establish but some tabled are defined to get $K_f$ as function of the weld type.

# Other permanent joints
## Brazing and soldering
While brazing/soldering only the filler material is melted, not the base one (requiring so a lower melting point of the filler material). In particular **brazing** occurs for melting at temperature in the range $500^\circ-900^\circ C$ while **soldering** is defined for temperatures lower then $450^\circ C$.

Advantages of this technique is that
- allows to joint large interfaces with no cross-section weakening and with lower notch effects: this is especially good for shear load transmission;
- has a lower manufacturing temperature.

This comes with few drawbacks of having:
- lower mechanical strength (shear aside);
- difficulty in identifying joint defects.

## Adhesive bondings
Typically made by polymeric resins, their strong points are
- the ability to joint between dissimilar materials;
- the non-generation of temperature-induced modifications;
- suitability for light constructions;

However this comes with this drawbacks:
- the strength of the connection depends on the surface preparation;
- it cannot work at high tempereature;
- is good only at bearing shear loads and requires large overlapping surfaces;
- is very sensitive to the environment conditions.

