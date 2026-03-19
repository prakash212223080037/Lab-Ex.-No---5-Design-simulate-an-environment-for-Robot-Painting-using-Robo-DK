Theory
Procedure
New project Follow these steps to create a new RoboDK project (RDK station):

Download and install RoboDK from the website: https://robodk.com/download
Double click the shortcut on the Desktop
If other stations are open: select File New Station (Ctrl+N) to start a new project Multiple RoboDK projects can be open at the same time. Double clicking the Station icon in the tree will activate and display that project.
Select a robot New robots can be added from a local drive or from the online library:

Select File Open online library (Ctrl+Shift+O). A new nested window will appear showing the online library It is also possible to select the corresponding button in the toolbar.
Use the filters to find your robot by brand, payload, ... In this example, we will use a UR10 robot (10 kg payload robot and 1.3 m reach).
Select Download. The robot should automatically appear in the station in a few seconds.
The online library can be closed once the robot is loaded
ct to a robot or with respect to other objects in the 3D space (including position and orientation). Note: More information about reference frames in RoboDK in the reference frames section. To add a new reference frame:
Select Program Add Reference Frame Alternatively, select the equivalent button in the toolbar
Double click the reference frame (on the tree or on the 3D geometry on the main screen) to enter the coordinates shown in the image (X,Y,Z position and Euler angles for the orientation). The mouse wheel can be used on top of each case to quickly update the position of the reference frame on the main screen. The following colors are used by default: o X coordinate  Red o Y coordinate  Green o Z coordinate  Blue o 1st Euler rotation  Cyan o 2nd Euler rotation  Magenta o 3rd Euler rotation  Yellow Tip: Select ToolsOptionsDisplayDisplay XYZ axis letters to see the Coordinate system axes.
Select ViewMake reference frames bigger (+) to increase the size of the reference frames
Select ViewMake reference frames smaller (-) to decrease the size of the reference frames
Select ViewShow/Hide text on screen (/) to show or hide the text on the screen
Optionally, rename any reference frame or object in the tree by selecting F2 image Import 3D objects RoboDK supports most standard 3D formats such as STL, STEP (or STP) and IGES (or IGS) formats. Other formats such as WRML, 3DS or OBJ are also supported (STEP and IGES are not supported on Mac and Linux versions). To load a new 3D file:
Select File Open
Select the object Object Inspection available in RoboDK’s default library: C:/RoboDK/Library/Object Inspection.
Alternatively, drag & drop files into RoboDK’s main window to import them automatically
Drag & drop the object to the reference frame Frame 2 (inside the station tree)
image Create a TCP New tools can be created in RoboDK from previously loaded 3D geometry:

