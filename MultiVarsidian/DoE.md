## Design of Experiments
Definition: DoE is a preplaned variation of input variables and measurement of output variables which are chosen in such a way as to gain maximum information about the system while minimizing the experimental effort.

![[multivar_doe_flowchart.png]]

#### DoE Graphically
In oposition to One Variable At a Time (OVAT) methods, DoE explores variable interactions by faithfully representing and spanning the whole parameter space.

![[multivar_doe_vs_ovat.png]]

#### Stages of DoE
BEFORE WE START: Calculate power of design. This is done through 4 inputs:
1) $\Delta$ - the significant difference in outcome for a given response. That is, is 0.5 cm error significant.
2) $\sigma$ the noise of the measurement of response variable.
3) Number of experiments
4) Significance level $\alpha$ (usually 5$\%$) 

Power is related to [[hypothesis testing]] as the probability of revealing an existing effect of size $\Delta$ relative to noise $\sigma$ as measured by signal to noise ratio $\Delta / \sigma$ . In hypothesis testing this is the probability of detection, $P_D$.  
- Screening: a design by selecting 6-12 (or more) factors that can be varied in order to affect the output. At this stage we are not sure what is important or how important in relation to one another, however we can choose the variables by using our domain knowledge or have coffee and talk with colegues who have the domain knowledge. Purpose is to identify important/dominant ones.
- Advanced Screening: Investigate possible interaction effects of a smaller nimber of factors.
- Optimization: Find the optimum setting with more precise model

Note that we can reuse experiments from previous stages! 


#### Different Designs
**Full Factorial Design** -  simplest designs, which are the basis for other designs. This is optimal for detecting main effects and their interactions. For a 2-level (2 dimensional) fictorial design we can do all 4 combinations of low-high values for the parameters, but also we need more than one center sample. For 3-level design we have 8 main combinations (corners of a cube) and at least 3 centre samples. In general for N dimensions we have $2^N$ + M center samples. Center samples should be taken not just at the end, but at the start, middle and end of the order of experiments.

![[multivar_doe_full_factorial.png]]

**Fractional Factorial Designs** - We take a subset of the full factorial design which covers as wide an area as possible. This neglects higher order interactions, and has the dissadvantage of aliasing the main effects with interactions, meaning some effects cannot be isolated and studied independently. For an N independent variable space we need $2^{N-1}$ experiments to get the fractional factorial design.

![[multivar_doe_fractional_factorial_cube.png]]

**Response Surface Designs** - The goal of these is to not only identify trends, main and interactive, but also to accurately model and represent the response surface. The goal is often to find the minima or maxima of the response surface. Used in finding the parameters which result in the optimization of some process's output value.

![[multivar_doe_optimal_design.png]]

**Central Composite Design (CCD)** - A full factorial design can be extended to the CCD by adding star points. Good for identifying and modelling a response surface. This has the disadvantage of being very expensive for a large number of factors. There are several types of CCD based on where one puts the stars in relation to the cube.

![[multivar_doe_ccd_types.png]]
**Constrained Optimal Designs** - These designs are concerned with respecting some practical/physical constraints that have to be met by the system. Thus we cannot span a cube, but the experiments result in a polyhedron. As such an orthogonal design is no longer possible. 

![[multivar_doe_constrained_polyhedron.png]]



#### Practical Examples

DoE allows us identify main effects, interactions and screen the different variables/factors. One way to do DoE is to start with 6-12 factor design, and screen the main effects of the variables. Should variables be found insignificant we can move on to factional factorials (reusing old measurements) and finally when we have isolated a small number of factors, we can extend the design to become an optimization design. The design can also be complicated/extended to include further variables in the next step, should the factors be deemed inadequate.

**Calculating Main Effects - Catalyst**
