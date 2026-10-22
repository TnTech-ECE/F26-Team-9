<div align="center">

# Variable-Speed Circulation Pump Controller Project Proposal

---

### Jocelyn Smith, Danielle Wolford, Kendall Arnold, Skyler Raines

Department of Electrical and Computer Engineering  
Tennessee Technological University

</div>

<br>

## General Requirements for the Document
- All submissions must be composed in markdown format.
- All sources must be cited unless the information is common knowledge for the target audience.
- The document must be written in third person.
- The document must identify all stakeholders including the instuctor, supervisor, and customer.
- The problem must be clearly defined using "shall" statements.
- Existing solutions or technologies that enable novel solutions must be identified.
- Success criteria must be explicitly stated.
- An estimate of required skills, costs, and time to implement the solution must be provided.
- The document must explain how the customer will benefit from the solution.
- Broader implications, including ethical considerations and responsibilities as engineers, must be explored.
- A list of references must be included.
- A statement detailing the contributions of each team member must be provided.


## Introduction

Hot water systems are expected to supply hot water while also responding to changing levels of demand. Tankless water heaters accomplish this by heating water as it passes through the system rather than storing a large volume of heated water. As demand changes the system must adjust to provide the required water temperature and flow. The Lochinvar Regent Commercial Tankless Water Heater is designed to meet these demands. However, operating the system at maximum all the time can result in unnecessary energy consumption. Improving how the system responds to changing water demand could provide an opportunity to reduce energy use while maintaining system performance.

The objective of this project is to investigate a method of improving the energy efficiency of the Regent water heater by controlling the circulation pump according to the system's operating conditions. The proposed approach will investigate the use of a variable speed pump and flow sensor to regulate water flow based on the heating requirements of the system. By adjusting pump speed rather than continuously operating at a maximum condition, the system may be able to provide the required hot water while reducing unnecessary electrical power consumption.

This proposal will provide background information on the Regent water heater and present measurements that will help establish a better understanding of how water heating systems operate. It will also examine existing solutions and technologies that may be applicable to the project. The proposal will explain the need for the project and identify the specifications and constraints that will guide the design process. In addition, it will provide an overview of the project resources, a detailed budget, the skills and responsibilities of each team member, the expected project timeline, and the potential impacts and implications of the proposed solution.


## Formulating the Problem

The primary customer for this project is Lochinvar, specifically the engineering team is responsible for the design, testing, and in control of their commerical water heating systems. The main product that could benefit from the results of this project is the Regent Commercial Instantaneous Water Heater. Even though the Regent is the intended application, the equipment currently available for testing at the Tennessee Tech lab consists of Lochinvar Knight KHB085 and WHB199 fire tube boilers. Lochinvar also pointed out that a recirculation loop, pump, flow sensor, and temperature sensors can
be provided if testing on Lochinvar hardware is needed. 
The problem also affects the people and facilities that use commerical domestic hot water systems. The systems need to supply hot water accurately despite if demand changes. From an engineering stand-point, Lochinvar is interested in determining whether the circulation pump can work at a lower speed when circulation isn't needed. Rather than treating the pump as a component that always needs to work at a constant, unneeded high speed, the project looks into if the pump can be more equivalent to the 
demands of the water heating system. The project proposal from Lochinvar specifically wants our team to run the internal circulation pump at different speeds while changing the flow rate/inlet water temperature and then measuring how the changes affect the performance of the system. 
Therefore, our Lochinvar needs engineering data and a control strategy that can demonstrate how and when the circulation pump speed can be reduced without sacrificing the predicted performance of the water heater. The results from our project could help Lochinvar decide if variable speed circulation control will benefit them for the Regent system and how that control could be implemented. 

