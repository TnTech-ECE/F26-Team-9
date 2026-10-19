# Conceptual Design

This document outlines the objectives of a conceptual design. After reading your conceptual design, the reader should understand:

- The fully formulated problem.
- The fully decomposed conceptual solution.
- Specifications for each of the atomic pieces of the solution.
- Any additional constraints and their origins.
- How the team will accomplish their goals given the available resources.

With these guidelines, each team is expected to create a suitable document to achieve the intended objectives and effectively inform their stakeholders.


## General Requirements for the Document
- Submissions must be composed in Markdown format. Submitting PDFs or Word documents is not permitted.
- All information that is not considered common knowledge among the audience must be properly cited.
- The document should be written in the third person.
- An introduction section should be included.
- The latest fully formulated problem must be clearly articulated using explicit "shall" statements.
- A comparative analysis of potential solutions must be performed
- The document must present a comprehensive, well-specified high-level solution.
- The solution must contain a hardware block diagram.
- The solution must contain an operational flowchart.
- For every atomic subsystem, a detailed functional description, inputs, outputs, and specifications must be provided.
- The document should include an acknowledgment of ethical, professional, and standards considerations, explaining the specific constraints imposed.
- The solution must include a refined estimate of the resources needed, including: costs, allocation of responsibilities for each subsystem, and a Gantt chart.


## Introduction

The introduction is intended to reintroduce the fully formulated problem. 

Commercial water heating systems play an important role in providing reliable hot water for applications such as apartments, hotels, restaurants, and other commercial facilities. These systems must be capable of meeting varying hot water demands while maintaining a consistent outlet temperature and sufficient flow rate. The Regent Commercial Tankless Water Heater is designed to heat water as it passes through the system rather than storing a large volume of heated water in a tank. Although this design allows the unit to provide hot water on demand, the system must respond to changes in water flow and temperature to maintain the desired performance. As hot water demand changes, the amount of energy required to heat the incoming water also changes. This creates an opportunity to investigate how the system can adjust its operation to meet actual demand without using its maximum operating capacity.

The objective of this project is to develop and evaluate a control strategy that adjusts water flow and heating operation based on real-time temperature and demand measurements. The proposed strategy will use components such as a variable-speed pump, flow sensor, and inlet and outlet temperature sensors to monitor system conditions and determine when adjustments are needed. By using this feedback, the control system will aim to regulate water flow and coordinate heating operation to provide the required outlet temperature while minimizing unnecessary energy consumption. As hot water demand changes, the system will respond by adjusting its operating conditions rather than continuously relying on maximum capacity when it may not be necessary. The team will investigate how changes in flow rate affect heat transfer, temperature regulation, and electrical power consumption to determine the most effective control approach. Engineering calculations, computer simulations, and testing will be used to evaluate the proposed strategy under different operating conditions and assess its ability to balance energy efficiency with consistent hot water delivery. Ultimately, the goal is to establish an algorithm that improves the energy efficiency of the Regent Commercial Tankless Water Heater without compromising its performance or reliability.

## Restating the Fully Formulated Problem

The fully formulated problem is the overall objective and scope complete with the set of shall statements. This was part of the project proposal. However, it may be that the scope has changed. So, state the fully formulated problem in the introduction of the conceptual design and planning document. For each of the constraints, explain the origin of the constraint (customer specification, standards, ethical concern, broader implication concern, etc).

The primary objective of this project is to develop and evaluate a control strategy for adjusting the pump speed of the Lochinvar Regent Commercial Instantaneous Water Heater based on changing operating conditions. Lochinvar is interested in determining whether reducing pump speed can decrease electrical energy consumption without compromising the performance of the water heating system when full circulation is unnecessary. Because hot water demand varies throughout the day, the pump may not need to operate at a constant speed under every condition. However, reducing pump speed must be carefully evaluated to ensure sufficient water flow through the heat exchanger and the ability to maintain the required water temperature.

The project will investigate the relationship between pump speed, water flow rate, inlet water temperature, and heater operation to determine how these variables affect system performance. The team will develop and evaluate a proposed control strategy that uses operating measurements to determine an appropriate pump speed under different conditions. Although the Regent is the intended application, testing may use the Lochinvar equipment available in the Tennessee Tech laboratory or additional equipment provided by Lochinvar, depending on hardware compatibility and availability. The boilers available at Tennessee Tech are also being used by other capstone teams, which may limit our access to the equipment. As a result, testing may need to rely on simulations and available operating data to identify operating conditions under which pump speed can be reduced while maintaining acceptable water heating performance.

