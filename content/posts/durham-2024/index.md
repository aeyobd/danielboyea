+++
title = 'Small Galaxies, Cosmic Questions II Resources'
date = '2024-07-23Tao:51:48-07:00'
featured_image = ''
+++



Here are some additional resources to my poster presented in Small galaxies cosmic questions II conference in Durham.
You are also welcome to [download my poster](durham_poster.pdf).

# Searching for tides in Sculptor

Sestito et al. (2023) detective a possible excess of stars in the outskirts of Sculptor. Is Sculptor's stellar component consistent with a tidal interpretation, or may this excess be the result of an extended stellar "halo," or other effects we should consider? My goal is to use simulations to determine if the tides of the Milky Way can perturb a dwarf galaxy to match the observational properties of Sculptor today. 



## Orbits

For the Milky Way potential, I use Errani & Peñarrubia et al. (2020) which defines a 4-component static potential approximating the McMillan (2011) potential. 

Our mean orbit reaches a pericentre of ~51 kpc with an apocentre of 102 kpc.

{{<figure 
    src="orbit.svg" 
    alt="Orbits" 
    caption="The orbit of our model in the R-z plane (cylindrical radius and z-coordinate). The initial position of sculptor is marked with the green triangle, and the track lightens with time, evolving slightly past an orange dot marking today. "
>}}


## Results

Matching the density profiles is a work in progress. I am working on adjusting the dark matter halos to match the present-day velocity dispersion. Additionally, the stellar component is challenging to match (and what is shown below technically only includes bound stars). 

The break radius is calculated using the fit from Peñarrubia et al. (2009),
$$
r_b = C\,\sigma_{\rm los}\, \Delta t
$$
where \(C=0.55\) is a fitted coefficient, \(\sigma_{\rm los}\) is the line-of-sight velocity dispersion, and \(\Delta t\) is the time since the last pericentric passage. 
We find a break radius of $r_b \approx 60$ arcminutes, larger than the location of the stellar excess reported in Sestito et al. (2023) at 30 arcminutes. Alternative orbits which may yield better results are a work in progress. 

{{<figure 
    src="density_i_f.svg" 
    alt="Density" 
    caption="The density profile at the initial (green) and final (orange) snapshots"
>}}




## Movies


The 2D projected dark matter density of Sculptor animated in time. The
colorscale is logrithmic spanning 5 decades.

{{<video 
    src="sculptor_dm.mp4" 
    width="600px" 
>}}


Below, the 2D projected stellar density of Sculptor animated in time. The
colorscale is logrithmic spanning 10 decades.
{{<video 
    src="sculptor_stars.mp4" 
    width="600px"
>}}


## Acknowledgements
This research takes place on the unceded lands of the Lək̓ʷəŋən (Songhees and Esquimalt) and the W̱SÁNEĆ peoples.


- [Gadget4](https://wwwmpa.mpa-garching.mpg.de/gadget4/).
- [Agama](http://agama.software) for potential calculations.
- [Julia](https://julialang.org) for analysis.
- [Makie](https://docs.makie.org/) for plotting.