This solution is needed because the amount of hot water being used in a commercial water heating system is not always the same. The demand can change throughout the day, which means that the pump may not need to run at the same speed under every state or situation. If the system doesn't need as much flow at a specific time, running the pump at a higher speed could just be wasting power.
At the same time, we can't just lower the pump speed and assume everything will still work efficiently. There still needs to be enough flow through the heat exchanger, and the system still needs to reach and maintain the needed water temperature. One of the main main goals of the project is to find a way to lower the speed of the pump when possible without hurting the overall execution of the system.
A variable speed pump controller would allow the pump to adjust based on what is happening in the system. When the demand is lower, the pump could run at lower speeds and potentially use less power. When the demand goes high, the controller could increase the speed of the pump to make sure there is enough water running through the system. The main objective is to find the most efficient pump speed while still meeting all of the requirements of the water heating system. 

This project needs a team because there are many different parts that have to work together for the system to operate efficiently and correctly. The project involves things like water flow, temperature, sensors, physical hardware, microcontroller programming, pump control, and testing. Changing one part of the system could also affect another part.
Another challenge is figuring out how the controller should decide what speed the pump needs to run at. The controller will need to look at the flow rate, modulation, and temperature and then use that information to adjust the the speed of the pump. We will also need to make sure the pump stays within the correct working range and doesn't constantly change speeds due to small changes in sensor readings.
There are also challenges with getting all of the hardware to work together. The sensors, microcontroller, pump, and current Lochinvar system will all need to communicate efficiently. We will have to make sure that the signals and sensors we use are compatible with the system under different working conditions to see how well the controller reacts. Having multiple people working on the project allows us to divide up the programming, hardware, testing, research, and documenation while still working toward the same overall goal. 
  
There are already variable speed pumps and controllers obtainable, but they may not completely solve the problem that Lochinvar is trying to solve. A normal pump controller might adjust the the pump depending on one measurement, such as temperature, pressure, or flow. For this project, we want the controller to deliberate multiple things happening in the system before deciding what speed the pump should run at.
Our controller could use the flow rate, modulation, and water temperature to determine the speed of the pump. It also has to make sure that the system still has enough flow, maintains the correct temperature, and stays within the limits of the pump and the rest of the system. These needs are more precise to Lochinvar's application.
Because of this, the main part of our project is not just finding a variable speed pump that already exists. The engineering part is developing the control approach that decides when the pump needs to speed up or slow down based on the current state of the system. We will then have to test the controller to make sure that reducing the pump's energy usage doesn't negatively affect the execution of the water heating system. 

### Background

Hot water systems provide heated water for applications such as showers, baths, laundry, kitchen sinks, and other units. These systems must be capable of responding to frequent changes in hot water demands while maintaining the required water temperature and flow.
Some systems use Instantaneous water heating which is the process of using a tankless water heater that will heat up the water only when you need it. The process starts with cold water entering the unit to be heated by a heating element then delivered at the desired temperature of the customer.
The Regent Commercial Tankless Water Heater is the target system being investigated in this project. The Regent is designed as a tankless water heater that heats water as it passes through the system rather than storing hot water in a tank. Cold water, referred to as the inlet water, enters the system and flows through the heat exchanger. This is where thermal energy is transferred from the heating system to the water. The heated water, referred to as the outlet water, then exits the unit at the required temperature. If additional heating is needed, water can be recirculated through the heat exchanger to increase its temperature before being delivered to the system.
The purpose of a heat exchanger is to be able to transfer thermal energy to the water, creating the desired supply of hot water without the two ever coming in direct contact. To understand heat exchangers better and how to reach desired temperatures, it's good to understand the relationship when a system at a higher temperature is in contact with a system at a lower temperature. The rate of heat transferred to the water can be described by:

$$
Q_h = c \ m_V \ \Delta T 
$$

where Q_h represents the rate of heat transferred to the water, m_V represents the mass flow rate, c is the specific heat capacity of water(constant), and ∆T is the temperature change (Tout-Tin). Tout and Tin represent the outlet and inlet water temperatures. This relationship demonstrates the connection between water flow and temperature change within the system. As the circulation flow rate changes, the amount of temperature increase required to transfer a given amount of thermal energy also changes. This relationship will be used as a foundation for modeling the thermal response of the system.