Select File Open (as described in the previous section)
Select the Paint gun.stl file to add it as an object (it will be added at the robot base frame)
Drag & drop the object to the robot item inside the station tree as shown in the next image New tools can be loaded or saved as a .tool format. By default, RoboDK will define the TCP at the position [X,Y,Z]=[0,0,200] mm. This can be changed by entering the coordinates manually and/or by moving the TCP holding the ALT+Shift key as shown in the next image:
Hold ALT+Shift or select the highlighted button from the toolbar
Select the light blue plane (XZ plane of the TCP) and drag the TCP approximately towards the surface of the spray gun, as shown in the next image image image By default, RoboDK will define the TCP at the position [X,Y,Z]=[0,0,200] mm. This can be changed by entering the coordinates manually and/or by moving the TCP holding the ALT+Shift key as shown in the next image:
Hold ALT+Shift or select the highlighted button from the toolbar
Select the light blue plane (XZ plane of the TCP) and drag the TCP approximately towards the surface of the spray gun, as shown in the next imageGetting Started with RoboDK 7
Select the Green rounded arrow (rotation around the Y axis) to make the Z axis point outwards
Once an estimate of the coordinates is obtained it is possible to touch up these values manually by double clicking the Paint gun object. The mouse wheel can be used on top of each case to quickly update the position on the main screen. Note: These are estimate values according to the 3D drawings. If the definition of the TCP is calibrated on the robot it is possible to import it by pasting the coordinates in that box. By default, RoboDK will define the TCP at the position [X,Y,Z]=[0,0,200] mm. This can be changed by entering the coordinates manually and/or by moving the TCP holding the ALT+Shift key as shown in the next image:
Hold ALT+Shift or select the highlighted button from the toolbar
Select the light blue plane (XZ plane of the TCP) and drag the TCP approximately towards the surface of the spray gun, as shown in the next imageGetting Started with RoboDK 7
Select the Green rounded arrow (rotation around the Y axis) to make the Z axis point outwards
Once an estimate of the coordinates is obtained it is possible to touch up these values manually by double clicking the Paint gun object. The mouse wheel can be used on top of each case to quickly update the position on the main screen. Note: These are estimate values according to the 3D drawings. If the definition of the TCP is calibrated on the robot it is possible to import it by pasting the coordinates in that box. image Create Targets Robot positions are recorded as Targets. Follow these steps to create two targets as a new home target and approach target respectively:
Double click the robot to show the robot panel
Select Paint gun as the Tool Frame. Once a tool or a reference frame becomes active it will show a green dot.
Select Frame 2 as the Reference Frame
Hold the Alt key and move the robot by dragging it through the TCP or the robot flange to a safe position, free of collisions with any objects. Alternatively, move the coordinates of the Tool Frame (TCP) with respect to the reference Frame.
Use the Other configurations section to switch between different robot configurations and make sure that none of the robot axes are close to the axis limits. Tip: In general, it is better if the first target of a program has the joint axes as centered as possible (the joint sliders are as centered as possible, as shown in the following image). This makes sure that the robot won’t reach the axis limits as it follows linear moves along the program. This is possible by changing the robot configuration.
Select Program Teach Target (Ctrl+T), or the corresponding button in the toolbar (as shown in the image). The target will be placed as a dependency of the active reference frame and will automatically remember the current robot position (cartesian and joints axes). In this example, the robot joint coordinates used for the first target are: [-150, -75, -90, -60, 70, 110] deg. These values can be copied from this text and pasted in the Joint axis jog of the robot panel using the corresponding button.
image 7. Rename the first target as Home by pressing F2. Alternatively, select ToolsRename item. 8. Move the robot closer to one edge of the part (by dragging the tool using the Alt key, entering coordinates or jogging the axis manually) In this example we used the following robot joint coordinates [0,0,200,180,0,180] deg. 9. Select Program Teach Target (Ctrl+T) or the appropriate button in the toolbar to create a new target 10. Rename the target to Approach as shown in step 7 11. 11. Select the Home target and the Approach target alternatively to see the robot moving between the two targets 12. Right click the target and select Teach Current Position (Alt+double click) if a different position needs to be recorded for one of the targets 13. Right click the target and select Target Options… (F3) to open the target options window shown in the next image Add an Approach Program Follow these steps to create a program that moves from the Home target to the Approach target:

Select Program Add Program from the menu or the corresponding button in the toolbar (as shown in the next image)
Rename the program to ApproachMove
Select the Home target
Select Program Move Joint Instruction (or the corresponding button in the toolbar) Two instructions will be added automatically to tell the robot what tool frame and reference frames we are using Note: If no target is selected, a new target will be created at the same location of the robot.
Select the Approach target
Select Program Move Joint Instruction again Double click the ApproachMove program and it will execute the program simulation. The simulation bar and an estimated cycle time will be displayed.
image
Create Targets on Surface The Create Targets on Surface feature, is useful for applications such as painting or inspection:

Select Program Teach Target(s) on Surface (Ctrl+Shift+T)

Move the mouse cursor over the part to see a preview of what the robot looks like when it reaches the part

Select a few points on the object (left click). Each mouse left click will define a new target keeping the Z axis of the TCP normal to the surface (perpendicular to the surface).

If necessary, adjust the orientation around the Z axis by moving the wheel on the left panel or pressing the left/right keys.

Hold Alt to move an existing target

Hold Alt+Shift to move an existing target while keeping it on the surface

Select Esc key or right click on the screen and select Done to exit the Create Targets on Surface mode

image

Select all the targets created on the surface and right click Tip: Hold the Ctrl key to select multiple targets. Alternatively, select the Target 3, hold shift, then select Target 10 to select all targets between Target 3 and Target 10.

Select Rename group from the pop up menu

Enter Top Paint. All selected targets will be renamed and numbered.