The proposed design shall meet the following requirements:

1. Pump speed control: The pump shall be able to run at different speeds based on the system's needs.
*	Variable-speed control is the main focus of this project. Adjusting pump speed may help reduce unnecessary electrical energy use while maintaining proper water flow through the system.
  
2. Operating measurements: The system shall measure or collect water flow rate, inlet water temperature, and other available data about the water heater.
*	These measurements will help the team understand how changes in water flow and temperature affect the heater's performance and determine how the pump should be controlled.
  
3. Performance evaluation: The team shall study how pump speed, water flow, inlet water temperature, and heater operation affect system performance.
*	Evaluating these factors will help determine whether changing pump speed can improve energy efficiency without negatively affecting the water heater's operation.
  
4. Minimum flow requirements: The pump shall maintain enough water flow through the heat exchanger to meet the manufacturer's requirements.
*	Maintaining sufficient flow is necessary to help prevent overheating and ensure the equipment operates within its specified limits.

5. Water temperature requirements: The proposed control strategy shall allow the water heater to reach and maintain the required water temperature.
*	The control strategy must consider water temperature so that energy savings do not come at the expense of the heater's intended performance.

6. Energy efficiency: The team shall evaluate whether running the pump at lower speeds can reduce electrical energy use.
* Comparing pump energy consumption at different speeds will help determine whether variable-speed control offers potential energy savings.

7. Equipment compatibility: All components shall work together properly with the equipment used for testing.
*	The team may use the Regent water heater, other compatible Lochinvar equipment, or laboratory simulations, depending on equipment availability.

8. Testing and validation: The team shall evaluate the proposed control strategy using calculations, simulations, and laboratory testing when possible.
*	These methods will help determine whether the proposed strategy is technically feasible and whether additional testing is needed.

9. Project feasibility: The proposed design shall fit within the available budget, equipment, schedule, and team resources.
*	These limits will help the team develop a realistic solution that can be completed within the capstone project timeline.

In summary, this project will investigate whether adjusting the internal circulation pump speed of the Lochinvar Regent Commercial Instantaneous Water Heater can reduce electrical energy consumption while maintaining reliable water heating performance. By evaluating pump speed, water flow rate, inlet water temperature, and heater operation, the team will develop and assess a proposed control strategy. Calculations, simulations, and laboratory testing, when available, will be used to compare energy consumption and system performance under different operating conditions. The final goal is to determine the feasibility of variable-speed pump control and identify opportunities to improve energy efficiency without compromising the water heater's operation.



## Comparative Analysis of Potential Solutions

In this section, various potential solutions are hypothesized, design considerations are discussed, and factors influencing the selection of a solution are outlined. The chosen solution is then identified with justifications for its selection.


## High-Level Solution

This section presents a comprehensive, high-level solution aimed at efficiently fulfilling all specified requirements and constraints. The solution is designed to maximize stakeholder goal attainment, adhere to established constraints, minimize risks, and optimize resource utilization. Please elaborate on how your design accomplishes these objectives.



   The proposed solution is to develop a variable speed pump controller that is able to reduce unneeded use of electrical energy while maintaining the performance of Lochinvar's water heating system. Rather than having the circulation pump run at a constant speed, the controller will adjust the speed of the pump based on the system's running conditions. Measurements such as the water flow rate, inlet and outlet water temperatures, and boiler firing rate will help determine when the speed of the pump can be reduced without affecting the system's ability to deliver hot water. The overall design will consist of six subsystems: Sensor and Data Acquisition, Microcontroller and Control Logic, Pump and Motor Control, Water Heating and Hydraulic, Monitoring and Performance Evaluation, and Data Logging and Simulation. Each subsystem will have a certain role in helping the controller run properly and meet the project's requirements.

   The Sensor and Data Acquisition subsystem will collect measurements from the water-heating system and send them to the controller. The Microcontroller and Control Logic subsystem will process this information and determine the appropriate pump speed based on the control algorithm and established operating limits. The Pump and Motor Control subsystem will acquire the command and adjust the speed of the pump using hardware that is compatible.