Flow rate describes the amount of water moving through the system over a given period also expressed as volumetric flow rate,

$$
Q_V = \frac{V}{t}
$$

Where Q_V is the volumetric flow rate, V is the volume of water, and t is the time.

Flow rate can also be expressed as mass flow rate, which describes the mass of water moving through the system over a given period:

$$
m_V = \frac{m}{t}
$$

Where m_V is the mass flow rate, m is the mass, and t is the time.

The relationship between volumetric and mass flow rate is: 

$$
m_V = \rho Q_V
$$

Where ρ is the density of water.These relationships allow changes in the volumetric flow rate of water to be related to the mass flow rate used in the heat transfer equation.
The demand for hot water is never stagnant, it is constantly changing. An increase in demand results in an increase in flow and requires the system to respond while maintaining the desired temperature. A flow sensor can detect changes in demand, allowing a variable speed pump to adjust its operation accordingly. This provides the foundation for matching pump operation to system demand rather than continuously operating at maximum capacity.

Electrical power is the rate at which electrical energy is used by a system. Power can be expressed as: 

$$
P = VI
$$

where P is electrical power, V is voltage, and I is current. 

The total electrical energy consumed depends on both power and operating time:

$$
E = Pt
$$

A circulation pump operating at a higher speed generally requires more electrical power. If the pump operates at maximum capacity when the system does not require maximum flow, unnecessary energy can be consumed. A variable speed pump can adjust its operation based on the required flow rate, potentially reducing power consumption during periods of lower demand. For the proposed system, monitoring and controlling pump operation can therefore help maintain the required hot water performance while reducing unnecessary electrical energy consumption.
Energy efficiency involves meeting the required system performance while using as little energy as possible. In a hot water system, the circulation pump does not necessarily need to operate at maximum speed under all operating conditions. Reducing pump speed when demand is lower can reduce unnecessary electrical power consumption.
However, reducing pump speed too much can also affect system performance by decreasing flow and potentially increasing the time required to reach or maintain the desired temperature. Therefore, the goal is to not just minimize pump speed, but to find a balance between energy consumption and system performance.
A variable speed pump provides a way to adjust flow according to system demand. By supplying only the flow needed for the current operating condition, the system can potentially reduce unnecessary energy use while still meeting the required temperature and response time requirements. This balance between efficiency and performance is a key consideration in the proposed system.

### Specifications and Constraints

#### Specifications

The main goal of this project is to develop a control strategy that adjusts the circulation pump speed based on the running conditions of the water heating system. The controller is intended to reduce unnecessary electrical power consumption while sustaining the required water flow, temperature stability, and overall system execution. The following specifications will be used to guide the design and evaluate the controller during testing.

* 1 – Temperature Stability: The system shall maintain the outlet water temperature within ±4 °F of the desired temperature setpoint during defined steady state operating conditions. This will be verified by recording the outlet temperature and comparing it with the desired value.

* 2 – Minimum Flow Rate: The controller shall maintain a circulation flow rate equal to or greater than the minimum required by Lochinvar, measured in gallons per minute (GPM). The minimum allowable flow rate will be determined from the manufacturer's requirements for the equipment being tested. This will be verified using the flow sensor.

* 3 – Pump Speed Control: The controller shall adjust the circulation pump speed when changes are made in system running conditions. The allowable pump speed range will be decided from the selected pump's specifications. This will be confirmed by recording the pump control signal and measured pump response during testing.

* 4 – Firing Rate Monitoring: The controller shall accept a 0–10 V firing rate signal from the compatible Lochinvar boiler, representing a firing rate of 0–100%. This will be verified by applying known input voltages and confirming that the controller read them correctly.

* 5 – Flow Rate Monitoring: The controller shall convert the pulse frequency output from the KEYENCE flow sensor into a water flow measurement in GPM. This will be confirmed by comparing the calculated flow rate with the sensor's measured output over its relevant running range.

