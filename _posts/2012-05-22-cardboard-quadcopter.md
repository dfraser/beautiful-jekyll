---
id: 492
title: Cardboard Quadcopter!
date: 2012-05-22T13:46:34+00:00
author: Dan Fraser
layout: post
guid: http://www.capybara.org/~dfraser/?p=492
permalink: /archives/492
categories:
  - general
---
[<img src="http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/75b3fb8aa22011e19e4a12313813ffc0_7-300x300.jpg" alt="" title="75b3fb8aa22011e19e4a12313813ffc0_7" width="300" height="300" class="alignnone size-medium wp-image-522" srcset="https://capybara.org/~dfraser/wp-content/uploads/2012/05/75b3fb8aa22011e19e4a12313813ffc0_7-300x300.jpg 300w, https://capybara.org/~dfraser/wp-content/uploads/2012/05/75b3fb8aa22011e19e4a12313813ffc0_7-150x150.jpg 150w, https://capybara.org/~dfraser/wp-content/uploads/2012/05/75b3fb8aa22011e19e4a12313813ffc0_7.jpeg 612w" sizes="(max-width: 300px) 100vw, 300px" />](http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/75b3fb8aa22011e19e4a12313813ffc0_7.jpeg)

In March 2012, Hacklab Toronto kicked off a Quadcopter meetup&#8230; people who were interested in buying, building, or flying quadcopters met for a Saturday afternoon and discussed plans. People signed up on a spreadsheet discussing what they wanted to build and how much they wanted to spend. I signed up to build a medium-sized copter, and I wanted to spend about $500 and end up with something that was fun to fly. I asked Andrew Kilpatrick and Hiro to help with the frame and some brainstorming and we got started!

**Concept**

We wanted to build a Quadcopter entirely at the Hacklab, using tools and materials that were easily available. We decided to use the Hacklab&#8217;s laser cutter, which is a low-power unit capable of cutting acrylic but not metal. In an effort to not take things too seriously and to keep costs and weight low, we considered trying a frame cut from corrugated cardboard.

**Design**