The Water Heating and Hydraulic subsystem will include the physical equipment involved in the system, such as the pump, piping, circulation loop, boiler, and heat exchanger. Because the changes in pump speed can affect the water flow and heat transfer, the system's response will need to be observed cautiously. The Monitoring and Performance Evaluation subsystem will help decide how well the controller performs by analyzing the electrical power use, water flow, temperature stability, and the time required to reach the wanted temperature. The Data Logging and Simulation subsystem will log measurements and help the team compare results from different running conditions. If enough information is available from the system, simulation software such as Dymola may also be used to study how the system is expected to react.

   All six subsystems will work together to help the controller react to changes in hot water demand. The sensors will give updated measurements, the controller will use those measurements to decide the speed of the pump, and the pump control hardware will make the needed adjustment. The resulting changes in the flow and temperature will then be observed to gauge the system's performance.

   The main focus is to reduce the pump energy consumption without negatively affecting the water heater's process. The pump must have the ability to maintain the minimum flow necessary by the manufacturer, and the system must still reach and maintain the required water temperature. The team will use calculations, simulations, and lab testing when possible to gauge the proposed design. Although the Regent Commercial Instantaneous Water Heater is the planned application, the equipment used for testing will depend strictly on availability and compatibility. The results will help determine whether the variable speed pump control is a realistic way to improve energy efficiency while keeping trustworthy hot water performance.

### Hardware Block Diagram

Block diagrams are an excellent way to provide an overarching understanding of a system and the relationships among its individual components. Generally, block diagrams draw from visual modeling languages like the Universal Modeling Language (UML). Each block represents a subsystem, and each connection indicates a relationship between the connected blocks. Typically, the relationship in a system diagram denotes an input-output interaction.

In the block diagram, each subsystem should be depicted by a single block. For each block, there should be a brief explanation of its functional expectations and associated constraints. Similarly, each connection should have a concise description of the relationship it represents, including the nature of the connection (such as power, analog signal, serial communication, or wireless communication) and any relevant constraints.

The end result should present a comprehensive view of a well-defined system, delegating all atomic responsibilities necessary to accomplish the project scope to their respective subsystems.

<img width="874" height="1104" alt="block-diagram-capstone" src="https://github.com/user-attachments/assets/565693de-2806-4bfb-9ca7-e67828a2532c" />


### Operational Flow Chart

Similar to a block diagram, the flow chart aims to specify the system, but from the user's point of view rather than illustrating the arrangement of each subsystem. It outlines the steps a user needs to perform to use the device and the screens/interfaces they will encounter. A diagram should be drawn to represent this process. Each step should be represented in the diagram to visually depict the sequence of actions and corresponding screens/interfaces the user will encounter while using the device.


<img width="1044" height="780" alt="flowchart-capstone" src="https://github.com/user-attachments/assets/edd6917d-b1f9-4489-a623-1d80af3193c1" />


## Atomic Subsystem Specifications


### 1) Sensor and Data Acquisition Subsystem


Overview:

The Sensor and Data Acquisition Subsystem will provide real-time and high-fidelity monitoring of all the critical hydraulic and thermal parameters within the heating loop. It shall ensure the pump microcontroller maintains a continuous stream of accurate measurements. These measurements will be the flow rate, outlet temperature, and boiler firing rate for the necessary data that will be needed for the circulation pump to be accurate. The design should emphasize signal control and sensor responsiveness.


Functional Description:

This subsystem's core function is to capture continuous live operating data of the heating loop and transmit it to the pump's microcontroller. This will prepare raw data for safe digital processing. 
	
* Real-time data collection: Pump system variables at sampling intervals, track fluctuating fluid velocity, thermal output and thermal input back into the boiler, and the boiler load.
  
* Industrial Signal Compatibility: Use hardware scaling to convert high-voltage analog inputs and digital frequencies into a safe manner for the microcontroller to read.
  
* Measure Responsiveness: Shall optimize the thermal and fluid feedback to ensure it is energy efficient and saves water while maintaining the temperature.

In addition, this subsystem would also need to be able to communicate with the boiler's main controller and display screen. It will share the temperature values from the pump controller and display real-time temperatures on the screen. This helps give a parameter visibility of live water temperatures.


Subsystem Interface:

1) Enviromental Input
   * Connected to: Water heating and hydraulic subsystem.
   * Description: Gathers raw physical fluid velocity and thermal energy changes directly from 	the piping by sensors.
     
2) Boiler Load Input
   * Connected to: Water Heating and Hydraulic Subsystem.
   * Description: Intercepts the boiler firing rate signal and captures the active heating demand.
     
3) Condition Data Output
   * Connected to: Microcontroller and Control Logic Subsystem.
   * Description: Transmits filtered, scaled analog voltages and digital pulses to the processing pins of the microcontroller.
     
