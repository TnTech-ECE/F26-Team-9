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


### Hardware Block Diagram

Block diagrams are an excellent way to provide an overarching understanding of a system and the relationships among its individual components. Generally, block diagrams draw from visual modeling languages like the Universal Modeling Language (UML). Each block represents a subsystem, and each connection indicates a relationship between the connected blocks. Typically, the relationship in a system diagram denotes an input-output interaction.

In the block diagram, each subsystem should be depicted by a single block. For each block, there should be a brief explanation of its functional expectations and associated constraints. Similarly, each connection should have a concise description of the relationship it represents, including the nature of the connection (such as power, analog signal, serial communication, or wireless communication) and any relevant constraints.

The end result should present a comprehensive view of a well-defined system, delegating all atomic responsibilities necessary to accomplish the project scope to their respective subsystems.


### Operational Flow Chart

Similar to a block diagram, the flow chart aims to specify the system, but from the user's point of view rather than illustrating the arrangement of each subsystem. It outlines the steps a user needs to perform to use the device and the screens/interfaces they will encounter. A diagram should be drawn to represent this process. Each step should be represented in the diagram to visually depict the sequence of actions and corresponding screens/interfaces the user will encounter while using the device.


## Atomic Subsystem Specifications

### 1) Sensor and Data Acquisition Subsystem

Overview
  

	
    
    
    

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

