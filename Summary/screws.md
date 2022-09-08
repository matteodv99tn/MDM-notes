# Threaded elements
Usually used for **non-permanent joints** or to transform angular to linear motion for generating high forces (as for **power-screws**).

A **thread** is a helix wrapped on a cylindrical/conical surface and are mainly characterized by an **axial pitch** $p$; the _lead_ $L$, multiple of $p$, describes the engagement of the thread per turn. Usually screws are right-handed. Usually threads have a trapezoidal profile with all dimensions depending on the pitch $p$ and the pressure angle $\alpha$ (based on the reference norms). The _inner_ part of the profile has fillets to reduce stress concentration at the rooth of the teeth.

The **Metric ISO** screws are characterized by V thread shape with high stripping resistance, high friction and low pitch, leading to an overall low efficiency (but has the benefit of not loosening during operations).
Given a norm, a nominal diameter $D$ and the bolt length $L$, all other parameters of the threaded element can be automatically deduced. There are also a lot of **screw heads** and **nuts** that might vary depending on size, geometry (this load capability) and functionality (lock nuts for example are good at countering bad effects due to vibrations).
There are also **washers** used to distribute load, protect the surfaces from scratches and galvanic cells; they also avoid the loosening of the connection due to vibrations.

Screws are designated as
$$\text{Screw \texttt{M12x50 ISO 4014 - 8.8}} $$
where 12 is the nominal diameter, 50 the length, 4014 the reference standard and 8.8 is the **property class** describing the material. The first number provides the number of $100MPa$ of tensile strength (in this case $\sigma_{uts} = 800MPa$) while the second one provides the relative yielding value (in this case $\sigma_{ys} = 0.8\cdot 800MPa = 640Mpa$).

Heads and nuts are usually described with english grades, however tables exists comparing the two references. As note, nuts should not be re-used as the first 3 thread are subjected to higher load and can be plastically deformed.

# Power screws
Power screws are used as linear actuators, providing great mechanical gain in weight lifting. Such component can be mounted in different configuration, but mainly what we want to determine is the required lifting force $F$ (applied with an arm $a$, generating so a torque $T=Fa$) to apply at the interface.
By computing the static equilibrium on a infinitestimal element, what we get is that
$$T = \frac{q d_m}2 = Fa = \frac{w d_m}2 \frac{f\pi d_m + L \cos\alpha_n}{-fL ++ \pi d_m \cos \alpha_n} + \frac{wf_cd_c}{2} $$
where the second addendum is modelling the friction of the collar; $d_m$ is representing the mean diameter of the thread.

Depending on the friction coefficient (and geometrical parameters of the threaded element) we can have
- **self-locking** mechanism that requires active torques to lower the weight, meaning that if we do not apply any force, the system stays still. This condition is matched when
 $$f \geq \frac{L\cos\alpha_n}{\pi d_m} = \tan \lambda \cos\alpha_n $$
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
$$t \simeq \frac 78d $$