4) Data Output
   * Connected to: Monitoring and performance evaluation subsystem.
   * Description: Gives real-time flow rates and temperature measurements for diagnostic checking.
     

Subsystem Operation:

1) Initialization Phase
   * The microcontroller will establish connection loops and verify stable reference points.
   * If any sensors are broken or out of bounds, a fault will be triggered to prevent the pump from running dry.
     
2) Data Ingestion Phase
   * The subsystem will start capturing raw inputs from the sensors on the heating loop.
     
3) Filtering and Calibration Phase
   * Capture the raw data from the analog and digital signals.
   * Filter out any high-frequency noise.
   * Take the raw data and convert it into values to read.
     
4) Transmission phase
   * Verified output data will be sent to the display screen.


Expected User Interaction:

1) Installation and Commissioning Phase
   * Physically mount the flow meter and temperature sensor.
   * Wire the sensors and boiler to the microcontroller.

2) Calibration Phase
	* Check the sensors against already calibrated sensors to make sure they are accurate readings.

3) Passive Monitoring Phase
	* Observe the continuous readings from the sensors.

4) Maintenance and Diagnostics Phase
	* If there is a fault, use diagnostic skills to help with troubleshooting any faults.

No direct user control of the raw voltage scaling, filtering or sensor calibration frequency.


Functional FLow Chart:

<img width="902" height="398" alt="image" src="https://github.com/user-attachments/assets/c7d8ce99-d4ac-42b1-9b6d-15a99f1c3480" />



Specifications:

1) This subsystem shall read data from the temperature sensor.

2)	This subsystem shall read data from the flow meter.
   
3)	This subsystem shall update all data every how many seconds we choose.
   
4)	This subsystem shall send a fault error if there is any out-of-bounds data or if there is a broken connection.
   
5)	This subsystem shall send data to the microcontroller .




### 2) Microcontroller and Control Logic Subsystem

Overview: 

   The Microcontroller and Control Logic subsystem will act as the decision-making part of the variable-speed pump controller. Its main job will be to use the measurements collected from the water-heating system to determine an appropriate pump speed. The controller will consider available information, such as water flow rate, water temperature, and boiler firing rate, to help determine when the pump can operate at a lower speed.
   The control algorithm must balance energy savings with the system's operating requirements. For example, reducing pump speed too much could cause the water flow to fall below the manufacturer's minimum requirement or affect the system's ability to maintain the desired temperature. Because of this, the controller will need to follow established operating limits when determining the pump-speed command.
   The microcontroller will receive measurements from the Sensor and Data Acquisition subsystem, process the information, and send a command to the Pump and Motor Control subsystem. After the pump speed changes, updated measurements will help the team evaluate how the system responds. This process will be used to test and improve the control algorithm. The specific microcontroller, control algorithm, and communication methods will be chosen after the team confirms which hardware is available and compatible with Lochinvar's equipment.
	

Inputs:

* Water flow rate measurements from the Sensor and Data Acquisition subsystem.
* Inlet and outlet water temperature measurements, when they are available.
* Boiling firing rate information, when it is available and compatible with the controller.
* Manufacturer running limits, in which includes the minimum required water flow.
* Target the running conditions and control settings created during testing.

Outputs:

* Pump speed commands that are sent to the Pump and Motor subsystem.
* Related running information sent to the Data Logging and Simulation subsystem.
* Controller status or fault information, if supported by the chosen hardware.
  

Interfaces and Procedure:

   The subsystem will get measurements from the Sensor and Data Acquisition subsystem. Depending on the chosen sensors and hardware, these measurements may be provided through analog voltage signals, digital signals, or digital communication. The microcontroller will process the new information and use the control algorithm to decide the suitable pump speed command. The command sent to the pump-control hardware must use a signal or communication approaches supported by the chosen equipment. The exact interface will be decided during detailed design after the team verify the pump's control requirements.
   During the procedure, the controller will read the accessible measurements, evaluate the current state, and calculate a pump speed command. The pump control hardware will then adjust the pump as instructed. The updated measurements will help determine whether the adjustment creates the expected results. If the measurements suggest an unsafe or unacceptable operating procedure, the controller will need to follow a response created during the design process with Lochinvar.


Specifications:

1. The subsystem shall process the accessible flow rate, temperature, and boiler running measurements needed by the control algorithm.

2. The subsystem shall determine pump speed commands depending on the current running conditions and created control logic.

3. The subsystem shall prevent pump speed commands from falling below the minimum permitted running level created from manufacturer requirements and hardware limitations.