* 6 – Temperature Response Time: The system shall reach and maintain the desired outlet temperature within a reasonable response time after a change in water demand. The maximum acceptable response time, measured in seconds, will be established using Lochinvar's requirements or approved standard measurements. This will be verified through timed testing at different flow rates.

* 7 – Electrical Power Reduction: The controller shall demonstrate a reduction in circulation pump electrical power consumption compared with baseline operation under equivalent operating conditions. The target reduction will be established before final testing. Electrical power will be measured in watts, and the percentage reduction will be calculated from the recorded measurements.

* 8 – Controller Stability: The controller shall maintain stable operation without excessive pump-speed oscillations during changes in water demand. Acceptable limits for speed fluctuations and settling time will be established before testing. Stability will be verified by recording pump speed, flow rate, and outlet temperature during controlled demand changes.

* 9 – Existing System Compatibility: The controller shall operate without bypassing or interfering with the existing Lochinvar temperature regulation and safety controls. This will be verified by reviewing the electrical and control interfaces and conducting approved functional tests.

* 10 – Operating Condition Testing: The team shall evaluate the controller at a minimum of three defined running conditions representing low, medium, and high water demand, dependant on the available test equipment. During each test, the team will record pump running conditions, water flow rate, inlet and outlet temperatures, firing rate, and electrical power consumption.

These specifications will be used to determine whether the proposed controller can improve pump efficiency while maintaining the running requirements of the water heating system. Any numerical limits not yet provided by Lochinvar will be established and documented before final performance testing.

#### Constraints
  
The proposed variable speed circulation pump controller must run within the electrical, mechanical, thermal, and safety limitations of the existing Lochinvar equipment. Because the project involves commercial water heating equipment, electrical components, and circulating hot water, the design must consider relevant engineering standards and manufacturer requirements. The following constraints will guide the development and testing of the controller.

Electrical and Safety Constraints

* 1 – Electrical Installation: Electrical wiring, grounding, and protection associated with the controller shall follow applicable requirements of NFPA 70, the National Electrical Code (NEC), where those requirements apply to the installation. The team will review the relevant NEC provisions before connecting the controller to the pump or boiler equipment [14].

* 2 – Electrical Compatibility: The controller shall operate within the voltage and current ratings of the selected microcontroller, sensors, and pump control interfaces. The existing boiler's 0–10 V firing rate signal must be connected through an appropriate signal-conditioning or input circuit compatible with the controller.

* 3 – Hazardous Energy Control: When servicing or modifying equipment, the team shall follow applicable laboratory safety procedures and hazardous energy control requirements. OSHA 29 CFR 1910.147 provides requirements for controlling hazardous energy during servicing and maintenance in covered workplaces. Its applicability to the specific testing environment must be confirmed [6].

* 4 – Existing Safety Controls: The proposed controller shall not bypass or disable the boiler's existing temperature limits, flow protections, or other manufacturer installed safety functions. Any proposed connection to the existing system must be reviewed before testing.

Plumbing and Mechanical Constraints

* 5 – Plumbing Requirements: Any modifications to the water circulation system shall be evaluated against the applicable locally adopted plumbing code, including requirements for piping materials, fittings, pressure protection, and safe hot water operation. The International Plumbing Code provides a reference for identifying relevant plumbing requirements, subject to local adoption and applicability [15].

* 6 – Pipe and Fitting Compatibility: Pipes, fittings, valves, and flow measurement equipment shall be compatible with the running temperature, pressure, and flow conditions of the test system. Component ratings will be verified using manufacturer documentation before installation.

* 7 – Minimum Circulation Flow: The pump shall not operate below the minimum circulation flow required by the equipment manufacturer during conditions requiring circulation. This constraint is necessary to avoid operating the heat exchanger outside its approved flow limits.

