<div align="center">

# Variable-Speed Circulation Pump Controller Project Proposal

---

### Jocelyn Smith, Kendall Arnold, Skyler Raines, Danielle Wolford 

Department of Electrical and Computer Engineering  
Tennessee Technological University

</div>

<br>


## Introduction

Hot water systems are expected to supply hot water while also responding to changing levels of demand. Tankless water heaters accomplish this by heating water as it passes through the system rather than storing a large volume of heated water. As demand changes the system must adjust to provide the required water temperature and flow. The Lochinvar Regent Commercial Tankless Water Heater is designed to meet these demands. However, operating the system at maximum all the time can result in unnecessary energy consumption. Improving how the system responds to changing water demand could provide an opportunity to reduce energy use while maintaining system performance.

The objective of this project is to investigate a method of improving the energy efficiency of the Regent water heater by controlling the circulation pump according to the system's operating conditions. The proposed approach will investigate the use of a variable speed pump and flow sensor to regulate water flow based on the heating requirements of the system. By adjusting pump speed rather than continuously operating at a maximum condition, the system may be able to provide the required hot water while reducing unnecessary electrical power consumption.

This proposal will provide background information on the Regent water heater and present measurements that will help establish a better understanding of how water heating systems operate. It will also examine existing solutions and technologies that may be applicable to the project. The proposal will explain the need for the project and identify the specifications and constraints that will guide the design process. In addition, it will provide an overview of the project resources, a detailed budget, the skills and responsibilities of each team member, the expected project timeline, and the potential impacts and implications of the proposed solution.


## Formulating the Problem

The primary customer for this project is Lochinvar, specifically its engineering team, which is responsible for the design, testing, and development of its commercial water heating systems. The main product that could benefit from the results of this project is the Regent Commercial Instantaneous Water Heater. Even though the Regent is the intended application, the equipment currently available for testing at the Tennessee Tech lab consists of Lochinvar Knight KHB085 and WHB199 fire tube boilers. Lochinvar also pointed out that a recirculation loop, pump, flow sensor, and temperature sensors canbe provided if testing on Lochinvar hardware is needed. 

The problem also affects the people and facilities that use commerical domestic hot water systems. The systems need to supply hot water accurately despite if demand changes. From an engineering stand-point, Lochinvar is interested in determining whether the circulation pump can work at a lower speed when circulation isn't needed. Rather than treating the pump as a component that always needs to work at a constant, unneeded high speed, the project looks into if the pump can be more equivalent to the demands of the water heating system. The project proposal from Lochinvar specifically wants our team to run the internal circulation pump at different speeds while changing the flow rate/inlet water temperature and then measuring how the changes affect the performance of the system. 

Therefore, Lochinvar needs engineering data and a control strategy that demonstrates how and when circulation pump speed can be reduced without compromising the expected performance of the water heating system. The results from our project could help Lochinvar decide if variable speed circulation control will benefit them for the Regent system and how that control could be implemented. 

This solution is needed because the amount of hot water being used in a commercial water heating system is not always the same. The demand can change throughout the day, which means that the pump may not need to run at the same speed under every state or situation. If the system doesn't need as much flow at a specific time, running the pump at a higher speed could just be wasting power.

At the same time, we can't just lower the pump speed and assume everything will still work efficiently. There still needs to be enough flow through the heat exchanger, and the system still needs to reach and maintain the needed water temperature. One of the main main goals of the project is to find a way to lower the speed of the pump when possible without hurting the overall execution of the system.

A variable speed pump controller would allow the pump to adjust based on what is happening in the system. When the demand is lower, the pump could run at lower speeds and potentially use less power. When the demand goes high, the controller could increase the speed of the pump to make sure there is enough water running through the system. The main objective is to find the most efficient pump speed while still meeting all of the requirements of the water heating system. 

This project needs a team because there are many different parts that have to work together for the system to operate efficiently and correctly. The project involves things like water flow, temperature, sensors, physical hardware, microcontroller programming, pump control, and testing. Changing one part of the system could also affect another part.

Another challenge is figuring out how the controller should decide what speed the pump needs to run at. The controller will need to look at the flow rate, modulation, and temperature and then use that information to adjust the the speed of the pump. We will also need to make sure the pump stays within the correct working range and doesn't constantly change speeds due to small changes in sensor readings.

There are also challenges with getting all of the hardware to work together. The sensors, microcontroller, pump, and current Lochinvar system will all need to communicate efficiently. We will have to make sure that the signals and sensors we use are compatible with the system under different working conditions to see how well the controller reacts. Having multiple people working on the project allows us to divide up the programming, hardware, testing, research, and documenation while still working toward the same overall goal. 
  
There are already variable speed pumps and controllers obtainable, but they may not completely solve the problem that Lochinvar is trying to solve. A normal pump controller might adjust the the pump depending on one measurement, such as temperature, pressure, or flow. For this project, we want the controller to deliberate multiple things happening in the system before deciding what speed the pump should run at.

Our controller could use the flow rate, modulation, and water temperature to determine the speed of the pump. It also has to make sure that the system still has enough flow, maintains the correct temperature, and stays within the limits of the pump and the rest of the system. These needs are more precise to Lochinvar's application.

Because of this, the main part of our project is not just finding a variable speed pump that already exists. The engineering part is developing the control approach that decides when the pump needs to speed up or slow down based on the current state of the system. We will then have to test the controller to make sure that reducing the pump's energy usage doesn't negatively affect the execution of the water heating system. 

### Project Stakeholders and Their Needs
--- 

The development of the variable-speed circulation pump controller involves several direct and indirect stakeholders who have different expectations for the system. Lochinvar is the primary project sponsor and customer, but the design also affects the people responsible for operating, maintaining, installing, and using commercial water heating equipment. Identifying these stakeholders and their needs is important because the controller must improve energy efficiency without negatively affecting the safety, reliability, or performance of the existing water heating system.

The following table identifies the primary stakeholders, their relationship to the project, and the specific needs that must be considered throughout the design process.


| Stakeholder | Classification | Interest or Need |
|---|---|---|
| Lochinvar Engineering Team | Direct: Project sponsor and customer | Needs a reliable control strategy that adjusts circulation pump speed based on operating conditions while maintaining minimum flow, outlet-temperature stability, and existing equipment protections. Also needs testing data to evaluate potential implementation in future products. |
| Tennessee Tech Capstone Team | Direct: Designers and developers | Needs access to appropriate equipment, technical documentation, manufacturer specifications, and testing resources to develop and evaluate the controller within the project timeline and budget. |
| Tennessee Tech Faculty and Laboratory Personnel | Direct: Academic supervisors and testing personnel | Need the design to meet academic requirements, demonstrate sound engineering principles, and follow laboratory safety procedures during development and testing. |
| Commercial Facility Owners and Managers | Indirect: Customers and decision-makers | Need reliable water heating performance while potentially reducing electrical operating costs and avoiding unnecessary maintenance expenses. |
| Building Operators | Indirect: System operators | Need the water heating system to respond appropriately to changing demand without requiring frequent manual adjustments or interfering with normal boiler operation. |
| Maintenance Technicians and Service Personnel | Indirect: Maintenance and repair | Need accessible equipment, clear documentation, safe servicing procedures, and reliable fault identification to maintain and troubleshoot the system. |
| Building Occupants and Hot Water Users | Indirect: End users | Need a consistent supply of hot water at an appropriate temperature and sufficient flow rate without unsafe temperature fluctuations. |
| Regulatory Authorities and Safety Organizations | Indirect: Compliance and public safety | Need applicable electrical, plumbing, equipment, and workplace safety requirements to be considered throughout design, installation, and testing. |
| Local Community and Environment | Indirect: Broader public and environmental interests | Benefit from responsible energy use and reduced unnecessary electricity consumption. The project should avoid introducing additional safety risks or environmental impacts while pursuing energy savings. |


Although Lochinvar is the primary customer, the needs of the other stakeholders influence how the proposed controller must operate. For example, Lochinvar's interest in reducing circulation pump electrical power consumption must be balanced with the needs of building occupants who depend on reliable hot water. Similarly, maintenance technicians need the controller to operate safely and provide enough information to identify problems without interfering with the water heater's existing safety systems.

These stakeholder needs are reflected in the project's specifications and constraints. Temperature stability, minimum circulation flow, pump operating limits, electrical power reduction, and compatibility with existing safety controls are all important requirements that will be considered during development and testing. By addressing these needs together, the project can evaluate whether variable speed circulation control provides a practical improvement for Lochinvar while maintaining the safety and reliability expected by other stakeholders.

### Background

Hot water systems provide heated water for applications such as showers, baths, laundry, kitchen sinks, and other units. These systems must be capable of responding to frequent changes in hot water demands while maintaining the required water temperature and flow.
Some systems use Instantaneous water heating which is the process of using a tankless water heater that will heat up the water only when you need it[1]. The process starts with cold water entering the unit to be heated by a heating element then delivered at the desired temperature of the customer[1].

The Regent Commercial Tankless Water Heater is the target system being investigated in this project. The Regent is designed as a tankless water heater that heats water as it passes through the system rather than storing hot water in a tank[2]. Cold water, referred to as the inlet water, enters the system and flows through the heat exchanger. This is where thermal energy is transferred from the heating system to the water[2],[3]. The heated water, referred to as the outlet water, then exits the unit at the required temperature. If additional heating is needed, water can be recirculated through the heat exchanger to increase its temperature before being delivered to the system[2].

The purpose of a heat exchanger is to be able to transfer thermal energy to the water, creating the desired supply of hot water without the two ever coming in direct contact[3]. To understand heat exchangers better and how to reach desired temperatures, it's good to understand the relationship when a system at a higher temperature is in contact with a system at a lower temperature. The rate of heat transferred to the water can be described by[4]:

$$
Q_h = c \ m_V \ \Delta T 
$$

where Q_h represents the rate of heat transferred to the water, m_V represents the mass flow rate, c is the specific heat capacity of water(constant), and ∆T is the temperature change (Tout-Tin). Tout and Tin represent the outlet and inlet water temperatures. This relationship demonstrates the connection between water flow and temperature change within the system. As the circulation flow rate changes, the amount of temperature increase required to transfer a given amount of thermal energy also changes[4]. This relationship will be used as a foundation for modeling the thermal response of the system.

Flow rate describes the amount of water moving through the system over a given period also expressed as volumetric flow rate[4],

$$
Q_V = \frac{V}{t}
$$

Where Q_V is the volumetric flow rate, V is the volume of water, and t is the time.

Flow rate can also be expressed as mass flow rate, which describes the mass of water moving through the system over a given period[4]:

$$
m_V = \frac{m}{t}
$$

Where m_V is the mass flow rate, m is the mass, and t is the time.

The relationship between volumetric and mass flow rate is[4]: 

$$
m_V = \rho Q_V
$$

Where ρ is the density of water.These relationships allow changes in the volumetric flow rate of water to be related to the mass flow rate used in the heat transfer equation.
The demand for hot water is never stagnant, it is constantly changing. An increase in demand results in an increase in flow and requires the system to respond while maintaining the desired temperature. A flow sensor can detect changes in demand, allowing a variable speed pump to adjust its operation accordingly. This provides the foundation for matching pump operation to system demand rather than continuously operating at maximum capacity.

Electrical power is the rate at which electrical energy is used by a system. Power can be expressed as[16]: 

$$
P = VI
$$

where P is electrical power, V is voltage, and I is current. 

The total electrical energy consumed depends on both power and operating time[17]:

$$
E = Pt
$$

A circulation pump operating at a higher speed generally requires more electrical power. If the pump operates at maximum capacity when the system does not require maximum flow, unnecessary energy can be consumed. A variable speed pump can adjust its operation based on the required flow rate, potentially reducing power consumption during periods of lower demand. For the proposed system, monitoring and controlling pump operation can therefore help maintain the required hot water performance while reducing unnecessary electrical energy consumption.

Energy efficiency involves meeting the required system performance while using as little energy as possible. In a hot water system, the circulation pump does not necessarily need to operate at maximum speed under all operating conditions. Reducing pump speed when demand is lower can reduce unnecessary electrical power consumption.

However, reducing pump speed too much can also affect system performance by decreasing flow and potentially increasing the time required to reach or maintain the desired temperature. Therefore, the goal is to not just minimize pump speed, but to find a balance between energy consumption and system performance.

A variable speed pump provides a way to adjust flow according to system demand. By supplying only the flow needed for the current operating condition, the system can potentially reduce unnecessary energy use while still meeting the required temperature and response time requirements. This balance between efficiency and performance is a key consideration in the proposed system.

### Specifications and Constraints

#### Specifications

The main goal of this project is to develop a control strategy that adjusts the circulation pump speed based on the operating conditions of the water heating system. The controller is intended to reduce unnecessary electrical power consumption while maintaining the required water flow, temperature stability, and overall system performance. The following specifications are based on the project requirements provided by Lochinvar and the preliminary engineering targets established by the team. Each specification includes measurable criteria and a verification method to determine whether the proposed controller meets the needs of the project stakeholders.

* 1 – Temperature Stability: The system shall maintain the outlet water temperature within ±4 °F of the desired temperature setpoint during defined steady-state operating conditions. This temperature tolerance is specified in Lochinvar's original capstone project proposal. A preliminary 60 second steady state observation interval will be used to evaluate temperature stability. Verification will be completed by recording the maximum absolute temperature deviation using a calibrated reference instrument with a preliminary expanded uncertainty target of no greater than ±1 °F.

* 2 – Minimum Circulation Flow: The controller shall maintain a circulation flow rate equal to or greater than the minimum required by Lochinvar whenever circulation is necessary. The minimum allowable flow rate, ($Q_{\min}$), shall be expressed in gallons per minute (GPM) and established using the applicable manufacturer requirements for the selected heat exchanger and testing equipment. Lochinvar's original proposal confirms that maintaining minimum circulation flow is required but does not provide a numerical GPM value. Verification will be completed by comparing recorded flow measurements with the manufacturer approved minimum.