## Tightening torque
To apply a tensile force $F$ at the interface of the members, the bolt should be installed with an _interference_ that requires a suitable tightening torque. By a static balance of the force acting we have that such torque is
$$T = \frac{Fd_m}2 \frac{f \pi d_m + L\cos\alpha_n}{-fL + \pi d_m\cos\alpha_n} + \frac{F f_{nut} d'}2 $$
The first addendum, associated to the friction of the threaded part, empirically determines 66% of the total torque (the second addendum is instead modelling the torque due to nut friction).
Having that usually the preload of the bolt is $N_0 = 0.8 A_{bt}\sigma_{ys}$ (80% of yield load) and considering that usually $2^\circ \leq \lambda 5^\circ$ and $0.15 \leq 5 \leq 0.2$, then
$$T \simeq 0.2 Fd $$

Given $F_{max}$ the maximum preload that lead to the system fracture and $F_{min}$ the minimum preload that guarantees proper functionality of the system, we define 
$$\alpha_a = \frac{F_{max}}{F_{min}} $$
the **tightening factor**, a value that can also be used as a measure to _how much to oversize the bolt_.

# Bolted joint verification of a single screw
Bolts must be verified at **resistance** (we need to prevent screw/member failure) and **stiffness** (we want to prevent the separation of relative sliding of the members the need to be joined). The principal **failure modes** are:
- net-tension of the minimum cross-section;
- tear-out of the plate (plastic deformation wasn't enough to handle the load);
- punching shear of the head inside the member.

## Shear joint
In case of tensile joints we should watch for:
- **sliding resistance** that ensures that the preload maintans member in contact with sufficient friction to avoid sliding; given a preload $N_0$, a separating action $N_b$ acting on the bolt and $n$ surfaces in contact then we require
	$$V_b \leq \frac{k_s n f}\phi\big(N_0 - 0.8N_b\big) $$
	where $k_s$ is a coefficient dependent on the hole type and $\phi$ is chosen by EUROCODE3 to be 1.1-1-25;
- **shear resistance** checks that the bolts cross section subjected to shear do not _shear-out_, implying
	$$V_b \leq \frac{\sigma_{uts}A_b}{\phi}$$
	where $\phi = \frac{1.25}{0.6}$ by EUROCODE3; $A_b$ is the bolts cross section subject to shear;
- **crushing resistance** associated to the member thickness:
	$$V_b \leq \frac{\sigma_{uts, member} dt}\phi $$
	where $\phi = 0.5$ by EUROCODE3.

## Tensile joints
In case of tensile joints we must watch for:
- **tension resistance**, verification of the plain axial load acting on the screw:
	$$N_b \leq \frac{\sigma_{uts}A_{bt}}\phi $$
	where $\phi = \frac{1.25}{0.9}$ by EUROCODE3;
- **punching resistance** of the head against the members:
	$$N_b \leq \frac{\pi d_0 t \sigma_{uts,member}}\phi$$
	with $\phi = \frac{1.25}{0.6}$ by EUROCODE3, $d_0$ the bolts head diameter and $t$ the member thickness.

## Fundamentals of tensile joint verification
A more accurate model to understand load distribution and required preloads is based on the computation of the **interference** $i = l_{0f} - l_{0b} = \Delta l_b - \Delta l_f$ between bolt+nut and the members considering the equivalent stiffnesses of the bodies. 

For what concerns the bolt, we consider the different section making up such _beam_ and compute the equivalent stiffness as
$$K_b = \left( \sum_i \frac{l_i}{EA_i} \right)^{-1} $$
Modelling members is more complex due to the nature of the stress distribution; based on experimental studies, the region thats more heavily affected by the loads are in a cone of angle $\alpha \simeq 30^\circ$. _Slicing_ each part of the member, the stiffness is
$$k_{f,i} = \frac{\pi Ed\tan\alpha}{\ln\left(\frac{D-d}{D+d} \frac{d_0+d}{d_0-d}\right)} \qquad \Rightarrow \qquad K_f = \left( \sum_i \frac 1 {K_{f,i}}\right)^{-1} $$

When assembled the bolt elongates, while the members are in compressions, leading to an equilibrium position that gives us the actual preload on the system. We have that the **tightening intererence** is 
$$i_s = \Delta l_b - \Delta l_f = N_0 \frac{K_f-K_b}{K_fK_b}$$
leading to 
$$\Delta l_b = i_s \frac{K_f}{K_f+K_b} \qquad \Delta l_f = - i_s \frac{K_b}{K_f+K_b} $$
Another assumption that can be made is that the members are infinitely stiff ($K_f \gg K_b$), implying that only the bolt deformes in the final assembly.

If we in general consider that on top of the preload $N_0$ there's applied a separating action $N$, then the axial load of the bolt $N_b$ increases, relieving the actions $N'$ on the members following the law
$$N_b = N_0 + N\frac{K_b}{K_f+K_b} \qquad N' = N_0 - N\frac{K_f}{K_f+K_b}$$
For a more detailed sliding resistance criterion, use $N'$ instead of the reported value $N_0 - 0.8N$

# Analysis of Bolted Joints: multiple screws
In presence of multiple screws we assume **rigid members** and **deformable bolts**; the external forces that must be transferred are applied on the **centroid** of the bolts.

### Sliding actions
In case of shear load we assume that each bolt bear a load proportional to its cross-sectional area; given that the sum must give the force $V$, we obtain
$$V_i = V \frac{A_{b,i}}{\sum_i A_{b,i}} $$
Each component is parallel in direction to the value of $V$.

Considering instead a torque $T$ that need to be transmitted, the shear loads $V_i$ on each bolt are proportional to the cross-sectional area and the distance $r_i$ from the centroid, leading to a formulation
$$V_i = T \frac{A_{b,i}r_i}{\sum_i A_{b,i}r_i^2}$$

### Separating actions
In case of normal loads, as for shear we have
$$N_i = N \frac{A_{b,i}}{\sum_i A_{b,i}} $$
Analysing bending moment is instead a little more tricky; multiple teories have been developed, such:
- **rigid members** hypothesis: in this case the preload is neglected and the axial load on each bolt is proportional at the cross-sectional area and the distance $h_i$ of the pivot point that is consider to be the extremal point where the connection can rotate according to the direction of the bending torque $M_b$:
	$$N_i = M_b \frac{A_{b,i}h_i}{\sum_iA_{b,i}h_i^2} $$
- **semi-rigid members** hypothesis: in this case normal load and bending moment must be analysed togheter. Given a stress distribution
	$$ \sigma = - \sigma_{max,co} \left(1 - \frac y{y_n}\right) $$
	where $\sigma_{max,co}$ and $y_n$ are unknowns representing the maxmimum value of the stress and the position of the neutral axis, then we want to define those values matching both normal and bending loads. Note that by changing $y_n$ we also change also the number of _active bolts_. The general problem that we need to solve is
	$$\begin{cases} \int_0^{A(y_n)} \sigma(y)\, dA + \sum_i - \sigma_{max,co} \left(1 - \frac {y_i}{y_n}\right) A_{b,i} = N \\ \int_0^{A(y_n)} \sigma(y) \big(y - y_n\big)\, dA + \sum_i - \sigma_{max,co} \left(1 - \frac {y_i}{y_n}\right)\big(y_i - y_n\big) A_{b,i} = M_b + N \big(y_g-y_n\big)\end{cases}$$
- a simplified approach of the semi-rigid members is to simply mvoe the pivot point at $h/4$ of the the flange height or simply at the first row of the bolts (and use the rigid members computations based on that pivot point). 

## Fatigue
Usually fatigue failure is localized in the first three threads of the bolts that are the one bearing more load. Given a pulsating normal load $N(t) = N_m + \frac{\Delta_N}2\cos(\omega t+\varphi)$, exploiting the equivalent stiffnesses of both member and bolt we can deduce the bolts load cycle mean and amplitude values as
$$\sigma_{a,nom} = \frac 1{2A_{bt}} \frac{K_b}{K_b+K_f} \Delta_N \qquad \sigma_{m,nom} = \left( N_0 + \frac{K_b}{K_n+K_b} N_m\right)\frac 1{A_{bt}}$$
The amplitude stress is amplified by a notch factor $K_f$ of $2.2$ for medium-low strength bolts (class $<5.8$) up to the value 3 for high strength bolt.
	