* 8 – Pump Operating Limits: The controller shall not command pump procedure outside the allowable speed, flow, pressure, or electrical limits established by the selected pump manufacturer.

System and Project Constraints

* 9 – Equipment Compatibility: The design must remain compatible with the available Lochinvar test equipment, including the Knight boilers and any pump, flow sensor, temperature sensors, or circulation loop components supplied for testing. Because the Regent is the intended application, differences between the test equipment and Regent system must be identified before applying the results to the Regent.

* 10 – Temperature Performance: Changes to pump speed shall not cause the system to violate the ±4 °F outlet temperature tolerance under the defined steady state test conditions.

* 11 – Budget and Resources: The design shall remain within the project budget approved by the team and its stakeholders. The current proposal estimates approximately $1,179 for the primary components, although additional materials, signal conditioning hardware, and testing equipment may affect the final cost.

* 12 – Project Timeline: The team must complete the research, requirements, and proposed design during Capstone 1, with implementation and testing planned for Capstone 2, according to the approved course schedule.

Environmental and Economic Considerations

Environmental and economic factors are also important considerations for this project. Reducing circulation pump speed when full prodecure is unneeded may reduce electrical energy consumption and operating costs. However, the controller must maintain the required water heating execution, and the potential savings must be evaluated against the additional cost of the control hardware and system integration.

The team will compare measured electrical power consumption during origianl and controlled procedure to estimate potential energy savings. The cost of implementing the proposed controller will also be considered when determining whether the system provides a practical improvement for Lochinvar. Research on variable speed pumping shows that matching pump output to system requirements can reduce unnecessary energy consumption, although the actual savings depend on the application and running conditions [5], [10].

Before the controller is considered for implementation in a commercial Lochinvar product, the team and Lochinvar would need to confirm the applicable product certification, electrical, plumbing, and safety requirements. The final design must not compromise equipment reliability in order to achieve energy savings.

## Survey of Existing Solutions

There is a wide variety of available circulation pumps in the current market. These include 3 main types: multi-speed circulator pumps, electronically commutated motor pumps, and automatic recirculation pumps.
Multi speed circulator pumps are manual variable speed pumps but can have 3+ speeds instead of just 2. They can be budget friendly but work best for small to medium sized water systems. 
Electronically commutated motor pumps can be automatic or have manually selectable speeds. They are energy efficient and reduce mechanical stress but work better for residential water systems.
Automatic recirculation pumps are the best fit for this project. They are sensor driven and programmable, reduce energy that is wasted, and can be used for tankless water heaters. To be more specific though, there are 4 types of automatic recirculation pumps: Constant temperature, demand controlled, temperature modulation, and hybrids. 
Constant temperature pumps adjust their speed to maintain a set temperature. Demand-controlled pumps use flow and temperature sensors to start or stop the pump. Temperature modulation pumps adjust temperature based on demand. Finally, Hybrid pumps typically combine constant temperature pumps and demand controlled pumps. 
For this project, demand controlled pumps fit the best. For the system to start, a user will trigger the system, or the controller senses a drop in temperature. The system will then adjust to the trigger and return to resting state when the temperature sensor has confirmed the hot water has reached the designated point in the loop. The “resting state” helps to save energy as well as extending the equipment’s lifespan.

## Measures of Success

Our goal is to form a fully functional variable circulation pump, but there are some checkpoints along the way to determine and measure our success. There are also some measurements based on the specifications of this project. 
The first is performance metrics. The accuracy and stability of the flow and flow sensor, as well as response time. 
The next measurement for success is energy efficiency. Essentially, asking if the energy savings are enough to justify the higher cost. 
After that, the next consideration is reliability. Is the mechanical stress reduced and by how much? What is the average time between failures? 
Our next measurements are economic and environmental measures. What is the return on investment? What about the life cycle cost versus the operating cost reduction? For environmental, does this new pump maintain water quality and system integrity?
We also need to measure the flow rates versus the demand and decide if this pump is in fact more efficient. Additionally, we need to maintain the temperature during the different flow speeds. 
If we can meet or exceed these measurements for our final product, then we will have succeeded in creating a functional and efficient variable circulation pump.