* 3 – Pump Speed Control: The controller shall adjust the circulation pump speed in response to changes in system operating conditions, including water flow rate, boiler firing rate, and outlet water temperature. Lochinvar's project documentation identifies the Grundfos UPMS 15-78 130 AR variable-speed circulation pump and describes low voltage PWM and 0–10 V control methods. The actual pump model and supported control interface will be confirmed before implementation. The allowable pump speed range, ($N_{\min}$) to ($N_{\max}$)), will be determined using the applicable pump specifications. Verification will include recording pump speed commands and measured pump response during controlled changes in demand.

* 4 – Firing Rate Monitoring: The controller shall accept a 0–10 V firing rate signal representing 0–100% firing demand from the compatible Lochinvar Knight boiler. Lochinvar's project documentation confirms this signal relationship, where 1 V represents approximately 10% firing rate. The input signal shall be conditioned to remain within the selected microcontroller's allowable electrical input range. A preliminary conversion accuracy target of ±2 percentage points of firing rate demand will be used during development. Verification will be completed by applying known input voltages and comparing the calculated firing rate percentage with the expected values.

* 5 – Flow Rate Monitoring: The controller shall convert the pulse frequency output from the KEYENCE flow sensor into a water flow measurement expressed in GPM. Lochinvar's original proposal confirms that the Regent system uses a KEYENCE FD-Q series flow sensor and converts its pulse-frequency output into a digital flow measurement. The exact sensor model, pulse to flow conversion factor, and operating range will be verified using the applicable sensor documentation. A preliminary accuracy target of ±5% of the reference reading will be used during development. Verification will be completed by comparing measured flow values with a calibrated reference over the approved operating range.

* 6 – Temperature Response Time: The system shall reach and maintain the desired outlet temperature following changes in water demand without negatively affecting the existing water heater's temperature recovery performance. Lochinvar identifies time to reach the temperature setpoint as a required performance measurement but does not specify a maximum allowable response time. A preliminary target is to return to within ±4 °F of the setpoint within 120 seconds after a defined demand change and remain within this range for at least 30 seconds. Verification will be completed by recording temperature recovery times during baseline and controlled operation under equivalent conditions.

* 7 – Electrical Power Reduction: The controller shall demonstrate a measurable reduction in circulation pump electrical power consumption compared with baseline operation under equivalent operating conditions. Lochinvar identifies reduced pump power consumption as a primary project objective but does not establish a required percentage reduction. A preliminary engineering target of at least 10% reduction in measured pump and drive electrical input power will be used for qualifying operating conditions. Verification will be completed by recording electrical input power in watts using an appropriate power measurement instrument and calculating:
  
$$
\text{Power Savings (\%)} =
\frac{P_{\text{baseline}} - P_{\text{controlled}}}
{P_{\text{baseline}}} \times 100
$$

Power savings will only be considered acceptable when minimum circulation flow, temperature stability, and equipment safety requirements are satisfied.

* 8 – Controller Stability: The controller shall adjust circulation pump speed without excessive oscillations, repeated limit cycling, or unstable temperature behavior. Lochinvar's original project proposal requires maintaining system stability but does not provide a numerical pump settling time limit. A preliminary target is for the pump speed command to settle within ±5% of its final steady state command within 30 seconds after a defined change in demand. Verification will be completed by recording pump speed commands, flow rate, and outlet temperature during controlled operating changes.

* 9 – Existing System Compatibility: The proposed controller shall operate without bypassing, disabling, or interfering with the existing Lochinvar temperature regulation and manufacturer installed safety controls. Lochinvar specifically requires that the proposed pump control strategy not negatively affect the existing temperature control system. Verification will include an electrical interface review, inspection of the proposed connections, and approved functional testing. The controller's fault response behavior will be established with Lochinvar before physical testing to ensure that existing protections remain operational.

* 10 – Operating Condition Testing: The team shall evaluate the proposed controller under a minimum of three defined operating conditions representing low, medium, and high water demand, subject to equipment availability and testing approval. Lochinvar's original project proposal requires investigating changes in water flow rate and inlet water temperature and identifies a flow tree as a method of producing repeatable demand changes. A preliminary test plan includes five paired baseline and variable speed controller trials at each operating condition, resulting in 15 paired comparisons. Measurements will include pump operating conditions, water flow rate in GPM, inlet and outlet temperatures in °F, boiler firing rate in percent, and electrical input power in watts. A preliminary acquisition and logging interval of no greater than 1 second will be used. Verification will be completed by reviewing the recorded datasets and confirming that all required operating conditions and measurements were documented.

The specifications above establish measurable criteria for evaluating the proposed controller. Requirements directly supported by Lochinvar's project documentation include the ±4 °F temperature stability tolerance, minimum circulation-flow protection, variable-speed pump operation, and evaluation of electrical power consumption and temperature response. Numerical values that are not provided in the manufacturer's documentation are identified as preliminary engineering targets and will be confirmed with Lochinvar before final testing.


#### Specification Traceability and Verification Summary
---

| Requirement | Primary stakeholder need | Acceptance evidence | Status |
|---|---|---|---|
| 1. Temperature Stability | Lochinvar and occupants need reliable outlet temperature | Maximum absolute setpoint deviation within ±4 °F over a documented steady state window, measured with calibrated reference | Existing requirement; measurement plan added |
| 2. Minimum Flow | Lochinvar requires heat-exchanger protection | Measured GPM ≥ confirmed manufacturer $Q_{\min}$ during required circulation | Manufacturer value pending |
| 3. Pump Speed | Lochinvar requires equipment compatibility | Logged command and response within approved $N_{\min}$ to $N_{\max}$ | Pump selection pending |
| 4. Firing Rate | Controller needs accurate demand information | Isolated 0–10 V input check using known reference voltages | ±2 percentage point goal preliminary |
| 5. Flow Rate | Controller needs reliable flow feedback | Calibrated reference comparison across operating range | Interface and ±5% goal preliminary |
| 6. Response Time | Occupants need timely hot water | Time to return to ±4 °F after specified demand step | 120 s / 30 s hold preliminary |
| 7. Power Reduction | Lochinvar needs demonstrable electrical savings | True RMS input power comparison at matched conditions | ≥10% preliminary target |
| 8. Stability | Operators need nonoscillatory pump behavior | Command trace, settling time and peak to peak variation | ±5% / 30 s preliminary |
| 9. Safety Compatibility | Lochinvar requires factory protections to remain active | Approved interface review and safe bench fault tests | Approved fallback pending |
| 10. Operating Conditions | Sponsor needs reproducible performance evidence | Low, medium, high condition datasets with repeated trials | Five paired runs preliminary |

#### Temperature Sensor Accuracy and Calibration
--- 

Accurate temperature measurements are necessary to verify that the proposed controller maintains the required ±4 °F outlet-temperature stability specified by Lochinvar. The originally proposed Cooper Atkins Type-K pipe clamp temperature sensors can be used to monitor temperature changes during development. However, the standard Type-K tolerance of approximately ±2.2 °C, equivalent to approximately ±4 °F, combined with pipe surface measurement differences and sensor response delays, makes uncalibrated pipe clamp measurements insufficient to independently verify the required temperature tolerance.

For final performance verification, the team will use a calibrated water temperature reference instrument with documented measurement uncertainty. A preliminary expanded uncertainty target of no greater than ±1 °F has been established for the reference measurement. An approved immersion RTD, thermistor, or calibrated reference probe may be considered depending on the available test equipment and authorized measurement locations. Thermocouple measurements will also require appropriate cold junction compensation.

The selected measurement method will be documented before testing, including calibration information, instrument specifications, and the measurement locations used. Any modifications to the existing Lochinvar equipment will require approval before implementation.

#### Constraints
  
The proposed variable speed circulation pump controller must run within the electrical, mechanical, thermal, and safety limitations of the existing Lochinvar equipment. Because the project involves commercial water heating equipment, electrical components, and circulating hot water, the design must consider relevant engineering standards and manufacturer requirements. The following constraints will guide the development and testing of the controller.

Electrical and Safety Constraints

* 1 – Electrical Installation: Electrical wiring, grounding, and protection associated with the controller shall follow the applicable requirements of NFPA 70, the National Electrical Code, where those requirements apply to the installation. The relevant provisions will be reviewed before connecting the controller to the pump or boiler equipment.

* 2 – Electrical Compatibility: The controller shall operate within the voltage and current ratings of the selected microcontroller, sensors, and pump control interfaces. The Knight boiler's 0–10 V firing rate signal must be connected through an appropriately designed signal-conditioning circuit compatible with the selected microcontroller.

* 3 – Hazardous Energy Control: Servicing or modifying the equipment shall follow applicable laboratory safety procedures and hazardous energy control requirements. OSHA 29 CFR 1910.147 provides requirements for controlling hazardous energy during servicing and maintenance in covered workplaces. Its applicability to the specific testing environment will be confirmed.

* 4 – Existing Safety Controls: The proposed controller shall not bypass or disable the boiler's existing temperature limits, flow protections, or other manufacturer installed safety functions. Any proposed connections to the existing system must be reviewed and approved before testing.

Plumbing and Mechanical Constraints

* 5 – Plumbing Requirements: Any modifications to the water circulation system shall be evaluated against applicable locally adopted plumbing requirements, including piping materials, fittings, pressure protection, and safe hot water operation. The International Plumbing Code may provide relevant requirements depending on local adoption and applicability.

* 6 – Pipe and Fitting Compatibility: Pipes, fittings, valves, and flow measurement equipment shall be compatible with the operating temperatures, pressures, and flow conditions of the selected test system. Component ratings will be verified using manufacturer documentation before installation.

* 7 – Minimum Circulation Flow: The pump shall not operate below the manufacturer-required minimum circulation flow during conditions requiring circulation. The applicable minimum flow rate will be confirmed with Lochinvar and documented in GPM before testing.
  
* 8 – Pump Operating Limits: The controller shall not command pump operation outside the allowable speed, flow, pressure, or electrical limits established by the selected pump manufacturer. Lochinvar's project documentation identifies the Grundfos UPMS 15-78 130 AR variable speed pump; the actual test pump and its approved operating limits will be verified before implementation.

System and Project Constraints

* 9 – Equipment Compatibility: The design must remain compatible with the available Lochinvar test equipment. The Regent Commercial Instantaneous Water Heater is the intended application, while the Knight KHB085 and WHB199 boilers are identified as available laboratory test equipment. Lochinvar may also provide a recirculation loop, pump, flow sensor, and temperature sensors for testing. Differences between the laboratory equipment and Regent system must be identified before applying the results to the Regent.

* 10 – Temperature Performance: Changes in circulation pump speed shall not cause the system to violate the manufacturer-specified ±4 °F outlet temperature stability requirement under the defined steady state operating conditions.

* 11 – Budget and Resources: The design shall remain within the project budget approved by the team and its stakeholders. The currently listed primary component estimates are $580 for the KEYENCE flow sensor, $500 for the variable speed pump, $20 for the microcontroller, and $79 each for two temperature sensors, totaling approximately $1,258. Additional signal conditioning components, power supplies, wiring, and testing equipment may affect the final budget. The team will also account for any equipment provided by Lochinvar to avoid unnecessary purchases.

* 12 – Project Timeline: The team must complete research, requirements development, and the proposed design during Capstone 1, with implementation and testing planned for Capstone 2 according to the approved course schedule.

Environmental and Economic Considerations

Environmental and economic factors are important considerations for this project. Reducing circulation pump speed when full operation is unnecessary may decrease electrical energy consumption and operating costs. However, the controller must maintain the required water heating performance, and potential savings must be evaluated against the additional cost of control hardware and system integration.

The team will compare measured electrical input power during baseline and controlled operation to estimate potential energy savings. The cost of implementing the controller will also be considered when determining whether the system provides a practical improvement for Lochinvar. The actual energy savings will depend on the pump characteristics, operating conditions, and results obtained during testing.

Before the controller is considered for implementation in a commercial Lochinvar product, the applicable product certification, electrical, plumbing, and safety requirements will need to be confirmed. The final design must not compromise equipment reliability or existing safety protections to achieve energy savings.

## Survey of Existing Solutions

There are several existing circulation pump technologies that are used in commercial and residential water heating systems. These technologies include fixed speed pumps, multi speed pumps, electronically commutated motor (ECM) pumps, and automatic variable speed pump controllers. Each type of pump has advantages depending on the application, but not all of them provide the level of control needed for this project. The main goal of researching these existing solutions is to understand how different systems control water circulation, reduce energy consumption, and respond to changes in demand.

Fixed speed circulation pumps run at a constant speed regardless of changes in the system's running conditions. These pumps are relatively simple to run, but they may use more electrical energy than necessary when the system does not require maximum circulation. Multi speed pumps provide some improvement by allowing the pump to operate at different predetermined speeds. However, these pumps may still require manual adjustments and cannot always respond automatically to changing water demand. Research published by Lawrence Berkeley National Laboratory explains that adjusting pump speed can reduce energy consumption by better matching pump operation to the flow requirements of a system [5].

A more advanced option is the use of variable speed pumps controlled by electronic systems. Variable frequency drives (VFDs) adjust the electrical frequency supplied to compatible pump motors, which allows the speed of the motor to change based on running requirements. The U.S. Department of Energy explains that adjustable speed pumping can reduce unnecessary energy consumption by matching the pump's output to the amount of flow needed instead of relying on throttling valves or bypassing excess flow [10]. However, the effectiveness of variable speed control depends on the pump characteristics and the operating conditions of the system.

One example of an existing variable speed circulation pump is the Grundfos MAGNA3. This pump uses several different control modes, including constant pressure, proportional pressure, AUTOADAPT, and FLOWADAPT. The proportional pressure mode adjusts pump performance as flow and pressure requirements change. AUTOADAPT automatically adjusts the pump's proportional pressure control curve based on the operating conditions, while FLOWADAPT combines automatic adjustment with a flow-limiting function [11]. These features allow the pump to respond to changes in the system rather than continuously operating at a fixed speed.