4. The subsystem shall sustain changes in pump speed as system demand changes, while staying within the created operating limits.

5. The subsystem shall send pump speed commands through an interface compatible with the selected pump control hardware.

6. The subsystem shall provide applicable operating information to the Data Logging and Simulation subsystem for analysis.

7. The subsystem shall be tested to determine whether the control algorithm can reduce pump energy consumption while still maintaining acceptable flow and temperature performance.

8. The subsystem shall define how it responds to null sensor measurements or operating conditions outside the permitted limits before implementation.

9. The subsystem shall run within the processing, memory, electrical, and communication limits of the chosen microcontroller.




### 3) Pump and Motor Control Subsystem

Overview:
The pump and motor control subsystem will take the controller's command and change the circulation pump speed to meet that demand. It will ensure the system adjusts the pump speeds based on the control command and demand. The design should emphasize operating within the pump's allowable speed, prevent motor strain, and provide the correct circulation needed to maintain the desirable water temperature.


Functional Description:
This subsystem's core function is to receive the calculated speed instructions from the pump's controller and use that to vary the circulation pump during different demand situations and maintain the desired water temperature. This will prepare digital signals for high-efficiency mechanical work.

1) Speed Modulation
   * Responds directly to incoming signals by altering the voltage or frequency line to the pump. This will allow the pump to adjust the speed based on the control command.
     
2) Operational Range Control
   * This makes sure the pump's motor is operating within the pump's allowable range.
   * Protects the motor from spinning too fast or stalling below its limit.
     
3) Thermal System Balancing
   * Regulates flow velocity to provide the circulation needed by the heat exchanger to keep the desired temperature under fluctuating demands.

In addition, the subsystem should provide running data for evaluations. This will share motor speed based on flow speeds and temperature readings for lab testing.


Subsystem Interface:

1) Control Logic Input
   * Connected To: Microcontroller and Control Logic Subsystem.
   * Description: Receives the low-voltage speed commands and safety faults calculated by the microcontroller.

2) Mains Power Input
   * Connected to: Water Heating and Hydraulic Subsystem.
   * Description: Connects to the 120VAC to supply the pump with power.
     
3) Mechanical Circulation Output
   * Connected to: Water Heating and Hydraulic Subsystem.
   * Description: Delivers control signals and power to the pump to control the motor's speed.
     
4) Operational Data Outpu
   * Connected to: Monitoring and Performance Evaluations Subsystem.
   * Description: Transmits real-time data to observe the motor speed.


Subsystem Operation:

1) Initialization Phase
   * During system startup, the pump controller will establish safe boundaries.
   * Verifies that the pump is operational and no faults have occurred.
     
2) Demand Activation Phase
   * Delivers 120 VAC to the pump.

3) Modulation Phase
   * During run time, raw data for the speed commands is captured.
   * System will continuously adjust pump speeds based on control command, water flow, and the water temperature.

4) Shutdown and Failsafe Phase
   * If there is a control logic fault or a communication fault, the subsystem will go into action and make sure the water will not overheat.
   * It will make sure there are safety measures put into effect in case of a fault.

Expected User Interaction:

1) Monitoring the active speed.
2) Monitor if the pump is operating within a safe boundary.
3) Could have an override program for maintenance.

No direct user control of frequency, pump speed, voltage scaling, or safety switching loops. Pumps' minimum and maximum speed can be programmed through the microcontroller's interface.


Functional Flow Chart:

<img width="938" height="413" alt="image" src="https://github.com/user-attachments/assets/fd6183a5-1590-4aad-a969-2af56a5a9838" />


Specifications:

1) This subsystem shall capture the microcontroller's command and change the circulation pump speed dynamically.
   
2) The subsystem shall operate within the pump's allowable speed range.

3) The subsystem shall transmit live motor speeds to the microcontroller's display.
   
4) This subsystem shall keep the pump speed so the heat exchanger keeps the desired water temperature.
	



### 6) Data Logging and Simulation Subsystem

