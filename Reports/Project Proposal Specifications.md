# Project Proposal

This document provides a comprehensive explanation of what a project proposal should encompass. The content here is detailed and is intended to highlight the guiding principles rather than merely listing expectations. The sections that follow contain all the necessary information to understand the requirements for creating a project proposal.


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

The introduction must be the opening section of the proposal. It acts as the "elevator pitch" of the project, briefly introducing the objective, its importance, and the proposed solution. Because readers may only read this section, it should effectively capture their attention and encourage them to read further.

Toward the end of the introduction, include a subsection that outlines what the proposal will cover. This helps set reader expectations for the ensuing sections.


## Formulating the Problem

Formulating the problem or objective involves clearly defining it through background information, specifications, and constraints. Think of it as "fencing in" the objective to make it unambiguously clear what is and is not being addressed and why.

Questions to consider:
- Who does the problem affect (i.e. who is your customer)?

    The primary customer for this project is Lochinvar, specifically the engineering team is responsible for the design, testing, and in control of their commerical water heating systems. The main product that could benefit from the results of this project is the Regent Commercial Instantaneous Water Heater. Even though the Regent is the intended application, the equipment currently available for testing at the Tennessee Tech lab consists of Lochinvar Knight KHB085 and WHB199 fire tube boilers. Lochinvar also pointed out that a recirculation loop, pump, flow sensor, and temperature sensors can
be provided if testing on Lochinvar hardware is needed. 
    The problem also affects the people and facilities that use commerical domestic hot water systems. The systems need to supply hot water accurately despite if demand changes. From an engineering stand-point, Lochinvar is interested in determining whether the circulation pump can work at a lower speed when circulation isn't needed. Rather than treating the pump as a component that always needs to work at a constant, unneeded high speed, the project looks into if the pump can be more equivalent to the 
demands of the water heating system. The project proposal from Lochinvar specifically wants our team to run the internal circulation pump at different speeds while changing the flow rate/inlet water temperature and then measuring how the changes affect the performance of the system. 
    Therefore, our Lochinvar needs engineering data and a control strategy that can demonstrate how and when the circulation pump speed can be reduced without sacrificing the predicted performance of the water heater. The results from our project could help Lochinvar decide if variable speed circulation control will benefit them for the Regent system and how that control could be implemented. 

- Why do we need this solution?

    This solution is needed because the amount of hot water being used in a commercial water heating system is not always the same. The demand can change throughout the day, which means that the pump may not need to run at the same speed under every state or situation. If the system doesn't need as much flow at a specific time, running the pump at a higher speed could just be wasting power.
    At the same time, we can't just lower the pump speed and assume everything will still work efficiently. There still needs to be enough flow through the heat exchanger, and the system still needs to reach and maintain the needed water temperature. One of the main main goals of the project is to find a way to lower the speed of the pump when possible without hurting the overall execution of the system.
    A variable speed pump controller would allow the pump to adjust based on what is happening in the system. When the demand is lower, the pump could run at lower speeds and potentially use less power. When the demand goes high, the controller could increase the speed of the pump to make sure there is enough water running through the system. The main objective is to find the most efficient pump speed while still meeting all of the requirements of the water heating system. 
  
- What challenges necessitate a dedicated, multi-person engineering team?
  
    This project needs a team because there are many different parts that have to work together for the system to operate efficiently and correctly. The project involves things like water flow, temperature, sensors, physical hardware, microcontroller programming, pump control, and testing. Changing one part of the system could also affect another part.
    Another challenge is figuring out how the controller should decide what speed the pump needs to run at. The controller will need to look at the flow rate, modulation, and temperature and then use that information to adjust the the speed of the pump. We will also need to make sure the pump stays within the correct working range and doesn't constantly change speeds due to small changes in sensor readings.
    There are also challenges with getting all of the hardware to work together. The sensors, microcontroller, pump, and current Lochinvar system will all need to communicate efficiently. We will have to make sure that the signals and sensors we use are compatible with the system under different working conditions to see how well the controller reacts. Having multiple people working on the project allows us to divide up the programming, hardware, testing, research, and documenation while still working toward the same overall goal. 
  