Right click on the targets again and select Create Program. A new program will be generated. The first movement will be a joint move and following movements will be linear.

Select F2 to rename the program to PaintTop

Double click the PaintTop program to see the simulation moving along the targets

If required, reorder the movements by dragging the move instructions inside the program

image Add a Retract Program Similar to the previous operations:

With the robot placed at the last target, move the robot upwards by increasing the Z coordinate of the TCP with respect to the reference frame in the robot panel (highlighted case in the next image)
Select Program Add Program, or the appropriate button in the toolbar.
Select Program Move Linear Instruction, or the appropriate button in the toolbar . Rename it to Retract by pressing F2 key.
Select the Home target
Select Program Move Joint Instruction. A new move instruction will be added, linked to the Home target
image

##Program:

import sys
import os
sys.path.append(os.path.abspath(r"""E:/RoboDK/Posts/""")) # temporarily add path to POSTS folder

from KUKA_KRC2 import *

try:
  from robodk.robomath import PosePP as p
except:
  # This will be removed in future versions of RoboDK
  from robodk import PosePP as p


print('Total instructions: 9')
r = RobotPost(r"""KUKA_KRC2""",r"""KUKA KR 10 R1100 sixx""",6, axes_type=['R','R','R','R','R','R'], ip_com=r"""127.0.0.1""", api_port=20500, prog_ptr=2377978405712, robot_ptr=2377971867552)

r.ProgStart(r"""Mainprog""")
r.RunMessage(r"""Program generated by RoboDK v5.4.1 for KUKA KR 10 R1100 sixx on 25/06/2022 17:41:55""",True)
r.RunMessage(r"""Using nominal kinematics.""",True)
r.setFrame(p(-206.148,1000,7.71825,0,0,0),2,r"""Frame 2""")
r.setTool(p(90,-20,440,0,30,0),-1,r"""Paint gun""")
r.MoveJ(p(1117.69,-1105.76,609.887,-180,16.2113,180),[8.1549,-82.7436,76.9395,-7.66655,50.137,10.5943],[0,0,0])
r.MoveL(p(1235.57,-1105.76,604.6,-180,16.2113,180),[6.82687,-69.9098,61.3567,-6.19225,52.7071,8.49696],[0,0,0])
r.MoveL(p(1345.91,-1105.76,606.688,-180,16.2113,180),[5.9226,-54.7824,38.0585,-4.89732,60.7551,6.50306],[0,0,0])
r.MoveJ(p(1357.79,-949.963,595.297,-180,16.2113,180),[-4.77441,-53.7251,37.635,3.97689,60.0381,-5.29643],[0,0,0])
r.MoveL(p(1233.95,-949.963,593.928,-180,16.2113,180),[-5.59685,-70.5586,63.4585,5.1875,51.1405,-7.13955],[0,0,0])
r.MoveL(p(1095.8,-943.964,603.458,-180,16.2113,180),[-7.51287,-85.2609,80.4688,7.17889,49.0509,-9.9335],[0,0,0])
r.MoveJ(p(1095.8,-820.371,603.458,-180,16.2113,180),[-19.0983,-82.267,77.1178,17.4714,51.8805,-24.4696],[0,0,0])
r.MoveL(p(1254.3,-793.956,621.299,-180,16.2113,180),[-17.094,-63.3582,49.9712,14.2921,59.2667,-19.4312],[0,0,0])
r.MoveL(p(1354.51,-793.956,621.243,-180,16.2113,180),[-15.1431,-45.9352,20.6798,11.5454,70.4288,-14.5217],[0,0,0])
r.ProgFinish(r"""Mainprog""")
r.ProgSave(r"""C:/Users/Sudharshna/Documents/RoboDK""",r"""Mainprog""",True,r"""E:/RoboDK/Other/VSCodium/VSCodium.exe""")
Developed by: PRAKASH T RegisterNumber: 212223080037 */ simulation: image
<img width="1015" height="493" alt="444068094-b4127737-178f-402c-b70c-b52d77e2a1ef" src="https://github.com/user-attachments/assets/87ff9347-80ef-4deb-8d6b-c85a1c397802" />

Results:The painting environment for a serial manipluator has been created and the surface for the same has been thaught.