Another existing solution is the Armstrong Design Envelope pump system, which uses integrated variable-speed controls and sensorless technology. Instead of depending entirely on external sensors, the system can estimate operating conditions using information from the pump and its control system. The controller then adjusts pump operation to better match the required flow and pressure. Armstrong's Design Envelope 4300 pump is an example of this technology and is designed for applications such as HVAC and industrial water circulation [12]. This approach demonstrates how automatic pump control can improve efficiency, although the control strategy must still be suitable for the specific water heating application.

Existing variable speed pump systems can also use temperature feedback to determine how the pump should run. In a temperature based control system, a sensor measures the water temperature and compares it to a desired setpoint. The controller then adjusts pump operation based on the difference between the measured and desired conditions. More advanced control methods, such as proportional integral derivative (PID) control, can continuously adjust the control output to reduce error and improve system stability. These methods are useful because they provide a way for the system to respond to changing conditions without requiring constant manual adjustments [8].

For Lochinvar's application, the main challenge is determining how circulation pump speed affects the overall performance of the water heater. The proposed controller will investigate the use of water flow rate, boiler firing rate, and temperature measurements to decide when the speed of the pump can be reduced. Unlike a controller that only responds to pressure or temperature, this approach would consider multiple operating conditions before adjusting the pump. The controller must also maintain the minimum required flow through the heat exchanger and avoid negatively affecting temperature stability or response time.

The research shows that variable speed pumps and automatic control systems already exist, but the team still needs to decide which control approach will work best with Lochinvar's equipment. The main contribution of this project will be developing and testing a control strategy for the specific operating requirements of the Regent Commercial Instantaneous Water Heater. By comparing different pump speeds, flow rates, firing rates, and temperatures, the team can determine whether variable speed circulation control provides measurable energy savings without sacrificing system performance.

## Measures of Success

The success of this project will be determined by how well the proposed variable speed circulation pump controller improves energy efficiency while maintaining the required performance of the water heating system. The team will evaluate the controller using several measurable criteria, including temperature stability, water flow rate, electrical power consumption, response time, and overall system reliability. These measurements will be collected during testing under different operating conditions and compared with the performance of the existing system.

The following measures will be used to evaluate the success of the project:

* 1 – Temperature Stability: The system shall maintain the outlet water temperature within ±4 °F of the desired temperature setpoint. This will be verified by recording the outlet water temperature during testing at different pump speeds and water flow rates. The measured temperature will be compared to the desired setpoint to decide whether the controller maintains acceptable temperature stability under the exact test conditions.

* 2 – Minimum Flow Rate: The controller shall maintain the minimum circulation flow rate required by Lochinvar. The flow sensor will measure the amount of water moving through the system in gallons per minute (GPM). The recorded flow rate will be compared with the minimum operating flow defined by Lochinvar to verify that reducing pump speed does not cause deficient circulation through the heat exchanger.

* 3 – Electrical Power Consumption: The controller shall demonstrate a measurable reduction in pump electrical power consumption when running conditions allow the pump to run at a lower speed. Electrical power will be measured in watts during both baseline operation and variable speed run. The results will be compared under equivalent running conditions to determine the percentage of power saved.

* 4 – System Response Time: The controller shall respond to changes in water demand without significantly increasing the time required for the system to reach the desired temperature setpoint. Response time will be measured in seconds following changes in flow rate or inlet water temperature. The results will be compared with the original system to determine whether the proposed controller negatively affects temperature recuperation.

* 5 – Controller Stability: The controller shall adjust pump speed without producing excessive oscillations or unstable operating circumstances. During testing, the team will analyze pump speed, water flow, and outlet temperature to decide whether the controller responds smoothly to changes in demand. The controller will be evaluated for repeated speed changes or temperature fluctuations that could affect system execution.

* 6 – System Compatibility and Safety: The proposed controller shall run with the existing Lochinvar equipment without interfering with the system's temperature regulation or safety controls. This will be verified by testing the controller within the manufacturer's running limits and confirming that the existing safety functions remain operational.

* 7 – Economic Feasibility: The team shall evaluate whether the potential energy savings justify the additional cost of implementing the controller. The estimated cost of the required hardware will be compared with the projected reduction in electrical energy consumption. This information will be used to estimate potential operating cost savings and determine whether the proposed system could provide a functional benefit to Lochinvar.

To determine the percentage of electrical power savings, the following equation will be used:

$$
\text{Power Savings (\%)} =
\frac{P_{\text{base}} - P_{\text{controlled}}}
{P_{\text{base}}} \times 100
$$

where $P_{\text{base}}$ represents the electrical power consumed during original pump procedure and $(P_{\text{controlled}})$ represents the electrical power consumed while using the proposed variable speed controller.

The team will also compare the results from different running conditions to determine how changes in pump speed affect the flow rate, temperature stability, and power consumption. Research from the U.S. Department of Energy explains that variable speed pumping can reduce energy consumption when pump output is adjusted to match system requirements [10]. However, the actual savings for Lochinvar's equipment will need to be decidied through testing.

The project will be considered successful if the controller can reduce pump electrical power consumption while maintaining the minimum required water flow, keeping outlet temperature within ±4 °F of the desired value, and operating without interfering with the existing system controls. The testing results will provide Lochinvar with engineering data that can be used to evaluate whether variable speed circulation control would be a practical improvement for the Regent Commercial Instantaneous Water Heater.


## Resources


### Budget
## Project Budget

| Item | Price ($) |
|---|---:|
| KEYENCE FD-Q50C Series Clamp-on Flow Sensor | Free – Provided by Lochinvar |
| Microcontroller | Free – Provided by Dr. Elfouly |
| Dymola Simulation Software | Free – Provided by Lochinvar |
| Water Reservoir (small tank or bucket) | $15.00 |
| Flexible Water Tubing | $20.00 |
| Tubing Fittings and Adapters | $20.00 |
| Hose Clamps and Valves | $20.00 |
| Platform | $15.00 |
| Heating Equipment | TBD – See what TN Tech can provide |
| DC Power Supply | TBD – See what TN Tech can provide |
| Wiring and Connectors | $10.00 |
| PT100 RTD Temperature Probes (×2) | $32.38 |
| MAX31865 Interface Modules (×2) | $19.24 |
| Grundfos UPMS 15-78 130 AR Pump | TBD – Lochinvar may provide |
| PZEM-004T V3.0 AC Power Monitor | $25.00 |
| Sensor Mounts | $15.00 |
| **Total** | **$191.62** |

*Note: Total includes only items with listed prices and excludes items marked TBD.*

The proposed project budget includes the equipment and materials needed to construct the physical bench-testing setup and evaluate the performance of the variable-speed circulation pump. Several major components, including the KEYENCE FD-Q50C clamp-on flow sensor, microcontroller, and Dymola simulation software, are expected to be provided by Lochinvar or Tennessee Tech at no additional cost. The remaining equipment includes a water reservoir, flexible tubing, plumbing fittings, hose clamps, valves, a mounting platform, wiring, and sensor mounts. Two PT100 RTD temperature probes and MAX31865 interface modules will also be used to monitor the water temperature at the inlet and outlet of the system. A PZEM-004T AC power monitor will measure the pump's electrical consumption during testing.

The current estimated cost of the project is **$191.62**, based on the items with confirmed prices. The final cost may change depending on the availability of additional equipment and materials from Tennessee Tech and Lochinvar. In particular, the heating equipment and DC power supply will be investigated for availability through Tennessee Tech, while Lochinvar may be able to provide the Grundfos UPMS 15-78 130 AR circulation pump for the bench setup. These potential contributions could reduce the overall project expenses while still providing the equipment needed to conduct physical testing and compare experimental results with the simulation.

### Personnel

* Jocelyn Smith: C/C++, Assembly, Python, TypeScript, SQL, MATLAB, VHDL, Circuit Analysis, Control System Analysis, LT Spice
* Danielle Wolford: C/C++, Assembly, Circuit Analysis, PLC Coding, HMI Formatting, Control System Analysis, LT Spice, KiCad
* Kendall Arnold: C/C++, Assembly, AUTOCAD, Controls Systems, Circuit Analysis, LT Spice, KiCad, Technical Documentation
* Skyler Raines: C/C++, Assembly, Circuit Analysis, AUTOCAD, Revit, PLC, Ladder Logic, Control Systems, Troubleshooting

The capstone team consists of four members: Jocelyn Smith, Danielle Wolford, Kendall Arnold, and Skyler Raines. Each member of the team has experience with different programming languages, engineering software, and electrical engineering concepts that will be useful throughout the project. Developing a variable speed pump controller will require knowledge of programming, circuit analysis, control systems, hardware integration, and testing. The team has experience in some of these areas, which will let the work be divided depending on each member's strengths. However, there are also areas where further research and learning will be needed before the project can be completed.
Although the team has experience in programming, circuit analysis, and control systems, there are still some areas that will require further knowledge. One of the biggest challenges will be to understand how the circulation pump affects the water flow and temperature inside the heat exchanger. 

The team will also need to learn more about the specific pump, sensors, and boiler signals given by Lochinvar. This includes understanding how the 0–10 V firing rate signal and flow sensor measurements can be used when developing the controller. Another area that may need further research is deciding how to alter the pump speed without causing the system to be unstable or negatively affecting the time required to reach the desired temperature.

To achieve the knowledge needed for these areas, the team plans to research the equipment being used, review technical documentation provided by Lochinvar, and communicate with Lochinvar's engineers when questions come up. The team may also need to become more familiar with simulation software such as Dymola if modeling is included in the project. Testing and evaluating results will also help the team better understand how the system responds when different running conditions occur. By combining the skills the members already have with further research and guidance, the team should be able to work through the challenges that come up during the project.

The team has chosen Dr. Storm as the project supervisor. The supervisor will help guide the team through the engineering and technical parts of the project. This will include giving feedback on the proposed control approach, helping the team understand the equipment being used, and answering questions that may come up during development and testing. Having a supervisor with knowledge of the project will be important because the team is working with commercial water heating equipment and needs to make sure the proposed controller meets the requirements supplied by Lochinvar.

The instructor for this capstone project is Dr. Storm. The instructor will be able to give the team guidance throughout the project and to make sure the team is meeting the expectations and requirements of the capstone. This includes reviewing project documentation, providing feedback on assignments and presentations, and helping the team stay on track with the project timeline. The instructor will also help evaluate the team's progress and make sure the work being completed meets the academic and engineering expectations of capstone.

Dr. Elfouly is another academic stakeholder involved in the project who can provide additional technical guidance throughout the design and development process. His background in microcontrollers and digital system design will be especially useful when developing the control system for the variable speed circulation pump. His expertise can help the team with choosing and programming the microcontroller, processing signals from the flow and temperature sensors, and developing the control logic needed to adjust the pump speed based on the system's running conditions. Having his guidance will help the team address challenges related to hardware integration, programming, and ensuring that the controller runs correctly with the existing Lochinvar equipment.

### Timeline

<p align="center">
<img width="1487" height="597" alt="image" src="https://github.com/user-attachments/assets/f5531d7d-e73e-413f-943a-abcbc1e83626" />
</p>


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

