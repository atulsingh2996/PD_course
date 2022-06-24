# PD_training_course
#Flow Diagram: ASIC design flow [OpenLANE]: 

 ![image](https://user-images.githubusercontent.com/108124284/175554215-99c2bd58-d7d9-490a-98a1-fdc260f82771.png)

#Different steps involved in flow- 

##(1) Design Preparation step-
Command: prep -design <design_name>
##(2) Synthesis – Synthesis is the process of transforming your RTL into a gate-level netlist, given all the specified constraints and optimization settings.
Command: run_synthesis
Calculating flop ratio- 

![image](https://user-images.githubusercontent.com/108124284/175554373-d7581753-2de1-42d8-9b0c-0742c75ea380.png)
![image](https://user-images.githubusercontent.com/108124284/175554396-215c4256-7b4a-4b9b-b398-1fb80011fbc2.png)

 

Flops ratio = (1613/14876) *100 = 10.8%

![image](https://user-images.githubusercontent.com/108124284/175554420-b6c7c1db-ea34-4f6e-893b-8b3f6800bc2e.png)
 
 ![image](https://user-images.githubusercontent.com/108124284/175554465-25c44dcd-4431-4205-a683-13580990be54.png)



##(3) Floor planning – In floorplanning, we define the size and shape of your chip or block, place the IO pins/pads, macros and blockage in the core or chip area to effectively find the routing space between them. 
Also, we reserve the place for standard cells at the floor planning stage.
Floor planning control parameters like aspect ratio and core utilization are defined as follows:
Aspect Ratio= Height/Width 
Utilization factor = Area occupied by netlist / total area of the core
Command: run_floorplan


Floorplan DEF-

 ![image](https://user-images.githubusercontent.com/108124284/175554498-1ab0f9a7-4dee-489d-a74a-67a1d19682dd.png)
![image](https://user-images.githubusercontent.com/108124284/175554534-d48f7b49-0d34-4a3a-8ac5-c672321d253e.png)

 
Std cells are not placed in floor plan step- 
 
![image](https://user-images.githubusercontent.com/108124284/175554560-872b5284-20a0-4430-aff9-af8d71759b46.png)

##(4) Placement- Placement is a step in the Physical Implementation process of placing the standard cell in a standard cell rows.
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

##(5) Standard cell design Flow- 
Cloning the GitHub data to the directory-

![image](https://user-images.githubusercontent.com/108124284/175555976-a68595ec-ce93-45d9-b459-d4b2f5fba73e.png)


Standard cell [Inverter] layout in Magic tool- 
 ![image](https://user-images.githubusercontent.com/108124284/175556006-df246dd9-9967-4a2a-bc12-4dd38eb61c91.png)

 ![image](https://user-images.githubusercontent.com/108124284/175556059-ce279af9-95c4-4246-9cd3-493ef0120304.png)


tkcon window-
 ![image](https://user-images.githubusercontent.com/108124284/175556096-a0aa702d-99c4-4d13-80c0-97953bcbfc03.png)

![image](https://user-images.githubusercontent.com/108124284/175556133-719ecc5b-8679-47f1-9e30-d7ca2c3df83a.png)


 ###Extracting-
![image](https://user-images.githubusercontent.com/108124284/175556223-4a17e9a7-0eab-487a-a923-916532eb202c.png)
Extracted parasitic through extract all –
![image](https://user-images.githubusercontent.com/108124284/175556264-226aab3f-5f73-4c49-aa60-3775ffe591b2.png)

Spice file generated from ex2spice command- 
![image](https://user-images.githubusercontent.com/108124284/175556363-2fe8363b-7509-45ba-b5c2-1e571d3ec1ae.png)


## SPICE characterization-
(1) Creating subckt file-

(2) Running ngspice-

![image](https://user-images.githubusercontent.com/108124284/175556548-d8af6400-adb0-4a03-aa75-759224b2b8af.png)

(3) Plotting output waveform-

![image](https://user-images.githubusercontent.com/108124284/175556624-0bf7f78b-8141-43a7-b19a-44e2e38da45f.png)

![image](https://user-images.githubusercontent.com/108124284/175556652-97170f43-f2ac-4401-935c-0d8b240dea03.png)


