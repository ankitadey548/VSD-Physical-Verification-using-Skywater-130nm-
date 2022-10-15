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


**Day2 : Lab2**

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



