# Haptic-Piezo-for-High-Precision-Actuation
Hacking commercial products spurs low-cost nanometric positioning stages. Our work merges piezo haptics &amp;amp;amp; 3D printing to design a scanner.

The search for inexpensive, high-precision positioning stages with nanometric resolution has driven extensive exploration by scientists, engineers, and makers over the past few decades. One of the key factors that has enabled the democratization of high-end scientific techniques is the hacking and repurposing of widely available commercial products.

Some studies have demonstrated the potential of using piezo buzzers for nanometric positioning, particularly in DIY scanning tunneling microscopes (STMs). In our work, we will investigate the potential of combining piezo systems developed for haptic feedback technologies with standard 3D printing techniques to design a piezo-based scanner stage.

Safety Notice – High Voltage Warning

First and foremost: This project involves high-voltage amplifier for piezo components, which can be dangerous or even deadly if mishandled.

If you are not completely sure about what you are doing, please avoid working on this project.

You are responsible for your own safety—so stay cautious and prioritize safe practices at all times.

Stay safe!



Piezo choice :
The main idea is to use the TDK PowerHap 6005 system to build a simple scanning stage. This piezo consists of a piezoelectric element combined with a mechanical stainless steel amplifier, that also permit the direct screwing with 4 m2 threaded holes. It can be driven up to 120V, providing a motion range of 120 µm (unloaded), as I measured below.
 Unload piezo motion VS voltage

Flexure design :

Designing a one-axis scanner requires a simple flexure-based solution, specifically a double leaf-spring parallel design (reference). This eliminates parasitic motion in other axes, making the stage very stiff in the Y and Z directions, while remaining flexible in the X direction.

To realize this in practice at a low cost, the best approach is to use 3D printing (PLA in this case). This method is inspired by the OpenFlexure project, developed by some truly great people!

At this point, we can also simulate the behavior of the design using your preferred CAD/FEM software.
FEM simulation of the design behaviour
1st one axis 3d print prototype with piezo



First tests :
For the first tests, I am using a Melles Griot PCW011 high-voltage amplifier to drive the prototype. However, since the piezo has a high capacitive load (3.2 µF), I am currently limited to low-frequency operation with the DAQ.

Looking ahead, I will need to develop a high-voltage, high-current, low-noise amplifier. The likely approach will involve a main voltage transformer for isolation, an HV low-noise op-amp, and a transistor output stage with a large heatsink—a project for the future!

For initial displacement measurements, I used a micrometric probing head (an old 1980s Heidenhain system with 1 µm resolution). To improve accuracy, I also incorporated a HeNe interferometer for high-precision measurements (oscilloscope shot post process).
Interferometer test setup
Instrumentation test setup

Current status :

I am now focusing on data processing from the interferometer to achieve high-resolution and accurate displacement measurements. Once this is optimized, the test setup will allow for in-depth analysis, including frequency response and hysteresis characterization.

In parallel, I plan to explore capacitive measurement techniques for motion detection. I have ordered a second-hand capacitive gauge, which—if it works—could provide a simpler alternative to the interferometer. While the interferometer is undoubtedly more precise, the complexity of coding and mathematical processing exceeds my current motivation and available free time!

The next major step is to implement a YZ two-axis topology and develop an independent Z-axis module that can be mounted onto the system. This will lead to a full XYZ scanner with nanometric precision.

Of course, drift measurements (temperature and time stability) will need to be conducted at some point—but unfortunately, I don’t have infinite free time... sadly!