\(9\) OpenAI, “ChatGPT,” [Online]. Available: [https://chatgpt.com/]. [Accessed: Oct. 9, 2026].

\(10\) U.S. Department of Energy and Hydraulic Institute, “Improving Pumping System Performance: A Sourcebook for Industry,” 2nd ed., May 2006. \(Online\). Available: [https://www.energy.gov/sites/default/files/2014/05/f16/pump.pdf]. \(Accessed: Oct. 22, 2026\)

\(11\) Grundfos, “MAGNA3 Operation and Control Modes.” \(Online\). Available: [https://www.grundfos.com/solutions/learn/ecademy/all-courses/the-magna3-circulator-pump-course1/magna3-operation-and-control-modes]. \(Accessed: Oct. 22, 2026\).

\(12\) Armstrong Fluid Technology, “Design Envelope 4300 Pumps.” \(Online\). Available: [https://armstrongfluidtechnology.com/products/design-envelope-4300-pumps]. \(Accessed: Oct. 22, 2026\).

\(13\) Armstrong Fluid Technology, “Armstrong Design Envelope Pumping with Integrated Sensorless Control,” white paper. \(Online\). Available: [https://armstrongfluidtechnology.com/~/media/documents/sales-and-marketing/white-papers/90_601_pspc_whitepaper.pdf?la=es-us]. \(Accessed: Oct. 22, 2026\).

\(14\) National Fire Protection Association, “NFPA 70: National Electrical Code,” 2026. \(Online\). Available: [https://www.nfpa.org/codes-and-standards/nfpa-70-development/70]. \(Accessed: Oct. 22, 2026\).

\(15\) International Code Council, “2024 International Plumbing Code,” 2024. \(Online\). Available: [https://shop.iccsafe.org/international-codes/model-codes/2024-international-plumbing-coder.html]. \(Accessed: Oct. 22, 2026\).

[16] OpenStax, “19.4 Electric Power,” University Physics Volume 2. [Online]. Available: https://openstax.org/books/physics/pages/19-4-electric-power. [Accessed: Oct. 23, 2026].

[17] OpenStax, “20.4 Electric Power and Energy,” College Physics. [Online]. Available: https://openstax.org/books/college-physics/pages/20-4-electric-power-and-energy. [Accessed: Oct. 23, 2026].

## Statement of Contributions

* Kendall Arnold - Introduction, Background, Budget
* Skyler Raines- Timeline, Broader Implications, Ethics and Responsibility as Engineers
* Jocelyn Smith - Formulating the Problem, Specifications and Constraints, Personel, Specific Implications
* Danielle Wolford - Survey of Existing Solutions, Measures of Success






<div align="center">

# Variable Speed Circulation Pump Controller
# Conceptual Design Document

---

---

### Jocelyn Smith, Danielle Wolford, Kendall Arnold, Skyler Raines

Department of Electrical and Computer Engineering

Tennessee Technological University

</div>


## Introduction

Commercial water heating systems play an important role in providing reliable hot water for applications such as apartments, hotels, restaurants, and other commercial facilities. These systems must be capable of meeting varying hot water demands while maintaining a consistent outlet temperature and sufficient flow rate. The Regent Commercial Tankless Water Heater is designed to heat water as it passes through the system rather than storing a large volume of heated water in a tank. Although this design allows the unit to provide hot water on demand, the system must respond to changes in water flow and temperature to maintain the desired performance. As hot water demand changes, the amount of energy required to heat the incoming water also changes. This creates an opportunity to investigate how the system can adjust its operation to meet actual demand without using its maximum operating capacity.

The objective of this project is to develop and evaluate a control strategy that adjusts circulation pump speed based on real time temperature and demand measurements while allowing the boiler's existing heating controls to operate independently. The proposed strategy will use components such as a variable speed pump, flow sensor, and inlet and outlet temperature sensors to monitor system conditions and determine when adjustments are needed. By using this feedback, the control system will aim to regulate water flow and coordinate heating operation to provide the required outlet temperature while minimizing unnecessary energy consumption. As hot water demand changes, the system will respond by adjusting its operating conditions rather than continuously relying on maximum capacity when it may not be necessary. The team will investigate how changes in flow rate affect heat transfer, temperature regulation, and electrical power consumption to determine the most effective control approach. Engineering calculations, computer simulations, and testing will be used to evaluate the proposed strategy under different operating conditions and assess its ability to balance energy efficiency with consistent hot water delivery. Ultimately, the goal is to establish an algorithm that improves the energy efficiency of the Regent Commercial Tankless Water Heater without compromising its performance or reliability.

## Restating the Fully Formulated Problem

The primary objective of this project is to develop and evaluate a control strategy for adjusting the pump speed of the Lochinvar Regent Commercial Instantaneous Water Heater based on changing operating conditions. Lochinvar is interested in determining whether reducing pump speed can decrease electrical energy consumption without compromising the performance of the water heating system when full circulation is unnecessary. Because hot water demand varies throughout the day, the pump may not need to operate at a constant speed under every condition. However, reducing pump speed must be carefully evaluated to ensure sufficient water flow through the heat exchanger and the ability to maintain the required water temperature.

The project will investigate the relationship between pump speed, water flow rate, inlet water temperature, and heater operation to determine how these variables affect system performance. The team will develop and evaluate a proposed control strategy that uses operating measurements to determine an appropriate pump speed under different conditions. Although the Regent is the intended application, testing may use the Lochinvar equipment available in the Tennessee Tech laboratory or additional equipment provided by Lochinvar, depending on hardware compatibility and availability. The boilers available at Tennessee Tech are also being used by other capstone teams, which may limit our access to the equipment. As a result, testing may need to rely on simulations and available operating data to identify operating conditions under which pump speed can be reduced while maintaining acceptable water heating performance.

The proposed design shall meet the following requirements:

1. Pump speed control: The pump shall be able to run at different speeds based on the system's needs.
*	Variable-speed control is the main focus of this project. Adjusting pump speed may help reduce unnecessary electrical energy use while maintaining proper water flow through the system.
  
2. Operating measurements: The system shall measure or collect water flow rate, inlet water temperature, and other available data about the water heater.
*	These measurements will help the team understand how changes in water flow and temperature affect the heater's performance and determine how the pump should be controlled.
  
3. Performance evaluation: The team shall study how pump speed, water flow, inlet water temperature, and heater operation affect system performance.
*	Evaluating these factors will help determine whether changing pump speed can improve energy efficiency without negatively affecting the water heater's operation.
  
4. Minimum flow requirements: The pump shall maintain enough water flow through the heat exchanger to meet Lochinvar's requirements.
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

## Engineering Principles, Mathematical Models, and Verification Tools (C1)

The proposed variable speed circulation pump controller will be developed around the Grundfos UPMS 15-78 130 AR circulation pump identified in the project documentation. Manufacturer published specifications for the UPMS 15-78 130 pump family provide the starting point for evaluating electrical power requirements, pump operation, and potential energy savings. These specifications will be combined with heat transfer equations and feedback control principles to develop and verify the proposed controller.

1. Manufacturer Pump Specifications

The Grundfos UPMS 15-78 130 data booklet identifies the following electrical and operating specifications:

| Parameter | Manufacturer-Published Value |
|---|---|
| Nominal electrical supply | 115 V AC, 60 Hz |
| Minimum electrical input power | 8.4 W |
| Maximum electrical input power | 68 W |
| Minimum listed current | 0.18 A |
| Maximum listed current | 1.25 A |
| Maximum system pressure | 174 psi |
| Liquid temperature range | 36–230 °F |
| Installation length | 130 mm |

These values are taken from the Grundfos UPMS technical data booklet. The final pump nameplate and specific AR configuration will be checked before implementation.

2. Electrical Input Power Calculations

The published maximum electrical input power is:

$$
P_{\max} = 68\text{ W}
$$

The published minimum electrical input power is:

$$
P_{\min} = 8.4\text{ W}
$$

The difference between the published operating extremes is:

$$
\Delta P = P_{\max} - P_{\min}
$$

$$
\Delta P = 68 - 8.4
$$

$$
\Delta P = 59.6\text{ W}
$$

The percentage difference relative to maximum electrical input power is:

$$
R = \frac{P_{\max} - P_{\min}}{P_{\max}} \times 100
$$

$$
R = \frac{68 - 8.4}{68} \times 100
$$

$$
R = 87.65\%
$$

This calculation establishes the difference between the manufacturer's published minimum and maximum electrical input power values. It does not represent the expected or experimentally verified energy savings of the proposed controller. The actual operating point must maintain the minimum circulation flow required by Lochinvar.

For the preliminary project target of a 10% reduction in electrical input power, the corresponding input power at a 68 W baseline would be:

$$
P_{\text{target}} = 68(1 - 0.10)
$$

$$
P_{\text{target}} = 61.2\text{ W}
$$

This value is a calculated target relative to the manufacturer's maximum input power, not a guaranteed operating point. Actual performance will be evaluated using measured baseline and controlled power at equivalent operating conditions.

3. Pump Affinity Laws

The pump affinity laws describe how centrifugal pump flow rate, head, and mechanical power change with rotational speed under comparable conditions.

$$
\frac{Q_2}{Q_1} = \frac{N_2}{N_1}
$$

$$
\frac{H_2}{H_1} = \left(\frac{N_2}{N_1}\right)^2
$$

$$
\frac{P_2}{P_1} = \left(\frac{N_2}{N_1}\right)^3
$$

These equations will be used to evaluate the expected relationship between pump speed and hydraulic performance. Numerical speed ratio calculations will use the selected pump's verified operating points rather than assumed rotational speeds.

The relationship between water flow rate and temperature rise can be evaluated using published performance information for the Lochinvar KNIGHT KHB085 boiler, which is one of the identified laboratory test units.

The manufacturer's published heating capacity is approximately 79,000 Btu/h, with a listed circulation flow of approximately 8 GPM for a 20°F design temperature rise.

Using the approximate water heat transfer relationship:

$$
\dot{Q}_h = 500(\mathrm{GPM})(\Delta T)
$$

Rearranging to determine the temperature rise:

$$
\Delta T = \frac{\dot{Q}_h}{500(\mathrm{GPM})}
$$

At 8 GPM:

$$
\Delta T = \frac{79{,}000}{500(8)}
$$

$$
\Delta T = 19.75^\circ F
$$

At a hypothetical reduced flow of 6 GPM:

$$
\Delta T = \frac{79{,}000}{500(6)}
$$

$$
\Delta T \approx 26.33^\circ F
$$

The calculated temperature rise increases from approximately 19.75°F to 26.33°F when the circulation flow decreases from 8 GPM to 6 GPM, assuming the same heat-transfer rate.

This example demonstrates why circulation flow must be considered when developing the pump speed control strategy. Reducing pump speed may decrease electrical power consumption, but it can also increase the temperature difference across the heat exchanger.

The 6 GPM operating point is included for calculation purposes only and has not been approved as a safe operating condition. Actual minimum flow requirements, permitted temperature rise, and operating limits must be confirmed with Lochinvar before laboratory testing. The proposed controller will not be permitted to override the boiler's existing safety protections.

The manufacturer published electrical input power values cannot be substituted directly into the mechanical power affinity law because electrical input power includes motor and control electronics losses. Manufacturer performance curves and laboratory measurements will be used to evaluate the actual relationship.

4. Heat-Transfer Model

The relationship between circulation flow and heat transfer will be evaluated using:

$$
\dot{Q}_h = \dot{m} c_p (T_{\text{out}} - T_{\text{in}})
$$

For water, an approximate relationship in U.S. customary units is:

$$
\dot{Q}_h \approx 500(\text{GPM})(\Delta T)
$$

where heat-transfer rate is expressed in Btu/h and temperature difference is expressed in °F.

The actual calculation will use the heat-transfer rate, circulation flow, and inlet and outlet temperatures associated with the Lochinvar equipment selected for testing. The manufacturer required minimum flow rate must be established before determining allowable reductions in circulation.

5. Feedback Control and Verification

The controller will use measured water flow, boiler firing rate demand, and outlet temperature to determine the circulation pump command. Feedforward control will establish an initial command, while temperature feedback will provide corrections within approved operating limits.

MATLAB will be used to calculate and plot pump performance relationships and analyze measured data. Manufacturer performance curves will be used to establish allowable pump operating conditions. STM32 development tools will support implementation and verification of sensor acquisition and control logic. Calibrated temperature, flow, and electrical power measurements will be used to compare predicted and actual system behavior.

The team will evaluate temperature stability, response time, minimum circulation flow, and electrical input power under matched baseline and controlled operating conditions. Manufacturer specifications will establish equipment limits, while experimental measurements will determine whether the proposed controller achieves its performance objectives.


## Comparative Analysis of Potential Solutions

Several potential solutions were considered for this project. Each solution uses different operating parameters to determine the appropriate pump speed, including boiler firing rate, water flow rate, outlet temperature, and predefined operating states. The selection of a final solution depends on several factors, which will be reviewed in this section.

The first potential solution involves adjusting pump speed based on the boiler's firing rate. This approach uses the boiler's existing 0–10 V signal, which represents its firing rate from 0% to 100%, to determine the appropriate pump speed. This solution does not require an additional sensor, and it could increase energy efficiency; however, firing rate alone may not accurately represent the system's circulation requirements because water demand and inlet-water temperature can vary independently of boiler output.

The second solution that was considered is based on controlling pump speed according to water flowrate. This approach adjusts circulation based on actual hot-water demand, allowing the pump to increase or decrease its speed as water usage changes. This solution also increased energy efficiency, but flow rate alone does not account for changes in inlet-water temperature or boiler firing rate, which may affect the amount of heat required to maintain the desired outlet temperature. 

The third potential solution uses a temperature-based feedback controller to regulate pump speed. This sensor will continuously measure the outlet-water temperature, which is then compared to the desired temperature. Then, the controller adjusts pump speed based on the difference between the measured and desired temperatures. This solution offers the advantage of directly monitoring temperature performance rather than relying solely on indirect indicators of system demand; however, the relationship between pump speed and outlet temperature must be determined experimentally, and the controller must be tuned carefully to prevent unstable operation or interference with the boiler's existing temperature-control system.

The fourth solution is state-based and divides the system operation into multiple states, such as startup, normal operation, increased demand, temperature recovery, and fault protection. Each state would have a corresponding pump-speed strategy based on the system's current operating conditions. This solution allows organization, and multiple operating conditions can be handled separately. This solution also can be less effective if the states are too broad. This can depend on selected pump speeds for each condition, transition conditions, and operating thresholds. 

The fifth solution is the one selected by our team, as it is the most comprehensive solution. This solution combines water flow rate, boiler firing rate, and outlet-temperature feedback. The flow rate and firing rate provide current conditions and will be used to determine the initial pump-speed command. The temperature feedback will monitor performance, and the system will make adjustments to keep the temperature at the desired point. By combining demand-based control with temperature feedback, this solution could respond to changes in hot-water usage while maintaining the required temperature performance. It also has the potential to reduce unnecessary pump operation more effectively than a strategy relying on a single input. However, this approach requires more extensive programming, sensor integration, experimental testing, and controller tuning.

The sixth and final potential solution our team proposed is simulation based, using a computer model of the boiler system. It would represent the relationships between pump speed and flow, as well as heat transfer, boiler firing rate, and outlet-water temperature. Different solutions could then be considered before being implemented physically.  This solution could help identify opportunities to reduce pump energy consumption while maintaining acceptable temperature performance. However, the accuracy of the simulation depends on how closely the model represents the actual system. 

Several factors influence the selection of the final design, including the energy savings, the ability to maintain the desired outlet temperature, responsiveness to changing water demand, implementation difficulty, and reliability during operation. Combining these inputs could therefore provide a more complete representation of the system's operating conditions, although it also increases development and testing requirements. Based on these requirements, solution five is our selected and preferred solution. This design offers the strongest overall potential to balance energy efficiency and temperature regulation because it incorporates information about both system demand and actual thermal performance. Although this solution is more complex than the alternatives, its additional inputs provide a more comprehensive basis for controlling pump operation under changing conditions. Finally, the selected design must be validated through physical testing to determine whether it actually reduces pump energy consumption while maintaining acceptable outlet-temperature performance and stable operation.



## High-Level Solution

The proposed solution is to develop a variable speed pump controller that is able to reduce unneeded use of electrical energy while maintaining the performance of Lochinvar's water heating system. Rather than having the circulation pump run at a constant speed, the controller will adjust the speed of the pump based on the system's running conditions. Measurements such as the water flow rate, inlet and outlet water temperatures, and boiler firing rate will help determine when the speed of the pump can be reduced without affecting the system's ability to deliver hot water. The overall design will consist of six subsystems: Sensor and Data Acquisition, Microcontroller and Control Logic, Pump and Motor Control, Water Heating and Hydraulic, Monitoring and Performance Evaluation, and Data Logging and Simulation. Each subsystem will have a certain role in helping the controller run properly and meet the project's requirements.

   The Sensor and Data Acquisition subsystem will collect measurements from the water-heating system and send them to the controller. The Microcontroller and Control Logic subsystem will process this information and determine the appropriate pump speed based on the control algorithm and established operating limits. The Pump and Motor Control subsystem will acquire the command and adjust the speed of the pump using hardware that is compatible.
The Water Heating and Hydraulic subsystem will include the physical equipment involved in the system, such as the pump, piping, circulation loop, boiler, and heat exchanger. Because the changes in pump speed can affect the water flow and heat transfer, the system's response will need to be observed cautiously. The Monitoring and Performance Evaluation subsystem will help decide how well the controller performs by analyzing the electrical power use, water flow, temperature stability, and the time required to reach the wanted temperature. The Data Logging and Simulation subsystem will log measurements and help the team compare results from different running conditions. If enough information is available from the system, simulation software such as Dymola may also be used to study how the system is expected to react.

   All six subsystems will work together to help the controller react to changes in hot water demand. The sensors will give updated measurements, the controller will use those measurements to decide the speed of the pump, and the pump control hardware will make the needed adjustment. The resulting changes in the flow and temperature will then be observed to gauge the system's performance.

   The main focus is to reduce the pump energy consumption without negatively affecting the water heater's process. The pump must have the ability to maintain the minimum flow necessary by the manufacturer, and the system must still reach and maintain the required water temperature. The team will use calculations, simulations, and lab testing when possible to gauge the proposed design. Although the Regent Commercial Instantaneous Water Heater is the planned application, the equipment used for testing will depend strictly on availability and compatibility. The results will help determine whether the variable speed pump control is a realistic way to improve energy efficiency while keeping trustworthy hot water performance.

#### Preliminary Control Design and Tuning Plan
--- 
The control logic described above will be developed using feedforward information from measured water flow and boiler firing rate, followed by temperature-feedback correction. A preliminary conceptual form is

$$
u_{\mathrm{cmd}}(t) = \min\left(
u_{\max},
\max\left(
u_{\min},
u_{\mathrm{ff}}(q(t), f(t)) + K_p e_T(t) + K_i \int e_T(t)\,dt
\right)
\right)
$$

Here, \(q\) is measured water flow, \(f\) is boiler firing rate demand, and \(e_T\) is the outlet temperature error defined after confirming the direction in which pump speed changes affect the actual system. The feedforward map, control gains, minimum and maximum commands, and fault response are not yet finalized. A rate limit and an appropriate deadband will be evaluated to prevent excessive command changes; integral anti-windup will be applied when a command reaches its limit. The lower command limit must never imply a flow below the manufacturer's approved minimum. Initial tuning will use simulation and approved bench tests, followed by documented adjustments based on temperature recovery, oscillation, and measured flow. The controller will preserve the existing boiler safety protections.

#### Preliminary Statistical Verification Plan
--- 

The Monitoring and Performance Evaluation and Data Logging and Simulation functions already described in the project will support repeated baseline-versus-controlled comparisons. The preliminary plan is five paired runs at each of three defined operating conditions, subject to equipment access and approval. For each pair, the team will compare true RMS electrical input power for the pump/drive at matched conditions and calculate

$$
S_i = 100 \frac{P_{\mathrm{baseline},i} - P_{\mathrm{controlled},i}}{P_{\mathrm{baseline},i}}.
$$

The results will include the mean percentage saving, standard deviation, sample size, and a 95% confidence interval where the data and assumptions support one. For outlet-temperature stability, the team will report the maximum absolute deviation from setpoint and standard deviation over a defined steady-state interval (preliminary: 60 seconds after settling), plus the recovery time after demand changes. Aborted or unsuccessful trials and their reasons will be recorded. Power savings will be interpreted as a success only when the minimum flow, temperature, and safety constraints are met.



### Hardware Block Diagram

<p align="center">
<img width="334" height="442" alt="image" src="https://github.com/user-attachments/assets/d265e0a7-57a0-460e-8f19-bc10e724f190" />
</p>

### Operational Flow Chart


<p align="center">
<img width="564" height="457" alt="image" src="https://github.com/user-attachments/assets/aeeeb999-b5ee-458f-a5ab-29ecb7f522bd" />
</p>

## Atomic Subsystem Specifications


### 1) Sensor and Data Acquisition Subsystem


**Overview:**

The Sensor and Data Acquisition Subsystem will provide real-time and high-fidelity monitoring of all the critical hydraulic and thermal parameters within the heating loop. It shall ensure the pump microcontroller maintains a continuous stream of accurate measurements. These measurements will be the flow rate, outlet temperature, and boiler firing rate for the necessary data that will be needed for the circulation pump to be accurate. The design should emphasize signal control and sensor responsiveness.


**Functional Description:**

This subsystem's core function is to capture continuous live operating data of the heating loop and transmit it to the pump's microcontroller. This will prepare raw data for safe digital processing. 
	
* Real time data collection: Pump system variables at sampling intervals, track fluctuating fluid velocity, thermal output and thermal input back into the boiler, and the boiler load.
  
* Industrial Signal Compatibility: Use hardware scaling to convert high voltage analog inputs and digital frequencies into a safe manner for the microcontroller to read.
  
* Measure Responsiveness: Shall optimize the thermal and fluid feedback to ensure it is energy efficient and saves water while maintaining the temperature.

In addition, this subsystem would also need to be able to communicate with the boiler's main controller and display screen. It will share the temperature values from the pump controller and display real time temperatures on the screen. This helps give a parameter visibility of live water temperatures.


**Subsystem Interface:**

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
     

**Subsystem Operation:**

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


**Expected User Interaction:**

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


**Functional Flowchart:**
<p align="center">
<img width="534" height="178" alt="image" src="https://github.com/user-attachments/assets/c16677ed-42c8-48d4-8e17-1cb589b570aa" />
</p>

**Specifications**

1) This subsystem shall read data from the temperature sensor.

2)	This subsystem shall read data from the flow meter.
   
3)	This subsystem shall update all data every how many seconds we choose.
   
4)	This subsystem shall send a fault error if there is any out-of-bounds data or if there is a broken connection.
   
5)	This subsystem shall send data to the microcontroller .




### 2) Microcontroller and Control Logic Subsystem

**Overview:**

The Microcontroller and Control Logic Subsystem will receive water flow measurements from the KEYENCE flow sensor through a pulse frequency input and boiler firing rate information through a conditioned 0–10 V analog input. The boiler signal will be electrically conditioned and isolated as required by the approved interface design to ensure compatibility with the selected STM32 microcontroller. Inlet and outlet temperature measurements will be received through the appropriate sensor interface and signal conditioning hardware.

The microcontroller will process these measurements and calculate a pump speed command using the proposed control algorithm. The command will be transmitted to the Pump and Motor Control Subsystem through a manufacturer supported control interface, such as low voltage PWM or 0–10 V, depending on the verified pump configuration. Operating measurements, pump commands, and controller status information will also be made available to the Data Logging and Simulation Subsystem.

During operation, the controller will continuously evaluate system measurements, calculate the required pump speed command, and enforce the established operating limits. If a sensor failure, communication error, or unsafe operating condition is detected, the controller will follow a fault response procedure approved by Lochinvar before physical testing. The final microcontroller pin assignments, electrical interfaces, and communication methods will be documented during Detailed Design.

**Inputs:**

* Water flow rate measurements from the Sensor and Data Acquisition subsystem.
* Inlet and outlet water temperature measurements, when they are available.
* Boiling firing rate information, when it is available and compatible with the controller.
* Manufacturer running limits, in which includes the minimum required water flow.
* Target the running conditions and control settings created during testing.

**Outputs:**

* Pump speed commands that are sent to the Pump and Motor subsystem.
* Related running information sent to the Data Logging and Simulation subsystem.
* Controller status or fault information, if supported by the chosen hardware.

**Interfaces and Procedure:**

The subsystem will get measurements from the Sensor and Data Acquisition subsystem. Depending on the chosen sensors and hardware, these measurements may be provided through analog voltage signals, digital signals, or digital communication. The microcontroller will process the new information and use the control algorithm to decide the suitable pump speed command. The command sent to the pump-control hardware must use a signal or communication approaches supported by the chosen equipment. The exact interface will be decided during detailed design after the team verify the pump's control requirements.
During the procedure, the controller will read the accessible measurements, evaluate the current state, and calculate a pump speed command. The pump control hardware will then adjust the pump as instructed. The updated measurements will help determine whether the adjustment creates the expected results. If the measurements suggest an unsafe or unacceptable operating procedure, the controller will need to follow a response created during the design process with Lochinvar.

**Functional Flowchart:**
<p align="center">
<img width="981" height="93" alt="image" src="https://github.com/user-attachments/assets/70949a81-fe63-4c40-ade3-aa1d8565058e" />
</p>

**Specifications**

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

**Overview:**

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


**Subsystem Operation:**

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

**Expected User Interaction:**

1) Monitoring the active speed.
2) Monitor if the pump is operating within a safe boundary.
3) Could have an override program for maintenance.