Overview:

   The Data Logging and Simulation subsystem will help the team to collect data, analyze the system's performance, and evaluate the proposed pump control strategy. Its main purpose will be to record measurements from testing so the team can compare how the system performs at different pump speeds and under different running conditions. Depending on the available equipment, the recorded data may include the speed of the pump, water flow rate, inlet and outlet water temperatures, boiler firing rate, and pump electrical power. The team will use this information to create graphs, identify direction, and compare the system's energy consumption and water heating performance. These results will help the team to decide whether reducing the speed of the pump can save energy without negatively affecting water flow or temperature.
   Simulation may also be used to learn how the system responds to changes in pump speed and hot water demand. If enough system information is available, the team may use Dymola or another appropriate simulation application to model the system's performance. The simulation results can then be compared with labo measurements or data provided by Lochinvar, when it's available. This comparison will help the team decide whether the model relatively represents the actual system. This subsystem will mainly support testing, analysis, and design improvements. Unless additional hardware and software are chosen for real time integration, the logging and simulation software will not directly control the actual pump during normal procedure.


Inputs:

* Water flow rate measurements from the Sensor and Data Acquisition subsystem.
* Inlet and outlet water temperature measurements, when it's available.
* Pump speed measurements or commanded pump speed values.
* Boiler firing rate information, when it's available.
* Pump electrical power measurements, if appropriate measurement equipment is available.
* Test conditions and target procedure values.
* System parameters and measured data needed to develop/evaluate a simulation model.
  
Outputs:

* Organized records of procedure measurements.
* Graphs and comparisons of pump speed, flow rate, temperature, and electrical power.
* Calculated performance results, including energy use and time to reach the desired temperature when enough data is available.
* Simulation results showing predicted system performance under chosen running conditions.
* Analysis that helps the team evaluate and improve the proposed control strategy.
  

Interfaces and Procedure:

   The subsystem will get data from the sensors, controller, and performance monitoring equipment. Depending on the chosen hardware and software, information may be handed over through digital communication, stored files, or manual data export. The exact methods and data formats will be decided during detailed design.
During lab testing, the team will take note of measurements while the pump runs under different conditions. The measurements will be organized so that results from different pump speeds and demand levels can be compared.          For simulation, the team will use available system information to decide whether an appropriate model can be developed. The model may help examine running conditions that are difficult to reproduce in the lab. When measured data is available, the team will compare the simulation results with the actual results to recognize the differences and decide whether the model needs further adjustments.
   The results from this subsystem will help the team decide whether the proposed control strategy will meet the project's requirements. If the data shows that certain pump speeds cause problems with flow or temperature, that information can be used to make changes to the control algorithm and testing in the future.


Specifications:

1. The subsystem shall record the available running measurements needed to assess the variable speed pump controller.

2. The subsystem shall correlate recorded measurements with the corresponding test conditions when that information is available.

3. The subsystem shall organize recorded data in a format appropriate for analysis, graphing, and comparison.

4. The subsystem shall assist comparisons of electrical energy consumption at different pump running conditions when appropriate power measurements are available.

5. The subsystem shall sustain the assessment of water flow, temperature stability, and time to reach the wanted temperature using available test data.

6. The subsystem shall sustain the development/use of a simulation model if adequate system information and appropriate software is available.

7. The subsystem shall sustain comparisons between simulation results and measured data when appropriate measurements are available.

8. The subsystem shall document the assumptions, limitations, and data sources used in its analysis and simulations.

9. The subsystem shall deliver results that can be used to assess and improve the proposed control strategy.

10. The subsystem shall document test conditions and data processing methods so that the results can be analyzed and compared consistently.

    
    

Based on the high-level design, provide a comprehensive description of the functions each subsection will perform.

Inclued a description of the interfaces between this subsystem and other subsystems:
- Give the type of signal (e.g. power, analog signal, serial communication, wireless communication, etc).
- Clearly define the direction of the signal (input or output).
- Document the communication protocols used.
- Specifying what data will be sent and what will be received.

Detail the operation of the subsystem:
- Illustrate the expected user interface, if applicable.
- Include functional flowcharts that capture the major sequential steps needed to achieve the desired functionalities.

For all subsystems, formulate detailed "shall" statements. Ensure these statements are comprehensive enough so that an engineer who is unfamiliar with your project can design the subsystem based on your specifications. Assume the role of the customer in this context to provide clear and precise requirements.


## Ethical, Professional, and Standards Considerations

The development of this variable circulation pump controller project has implications across environmental, societal, economic, scientific, cultural, and ethical domains. These considerations directly influence the controller’s design and the engineering practices required to develop a reliable and efficient system. Throughout the project, the team must consider how the controller will affect facility operations, public health and safety, energy consumption, and future applications developed by Lochinvar.

