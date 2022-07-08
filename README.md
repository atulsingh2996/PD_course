# PD_training_course
# Flow Diagram: ASIC design flow [OpenLANE]: 

 ![image](https://user-images.githubusercontent.com/108124284/175554215-99c2bd58-d7d9-490a-98a1-fdc260f82771.png)

#Different steps involved in flow- 

## (1) Design Preparation step-

Command: prep -design <design_name>

## (2) Synthesis – Synthesis is the process of transforming your RTL into a gate-level netlist, given all the specified constraints and optimization settings.

Command: run_synthesis

Calculating flop ratio- 

![image](https://user-images.githubusercontent.com/108124284/175554373-d7581753-2de1-42d8-9b0c-0742c75ea380.png)
![image](https://user-images.githubusercontent.com/108124284/175554396-215c4256-7b4a-4b9b-b398-1fb80011fbc2.png)

 

Flops ratio = (1613/14876) *100 = 10.8%

![image](https://user-images.githubusercontent.com/108124284/175554420-b6c7c1db-ea34-4f6e-893b-8b3f6800bc2e.png)
 
 ![image](https://user-images.githubusercontent.com/108124284/175554465-25c44dcd-4431-4205-a683-13580990be54.png)



## (3) Floor planning – In floorplanning, we define the size and shape of your chip or block, place the IO pins/pads, macros and blockage in the core or chip area to effectively find the routing space between them. 
Also, we reserve the place for standard cells at the floor planning stage.
Floor planning control parameters like aspect ratio and core utilization are defined as follows:
Aspect Ratio= Height/Width 
Utilization factor = Area occupied by netlist / total area of the core
Command: run_floorplan


Floorplan DEF-

 ![image](https://user-images.githubusercontent.com/108124284/175554498-1ab0f9a7-4dee-489d-a74a-67a1d19682dd.png)
![image](https://user-images.githubusercontent.com/108124284/175554534-d48f7b49-0d34-4a3a-8ac5-c672321d253e.png)

 
Std cells are not placed in floor plan step- 
 
![image](https://user-images.githubusercontent.com/108124284/175557461-27636c6b-6347-47b8-b57c-b8d09c8c2de2.png)


## (4) Placement- Placement is a step in the Physical Implementation process of placing the standard cell in a standard cell rows.
There are two steps in placement:
(1) Global Placement: As a part of global placement all the standard cells will place in standard cell rows but there may be some overlap of standard cells.
(2) Detail Placement: All standard cells on standard cell rows will be legalized and refined and there will not be any overlaps.

Once the placement is done then we must check timing as well as congestion. Outputs from the placement will be netlist, def, and spef.

Viewing placement in Magic-
![image](https://user-images.githubusercontent.com/108124284/175555352-68366e98-5761-4e9f-99c6-c5bd4f489c5d.png)

![image](https://user-images.githubusercontent.com/108124284/175555383-1fa57851-b693-4305-ae46-8595cd307e8f.png)

![image](https://user-images.githubusercontent.com/108124284/175555405-ab6b0f64-02ae-4321-914d-463a59e5a478.png)

![image](https://user-images.githubusercontent.com/108124284/175555453-3be635fc-cd89-4e3b-8b2c-55a8c0bf99ef.png)

Standard cell placement- 

![image](https://user-images.githubusercontent.com/108124284/175555527-9eeaafb8-b47a-4df4-9e77-4089da5d3e33.png)

## (5) Standard cell design Flow- 
Cloning the GitHub data to the directory-

![image](https://user-images.githubusercontent.com/108124284/175555976-a68595ec-ce93-45d9-b459-d4b2f5fba73e.png)


Standard cell [Inverter] layout in Magic tool- 

copy the tech file from /home/kunalg123/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech to vsdstdcell dir then run-
 ![image](https://user-images.githubusercontent.com/108124284/175556006-df246dd9-9967-4a2a-bc12-4dd38eb61c91.png)

 ![image](https://user-images.githubusercontent.com/108124284/175556059-ce279af9-95c4-4246-9cd3-493ef0120304.png)


tkcon window-
 ![image](https://user-images.githubusercontent.com/108124284/175556096-a0aa702d-99c4-4d13-80c0-97953bcbfc03.png)

![image](https://user-images.githubusercontent.com/108124284/175556133-719ecc5b-8679-47f1-9e30-d7ca2c3df83a.png)


 ### Extracting-
![image](https://user-images.githubusercontent.com/108124284/175556223-4a17e9a7-0eab-487a-a923-916532eb202c.png)
Extracted parasitic through extract all –
![image](https://user-images.githubusercontent.com/108124284/175556264-226aab3f-5f73-4c49-aa60-3775ffe591b2.png)

Spice file generated from ex2spice command- 
![image](https://user-images.githubusercontent.com/108124284/175556363-2fe8363b-7509-45ba-b5c2-1e571d3ec1ae.png)


## SPICE characterization-
(1) Creating subckt file-

![image](https://user-images.githubusercontent.com/108124284/177946824-ae073636-a352-4c77-86d1-7c425710925e.png)


(2) Running ngspice-

![image](https://user-images.githubusercontent.com/108124284/175556548-d8af6400-adb0-4a03-aa75-759224b2b8af.png)

(3) Plotting output waveform-

![image](https://user-images.githubusercontent.com/108124284/175556624-0bf7f78b-8141-43a7-b19a-44e2e38da45f.png)

![image](https://user-images.githubusercontent.com/108124284/175556652-97170f43-f2ac-4401-935c-0d8b240dea03.png)

## Enabling grid in layout-–

![image](https://user-images.githubusercontent.com/108124284/175800897-4a87e354-8342-4cce-9d61-27e8e25adc16.png)

![image](https://user-images.githubusercontent.com/108124284/175800902-32853728-3a3a-4aa3-99dd-5a5eefccc047.png)

Writing lef file of the inverter-

![image](https://user-images.githubusercontent.com/108124284/175800911-235bb333-8d47-4295-b5fd-02a786cb225f.png)

![image](https://user-images.githubusercontent.com/108124284/175800913-eedb6d33-f3fe-4306-9b97-9805cfc37967.png)

Include the cell data in design data- 
-copy the inv lef file and lib file(from vsdstdcelldesign/libs to picorv32a/src folder)

After including inv cell – 

![image](https://user-images.githubusercontent.com/108124284/175800925-168c8e23-9c16-4fd2-b1c8-f8fe65440fa9.png)
We resolved this warning by making required changes in the config file and final config file is pasted below.

Config file to merge lef and do prep design-

In the design's config.tcl file add the below line to point to the lef location which is required during spice extraction.

    set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]
    
![image](https://user-images.githubusercontent.com/108124284/175800938-3caa9b4a-8228-4d1d-8918-56e5eeed8a8d.png)

After running prep -design picorv32a -tag dir_name -overwrite 

![image](https://user-images.githubusercontent.com/108124284/177954527-50646b7d-81fd-4609-896f-573c50edbc45.png)

 
--run these commands to add all the reuired lef files-
 Include the below command to include the additional lef into the flow:
 
    set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
 
    add_lefs -src $lefs

 ![image](https://user-images.githubusercontent.com/108124284/177954086-955cd05a-691e-46da-bd8f-946bd71451d9.png)

 
Running synthesis – **our cell is added**.
![image](https://user-images.githubusercontent.com/108124284/175800958-459c54ef-4311-45f8-a931-26049b9ceaa1.png)

Merged.lef is created here-
![image](https://user-images.githubusercontent.com/108124284/175800972-b772defe-1088-4e04-a562-6ca317f8a45c.png)