No direct user control of frequency, pump speed, voltage scaling, or safety switching loops. Pumps' minimum and maximum speed can be programmed through the microcontroller's interface.


**Functional Flowchart:**
<p align="center">
<img width="825" height="242" alt="image" src="https://github.com/user-attachments/assets/97c8f6ae-c530-4c08-8fbd-bd51574dd9e2" />
</p>

**Specifications:**

1) This subsystem shall capture the microcontroller's command and change the circulation pump speed dynamically.
   
2) The subsystem shall operate within the pump's allowable speed range.

3) The subsystem shall transmit live motor speeds to the microcontroller's display.
   
4) This subsystem shall keep the pump speed so the heat exchanger keeps the desired water temperature.


### 4) Water Heater and Hydraulic Subsystem

**Overview:**

The Water Heating and Hydraulic Subsystem will provide the physical environment needed to test the variable-speed pump controller. Its main purpose is to heat and circulate water through the existing water-heating system while allowing the team to observe how changes in pump speed affect water flow, inlet and outlet temperatures, and overall heating performance. This subsystem is expected to use the available Lochinvar water heater and circulation pump, along with the existing piping and any additional hydraulic components required for testing. Depending on the condition and configuration of the existing equipment, additional materials may be needed to establish reliable hydraulic connections.

**Functional Description:**

* **Water Heating:** use the existing water heater to provide thermal energy and heat the water according to its established operating settings.
* **Water Circulation:**  use the circulation pump to move water through the connected hydraulic components and establish the flow conditions required for testing.
* **Pump Speed Adjustment:** accommodate changes in pump speed commanded by the Pump and Motor Control Subsystem based on instructions from the Microcontroller and Control Logic Subsystem.
* **Flow and Temperature Response:** allow the team to observe how changes in pump speed affect water flow rate, heat transfer, and outlet-water temperature.
* **Sensor Integration:** provide appropriate installation points for flow and temperature sensors so that operating measurements can be collected by the Sensor and Data Acquisition Subsystem.

**Inputs:**
* Heated or partially heated water supplied by the existing water-heating equipment.
* Pump-speed commands from the Pump and Motor Control Subsystem.
* Water-flow and temperature measurements from the Sensor and Data Acquisition Subsystem for monitoring and evaluation.
* Electrical power supplied to the water heater and circulation pump through their existing electrical systems.
* Test conditions, including target outlet temperature, pump operating speed, and water-demand conditions.
* Hydraulic connections and operating settings established for each laboratory test.

**Outputs:**
* Circulated water supplied through the hydraulic system.
* Heated water at the system outlet under the operating conditions established for testing.
* Water-flow conditions that can be measured and compared at different pump speeds.
* Inlet and outlet water temperatures for evaluating heat transfer and temperature stability.
* A physical test environment for assessing the performance of the variable-speed pump controller.
* Hydraulic operating data that can be used by the Monitoring and Performance Evaluation Subsystem and the Data Logging and Simulation Subsystem.

**Interfaces and Procedure:**

The Water Heating and Hydraulic Subsystem receives pump-speed commands from the Pump and Motor Control Subsystem and the Microcontroller and Control Logic Subsystem. Flow-rate and temperature measurements are collected through the Sensor and Data Acquisition Subsystem and shared with the monitoring and data logging subsystems for performance evaluation.

Before testing, the water heater, circulation pump, piping, and connections shall be inspected for safe operation and leaks. The system is then operated, pump speed is adjusted under different conditions, and flowrate and temperature data are recorded. After testing, the system shall be shut down according to the manufacturer's procedures.

**Functional Flowchart:**
<p align="center">
<img width="431" height="273" alt="image" src="https://github.com/user-attachments/assets/3830704c-444d-49e2-8881-834f89bec4f3" />
</p>
**Specifications:**

1. The subsystem shall maintain water circulation within the water heater and pump manufacturer's operating limits.
2. All piping, fittings, and seals shall withstand the system's operating temperature and pressure without leakage.
3. The subsystem shall provide suitable locations for flow-rate and temperature sensors.
4. The subsystem shall support pump-speed adjustments through the Pump and Motor Control Subsystem.
5. The subsystem shall retain the water heater's existing safety controls and protection mechanisms.


### 5) Monitoring and Performance Evaluation Subsystem

**Overview:**

The Monitoring and Performance Evaluation Subsystem will evaluate the performance of the proposed variable speed pump control strategy during testing. It will use system operating results, including available flow rate, water temperature, and pump operating measurements, to determine how changes in pump speed affect the water heating system. The subsystem will assess whether reducing pump speed can decrease electrical energy consumption while maintaining the required water flow and temperature. The resulting performance information will be sent to the Data Logging and Simulation Subsystem for further analysis.

