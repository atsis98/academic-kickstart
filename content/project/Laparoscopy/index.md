---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Numerical Simulations and Design of a Novel Laparoscopic Instrument
"
summary: "The project aims to introduce a new design of an instrument that combines the functionality of surgical forceps, a Suction-Irrigation (S-I) device, and a Carbon Dioxide (CO2) insufflator. A brief introduction to surgery and laparoscopy is provided before moving on to the details of the project."
authors: [Harsha Sista]
tags: [Laparoscopy, Design and Simulation]
categories: [Undergraduate Projects]
date: 2020-08-18T22:38:08+05:30

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

The project aims to introduce a new design of an instrument that combines the functionality of surgical forceps, a Suction-Irrigation (S-I) device, and a Carbon Dioxide (CO2) insufflator. To understand the project in the right context, I will start with a brief introduction to surgery and laparoscopy before moving on to the details of the project.


## <b>Introduction</b>

The abdominal cavity has long been a focus for surgical procedures since it contains a variety of organs and is relatively easy to access from the outside. However, surgeons traditionally made a cut that was 6-12 inches long to see the organ they were working on and give enough room for the proper maneuvers. However, the onset of laparoscopy changed this completely. Laparoscopy is a minimally-invasive diagnostic procedure used by surgeons to examine and operate upon organs in the abdomen. Several small cuts are made, usually less than half an inch wide, through which a camera and the surgical instruments are inserted. This advantages of doing so are listed below:

* There is minimal scarring since the size of the cuts is smaller
* Lesser possibility of hemorrhaging, leading to the lesser necessity of blood transfusions
* Lesser pain for the patient
* Faster recovery time, leading to quicker normalization back into society

Due to these advantages, laparoscopy has quickly gained traction among the medical community as a viable alternative to opening up the abdominal cavity.

{{< figure src="featured.png" title="Figure 1: An example of laparoscopy" numbered="false" lightbox="false" >}}

## <b>How is Laparoscopic Surgery performed?</b>

In laparoscopic surgery, the surgeon views the abdominal cavity from the monitor and operates by creating multiple incisions and inserting trocars of 5-12 mm sizes, as shown in the figure below. A trocar is a surgical instrument that is sharp-pointed and is used with the cannula to puncture the abdominal cavity and to insert different instruments through it.

{{< figure src="figure 2.png" title="Figure 2: An overview of the instruments used in a laparoscopic surgery" numbered="false" lightbox="false" >}}

Initially, the surgeon makes a small incision through a trocar near the belly button. Then a camera-enabled laparoscope is inserted into the abdominal cavity through a trocar into the first of the three ports. The abdomen is inflated with carbon dioxide gas (a method known as pneumoperitoneum) through the second port to view internal organs clearly on a monitor. The reason for preferring carbon dioxide over other gases is that it is non-flammable, non-combustible, colorless, readily soluble in water, cheap, and reduces the risk of complications occurring by blood clots in veins.

The final port is for the laparoscopic forceps, to perform operations such as grasping, cutting, lasing, cauterizing, etc. After inflating the carbon dioxide gas, the surgeon inserts the required instruments and begins operating.

## <b>What is being done in the project?</b>

The objectives of the project are enumerated below:

1. To design and develop a laparoscopic surgical device which:
   * Functions as a multipurpose and reusable instrument that can cut, grasp, and cauterize the tissue.
   * Is useful for simultaneous suction and irrigation and Carbon dioxide insufflation.
   * Provides added safety by avoiding multiple insertion and removal, reducing the time of surgery.
   * Can be assembled and disassembled with ease, facilitating fast sterilization.
2. To simulate the flow of blood through the annular region in ANSYS Fluent using the various models of non-newtonian flow.
3. To simulate the multiphase flow of carbon dioxide and water for various volume fractions.

## <b>Part 1: Designing the novel instrument</b>

I joined the ongoing project in January 2020, with the initial objective of running simulations, but with my previous experience with design and Solidworks in particular, I started on converting the conceptual idea into a tangible design. The idea was simple, modify and add on to an existing design of the forceps, as shown in the figure below:

{{< figure src="figure 3.png" title="Figure 3: Existing surgical forceps" numbered="false" lightbox="false" height=400 width=400 >}}

To achieve the desired multi-functionality, we decided to add a sleeve covering the forceps, which would act as the common conduit for the S-I process as well as the CO2 insufflation, depending on usage.

After spending the first few weeks building a forceps assembly based on existing designs, I added the outer sleeve and other components as required. The design process was iterative in nature, with me working closely with my two advising professors and the Ph.D. student to give it the desired shape, literally and figuratively. After all the requirements were met, we filed an Invention Disclosure Form and applied for an Indian Patent for our design.

## <b>Part 2: Non-Newtonian Simulations</b>

What is a non-Newtonian fluid? It is a fluid that does not follow Newton's law of viscosity. Now, what is that? Newton defines viscosity as the ratio between shear stress and shear rate.

{{< figure src="figure 4.png" title="" numbered="false" lightbox="false" >}}

In Newtonian fluids, the viscosity remains constant and is independent of stress. In non-Newtonian fluids, viscosity can change when under force to either more liquid or more solid, so they can become thicker or thinner under force. An example of this is ketchup becoming runnier when shaken (and possibly even stirred).

Blood is one such non-newtonian fluid. Since laparoscopic surgery involves grasping tissue using forceps and using the S-I apparatus to suck out the excess fluids, blood is the obvious choice for the fluid to simulate for our instrument.

There are many models available to model blood as a non-newtonian fluid in ANSYS, a simulation software. We chose to go with two such models and run simulations to decide which gave better results.

Once the outer sleeve was added onto the design, I extracted a fluid domain from it, which would serve as the geometry for all the fluid simulations we were going to do. Importing it into ANSYS, we spent a couple of weeks conducting mesh-independent studies to select one final mesh.

Then, with the two models and the final mesh, we simulated the process of the apparatus sucking the blood out of the operating area, by giving the appropriate pressure differences. The resulting depictions of the flow physics were interesting, to say the least, and make up the crux of a couple of research papers that are being written right now.

## <b>Part 3: Multiphase Simulations</b>

The part I am currently working on, apart from writing a few papers detailing our research, is multiphase simulations. So what exactly does multiphase flow mean? It refers to the flow of two or more fluid phases through the same medium. In this case, for CO2 insufflation, CO2 and air make up the two phases that flow through the outer sleeve.
Therefore, the modeling of this situation on ANSYS is much more complex. To reduce a degree of complexity, the inlet was divided into two fractions, according to the respective volume fraction of the two elements, and then simulated in Fluent. These are very computationally intensive simulations, which in ordinary speak means that they take a lot of time. For the next month or so, I will be working on this. Stay tuned for further updates, and you just might be rewarded with more details for your patience.
 
## <b>Conclusion</b>

I have been working on this project since the beginning of the year. Although this is a new area of research, having never ventured to the biomechanical side of my degree, it caught my interest in my initial conversations with Prof. Murthy when I approached him for a project back in November last year. Although most of my research work has been related to topics that come under the banner of Aerospace Engineering, I am glad I took up a topic that was on a different segment of the broad Mechanical umbrella.
In addition to giving me insights into the design and simulation of a practical problem, this project honed my research methodology, especially with respect to the iterative nature of the process and the hard work involved in sowing the seeds that will eventually blossom into tangible branches of knowledge.
 
I am deeply grateful to have the opportunity to have worked for an extended period of time on this project, and I believe that my skillset is much improved because of this. Carrying this forward, I shall complete the rest of my tenure with the same enthusiasm for learning with which I began this journey.
