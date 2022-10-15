# VSD-Physical-Verification-using-Skywater-130nm
![image](https://user-images.githubusercontent.com/115497145/195976739-00743831-0c13-4f2f-a1e0-1e8536c72bb2.png)

This report details the learning in 5-day Physical Verification workshop by VSD-IAT from Oct-10 2022 to Oct-14 2022. Below is a brief, day-wise documentation about the topics covered in the course.

**The tools used are**:
* magic
* xschem
* netgen
* ngspice



The libraries supported by open_pdks are:
*  Digital standard cells (ex: sky130_fd_sc_hd)
*  Primitive devices/analog (ex: sky130_fd_pr)
*  I/O cells (ex: sky130_fd_io)
*  3rd party libraries (ex: sky130_ml_xx_hd)

**MAGIC**
   * Handles GDS DEF and LEF, Does extraction and layouts are created and managed.
   * Mainly used to check DRCs and the violations can be fixed by following the design rules.
   * The layout is drawn based on the parameters used.
   * The tool magic looks like this

![magic pv](https://user-images.githubusercontent.com/115497145/195980126-0d239ced-28c2-43fd-a971-574530d00ae7.PNG)
![magic_with_nocon_nolayout pv](https://user-images.githubusercontent.com/115497145/195980134-b8b9f7a5-1e37-4b8e-9aea-821c09005dfe.PNG)
![magic_wnoconsole pv](https://user-images.githubusercontent.com/115497145/195980142-2c01be65-afb3-40b2-895b-47ca10689ee3.PNG)
* Two windows will pop up, when we type magic 
    * tkcon console
    * layout window

**Netgen**
* LVS tool that compares the layout design with its schematic between netlists to verify the geometries.
* Netgen will invoke one layout window & one console

![netgen pv](https://user-images.githubusercontent.com/115497145/195980148-aa0c3a58-1f96-46d5-8140-e6ea356071ce.PNG)
![netgen_noconsole pv](https://user-images.githubusercontent.com/115497145/195980155-206ee76e-ad28-468b-92d9-d68c5312923a.PNG)

**Ngspice**
* It is a Spice simulator, used to study the characteristics of the design
* The ngspice tool looks like this,

![ngspice pv](https://user-images.githubusercontent.com/115497145/195980159-a3a19935-5b9c-438c-906e-3ecfb8d9105c.PNG)

**Xschem** 
* Third repository for Schematic Editor that is used to create new schematics or can be used to import the schematics and generate nelists out of that. Xschem has symbol libraries to create schematics. It supports both ngspice for analog simulation and gaw for waveform viewing.
* Xschem looks like this

![Xschem pv](https://user-images.githubusercontent.com/115497145/195980099-afb8f552-d8d7-42fc-a330-f98e498f36af.PNG)


**Design Inverter**

Opening magic,

![magic pv](https://user-images.githubusercontent.com/115497145/195982284-362a83dd-8f94-440c-ab0d-a8ca0b26a318.PNG)

Opening Xschem,
 
![xschem_layout pv](https://user-images.githubusercontent.com/115497145/195982307-e8b703e8-38ac-4ae2-96c9-f9b9aabd64a4.PNG)

Nmos schematic, 

![nmos pv](https://user-images.githubusercontent.com/115497145/195982288-332adb84-32e9-448a-b78b-4e4edd7139af.PNG)

Inverter schematic,

![inverter_sch](https://user-images.githubusercontent.com/115497145/195982272-62a05a65-df86-458b-acb5-1df8f20a0834.PNG)

Inverter testbench,

![inverter_tb](https://user-images.githubusercontent.com/115497145/195982275-1daca4be-f5ac-4e45-9228-fdc3231d279f.PNG)

Inverter graph,

![inverter_graph](https://user-images.githubusercontent.com/115497145/195982252-6a64af22-828d-45a0-a835-5c8f60a3e0b6.PNG)



# Day - 2 Introduction to DRC and LVS

## GDS read
- Create a new project directory
- create a magic directory and copy the sky130 tech files
- open magic and understand different cif styles
  - *cif listall istyle* This lists all the available styles
  - *cif list istyle* This lists the current style
  - *cif istyle random* This lists the style random
  - *cif istyle sky130(vendor) is set*



Reading gds,

![gds_read](https://user-images.githubusercontent.com/115497145/195987057-38bff5ed-6f62-46c4-9551-c995fd98e205.PNG)

Reading vendor gds,


![history](https://user-images.githubusercontent.com/115497145/195987208-171126f3-a0f9-49dc-891e-efaaae1b1dbc.PNG)

![list_of_styles](https://user-images.githubusercontent.com/115497145/195987225-d4e754ac-f421-49cd-8c04-dfee4cfab3ec.PNG)

Extracting a SPICE netlist from magic

![and2_1_layout](https://user-images.githubusercontent.com/115497145/195987246-c3b3d83f-3d60-4c25-b1f8-a24459400cac.PNG)

![lef_read](https://user-images.githubusercontent.com/115497145/195987484-c7e75df8-c481-4640-86d1-bf7b4eadf526.PNG)

![ls_of_spice](https://user-images.githubusercontent.com/115497145/195987503-b29a10b6-c2d1-4b9f-948d-3df0df4f6767.PNG)


**Lab3 :Front-end and back-end DRC**

![gds read test](https://user-images.githubusercontent.com/115497145/195987521-7553d054-48f1-4210-8f0d-b468bfaa034e.PNG)

![gds write test](https://user-images.githubusercontent.com/115497145/195987575-82b958d4-fb95-46bf-853f-8dc39019932a.PNG)

![gds_write_test](https://user-images.githubusercontent.com/115497145/195987584-b3151386-5624-48c7-bb73-14122bc99f30.PNG)

![gds_write_test_property](https://user-images.githubusercontent.com/115497145/195987598-6c881149-1671-4733-97e3-5c0eb06dfe0a.PNG)

![loading drc cif style](https://user-images.githubusercontent.com/115497145/195987631-1b2670d3-a52e-4789-a689-b8269bc8c3fa.PNG)

![with_new_test_property](https://user-images.githubusercontent.com/115497145/195987650-82734312-8d5a-481e-85ba-bf09f55e65d1.PNG)


RC Extraction,

![rc_extraction](https://user-images.githubusercontent.com/115497145/195987884-2d2f1989-1452-4745-ae4b-290aab89d631.PNG)

DRC Error,

![drc error](https://user-images.githubusercontent.com/115497145/195987920-c816f0a8-55ae-4bc1-ab41-d0aa1f8ccd41.PNG)

![DRC](https://user-images.githubusercontent.com/115497145/195987953-2e20d038-a717-4a16-9eb6-b2bae38a026b.PNG)

Setup for lvs,

![lvs](https://user-images.githubusercontent.com/115497145/195988012-8e7affbc-a86d-4b2b-9e7e-e5b7181ef35a.PNG)


Creating an ECO & running xor


![xor](https://user-images.githubusercontent.com/115497145/195988028-3556aeee-727f-44ad-a5f2-c6eb87eb066e.PNG)

**Day3**

## Basic Rules
 - width-rule
   - select the area and choose DRC report (?). It details the error
   - The error is reported only for the area covered by the box
   - Pressing B key gives the dimensions of the box and grid on option helps view the grid
   - Select the box manually and paint it or use the following commands:
   - *:box width 0.14um*
   - *:paint m2*
 
 - Spacing rule
  - select the area until the white error dots and press key 6 to stretch the box.
  - Use move-stret-move command to manually spilt a single box to satisfy the rules.

- wide-spacing rule
  - select the smallest box and move the box by using key 6 and the issue is resolved
  
- notch_rule
  - select the box press key a and move the box by pressing key 8 as many times required


## Via Rules

### width-rule - both horizontally and vertically
- Select the area vertically and press "a" then press key 6 as many times required  to stretch the box horizontally 
- select the area horizontally and press "a" then press key 8 once and press up arrow as namy times required
- The below video explains in detail:



### Multiple vias
- Contact cuts can be seen using *cif see contact_name*
- Contacts filt based on the available space
- Details presented in the video below:


### Via overlap
- This can be resolved by growing the box in all directions.
- *Box grow c* (centre) doesn't solve the issue completely and hence *box grow e* (east) and *box grow w* 


# Day - 4 OpenLane FLow


# OpenLane flow - non-interactive
To do the open lane flow non-interactively:
- Choose OpenLane -> Designs -> Choose one design of choice
- src folder has the RTL design
- Config.tcl has all the parameters required to design and check the circuit
- Export the path as:
  export PDK_ROOT=/usr/share/pdk and run ./flow.tcl -design  <design name>
- It completes all the steps and generates gds files in the "runs" folder.
  

 ## Common DRC Errors
  - Follow the local interconnect rules
  - Plan the density in a appropriate way like, utilizatioln ratio and the cell density
  
    Here is a sample config.tcl parameters I used for the c17 design
  
 
  
## violations - Fixing manually
  
  - The violations are seen as white dots in the .mag file
  - To fix the DRC violatiolns manually, Choose .mag file of the error reported design and correct the violations by design rules and then save it to GDSII

#Day 5**

**Lab1**

Generating netlists from schematic,

![comp out](https://user-images.githubusercontent.com/115497145/195991251-45629128-6ddb-41a6-b06a-14d5a8f738d9.PNG)

![diff netA](https://user-images.githubusercontent.com/115497145/195991384-11315da1-f6cf-45e4-815b-18802c705450.PNG)


**Lab2**

Generating LVS netlists from layout,

![run lvs](https://user-images.githubusercontent.com/115497145/195991449-6dc16d3f-487a-4450-a077-7fa370d4042b.PNG)

![exercise_2_comp out](https://user-images.githubusercontent.com/115497145/195991464-bbf696ef-31ce-4547-8aee-4175f3aa1b12.PNG)


**Lab3**


![LVS DONE](https://user-images.githubusercontent.com/115497145/195991588-670c908d-0e79-476f-9cf8-bbdb1cb10b32.PNG)


**Lab4**

![lvs with spicelow_1](https://user-images.githubusercontent.com/115497145/195991607-6bd4d012-20bb-4bff-8cf1-7f4ecb319e8e.png)


**Lab5**

Netgen schematic,



![netgen_xschem](https://user-images.githubusercontent.com/115497145/195991648-f66f5a0d-846a-4ab4-8637-1cfd51eaf0d3.PNG)





![xschem user_analog_project_wrapper1](https://user-images.githubusercontent.com/115497145/195991677-e78eb8b3-187c-4044-918e-c1465198e917.PNG)

Testbench of schematic,







![xschem_tb](https://user-images.githubusercontent.com/115497145/195991692-e2e0bea5-42e1-4f9d-9318-2c0e2cecea16.PNG)





**Lab6**






![box_paint](https://user-images.githubusercontent.com/115497145/195991784-5ed72497-0a60-48f7-addb-d9198a4d4f61.PNG)





![example_por](https://user-images.githubusercontent.com/115497145/195991811-45c5f961-ee6a-48c3-a789-30e54b6a3584.PNG)




**Lab7**

Changing lvs script for running netgen,






![changes_in_run_lvs sh](https://user-images.githubusercontent.com/115497145/195991831-fc35884f-2640-4c76-a50b-6b2a3a851565.PNG)





Loading digital PLL




![digital_pll](https://user-images.githubusercontent.com/115497145/195991842-1d8a1e3a-2bc5-4cfa-98ac-561992ebf2e4.PNG)





![digital_pll spice](https://user-images.githubusercontent.com/115497145/195991848-501f02b3-24f7-4660-b178-48cee82c2ff8.PNG)





**Lab8**





![mgmt](https://user-images.githubusercontent.com/115497145/195991884-f018d2e4-9a64-4253-95ab-88280dd72228.PNG)





![mgmt_project](https://user-images.githubusercontent.com/115497145/195991896-c328c78f-7f10-4fc1-a2c5-8fbee13b020f.PNG)





![run_lvs sh](https://user-images.githubusercontent.com/115497145/195991901-cdcd0db0-e230-4709-83e8-f800e3e8b696.PNG)




**Lab11**




![example_por](https://user-images.githubusercontent.com/115497145/195991941-43814410-340a-4264-b757-b3535c450cd2.PNG)







![testbench for simple por](https://user-images.githubusercontent.com/115497145/195991971-6b0f4e47-28fc-49d0-a5b6-10f76c069a03.PNG)











