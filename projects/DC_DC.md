---
layout: project
type: project
image: img/
title: "DC_DC converter"
date: 2024-03-01
published: false
labels:
  - Switch Mode Power Supplies
  - Analogue 
  - Oscilloscope
  - LTSPICE
  - Altium
  - PCB
summary: "This is a DC_DC developed as part of a coursework by myself and had to meet a set of specifications. It was built on a PCB."
---

<h2>Specifications</h2>

<ul>
  <item1>Vin=40V, Vout=12V</item1>
  <item2>Iout=3.5A</item2>
  <item3>Isolated</item3>
  <item4>Openloop</item4>
  <item5>Efficiency > 85%</item5>
</ul>

<h2>Topology selection</h2>

The choice of topology depends on the required properties of the power supply. We first consider practical and safety features required, and these can be explored by studying safety standards set by the IET. For simplicity, we will consider whether we need galvanic isolation or not. This is important in preventing electric shock to the user, especially when the converter is connected to the mains (in which case it would be mandatory). Moreover, the power rating is a significant factor to consider when selecting the optimal toplogy as certain ones are better suited for a range of power values than others. For example, flyback converters have a simple design, but require a large ferromagnetic core to deliver more power without saturating. In such a case, we would opt for toplogies that can deliver the same amount of power with smaller cores, like the Push-Pull converter.

In our case we will need around 40w rating, which will be scaled by to account for inefficiencies by divding the power rating by the minimum expected efficiency (85%), giving us 47W. This is a relatively low power converter, so we can go for a Flyback or a Double Switch Forward converter. They offer similar power ratings, however a double switch does not have the voltage osccillations seen in a Flyback. I will explain the difference in the section below.

<h2>Flyback vs Double switch forward converter</h2>
(insert an image of both topologies)

In both converters, a PWM signal switches the single MOSFET in a Flyback (and the two MOSFET's in a Double Switch), and when PWM is ON the primary coil of the transformer is charged. At this stage the diode in the output stage is reverse biased because the secondary voltage is negative , meaning no current flows in the secondary coil. When PWM is OFF, the secondary coil voltage reverses to maintain current flow, forward biasing the diode. The abrupt change of current in the primary coil causes voltage spikes, in accordance



<h2>Simulation</h2>

The converter was initially simulated using ideal switche