**Functional Description:**

The primary function of this subsystem is to evaluate the system's response to changes in pump speed. It will use the results to assess the effectiveness of the control strategy.

1. **Flow and Temperature Evaluation:** Evaluate changes in water flow rate and temperature to determine whether the system is functioning correctly.
2. **Energy Performance Evaluation:** Compare energy consumption at different pump speeds when measurements are available.
3. **Operating Requirements:** Determine whether the system maintains minimum flow and temperature requirements.
4. **Control Strategy Assessment:** Evaluate whether the proposed control strategy achieves potential energy savings without compromising the performance of the water heater.
5. **Performance Feedback:** Send evaluation results to the Data Logging and Simulation Subsystem to support further analysis.

**Subsystem Interfaces:**

1. **System Running Results Input**
   - Connected to: Water Heating and Hydraulic Subsystem.
   - Description: Receives the system's operating results. 

2. **Performance Results Output**
   - Connected to: Data Logging and Simulation Subsystem.
   - Description: Sends performance evaluation results for data recording, comparison, and further analysis.

**Subsystem Operation:**

1. **Receive Operating Results:** Obtain measurements and system operating results during pump testing.
2. **Evaluate System Performance:** Assess the effects of pump speed changes on water flow rate, temperature, and available electrical power measurements.
3. **Compare Test Conditions:** Compare performance at different pump speeds against baseline operation.
4. **Determine Effectiveness:** Evaluate whether the control strategy reduces pump energy consumption while maintaining acceptable flow and temperature performance.
5. **Transfer Results:** Send the performance results to the Data Logging and Simulation Subsystem for documentation and further analysis.

**Expected User Interaction:**

The team will use this subsystem during laboratory testing to evaluate the system's performance under different operating conditions. The results will help determine whether the proposed control strategy meets the project objectives and identify potential improvements. The subsystem will support performance evaluation only.

**Functional Flow Chart:**
<p align="center">
<img width="455" height="168" alt="image" src="https://github.com/user-attachments/assets/a5cbd779-ad76-486f-a6b7-4c7ed8f2db7f" />
</p>

**Specifications:**

1. This subsystem shall evaluate available flow rate and temperature measurements during testing.
2. This subsystem shall evaluate energy consumption when suitable measurement equipment is available.
3. This subsystem shall compare system performance under different pump speeds and operating conditions.
4. This subsystem shall evaluate whether the system maintains minimum flow and temperature requirements.
5. This subsystem shall provide performance results to the Data Logging and Simulation Subsystem for further analysis.
6. This subsystem shall help identify performance issues found during testing that may require adjustments to the proposed control strategy.


### 6) Data Logging and Simulation Subsystem

**Overview:**

The Data Logging and Simulation Subsystem will receive operating measurements from the Sensor and Data Acquisition Subsystem, pump speed commands and controller status from the Microcontroller and Control Logic Subsystem, and performance results from the Monitoring and Performance Evaluation Subsystem. The proposed logging system will record water flow rate, inlet and outlet temperatures, boiler firing rate, pump-speed command, available electrical power measurements, timestamps, and corresponding test conditions.

A preliminary logging interval of no greater than one second will be used during laboratory testing. Measurements will be stored in an organized format suitable for graphing and analysis, such as CSV files. An SD card or another compatible storage method may be used, depending on the selected hardware. The exact communication protocol and storage interface will be established during Detailed Design.

After testing, the recorded measurements will be used to compare baseline and controlled pump operation, calculate electrical power savings, evaluate temperature stability, and determine response time. If sufficient system information is available, simulation software may also be used to model the system's behavior and compare predicted results with measured data. This subsystem will support performance evaluation and future improvements to the control strategy rather than directly controlling the circulation pump.

**Inputs:**

* Water flow rate measurements from the Sensor and Data Acquisition subsystem.
* Inlet and outlet water temperature measurements, when it's available.
* Pump speed measurements or commanded pump speed values.
* Boiler firing rate information, when it's available.
* Pump electrical power measurements, if appropriate measurement equipment is available.
* Test conditions and target procedure values.
* System parameters and measured data needed to develop/evaluate a simulation model.
  
**Outputs:**

* Organized records of procedure measurements.
* Graphs and comparisons of pump speed, flow rate, temperature, and electrical power.
* Calculated performance results, including energy use and time to reach the desired temperature when enough data is available.
* Simulation results showing predicted system performance under chosen running conditions.
* Analysis that helps the team evaluate and improve the proposed control strategy.
  

**Interfaces and Procedure:**

   The subsystem will get data from the sensors, controller, and performance monitoring equipment. Depending on the chosen hardware and software, information may be handed over through digital communication, stored files, or manual data export. The exact methods and data formats will be decided during detailed design.
During lab testing, the team will take note of measurements while the pump runs under different conditions. The measurements will be organized so that results from different pump speeds and demand levels can be compared.          For simulation, the team will use available system information to decide whether an appropriate model can be developed. The model may help examine running conditions that are difficult to reproduce in the lab. When measured data is available, the team will compare the simulation results with the actual results to recognize the differences and decide whether the model needs further adjustments.
   The results from this subsystem will help the team decide whether the proposed control strategy will meet the project's requirements. If the data shows that certain pump speeds cause problems with flow or temperature, that information can be used to make changes to the control algorithm and testing in the future.

**Functional Flowchart:**
<p align="center">
<img width="942" height="203" alt="image" src="https://github.com/user-attachments/assets/6a49cbd7-0922-45fe-a327-cdd5e8c62fc1" />
</p>
**Specifications:**

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

From an environmental perspective, the controller should be designed to improve pump electrical energy efficiency compared with the current fixed-speed circulation pump. Developing a controller that adjusts pump operation based on system demand could reduce unnecessary energy consumption and decrease the facility’s overall carbon footprint. By allowing the pump to operate at different speeds rather than continuously operating at a fixed speed, the controller could improve energy efficiency during periods of lower demand. These environmental considerations will influence the control logic by prioritizing efficient pump operation while maintaining the required water temperature and circulation conditions.

From a societal standpoint, the variable circulation pump controller must operate reliably within the approved equipment limits across different commercial facilities. The system must continuously respond to fluctuating peak demands while maintaining strict temperature stability parameters. If the pump fails to satisfy these demands, it could result in financial losses, interruptions in facility operations, and risks to public health and safety. Therefore, the controller should be designed to provide reliable operation, accurate temperature monitoring, and consistent performance under changing operating conditions. These design considerations would help improve the overall reliability of the facility’s water circulation system.

From an economic perspective, implementing a variable circulation pump controller could reduce operating expenses by adjusting the pump’s performance to match system demand. Compared with a fixed-speed circulation pump, the variable controller could reduce unnecessary energy consumption during periods of lower demand. However, these potential savings must be considered alongside the controller’s initial cost, maintenance requirements, and equipment reliability. A system failure could result in additional maintenance costs, equipment damage, or interruptions in facility operations. Therefore, the design should prioritize long-term performance, efficient energy consumption, and reliability while minimizing unnecessary operating expenses.

From a scientific perspective, the variable circulation pump controller must incorporate an accurate and stable control loop capable of responding to changing operating conditions. The accuracy of the controller can be supported by field data provided by Lochinvar from its testing locations. This information will provide physical measurements that can be used to develop, configure, and validate the controller’s logic. Without accurate data, cross-referencing simulation predictions with actual system performance would be difficult and could reduce the reliability of the final design. Standardizing data-collection and testing procedures could improve simulation accuracy, help identify anomalies, and allow the team to make necessary adjustments to the controller. These practices will help ensure that the system responds appropriately to changes in temperature and demand.

Ethical responsibilities are integrated into the design and implementation of the project. As engineers, the team is committed to ensuring the accuracy and integrity of its methodology and data. This commitment includes rigorous measurement validation, proper documentation, equipment calibration, and strict attention to detail. Through collaboration with Lochinvar, the team must remain accountable for its deliverables while adhering to applicable engineering standards, copyrights, and intellectual property rights. Upholding these responsibilities allows the team to use the data provided by Lochinvar securely and incorporate that information into a product intended to remain internal to the company. Maintaining professional integrity throughout the design process will help ensure that the final controller is developed responsibly and that all testing results accurately represent its performance.

From a cultural perspective, the variable circulation pump controller should be designed to accommodate different types of commercial facilities and their operating requirements. Each facility may have different water demands, equipment configurations, and levels of operator experience. The controller would need to be configured and validated for the requirements of each facility; a user-facing interface is not part of the current design requirements. The controller should also be adaptable to different operating environments while maintaining consistent performance. This flexibility could allow Lochinvar to implement the controller in future products and across a wider range of commercial applications.

Public health and safety are essential considerations throughout the design process. The circulation pump controller must maintain the required water-temperature and flow conditions during fluctuations in system demand. Failure to maintain these parameters could create unsafe operating conditions, affect water availability, or interrupt facility operations. To address these concerns, the controller should incorporate temperature monitoring, appropriate operating limits, and fault-detection capabilities. These features would allow the system to identify abnormal operating conditions and respond appropriately. The design should also account for potential sensor failures, communication issues, and unexpected changes in system demand. Incorporating these safeguards would help protect facility operators and occupants while improving the reliability of the overall system.

Relevant engineering standards will also influence the development of the controller. Organizations such as the American Society of Heating, Refrigerating and Air-Conditioning Engineers (ASHRAE), the American National Standards Institute (ANSI), the American Society of Mechanical Engineers (ASME), and UL Standards & Engagement establish or coordinate standards relevant to building energy efficiency, electrical equipment, and control systems. ASHRAE Standard 90.1 provides requirements for energy-efficient building systems, while UL 60730-1 addresses safety requirements for automatic electrical controls. Depending on the final application of the pump, additional requirements involving water circulation, equipment protection, and electrical safety may also apply. The team will need to determine which standards apply to the controller and use them to guide the selection of electrical components, operating limits, control logic, and testing procedures. Following applicable standards will help improve the overall safety, reliability, and compatibility of the final design.

These considerations will influence the design constraints, specifications, and engineering practices implemented throughout the project. The controller must be capable of responding to fluctuations in system demand while maintaining water temperature and circulation within the operating limits established with Lochinvar. These limitations will influence the selection of sensors, the controller’s response time, pump-speed adjustments, and the development of protective features. To evaluate the controller’s performance, the team will compare its energy consumption with that of the existing fixed-speed pump and analyze temperature stability under different loading conditions. Testing should also include simulated faults and abnormal operating conditions to verify that the controller responds safely and reliably. The team will use field measurements, simulation results, and repeated testing to validate the accuracy of the control system. Proper documentation, calibration, and consistent testing practices will help ensure that the final design meets the established requirements.

In conclusion, upholding public safety remains a primary responsibility throughout this project. The development of the variable circulation pump controller must maintain reliable temperature stability under fluctuating loads in commercial facilities while improving energy efficiency and overall system performance. Achieving these goals will require each team member to complete their contributions with technical diligence, professional integrity, and attention to the environmental, societal, cultural, and economic impacts of the design. Team members must also remain mindful that this controller may be used in future products developed by Lochinvar. By following applicable engineering standards, validating system performance, and maintaining ethical responsibilities, the team can work toward delivering a safe, reliable, and efficient controller that benefits both Lochinvar and the public while reducing potential operational risks and liabilities.

#### Specific Health, Safety, and Welfare Hazards (H1)
---

The existing discussion of public health and safety above establishes the importance of reliable temperature and flow control. The following table identifies the particular hazards, people exposed, severity, design safeguards, and evidence required to make these considerations actionable.

| Hazard and Cause | People Potentially Affected | Potential Severity | Planned Design Safeguard | Verification |
|---|---|---|---|---|
| Insufficient circulation while the heater is firing | Building occupants, maintenance staff, equipment owner | High: heat exchanger overheating and equipment damage | Preserve factory high-limit and flow protections, enforce Lochinvar approved minimum flow, and use an approved circulation preserving fault response | Trace minimum flow requirement to manufacturer data; safely simulate low flow fault |
| Outlet water temperature overshoot | Building occupants and facility operators | High: possible scalding | Maintain ±4°F steady state target, monitor outlet temperature, and preserve existing heater safety limits | Calibrated reference temperature recording during approved operating changes |
| Water held at unsuitable temperatures | Occupants and building management | High: possible Legionella related health risk | Do not change existing temperature management or sanitation controls; evaluate ASHRAE Standard 188 applicability with Lochinvar | Review operating policy and confirm protective settings are not overridden |
| 120 VAC and motor electrical connections | Students, technicians, laboratory staff | High: electrical shock, burns, or fire | Isolate low voltage controls, protect power circuits, and require authorized electrical work and hazardous energy control procedures | Qualified wiring inspection and documented pre work isolation |
| Hot pressurized water and piping | Technicians and nearby personnel | High: burns, leaks, or pressure related injuries | Use manufacturer rated fittings, approved connections, and authorized plumbing work | Component rating review and supervised leak inspection |
| Gas fired boiler operation and combustion related hazards | Students, laboratory personnel, maintenance technicians, and nearby occupants | High: potential gas leaks, fire, combustion related injuries, or carbon monoxide exposure | Preserve manufacturer combustion safety controls, prohibit unauthorized gas system modifications, and require qualified personnel for gas related work | Confirm manufacturer safety protections remain operational and obtain authorized inspection before testing |
| Failed sensors or lost communication | Occupants, operators, equipment owner | High: potential unsafe circulation and equipment overheating | Validate sensor data, indicate faults, preserve existing protections, and transition to a Lochinvar approved safe circulation mode | Isolated bench fault injection testing |

Only qualified or institutionally authorized personnel will perform electrical, gas-appliance, or pressurized plumbing modifications. Unsafe fault scenarios will be tested in simulation or an approved isolated bench setup, rather than intentionally defeating the protection of an operating heater.

#### Application and Verification of Engineering Standards (H2 and H3)
--- 