## Resources


### Budget

<img width="773" height="197" alt="image" src="https://github.com/user-attachments/assets/60f14c90-7f94-4488-af62-af302226a655" />


The estimated budget for the project is approximately $1,179. The primary expenses include the variable-speed pump, flow measurement, temperature measurement, and control components required to develop and test the proposed system. The KEYENCE FD-Q50C clamp-on flow sensor, estimated at $580, will measure water flow without requiring significant modifications to the existing plumbing. A variable-speed pump, estimated at $500, will allow the team to investigate how adjusting pump speed affects flow rate, water temperature, and overall system performance. A microcontroller, estimated at $20, will be used to facilitate communication between the sensors and control system during testing.

Temperature measurements will be obtained using two Cooper-Atkins 4005MK Type-K pipe clamp sensors, estimated at $79 each, to measure water temperatures at the inlet and outlet of the system. These measurements will allow the team to calculate the temperature change across the water heater and evaluate its thermal performance. The total estimated cost of these primary components is $1,179. However, the final project cost may vary depending on the development of the project, any additional equipment or materials required, and the potential availability of components or resources provided by Lochinvar.

### Personel

* Jocelyn Smith: C/C++, Assembly, Python, TypeScript, SQL, MATLAB, VHDL, Circuit Analysis, Control System Analysis, LT Spice
* Danielle Wolford: C/C++, Assembly, Circuit Analysis, PLC Coding, HMI Formatting, Control System Analysis, LT Spice, KiCad
* Kendall Arnold: C/C++, Assembly, AUTOCAD, Controls Systems, Circuit Analysis, LT Spice, KiCad, Technical Documentation
* Skyler Raines: C/C++, Assembly, Circuit Analysis, AUTOCAD, Revit, PLC, Ladder Logic, Control Systems, Troubleshooting

The capstone team consists of four members: Jocelyn Smith, Danielle Wolford, Kendall Arnold, and Skyler Raines. Each member of the team has experience with different programming languages, engineering software, and electrical engineering concepts that will be useful throughout the project. Developing a variable speed pump controller will need knowledge of programming, circuit analysis, control systems, hardware integration, and testing. The team has experience in some of these areas, which will let the work be divided depending on each member's strengths. However, there are also areas where further research and learning will be needed before the project can be completed.
Although the team has experience in programming, circuit analysis, and control systems, there are still some areas that will require further knowledge. One of the biggest challenges will be to understand how the circulation pump affects the water flow and temperature inside the heat exchanger. The team will also need to learn more about the specific pump, sensors, and boiler signals given by Lochinvar. This contains understanding how the 0–10 V firing rate signal and flow sensor assessments can be used when developing the controller. Another area that may need further research is deciding how to alter the pump speed without causing the system to be unstable or negatively affecting the time required to reach the wanted temperature.
To achieve the knowledge needed for these areas, the team plans to research the equipment being used, go over technical documentation provided by Lochinvar, and communicate with Lochinvar's engineers when questions come up. The team may also need to become more familiar with simulation software such as Dymola if modeling is included in the project. Testing and evaluating results will also help the team better understand how the system responds when different running conditions occur. By combining the skills the members already have with further research and guidance, the team should be able to work through the challenges that come up during the project.
The team has chosen Dr. Storm as the project supervisor. The supervisor will help guide the team through the engineering and technical parts of the project. This will include giving feedback on the proposed control approach, helping the team understand the equipment being used, and answering questions that may come up during development and testing. Having a supervisor with knowledge of the project will be important because the team is working with commercial water heating equipment and needs to make sure the proposed controller meets the requirements supplied by Lochinvar.
The instructor for this capstone project is Dr. Storm. The instructor will be able to give the team guidance throughout the project and to make sure the team is meeting the expectations and requirements of the capstone. This contains reviewing project documentation, providing feedback on assignments and presentations, and helping the team stay on track with the project timeline. The instructor will also help evaluate the team's progress and make sure the work being completed meets the academic and engineering expectations of capstone.

