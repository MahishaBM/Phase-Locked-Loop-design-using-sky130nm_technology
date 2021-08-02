# Phase-Locked-Loop-design-using-sky130nm_technology
![image](https://user-images.githubusercontent.com/88282645/127779274-bc74db6a-106e-417e-8b7e-43c020197d84.png)
<br/>
# Table of Contents<br/> 
   >>  i. Introduction to PLL<br/>
   ii. Viewing components present inside PLL<br/>
   iii. Getting into ngspice and magic for designing layout<br/>
    iv. Prelayout stage ngspice simulation<br/>
   v. Layout design using magic<br/>
----
# Tools used
  >>  1.ngspice<br/>2.magic<br/>
----
# Introduction to PLL<br/>
PLL (Phase- Locked Loop) is a control system with negative feedback which generates an output signal whose phase is compared to phase of input signal. <br/>![PLL](https://user-images.githubusercontent.com/88282645/127800843-ab98ebfa-11c4-43b8-9437-48df0498db75.jpg)
----
# Viewing inside control system block<br/><br/>
# Main blocks present inside control system are<br/>
<br/>1. Phase frequency detector(PFD)<br/>2. Charge Pump(CP)<br/>3. Voltage controlled oscillator(VCO)<br/> 4. Frequency divider(FD)<br/><br/>
# Block diagram<br/><br/>![PLL (1)](https://user-images.githubusercontent.com/88282645/127839125-a45b905e-2d21-411f-b794-6c8aace97ab4.jpg)<br/>
# 1.Phase frequency detecctor<br/>
<br/> PFD compares the phase of input signal and output signal via negative feedback and give output as either up or down signal. Phase difference can be found by performing XOR operation between both the signal. Two situations are possible here leading or lagging. During lagging the output siganal is laggs behind ref signal/input signal so to increase its speed, up signal is needed. During leading the output s ignal will leads the ref signal so we need to slow down the output at that time down signal is needed<br/>PFD cir file![pfd__cir](https://user-images.githubusercontent.com/88282645/127843445-b9a87a47-c84f-4b7e-9618-7f0cd8a4d9f6.png)<br/><br/>PFD waveform<br/><br/>![pfd__wf](https://user-images.githubusercontent.com/88282645/127842718-952cf89b-6b1f-48b9-91cc-ec0a5c4548e4.png)<br/><br/>PFD Layout<br/><br/>![pfd__lay](https://user-images.githubusercontent.com/88282645/127844182-6bf06bcd-5975-4a62-ac8e-e6cbee280936.png)<br/><br/>
# 2. Charge pump<br/>
<br/> This block converts all the digital measures to analog which is done to control the voltage controll oscilattor<br/><br/>![PLL (3)](https://user-images.githubusercontent.com/88282645/127848305-8c86942c-ea64-455a-bd0f-cb5786549456.jpg)<br/><br/>To smoothen the process we include low pass filter in charge pump circuit<br/><br/>
![PLL (4)](https://user-images.githubusercontent.com/88282645/127850428-559dd14e-b1a8-4cf9-a9b3-4951f7d1c9c8.jpg)<br/><br/> CP cir<bir/>![cp_cir](https://user-images.githubusercontent.com/88282645/127850991-50d33959-ed84-41c1-8769-f22bca84624a.png)<br/><br/> CP Waveform<br/><br>![cp_wf](https://user-images.githubusercontent.com/88282645/127851202-27d3526e-4bf0-4725-989c-2b0530a8c39c.png)<br/>br/> CP Layout<br/><br/>
![cp_lay](https://user-images.githubusercontent.com/88282645/127851303-0f40e1ae-2dc5-4f04-bc05-2c1c5de020ee.png)<br/><br/>
# 3. Voltage Control Oscillator(VCO)<br/>
Voltage Control Oscillator is elctronic ossilator here oscillation frequency is contolled by input vlotage. Output signal of VCO is fedback to PFD via negative feedback 
<br/>VCO cir file<br/><br/>![vco_cir](https://user-images.githubusercontent.com/88282645/127852470-27f4b7b9-e6ac-4e21-aae9-b2f878324766.png)<br/><br/>VCO Waveform<br/><br/>![vco_wf](https://user-images.githubusercontent.com/88282645/127852691-963f7a01-4678-4aae-93ce-90d56074e60f.png)<br/><br/>VCO Layout<br/><br/>![vco_lay](https://user-images.githubusercontent.com/88282645/127852795-4f9a7ac8-c167-4097-a6ff-08d5950881f6.png)