Identifying engineering standards is important, but the standards must also influence the actual design and testing of the variable speed circulation pump controller. The project involves electrical connections, motor control, water circulation, temperature regulation, and equipment that may operate under hazardous conditions. Therefore, the team must consider how applicable standards and regulations affect component selection, hardware connections, controller behavior, and testing procedures.

The following table connects each identified standard or regulation to specific engineering decisions, existing project specifications and constraints, and the evidence that will be used to verify the design. The team will confirm the applicable editions, provisions, and requirements with Lochinvar and authorized Tennessee Tech personnel before implementation. These activities represent planned engineering verification and do not establish formal product certification.


| Standard or regulation | How it affects the proposed design | Verification evidence | Remaining confirmation |
|---|---|---|---|
| NFPA 70 (NEC), including Article 430 when applicable | Motor circuit wiring, grounding, overcurrent protection, and any compatible adjustable speed drive are selected and installed using applicable provisions | Qualified inspection of power schematic, wiring, component ratings, and protective devices | Adopted edition and exact relevant articles/clauses |
| OSHA 29 CFR 1910.147 | Authorized personnel establish isolation and verification steps before servicing or modifying equipment | Written lockout/tagout procedure and pre work record where applicable | Workplace applicability and institutional procedure |
| UL 60730-1 | Fault states, controller reset, and loss of input behavior inform the automatic control design | Documented bench fault injection tests showing expected and observed safe outputs | Applicable edition, relevant clauses, and product certification scope |
| Locally adopted plumbing code, using International Plumbing Code as a reference where applicable | Temperature/pressure ratings and permitted plumbing modifications constrain sensor installation | Component datasheets and approved connection inspection | Jurisdiction, code edition, and permission to modify plumbing |
| ASHRAE 188 | Existing water management controls must not be undermined by pump control changes | Review of facility temperature management strategy and interface boundary | Whether the standard applies to the final installation |
| ASHRAE 90.1 | Provides energy efficiency context without automatically imposing a prototype specific requirement | Documented applicability review and measured pump electrical power comparison | Applicability to a commercial implementation |

#### Standards Verification and Documentation Procedure

* 1. Identify Applicable Requirements: The team will review the selected boiler, circulation pump, sensors, and microcontroller documentation to determine which engineering standards, code provisions, and manufacturer requirements apply to the testing configuration. Any requirements that depend on final equipment selection will remain identified as pending until the necessary information is available.
 
* 2. Connect Standards to Design Decisions: Each applicable requirement will be connected to a specific design decision. This includes selecting compatible electrical components, establishing safe sensor connections, determining allowable pump operating limits, and developing appropriate controller responses to abnormal conditions.

* 3. Review the Design Before Implementation: Before physical testing begins, the team will review the electrical schematics, proposed hydraulic connections, and equipment modifications with Lochinvar and authorized Tennessee Tech personnel. This review will help identify potential safety concerns and ensure that the proposed controller does not interfere with existing equipment protections.

* 4. Perform Verification Testing: Verification will include reviewing component ratings, inspecting electrical connections, comparing sensor measurements with calibrated references, and evaluating controller behavior through simulations and approved bench testing. The team will also investigate how the controller responds to abnormal sensor measurements and communication failures. Unsafe conditions will be evaluated through simulation or appropriately isolated testing rather than intentionally disabling the protections of an operating water heater.

* 5. Document Testing Results: The team will maintain records identifying the requirement being evaluated, the verification method, expected results, observed results, and any corrective actions needed. Requirements that cannot be verified during the current project phase will be documented as pending rather than reported as successfully completed.
 
* 6. Review Changes to the Final Design: If the selected pump, microcontroller, boiler, or control interface changes during development, the team will review the affected engineering standards and update the relevant design requirements and verification procedures.
 
#### Remaining Standards Related Confirmations

Several engineering details still require confirmation from Lochinvar or the selected equipment manufacturers. These include the minimum required circulation flow rate, allowable pump operating range, supported pump control interface, and approved controller response during sensor or communication failures.

The team will also need to determine which electrical, plumbing, and product safety requirements apply to the final laboratory testing configuration. Until these details are confirmed, preliminary engineering targets will remain separate from verified manufacturer requirements.

The project will not claim formal product certification or complete compliance with a building level standard based solely on capstone laboratory testing.

By connecting engineering standards to specific design decisions, numbered specifications, constraints, and measurable verification activities, the team can demonstrate how safety, equipment compatibility, and professional engineering requirements are being incorporated throughout the development process.

#### Project Specific Ethics and Sustainability Actions (E1)
--- 

The development of the variable-speed circulation pump controller involves ethical responsibilities related to public safety, engineering accuracy, environmental sustainability, and the proper handling of technical information. Although the primary objective is to reduce unnecessary electrical power consumption, the controller must also maintain reliable water heating performance and operate within the approved limits of the existing Lochinvar equipment. The team must ensure that improvements in energy efficiency do not come at the expense of equipment safety, temperature stability, or the needs of individuals who depend on commercial hot water systems.

The project will follow the principles established in the IEEE Code of Ethics, particularly those involving public health and safety, sustainable engineering practices, accurate technical reporting, and professional responsibility [12]. These principles require engineers to prioritize public welfare, communicate technical findings accurately, acknowledge limitations, and consider the potential consequences of engineering decisions.


#### Public Safety and Engineering Responsibility

One of the most important ethical considerations for this project is ensuring that changes in circulation pump speed do not negatively affect the safety or performance of the water heating system. Reducing pump speed may decrease electrical power consumption, but insufficient circulation could cause excessive heat exchanger temperatures, unstable outlet water temperatures, or other operating conditions outside the manufacturer's approved limits.

To address these concerns, the controller will be designed to maintain the manufacturer required minimum circulation flow rate and preserve the existing boiler safety protections. The team will also evaluate controller responses to sensor failures, invalid measurements, and communication interruptions. Any fallback behavior that affects pump operation will require review and approval from Lochinvar before physical testing.

Safety related decisions will take priority over potential energy savings. If a proposed operating condition cannot maintain the required temperature stability, minimum circulation flow, or equipment operating limits, it will not be considered an acceptable energy-saving operating condition.

#### Accuracy, Data Integrity, and Technical Reporting

Another important ethical responsibility is ensuring that the project's results are accurate, reproducible, and presented without misleading claims. The controller's performance will be evaluated using measurements of pump electrical power consumption, water flow rate, inlet and outlet water temperatures, and boiler firing rate.

The team will document the equipment used during testing, measurement conditions, calibration information, and any known limitations in the collected data. Preliminary engineering targets will be distinguished from confirmed manufacturer requirements. For example, the proposed 10% electrical power reduction target is a preliminary team objective rather than a guaranteed performance improvement established by Lochinvar.

The team will also document unsuccessful trials, unexpected system behavior, and differences between simulated and experimentally measured results. Simulation predictions will not be presented as verified laboratory measurements. Any reported energy savings will be calculated from recorded electrical measurements under comparable operating conditions.

These practices will help ensure that Lochinvar receives reliable engineering information that can be used to evaluate the feasibility of implementing variable speed circulation control.

#### Intellectual Property and Confidentiality

Because this project is sponsored by Lochinvar, the team may receive manufacturer documentation, equipment information, technical specifications, and operating data that are not intended for unrestricted public distribution.

The team will respect Lochinvar's intellectual property and confidentiality requirements by reviewing technical information before including it in public reports, presentations, or online repositories. Any confidential or proprietary information will only be shared with individuals who have appropriate authorization.

Publicly available technical references, manufacturer documentation, and external research will be cited appropriately. The team will also acknowledge the contributions of its members and other individuals who provide technical assistance throughout the project.

#### Environmental Sustainability and Energy Efficiency

Environmental sustainability is directly related to the purpose of the variable speed circulation pump controller. Commercial water heating systems consume energy during normal operation, and reducing unnecessary pump electrical power consumption could provide an opportunity to decrease energy use.

The proposed controller will attempt to improve efficiency by adjusting circulation pump speed according to water flow rate, boiler firing rate, and outlet-temperature feedback. Rather than operating at a constant high speed, the controller will determine whether a lower speed can maintain the required system performance.

However, reducing pump speed does not automatically guarantee lower total system energy consumption. The team must evaluate whether reduced pump electrical power is accompanied by changes in heating performance, temperature recovery time, or other operating conditions.

The environmental benefits of the proposed design will therefore be evaluated using measured electrical power consumption and documented operating conditions. Any estimated reductions in electrical energy use or greenhouse gas emissions will be supported by stated assumptions and calculations rather than unsupported predictions.

The team will also consider the environmental impact of additional electronic components, wiring, sensors, and equipment required to implement the controller. Reusing compatible equipment provided by Lochinvar or Tennessee Tech may help reduce unnecessary material consumption and project costs.

#### Economic and Social Responsibility

The proposed controller may provide economic benefits to Lochinvar and commercial facility owners by reducing unnecessary circulation pump electrical power consumption. However, these potential savings must be compared with the additional costs associated with sensors, microcontroller hardware, installation, maintenance, and equipment integration.

The team will consider whether the controller provides a practical improvement rather than assuming that increased system complexity is justified by a small reduction in electrical power consumption.

The project must also consider the individuals who rely on commercial hot water systems. Building occupants require reliable hot water at appropriate temperatures, while facility operators and maintenance personnel need equipment that can operate safely and be serviced without unnecessary complications.

These stakeholder needs will be considered when evaluating the proposed control strategy. The design will not prioritize electrical power savings over the reliability, safety, or maintainability of the water heating system.

#### Ethical Verification and Accountability

The team will incorporate ethical considerations into its design reviews, testing procedures, and final evaluation. The following table identifies the main ethical responsibilities, how they will be addressed, and the evidence that will be used to demonstrate that these considerations were evaluated.


| Ethical Consideration | Planned Action | Verification Evidence |
|---|---|---|
| Public Safety | Maintain the manufacturer-required minimum circulation flow rate and preserve existing Lochinvar boiler safety protections. | Approved operating limits, design reviews, and documented safety test results. |
| Data Integrity | Record actual measurements, calibration information, operating conditions, and unsuccessful trials. | Test logs, calibration records, and documented experimental results. |
| Honest Reporting | Clearly distinguish preliminary engineering targets, simulation predictions, and experimentally measured performance. | Final technical report, engineering calculations, and supporting datasets. |
| Intellectual Property | Protect confidential Lochinvar information and properly cite external technical sources. | Sponsor-approved documentation, public repository reviews, and reference list. |
| Environmental Sustainability | Evaluate electrical energy savings and consider the environmental impact of additional electronic components and materials. | Electrical power measurements, energy calculations, and component inventory. |
| Economic Responsibility | Compare potential electrical energy savings with hardware, installation, integration, and maintenance costs. | Project budget and preliminary cost-benefit evaluation. |
| Stakeholder Welfare | Maintain reliable hot water performance while considering the needs of building occupants, operators, and maintenance personnel. | Temperature stability, minimum-flow, controller stability, and equipment compatibility verification results. |


The team will review these responsibilities during design development and before approved physical testing. Any identified safety concerns, unreliable measurements, or conflicts with manufacturer requirements will be documented and addressed before the affected design is considered acceptable.

By incorporating professional ethics, sustainability, and stakeholder responsibilities into the development process, the project can evaluate potential improvements in energy efficiency while maintaining the safety, reliability, and integrity expected of an engineering design.


## Resources


### Budget

The proposed budget covers all six subsystems required to develop and evaluate the variable-speed pump controller. The selected design combines flow-rate measurements, the boiler's firing-rate signal, and outlet-temperature feedback to adjust pump speed according to operating conditions.

The budget includes sensing and data acquisition, control hardware and programming, pump-speed control equipment, hydraulic components, performance-monitoring instruments, and data-logging and simulation resources. The estimates are preliminary allowances and assume that the existing Lochinvar water heater, circulation pump, and Keyence flow sensor can be reused where compatible. Existing laboratory equipment and available software are also assumed to be available at no additional cost.

**1. Sensor and Data Acquisition Subsystem**
<p align="center">
<img width="930" height="290" alt="image" src="https://github.com/user-attachments/assets/5b57a5b0-8418-431c-8efe-411c7938d2df" />
</p>
Justification: The flow sensor measures hot-water demand, while the temperature sensors measure system thermal performance. Signal-conditioning components and wiring provide reliable connections to the controller, and the data acquisition interface allows sensor measurements to be read and recorded. The budget assumes the existing flow sensor is compatible with the selected control hardware.

**2. Microcontroller and Control Logic Subsystem**
<p align="center">
<img width="922" height="350" alt="image" src="https://github.com/user-attachments/assets/ceb87af1-52ad-4600-83e7-ed0697139abc" />
</p>
Justification: The microcontroller executes the control logic and processes the flowrate, firing-rate, and temperature measurements. The analog input interface is needed to read the boiler's 0–10 V firing-rate signal, while the analog output interface generates the appropriate command for the pump-speed control equipment. The connection hardware helps protect and organize the electronics. Final component selection must account for signal ranges, electrical isolation, and compatibility with the existing boiler and drive.

**3. Pump and Motor Control Subsystem**
<p align="center">
<img width="916" height="266" alt="image" src="https://github.com/user-attachments/assets/1311b881-9dbe-4518-85d0-45c9e92654bb" />
</p>
Justification: The speed controller adjusts pump operation based on the command from the microcontroller. The VFD is a preliminary option for an appropriately compatible AC motor; the existing pump and motor specifications must be checked before selecting the drive. Wiring and electrical protection components support safe integration. If the existing pump uses a different motor type or has an integrated electronic controller, a different compatible speed-control solution may be required.

**4. Water Heating and Hydraulic Subsystem**
<p align="center">
<img width="928" height="414" alt="image" src="https://github.com/user-attachments/assets/980f4cd6-dc09-4630-a1bd-6dc61566811c" />
</p>
Justification: The water heater and circulation pump provide the existing test platform. Fittings and connectors support proper hydraulic connections, while valves allow the system to be configured for testing and insulation helps reduce heat loss. Seals and leak-prevention materials support safe, reliable operation. The estimate assumes that the existing equipment is functional and that major plumbing modifications are unnecessary.

