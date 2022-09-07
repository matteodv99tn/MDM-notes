# Threaded elements
Usually used for **non-permanent joints** or to transform angular to linear motion for generating high forces (as for **power-screws**).

A **thread** is a helix wrapped on a cylindrical/conical surface and are mainly characterized by an **axial pitch** $p$; the _lead_ $L$, multiple of $p$, describes the engagement of the thread per turn. Usually screws are right-handed. Usually threads have a trapezoidal profile with all dimensions depending on the pitch $p$ and the pressure angle $\alpha$ (based on the reference norms). The _inner_ part of the profile has fillets to reduce stress concentration at the rooth of the teeth.

The **Metric ISO** screws are characterized by V thread shape with high stripping resistance, high friction and low pitch, leading to an overall low efficiency (but has the benefit of not loosening during operations).
Given a norm, a nominal diameter $D$ and the bolt length $L$, all other parameters of the threaded element can be automatically deduced. There are also a lot of **screw heads** and **nuts** that might vary depending on size, geometry (this load capability) and functionality (lock nuts for example are good at countering bad effects due to vibrations).
There are also **washers** used to distribute load, protect the surfaces from scratches and galvanic cells; they also avoid the loosening of the connection due to vibrations.

Screws are designated as
$$ \text{Screw \texttt{M12x50 ISO 4014 - 8.8}} $$
where 12 is the nominal diameter, 50 the length, 4014 the reference standard and 8.8 is the **property class** describing the material. The first number provides the number of $100MPa$ of tensile strength (in this case $\sigma_{uts} = 800MPa$) while the second one provides the relative yielding value (in this case $\sigma_{ys} = 0.8\cdot 800MPa = 640Mpa$).

Heads and nuts are usually described with english grades, however tables exists comparing the two references. As note, nuts should not be re-used as the first 3 thread are subjected to higher load and can be plastically deformed.

# Power screws
Power screws are used as linear actuators, providing great mechanical gain in weight lifting. Such component can be mounted in different configuration, but mainly what we want to determine is the required lifting force $F$ (applied with an arm $a$, generating so a torque $T=Fa$) to apply at the interface.
By computing the static equilibrium on a infinitestimal element, what we get is that
$$ T = \frac{q d_m}2 = Fa = \frac{w d_m}2 \frac{f\pi d_m + L \cos\alpha_n}{-fL ++ \pi d_m \cos \alpha_n} + \frac{wf_cd_c}{2} $$
where the second addendum is modelling the friction of the collar; $d_m$ is representing the mean diameter of the thread.

Depending on the friction coefficient (and geometrical parameters of the threaded element) we can have
- **self-locking** mechanism that requires active torques to lower the weight, meaning that if we do not apply any force, the system stays still. This condition is matched when
 $$ f \geq \frac{L\cos\alpha_n}{\pi d_m} = \tan \lambda \cos\alpha_n $$
- **overhauling screw** when the weigth $w$ alone is able to lower the system by itself; in this case a constant force must be applied to leave the system in equilibrium configuration.

Power screws are also characterized by an input-output **power transmission efficiency** that depends on both friction coefficient and helix angle; such coefficient differs for lowering and lifting operation).

# Bolt analysis
## Stresses
Usually threaded fasteners are subjected mainly to **tensile loads**; due to the complex geometry, there's a non uniform stress distribution that leads to high stress concentration factors. Screws should however be ductile enough to permit local plasticization without permanently damaging the component.

Threads in contact can be schematized as springs where the closer ones are the stiffer ones, thus bearing more load; this of course leads to a worse fatigue response.
Due to the higher load on the firsts threads, there are higher deflections increasing bolts pitch and reducing the nuts pitch, consequently relieving loads from other threads and increasing the load on the first thread.
As counter measures:
- use softer nut in order to have a better load exchange by permitting its plasticization;
- use a nut with a pitch slightly greater then the one of the screw;
- use partitular design for the nut.

## Stripping and nut thickness
To avoid the **stripping** of the screw from the nut, a proper **nut thickness** $t$ should be chosen. Equating the bolt tensile strength $F_{bolt} = \frac \pi 4 (0.9d)^2\sigma_{ys}$ and the stripping action on the nut $F_{nut} = \pi d(0.75d)\sigma_{ys} \approx \pi d(0.75t)(0.58\sigma_{ys})$ leads to a thickness $t \approx 0.47d$. This was based considering bolt and nut of same material, however usually this last component is softer and we safely consider
$$ t \simeq \frac 78d $$

## Tightening torque
To apply a tensile force $F$ at the interface of the members, the bolt should be installed with an _interference_ that requires a suitable tightening torque. By a static balance of the force acting we have that such torque is
$$ T = \frac{Fd_m}2 \frac{f \pi d_m + L\cos\alpha_n}{-fL + \pi d_m\cos\alpha_n} + \frac{F f_{nut} d'}2 $$
The first addendum, associated to the friction of the threaded part, empirically determines 66% of the total torque (the second addendum is instead modelling the torque due to nut friction).
Having that usually the preload of the bolt is $N_0 = 0.8 A_{bt}\sigma_{ys}$ (80% of yield load) and considering that usually $2^\circ \leq \lambda 5^\circ$ and $0.15 \leq 5 \leq 0.2$, then
$$ T \simeq 0.2 Fd $$

Given $F_{max}$ the maximum preload that lead to the system fracture and $F_{min}$ the minimum preload that guarantees proper functionality of the system, we define 
$$ \alpha_a = \frac{F_{max}}{F_{min}} $$
the **tightening factor**, a value that can also be used as a measure to _how much to oversize the bolt_.

# Bolted joint verification of a single screw
Bolts must be verified at **resistance** (we need to prevent screw/member failure) and **stiffness** (we want to prevent the separation of relative sliding of the members the need to be joined).

## Tensile joint







































