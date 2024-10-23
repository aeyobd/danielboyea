+++
title = 'Excellence in Graduate Research Symposium'
date = '2024-10-09:51:48-07:00'
featured_image = ''
+++


(jump to [movies](#movies))


Here I include some additional notes, resources, plots, and movies for my poster (Excellence in Graduate Research Symposium by the Graduate Student Society at the University of Victoria in Fall 2024).


## Introduction to Dwarf Galaxies and Galactic Tides

Dwarf galaxies are unusual and extreme. The largest dwarf galaxies have between 1/100 or 1/1000th of the Milky Way's stellar mass. However, the smallest dwarf galaxy might have as few as 50 stars total![^1] 
Because of dwarf's tiny stellar masses, most dwarfs formed their stars billions of years ago. So, dwarf galaxies are *relics* from the early universe---testing our theories of the formation of galaxies and the universe. Dwarf galaxies are furthermore some of the most *Dark Matter dominated* objects in the universe. A typical dwarf galaxy has 100 to 1000 times more mass in mysterious Dark Matter than in their stars and gas. Investigating the kinematic properties of dwarf galaxies directly tests our fundamental understanding of Dark Matter.

Our own Milky Way has over 60 dwarf galaxies in orbit[^2]. Additionally, we have identified the remnants of many dwarf galaxies in the Milky Way's halo (the diffuse cloud of stars that extends far past the disk and bulge of the Galaxy). As these galaxies are the closest galaxies outside of our own, we can study them in detail. Most nearby dwarfs have measured 3D orbital properties and detailed chemical abundance measurements.

After a dwarf galaxy forms, perhaps the strongest force governing the future fate of the galaxy is Gravity. Just like the oceans of Earth, the stars in dwarf galaxies can slosh around as they orbit other galaxies. The difference in the gravitational force from one side to the other of the dwarf galaxy causes some stars to escape, creating *tidal tails* which can extend across extraordinary distances. The effects of these tides depend on how close the galaxy becomes to the Milky Way (the pericentric distance). We have even spotted the remnants of some dwarf galaxies in the Milky Way's own halo.

## Sculptor
For my project, I have been focusing on the Sculptor dwarf spheroidal galaxy. This galaxy was first identified in 1938[^3], making it one of the first dwarf galaxies discovered (besides the large and small magellanic clouds visible by eye in the southern hemisphere). Sculptor is a relatively bright and massive dwarf galaxy at a distance of about 250 thousand light years away (83 kiloparsecs (kpc)). In the image below, we can see Sculptor as a bright overdensity of stars---completely different from more prototypical images of galaxies.


{{<figure 
    src="scl_desi_legacy_dr1_30arcmin.png"
    alt="Photograph of Sculptor Galaxy" 
    caption="An image of the Sculptor dwarf galaxy from the DESI Legacy Imaging survey (DR9). The image shown is 1/2 a degree wide, which is about the width of the full moon on the sky."
>}}


In this project, my goal is to determine if Sculptor is affected by tides.
Recent work has indicated that Sculptor may have an *excess* of stars around the outskirts.[^7] Such signatures are predicted for the gravitational evolution of a dwarf galaxy in a Milky Way like gravitational potential. However, it is unclear if Sculptor approaches the Milky Way close enough to reproduce the observed tidal signatures. If not, these signatures could be a hint of a diffuse *stellar halo*, another past interaction, or an unusual formation pathway for Sculptor. 


## Dynamical modeling
As my poster describes, dynamically modeling the tidal evolution of a galaxy like Sculptor can be summarized in a few steps.
1. Understand or measure the orbital properties and size of the galaxy. 
2. Select an orbit. Requires a model of the Milky Way (and potentially the Large Magellanic Cloud, see caveats) in addition to the kinematic properties of the galaxy.
3. Create the galaxy model. In my case, we simply simulate the Dark Matter only. Same idea as drawing random numbers but with a little more math and assumptions about the shape of Dark Matter in the galaxy. It is also good practice to run the galaxy by itself to make sure it is gravitationally *relaxed*, i.e. nothing changes with time.
4. Simulate! Let the galaxy roam around the Milky Way and see what happens :).

Note that Dark Matter is assumed to be cold and collisionless. This means the Dark Matter is born in equilibrium and does not interact except through gravity. To simulate the evolution, we sample 10 million particles from the galaxy's density (and energy) distribution and use Newton's gravitational law to calculate the force on each particle.[^9]

## Movies {#movies}

Below, I have created a video of both the Dark Matter (first) and stars[^6] (second) evolved over the entire simulation time of 10 billion years. Note that the Dark Matter is dramatically affected through the orbit. Most of the Dark Matter which leaves the galaxy is only loosely bound, whereas the more tightly bound centre of the galaxy and the stars are mostly unaffected.

{{<video 
    src="sculptor_dm.mp4" 
    width="100%"
    caption="Animation of Sculptor's Dark Matter over 10 billion years. The Dark Mattertter is represented in grey scale. The yellow line in the middle represents the Milky Way's stellar component."
>}}


{{<video 
    src="sculptor_stars.mp4" 
    width="100%"
    caption="Animation of Sculptor's stellar component over 10 billion years. Lighter colors represent a higher (log) density of stars. The yellow line in the middle represents the Milky Way's stellar component."
>}}


## Results

We created a model which reproduces Sculptor's observed properties (within a few times the errors). The closest Sculptor approaches the Milky Way is about 50 kpc (about 6 times the distance from the sun to the galactic centre). At this distance, the extended, diffuse Dark Matter particles are affected strongly (see movies above). However, the stars, which are much more compact than the Dark Matter, are hardly affected. In fact, on any reasonable orbit we have investigated, Sculptor only passes as close as 43 kpc from the Milky Way.

{{<figure
    src="scl_yz_orbit_egrs.svg"
    alt="The orbit of Sculptor. The orbit traces a rosette (flower like shape) oscillating from 50 to 100 kiloparsecs from the Milky Way."
    caption="The orbit of Sculptor is predominantly in the y, z plane shown. (Milky Way disc is instead in the x, y plane.) The units in the plot are kpc which are about 3,000 lightyears long."
>}}

{{<figure
    src="stars_samples.svg"
    alt="Simulated stars of Sculptor. "
    caption="A comparison of the on-sky distributions of stars from Sculptor for our simulation (left) and Gaia observations (right). Xi and eta are coordinates on the sky centered at Sculptor (known as the tangent plane). The simulated stars create a visibly similar distribution to the observations. However, we do not create the squashed shape that the real galaxy has. The stellar component shows no observable effects of tidal interactions in this model."
>}}

{{<figure
    src="density_i_f.svg"
    alt=""
    caption="The density of stars on the sky as a function of distance from the center of Sculptor. The Gaia observations are plotted as black points and the initial and final lines of the model are plotted as green and orange lines. The units of radius are in log arcminutes (1 / 60th of a degree). After the simulation ends, the stellar component remains almost exactly the same shape as the initial conditions."
>}}




## Caveats
A summary of simplifying assumptions.
- We currently assume Sculptor is spherical. Sculptor is visibly elongated, so it is possible that this elongation is intrinsic to Sculptor and needs to be taken in to account.
- We only simulate Dark Matter interactions in the galaxy. As Sculptor is mostly composed of old stars, it is unlikely Sculptor would have formed significant (Stars are well approximated by collisionless dark-matter particles.)
- We assume the Milky Way is a static gravitational field. This assumption is likely less valid as we know the Milky Way has evolved over time and may have responded to the infall of the Large Magellanic Cloud among other merging events.
- Additionally, the Large Magellanic Cloud (LMC, the largest of the Milky Way's satellites) may be as large as 10 percent of the Milky Way's mass. If this is true, than the LMC likely substantially distorts and stretches the Milky Way. I am working on assessing the impact of the LMC. (From preliminary orbital analysis, Sculptor may have passed much closer to the LMC than the Milky Way.) 

## Acknowledgements
This research takes place on the unceded lands of the Lək̓ʷəŋən (Songhees and Esquimalt) and the W̱SÁNEĆ peoples.


- [Gadget4](https://wwwmpa.mpa-garching.mpg.de/gadget4/) for N-body simulations and orbit integration.
- [Agama](http://agama.software) for modeling of potentials and forces.
- [Julia](https://julialang.org) for general analysis.
- [Makie](https://docs.makie.org/) for plotting.


## Notes
[^1]: Smith, Simon et al., 2024, [ApJ, 961, 92](https://ui.adsabs.harvard.edu/abs/2024ApJ...961...92S/abstract).
[^2]: McConnachie & Venn, 2020, [AJ, 160, 124](https://ui.adsabs.harvard.edu/abs/2020AJ....160..124M).
[^3]: Shapley H., 1938, [Har. College Obs. Bull., 908, 1](https://ui.adsabs.harvard.edu/abs/1938BHarO.908....1S).
[^4]: Jensen et al., 2024, [MNRAS, 527, 4209](https://ui.adsabs.harvard.edu/abs/2024MNRAS.527.4209J).
[^5]: The colorscale of the Dark Matter is logarithmic projected density
[^6]: The dark matter profile of this simulation is an NFW profile with \(v_{\rm circ,\ max}=31\)km/s at a radius \(r_{\rm circ,\ max}=3.1\) kpc.  The stellar profile is a Plummer profile with a scale radius of 0.20 kpc painted on using Eddington inversion. The colorscale spans 6.5 decades in log.
[^7]: Sestito et al., 2023, [MNRAS, 523, 123](https://ui.adsabs.harvard.edu/abs/2023MNRAS.523..123S).
[^8]: Schlegel et al., 2021, [AAS, 237, 235.03](https://ui.adsabs.harvard.edu/abs/2021AAS...23723503S).
[^9]: There is also a gravitational softening of 0.0074 kpc used in these simulations, which prevents two Dark Matter particles from strongly interacting if they happen to collide.
