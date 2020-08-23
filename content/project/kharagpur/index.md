---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Flow simulation of supercritical Carbon Dioxide through a channel"
summary: "The project focused on simulating the flow of supercritical Carbon Dioxide (CO2) through a small channel, studying the velocity and temperature profiles."
authors: [Harsha Sista]
tags: [CFD, Supercritical Fluid]
categories: [Undergraduate Projects]
date: 2020-08-16T16:04:43+05:30

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: true

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

This project was the focus of my research-oriented summer internship under Dr. Sourav Mitra, Assistant Professor at the Indian Institute of Technology, Kharagpur. It focused on simulating the flow of supercritical Carbon Dioxide (CO2) through a small channel, studying the velocity and temperature profiles.

## <b>Introduction</b>

In the modern era of industrialization, many processes require the usage of solvents for different applications pertaining to the particular industry. For example, solvents are routinely used as paint removers, lacquers, adhesives, cleaning materials, etc. Different industries use different kinds of solvents for their applications, and with an increase in health awareness, the food industry is looking to move away from classic solvents. Due to this, supercritical Carbon Dioxide is finding favor in the coffee manufacturing industry, as a decaffeinating solvent.

It is also gaining momentum in other industrial aspects, as a working fluid due to its relative stability, and as a component in power generation. Due to these advances and the growing use of Supercritical CO2, it is vital to study this fluid's characteristics and behavior for innovative future applications.

## <b>What is a supercritical fluid?</b>

A supercritical fluid is any fluid at a temperature and pressure above its critical point, where distinct liquid and gas phases do not exist. Applying temperature and pressure above the critical point of a substance pushes that substance into the supercritical phase. The properties of this fluid can be adjusted by going further into the supercritical region. This is achieved by increasing the temperature or pressure.

{{< figure src="featured.png" title="Figure 1: Depiction of various phases" numbered="false" lightbox="false" height=500 width=500 >}}

## <b>Supercritical Carbon Dioxide</b>

Under normal atmospheric conditions, CO2 behaves as a gas. However, if the temperature and the pressure are increased to beyond the parameters of its critical point, it starts behaving midway between a liquid and a gas. This is called the supercritical state of CO2, with the fluid having a density similar to that of a liquid while occupying a volume in the same way a gas does. The parameters for the critical point for CO2 are given below:

Temperature: 304.25 K
Pressure: 7.39 MPa

## <b>Simulation setup for normal CO2</b>

To get familiarized with the behavior of CO2 in a flow channel, it was first simulated under normal conditions. The properties of CO2 were imported from NIST REFPROP, by writing a line of code in ANSYS Fluent to initialize the REFPROP database, and select the corresponding CO2 file to be imported.

The pipe length was set to be 0.1m, and the diameter as 0.005m. The boundary conditions are summarized below:

Inlet velocity = 0.5 m/s
Temperature of Fluid at inlet = 300 K
Wall Temperature = 273 K
Outlet: Outflow Condition
Walls: No-slip condition

The velocity and temperature profiles are plotted for the entire region, with analysis conducted on 9 sections across the length.

{{< figure src="fig1.png" title="Figure 2: Velocity profiles at each of the 9 slices" numbered="false" lightbox="false" height=500 width=500 >}}

Therefore, we see that the velocity converges to parabolic throughout the course of the flow.

{{< figure src="fig2.png" title="Figure 3: Temperature profiles at each of the 9 slices" numbered="false" lightbox="false" height=500 width=500 >}}

Therefore, we see that the temperature profile converges to parabolic.

From the above data and analysis, we can conclude that flow of CO2 through a pipe develops, both hydrodynamically and thermally, after a certain point, as shown by the calculations. The next step is to simulate a similar case for supercritical flow, with the temperature and pressure being inputted accordingly.

## <b>Simulation setup for supercritical CO2</b>

The setup remains the same, except for the temperature of the fluid at the inlet, which is changed to 304.25 K, the supercritical temperature of CO2. However, at the supercritical pressure and temperature, the simulation in Fluent did not behave as expected, even if the outlet boundary condition is changed. So far, the NIST Real gas tables have been linked with the Fluent console. Since the results were not satisfactory, a different approach was required.

Fundamental properties such as density and thermal conductivity were explicitly exported from REFPROP into MS-Excel, and their variations with temperature were plotted. Using the trend line feature of Excel, the approximate polynomials for the respective graphs were extracted, as shown below:

{{< figure src="fig3.png" title="Figure 4: Physical properties as plotted in Excel" numbered="false" lightbox="false" height=750 width=750 >}}

These polynomials are then inputted into Fluent as a new material, corresponding to CO2. When the User-Defined Function (UDF) was discarded, and the polynomials were inputted with the right units, there were no further errors in the initialization phase.

This simulation was run at an inlet velocity of 1m/s, keeping all the other boundary conditions the same. The velocity contour, however, was almost uniform, even though the flow was laminar. The same simulation was run at 0.01 m/s, and the velocity contour behaved as expected. Seeing this anomaly, the domain length was changed to 1m to see if there were any discernable changes in a larger flow domain. The velocity and temperature profiles are quite different, while the specific heat contours show a slight variation, and the pressure contours behave almost the same.

## <b>Conclusion</b>

Therefore, the variable material properties of supercritical carbon dioxide have successfully been imported into Fluent, utilizing the NIST provided REFPROP software. The polynomials generated through MS Excel have proved to be durable. The resulting velocity and temperature contours are deviant from the expected results and need to be probed into. Once this issue is resolved, the simulation can then be moved to a microchannel, with additional parameters like surface tension coming into play.