# ESP32 Musical Tesla Coil interrupter - a truly versatile interrupter


<img width="709" height="945" alt="image" src="https://github.com/user-attachments/assets/03fd7dee-795c-4024-9ca7-99c24f780e06" />
<img width="709" height="945" alt="image" src="https://github.com/user-attachments/assets/32726d6c-687f-4a99-9146-a1de5dbee507" />

<img width="709" height="945" alt="image" src="https://github.com/user-attachments/assets/ca532ac1-2842-4bfd-9f0c-404d7121bf63" />


<img width="1040" height="698" alt="image" src="https://github.com/user-attachments/assets/a418eb98-ba74-491a-8d83-ac445f594539" />


Demo video of it working!!(YouTube)
[Demo!!](https://youtu.be/YgG9X8sHGf4)

Link to onshape: [Onshape](https://cad.onshape.com/documents/e0858d62bc807065493100b9/w/9e573f9273f6c5cefa0e0909/e/5fb6c5c268f4d3541bf88c26?renderMode=0&uiState=69cbe64c76ff3f85d768a45f)

## Why? 

I always wanted a good, cheap and reliable Tesla Coil Interrupter but as of now, there is not a good, easily accessible proper product like project or prototype I could get. And I needed a good, feature rich, safe interrupter too for my Tesla Coil journey since all my prototype perfboard designs failed of the harsh environments. I wanted something close to the OneTesla SD interrupter but a modern touch, more modern features that make sense and a lot of new features that is essential nowadays. 
 
That is why I set out to build a good, ESP32S3 based Tesla Coil interrupter that is reliable as a product and robust for the environments of a Tesla Coil.

## About the project in a nutshell

It is a portable fiber optic(POF) output interrupter designed to interrupt DRSSTCs and SSTCs safely with limits, and even audio modulate the interruption for musical tesla coil arcs! 
It has an easy to use UI, simple settings on the frontend, and importantly, it has so much limits and safeties specifically tuned for DRSSTC to ensure the coil and driver is not stressed very much. 

It is powered by a 9V battery inside the battery compartment by default, but USB C power input(compatible with modern chargers) can also be used by changing a mode select jumper. 

## Hardware it uses and more features

- Compact 16x2 LCD for displaying information. 
- Micro SDcard slot for music. It supports playing  .mid file and even OneTesla's propietary binary music data file (.omd) used kn their interrupters as a fallback. 
- 4 Voices support for midi files(2 voice for  .omd) means more complex music can be played! 
- Optical fiber output (POF 1mm) for output to coil driver, ensuring isolation from EM radiation and noise. 
- Live mode MIDI over serial through DIN 5 jack and also USB MIDI support is present (usb midi needs firmware addition yet) 
- Tactile Buttons and Rotary encoder(setting volume and also for selection) for the UI and adjustments in operation. There is also a latching power switch. 
- Fixed-frequency mode with adjustable freq and volume

## How to use. 

- Press the latching switch. The device will turn on and display by default Fixed Mode. 
- Left&Right buttons can be used to scroll through menus. Select is done by pressing on the rotary encodee knob till thr encoder knob clicks. 
- The middle button(used to be select)will become the new exit button to exit out of modes(yet to be totally verified in firmware)
- To play fixed freq pulses select fixed mode. Rotating rotary knob when the Freq is selected will change the frequency, to select volume, left or right button is used till bottom row of LCD is highlighted,then volume(duty cycle) can be adjusted by rotary knob. Middle button will be used to exit the mode.Note optical output starts once in fixed mode(default 20Hz with minimum volume) and will stop once exited. 

- For live modes(Live&MIDI BLE), an input such as from a keyboard or any device can be given to the interrupter in live. The device will act as Midi receiver. 


# Firmware details

## Build & Upload (Arduino IDE)
 Please install the ESP32 board core before proceeding
 The interrupter after building needs to be programmed with firmware. The latest firmware files can be accessed in releases. 

1. Board: Select **ESP32S3 Devkit** (or ESP32S3 Dev Module)

2. Libraries: Unlike previous firmware versions, Now the libraries are included within the firmware locally

3. Select correct COM port, Upload.

## Controls

- **Main menu**: LEFT/RIGHT to navigate; SELECT(rotary's switch) to enter, soon mid button for exiting. 
- **Fixed mode**: short SELECT toggles freq/volume adjust; Press middle button to exit

- **Live mode&MIDI BLE**: SELECT activates and exits live mode. Status is shown in LCD. 

- **SD browser**:LEFT/RIGHT to navigate through files & directories; SELECT opens folder or plays file; press middle button to go one up if inside directories or exit the mode if in root directory. 

- **Playback**: SELECT starts & stops; Rotary knob rotation adjusts volume bar(the coil duty)

## File format

- It accepts .mid MIDI files. More than 4 channels won't play correctly, always keep melody in first two as they are preferred internally. 
-It also uses .omd file but it is a limited fallback only, it is a cut down midi file format OneTesla used so your music may not play properly. Soon  .omd will be disabled by default. 

# CAD images and images of PCB & schematic
<img width="1040" height="698" alt="image" src="https://github.com/user-attachments/assets/12806c8d-9917-457d-9b22-7d3ea8295f2e" />
<img width="1119" height="729" alt="image" src="https://github.com/user-attachments/assets/3267d5b2-65cc-449b-a5e4-538f2b3e59a3" />
<img width="1037" height="654" alt="image" src="https://github.com/user-attachments/assets/e0aef778-549c-4adc-9854-0258119e6a1a" />
<img width="1125" height="752" alt="image" src="https://github.com/user-attachments/assets/54ab21e9-6d59-44b7-8b3e-3d0ef41a42a8" />

PCB images
<img width="1110" height="689" alt="image" src="https://github.com/user-attachments/assets/034d31ff-116e-4973-984a-e11640f1c2bb" />
<img width="1089" height="704" alt="image" src="https://github.com/user-attachments/assets/0681e38a-0413-4788-b667-271d76ff738a" />
<img width="1071" height="741" alt="image" src="https://github.com/user-attachments/assets/c082c0d8-5494-4f0d-8e80-0dc4a9b38fc8" />
<img width="1083" height="720" alt="image" src="https://github.com/user-attachments/assets/471e31b0-8290-4355-9680-07b72527f487" />
<img width="1017" height="677" alt="image" src="https://github.com/user-attachments/assets/4dc4ce45-058b-4e26-9b5e-25ab8a653146" />
<img width="1047" height="722" alt="image" src="https://github.com/user-attachments/assets/4420cc9a-2e89-4006-9dbc-dada66156075" />
<img width="1125" height="652" alt="image" src="https://github.com/user-attachments/assets/c438f657-a9f9-420c-9804-2b4fc165c1c9" />

All mech parts in parts studio
<img width="936" height="770" alt="image" src="https://github.com/user-attachments/assets/3df61321-2c21-4edd-a633-c8058c8be56c" />
<img width="827" height="674" alt="image" src="https://github.com/user-attachments/assets/c9e2ea21-69da-4d75-b269-27405693ea07" />



Exploded views
<img width="670" height="730" alt="image" src="https://github.com/user-attachments/assets/9a7b5c72-fe66-458b-8948-711e4b33f0de" />
<img width="968" height="475" alt="image" src="https://github.com/user-attachments/assets/b3b6d3d0-0071-48f3-af3e-8a340bb8b8cd" />
<img width="1071" height="706" alt="image" src="https://github.com/user-attachments/assets/80e332d2-4d14-45ab-81e6-9e629a242d1e" />
<img width="671" height="720" alt="image" src="https://github.com/user-attachments/assets/7063afb5-f940-4159-918c-33ff52f8f28c" />

Here is schematic
<img width="2358" height="1672" alt="SCH_ESP32 SD Interrupter_1-Sheet_1_2026-03-31" src="https://github.com/user-attachments/assets/584c0d0e-c3f7-41b7-809b-03401be68280" />

# Bill of materials

| Part name | Qty required(not ordered due to MOQs) | Source | Price | Actual Price with taxes & shipping | Links |
| --- | --- | --- | --- | --- | --- |
| PCB board fabrication | 1 used 5 MOQ |Lion Circuits or ~~Robu.in~~ | ~~robu(₹3556/$37.7)~~, Lion ₹2983 $31.74 | ~~robu(same)~~,Lion ₹2983 $31.74 |Cannot link to quote|
| 2.54MM male Pin headers | 5 pins(2+3) | Local shop | Already own | Already own | |
|Power Switch Latching|1|LCSC|$0.84|$0.84|[link](https://www.lcsc.com/product-detail/C22386787.html?spm=wm.gwc.xh.7.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|USB C Port Connector|1|LCSC|$1.06|$1.06|[link](https://www.lcsc.com/product-detail/C20624793.html?spm=wm.gwc.xh.8.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|Tactile Button|3|LCSC|$0.06|$0.06|[link](https://www.lcsc.com/product-detail/C7528723.html?spm=wm.gwc.xh.6.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|OptoTransmitter HFBR-1521Z|1|LCSC|$7.65|$7.65|[link](https://www.lcsc.com/product-detail/C188712.html?spm=wm.gwc.xh.9.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|AMS1117-3.3 regulator|1|LCSC|$1.13|$1.13|[link](https://www.lcsc.com/product-detail/C6186.html?spm=wm.gwc.xh.10.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|AMS1117-5.0 regulator|1|LCSC|$1.19|$1.19|[link](https://www.lcsc.com/product-detail/C6187.html?spm=wm.gwc.xh.11.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|ESP32S3 Wroom 1 N8|1|LCSC|$5.42|$5.42|[link](https://www.lcsc.com/product-detail/C2913198.html?spm=wm.gwc.xh.12.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|10uF 25V Aluminum Electrolytic Cap|1|LCSC|$0.49|$0.49|[link](https://www.lcsc.com/product-detail/C43846.html?spm=wm.gwc.xh.13.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|100nF 25V 0805 Ceramic cap|8|LCSC|$0.18|$0.18|[link](https://www.lcsc.com/product-detail/C53084462.html?spm=wm.gwc.dh.14.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|470Ω 150V Thin Film Resistor|1|LCSC|$0.70|$0.70|[link](https://www.lcsc.com/product-detail/C479100.html?spm=wm.gwc.xh.4.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|220Ω 0805 Res|1|LCSC|$1.70|$1.70|[link](https://www.lcsc.com/product-detail/C186237.html?spm=wm.gwc.xh.3.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|180Ω 0805 Res|1|LCSC|$0.49|$0.49|[link](https://www.lcsc.com/product-detail/C313842.html?spm=wm.gwc.xh.2.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|33ohm 0805 Res|1|LCSC|$0.41|$0.41|[link](https://www.lcsc.com/product-detail/C557530.html?spm=wm.gwc.xh.5.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|Rotary encoder EC11E18244A5|1|LCSC|$2.05|$2.05|[link](https://www.lcsc.com/product-detail/C255515.html?spm=wm.gwc.xh.1.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|Micro SD TF card port|1|LCSC|$0.73|$0.73|[link](https://www.lcsc.com/product-detail/C111196.html?spm=wm.gwc.xh.0.cbm___wm.sxq.ssl.gwc&lcsc_vid=RAIIXwdQElVfUAVfEgNfVlFWEVQIXwcAR1RbVVFeTlIxVlNRQ1hYXlxWRVBfVTsOAxUeFF5JWBYZEEoKFBINSQcJGk4dAgUUFAk%3D)|
|10K Resistor array 1206|1|robu.in|₹ 2.28 $0.0243|₹ 2.28 $0.0243|[link](https://robu.in/product/cay16-1002f4lf-bourns-4-%c2%b11-10k%cf%89-62-5mw-%c2%b1200ppm-%e2%84%83-1206-resistor-networks-arrays-rohs/)|
|0805 LED Green|1|robu.in|₹ 2.62 $0.0279|₹ 2.62 $0.0279|[link](https://robu.in/product/0805-surface-mount-led-green-50-pcs/)|
|0805 LED Red|2|robu.in|₹2.36 $0.0252|₹2.36 $0.0252|[link](https://robu.in/product/0805-surface-mount-led-red-50-pcs/)|
|DSS34 diode|2|robu.in|₹ 9.58 $0.1021|₹ 9.58 $0.1021|[link](https://robu.in/product/dss34-slkor-sod-123fl-schottky-diodes-rohs/)|
|1N4148W 1206 Diode|2|robu.in|₹ 1.70 $0.0181| ₹ 1.70 $0.181|[link](https://robu.in/product/1n4148w-sod-123-1206-diodereel-of-3000/)|
|SS8050S-FOSAN-SOT-23 Bipolar (BJT)|1|robu.in|₹1.82 $0.0194| ₹1.82 $0.0194|[link](https://robu.in/product/ss8050s-fosan-sot-23-bipolar-bjt-rohs/)|
|510kΩ 0805 res|1|robu.in|₹0.21 $0.0022||[link](https://robu.in/product/0805w8j0514t5e-uniohm-royal-ohm-125mw-thick-film-resistors-150v-%c2%b1100ppm-%e2%84%83-%c2%b15-510k%cf%89-0805-chip-resistor-surface-mount-rohs/)|
|5.1kΩ 0805 res|2|robu.in|₹ 1.96 $0.0209|₹ 1.96 $0.0209|[link](https://robu.in/product/ac0805fr-075k1l-yageo-res-thick-film-0805-5-1k-ohm-1-0-125w1-8w-%c2%b1100ppm-c-pad-smd-t-r-automotive-aec-q200/)|
|2.2Kohm 0805 res|1|robu.in|₹ 0.42 $0.0045|₹ 0.42 $0.0045|[link](https://robu.in/product/ac0805jr-072k2l-yageo-res-thick-film-0805-2-2k-ohm-5-0-125w1-8w-%c2%b1100ppm-c-pad-smd-t-r-automotive-aec-q200/)|
|47Ω 0805 res|1|robu.in|₹ 0.20 $0.0021|₹ 0.20 $0.0021|[link](https://robu.in/product/0805w8f470jt5e-uniohm-royal-ohm-125mw-thick-film-resistors-150v-%c2%b11-%c2%b1200ppm-%e2%84%83-47%cf%89-0805-chip-resistor-surface-mount-rohs/)|
|TS-1088-AR02016 Switch|2|robu.in|₹8.43 $0.0899|₹8.43 $0.0899|[link](https://robu.in/product/1-month-warranty-470/)|
|TLJR106M010S2000-KYOCERA AVX-10uF 10V cap|1|robu.in|₹26 $0.2772|₹26 $0.2772|[link](https://robu.in/product/tljr106m010s2000-kyocera-avx-10uf-10v-2%cf%89-%c2%b120-0805-tantalum-capacitors-rohs/)|
|16V 10uF X5R 0805|2|robu.in|₹1.96 $0.0209|₹1.96 $0.0209|[link](https://robu.in/product/cl21a106kofnnne-samsang-16v-10uf-x5r-%c2%b110-0805-multilayer-ceramic-capacitors-mlcc-smd-smt-rohs/)|
|1.3Kohm 0805 res|1|robu.in|₹ 1.96 $0.021|₹ 1.96 $0.021|[link](https://robu.in/product/rt0805fre071k3l-yageo-125mw-thin-film-resistor-%c2%b150ppm-%e2%84%83-%c2%b11-1-3k%cf%89-0805-chip-resistor-surface-mount-rohs/)|
|M2 X 12mm Female to Female Brass with Nickel plating Hex Threaded Standoff Spacer|4|onlyscrews.in|₹24.8 $0.2644|₹24.8 $0.2644|[link](https://onlyscrews.in/products/m2-x-12mm-female-to-female-brass-with-nickel-plating-hex-threaded-standoff-spacer?variant=50830639006009)|
|M2 X 10mm Hex (Allen) Socket Head High Tensile(12.9) Black oxide screw (Dia. 2mm, Length 10mm)|8|onlyscrews.in|₹28.8 $0.307|₹28.8 $0.307|[link](https://onlyscrews.in/products/m2-x-10mm-hex-allen-socket-head-high-tensile12-9-black-oxide-screw-dia-2mm-length-10mm?variant=49979287339321)|
|M2 Plain Washer SS304 (ID. 2.1mm OD:4.5mm T:0.5mm)|4|onlyscrews.in|₹2.4 $0.0256|₹2.4 $0.0256|[link](https://onlyscrews.in/products/m2-x-6mm-hex-allen-socket-head-high-tensile12-9-black-oxide-screw-dia-2mm-length-6mm?variant=49979039416633)|
|M2 Hex Nut Mild Steel with White Zinc Plating (Dia. 2mm)|4|onlyscrews.in|₹4 $0.0426|₹0.0426|[link](https://onlyscrews.in/products/m2-hex-nut-mild-steel-dia-2mm?variant=50252401246521)|
|M2 X 4mm Brass Threaded Inserts (Dia. 2mm, Length 4mm)|8|onlyscrews.in|₹21.6 $0.23|₹21.6 $0.23|[link](https://onlyscrews.in/products/m2-x-4mm-brass-threaded-inserts?variant=49423172829497)|
|16*2 I2C LCD|1|Local shop|Alr own|Alr own| |
|9V PP3 Battery|1|Local shop|Alr own|Alr own| |
|9V PP3 Battery connector clip|1|Local shop|Will purchase myself|Will purchase myself| |
|Sum||||$58.8217 excluding shipping cost of LCSC of $29.25 and $0.5224 of Robu,LionCircuits is free shipping,OnlyScrews has shipping cost of $0.6397| |
|Grand Total|||||$89.2338| |

 
Link to onshape doc: [Onshape](https://cad.onshape.com/documents/e0858d62bc807065493100b9/w/9e573f9273f6c5cefa0e0909/e/5fb6c5c268f4d3541bf88c26?renderMode=0&uiState=69cbe64c76ff3f85d768a45f)