- Why aren’t off-the-shelf solutions sufficient?
  
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

Specifications and constraints define the system's requirements. They can be positive (do this) or negative (don't do that). They can be mandatory (shall or must) or optional (may). They can cover performance, accuracy, interfaces, or limitations. Regardless of their origin, they must be unambiguous and impose measurable requirements.

#### Specifications

Specifications are requirements imposed by **stakeholders** to meet their needs. If a specification seems unattainable, it is necessary to discuss and negotiate with the stakeholders.

  The main goal of this project is to control the speed of the circulation pump in a way that improves the efficiency of the water heating system without negatively affecting how the system controls the temperature already. The pump needs to be able to run at different speeds depending on the present demand of the system. This demand can changed based on the water flow or the inlet water temperature. 
  Another important specification is that the controller needs to be able to maintain the minimum amount of flow needed for the system to run correctly. The goal is to lower the speed of the pump when possible to reduce power consumption, but not that it causes problems with the system. Changing the speed of the pump shouldn't increase the amount of time it takes the water to reach its temperature set point significantly. The system also needs to stay stable and maintain the temperature within +-4 degrees F.
  The controller will also need to use the information already given from the existing system to determine how the pump should operate. The Knight boiler has a firing rate output from 0-10 V, which signifies a firing rate of 0-100%. The Regent system also uses a Keyence flow sensor to measure the amount of water that is flowing through the system. The flow sensor uses a pulse output frequency that gets converted into a flow measurement in GPM. These signals can provide information to the controller about that the system is doing in real time and help decide what speed the pump needs to run at. 
  The system will also need to be tested under different operating conditions. We will need to change the circulation rate and water demand to identify how different pump speeds affect power consumption and the amount of time it takes the system to reach the temperature set point. Lochinvar currently uses a flow tree to create constant changes in flow rate, which can help us to simulate the different levels of hot water demand that the system could encounter while it is running. 


#### Constraints

Constraints often stem from governing bodies, standards organizations, and broader considerations beyond the requirements set by stakeholders.

Questions to consider:
- Do governing bodies regulate the solution in any way?
  
    At this point, the information that Lochinvar provided doesn't list a specific governing body or regulation that our project is required to follow. However, because the project includes a commercial water heating system, electrical components, hot water, and a circulation pump, safety still needs to be considered when designing and testing the controller. The controller shouldn't intrude on any of the existing safety features of the boiler. Before the final design is in the process of being implemented into an actual Lochinvar product, any mandatory regulations would need to be identified and followed.

- Are there industrial standards that need to be considered and followed?

    The project details provided by Lochinvar doesn't give our team any specific industry standards that we are required to follow.. Because of this, we shouldn't assume or list a certain standard unless Lochinvar tells us that it applies to the project. For our work at this point in time, the main requirement is making sure that the controller works with the existing Lochinvar equipment and doesn't negatively affect the current temperature control. The controller also needs to keep the minimum required flow rate and keep the system temperature steady within +-4 degrees F.
  
- What impact will the engineering, manufacturing, or final product have on public health, safety, and welfare?

    Safety is important for this project because the system deals with hot water, boiler equipment, electrical components, and a circulation pump. If the pump is running at too low of a speed, there is a possibility that there isn't enough water flowing through the system for it to run correctly and efficiently. Because of this, our controller needs to keep the minimum needed flow rate while adjusting the speed of the pump. It also can't negatively affect how quickly the system attains its temperature set point. or causes the water temperature to be unstable. 
    The final design should also work with the current temperature and safety controls rather than replacing or meddling with them. Because of the main purpose of the controller is to improve the efficiency, any energy savings would not be worth it if they caused the water to run incorrectly or unsafely. 

- Are there global, cultural, social, environmental, or economic factors that must be considered?