From an environmental perspective, the controller should be designed to maximize energy efficiency and support water conservation compared with the current fixed-speed circulation pump. Developing a controller that adjusts pump operation based on system demand could reduce unnecessary energy consumption and decrease the facility’s overall carbon footprint. By allowing the pump to operate at different speeds rather than continuously operating at a fixed speed, the controller could improve energy efficiency during periods of lower demand. These environmental considerations will influence the control logic by prioritizing efficient pump operation while maintaining the required water temperature and circulation conditions.

From a societal standpoint, the variable circulation pump controller must feature an intuitive user interface to help operators manage the pump across different commercial facilities. The system must continuously respond to fluctuating peak demands while maintaining strict temperature stability parameters. If the pump fails to satisfy these demands, it could result in financial losses, interruptions in facility operations, and risks to public health and safety. Therefore, the controller should be designed to provide reliable operation, accurate temperature monitoring, and consistent performance under changing operating conditions. These design considerations would help improve the overall reliability of the facility’s water circulation system.

From an economic perspective, implementing a variable circulation pump controller could reduce operating expenses by adjusting the pump’s performance to match system demand. Compared with a fixed-speed circulation pump, the variable controller could reduce unnecessary energy consumption during periods of lower demand. However, these potential savings must be considered alongside the controller’s initial cost, maintenance requirements, and equipment reliability. A system failure could result in additional maintenance costs, equipment damage, or interruptions in facility operations. Therefore, the design should prioritize long-term performance, efficient energy consumption, and reliability while minimizing unnecessary operating expenses.

From a scientific perspective, the variable circulation pump controller must incorporate an accurate and stable control loop capable of responding to changing operating conditions. The accuracy of the controller can be supported by field data provided by Lochinvar from its testing locations. This information will provide physical measurements that can be used to develop, configure, and validate the controller’s logic. Without accurate data, cross-referencing simulation predictions with actual system performance would be difficult and could reduce the reliability of the final design. Standardizing data-collection and testing procedures could improve simulation accuracy, help identify anomalies, and allow the team to make necessary adjustments to the controller. These practices will help ensure that the system responds appropriately to changes in temperature and demand.

Ethical responsibilities are integrated into the design and implementation of the project. As engineers, the team is committed to ensuring the accuracy and integrity of its methodology and data. This commitment includes rigorous measurement validation, proper documentation, equipment calibration, and strict attention to detail. Through collaboration with Lochinvar, the team must remain accountable for its deliverables while adhering to applicable engineering standards, copyrights, and intellectual property rights. Upholding these responsibilities allows the team to use the data provided by Lochinvar securely and incorporate that information into a product intended to remain internal to the company. Maintaining professional integrity throughout the design process will help ensure that the final controller is developed responsibly and that all testing results accurately represent its performance.

From a cultural perspective, the variable circulation pump controller should be designed to accommodate different types of commercial facilities and their operating requirements. Each facility may have different water demands, equipment configurations, and levels of operator experience. A user-friendly interface would allow operators to adjust the controller to meet specific facility requirements without extensive technical knowledge. The controller should also be adaptable to different operating environments while maintaining consistent performance. This flexibility could allow Lochinvar to implement the controller in future products and across a wider range of commercial applications.

Public health and safety are essential considerations throughout the design process. The circulation pump controller must maintain the required water-temperature and flow conditions during fluctuations in system demand. Failure to maintain these parameters could create unsafe operating conditions, affect water availability, or interrupt facility operations. To address these concerns, the controller should incorporate temperature monitoring, appropriate operating limits, and fault-detection capabilities. These features would allow the system to identify abnormal operating conditions and respond appropriately. The design should also account for potential sensor failures, communication issues, and unexpected changes in system demand. Incorporating these safeguards would help protect facility operators and occupants while improving the reliability of the overall system.

Relevant engineering standards will also influence the development of the controller. Organizations such as the American Society of Heating, Refrigerating and Air-Conditioning Engineers (ASHRAE), the American National Standards Institute (ANSI), the American Society of Mechanical Engineers (ASME), and UL Standards & Engagement establish or coordinate standards relevant to building energy efficiency, electrical equipment, and control systems. ASHRAE Standard 90.1 provides requirements for energy-efficient building systems, while UL 60730-1 addresses safety requirements for automatic electrical controls. Depending on the final application of the pump, additional requirements involving water circulation, equipment protection, and electrical safety may also apply. The team will need to determine which standards apply to the controller and use them to guide the selection of electrical components, operating limits, control logic, and testing procedures. Following applicable standards will help improve the overall safety, reliability, and compatibility of the final design.

