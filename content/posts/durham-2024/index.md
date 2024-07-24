+++
title = 'Small Galaxies, Cosmic Questions II Resources'
date = '2024-07-23Tao:51:48-07:00'
featured_image = ''
+++



Here are some additional resources to my poster presented in Small galaxies cosmic questions II conference in Durham.
You are also welcome to [download my poster](durham_poster.pdf).

# Searching for tides in Sculptor

Sestito et al. (2023) detective a possible excess of stars in the outskirts of Sculptor. Is sculptor's stellar component consistent with a tidal interpretation, or may this excess be the result of an extended stellar "halo," or other effects we should consider?



## Orbits
All of the orbits we consider so far are as in the potential defined by Errani & Peñarrubia et al. (2020). 

Our mean orbit has a pericenter 50.766
101.846

{{<figure 
    src="orbit.svg" 
    alt="Orbits" 
    caption="The orbit of our model in the R-z plane (cylindrical radius and z-coordinate). The initial position of sculptor is marked with the green triangle, and the track lightens with time, evolving slightly past an orange dot marking today. "
>}}


{{<figure 
    src="density_i_f.svg" 
    alt="Density" 
    caption="The density profile at the initial (green) and final (orange) snapshots"
>}}




## Simulation Details

- Performed in Gadget4

{{<video 
    src="sculptor_dm.mp4" 
    width="600px" 
>}}


{{<video 
    src="sculptor_stars.mp4" 
    width="600px"
>}}


## Acknowledgements
This research takes place on the unceded lands of the Lək̓ʷəŋən (Songhees and Esquimalt) and the W̱SÁNEĆ peoples.


- [Gadget4](https://wwwmpa.mpa-garching.mpg.de/gadget4/) is the core engine of this project, carying out N-body dark matter simulations.
- [Agama](http://agama.software) is used to compute the gravitational potential and the forces acting on the stars.
- [Julia](https://julialang.org) is my current 
- [Makie](https://docs.makie.org/)