The biggest influence for our project are environmental and economic. The main goal of the project is to improve the efficiency of the system overall by controlling the circulation pump speed. If the pump is able to run at a lower speed when the full pump is not needed, the system could possibly use less electrical power. This could reduce the amount of energy used while it's running, which would have both an environmental and economical advantage.
    There is also an economic deliberations when it comes to implementing the controller. Any improvement in efficiency would need to be worth the extra hardware, sensors, programming, and controls needed to make the system work. Our team would need to consider if the amount of energy saved by modifying the pump speed is enough to validate adding the control system. 
    

## Survey of Existing Solutions

There is a wide variety of available circulation pumps in the current market. These include 3 main types: multi-speed circulator pumps, electronically commutated motor pumps, and automatic recirculation pumps.

Multi-speed circulator pumps are manual variable speed pumps but can have 3+ speeds instead of just 2. They can be budget friendly but work best for small to medium sized water systems. 
Electronically commutated motor pumps can be automatic or have manually selectable speeds. They are energy efficient and reduce mechanical stress but work better for residential water systems.

Automatic recirculation pumps are the best fit for this project. They are sensor-driven and programmable, reduce energy wastage, and can be used for tankless water heaters. To be more specific though, there are 4 types of automatic recirculation pumps: Constant temperature, demand-controlled, temperature modulation, and hybrids. 

Constant temperature pumps adjust their speed to maintain a set temperature. Demand-controlled pumps use flow and temperature sensors to start or stop the pump. Temperature modulation pumps adjust temperature based on demand. Finally, Hybrid pumps typically combine constant temperature pumps and demand-controlled pumps. 

For this project, demand-controlled pumps fit the best. For the system to start, a user will trigger the system, or the controller senses a drop in temperature. The system will then adjust to the trigger and return to resting state when the temperature sensor has confirmed the hot water has reached the designated point in the loop. The “resting state” helps to save energy as well as extending the equipment’s lifespan.

Remember to cite all information that is not common knowledge.


## Measures of Success

Define how the project’s success will be measured. This involves explaining the experiments and methodologies to verify that the system meets its specifications and constraints.


## Resources

Each project proposal must include a comprehensive description of the necessary resources.

### Budget

Provide a budget proposal with justifications for expenses such as software, equipment, components, testing machinery, and prototyping costs. This should be an estimate, not a detailed bill of materials.
<img width="773" height="197" alt="image" src="https://github.com/user-attachments/assets/60f14c90-7f94-4488-af62-af302226a655" />



### Personel

Identify the skills present in the team and compare them to those required to complete the project. Address any skill gaps with a plan to acquire the necessary knowledge.

Besides the team, also state who you choose to be you supervisor and why.

State who your instructor is and what role you expect them to play in the project.

* Jocelyn Smith: C/C++, Assembly, Python, TypeScript, SQL, MATLAB, VHDL, Circuit Analysis, Control System Analysis, LT Spice
* Danielle Wolford: C/C++, Assembly, Circuit Analysis, PLC Coding, HMI Formatting, Control System Analysis, LT Spice, KiCad
* Kendall Arnold: C/C++, Assembly, AUTOCAD, Controls Systems, Circuit Analysis

### Timeline


<img width="1487" height="597" alt="image" src="https://github.com/user-attachments/assets/f5531d7d-e73e-413f-943a-abcbc1e83626" />



## Specific Implications

Explain the implications of solving the problem for the customer. After reading this section, the reader should understand the tangible benefits and the worthiness of the proposed work.


## Broader Implications, Ethics, and Responsibility as Engineers

Consider the project’s broader impacts in global, economic, environmental, and societal contexts. Identify potential negative impacts and propose mitigation strategies. Detail the ethical considerations and responsibilities each team member bears as an engineer.


## References

All sources used in the project proposal that are not common knowledge must be cited. Multiple references are required.


## Statement of Contributions

Each team member must contribute meaningfully to the project proposal. In this section, each team member is required to document their individual contributions to the report. One team member may not record another member's contributions on their behalf. By submitting, the team certifies that each member's statement of contributions is accurate.