These considerations will influence the design constraints, specifications, and engineering practices implemented throughout the project. The controller must be capable of responding to fluctuations in system demand while maintaining water temperature and circulation within the operating limits established with Lochinvar. These limitations will influence the selection of sensors, the controller’s response time, pump-speed adjustments, and the development of protective features. To evaluate the controller’s performance, the team will compare its energy consumption with that of the existing fixed-speed pump and analyze temperature stability under different loading conditions. Testing should also include simulated faults and abnormal operating conditions to verify that the controller responds safely and reliably. The team will use field measurements, simulation results, and repeated testing to validate the accuracy of the control system. Proper documentation, calibration, and consistent testing practices will help ensure that the final design meets the established requirements.

In conclusion, upholding public safety remains a primary responsibility throughout this project. The development of the variable circulation pump controller must maintain reliable temperature stability under fluctuating loads in commercial facilities while improving energy efficiency and overall system performance. Achieving these goals will require each team member to complete their contributions with technical diligence, professional integrity, and attention to the environmental, societal, cultural, and economic impacts of the design. Team members must also remain mindful that this controller may be used in future products developed by Lochinvar. By following applicable engineering standards, validating system performance, and maintaining ethical responsibilities, the team can work toward delivering a safe, reliable, and efficient controller that benefits both Lochinvar and the public while reducing potential operational risks and liabilities.









## Resources

You have already estimated the resources needed to complete the solution. Now, let's refine those estimates.

### Budget

Develop a budget proposal with justifications for expenses associated with each subsystem. Note that the total of this budget proposal can also serve as a specification for each subsystem. After creating the budgets for individual subsystems, merge them to create a comprehensive budget for the entire solution.

### Division of Labor

First, conduct a thorough analysis of the skills currently available within the team, and then compare these skills to the specific requirements of each subsystem. Based on this analysis, appoint a team member to take the specifications for each subsystem and generate a corresponding solution (i.e. detailed design). If there are more team members than subsystems, consider further subdividing the solutions into smaller tasks or components, thereby allowing each team member the opportunity to design a subsystem.

### Timeline

Revise the detailed timeline (Gantt chart) you created in the project proposal. Ensure that the timeline is optimized for detailed design. Address critical unknowns early and determine if a prototype needs to be constructed before the final build to validate a subsystem. Additionally, if subsystem $A$ imposes constraints on subsystem $B$, generally, subsystem $A$ should be designed first.

<img width="1262" height="665" alt="image" src="https://github.com/user-attachments/assets/40428e21-fbbf-461b-a409-2e50152ccd55" />



## References

All sources utilized in the conceptual design that are not considered common knowledge must be properly cited. Multiple references should be included.

[1] Lochinvar, “Regent™ Commercial Tankless Water Heater – 6 Gallons | Model IWH0500N,” Lochinvar. [Online]. Available: https://www.lochinvar.com/en_CA/products/tankless-condensing-regent/iwh0500n-100/100389046.html. [Accessed: Oct. 16, 2026]

[2] Lochinvar, Regent Commercial Tankless Water Heater Installation and Operation Manual, Rev. D, document no. 100399794/2000857139. [Online]. Available: Lochinvar Regent Manual (PDF). [Accessed: Oct. 16, 2026]

[3] M. Irfan, A. A. Amin, S. Waseem, S. Rahman, H. Alwadie, and S. Al Dawsari, “Design of a fault-tolerant control system for a centrifugal pump-based level control system for sensor faults,” Scientific Reports, vol. 16, art. no. 14189, Mar. 2026, doi: 10.1038/s41598-026-42361-x.

[4] U.S. Department of Energy, Hydraulic Institute, and Europump, Variable Speed Pumping: A Guide to Successful Applications—Executive Summary. U.S. Department of Energy, Energy Efficiency and Renewable Energy, Industrial Technologies Program. [Online]. Available: Variable Speed Pumping (PDF). [Accessed: Oct. 16, 2026]

[5] T. C. Hayes and P. Horowitz, The Art of Electronics Student Manual. Cambridge, U.K.: Cambridge University Press, 1989. [Online]. Available: The Art of Electronics Student Manual (PDF). [Accessed: Oct. 16, 2026]


## Statement of Contributions

Each team member is required to make a meaningful contribution to the project proposal. In this section, each team member is required to document their individual contributions to the report. One team member may not record another member's contributions on their behalf. By submitting, the team certifies that each member's statement of contributions is accurate.

Skyler Raines: TimeLine, Ethical, Professional, and Standards Considerations, Sensor and Data Acquisition Subsystem, and  Pump and Motor Control Subsystem