We decided to make a copter with about a 600mm diameter. This is the size of the GAUI 330x and a few other commercial copters. It works well with commonly available 10&#8243; props. I clicked over to trusty HobbyKing to choose some cheap components. This is what I ended up with:

  * 4x MY30ABEC [Mystery 30A BEC Brushless Speed Controller (Blue Series)](http://www.hobbyking.com/hobbyking/store/uh_viewItem.asp?idProduct=9483) 
  * 2x HCB-10 [10X6 Propellers (Standard and Counter Rotating) (6pc)](http://www.hobbyking.com/hobbyking/store/uh_viewItem.asp?idProduct=11333)
  * 4x SK3-2830-920 [Turnigy Aerodrive SK3 &#8211; 2830-920kv Brushless Outrunner Motor](http://www.hobbyking.com/hobbyking/store/uh_viewItem.asp?idProduct=18155)
  * 2x AM1001A [PolyMax 3.5mm Gold Connectors 10 PAIRS (20PC)](http://www.hobbyking.com/hobbyking/store/uh_viewItem.asp?idProduct=68)
  * 1x N2200.3S.35 [Turnigy nano-tech 2200mah 3S 35~70C Lipo Pack](http://www.hobbyking.com/hobbyking/store/uh_viewItem.asp?idProduct=11944)
  * 2x XT60 [Nylon XT60 Connectors Male/Female (5 pairs)](http://www.hobbyking.com/hobbyking/store/uh_viewItem.asp?idProduct=9572)

The HobbyKing order came to just under $200 including shipping. I added some miscellaneous wire and a Spektrum AR6200 + Satellite receiver from my spare parts stock. I already had a Spektrum DX7 transmitter, an iCharger 208B battery charger, and a [MAAC](http://www.maac.ca) membership.

[<img src="http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/quadframe3-150x150.png" alt="" title="Quadcopter CAD Render" width="150" height="150" class="alignright size-thumbnail wp-image-495" />](http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/quadframe3.png)

The frame of the Quadcopter was quickly sketched in CAD by Andrew and refined by Hiro. They developed an easy to build frame that would hopefully be strong and rigid enough to perform well. It had a cool looking shape with integrated landing platforms and an internal space for the battery.

For the brain of the quadcopter I had to choose between a commercial, closed solution and one of the open-source autopilot boards on the market. Frontrunners in the commercial world were the GAUI GU-344 and the FyeTech FY91Q. The open-source boards were the ArduPilot and the OpenPilot projects. All of the units were about the same price. The open-source boards had far more features like advanced sensors and autopilot, but both were severely backordered. The commercial boards could only fly, but were available right away. I chose to be patient and ordered the new ArduPilot APM 2.0 (purple) board.

  * 1x BR-ArduPilotMega-03-0001 [APM 2.0 Purple Full Kit Assembled &#8211; MediaTek MT3329 10Hz &#8211; HMC5883L 3 Axis Magnetometer](https://store.diydrones.com/APM_2_0_Kit_p/br-ardupilotmega-03.htm)
  * 8x PR-0003-03-10cm [Servo Extension Cable 10cm Female-Female](https://store.diydrones.com/Servo_Jumper_Female_double_sided_p/pr-0003-03-10cm.htm)

From the [DIYDrones store](http://store.diydrones.com/). That order came to $210, putting us at about $410 in purchases for this project.

**Implementation**

[<img src="http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/quadframe-assy-150x150.jpg" alt="" title="Assembled Quadcopter Frame" width="150" height="150" class="alignleft size-thumbnail wp-image-499" />](http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/quadframe-assy.jpeg)We laser-cut the frame out of corrugated cardboard from a large U-Line shipping box and glued it together with Weld-Bond (it&#8217;s a space-age adhesive, you know). The frame was panelized to fit on the 24&#8243;x18&#8243; bed of the laser cutter at HacklabTO. We cut and assembled the frame in an evening.

[<img src="http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/img_20371-150x150.jpg" alt="" title="Motor and Prop" width="150" height="150" class="alignright size-thumbnail wp-image-512" />](http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/img_20371.jpg)
  
The outrunner motors from HobbyKing had the shaft coming out the wrong end. They are designed to be reversed, which was a simple but annoying process. Once I had reversed all of the shafts, I realized that the motors included a special prop mount that bolted onto the bottom of the can&#8230; and that the reversal was unnecessary. I didn&#8217;t bother to undo it and instead used the included collet prop adapters. The motors also included a convenient &#8220;X&#8221; plate to attach the motor to the motor mount. We used these to easily bolt the motor through the cardboard.

The ESCs came out of the box with reasonable programming and Just Worked. After soldering on bullet connectors and XT60 power connectors, we zip-tied them to the frame of the copter, and hooked them up to the motors. I built a 4-way XT60 power splitter to power the ESCs, and I disconnected the red (BEC) wire from all but one of the ESCs.
  
[<img src="http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/APM2-150x150.jpg" alt="" title="APM2" width="150" height="150" class="alignleft size-thumbnail wp-image-515" />](http://www.capybara.org/~dfraser/wp-content/uploads/2012/05/APM2.jpeg)
  
Once the ArduPilot board arrived, I tried to set it up and program it with a Windows VM inside VirtualBox on my Mac. It didn&#8217;t work, complaining that the serial port was too slow. I installed Windows in a Boot Camp partition instead, and everything was happy. Programming the ArduPilot board with the ArduPilot firmware and following the instructions on the wiki to configure the basic settings was easy and uneventful. In order to use the 3-position Flight Mode switch on my DX7 to control the flight modes on the ArduPilot, I used the ACRO (plane) profile on the transmitter, and programmed the Flight Mode switch to control the FLAP channel. Other than servo reversing to match the expected ArduPilot control directions, everything else was left as stock. 6 F-F servo jumper wires were used to connect the RC receiver to the ArduPilot board. 

We tested the system with the props removed from the copter for our safety, mostly making sure that all of the speed controllers armed properly and that the motors would spin. Once everything was working on the bench, we attached the props, and went outside for a proper flight test.

**Test**

<!--YouTube Error: bad URL entered-->

We decided to test in the little park near the HackLab. Since it was a nice day and the park was moderately busy, we didn&#8217;t intend to do anything other than see if the Quadcopter would hover. We plugged in the battery and verified the direction of each motor&#8217;s spin. Two motors were wrong, but were easily fixed by reversing two of the motor power wires.

After carefully applying just enough throttle to make the copter light on the ground, it was easy to see that all of the gyro compensation directions were correct and that the copter wasn&#8217;t about to flip itself over or spin out of control. Taking it off into a hover revealed that the elevator control direction was reversed (you can see this on the video), but I was able to land it safely and reverse the channel on my transmitter. Once this was set up properly, it was easy to take off and hover!

Controlling the altitude of the Quadcopter was much different from the RC Helicopters I&#8217;m used to, so you can see the quad bobbing up and down a lot in the video as I tried to adjust the power. It will take some practice to fly this thing well!

We didn&#8217;t try any of the automation because of the dangers of flying in a small park. That&#8217;s something we&#8217;ll check out at the Toronto RC Heli Club field!

**Results**

Overall, I&#8217;m very happy with this project! The cardboard frame works better than expected and will only improve as we tweak it to make it more rigid and easy to build. The props need balancing, the wiring needs cleaned up, and dozens of other little improvements need to me made. The cheap chinese electronics worked surprisingly well, and the ArduPilot is a well engineered and easy to use product. Hopefully the Quadcopter will be hours of fun, for less than our $500 goal!