**5. Monitoring and Performance Evaluation Subsystem**
<p align="center">
<img width="916" height="264" alt="image" src="https://github.com/user-attachments/assets/fbc19844-e9e7-49d8-9760-4bc164dbd20a" />
</p>
Justification: Electrical power measurements allow the team to compare pump energy consumption under fixed-speed and variable-speed operation. An independent temperature instrument provides a way to verify the installed sensors, while measurement accessories support data collection during testing. These measurements are necessary to determine whether the proposed controller reduces energy use without negatively affecting outlet-temperature performance.

**6. Data Logging and Simulation Subsystem**
<p align="center">
<img width="918" height="272" alt="image" src="https://github.com/user-attachments/assets/f7282957-da67-4ab6-af13-652bc6a57889" />
</p>
Justification: Data logging software records flow rate, firing rate, outlet temperature, pump speed, and electrical power measurements for later analysis. Simulation software can help evaluate control strategies before hardware implementation. The budget assumes access to an existing computer and a suitable software license or free simulation tool. If a paid MATLAB/Simulink or Dymola license must be purchased, the project budget will need to be revised.

**7. Comprehensive Project Budget**
<p align="center">
<img width="778" height="342" alt="image" src="https://github.com/user-attachments/assets/cf2bb408-17c0-472a-bb89-265b29597eb6" />
</p>

### Division of Labor


* High-Level Solution - Jocelyn Smith
	* Requirements: Develop an overall solution for the variable-speed pump controller, identify how the six subsystems will work together, 	create a hardware block diagram, and develop an operational flowchart showing how the system will respond to changing operating 			conditions.
	* Responsible team member and rationale: Jocelyn was assigned this section because of her experience with circuit analysis, 				control systems, and programming. Her knowledge of C/C++, Python, and MATLAB will help her understand how the different subsystems 			interact and how they contribute to reducing pump energy consumption while maintaining system performance.
* Atomic Subsystem (Microcontroller and Control Logic) - Jocelyn Smith
	* Requirements: Develop the control logic needed to process sensor measurements and determine the appropriate pump speed. Identify the 		microcontroller requirements, establish how information will be received from the sensors, and determine how commands will be sent to 		the pump control hardware. The design must also account for minimum flow requirements, temperature conditions, and potential sensor 		errors.
 	* Responsible team member and rationale: Jocelyn was assigned this subsystem because of her experience with C/C++, Assembly, 				Python, and control system analysis. These skills will be very useful when developing the programming needed to process sensor data and 	adjust pump speed based on the system's operating conditions. Her background in circuit analysis will also help with understanding the 		connections between the microcontroller, sensors, and pump control hardware.
* Atomic Subsystem (Data Logic and Simulation Subsystem) - Jocelyn Smith
	* Requirements: Developing a method for collecting and organizing operating data, including water flow rate, temperature, pump speed, 		and electrical power when available. Use MATLAB or other available software to analyze the collected measurements, develop simulations 		when sufficient information is available, and compare different running conditions to evaluate potential energy savings and system 			performance.
	* Responsible team member and rationale: Jocelyn was assigned this subsystem because of her experience with MATLAB, Python, and 			control system analysis. These skills will help her organize experimental data, develop simulations, and analyze how changes in pump 		speed affect the water heating system. Because this subsystem works closely with the Microcontroller and Control Logic subsystem, 			assigning both to the same team member will also help maintain consistency between the controller design and performance analysis.
 * Atomic Subsystems(Monitoring and Performance Evaluation Subsystem)- Kendall Arnold
	 * Requirements: Develop a method for evaluating system performance using operating data, including water flow rate, inlet and outlet 		 water temperatures, pump speed, and available heater operating measurements. Compare the system’s energy consumption and water heating 	 performance when the pump operates at different speeds with its performance at a constant speed. This will help determine whether the 		 proposed control strategy reduces electrical energy consumption while maintaining required water heating performance. Verify that the 		 system meets minimum flow and temperature requirements, evaluate the control strategy under different operating conditions, and 			 provide performance results to the Data Logging and Simulation Subsystem for further analysis.
     * Responsible team member and rationale: Kendall was assigned this subsystem because of her background in applied physics and 				 experience conducting experimental projects involving data collection, analysis, and comparison of results. She is also experiences 		 with C/C++, assembly, and currently in Control Systems. These skills will be valuable when evaluating system performance under 			 different operating conditions and determining whether the proposed control strategy reduces electrical energy consumption without 		 compromising the performance of the heater.
* Atomic Subsystem (Sensor and Data Acquisition Subsystem) – Skyler Raines
	* Requirements: Collect and transfer data from the system. This includes water flow rate, inlet and outlet water temperatures, and 		  boiler firing rate for the necessary data that will be needed for the circulation pump to be accurate. Process sensor readings into 		usable data and send them to the Microcontroller and Control Logic Subsystem to support pump speed adjustments. Identify sensor 			faults, disconnected sensors, and measurements outside acceptable operating ranges. Provide the collected measurements to the 			  Monitoring and Performance Evaluation Subsystem and Data Logging and Simulation Subsystem for analyzing system performance.
	* Responsible team member and rationale: Skyler was assigned this subsystem because her background in Electronics and Computer 			Engineering Technology provides relevant knowledge of electrical connections and hardware components. Her experience assembling 			electrical panels and working with wiring during her internship will help her connect sensors, integrate their wiring with the 			  microcontroller, and ensure the hardware is properly assembled. Her troubleshooting experience will also be useful for identifying 		  faulty connections and resolving issues that could affect the accuracy and reliability of collected data. Additionally, her current 		Control Systems coursework provides relevant knowledge.
* Atomic Subsystem (Pump and Motor Control Subsystem) – Skyler Raines
	* Requirements: Adjust the circulation pump speed based on commands received from the Microcontroller and Control Logic Subsystem. 		  Keep the pump operating within its range while providing sufficient water flow to maintain required water heating performance. 			  Provide pump operating data to the Monitoring and Performance Evaluation Subsystem for analysis and maintain safe pump operation if a 	  control or communication fault occurs.
	* Responsible team member and rationale: Skyler was assigned this subsystem because her experience assembling electrical panels and 		  troubleshooting electrical hardware provides a foundation for integrating the pump's motor control components. Her background in 			  Electronics and Computer Engineering Technology will help her work with electrical connections between the pump, motor control 			  hardware, and microcontroller. Her troubleshooting skills will also be valuable for diagnosing wiring problems, addressing hardware 		  malfunctions, and helping ensure the pump control system operates reliably during testing.
* Comparative Analysis of Potential Solutions - Danielle Wolford
	* Requirements: Research and compare the different control strategies that could be used for the variable speed circulation pump 			  controller. Evaluate each solution based on energy efficiency, temperature stability, water flow requirements, system response, and 		  implementation difficulty. Identify the advantages and disadvantages of each approach and explain why the combined flow rate, boiler 		  firing rate, and temperature feedback solution was selected as the preferred design.
	* Responsible team member and rationale: Danielle was assigned this section because of her experience with control system analysis, 		  circuit analysis, and PLC programming. These skills will help her understand how different control strategies operate and evaluate 		  how each approach could affect the performance of the water heating system. Her knowledge of control systems will also be useful when 	  comparing the proposed solutions and determining which approach best meets Lochinvar's requirements.
* Budget - Danielle Wolford
	* Requirements: Develop an estimated budget for the variable speed circulation pump controller, including the components and 				  equipment needed for all six subsystems. Identify the expected costs of sensors, microcontroller hardware, pump control equipment, 		  hydraulic components, testing instruments, and simulation resources. Explain why each component is needed and determine how existing 		  equipment given by Lochinvar or Tennessee Tech could help reduce the overall project cost.
  	* Responsible team member and rationale: Danielle was assigned this section because of her experience with circuit analysis, KiCad, 		  and electrical hardware. These skills will help her understand the components that are needed for the controller and decide which 		  materials and equipment should be included in the project budget. Her background in programming and control systems will also help 		  her identify the hardware and software resources needed to develop and test the proposed design.
* Atomic Subsystem (Water Heating and Hydraulic Subsystem) - Danielle Wolford
	* Requirements: Develop the design requirements for the physical water heating and circulation system, including the water heater, 		  circulation pump, piping, and hydraulic connections. Identify how the subsystem will secure changes in pump speed while maintaining 		  the required water flow and temperature. Determine how the subsystem will interface with the Pump and Motor Control, Sensor and Data 		  Acquisition, and Monitoring and Performance Evaluation subsystems. The design must also consider the equipment compatibility, 			  operating limits, and existing safety controls.
	* Responsible team member and rationale: Danielle was assigned this subsystem because of her experience with circuit analysis, control systems, and electrical hardware design. These skills will help her understand how the circulation pump and water heating equipment interact with the controller. Her background in PLC programming and control system analysis will also be useful when analyzing how changes in pump speed affect water flow and temperature. This knowledge will help her develop a subsystem design that secures reliable procedure and meets the requirements made by Lochinvar.
  
### Timeline

<p align="center">
<img width="1262" height="665" alt="image" src="https://github.com/user-attachments/assets/40428e21-fbbf-461b-a409-2e50152ccd55" />
</p>


## References

[1] Lochinvar, “Regent™ Commercial Tankless Water Heater – 6 Gallons | Model IWH0500N,” Lochinvar. [Online]. Available: [https://www.lochinvar.com/en_CA/products/tankless-condensing-regent/iwh0500n-100/100389046.html]. [Accessed: Oct. 16, 2026]

[2] Lochinvar, Regent Commercial Tankless Water Heater Installation and Operation Manual, Rev. D, document no. 100399794/2000857139. [Online]. Available: Lochinvar Regent Manual (PDF). [Accessed: Oct. 16, 2026]

[3] M. Irfan, A. A. Amin, S. Waseem, S. Rahman, H. Alwadie, and S. Al Dawsari, “Design of a fault-tolerant control system for a centrifugal pump-based level control system for sensor faults,” Scientific Reports, vol. 16, art. no. 14189, Mar. 2026, doi: 10.1038/s41598-026-42361-x.

[4] U.S. Department of Energy, Hydraulic Institute, and Europump, Variable Speed Pumping: A Guide to Successful Applications—Executive Summary. U.S. Department of Energy, Energy Efficiency and Renewable Energy, Industrial Technologies Program. [Online]. Available: Variable Speed Pumping (PDF). [Accessed: Oct. 16, 2026]

[5] T. C. Hayes and P. Horowitz, The Art of Electronics Student Manual. Cambridge, U.K.: Cambridge University Press, 1989. [Online]. Available: The Art of Electronics Student Manual (PDF). [Accessed: Oct. 16, 2026]

[6] U.S. Department of Energy and Hydraulic Institute, “Improving Pumping System Performance: A Sourcebook for Industry,” 2nd ed., May 2006. [Online]. Available: [https://www.energy.gov/sites/default/files/2014/05/f16/pump.pdf]. [Accessed: Oct. 22, 2026].

[7] ASHRAE, “Design and Application of Controls,” 2023 ASHRAE Handbook—HVAC Applications, ch. 48, 2023. [Online]. Available: [https://handbook.ashrae.org/Handbooks/A23/IP/A23_Ch48/A23_Ch48_ip.aspx]. [Accessed: Oct. 9, 2026].

[8] National Fire Protection Association, “NFPA 70: National Electrical Code.” [Online]. Available: [https://www.nfpa.org/codes-and-standards/nfpa-70-development/70]. [Accessed: Oct. 22, 2026].

[9] Occupational Safety and Health Administration, “1910.147—The Control of Hazardous Energy (Lockout/Tagout).” [Online]. Available: [https://www.osha.gov/laws-regs/regulations/standardnumber/1910/1910.147]. [Accessed: Oct. 9, 2026].

[10] International Code Council, “2024 International Plumbing Code,” 2024. [Online]. Available: [https://shop.iccsafe.org/international-codes/model-codes/2024-international-plumbing-coder.html]. [Accessed: Oct. 22, 2026].

[11] V. Tutterow and A. T. McKane, “Variable Speed Pumping: A Guide to Successful Applications,” Lawrence Berkeley National Laboratory, 2004. [Online]. Available: [https://escholarship.org/uc/item/4691d71q]. [Accessed: Oct. 9, 2026].

[12] IEEE, “IEEE Code of Ethics,” IEEE Circuits and Systems Society. [Online]. Available: https://ieee-cas.org/about/ieee-code-ethics. [Accessed: Nov. 14, 2026].

[13] Lochinvar, “KNIGHT Fire Tube Boiler Product Summary: KHB Series,” Lochinvar Corporation. [Online]. Available: [https://assets.lochinvar.com/damroot/Original/10012/024819KHB-PS-01.pdf]. [Accessed: Nov. 15, 2026].

[14] Lochinvar, “KNIGHT Fire Tube Boiler Installation & Operation Manual, Models 55–285,” Lochinvar Corporation. [Online]. Available: [https://www.lochinvar.com/lit/712268KHB-I-O_Rev%20D_100305277_2000558126%20%2834301%29.pdf]. [Accessed: Nov. 15, 2026].



## Statement of Contributions


Jocelyn Smith: High Level Solution, Atomic Subsystem (Microcontroller and Control Logic, Data Logic and Simulation Subsystem), Divison of Labor

Skyler Raines: TimeLine, Ethical, Professional, and Standards Considerations, Atomic Subsystems(Sensor and Data Acquisition Subsystem and Pump and Motor Control Subsystem)

Kendall Arnold: Introduction, Restating the Fully Formulated Problem, Atomic Subsystems(Monitoring and Performance Evaluation Subsystem), Division of Labor

Danielle Wolford: Comparative analysis of potential solutions, Budget, Atomic Subsystems (Water Heating and Hydraulic Subsystem)

