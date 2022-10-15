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