### Timeline


<img width="1487" height="597" alt="image" src="https://github.com/user-attachments/assets/f5531d7d-e73e-413f-943a-abcbc1e83626" />



## Specific Implications

Solving this problem could give various benefits to Lochinvar, especially when it comes to improving the efficiency of their commercial water heating systems. The main goal of our project is to develop a controller that adjusts the circulation pump speed depending the current running conditions of the system. Rather than having the pump run at a higher speed than what is actually needed, the controller would allow the pump to slow down when the system doesn't need as much circulation. This could help reduce that number of electrical power being used by the pump while still allowing the water heating system to run correctly and efficiently. If our team is able to create a successful control strategy, Lochinvar could potentially use the results to improve the efficiency of their current water heating systems. 
Another benefit of solving this problem is being able to improve energy efficiency without negatively affecting the execution of the system. One of the biggest hurdles is making sure that lowering the speed of the pump doesn't cause problems with water flow or temperature control. The system will sill need to maintain the minimum needed flow rate, reach the wanted temperature set point within a reasonable amount of time, and maintain a stable temperature within +-4 degrees F. By developing a controller that deliberates the flow rate, boiler firing rate, and temperature, our team is in hopes of finding a way to reduce unneeded pump procedure while still meeting these requirements. This would be a benefit to Lochinvar because it could improve the way their systems run without surrendering the performance their customers expect.
There are also potential economic and environmental benefits that could result from this project. If the circulation pump is able to run at lower speeds when feasible, it could reduce the amount of electricity needed to run the system. Although the actual energy savings would need to be decided through testing, the likelihood of reducing the running costs while keeping the same level of performance make the project worth researching. 
Overall, solving this problem could give Lochinvar a better understanding of how different circulation pump speeds affect power consumption, water flow, and temperature execution. The data accumulated from testing could help decide if a variable speed pump controller would be a functional improvement for their Regent Commercial Instantaneous Water Heater. The main value or gain if this project is finding a ay to make the system more energy efficient while also keeping the reliability that Lochinvar and the customers need. 



## Broader Implications, Ethics, and Responsibility as Engineers

The development of this variable pump project has implications from environmental, societal, ethical, and scientifical domains. From the environmental perspective, the controller should be designed to maximize both water conservation and energy efficiency compared to the current fixed circulation pump. Building a controller that allows optimizing energy performances could reduce the facility's overall carbon footprint. 

From a societal standpoint, the variable circulation pump controller must feature an intuitive user interface to help control the pump for different facilities. The system is required continuously to meet fluctuating peak demands while maintaining strict parameters for temperature stability. If the pump parameters fail to satisfy these demands, it may result in financial losses as well as public health and safety risks.  

Ethical responsibilities are integrated into the design and implication of the project. As engineers, we are committed to ensuring the accuracy and integrity of our methodology and data. This commitment would include rigorous validation of measurements, documentation, equipment calibration, and strict attention to detail. With the collaboration with Lochinvar, the team would require strict accountability for our deliverables while adhering to all the established standards, copyrights, and property rights. Upholding these standards allows the team to securely utilize data that Lochinvar has provided and implement that data into a product that will remain internal to the company. 

For scientifical aspects, the variable circulation pump needs to ensure that there is an accurate stability control loop. The accuracy could be supported from field data that is given from testing locations of Lochinvar. The data that is given from Lochinvar will provide precise physical measurements to map and configure the controller’s logic. Without these accurate data bases, any cross-referencing and validation from any simulation prediction could become unfeasible. Standardizing this data could improve simulations which would allow any anomalies to be cut out. 

In conclusion, as engineers, upholding public safety remains our primary directive and core professional responsibilities throughout this project. The development of this variable circulation controller will need to maintain absolute precision in the thermal stability under high fluctuating loads in a commercial business. Achieving these standards will require each member of the team to execute their contributions with technical diligence and professional integrity.  Members of the team must be mindful that this design may be used in future implementations that Lochinvar develops. We must remain aware of our ethical obligations to the public and deliver a safe, high-performing product that will have a positive public impact and will eliminate corporate liabilities for Lochinvar.

## References

\(1\) “How Do Instant Water Heaters Work? A Look Inside the Technology and Installation Process,” Motivated Mechanical Solutions. \(Online\). Available: [https://motivatedmechanicalsolutions.com/how-do-instant-water-heaters-work-a-look-inside-the-technology-and-installation-process/](https://motivatedmechanicalsolutions.com/how-do-instant-water-heaters-work-a-look-inside-the-technology-and-installation-process/). \(Accessed: Sept. 29, 2026\).

\(2\) “Regent™ Commercial Tankless Water Heater – 6 Gallons | Model IWH0500L,” Lochinvar. \(Online\). Available: [https://www.lochinvar.com/en_US/products/IWH0500L-SG101.html](https://www.lochinvar.com/en_US/products/IWH0500L-SG101.html). \(Accessed: Sept. 29, 2026\).

\(3\) “How Do Heat Exchangers Work?,” Explain That Stuff. \(Online\). Available: [https://www.explainthatstuff.com/how-heat-exchangers-work.html](https://www.explainthatstuff.com/how-heat-exchangers-work.html). \(Accessed: Sept. 30, 2026\).

\(4\) “Heat Exchangers Formulas Explained with Calculation Examples,” Heat Exchanger. \(Online\). Available: [https://www.heatexchanger.co.in/Heat-Exchanger-Blog-Details/heat-exchanger-formula/](https://www.heatexchanger.co.in/Heat-Exchanger-Blog-Details/heat-exchanger-formula/). \(Accessed: Oct. 1, 2026\).

\(5\) V. Tutterow and A. T. McKane, “Variable Speed Pumping: A Guide to Successful Applications,” Lawrence Berkeley National Laboratory, 2004. \(Online\). Available: [https://escholarship.org/uc/item/4691d71q] \(Accessed: Oct. 9, 2026\).

\(6\) Occupational Safety and Health Administration, “1910.147—The Control of Hazardous Energy (Lockout/Tagout).” \(Online\). Available: [https://www.osha.gov/laws-regs/regulations/standardnumber/1910/1910.147]. \(Accessed: Oct. 9, 2026\).

\(7\) Hydraulic Institute, “Application Guideline for Variable Speed Pumping,” 2017. \(Online\). Available: [https://store.accuristech.com/standards/application-guideline-for-variable-speed-pumping-a148e?product_id=1946769]. \(Accessed: Oct. 9, 2026\).

\(8\) ASHRAE, “Design and Application of Controls,” 2023 ASHRAE Handbook—HVAC Applications, ch. 48, 2023. \(Online\). Available: [https://handbook.ashrae.org/Handbooks/A23/IP/A23_Ch48/A23_Ch48_ip.aspx]. \(Accessed: Oct. 9, 2026\).

\(9\) OpenAI, “ChatGPT,” [Online]. Available: https://chatgpt.com/. [Accessed: Oct. 9, 2026].

## Statement of Contributions

Each team member must contribute meaningfully to the project proposal. In this section, each team member is required to document their individual contributions to the report. One team member may not record another member's contributions on their behalf. By submitting, the team certifies that each member's statement of contributions is accurate.

* Kendall Arnold - Introduction, Background, Budget
* Skyler Raines- Timeline, Broader Implications, Ethics and Responsibility as Engineers
* Jocelyn Smith - Formulating the Problem, Specifications and Constraints, Personel, Specific Implications
* Danielle Wolford - Survey of Existing Solutions, Measures of Success

