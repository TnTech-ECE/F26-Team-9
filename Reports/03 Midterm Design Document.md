<div align="center">

# Variable Speed Circulation Pump Controller Project Proposal

---

### Jocelyn Smith, Kendall Arnold, Skyler Raines, Danielle Wolford 

Department of Electrical and Computer Engineering  
Tennessee Technological University

</div>

<br>


## Introduction

Hot water systems are expected to supply hot water while also responding to changing levels of demand. Tankless water heaters accomplish this by heating water as it passes through the system rather than storing a large volume of heated water. As demand changes the system must adjust to provide the required water temperature and flow. The Lochinvar Regent Commercial Tankless Water Heater is designed to meet these demands. However, operating the system at maximum all the time can result in unnecessary energy consumption. Improving how the system responds to changing water demand could provide an opportunity to reduce energy use while maintaining system performance.

The objective of this project is to investigate a method of improving the energy efficiency of the Regent water heater by controlling the circulation pump according to the system's operating conditions. The proposed approach will investigate the use of a variable speed pump and flow sensor to regulate water flow based on the heating requirements of the system. By adjusting pump speed rather than continuously operating at a maximum condition, the system may be able to provide the required hot water while reducing unnecessary electrical power consumption.

This proposal will provide background information on the Regent water heater and present measurements that will help establish a better understanding of how water heating systems operate. It will also examine existing solutions and technologies that may be applicable to the project. The proposal will explain the need for the project and identify the specifications and constraints that will guide the design process. In addition, it will provide an overview of the project resources, a preliminary budget, the skills and responsibilities of each team member, the expected project timeline, and the potential impacts and implications of the proposed solution.


## Formulating the Problem

The primary customer for this project is Lochinvar's engineering team, which is responsible for designing, testing, and developing commercial water heating systems, including the Regent Commercial Instantaneous Water Heater. Commercial hot water demand changes throughout the day, creating a need to determine whether circulation pump energy consumption can be reduced during periods of lower demand without compromising minimum circulation flow, outlet water temperature, or overall heating performance. The project will evaluate whether a reduction of at least 10% in pump electrical input power can be achieved under comparable operating conditions while maintaining Lochinvar's required flow and temperature limits.

### Project Stakeholders and Their Needs
--- 

The controller must meet the needs of the sponsor without creating additional risks for people who use, maintain, or test hot-water equipment. Lochinvar needs credible engineering results that show whether the control strategy can reduce pump power while maintaining acceptable thermal and hydraulic performance. The capstone team needs equipment, documentation, technical support, and enough time to construct and test the bench loop. Tennessee Tech faculty and laboratory personnel need a setup that can be reviewed and operated safely.

The following table identifies the primary stakeholders, their relationship to the project, and the specific needs that must be considered throughout the design process.


| Stakeholder | Classification | Interest or Need |
|---|---|---|
| Lochinvar Engineering Team | Direct — sponsor and customer | A practical pump-control strategy supported by repeatable bench measurements, model validation, and clearly stated operating limits. |
| Tennessee Tech Capstone Team | Direct — designers and developers | Access to compatible components, engineering information, simulation tools, and a realistic testing schedule. |
| Tennessee Tech Faculty and Laboratory Personnel | Direct — academic and safety oversight | Documented electrical, hydraulic, and thermal safeguards; an approved bench setup before energizing equipment. |
| Commercial Facility Owners and Managers | Indirect — future customers | Reliable hot-water performance and the possibility of lower electrical operating costs. |
| Building Operators | Indirect — future operators | Predictable temperature and flow performance with clear indications of abnormal conditions. |
| Maintenance and Service Personnel | Indirect — future service users | Safe access, documented connections, identifiable faults, and procedures for working around electrical and heated-water equipment. |
| Building Occupants and Hot-Water Users | Indirect — end users | Adequate flow and stable water temperature without unsafe overheating or scalding. |
| Safety and Regulatory Authorities | Indirect — oversight | Appropriate consideration of electrical, plumbing, workplace, and equipment-safety requirements. |
| Local Community and Environment | Indirect — broader impact | Responsible use of electricity and water without shifting energy savings into avoidable safety or reliability problems. |

These needs shape the project's main requirements. Pump electrical savings will only count as a successful result when the bench loop also meets its approved flow, temperature, and safety limits. The team will document both successful and unsuccessful tests so Lochinvar can understand the benefits and limitations of the proposed controller.

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

For centrifugal pumps, the relationship between pump speed and energy consumption can be described using the pump affinity laws[18]. These laws state that volumetric flow rate is proportional to pump speed, pump head is proportional to the square of pump speed, and pump power is proportional to the cube of pump speed. These relationships can be expressed as:

```math
\frac{Q_2}{Q_1}=\frac{N_2}{N_1}
```

```math
\frac{H_2}{H_1}=\left(\frac{N_2}{N_1}\right)^2
```

```math
\frac{P_2}{P_1}=\left(\frac{N_2}{N_1}\right)^3
```

Where Q represents volumetric flow rate, H represents pump head, P represents pump power, and N represents pump rotational speed. Subscripts 1 and 2 represent the initial and adjusted operating conditions. 

These relationships provide a theoretical model for predicting pump performance at different operating speeds. However, actual energy savings may differ because of changes in pump efficiency, motor and electronic losses, minimum flow requirements, and the hydraulic characteristics of the circulation loop. In particular, static head can prevent flow and power from following the ideal affinity-law relationships. The predictions will provide a baseline for comparison.

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

In addition to controlling pump speed, evaluating energy efficiency requires measuring the actual electrical power consumed by the pump. Electrical power can be estimated using voltage and current. However, for AC-powered equipment, their product represents apparent power rather than actual real power because of power factor. Therefore, a power measurement device capable of measuring real power will be used at the pump's electrical input to measure total electrical consumption, including the motor and its internal drive electronics. This allows energy use to be compared between constant-speed and variable-speed operation to determine whether adjusting pump speed produces measurable energy savings.

However, reducing pump speed too much can negatively affect system performance by decreasing flow and potentially increasing the time required to reach or maintain the desired water temperature. Therefore, the objective is not simply to minimize pump speed, but to find a balance between electrical energy consumption and heating performance.

A variable speed pump provides a way to adjust water flow according to system demand. By supplying only the flow needed under current operating conditions, the system can potentially reduce unnecessary energy consumption while maintaining the required temperature, minimum flow rate, and response time.

### Specifications and Constraints

#### Specifications

The following requirements describe how the controller will be evaluated on the bench. Values not provided by Lochinvar or the selected equipment manufacturers are preliminary engineering targets. They will be reviewed with the sponsor and faculty before final testing.

* 1 – Temperature Stability: During a defined steady-state bench condition, the controller shall maintain the measured outlet-water temperature within ±4°F of the selected setpoint. A preliminary 60-second observation window will be used after the system settles. Verification will use a calibrated water-temperature reference with a preliminary expanded uncertainty target of no greater than ±1°F. The maximum absolute deviation and standard deviation will be reported. The ±4°F target is based on the original project objective; its application to the bench will be confirmed during test planning.

* 2 – Minimum Circulation Flow: The controller shall maintain flow at or above the safe minimum established for the selected bench heat source, pump, and circulation loop whenever heated circulation is required. The numerical minimum, in GPM, will be documented from component requirements and the approved bench design before testing. Verification will use recorded flow measurements and approved low-flow fault tests. The bench minimum shall not be represented as the Regent's manufacturer-required minimum.

* 3 – Pump Speed Control: The controller shall issue commands within the selected pump's supported control range and respond to changing operating conditions. The proposed Grundfos UPMS 15-78 130 AR remains a candidate pump, subject to availability and confirmation of its exact interface and electrical ratings. Verification will compare commanded operation with observed flow and available pump feedback during bench trials.

* 4 – Heating-Demand Input: For bench testing, the controller shall accept a representative heating-demand input to support the proposed feedforward algorithm. A preliminary conditioned 0–10 V signal corresponding to 0–100% demand may be used if an approved source and interface are available. The preliminary conversion-accuracy target is ±2 percentage points. Known input values will be applied to verify scaling and electrical compatibility. This input is a bench-test representation of heating demand and is not claimed to be an actual boiler signal.

* 5 – Flow Rate Monitoring: The controller shall convert the selected flow sensor's output into GPM. The KEYENCE FD-Q series sensor is a proposed option, but its exact model, supported output mode, and calibration relationship will be confirmed before wiring and programming. A preliminary accuracy target of ±5% of the reference reading will be evaluated using a suitable reference method across the approved bench range.

* 6 – Temperature Response Time: Following a defined change in bench operating conditions, the outlet temperature should return to within ±4°F of setpoint within a preliminary target of 120 seconds and remain there for at least 30 seconds. The team will record recovery time for matched baseline and controlled runs. This is a preliminary project target, not a verified characteristic of the selected heat source.

* 7 – Electrical Power Reduction: At qualifying operating conditions, the controller shall aim for at least a 10% reduction in measured pump-and-drive real electrical input power compared with baseline operation under equivalent conditions. A suitable power instrument shall measure real input power in watts. Savings will be calculated as:
  
$$
\text{Power Savings (\%)} =
\frac{P_{\text{baseline}} - P_{\text{controlled}}}
{P_{\text{baseline}}} \times 100
$$

Power reduction will not count as a successful result if the controlled run violates the approved minimum flow, temperature, or safety limits.

* 8 – Controller Stability: After a defined demand change, the pump-speed command shall settle within ±5% of its final steady-state value within a preliminary target of 30 seconds, without repeated limit cycling. Command traces, flow measurements, and temperature data will be reviewed together to identify oscillations.

* 9 – Bench Compatibility and Safety: The controller shall operate with the selected bench pump, heat source, sensors, and power equipment without bypassing their required safety functions. Before the loop is energized, the complete setup shall be reviewed with the faculty supervisor. Bench verification shall include approved checks of maximum temperature, minimum flow, electrical isolation, and defined fault responses. Compatibility with commercial Lochinvar equipment will be evaluated separately if optional laboratory testing occurs.

* 10 – Operating Condition Testing and Model Validation: The team shall conduct at least three defined bench operating conditions representing low, medium, and high demand. The preliminary plan is five paired baseline and controlled runs at each condition, giving 15 paired comparisons. Measurements will be logged at a preliminary interval of no more than one second. The simulation will be run under matching conditions, and differences between predicted and measured flow, temperature, and response time will be reported. Mean percentage electrical savings, sample standard deviation, and a 95% confidence interval will be reported where supported by the data and assumptions.


#### Specification Traceability and Verification Summary
---

| Requirement | Primary verification | Evidence to report |
|---|---|---|
| 1. Temperature stability | Bench test | Calibrated temperature trace, maximum absolute deviation, standard deviation, 60-second window |
| 2. Minimum flow | Bench test and approved fault test | Measured GPM compared with documented bench minimum |
| 3. Pump speed control | Simulation, then bench test | Command trace, observed pump/flow response, verified interface limits |
| 4. Heating-demand input | Bench input test | Known input values, scaling error, electrical-interface check |
| 5. Flow monitoring | Sensor calibration and bench test | Sensor/reference comparison and conversion method |
| 6. Temperature response | Simulation and bench test | Time to recover within ±4°F, baseline comparison |
| 7. Power reduction | Repeated bench trials | Real input power, paired savings, confidence interval |
| 8. Controller stability | Simulation and bench test | Settling time, oscillation and command-limit traces |
| 9. Compatibility and safety | Pre-energization review and bench tests | Approved setup, isolation inspection, safe temperature/flow and fault-response checks |
| 10. Repeatability and validation | Repeated bench trials and model comparison | Trial datasets, uncertainty, simulation-versus-measurement error |


#### Temperature Sensor Accuracy and Calibration
--- 

Temperature measurements must be accurate enough to support the ±4°F stability requirement. A standard uncalibrated Type-K thermocouple or pipe-clamp probe may not be adequate on its own because its measurement tolerance, pipe-surface effects, and response delay can be large relative to the temperature band being evaluated. Thermocouples also require suitable cold-junction compensation.

The proposed bench budget includes two PT100 RTD probes and MAX31865 interface modules. The final probe construction, installation method, calibration, and electrical connections will be checked before use. The team will use a calibrated reference instrument, with a preliminary expanded uncertainty target no greater than ±1°F, to verify the measurement system. Sensor locations will be chosen to represent the water temperature as closely as the approved bench design allows, rather than relying on an uncorrected pipe-surface measurement.

Calibration results, sensor specifications, and measurement uncertainty will be recorded with the test data. Any change to the probe type or mounting arrangement will be documented so temperature results remain traceable.

#### Constraints
  
Electrical and Safety Constraints

* 1 – Electrical and Safety Constraints. The bench controller, pump, heat source, power supplies, and measurement equipment must operate within their rated voltage, current, and insulation limits. Electrical wiring and protection will be reviewed against applicable requirements of NFPA 70 and relevant laboratory procedures. Only qualified or institutionally authorized personnel may make changes that require electrical or plumbing expertise. Appropriate hazardous-energy controls, including lockout/tagout when applicable, will be followed before servicing. The bench shall be reviewed by the faculty supervisor before it is energized, and no test will bypass required overtemperature, flow, or electrical protections.

* 2 – Hydraulic and Thermal Constraints. The reservoir, tubing, fittings, valves, heat source, and pump must be suitable for the selected temperatures, pressures, and flow rates. The team will establish the safe minimum circulation flow and maximum temperature from the actual bench equipment and approved design. The controller will not command operation outside those limits. The loop will be checked for leaks, secure connections, and suitable protection from hot water and moving or energized equipment.

* 3 – Equipment and Interface Constraints. The final pump, heat source, flow sensor, RTDs, controller, and power-monitoring method must be confirmed before the wiring and software interfaces are finalized. The proposed heating-demand input must be a properly conditioned bench signal. The project will not depend on access to an existing commercial boiler. Any later integration with the Regent or other Lochinvar laboratory equipment will require a separate compatibility and safety review.

* 4 – Budget and Schedule Constraints. The project must remain within the approved capstone budget and schedule. The current bench budget identifies an estimated $191.62 in priced items, while the pump, heat source, and power-supply costs or availability remain unresolved. That figure is a partial estimate, not a complete project total. The bench must be assembled, reviewed, tested, and used to collect repeatable data during Capstone 2. Optional testing at Lochinvar's laboratory must not delay the required bench validation.
  
* 5 - Environmental and Economic Considerations. The team will compare measured electrical input power under matched operating conditions rather than assuming that lower speed always produces the predicted energy savings. Potential savings must be considered alongside the cost of additional controls, the energy used by the heating equipment, and the need to maintain safe circulation. The bench results will establish whether the control strategy works under the tested conditions; they will not, by themselves, establish full commercial product performance or certification.

## Survey of Existing Solutions

Several existing technologies and control methods are used to regulate water circulation in commercial and residential heating systems. These include fixed-speed pumps, multi-speed pumps, variable-speed pumps, and automatic control systems that adjust pump operation based on pressure, temperature, or water flow. Each approach has advantages and limitations depending on the application. Reviewing these technologies is important because the goal of this project is not simply to reduce pump speed, but to determine whether adjusting circulation based on operating conditions can reduce electrical power consumption while maintaining acceptable water flow and temperature performance.

Fixed-speed circulation pumps operate at a constant speed regardless of changes in system demand. These pumps are commonly used because they are relatively simple to install, operate, and maintain. However, a fixed-speed pump may consume more electrical energy than necessary when the system does not require its full circulation capacity. Multi-speed pumps provide additional flexibility by allowing the operator to select between several predetermined speed settings. Although this can reduce energy consumption under certain conditions, these pumps may still require manual adjustments and do not necessarily respond automatically to changing system conditions. Research published by Lawrence Berkeley National Laboratory discusses how variable-speed pumping can improve efficiency by matching pump operation more closely to system requirements [5].

A more advanced approach involves using variable-speed pumps and electronic motor controls. Variable-frequency drives (VFDs) adjust the electrical frequency supplied to compatible motors, allowing pump speed to change based on operating demand. Other pumps use electronically commutated motors (ECMs) with integrated electronic speed control. According to the U.S. Department of Energy, adjustable-speed pumping can reduce unnecessary electrical energy consumption by matching pump output to the requirements of the system rather than relying on constant-speed operation or throttling methods [10]. However, the actual energy savings depend on the pump, motor efficiency, hydraulic resistance, and required operating flow. Reducing speed does not guarantee that the system will maintain acceptable temperature performance or minimum circulation requirements.

One example of an existing variable-speed circulation pump is the Grundfos MAGNA3. This pump includes several control modes, such as constant pressure, proportional pressure, AUTOADAPT, and FLOWADAPT. Proportional-pressure control adjusts pump performance based on changes in system demand, while AUTOADAPT automatically adjusts the pump's operating characteristics. FLOWADAPT combines automatic adjustment with a flow-limiting function [11]. These features demonstrate how modern circulation pumps can respond to changing operating conditions without requiring continuous manual adjustments. Although the MAGNA3 is not the pump currently proposed for the team's bench-testing system, its control methods provide useful examples of how variable-speed operation can improve circulation efficiency.

Another existing solution is the Armstrong Design Envelope pump system. This technology combines variable-speed operation with integrated controls and sensorless methods for estimating system conditions. Rather than relying entirely on external sensors, certain Design Envelope pumps use information from the pump and motor to estimate operating requirements and adjust performance. The Armstrong Design Envelope 4300 is an example of this approach [12]. These systems demonstrate how pump controls can be integrated into larger heating and cooling applications. However, the proposed capstone project will investigate an external microcontroller-based control strategy that uses measured flow rate, water temperature, and a representative heating-demand input.

Temperature-based feedback control is another approach that can be used in water circulation systems. In this method, a temperature sensor measures the water temperature and compares it with a desired setpoint. The controller then adjusts an output based on the difference between the measured and desired temperatures. Proportional-integral-derivative (PID) control is one method used to reduce steady-state error and improve system response [8]. For this project, temperature feedback is important because reducing pump speed can change the amount of heat transferred to the circulating water. However, temperature feedback alone may not provide enough information to determine whether the pump is maintaining the required circulation flow. Therefore, the team has selected a control strategy that combines multiple operating measurements rather than depending on only one variable.

Computer simulation is also commonly used when developing and evaluating control systems. Simulation allows engineers to study the expected response of a system, compare different control settings, and identify potential problems before implementing the design on physical equipment. For this project, the team plans to use Dymola simulation software provided by Lochinvar to model the relationships between pump speed, water flow, heat transfer, and temperature response. The simulation will help establish preliminary controller settings and determine suitable operating conditions for the physical bench test. However, simulation results alone cannot confirm that the controller will perform correctly because the accuracy of the model depends on its assumptions and how closely it represents the actual equipment.

For this reason, the team will use a physical bench-testing system as the primary method of evaluating the proposed controller. The bench setup will include a small water circulation loop, variable-speed pump, heat source, flow and temperature sensors, and the actual microcontroller-based control system. The team will evaluate the controller under different operating conditions and compare its performance with baseline pump operation. Measurements will include electrical input power, circulation flow rate, inlet and outlet water temperatures, and system response time. Repeated trials will be conducted to determine whether the results are consistent and to evaluate measurement uncertainty.

An important part of the testing process will be comparing the physical bench measurements with the simulation predictions. By applying equivalent operating conditions to both systems, the team will be able to determine how accurately the simulation represents the actual circulation loop. Differences between the predicted and measured responses will be documented and used to improve the model and control algorithm. This approach allows simulation to support the development process while ensuring that the final performance conclusions are based on experimental measurements.

The proposed design differs from many existing commercial pump-control systems because it focuses on developing and testing a control algorithm for a specific water-heating application rather than relying entirely on a pump's built-in control features. The controller will use flow rate, temperature feedback, and a representative heating-demand input to determine when pump speed can be reduced. It will also enforce the selected bench equipment's minimum-flow and operating limits to prevent energy savings from being achieved at the expense of system safety or performance.

Overall, the existing solutions demonstrate that variable-speed pumping and automatic control methods can reduce unnecessary electrical energy consumption under suitable operating conditions. However, the team must still determine whether its selected control strategy provides measurable improvements while maintaining acceptable temperature stability, response time, and circulation flow. The physical bench test will provide the experimental data needed to evaluate these requirements. If time and resources permit near the end of Capstone 2, additional testing may be conducted on actual equipment at Lochinvar's laboratory. This would provide an opportunity to evaluate the controller under conditions more representative of its intended commercial application, but the bench test will remain the primary method of project validation.


## Measures of Success

The success of this project will be determined by how effectively the proposed variable-speed circulation pump controller reduces electrical power consumption while maintaining acceptable operating performance. The team will evaluate the controller using several measurable criteria, including temperature stability, water flow rate, electrical power consumption, response time, controller stability, and overall system reliability. These measurements will be collected during bench testing under different operating conditions and compared between constant-speed and variable-speed operation.

The following measures will be used to evaluate the success of the project:

* 1 – Temperature Stability: The system shall maintain the outlet water temperature within ±4 °F of the desired temperature setpoint. This will be verified by recording inlet and outlet water temperatures during testing at different pump speeds and flow rates. The measured outlet temperature will be compared with the desired setpoint to determine whether the system maintains acceptable temperature stability under the tested conditions.

* 2 – Minimum Flow Rate: The controller shall maintain the minimum flow rate established for the bench-testing setup. The flow sensor will measure the amount of water moving through the system in gallons per minute (GPM). The recorded flow rate will be compared with the established minimum operating target to verify that reducing pump speed does not result in insufficient circulation. If applicable, Lochinvar's specified minimum flow requirements will also be considered when evaluating the potential application to the Regent water heater.

* 3 – Electrical Power Consumption:  The controller shall demonstrate a measurable reduction in pump electrical power consumption when operating conditions allow the pump to run at a lower speed. Electrical power will be measured in watts during both constant speed baseline operation and variable speed operation. The results will be compared under equivalent test conditions to determine the percentage of power saved.

* 4 – System Response Time: The controller shall respond to changes in simulated or measured operating conditions by adjusting pump speed within an acceptable amount of time. Response time will be measured in seconds following changes in demand or temperature input. The recorded response will be evaluated to determine whether the controller adjusts pump operation appropriately without excessive delays.

* 5 – Controller Stability: The controller shall adjust pump speed without producing excessive oscillations or unstable operating conditions. During testing, the team will monitor pump speed, water flow rate, and outlet temperature to determine whether the controller responds smoothly to changing operating conditions. The controller will also be evaluated for repeated or unnecessary speed adjustments that could affect system performance.

* 6 – System Compatibility and Safety: The controller shall operate reliably with the selected bench-testing components without causing electrical, mechanical, or operational issues. This will be verified by monitoring the pump, sensors, and controller during testing and confirming that the system operates within the specified limits of the selected components. The design will also consider the requirements for potential future integration with Lochinvar equipment.

* 7 – Economic Feasibility: The team shall evaluate whether the potential energy savings justify the additional cost of implementing the variable speed controller. The estimated cost of the required hardware will be compared with the projected reduction in electrical energy consumption. This information will be used to estimate potential operating cost savings and determine whether the proposed control strategy could provide a practical benefit to Lochinvar.

To determine the percentage of electrical power savings, the following equation will be used:

$$
\text{Power Savings (\%)} =
\frac{P_{\text{base}} - P_{\text{controlled}}}
{P_{\text{base}}} \times 100
$$

where $P_{\text{base}}$ represents the electrical power consumed during original pump procedure and $(P_{\text{controlled}})$ represents the electrical power consumed while using the proposed variable speed controller.

The team will also compare results from different operating conditions to determine how changes in pump speed affect flow rate, temperature stability, and electrical power consumption. Research from the U.S. Department of Energy explains that variable speed pumping can reduce energy consumption when pump output is adjusted to match system requirements [10]. However, the actual savings associated with the proposed control strategy will be determined through bench testing.

The project will be considered successful if the controller demonstrates a reduction in pump electrical power consumption while maintaining the established minimum flow rate, keeping outlet water temperature within ±4 °F of the desired value, and operating reliably under the tested conditions. The testing results will provide Lochinvar with engineering data that can be used to evaluate the potential benefits and feasibility of variable-speed circulation control for the Regent Commercial Instantaneous Water Heater.


## Resources


### Preliminary Budget


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


The preliminary budget provides an initial estimate of the equipment and materials anticipated for constructing the bench-testing setup and evaluating the variable-speed circulation pump. Costs and component selections may be revised as the design is further developed mentioned later in the document. Several major components, including the KEYENCE FD-Q50C clamp-on flow sensor, microcontroller, and Dymola simulation software, are expected to be provided by Lochinvar or Tennessee Tech at no additional cost. The remaining equipment includes a water reservoir, flexible tubing, plumbing fittings, hose clamps, valves, a mounting platform, wiring, and sensor mounts. Two PT100 RTD temperature probes and MAX31865 interface modules will also be used to monitor the water temperature at the inlet and outlet of the system. A PZEM-004T AC power monitor will measure the pump's electrical consumption during testing.

The current estimated cost of the project is **$191.62**, based on the items with confirmed prices. The final cost may change depending on the availability of additional equipment and materials from Tennessee Tech and Lochinvar. In particular, the heating equipment and DC power supply will be investigated for availability through Tennessee Tech, while Lochinvar may be able to provide the Grundfos UPMS 15-78 130 AR circulation pump for the bench setup. These potential contributions could reduce the overall project expenses while still providing the equipment needed to conduct physical testing and compare experimental results with the simulation.

### Personnel

* Jocelyn Smith: C/C++, Assembly, Python, TypeScript, SQL, MATLAB, VHDL, Circuit Analysis, Control System Analysis, LT Spice
* Danielle Wolford: C/C++, Assembly, Circuit Analysis, PLC Coding, HMI Formatting, Control System Analysis, LT Spice, KiCad
* Kendall Arnold: C/C++, Assembly, AUTOCAD, Controls Systems, Circuit Analysis, LT Spice, KiCad, Technical Documentation
* Skyler Raines: C/C++, Assembly, Circuit Analysis, AUTOCAD, Revit, PLC, Ladder Logic, Control Systems, Troubleshooting

The capstone team consists of Jocelyn Smith, Danielle Wolford, Kendall Arnold, and Skyler Raines. The project includes programming, control systems, circuit analysis, hardware integration, simulation, and experimental testing. Each team member will contribute to the overall design, with primary responsibilities assigned to the individual subsystems.

Jocelyn has experience with C/C++, Assembly, Python, MATLAB, circuit analysis, and control system analysis. These skills are relevant to developing the microcontroller control logic, supporting simulation work, and organizing recorded measurements. Danielle has experience with C/C++, circuit analysis, PLC programming, control system analysis, LTspice, and KiCad, which will be useful for the pump interface and hydraulic design. Kendall has experience with C/C++, AutoCAD, control systems, circuit analysis, and technical documentation, supporting test planning and performance evaluation. Skyler has experience with electrical hardware, troubleshooting, PLCs, and control systems, which will help with the sensor integration and acquisition hardware.

The team will need additional experience with the selected pump interface, the physical water loop, temperature measurement and calibration, and Dymola simulation. The simulation will be used to develop the control strategy and select the initial test conditions, but the team will also need to learn how to compare its predictions with real bench measurements. Testing will involve heated water and electrical equipment, so the team will work with the faculty supervisor and authorized laboratory personnel to review the setup before energizing it.

Dr. Storm will provide capstone supervision, project feedback, and oversight of the proposed test plan. Dr. Elfouly can provide technical guidance on the microcontroller, sensor interfaces, and digital control implementation. Lochinvar's engineers will remain important contacts for sponsor requirements, pump compatibility, and any possible final testing at their laboratory. The team will document unresolved equipment details rather than assuming that an interface or operating limit has already been approved.

### Timeline

<p align="center">
<img width="1487" height="597" alt="image" src="https://github.com/user-attachments/assets/f5531d7d-e73e-413f-943a-abcbc1e83626" />
</p>


## Specific Implications

If the project is successful, Lochinvar will have experimental evidence showing whether a variable-speed circulation pump controller can reduce electrical input power while maintaining acceptable water flow and temperature performance. The goal is not simply to make the pump run more slowly. The controller must respond to changes in demand without allowing the water loop to operate below its safe minimum flow or outside its approved temperature limits.

The physical bench test will make it possible to measure these effects under repeatable conditions. By comparing baseline and controlled operation, the team can identify when a lower pump-speed command provides a meaningful power reduction and when the controller needs to maintain a higher flow rate. Repeated tests will help show whether the results are consistent rather than depending on one successful run. Comparing the bench measurements with simulation predictions will also help the team understand which parts of the model need improvement.

The project could have economic and environmental benefits if reduced pump electrical consumption can be achieved without adding unacceptable cost or complexity. However, the measured savings will apply first to the selected bench equipment and test conditions. The team will avoid presenting bench results as proof that the same percentage savings will occur in every commercial water heater.

The main value of the project is a tested control strategy, a documented bench-testing method, and a set of measured results that Lochinvar can use to evaluate future development. If testing at Lochinvar's laboratory becomes possible near the end of Capstone 2, it may provide additional evidence about how the design behaves with actual commercial equipment. The project will still be complete if that optional testing cannot be arranged.


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
[18] Grundfos, Grundfos E-Pumps Product Guide, “Affinity Equations,” p. 3. [Online]. Available: https://d1pkofokfruj4.cloudfront.net/media/upload/resource/m/Grundfos-E-Pumps-Product-Guide.pdf. [Accessed: Nov. 16, 2026].

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

The objective of this project is to develop and evaluate a control strategy that adjusts circulation pump speed based on real-time temperature and demand measurements while allowing the boiler's existing heating controls to operate independently. The proposed strategy will use components such as a variable-speed pump, flow sensor, and inlet and outlet temperature sensors to monitor system conditions and determine when adjustments are needed. A microcontroller will process these measurements and adjust the pump speed according to the developed control algorithm. A physical bench-testing setup will be constructed to demonstrate pump control, monitor operating conditions, and measure the electrical power consumed by the pump at different speeds. These measurements will allow the team to compare power consumption under variable-speed operation against constant-speed operation and evaluate the potential energy savings associated with reducing pump speed. Engineering calculations and computer simulations will also be used to examine the relationship between flow rate, temperature rise, and heat transfer under different operating conditions. The collected data will help evaluate the effectiveness of the control strategy and identify operating conditions that balance reduced electrical power consumption with adequate flow and temperature performance. Ultimately, the goal is to develop an algorithm that demonstrates the potential to improve the energy efficiency of the Regent Commercial Tankless Water Heater without compromising its performance or reliability.

## Restating the Fully Formulated Problem

The objective of this project is to design, implement, and evaluate a variable-speed circulation pump controller that can reduce unnecessary electrical power consumption while maintaining safe water flow and stable temperature performance. The Lochinvar Regent Commercial Instantaneous Water Heater remains the intended future application, but the controller will be developed and evaluated first using a dedicated physical bench-testing system.

The bench setup will include a variable-speed pump, a small water circulation loop, a heat source, flow and temperature sensors, and the team's actual microcontroller-based controller. It will provide a controlled environment for changing flow and heating-demand conditions, recording system responses, and evaluating the effect of pump-speed adjustments. The physical bench test is required and will provide the primary experimental evidence for the project.

A simulation model will be developed before testing to represent the expected relationships between pump operation, water flow, heat transfer, and outlet temperature. The simulation will help establish preliminary controller settings and choose bench-test conditions. After measurements have been collected, the simulation will be run under matching conditions and compared with the physical response. The team will report the differences and use the results to improve the model and controller.

The design shall meet the following requirements:

1. Pump speed control: The controller shall issue variable-speed commands through the selected pump's supported interface and remain within its documented operating limits.
  
2. Operating measurements: The system shall acquire flow rate, inlet and outlet water temperatures, applied heating-demand input, and available pump operating information at a preliminary logging interval of no more than one second.
   
3. Temperature stability: The system shall aim to maintain outlet temperature within ±4°F of the selected setpoint during a defined 60-second steady-state window, using a calibrated reference measurement.
   
4. Minimum flow: The controller shall maintain at least the approved minimum circulation flow for the actual bench equipment whenever heated circulation is required. The numerical limit will be established before testing.
   
5. Response time: After a defined operating change, the controller shall aim to return the outlet temperature to within ±4°F of setpoint within 120 seconds and remain there for at least 30 seconds.

6. Electrical power reduction: The controller shall aim for at least a 10% reduction in measured pump-and-drive real electrical input power compared with a matched baseline, provided all safety and performance limits remain satisfied.
   
7. Controller stability: The pump-speed command shall aim to settle within ±5% of its final value within 30 seconds after a defined change, without repeated limit cycling.

8. Physical validation: The team shall complete a bench test using the actual controller, sensors, pump, heat source, and circulation loop. Simulation alone will not satisfy this requirement.

9. Repeated testing and uncertainty: The preliminary test plan shall include five paired baseline and controlled runs at each of three operating conditions. The results shall include variability, a 95% confidence interval for power savings when statistically supported, and defined temperature-stability measures.
    
10. Model validation: Predicted and measured responses shall be compared under equivalent conditions, with model error reported for selected flow, temperature, and response-time measurements.

11. Safety: The bench setup shall be reviewed with the faculty supervisor before energizing. Approved testing shall verify temperature limits, minimum flow, electrical isolation, and fault responses.

12. Future application: Testing on actual Lochinvar equipment may be pursued near the end of Capstone 2 if access and approval permit, but is not required to complete the project.

In summary, The project will be judged primarily by the quality of the bench implementation, repeatability of the measurements, safe operation, and evidence that the controller meets the defined performance targets. The team will clearly distinguish results measured on the bench from any predictions about future use in the Regent.

## Engineering Principles, Mathematical Models, and Verification Tools (C1)

The proposed Variable Speed Circulation Pump Controller will be developed using engineering principles involving fluid mechanics, heat transfer, electrical power, and feedback control. These principles will be used to predict how changes in pump speed affect water circulation, temperature response, and electrical energy consumption.

The initial calculations will support development of the Dymola simulation model and selection of preliminary controller settings. The physical bench will then be used to evaluate these predictions using the actual STM32L476RG controller, variable speed pump, electric heat source, flow sensor, and temperature sensors. Simulation results will be compared with experimental measurements to determine how accurately the model represents the physical system.

The Grundfos UPMS 15-78 130 AR remains a candidate pump. The manufacturer published specifications for the UPMS 15-78 130 pump family will be used as preliminary reference information until the exact model, control interface, and operating limits are confirmed.

### Manufacturer Pump Specifications
---

The Grundfos UPMS technical data booklet provides the following specifications for the UPMS 15-78 130 pump family [15].

| Parameter | Manufacturer-Published Value |
|---|---|
| Nominal electrical supply | 115 V AC, 60 Hz |
| Minimum electrical input power | 8.4 W |
| Maximum electrical input power | 68 W |
| Minimum listed current | 0.18 A |
| Maximum listed current | 1.25 A |
| Maximum system pressure | 174 psi |
| Liquid temperature range | 36–230°F |
| Installation length | 130 mm |


These values describe the published pump family configuration and are not confirmation of the exact AR variant proposed for the bench. The team will verify the installed pump's nameplate, supported speed control method, hydraulic performance, and applicable operating limits before finalizing the electrical and mechanical design.

### Electrical Input Power Calculations
---

Electrical power consumption is one of the primary measurements used to evaluate the proposed controller. The selected pump family's published maximum electrical input power is:

$$
P_{\max}=68\text{ W}
$$

The published minimum electrical input power is:

$$
P_{\min}=8.4\text{ W}
$$

The difference between the published operating extremes is:

$$
\Delta P=P_{\max}-P_{\min}
$$

$$
\Delta P=68-8.4=59.6\text{ W}
$$

The percentage difference relative to the published maximum electrical input power is:

$$
R=\frac{P_{\max}-P_{\min}}{P_{\max}}\times100
$$

$$
R=\frac{68-8.4}{68}\times100=87.65\%
$$

This calculation identifies the difference between the manufacturer's published electrical input-power limits. It does not represent the expected energy savings of the proposed controller because the minimum and maximum operating points may not provide equivalent flow, temperature performance, or heating conditions.

The project's preliminary target is a reduction of at least 10% in measured pump-and-drive real electrical input power while maintaining approved performance and safety requirements.

Using the manufacturer's published maximum power of 68 W as an illustrative baseline:

$$
P_{\text{target}}=P_{\text{baseline}}(1-0.10)
$$

$$
P_{\text{target}}=68(0.90)=61.2\text{ W}
$$

Therefore, a reduction from 68 W to 61.2 W would correspond to the project's 10% power-reduction target for that illustrative baseline.

During physical testing, the team will use actual measured electrical input power rather than assuming the pump operates at the published maximum. The measured percentage savings will be calculated as:

$$
S=\frac{P_{\text{baseline}}-P_{\text{controlled}}}{P_{\text{baseline}}}\times100\%
$$

For AC-powered equipment, multiplying RMS voltage by RMS current does not necessarily provide real power because of power factor and possible waveform distortion. Therefore, an appropriately rated instrument capable of measuring real electrical input power will be used.

### Pump Affinity Laws

The pump affinity laws describe the theoretical relationships between rotational speed, volumetric flow rate, pump head, and mechanical power for a centrifugal pump operating under comparable conditions [6], [15].

The relationship between flow rate and pump speed is:

$$
\frac{Q_2}{Q_1}=\frac{N_2}{N_1}
$$

The relationship between pump head and speed is:

$$
\frac{H_2}{H_1}=\left(\frac{N_2}{N_1}\right)^2
$$

The relationship between mechanical pump power and speed is:

$$
\frac{P_2}{P_1}=\left(\frac{N_2}{N_1}\right)^3
$$

where:

- **Q** represents volumetric flow rate.
- **H** represents pump head.
- **P** represents mechanical pump power.
- **N** represents pump rotational speed.
- Subscripts 1 and 2 represent the initial and adjusted operating conditions.

For an illustrative reduction to 80% of the original rotational speed:

$$
\frac{N_2}{N_1}=0.80
$$

The theoretical flow ratio is:

$$
\frac{Q_2}{Q_1}=0.80
$$

The theoretical head ratio is:

$$
\frac{H_2}{H_1}=(0.80)^2=0.64
$$

The theoretical mechanical power ratio is:

$$
\frac{P_2}{P_1}=(0.80)^3=0.512
$$

The corresponding ideal mechanical power reduction is:

$$
(1-0.512)\times100=48.8\%
$$

This example demonstrates the theoretical relationship between pump speed and mechanical power. It does not establish that the bench pump will achieve a 48.8% reduction in measured electrical input power. Actual results will depend on the pump's operating characteristics, motor efficiency, electronic drive losses, and hydraulic resistance of the water loop.

The team will use these relationships to develop preliminary predictions in Dymola and compare them with actual bench measurements. Manufacturer pump curves and the verified supported operating range will be used to determine whether the selected speed commands are practical.

### Heat-Transfer Model

Heat transfer is an important consideration because changing circulation flow can affect the temperature difference between the inlet and outlet of the heat source.

The rate of thermal energy transferred to circulating water can be represented by:

$$
\dot{Q}_h=\dot{m}c_p(T_{\text{out}}-T_{\text{in}})
$$

where:

- **Q̇ₕ** is the heat-transfer rate in watts.
- **ṁ** is the mass flow rate in kg/s.
- **cₚ** is the specific heat capacity of water in J/(kg·K).
- **T_out** is the outlet-water temperature.
- **T_in** is the inlet-water temperature.

Mass flow rate can be determined from volumetric flow rate using:

$$
\dot{m}=\rho\dot{V}
$$

where:

- **ρ** represents water density in kg/m³.
- **V̇** represents volumetric flow rate in m³/s.

For preliminary calculations involving liquid water, an approximate U.S. customary relationship is:

$$
\dot{Q}_h\approx500(\text{GPM})(\Delta T)
$$

where heat-transfer rate is expressed in Btu/h and temperature difference is expressed in °F.

Rearranging the equation gives:

$$
\Delta T=\frac{\dot{Q}_h}{500(\text{GPM})}
$$

This relationship demonstrates that, for approximately constant heat transfer to the water, decreasing the flow rate increases the temperature rise across the heat source.

### Preliminary Bench Heat-Transfer Calculation

The exact heat source has not yet been selected. Therefore, the following example uses an illustrative thermal input of 500 W to demonstrate the calculation method. This value is not a confirmed heater rating, measured heat-transfer rate, or approved operating condition.

Converting 500 W to Btu/h:

$$
\dot{Q}_h=500(3.412142)
$$

$$
\dot{Q}_h\approx1706.1\text{ Btu/h}
$$

At an illustrative flow rate of 1.0 GPM:

$$
\Delta T=\frac{1706.1}{500(1.0)}
$$

$$
\Delta T\approx3.41^\circ\text{F}
$$

At an illustrative reduced flow rate of 0.5 GPM:

$$
\Delta T=\frac{1706.1}{500(0.5)}
$$

$$
\Delta T\approx6.82^\circ\text{F}
$$

| Illustrative Condition | Flow Rate | Assumed Heat Transfer | Calculated Temperature Rise |
|---|---|---|---|
| Condition 1 | 1.0 GPM | 500 W | 3.41°F |
| Condition 2 | 0.5 GPM | 500 W | 6.82°F |

These calculations demonstrate that reducing flow from 1.0 GPM to 0.5 GPM doubles the theoretical temperature rise across the heat source when the heat-transfer rate remains constant.

The calculations do not establish that either flow rate is safe for the selected bench equipment. The actual minimum flow, heat-source rating, water-temperature limits, and achievable operating conditions will be determined after the equipment has been selected.

In the physical bench, heat losses, reservoir temperature changes, heater control behavior, and the hydraulic arrangement may cause measured temperatures to differ from these simplified predictions.

### Reservoir Thermal Response

Because the proposed bench may use a reservoir and recirculating water loop, the team must also consider how the overall water temperature changes over time.

A simplified energy balance for a well-mixed reservoir is:

$$
m_wc_p\frac{dT}{dt}=P_{\text{heat,water}}-\dot{Q}_{\text{loss}}
$$

where:

- **m_w** represents the mass of water in the reservoir.
- **cₚ** represents the specific heat capacity of water.
- **T** represents the reservoir-water temperature.
- **P_heat,water** represents thermal power delivered to the water.
- **Q̇_loss** represents the heat-transfer rate from the water to the surroundings.

This relationship shows that reservoir temperature will increase when the heat delivered to the water exceeds heat losses. In a continuously heated closed loop, pump-speed adjustments alone may not be sufficient to maintain a constant outlet-water temperature.

The selected bench arrangement must therefore provide a suitable method for establishing repeatable thermal operating conditions. Depending on the final design, this may involve controlled heater operation, a suitable heat-removal mechanism, or a defined transient testing procedure. The team will document the actual arrangement and its limitations before interpreting temperature-control results.

### Preliminary Feedback Control Model

The controller will use measured flow rate, a representative heating-demand input, and temperature feedback to determine the pump-speed command.

The feedforward component will provide an initial pump-speed estimate based on the measured operating conditions. Temperature feedback will then be used to adjust the command when necessary.

A preliminary proportional-integral control relationship is:

$$
u_{\text{raw}}(t)=u_{\text{ff}}(q(t),f(t))+K_pe_T(t)+K_i\int_0^t e_T(\tau)\,d\tau
$$

The command will be limited to the permitted pump-control range:

$$
u_{\text{cmd}}(t)=\operatorname{clip}(u_{\text{raw}}(t),u_{\min},u_{\max})
$$

where:

- **u_cmd** represents the commanded pump operating level.
- **u_ff** represents the preliminary feedforward command.
- **q(t)** represents the measured flow rate.
- **f(t)** represents the representative heating-demand input.
- **e_T(t)** represents the temperature error.
- **Kₚ** and **Kᵢ** represent proportional and integral gains.
- **u_min** and **u_max** represent approved pump-command limits.

The temperature error and appropriate direction of the feedback correction will be established from the actual thermal response of the selected bench. The team will not assume that increasing pump speed always increases outlet-water temperature.

The controller will also incorporate command limits, fault detection, and appropriate measures to reduce oscillations. The final control gains and command mapping will be developed through simulation and adjusted using measured bench results.

### Dymola Simulation and Physical Bench Validation

Dymola will be used to model the circulation loop and predict how changes in pump operation affect flow rate, heat transfer, and temperature response. The model will include the selected pump characteristics, hydraulic resistance, heat source behavior, and relevant thermal properties to the extent supported by available equipment information.

The simulation will be developed before physical testing and used to select preliminary controller settings and experimental operating conditions.

The physical bench will then use the actual STM32L476RG controller to acquire measurements and command the selected pump. The planned measurement system includes the KEYENCE flow sensor, PT100 RTD temperature sensors with MAX31865 SPI interface modules, and a suitable real power measurement instrument.

The preliminary testing plan includes three operating conditions representing low, medium, and high demand. Five paired baseline and controlled runs will be conducted at each condition, resulting in 15 paired comparisons.

The team will record:

- Water flow rate in GPM.
- Inlet and outlet water temperatures.
- Pump-speed command and available operating feedback.
- Applied representative heating-demand input.
- Measured pump-and-drive real electrical input power.
- Time and operating condition for each measurement.
- Controller faults and abnormal operating events.

Measurements will be recorded at a preliminary interval of no more than one second.

Simulation predictions will be compared with bench measurements under equivalent operating conditions. The absolute prediction error for a measured quantity can be calculated as:

$$
e_x=|x_{\text{simulated}}-x_{\text{measured}}|
$$

Where an appropriate nonzero reference exists, percentage error may be calculated as:

$$
e_{x,\%}=\frac{|x_{\text{simulated}}-x_{\text{measured}}|}{|x_{\text{measured}}|}\times100\%
$$

The team will report differences in flow rate, temperature response, and relevant transient behavior. Measured electrical-power savings will be evaluated using matched baseline and controlled runs, including variability and a 95% confidence interval when supported by the experimental data.

The final evaluation will determine whether the controller can achieve the preliminary target of at least 10% pump electrical-input-power reduction while maintaining approved flow, temperature, stability, and safety requirements.

### Engineering Verification Summary

The mathematical models will support the initial design, but experimental measurements will determine whether the proposed controller meets its requirements.

| Engineering Principle | Design Application | Verification Method |
|---|---|---|
| Pump affinity laws | Estimate changes in flow, head, and mechanical power with pump speed. | Compare predictions with manufacturer curves and bench measurements. |
| Electrical power | Evaluate pump and drive input power reduction. | Measure real electrical input power during matched trials. |
| Heat transfer equation | Estimate temperature rise across the bench heat source. | Compare calculated and measured inlet/outlet temperature differences. |
| Reservoir energy balance | Evaluate temperature drift and thermal operating conditions. | Record reservoir and loop temperature behavior during testing. |
| Feedback control | Calculate pump speed commands from measured conditions. | Review STM32 command traces, response time, and stability. |
| Dymola simulation | Select initial controller settings and test conditions. | Compare simulation predictions with physical bench data. |
| Statistical analysis | Evaluate repeatability and uncertainty of electrical savings. | Analyze paired trials, variation, and confidence intervals. |

The final design will distinguish theoretical predictions, manufacturer specifications, preliminary targets, and experimental results. This approach will allow the team to evaluate the proposed control strategy without assuming that ideal pump relationships or simulation predictions will automatically be achieved on the physical bench.

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

The proposed system will adjust the speed of a circulation pump according to the conditions measured in a small water loop. Instead of running at one fixed speed, the controller will use flow, temperature, and a representative heating-demand input to decide whether the pump can operate at a lower setting. The goal is to reduce electrical input power while maintaining safe circulation and acceptable temperature behavior.

The system will be developed in simulation first and then implemented using a physical bench setup. The simulation will provide an initial understanding of the system and help the team choose controller settings. The bench will include the actual microcontroller, sensors, variable-speed pump, heat source, reservoir, and plumbing. Repeated bench trials will provide the measured data needed to evaluate the controller and validate the simulation.

* 1 –  Sensor and Data Acquisition: Measures flow and temperature and provides conditioned operating inputs to the controller.
 
* 2 – Microcontroller and Control Logic: Calculates pump speed commands, enforces operating limits, and handles detected faults.

* 3 – Pump, Motor Control, and Hydraulic System: Includes the pump interface, water loop, hydraulic model, and minimum-flow protection.
  
* 4 – Monitoring, Performance Evaluation, and Bench Testing: Plans and operates the approved bench experiment and evaluates the controller's performance.

* 5 – Data Logging and Simulation: Develops the model, records and stores experimental measurements, compares predictions with bench data, and documents model error.

The main information path begins with measurements from Subsystem 1. Subsystem 2 processes these measurements and sends a command to the compatible pump interface in Subsystem 3. The physical loop responds, producing new flow and temperature conditions. Subsystem 4 manages the test conditions and evaluates the results. Subsystem 5 records the measurements and uses them to check and refine the simulation.

The bench experiment is required for project completion. Testing on actual Lochinvar equipment at the sponsor's laboratory may be pursued near the end of Capstone 2 if the opportunity becomes available, but the team will not depend on that testing to meet its primary objectives.

#### Preliminary Control Design and Tuning Plan
--- 

The controller will use a feedforward estimate based on measured flow and a representative heating-demand input, followed by a temperature-feedback correction. A preliminary PI-based expression is:

$$
u_{\mathrm{cmd}}(t) = \min\left(
u_{\max},
\max\left(
u_{\min},
u_{\mathrm{ff}}(q(t), f(t)) + K_p e_T(t) + K_i \int e_T(t)\,dt
\right)
\right)
$$

The feedforward map and control gains will first be developed in simulation. The direction of the temperature-feedback correction will be checked against the actual bench response because changing pump flow can affect outlet temperature differently depending on the heat source and loop arrangement. The controller will use a deadband, a rate limit, and anti-windup logic to reduce unnecessary oscillations and prevent the integral term from continuing to grow when the command reaches a limit.

The final minimum and maximum commands will be based on the installed pump and the safe flow range of the bench. Simulation will be used to select initial settings, and repeated bench measurements will be used to adjust them. The team will document changes to the control gains, settling behavior, temperature response, and flow protection. Any fault response will be defined and approved before the heated loop is energized.

#### Preliminary Statistical Verification Plan
--- 

The team plans five paired baseline and controlled runs at each of three defined bench operating conditions: low, medium, and high demand. This gives a preliminary total of 15 paired comparisons. Conditions will be matched as closely as possible within each pair, and test order, initial conditions, and any changes in equipment settings will be documented. For each pair, percentage electrical-power savings will be calculated as:

$$
S_i = 100 \frac{P_{\mathrm{baseline},i} - P_{\mathrm{controlled},i}}{P_{\mathrm{baseline},i}}.
$$

The results will include the mean saving, sample standard deviation, sample size, and a 95% confidence interval where the data and statistical assumptions support one. Temperature stability will be reported as maximum absolute deviation from setpoint and standard deviation over a preliminary 60-second steady-state window after settling. The team will also record recovery time following a defined operating change. Aborted trials, faults, and results that do not meet the flow or temperature requirements will not be hidden. Power savings will be considered successful only when the controller also meets the approved safety and performance limits. Measurement uncertainty and the small sample size will be discussed when interpreting the results.


#### Scope Changes 
--- 

The project testing strategy has changed from depending on existing commercial heating equipment to building a dedicated physical bench-testing loop. This change will give the team more control over test conditions and provide a reliable way to collect experimental data during Capstone 2. The bench will include a variable-speed pump, a heat source, the actual controller, and the sensors needed to measure system performance.

Simulation remains an important development tool, but it will not replace physical testing. It will be used to develop the control algorithm, choose preliminary operating conditions, and predict the system response. The bench will provide measured results, and those results will be compared with the simulation under matching conditions to determine model error and guide improvements.

The original pump control and hydraulic subsystems have been combined into one subsystem, reducing the design from six subsystems to five. Bench testing has been added to the monitoring and performance subsystem. Data recording and storage will be owned by the Data Logging and Simulation Subsystem so those responsibilities do not overlap with test operation and performance evaluation.

Testing at Lochinvar's laboratory may be considered near the end of Capstone 2 if time, access, and approval permit. It is an optional stretch goal and will not be required for successful completion of the project.

###

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

The Sensor and Data Acquisition Subsystem will provide real-time measurements of the water flow rate, inlet and outlet water temperatures, and heating demand within the water circulation loop. The subsystem will use the proposed KEYENCE FD-Q50C flow sensor to measure water flow and two PT100 RTD temperature sensors to monitor inlet and outlet water temperatures. A representative heating-demand signal, potentially using a 0–10 V analog input, will also be included to provide information about the current heating requirements of the system.

The flow sensor will provide an electrical output that corresponds to the measured water flow rate. Depending on the verified configuration of the selected KEYENCE sensor, this output may be a digital pulse-frequency signal or an analog signal. The PT100 temperature sensors will change resistance according to the measured water temperature. These resistance measurements will be converted into digital information using MAX31865 interface modules, which will communicate with the STM32 microcontroller through SPI communication. The proposed 0–10 V heating-demand input will be conditioned and isolated as required by the approved interface design to ensure compatibility with the microcontroller's supported analog input range.

During operation, the subsystem will continuously acquire measurements from the sensors and provide the signals required by the Microcontroller and Control Logic Subsystem. The microcontroller will process these measurements to determine the current operating conditions and calculate the appropriate pump speed command. The subsystem will also support the detection of sensor failures, invalid measurements, and communication errors. These conditions will be reported to the Microcontroller and Control Logic Subsystem so that the appropriate fault response can be initiated.

The final sensor configurations, electrical connections, signal conditioning requirements, and microcontroller interfaces will be verified and documented during Detailed Design. The initial implementation will focus on the approved physical bench-testing system, while communication with actual Lochinvar boiler equipment may be evaluated during future testing if the required interfaces and approvals are available.

**Inputs:**

* Water flow measurements from the KEYENCE FD-Q50C flow sensor installed on the circulation loop.
* Inlet water temperature measurements from a PT100 RTD temperature sensor.
* Outlet water temperature measurements from a second PT100 RTD temperature sensor.
* A representative heating-demand signal, potentially using a conditioned 0–10 V analog input.
* Sensor calibration information and operating limits established from manufacturer specifications and bench-testing requirements.

**Outputs:**

* Water flow measurement signals transmitted to the Microcontroller and Control Logic Subsystem through the verified flow-sensor interface.
* Inlet and outlet temperature measurements transmitted through MAX31865 modules using SPI communication.
* Conditioned heating-demand information transmitted to the microcontroller through an analog input.
* Sensor status and fault information used by the Microcontroller and Control Logic Subsystem to identify invalid measurements or sensor failures.
* Measurement information made available through the microcontroller to the Monitoring, Performance Evaluation, and Bench Testing Subsystem and the Data Logging and Simulation Subsystem.

**Interfaces and Procedure:**

The subsystem will collect water flow, inlet temperature, and outlet temperature measurements from sensors installed on the circulation loop. The KEYENCE FD-Q50C flow sensor will provide an electrical signal corresponding to the measured flow rate. The two PT100 RTD sensors will connect to MAX31865 modules, which will transmit digital temperature measurements to the STM32 microcontroller through SPI communication.

A representative heating-demand signal, potentially using 0–10 V, will be conditioned to a voltage compatible with the microcontroller's analog input. During bench testing, this signal may be simulated rather than obtained directly from a Lochinvar boiler. The exact flow-sensor configuration and electrical interfaces will be confirmed during Detailed Design.

During operation, the subsystem will continuously acquire and condition sensor signals for processing by the microcontroller. The measurements will be converted into engineering units such as GPM, °F, and heating-demand percentage. Invalid readings or communication failures will be identified and reported to the Microcontroller and Control Logic Subsystem for the approved fault response. Valid measurements will support pump control, system monitoring, and experimental data logging.
  
**Functional Flowchart:**
<p align="center">
<img width="534" height="178" alt="image" src="https://github.com/user-attachments/assets/c16677ed-42c8-48d4-8e17-1cb589b570aa" />
</p>

**Specifications**

1) This subsystem shall read data from the temperature sensor.

2)	This subsystem shall read data from the flow meter.
   
3)	This subsystem shall update all data every how many seconds we choose.
   
4)	This subsystem shall send a fault error if there is any out-of-bounds data or if there is a broken connection.
   
5)	This subsystem shall send data to the microcontroller.




### 2) Microcontroller and Control Logic Subsystem

**Overview:**

The Microcontroller and Control Logic Subsystem will process the operating measurements collected from the Sensor and Data Acquisition Subsystem and determine the appropriate circulation pump speed command. The proposed controller will use the STM32 Nucleo-L476RG development board and a control algorithm that combines water flow rate, a representative heating-demand input, and outlet-temperature feedback.

The controller will initially estimate the required pump operating level from flow rate and heating demand. It will then use temperature feedback to evaluate whether additional adjustments are necessary. The controller will enforce the minimum circulation flow requirement and the verified pump command limits so that reducing electrical consumption does not compromise safe operation.

The physical bench will use a representative heating demand signal rather than requiring a connection to an operating Lochinvar boiler. The exact output configuration of the KEYENCE flow sensor and the control interface of the selected Grundfos pump must be verified before the electrical connections are finalized.

The subsystem will also detect invalid measurements, communication failures, and operating conditions outside approved limits. When a fault occurs, the controller will initiate the defined response without bypassing independent equipment protection. Operating measurements, calculated commands, and controller status will be transmitted to the Data Logging and Simulation Subsystem for recording and evaluation.

**Functional Description:**

1. **Controller Initialization:** Initialize the STM32, communication peripherals, sensor interfaces, pump-command output, and controller operating parameters.

2. **Measurement Acquisition:** Receive water flow rate, inlet temperature, outlet temperature, and representative heating-demand information through the interfaces established by Subsystem 1.

3. **Measurement Validation:** Check incoming measurements for invalid values, communication failures, and conditions outside the approved operating range.

4. **Feedforward Control:** Calculate an initial pump operating command using measured flow rate and the representative heating-demand input.

5. **Temperature Feedback:** Compare measured outlet temperature with the selected setpoint and determine whether a correction to the pump command is appropriate.

6. **Operating-Limit Enforcement:** Restrict the calculated command to the verified pump-control range and enforce the approved minimum circulation-flow requirement.

7. **Pump Command Transmission:** Send the final command to Subsystem 3 through the manufacturer-supported pump-control interface.

8. **Fault Handling:** Detect abnormal conditions and initiate the approved fault response, including a safe heater response where an authorized interface is provided.

9. **Data Communication:** Transmit measurements, operating commands, controller states, and fault information to Subsystem 5 for recording.

**Inputs:**

* Water flow rate from Subsystem 1, expressed in GPM after conversion.
* Inlet and outlet water temperatures from PT100 RTDs through MAX31865 SPI interface modules.
* Representative heating demand input, preliminarily 0–10 V before appropriate signal conditioning.
* Selected outlet temperature setpoint and controller operating parameters.
* Approved minimum circulation flow and pump command limits.
* Available pump status or fault feedback from Subsystem 3, if supported by the selected equipment.

**Outputs:**

* Pump speed command to Subsystem 3 through the verified manufacturer supported control interface.
* Controller operating state, command value, and measurement information to Subsystem 5.
* Fault codes and diagnostic status for monitoring and recording.
* Approved heater shutdown or inhibit request, if the final bench includes a suitable authorized interface.

**Interfaces Between Subsystems:**

| Connection | Direction | Signal Type | Purpose |
|---|---|---|---|
| Subsystem 1: Flow sensor | Input | Pulse/digital or conditioned analog; final type TBD | Receive flow measurement and calculate GPM |
| Subsystem 1: PT100 temperature channels | Input | SPI digital communication from two MAX31865 modules | Receive inlet and outlet temperature measurements |
| Subsystem 1: Heating demand input | Input | Conditioned analog voltage to STM32 ADC; proposed external range 0–10 V | Receive representative demand information |
| Subsystem 3: Pump control | Output | Manufacturer-supported PWM, analog, or other verified control interface; TBD | Command pump operating level |
| Subsystem 3: Pump feedback | Input, if available | Manufacturer supported status or feedback signal; TBD | Monitor pump operating status |
| Subsystem 4: Bench operating parameters | Input | Configured values and approved test settings | Establish test setpoint, limits, and operating condition |
| Subsystem 5: Data logging | Output | USB serial/UART digital communication | Transmit measurements, commands, states, and faults |
| Low voltage power system | Input | Regulated supply compatible with STM32 and interface hardware | Supply controller and low voltage circuitry |

The STM32 shall not be connected directly to an unconditioned 0–10 V signal or an incompatible pump control input. Required isolation, level shifting, and signal conditioning will be established from verified equipment specifications.

The STM32 GPIO and peripheral assignments will be finalized during Detailed Design. The proposed implementation will use SPI for temperature acquisition, ADC or a digital input for the verified flow and demand interfaces, an appropriate timer or output peripheral for the pump command, and USB serial/UART for logging.


**Interfaces and Procedure:**

When the bench is initialized, the STM32 will configure the required peripherals and check the availability of the expected measurement inputs. The controller will remain in an approved startup state until the conditions required for operation have been satisfied.

During normal operation, the microcontroller will acquire the latest measurements, convert them into engineering units, and evaluate their validity. The feedforward algorithm will determine an initial pump operating command using flow rate and heating demand. The temperature-feedback algorithm will then calculate any necessary correction.

A preliminary proportional-integral control relationship is:

$$
u_{\text{raw}}(t)=u_{\text{ff}}(q(t),f(t))+K_pe_T(t)+K_i\int_0^t e_T(\tau)\,d\tau
$$

The final command will be restricted to the permitted range:

$$
u_{\text{cmd}}(t)=\operatorname{clip}(u_{\text{raw}}(t),u_{\min},u_{\max})
$$

The correct feedback direction, controller gains, and command limits will be established using the Dymola model and verified through physical bench testing. Integral windup protection and suitable command rate limits will be considered during implementation.

The controller will transmit the approved command to the pump and continue monitoring the resulting flow and temperature response. Measurement records and controller states will be provided to Subsystem 5 at the required logging interval.

If the controller detects insufficient circulation, invalid sensor information, or a critical operating fault, it will initiate the approved fault response. Independent thermal and electrical protection will remain separate from the STM32 control algorithm.


**Functional Flowchart:**
<p align="center">
<img width="981" height="93" alt="image" src="https://github.com/user-attachments/assets/70949a81-fe63-4c40-ade3-aa1d8565058e" />
</p>

**Specifications:**

| ID | Specification | Verification Method |
|---|---|---|
| 1 | The subsystem shall acquire the flow, inlet temperature, outlet temperature, and representative heating demand measurements required by the control algorithm. | Sensor interface and integration testing |
| 2 | The subsystem shall convert valid measurements into GPM, °F, and heating demand percentage. | Comparison with known input values |
| 3 | The subsystem shall calculate an initial pump command using flow rate and representative heating demand. | Software tests and Dymola comparison |
| 4 | The subsystem shall use outlet temperature feedback to calculate a correction to the initial pump command. | Simulation and bench response testing |
| 5 | The subsystem shall restrict pump commands to the verified supported operating range. | Command boundary testing |
| 6 | The subsystem shall enforce the approved minimum circulation flow requirement whenever heated circulation is required. | Supervised minimum flow verification |
| 7 | The subsystem shall transmit commands through the selected pump's verified control interface. | Electrical interface and pump response testing |
| 8 | The subsystem shall detect invalid or unavailable critical sensor measurements and initiate the approved fault response. | Sensor fault testing |
| 9 | The subsystem shall record or transmit controller state, measurement values, pump command, and fault status at intervals no greater than one second. | Timestamp and communication testing |
| 10 | Following a defined demand change, the pump command output shall aim to settle within ±5% of its final value within 30 seconds without repeated limit cycling. | Command trace analysis |
| 11 | The subsystem shall support evaluation of the preliminary ±4°F outlet temperature stability target over a defined 60 second steady state window. | Physical bench testing |
| 12 | The subsystem shall provide a defined startup, shutdown, and fault recovery procedure without bypassing independent equipment safety devices. | Approved functional and fault testing |


### 3) Pump, Motor Control, and Hydraulic System

**Overview:**

The Pump, Motor Control, and Hydraulic System will control water circulation and provide the physical environment required to test the Variable-Speed Circulation Pump Controller. The subsystem will use the proposed Grundfos UPMS 15-78 circulation pump, a water heater or approved heat source, a water reservoir, piping, fittings, and other hydraulic components needed for laboratory testing. Its primary purpose is to receive pump-speed commands from the STM32 microcontroller, adjust water circulation accordingly, and provide the operating conditions necessary to evaluate system performance.

The circulation pump will receive a speed-control signal from the Microcontroller and Control Logic Subsystem through the pump's compatible control interface. The pump will adjust its operating speed based on the commanded signal while remaining within the manufacturer's allowable operating limits. The final control signal type, electrical connections, and operating requirements will be verified using the selected pump's manufacturer documentation during Detailed Design.

During operation, the circulation pump will move water through the heating loop while the selected water heater or heat source provides thermal energy to the circulating water. Changes in pump speed will affect the water flow rate and heat transfer within the system. The hydraulic system will provide suitable installation locations for the KEYENCE FD-Q50C flow sensor and two PT100 RTD temperature sensors used by the Sensor and Data Acquisition Subsystem. These sensors will allow the team to monitor water flow rate and inlet and outlet temperatures during testing.

The subsystem will support testing under different heating-demand conditions to evaluate how variable-speed circulation affects water temperature stability, flow rate, and overall system performance. The design will emphasize maintaining sufficient circulation, preventing operation outside the pump's allowable limits, and retaining the existing safety protections of the pump and heating equipment. The initial implementation will focus on the approved laboratory bench-testing system, while integration with actual Lochinvar boiler equipment may be evaluated during future testing if the required interfaces and approvals are available.

**Inputs:**

* Pump-speed commands received from the Microcontroller and Control Logic Subsystem through the verified pump-control interface.
* Electrical power supplied to the Grundfos UPMS 15-78 circulation pump and heating equipment.
* Water supplied through the reservoir and hydraulic circulation loop.
* Heating conditions established by the selected water heater or approved heat source.
* Flow rate and temperature measurements provided by the Sensor and Data Acquisition Subsystem for control and fault detection.
* Pump operating limits and hydraulic requirements established from manufacturer specifications and bench-testing conditions.

**Outputs:**

* Adjustable water circulation through the hydraulic system based on pump-speed commands.
* Heated water circulating through the heating loop.
* Changes in water flow rate resulting from adjustments to pump speed.
* Inlet and outlet water temperatures available for monitoring and heat-transfer evaluation.
* Available pump operating information, including pump speed and operating status, if supported by the selected pump interface.
* Operating conditions and performance measurements made available through the microcontroller to the Monitoring, Performance Evaluation, and Bench Testing Subsystem and the Data Logging and Simulation Subsystem.

**Interfaces and Procedure:**

The subsystem will receive pump-speed commands from the STM32 microcontroller through the verified control interface of the Grundfos UPMS 15-78 circulation pump. The pump will adjust its operating speed according to the received command while maintaining operation within the manufacturer's electrical and hydraulic limits. The final control signal type and electrical connections will be confirmed during Detailed Design.

The circulation pump, water heater or approved heat source, reservoir, piping, and fittings will establish a closed-loop water circulation system for laboratory testing. The KEYENCE FD-Q50C flow sensor and two PT100 RTD temperature sensors will be installed at appropriate locations within the hydraulic loop. These sensors will provide operating measurements to the Sensor and Data Acquisition Subsystem, which will transmit the processed information to the STM32 microcontroller.

Before testing, the hydraulic and electrical connections will be inspected to verify safe operating conditions. During operation, the microcontroller will adjust pump speed according to the measured flow rate, water temperatures, and representative heating-demand conditions. The subsystem will maintain circulation within the established operating limits while allowing the team to observe changes in flow rate and thermal performance. Any detected fault or unsafe operating condition will be handled according to the approved shutdown procedure without bypassing the manufacturer's existing safety protections.

The collected operating measurements will support performance evaluation and experimental data logging. After testing, the circulation pump and heating equipment will be shut down according to the manufacturer's procedures.

**Functional Flowchart:**
<p align="center">
<img width="825" height="242" alt="image" src="https://github.com/user-attachments/assets/97c8f6ae-c530-4c08-8fbd-bd51574dd9e2" />
</p>

**Specifications:**

1) This subsystem shall receive pump-speed commands from the Microcontroller and Control Logic Subsystem through the verified pump-control interface.
2) This subsystem shall adjust the circulation pump speed according to the received control commands.
3) This subsystem shall maintain pump operation within the manufacturer's specified electrical and operating limits.
4) This subsystem shall circulate water through the heating system while maintaining the required minimum flow rate during heated operation.
5) This subsystem shall provide the hydraulic connections and installation locations required for the flow-rate and temperature sensors.
6) This subsystem shall support water heating and circulation under the established laboratory testing conditions.
7) This subsystem shall maintain piping, fittings, and seals capable of withstanding the system's operating temperature and pressure without leakage.
8) This subsystem shall retain the existing safety protections of the circulation pump and heating equipment.
9) This subsystem shall support the detection and handling of pump faults and unsafe operating conditions through the approved controller response.
10) This subsystem shall provide available operating information to support system monitoring, performance evaluation, and data logging.



### 4) Monitoring, Performance Evaluation, and Bench Testing Subsystem

**Overview:**

The Monitoring, Performance Evaluation, and Bench Testing Subsystem will be responsible for assembling, integrating, and evaluating the physical water circulation bench used to test the proposed variable-speed pump control strategy. The bench will use the Grundfos UPMS 15-78 130 AR circulation pump provided by Lochinvar, an STM32 Nucleo-L476RG microcontroller, a flow sensor, temperature sensors, and electrical measurement equipment. A heating element is also being evaluated for integration into the water circulation loop.

This subsystem will monitor system operating measurements, including water flow rate, inlet and outlet temperatures, and pump electrical consumption, to determine how changes in pump speed affect system performance. The pump control algorithm and associated microcontroller code developed by the Microcontroller and Control Logic Subsystem (Subsystem 2) will be loaded onto the STM32 and used during physical testing. This subsystem will compare constant-speed and variable-speed operation to evaluate whether reducing pump speed can decrease electrical energy consumption while maintaining acceptable water flow and temperature performance. The collected measurements and performance results will be provided to the Data Logging and Simulation Subsystem (Subsystem 5) for recording, comparison with simulation results, and further analysis.

**Functional Description:**

1. **Bench Test Integration:** Assemble the physical water circulation loop and integrate the pump, heating element (if used), sensors, and measurement equipment. Coordinate with the Pump, Motor Control, and Hydraulic System Subsystem (Subsystem 3) to integrate the pump interface and hydraulic components into the bench setup.

2. **Flow and Temperature Monitoring:** Work with the Sensor and Data Acquisition Subsystem (Subsystem 1) to obtain and monitor flow rate, inlet and outlet temperatures, and other required measurements during physical testing.

3. **Energy Performance Evaluation:** Measure and compare pump electrical power and energy consumption at different pump speeds to evaluate the energy performance of the proposed control strategy.

4. **Operating Requirements:** Determine whether the system maintains minimum flow and acceptable temperature requirements during variable-speed operation, using the operating limits and requirements established by Subsystems 2 and 3.

5. **Control Strategy Testing:** Load and run the pump control algorithm and associated microcontroller code developed by the Microcontroller and Control Logic Subsystem (Subsystem 2) on the STM32 to test the pump's response to different operating conditions.

6. **Performance Feedback:** Provide collected measurements and physical test results to the Data Logging and Simulation Subsystem (Subsystem 5) for data recording, comparison with simulation results, and further analysis.

7. **System Evaluation:** Identify performance issues during physical testing and communicate findings to the appropriate subsystems for potential adjustments to the pump control algorithm, sensor integration, hydraulic setup, or simulation model.

**Inputs:**

- Water flow rate measurements from Subsystem 1.
- Inlet and outlet temperature measurements from Subsystem 1.
- Pump control algorithm and associated microcontroller code from Subsystem 2.
- Pump interface and hydraulic components from Subsystem 3.
- Selected pump operating conditions and approved minimum flow and temperature requirements.
- Pump voltage and current measurements from electrical measurement equipment integrated into the bench setup.

**Outputs:**

- Pump operating measurements, including flow rate and inlet and outlet temperatures.
- Pump electrical power and energy consumption measurements.
- Pump operating speed and corresponding test conditions.
- Physical test results comparing constant-speed and variable-speed operation.
- Performance findings and recommendations communicated to the appropriate subsystems.
- Experimental measurements and test results transmitted to Subsystem 5 for data logging and comparison with simulation results.

**Interfaces Between Subsystems:**

1. **Subsystem 1: Sensor and Data Acquisition**
   - **Direction:** Input to Subsystem 4.
   - **Signal Type:** Analog or digital sensor signals, depending on the selected sensor interfaces.
   - **Data Received:** Water flow rate and inlet and outlet temperature measurements.
   - **Purpose:** Provides the measurements needed to monitor water circulation and temperature performance during physical testing. Subsystem 1 is responsible for sensor selection, integration, and required signal conditioning.

2. **Subsystem 2: Microcontroller and Control Logic**
   - **Direction:** Input to Subsystem 4.
   - **Signal Type:** Digital program code and control algorithm.
   - **Data Received:** Pump control algorithm, associated microcontroller code, and established operating limits.
   - **Purpose:** Provides the control code that Subsystem 4 loads and runs on the STM32 during physical testing. Subsystem 4 evaluates the resulting pump operation but does not develop the control algorithm.

3. **Subsystem 3: Pump, Motor Control, and Hydraulic System**
   - **Direction:** Input and output between subsystems.
   - **Signal Type:** Hydraulic connections and electrical pump-control signals.
   - **Data Exchanged:** Pump operating commands, pump status or feedback if available, and hydraulic operating conditions.
   - **Purpose:** Provides the pump interface and hydraulic components needed to integrate and operate the physical circulation bench.

4. **Subsystem 5: Data Logging and Simulation**
   - **Direction:** Output from Subsystem 4.
   - **Signal Type:** Digital serial communication through USB virtual COM or UART.
   - **Data Sent:** Flow rate, inlet and outlet temperatures, pump speed, electrical power consumption, and physical test results.
   - **Purpose:** Receives experimental measurements for data recording, comparison with simulation results, and further analysis.

The STM32 Nucleo-L476RG operates with 3.3 V logic levels. Sensor and control signals must be compatible with the microcontroller's electrical requirements. The KEYENCE FD-Q50C flow sensor will provide measurements through its specified electrical output interface, and the temperature sensors will provide measurements through their selected interfaces. Signal conditioning or voltage-level conversion may be required before connecting these signals to the STM32.

The Grundfos pump will receive operating power through its designated electrical supply, independently of the STM32. The STM32 will provide the appropriate speed-control command through the pump interface established by Subsystem 3. The exact pump control signal and voltage requirements must be verified using the manufacturer's specifications before finalizing the electrical design. Appropriate electrical protection and isolation will be used between high-voltage and low-voltage circuits.

Pump voltage and current will be measured using suitable electrical measurement equipment. The resulting electrical measurements will be used to calculate pump power and energy consumption.

Communication between the STM32 and Subsystem 5 will use USB virtual COM or UART serial communication, depending on the final implementation. The transmitted information will include flow rate, temperature measurements, pump speed, electrical power consumption, and test results.

**Interfaces and Procedure:**

The team will use this subsystem during laboratory testing to assemble, operate, and monitor the physical water circulation bench. The subsystem will coordinate with Subsystem 1 to obtain flow and temperature measurements, Subsystem 2 to run the developed pump control algorithm and associated microcontroller code on the STM32, and Subsystem 3 to integrate and operate the pump and circulation system.

When the bench is initialized, the team will verify sensor connections, microcontroller communication, pump operation, and measurement equipment. The pump will first operate at a selected constant speed to establish baseline measurements. Flow rate, inlet and outlet temperatures, and electrical consumption will be recorded during this test.

After baseline testing, the control code developed by Subsystem 2 will be loaded and run on the STM32. The controller will adjust pump speed according to the programmed operating conditions. During variable-speed testing, the subsystem will monitor flow rate, temperature response, pump operation, and electrical consumption.

The results from constant-speed and variable-speed operation will be compared to determine changes in pump energy consumption and overall system performance. The subsystem will evaluate whether the pump maintains the required minimum flow and acceptable temperature conditions while operating at reduced speeds.

Collected measurements and physical test results will be transmitted to Subsystem 5 for data logging, comparison with simulation results, and further analysis. Any performance issues identified during testing will be communicated to the appropriate subsystems for potential design adjustments.

**Functional Flowchart:**
<img width="1314" height="510" alt="image" src="https://github.com/user-attachments/assets/28966266-766a-4621-9a8d-618993ed77ae" />


<img width="1316" height="990" alt="image" src="https://github.com/user-attachments/assets/3c9903be-fe6e-49a5-bd7d-fa4f52222671" />


**Specifications:**

1. This subsystem shall assemble and integrate the physical water circulation bench, including the pump, heating element (if used), sensors, and measurement equipment, coordinating with Subsystem 3.

2. This subsystem shall monitor water flow rate and inlet and outlet temperature measurements using the sensors integrated by Subsystem 1.

3. This subsystem shall measure pump electrical power and energy consumption using suitable voltage and current measurement equipment.

4. This subsystem shall load and run the control code developed by Subsystem 2 on the STM32 to evaluate variable-speed pump operation.

5. This subsystem shall provide collected sensor measurements and physical test results to Subsystem 5 for recording, comparison with simulation results, and further analysis.

6. This subsystem shall evaluate whether the system maintains minimum flow and acceptable temperature requirements during testing, considering the operating limits established by Subsystems 2 and 3.

7. This subsystem shall identify performance issues found during testing that may require adjustments to the physical setup, sensor measurements, or proposed control strategy and communicate relevant findings to the appropriate subsystems.

8. The pump shall receive operating power independently from the STM32, with appropriate electrical protection and isolation between high-voltage and low-voltage circuits.


### 5) Data Logging and Simulation Subsystem

**Overview:**

The Data Logging and Simulation Subsystem will support development and experimental validation of the Variable Speed Circulation Pump Controller by combining computer simulation with organized physical bench-test measurements. Dymola simulation software will be used to model the relationships between circulation pump operation, water flow rate, heat transfer, and temperature response. The simulation will serve as an input to the physical bench-testing process by helping the team select preliminary controller settings and appropriate experimental operating conditions.

The physical bench test will remain the primary method of verifying controller performance. After testing, the measured results will be compared with simulation predictions under equivalent operating conditions to evaluate model accuracy and identify differences between theoretical and actual system behavior. The subsystem will also collect and organize measurements from the STM32 controller and the approved electrical power measurement system. Data will be recorded with timestamps and test condition identifiers in a structured format suitable for analysis, such as CSV files. The logging and simulation functions are required parts of the project. The subsystem will not directly command the circulation pump during normal operation. Pump control firmware and real time control decisions remain the responsibility of Subsystem 2.

**Functional Description:**

1. **Simulation Development:** Develop a Dymola model representing the selected pump, hydraulic loop, heat source, and relevant temperature behavior.

2. **Preliminary Test Selection:** Use simulation predictions to help identify controller settings and low-, medium-, and high-demand conditions for the physical bench.

3. **Data Acquisition:** Receive measurements, controller commands, operating states, and fault information from the STM32.

4. **Power Data Integration:** Incorporate real electrical input-power measurements from the approved power-monitoring equipment.

5. **Data Storage:** Save measurements in organized CSV files containing timestamps, units, operating conditions, and test identifiers.

6. **Baseline and Controlled Comparison:** Organize the results from matched constant-speed and variable-speed trials.

7. **Simulation Validation:** Compare Dymola predictions with measured flow rate, temperature, and transient response.

8. **Error and Uncertainty Analysis:** Calculate model errors, electrical-power savings, repeatability, and appropriate statistical measures.

9. **Results Documentation:** Generate graphs, tables, and datasets for the technical report and performance evaluation.


**Inputs:**

* Flow rate in GPM from the STM32 measurement system.
* Inlet and outlet water temperatures in °F.
* Representative heating demand input and selected temperature setpoint.
* Commanded pump operating level and available pump feedback.
* Controller operating state and fault information.
* Real electrical input power measurements from the approved monitoring equipment.
* Bench-test identifiers, operating conditions, and timestamps.
* Pump curves, hydraulic parameters, heat source characteristics, and other verified model inputs.
  
**Outputs:**

* Dymola simulation predictions and preliminary controller setting recommendations.
* CSV files containing organized physical bench-test measurements.
* Baseline and controlled operating-condition datasets.
* Flow rate, temperature, pump-command, and electrical power graphs.
* Calculated electrical power savings and applicable energy consumption results.
* Simulation versus measurement error calculations.
* Statistical summaries, uncertainty information, and documented limitations.
* Data and analysis provided to Subsystem 4 for performance evaluation.
  
**Interfaces Between Subsystems:**

| Connection | Direction | Signal or Data Type | Purpose |
|---|---|---|---|
| Subsystem 1: Sensor measurements | Input through Subsystem 2 | Digital measurement records | Obtain validated flow and temperature information |
| Subsystem 2: Controller data | Input | USB serial/UART digital communication | Receive measurements, pump commands, states, and faults |
| Subsystem 3: Pump characteristics | Input | Manufacturer documentation and model parameters | Represent pump performance in Dymola |
| Subsystem 4: Electrical measurements | Input | Instrument export, supported digital interface, or documented data import | Record real pump-and-drive input power |
| Subsystem 4: Bench-test conditions | Input | Test identifiers, operating settings, and recorded procedures | Associate measurements with physical trials |
| Subsystem 4: Analysis results | Output | CSV files, plots, tables, and reports | Support experimental performance evaluation |
| Subsystem 2: Simulation recommendations | Output | Model results and proposed controller parameters | Inform initial controller settings before bench testing |
| Computer storage | Output | CSV files and associated metadata | Preserve experimental records |

The preliminary communication approach will use the STM32's USB serial/UART connection to transfer operating measurements to a computer. A computer-based logging program will organize the received data into CSV files. If the electrical power instrument cannot communicate directly with the STM32 or computer, its measurements will be imported using a documented method. The final design must provide a way to associate electrical power readings with the correct test conditions and measurement times. The Dymola simulation will not be assumed to communicate with the STM32 in real time. Instead, its predictions will be used to prepare the bench experiment and later compared with the recorded experimental results.


**Interfaces and Procedure:**

The subsystem will first collect the verified specifications and physical parameters needed to develop the simulation model. These may include pump characteristics, hydraulic resistance, water properties, heat source behavior, and selected operating conditions. Dymola will be used to predict system responses at different pump operating levels and heating-demand conditions. The resulting predictions will help establish initial controller parameters and identify useful physical test conditions. Before bench testing, the data logging system will be configured to receive measurements from the STM32. Each record will include the applicable timestamp, test identifier, and available operating measurements.

A preliminary CSV record will contain the following fields:

| Field | Unit or Format | Description |
|---|---|---|
| timestamp_s | Seconds | Time relative to the beginning of the test |
| test_id | Text | Unique test identification |
| demand_level | Low, Medium, High | Selected operating condition |
| test_mode | Baseline or Controlled | Pump operating strategy |
| flow_gpm | GPM | Measured circulation flow rate |
| inlet_temp_f | °F | Measured inlet-water temperature |
| outlet_temp_f | °F | Measured outlet-water temperature |
| temp_setpoint_f | °F | Selected outlet-temperature target |
| heating_demand_pct | % | Applied representative heating demand |
| pump_command_pct | % | Normalized pump operating command |
| pump_power_w | W | Measured real electrical input power |
| controller_state | Text or numeric code | Current controller operating state |
| fault_code | Text or numeric code | Recorded controller fault information |

The pump power measurement may be stored in a synchronized companion dataset if the selected power instrument cannot provide readings through the same communication interface. The physical bench-testing plan will include three operating conditions representing low, medium, and high demand. Five paired baseline and controlled trials will be completed for each condition, resulting in 15 paired comparisons. After testing, the subsystem will organize the collected data and compare baseline and controlled operation. Simulation predictions will be evaluated using matching test conditions.

**Electrical Power Savings Calculation:**

The measured percentage reduction in electrical input power will be calculated using:

$$
S=\frac{P_{\text{baseline}}-P_{\text{controlled}}}{P_{\text{baseline}}}\times100\%
$$

where:

- **S** represents percentage electrical power savings.
- **P_baseline** represents measured baseline real electrical input power.
- **P_controlled** represents measured controlled real electrical input power.

For time varying measurements, the team will calculate average real power over equivalent observation windows. Electrical energy may also be calculated from the recorded power measurements using:

$$
E=\int_{t_0}^{t_1}P(t)\,dt
$$

For discrete measurements, a numerical approximation may be used:

$$
E\approx\sum_{i=1}^{n-1}\frac{P_i+P_{i+1}}{2}(t_{i+1}-t_i)
$$

The units of energy will be reported consistently, such as joules or watt hours.

**Simulation Error Calculation:**

Absolute error between simulated and measured values will be calculated as:

$$
e_x=|x_{\text{simulated}}-x_{\text{measured}}|
$$

Percentage error will be calculated where the measured reference value is nonzero and the comparison is meaningful:

$$
e_{x,\%}=\frac{|x_{\text{simulated}}-x_{\text{measured}}|}{|x_{\text{measured}}|}\times100\%
$$

The team will compare simulation and physical bench results for selected flow rate, temperature, and response time measurements. Differences will be documented and used to evaluate model assumptions and improve subsequent predictions. The analysis will also report trial to trial variability and a 95% confidence interval for electrical power savings when supported by the collected data and statistical assumptions.

**Functional Flowchart:**
<p align="center">
<img width="942" height="203" alt="image" src="https://github.com/user-attachments/assets/6a49cbd7-0922-45fe-a327-cdd5e8c62fc1" />
</p>

**Specifications:**

| ID | Specification | Verification Method |
|---|---|---|
| 1 | The subsystem shall develop a Dymola simulation representing the selected bench pump, hydraulic loop, and relevant thermal behavior. | Model review and simulation execution |
| 2 | The subsystem shall use simulation predictions to identify preliminary controller settings and bench operating conditions. | Documented simulation to test comparison |
| 3 | The subsystem shall receive and store available flow, temperature, demand, pump command, controller state, and fault measurements. | Data logging integration test |
| 4 | The subsystem shall incorporate measured real pump and drive electrical input power into the experimental dataset. | Power measurement and data import verification |
| 5 | The subsystem shall record operating measurements at intervals no greater than one second, excluding separately documented instrument limitations. | Timestamp interval analysis |
| 6 | The subsystem shall associate each measurement with its test identifier and baseline or controlled operating mode. | CSV record inspection |
| 7 | The subsystem shall store experimental data in a documented, machine readable format suitable for analysis and graphing. | CSV import and data integrity testing |
| 8 | The subsystem shall support five paired baseline and controlled trials at each of three demand conditions, producing 15 paired comparisons. | Completed test-record review |
| 9 | The subsystem shall calculate measured percentage electrical-power savings using matched baseline and controlled data. | Independent calculation verification |
| 10 | The subsystem shall compare simulated and measured flow, temperature, and response time values under equivalent conditions. | Simulation validation report |
| 11 | The subsystem shall calculate and report appropriate model error measures. | Independent calculation verification |
| 12 | The subsystem shall report repeatability, variability, and a 95% confidence interval for power savings when statistically supported. | Statistical analysis review |
| 13 | The subsystem shall preserve available raw measurements and document missing data, processing methods, assumptions, and model limitations. | Dataset and report review |
| 14 | The subsystem shall generate graphs and summary tables for the final engineering report. | Review of submitted analysis results |


## Ethical, Professional, and Standards Considerations

The development of this variable circulation pump controller project has implications across environmental, societal, economic, scientific, cultural, and ethical domains. These considerations directly influence the controller’s design and the engineering practices required to develop a reliable and efficient system. Throughout the project, the team must consider how the controller will affect facility operations, public health and safety, energy consumption, and future applications developed by Lochinvar.

From an environmental perspective, the controller should be designed to improve pump electrical energy efficiency compared with the current fixed-speed circulation pump. Developing a controller that adjusts pump operation based on system demand could reduce unnecessary energy consumption and decrease the facility’s overall carbon footprint. By allowing the pump to operate at different speeds rather than continuously operating at a fixed speed, the controller could improve energy efficiency during periods of lower demand. These environmental considerations will influence the control logic by prioritizing efficient pump operation while maintaining the required water temperature and circulation conditions.

From a societal standpoint, the variable circulation pump controller must operate reliably within the approved equipment limits across different commercial facilities. The system must continuously respond to fluctuating peak demands while maintaining strict temperature stability parameters. If the pump fails to satisfy these demands, it could result in financial losses, interruptions in facility operations, and risks to public health and safety. Therefore, the controller should be designed to provide reliable operation, accurate temperature monitoring, and consistent performance under changing operating conditions. These design considerations would help improve the overall reliability of the facility’s water circulation system.

From an economic perspective, implementing a variable circulation pump controller could reduce operating expenses by adjusting the pump’s performance to match system demand. Compared with a fixed speed circulation pump, the variable controller could reduce unnecessary energy consumption during periods of lower demand. However, these potential savings must be considered alongside the controller’s initial cost, maintenance requirements, and equipment reliability. A system failure could result in additional maintenance costs, equipment damage, or interruptions in facility operations. Therefore, the design should prioritize long-term performance, efficient energy consumption, and reliability while minimizing unnecessary operating expenses.

From a scientific perspective, the variable circulation pump controller must incorporate an accurate and stable control loop capable of responding to changing operating conditions. The accuracy of the controller can be supported by field data provided by Lochinvar from its testing locations. This information will provide physical measurements that can be used to develop, configure, and validate the controller’s logic. Without accurate data, cross referencing simulation predictions with actual system performance would be difficult and could reduce the reliability of the final design. Standardizing data collection and testing procedures could improve simulation accuracy, help identify anomalies, and allow the team to make necessary adjustments to the controller. These practices will help ensure that the system responds appropriately to changes in temperature and demand.

Ethical responsibilities are integrated into the design and implementation of the project. As engineers, the team is committed to ensuring the accuracy and integrity of its methodology and data. This commitment includes rigorous measurement validation, proper documentation, equipment calibration, and strict attention to detail. Through collaboration with Lochinvar, the team must remain accountable for its deliverables while adhering to applicable engineering standards, copyrights, and intellectual property rights. Upholding these responsibilities allows the team to use the data provided by Lochinvar securely and incorporate that information into a product intended to remain internal to the company. Maintaining professional integrity throughout the design process will help ensure that the final controller is developed responsibly and that all testing results accurately represent its performance.

From a cultural perspective, the variable circulation pump controller should be designed to accommodate different types of commercial facilities and their operating requirements. Each facility may have different water demands, equipment configurations, and levels of operator experience. The controller would need to be configured and validated for the requirements of each facility. A user facing interface is not part of the current design requirements. The controller should also be adaptable to different operating environments while maintaining consistent performance. This flexibility could allow Lochinvar to implement the controller in future products and across a wider range of commercial applications.

Public health and safety are essential considerations throughout the design process. The circulation pump controller must maintain the required water temperature and flow conditions during fluctuations in system demand. Failure to maintain these parameters could create unsafe operating conditions, affect water availability, or interrupt facility operations. To address these concerns, the controller should incorporate temperature monitoring, appropriate operating limits, and fault detection capabilities. These features would allow the system to identify abnormal operating conditions and respond appropriately. The design should also account for potential sensor failures, communication issues, and unexpected changes in system demand. Incorporating these safeguards would help protect facility operators and occupants while improving the reliability of the overall system.

Relevant engineering standards will also influence the development of the controller. Organizations such as the American Society of Heating, Refrigerating and Air-Conditioning Engineers (ASHRAE), the American National Standards Institute (ANSI), the American Society of Mechanical Engineers (ASME), and UL Standards & Engagement establish or coordinate standards relevant to building energy efficiency, electrical equipment, and control systems. ASHRAE Standard 90.1 provides requirements for energy-efficient building systems, while UL 60730-1 addresses safety requirements for automatic electrical controls. Depending on the final application of the pump, additional requirements involving water circulation, equipment protection, and electrical safety may also apply. The team will need to determine which standards apply to the controller and use them to guide the selection of electrical components, operating limits, control logic, and testing procedures. Following applicable standards will help improve the overall safety, reliability, and compatibility of the final design.

These considerations will influence the design constraints, specifications, and engineering practices implemented throughout the project. The controller must be capable of responding to fluctuations in system demand while maintaining water temperature and circulation within the operating limits established with Lochinvar. These limitations will influence the selection of sensors, the controller’s response time, pump speed adjustments, and the development of protective features. To evaluate the controller’s performance, the team will compare its energy consumption with that of the existing fixed-speed pump and analyze temperature stability under different loading conditions. Testing should also include simulated faults and abnormal operating conditions to verify that the controller responds safely and reliably. The team will use field measurements, simulation results, and repeated testing to validate the accuracy of the control system. Proper documentation, calibration, and consistent testing practices will help ensure that the final design meets the established requirements.

In conclusion, upholding public safety remains a primary responsibility throughout this project. The development of the variable circulation pump controller must maintain reliable temperature stability under fluctuating loads in commercial facilities while improving energy efficiency and overall system performance. Achieving these goals will require each team member to complete their contributions with technical diligence, professional integrity, and attention to the environmental, societal, cultural, and economic impacts of the design. Team members must also remain mindful that this controller may be used in future products developed by Lochinvar. By following applicable engineering standards, validating system performance, and maintaining ethical responsibilities, the team can work toward delivering a safe, reliable, and efficient controller that benefits both Lochinvar and the public while reducing potential operational risks and liabilities.

#### Specific Health, Safety, and Welfare Hazards (H1)
---

The proposed Variable Speed Circulation Pump Controller will be developed and evaluated using a dedicated physical bench-testing system. The bench will include a water reservoir, variable-speed circulation pump, electric heat source, flow sensor, inlet and outlet temperature sensors, STM32L476RG microcontroller, and electrical measurement equipment. Although the system will not initially operate on commercial Lochinvar heating equipment, the physical bench introduces electrical, hydraulic, and thermal hazards that must be addressed before testing begins.

The primary safety concern is ensuring that the controller does not reduce circulation flow below the safe operating limits of the selected bench equipment. Insufficient flow could result in excessive water temperature rise, overheating of the heat source, or damage to the pump and surrounding components. Additional hazards include electrical shock, hot-water exposure, leaks, unexpected pressure increases, sensor failures, and incorrect pump control commands.

The following table identifies the primary hazards, individuals who may be affected, potential severity, planned safeguards, and verification methods.


| Hazard and Cause | People Potentially Affected | Potential Severity | Planned Design Safeguard | Verification |
|---|---|---|---|---|
| Insufficient circulation while the electric heat source is operating | Students, faculty, and laboratory personnel | High: localized overheating, equipment damage, or unsafe water temperatures | Establish the minimum safe circulation flow from selected equipment specifications; monitor flow continuously; require an approved heater shutdown or interlock response when circulation becomes insufficient. | Document minimum flow requirements and perform approved low flow protection tests without bypassing independent safety devices. |
| Outlet-water temperature exceeding the approved operating limit | Students and nearby laboratory personnel | High: burns, overheating, or component damage | Monitor outlet temperature using the PT100 RTD measurement system, establish a maximum permitted temperature, preserve independent overtemperature protection. | Compare recorded temperatures with a calibrated reference and verify approved overtemperature responses. |
| Electrical shock from pump, heater, or power monitoring connections | Students, technicians, and faculty | High: electrical shock, burns, or fire | Separate hazardous voltage wiring from STM32 low voltage circuitry. Use appropriate grounding, enclosures, protection, and authorized electrical installation. | Inspect electrical schematics, wiring, protective devices, and isolation before energizing. |
| Water leakage near energized electrical equipment | Students and laboratory personnel | High: electrical hazards, slipping, or equipment damage | Use compatible tubing, fittings, clamps, and secure connections; position electrical components away from possible leaks. Inspect the loop before operation. | Perform a supervised leak inspection and verify electrical equipment placement. |
| Excessive hydraulic pressure or unsuitable component ratings | Students and nearby personnel | High: tubing failure, water release, or injury | Verify pressure and temperature ratings of the reservoir, tubing, fittings, pump, and heat source; provide appropriate pressure protection if required by the final loop design. | Review component datasheets, hydraulic schematic, and pressure protection arrangements before heated operation. |
| Pump malfunction or unexpected loss of circulation | Students, faculty, and laboratory personnel | High: heat source overheating or equipment damage | Detect insufficient measured flow and relevant pump faults; use an approved response that places the heat source and circulation equipment in a safe condition. | Conduct supervised pump fault and circulation loss tests using approved methods. |
| Failed temperature or flow sensors | Students and laboratory personnel | High: incorrect pump commands or undetected unsafe operating conditions | Validate sensor ranges, communication status, and measurement plausibility. Reject invalid readings and initiate the approved fault response. | Test disconnected, invalid, and out of range sensor conditions without defeating independent protections. |
| Incorrect STM32 control output or communication failure | Students, technicians, and laboratory personnel | Moderate to high: unexpected pump operation or inadequate circulation | Limit pump commands to the verified supported range. Define startup, reset, watchdog, and communication loss behavior. Maintain independent heater protection. | Verify controller limits, startup behavior, and approved fault responses before heated operation. |
| Contact with hot tubing, fittings, or heating equipment | Students and laboratory personnel | Moderate to high: skin burns | Identify hot surfaces, provide appropriate guards or insulation, and require cooling before handling or servicing. | Inspect exposed surfaces and document safe handling and shutdown procedures. |
| Unexpected energization or stored energy during maintenance | Students, faculty, and authorized technicians | High: electrical injury, hot water release, or unexpected equipment operation | Follow applicable hazardous-energy isolation procedures. Disconnect and verify electrical power and safely release thermal or hydraulic energy before servicing. | Document shutdown and isolation procedures and verify their use during supervised maintenance. |


#### Hazard Prevention and Fault Response Procedures

Before physical testing, the team will identify the operating limits of the selected pump, heat source, reservoir, tubing, and sensors. These limits will include the minimum circulation flow, maximum water temperature, allowable pressure, electrical supply requirements, and supported pump control interface. Any limit that has not been confirmed will remain unresolved until the necessary manufacturer information and faculty approval are obtained.

The STM32L476RG controller will monitor the available flow and temperature measurements and compare them with the approved operating limits. If a sensor failure, communication error, insufficient circulation condition, or abnormal temperature is detected, the controller will initiate the fault response established during Detailed Design. Software based protection will supplement, rather than replace, independent protective devices associated with the heat source and electrical equipment.

The team will use simulation to evaluate potentially unsafe operating conditions before attempting physical fault testing. Physical tests involving abnormal conditions will only be conducted after approval from the faculty supervisor and will not involve bypassing manufacturer required safety protections.

#### Bench Inspection and Safety Verification

The physical bench will undergo a documented inspection before heated operation. The team will verify the electrical connections, component ratings, sensor installation, pump control interface, hydraulic connections, and available safety protections. The system will first be evaluated under approved low risk conditions to confirm basic circulation, measurement accuracy, and controller communication.

After initial verification, the team will conduct supervised operating tests and record water flow, inlet and outlet temperatures, pump electrical input power, and controller status. Any observed unsafe condition or unexpected equipment response will require the affected test to be stopped and reviewed before testing continues.

Only qualified or institutionally authorized personnel will perform work requiring electrical or plumbing expertise. The team will follow applicable Tennessee Tech laboratory procedures and hazardous-energy requirements, including OSHA 29 CFR 1910.147 where applicable [9].

The final bench design will prioritize the safety of students, faculty, and laboratory personnel while providing a controlled environment for evaluating the proposed pump control strategy. Future integration with Lochinvar equipment will require a separate safety review because the operating conditions and hazards of a commercial water heater may differ from those of the physical bench.


#### Application and Verification of Engineering Standards (H2 and H3)
--- 

The variable speed circulation pump controller will be developed and evaluated using a dedicated physical bench test rather than depending on access to commercial heating equipment. The bench will include a variable speed pump, heat source, water circulation loop, sensors, power connections, and the actual controller. Because the experiment involves electricity, moving water, and heat, the team must consider the standards and safety procedures that apply to the equipment actually selected for the bench. The standards will guide component selection, wiring, plumbing, control limits, fault responses, and testing methods.

The following table explains how each standard or regulation may influence the design and what evidence the team plans to collect. Applicability depends on the final equipment, installation, jurisdiction, and institutional requirements. The team will confirm the relevant editions and provisions with the faculty supervisor and authorized laboratory personnel before implementation. The verification activities described here are part of the capstone design process; they do not constitute formal certification or a claim of full code compliance.



| Standard or regulation | How it affects the proposed bench design | Planned verification evidence | Applicability or detail still to confirm |
|---|---|---|---|
| NFPA 70 (National Electrical Code), including Article 430 where applicable | Guides the review of motor branch circuit wiring, conductor sizing, grounding, overcurrent protection, disconnecting means, and the selected pump or motor control equipment. Low voltage control circuits will be appropriately separated or isolated from hazardous voltage circuits. | Power and control schematics, component ratings, protective device review, and an inspection by qualified or institutionally authorized personnel before energizing the bench. | Adopted code edition, relevant articles, the pump's electrical design, and whether Article 430 provisions apply to each installed component. |
| OSHA 29 CFR 1910.147 and Tennessee Tech hazardous energy procedures, as applicable | Informs the procedure for isolating electrical, thermal, pressure, and other hazardous energy before servicing, modifying, or repairing the bench setup. The team will not assume that switching off the controller makes the apparatus safe to work on. | Written isolation and verification procedure. Authorized pre work checks and records where required. | Regulatory applicability to the educational laboratory and the institution's required procedures. |
| UL 60730-1, where applicable to the selected automatic electrical control | Provides a safety design reference for abnormal operation, loss of inputs, controller resets, and safe responses to faults. Software will not be treated as a substitute for independent equipment protection. | Documented fault response requirements, simulation of unsafe scenarios, and approved bench fault injection tests that do not defeat protective devices. | Applicable clauses, whether the controller falls within the standard's scope, and whether any product certification would be required for future commercialization. |
| Applicable plumbing and mechanical requirements; International Plumbing Code as a reference where appropriate | Informs the selection of temperature and pressure rated tubing, fittings, reservoir, valves, and connections. The water loop will be checked for leakage and safe operation within the selected components' ratings. | Component datasheets, bench loop schematic, approved connection review, and supervised leak inspection before heated operation. | Local code applicability, pressure relief and backflow requirements, and the approved configuration of the final bench loop. |
| ASHRAE Standard 188 | Relevant primarily to future building water system applications and water management responsibilities. The bench will not be presented as a commercial domestic hot water installation. If the controller is later connected to commercial equipment, it must not undermine existing water management protections. | Written applicability review, identification of the boundary between the bench experiment and a future building installation, and a future integration safety review if sponsor testing is approved. | Whether and how the standard applies to any eventual commercial installation; not automatically a direct bench test requirement. |
| ASHRAE Standard 90.1 | Provides context for energy efficient building systems and future commercial use, but does not automatically establish a compliance requirement for the capstone bench prototype. | Measured pump and drive real electrical input power comparisons, documented test conditions, and a written applicability statement. | Applicable edition and whether specific provisions would apply to a future commercial product or installation. |
| Selected pump, heat source, and sensor manufacturer instructions | Establish the actual safe operating limits for the bench, including maximum temperature, permitted flow range, pressure, electrical ratings, and supported pump control interface. These equipment specific limits take priority over unverified assumptions. | Verified datasheets and nameplates, a documented limits table, wiring/interface review, calibrated measurements, and approved bench checks of temperature and minimum flow. | Final component models, approved minimum circulation flow in GPM, maximum temperature, pump control method, and any required independent protective devices. |


#### Standards Verification and Documentation Procedure

* 1. Identify Applicable Requirements: Once the bench pump, heat source, sensors, and electrical components are selected, the team will review their manufacturer documentation and the relevant standards, codes, and Tennessee Tech laboratory procedures. Unconfirmed requirements will be listed as pending instead of being assigned assumed values.
 
* 2. Connect requirements to the design: Each applicable requirement will be linked to a specific design choice, such as electrical isolation, motor protection, pressure rated fittings, a minimum flow limit, a maximum temperature limit, or a defined controller fault response. The relevant requirement will also be linked to a verification method.

* 3. Review the bench before energizing it: The team will present the bench schematic, component ratings, wiring plan, hydraulic layout, heat source protection, and proposed test procedure to the faculty supervisor. Work requiring qualified electrical or plumbing personnel will be performed only by authorized individuals. The bench will not be energized until the required review and approval are complete.

* 4. Verify safety on the physical bench: The team will check electrical isolation and protective devices, inspect connections for leaks, confirm the documented temperature and minimum flow limits, and test defined fault responses through approved methods. Simulation may be used to explore dangerous conditions, but it will not replace the required physical verification of safety related limits. Fault testing must not bypass the heat source's or pump's independent protections.

* 5. Document the evidence: For each requirement, the team will record the source, expected result, test procedure, measured result, uncertainty where relevant, and any corrective action. Incomplete or failed checks will remain visible in the documentation until resolved.
 
* 6. Review changes: If the selected heat source, pump, controller, sensor, or interface changes, the team will revisit the affected limits, schematics, test procedures, and applicable standards before repeating the relevant verification steps. Any optional testing at Lochinvar's laboratory will require a separate equipment specific review and approval.
 
#### Remaining Standards Related Confirmations

The final bench heat source, pump configuration, supported speed control interface, safe minimum circulation flow, maximum operating temperature, and required independent protections have not all been confirmed. These values must be obtained from the selected equipment and approved test design before heated operation. The team must also confirm which electrical, plumbing, and institutional procedures apply to the final setup.

Testing at Lochinvar's laboratory near the end of Capstone 2 remains an optional stretch goal. If it becomes possible, the team will review the actual equipment's operating limits, electrical and signal interfaces, water management protections, and site specific safety requirements before attempting integration. Successful bench testing will not be described as certification or as proof of compliance for a commercial installation.

By linking the standards to specific design decisions and recorded bench checks, the team can demonstrate that safety and professional engineering requirements have influenced the controller's development rather than simply appearing in a reference list.

#### Project Specific Ethics and Sustainability Actions (E1)
--- 

The goal of this project is to determine whether a variable speed circulation pump controller can reduce electrical power use without sacrificing safe water flow or acceptable temperature performance. The team will evaluate the controller through a physical bench experiment, using simulation to plan initial operating conditions and compare predicted results with measured behavior. This approach creates ethical responsibilities in the way the system is designed, tested, documented, and presented to Lochinvar.

The team will use the IEEE Code of Ethics as a guide for prioritizing public safety, reporting technical results accurately, recognizing the limits of its expertise, and considering the environmental and social effects of engineering decisions. A lower pump-power reading will not be treated as a successful outcome if the test violates an approved flow, temperature, or safety limit.


#### Public Safety and Engineering Responsibility

The bench loop will contain heated water, electrical power, and pressurized or circulating components. Reducing pump speed too far could cause inadequate circulation or excessive water temperature rise, depending on the selected heat source and loop design. The controller will therefore enforce the documented safe minimum flow and operating limits of the actual bench equipment, rather than relying on a limit assumed from a different heater or pump.

Before the bench is energized, the team will review the design and test plan with the faculty supervisor. Authorized personnel will inspect the electrical and plumbing arrangements where required. Independent heat-source and electrical protections will remain active. The team will also define how the controller should respond to failed sensors, invalid measurements, communication loss, and abnormal temperature or flow readings. Unsafe conditions will first be evaluated in simulation or through an approved isolated test; the team will not intentionally defeat protective devices to demonstrate a fault.

If the bench cannot maintain the approved minimum flow, temperature limits, or other safety requirements at a proposed pump setting, that setting will be rejected even if it uses less electrical power. Any later testing on Lochinvar equipment will require a separate safety and interface review because the bench results do not automatically establish safe operation on a commercial system.

#### Accuracy, Data Integrity, and Technical Reporting

The project's main conclusions will come from measured bench data, not simulation results alone. The team plans to record real pump and drive electrical input power, water flow, inlet and outlet temperatures, pump commands, applied heating demand conditions, controller status, and timestamps. Measurements will be accompanied by equipment identification, calibration information, test conditions, and known uncertainty.

The preliminary testing plan includes five paired baseline and controlled runs at each of three operating conditions. The team will report the average percentage electrical power savings, variation between runs, and a 95% confidence interval where the data and assumptions support it. Temperature stability and response time will also be reported using defined measurement windows. Unsuccessful trials, unexpected behavior, and excluded or incomplete measurements will be documented rather than hidden.

Simulation will be used to select initial controller settings and test conditions. After the bench experiments, predicted and measured responses will be compared under equivalent conditions, and model error will be reported. The team will distinguish between initial predictions, updated simulation results, and physical measurements. The preliminary goal of at least 10% electrical power reduction will be described as a design target, not a result already achieved. Any conclusions about future use in the Regent will be identified as potential applications rather than proven commercial performance.

#### Intellectual Property and Confidentiality

Because Lochinvar is sponsoring the project, the team may receive technical information, software resources, specifications, or guidance that should not be distributed publicly. The team will review what may be included in public reports, presentations, and GitHub repositories, and will follow sponsor and university requirements for confidential or proprietary material.

Manufacturer information and outside research will be cited appropriately. The team will acknowledge contributions from individual members, faculty, and Lochinvar personnel. If optional testing at Lochinvar's laboratory takes place, any resulting data, photographs, or equipment details will be shared only with the necessary permission.

#### Environmental Sustainability and Energy Efficiency

Reducing unnecessary circulation pump electrical consumption could reduce energy use, but lower pump speed does not guarantee lower overall energy consumption. A change in flow may affect temperature response, heating time, or the amount of energy required by the heat source. For this reason, the team will measure pump and drive real electrical input power under matched bench conditions and will discuss any observed tradeoffs in thermal performance.

The project will report electrical power savings for the tested pump and operating conditions without assuming the same savings will occur in every commercial installation. Any estimate of longer term energy or emissions reductions will state its assumptions and distinguish measured values from projections. The team will also consider the cost and environmental impact of sensors, electronics, wiring, water use, and replacement parts. Where practical and safe, compatible existing equipment will be reused.

#### Economic and Social Responsibility

The controller could provide a practical benefit if electrical savings justify the added hardware, integration, and maintenance requirements. The team will therefore consider component costs and implementation complexity alongside the measured savings. The current bench budget is incomplete until the final pump, heat source, and supporting equipment are confirmed, and any economic comparison will acknowledge those missing costs.

The bench experiment is not itself a commercial hot water installation, but the intended future application could affect building operators, maintenance personnel, and people who rely on hot water. The team will therefore consider reliability, serviceability, temperature control, and safety when judging whether the control strategy is worth developing further. Optional testing at Lochinvar's laboratory may help evaluate these questions in a more representative setting, but the project will not depend on that opportunity.

#### Ethical Verification and Accountability

The following table connects the team's ethical responsibilities to actions and evidence that can be reviewed at the end of Capstone 2.



| Ethical consideration | Planned action | Verification evidence |
|---|---|---|
| Public safety | Maintain the selected bench equipment's approved flow and temperature limits, preserve independent protections, and obtain a faculty review before energizing. | Approved test plan, equipment limit records, inspection notes, and bench safety test results. |
| Responsible fault testing | Define sensor, communication, and abnormal condition responses without bypassing protective devices. | Simulation records, approved fault injection procedures, and measured controller responses. |
| Data integrity | Record calibrated measurements, operating conditions, timestamps, uncertainty, unsuccessful runs, and data processing steps. | Raw datasets, calibration records, test logs, and analysis files. |
| Honest reporting | Distinguish simulation predictions, measured bench results, preliminary targets, and optional future application claims. | Model error comparisons, technical report, plots, and clearly labeled results. |
| Intellectual property | Respect Lochinvar's restrictions and cite technical information and outside research appropriately. | Reviewed public documents, repository contents, and reference list. |
| Environmental sustainability | Measure real electrical input power and evaluate changes in thermal performance rather than assuming lower speed always means better overall efficiency. | Paired bench measurements, energy calculations, and stated assumptions. |
| Economic responsibility | Compare measured benefits with the cost and complexity of the proposed hardware and test setup. | Updated budget, component list, and preliminary cost benefit discussion. |
| Stakeholder welfare | Consider safe temperature, reliable circulation, maintainability, and the limits of bench to commercial transfer. | Temperature and flow results, safety checks, and documented limitations. |



The team will review these responsibilities throughout design development and before physical testing. If a safety concern, measurement problem, or equipment incompatibility is discovered, the affected test or design decision will be reconsidered before the result is presented as acceptable. This approach will help ensure that the project produces useful engineering evidence while maintaining the professional responsibility expected of a sponsor supported capstone design.

#### Benefits and Disadvantages (J1)
---

The development of the Variable Speed Circulation Pump Controller could provide economic, environmental, and societal benefits to the population. By adjusting the circulation pump speed according to heating demand, water flow rate, and outlet temperature, the proposed system aims to reduce unnecessary electrical energy consumption while maintaining reliable hot water performance. Some stakeholders may face disadvantages due to the implementation of additional control hardware, sensors, and software. Explaining these disadvantages will be essential to ensuring that the proposed project will benefit its intended users without compromising the safety, reliability, or economic feasibility. 

1. Building Occupants and Hot-Water Users(Societal Impact)

This project would benefit commercial building occupants through improved hot water temperature stability and more reliable circulation during demand changes. The controller could help maintain consistent system performance while reducing unnecessary pump speed operation. This could help reduce the energy the pump needs to circulate at certain times. 

However, building occupants could be disadvantaged if the pump operates below the required circulation flow or fails to respond appropriately to changing demand. A controller malfunction or failure of the system's safety protections could result in inconsistent water temperatures, insufficient hot water availability, or unsafe operating conditions. These disadvantages could negatively affect commercial facilities with high or fluctuating hot water demands [4].


2. Maintenance and Service Technicians (Economic and Societal Impact)

Maintenance technicians could benefit from the additional operating measurements that could be collected by the controller. The flow rate, temperature, and pump operating data could assist the technician in identifying any abnormal conditions as well as troubleshooting the system performance [2]. 

However, introducing additional sensors, wiring, electronic control, and software could also be a disadvantage to the technician. Adding these components could make the system more complex for maintenance and troubleshooting. Technicians may require additional training to understand the controller's operation and diagnose potential sensor or control system failures, increasing maintenance time and labor costs. Having incorrect maintenance procedures could affect the equipment's reliability and its safe operation.

3. Commercial Facility Owners and Building Operators (Economic Impact)

Commercial facility owners could benefit from reduced electrical operating expenses if the variable speed pump consumes less power during lower demand conditions. Reduced pump operations may also improve energy management and provide opportunities for long term operating cost savings [4].

However, additional controller hardware, sensors, installation requirements, and maintenance could increase the initial cost of implementing the system. If the electrical savings are smaller than anticipated, the cost of the system could outweigh its financial benefits. Unexpected controller failures could also create additional maintenance expenses or equipment downtime.


4. Lochinvar Engineering Team and Company (Economic and Societal Impact)

Lochinvar could benefit from a control strategy that demonstrates reduced pump electrical consumption while maintaining acceptable temperature and flow conditions. Successful experimental results could provide useful data for future commercial water heating applications and potential improvements in energy efficiency. 

However, Lochinvar could also be at a disadvantage if the controller has reliability problems, inaccurate measurements, or equipment failure in the future. A controller failure could result in additional warranty expenses, engineering modification, customer dissatisfaction, or any potential liability associated with inadequate performance.

5. Environment and Local Communities (Environmental and Economic Impact)

The environment and surrounding communities could benefit from reduced electricity consumption. Reduced energy demand could contribute to lower greenhouse gas emissions, depending on the electricity generation source, while supporting more efficient resource utilization in commercial facilities.

However, the additional sensors, electronic components, and controller hardware introduce material consumption and eventual electronic waste. If the equipment has a short operating life or the controller fails to provide measurable energy savings, the environmental benefits could be reduced or offset by the resources required to manufacture, maintain, and replace the additional components.


#### Mitigation Strategies for the Disadvantages (J2)
---

To address the potential disadvantages identified in the Benefits and Disadvantages to affected Groups, the team will incorporate specific mitigation measures into the controller design, simulation, and physical testing process. Additional measures will be recommended to Lochinvar and the team's faculty advisors for consideration before future commercial implementation. These strategies are intended to reduce safety risks, improve equipment reliability, limit unnecessary costs, and ensure that energy savings do not compromise the water-heating performance.

1. Building Occupants and Hot-water Users

To reduce the possibility of unstable temperatures or inadequate circulation, the controller will continuously monitor water flow and inlet and outlet temperatures through the Sensor and Data Acquisition Subsystem. The control algorithm will enforce the minimum circulation flow established for the approved bench equipment and will be designed to maintain outlet temperature within ±4°F of the selected setpoint under defined steady state testing conditions.

If measured flow or temperature exceeds the established operating limits, the controller will initiate a predefined fault response approved during the bench safety review. The system will not override the heat source's existing safety protections. Before recommending future implementation on the Regent, the team will verify the manufacturer's minimum-flow requirements, acceptable temperature limits, and appropriate independent protective controls.

2. Maintenance and Service Technicians

To reduce maintenance complexity, the team will develop a clear wiring diagram that the technicians can follow when troubleshooting. There will also be documentation of sensor connections and spec sheets for the different components. These will identify how each sensor, microcontroller, and pump work and communicate with each other.

When a sensor fault is detected, the controller will initiate the predefined fault response established during bench testing rather than continuing normal pump speed adjustments using unreliable measurements. The team will document the expected sensor operating ranges and the corresponding fault responses. Recorded measurements and fault information will be used to assist technicians in identifying whether abnormal operation originates from a sensor, microcontroller, or pump interface. These measures will help reduce troubleshooting time and improve the reliability of future maintenance procedures.

3. Commercial Facility Owners and Building Operators (Economic Impact)

To reduce the possibility of unnecessary installation expenses and operating costs, the team will conduct an economic evaluation comparing the additional hardware costs with the potential electrical savings achieved through variable speed operation.

The team will evaluate whether the controller achieves the project's target of at least a 10% reduction in measured pump and drive real electrical input power under qualifying operating conditions. This reduction will only be considered successful if the system continues to meet the established temperature stability, minimum flow, and safety requirements [8].

Measured savings will be used to estimate potential electricity cost reductions and assess whether the additional system cost is economically justified. If testing indicates that the energy savings are insufficient to offset implementation costs, the team will document these limitations and recommend design improvements before commercial adoption.

4. Lochinvar Engineering Team and Company

To reduce the risk of equipment failure, unreliable performance, and unnecessary development costs, the team will validate the proposed control strategy through simulation and physical bench testing before recommending commercial implementation.

The controller will be tested under low, medium, and high demand conditions. The preliminary testing plan will include five paired baseline and controlled runs at each operating condition, resulting in 15 paired comparisons. During these tests, the team will record outlet temperature, water flow rate, pump electrical power consumption, and controller response. This testing will allow the team to evaluate temperature stability, minimum-flow compliance, electrical power reduction, and repeatability before recommending the controller for future commercial applications.

The system will also preserve the heat source's existing safety functions and enforce approved operating limits. Any future integration with Lochinvar equipment will require separate compatibility testing and safety approval. These procedures will provide Lochinvar with documented evidence of the controller's performance and limitations before considering further development.

5. Environment and Local Communities

To reduce the environmental impact of additional electronic components, the team will prioritize reliable hardware and use available equipment from Lochinvar and Tennessee Tech where practical. Components will be selected based on their compatibility with the system's operating requirements to reduce unnecessary replacement or redesign.

The team will compare measured pump electrical power consumption between constant-speed baseline operation and variable speed controlled operation under equivalent low-, medium-, and high-demand conditions rather than assuming that reducing pump speed automatically results in energy savings [4].

For future commercial development, the team recommends evaluating component service life, repairability, and proper electronic-waste disposal. These measures will help determine whether the electrical savings provide a meaningful long term environmental benefit.

 
## Resources


### Budget

The proposed budget covers all six subsystems required to develop and evaluate the variable speed pump controller. The selected design combines flow rate measurements, the boiler's firing rate signal, and outlet temperature feedback to adjust pump speed according to operating conditions.

The budget includes sensing and data acquisition, control hardware and programming, pump speed control equipment, hydraulic components, performance monitoring instruments, and data logging and simulation resources. The estimates are preliminary allowances and assume that the existing Lochinvar water heater, circulation pump, and Keyence flow sensor can be reused where compatible. Existing laboratory equipment and available software are also assumed to be available at no additional cost.

**1. Sensor and Data Acquisition Subsystem**
<p align="center">
<img width="930" height="290" alt="image" src="https://github.com/user-attachments/assets/5b57a5b0-8418-431c-8efe-411c7938d2df" />
</p>
Justification: The flow sensor measures hot-water demand, while the temperature sensors measure system thermal performance. Signal conditioning components and wiring provide reliable connections to the controller, and the data acquisition interface allows sensor measurements to be read and recorded. The budget assumes the existing flow sensor is compatible with the selected control hardware.

**2. Microcontroller and Control Logic Subsystem**
<p align="center">
<img width="922" height="350" alt="image" src="https://github.com/user-attachments/assets/ceb87af1-52ad-4600-83e7-ed0697139abc" />
</p>
Justification: The microcontroller executes the control logic and processes the flowrate, firing rate, and temperature measurements. The analog input interface is needed to read the boiler's 0–10 V firing rate signal, while the analog output interface generates the appropriate command for the pump speed control equipment. The connection hardware helps protect and organize the electronics. Final component selection must account for signal ranges, electrical isolation, and compatibility with the existing boiler and drive.

**3. Pump and Motor Control Subsystem**
<p align="center">
<img width="916" height="266" alt="image" src="https://github.com/user-attachments/assets/1311b881-9dbe-4518-85d0-45c9e92654bb" />
</p>
Justification: The speed controller adjusts pump operation based on the command from the microcontroller. The VFD is a preliminary option for an appropriately compatible AC motor. The existing pump and motor specifications must be checked before selecting the drive. Wiring and electrical protection components support safe integration. If the existing pump uses a different motor type or has an integrated electronic controller, a different compatible speed control solution may be required.

**4. Water Heating and Hydraulic Subsystem**
<p align="center">
<img width="928" height="414" alt="image" src="https://github.com/user-attachments/assets/980f4cd6-dc09-4630-a1bd-6dc61566811c" />
</p>
Justification: The water heater and circulation pump provide the existing test platform. Fittings and connectors support proper hydraulic connections, while valves allow the system to be configured for testing and insulation helps reduce heat loss. Seals and leak prevention materials support safe, reliable operation. The estimate assumes that the existing equipment is functional and that major plumbing modifications are unnecessary.

**5. Monitoring and Performance Evaluation Subsystem**
<p align="center">
<img width="916" height="264" alt="image" src="https://github.com/user-attachments/assets/fbc19844-e9e7-49d8-9760-4bc164dbd20a" />
</p>
Justification: Electrical power measurements allow the team to compare pump energy consumption under fixed speed and variable speed operation. An independent temperature instrument provides a way to verify the installed sensors, while measurement accessories support data collection during testing. These measurements are necessary to determine whether the proposed controller reduces energy use without negatively affecting outlet-temperature performance.

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

The revised design contains five subsystems. Each team member has a primary subsystem responsibility, while Subsystem 2 will be a group effort with a designated documentation lead. The proposed lead below should be confirmed by the team before the updated ownership list is submitted to the professor.

| Subsystem | Primary owner or lead | Responsibility |
|---|---|---|
| 1. Sensor and Data Acquisition | Skyler Raines | Select and integrate flow and temperature sensors, condition measurements, verify sensor interfaces, and provide reliable inputs to the controller. |
| 2. Microcontroller and Control Logic | Group effort; **lead: Jocelyn Smith** | Develop and document the controller, fault responses, command limits, and control algorithm. Integrate contributions from all four members. |
| 3. Pump, Motor Control, and Hydraulic System | Danielle Wolford | Develop the pump interface, circulation-loop and hydraulic model, and minimum-flow protection for the bench setup. |
| 4. Monitoring, Performance Evaluation, and Bench Testing | Kendall Arnold | Plan and carry out the approved physical bench tests, coordinate repeated trials, and evaluate whether performance targets are met. |
| 5. Data Logging and Simulation | Jocelyn Smith | Develop the simulation, establish preliminary test conditions, record and store experimental data, compare model predictions with bench measurements, and report model error. |


* Subsystem 1 — Skyler Raines. Skyler will lead sensor selection and integration, including flow measurement, temperature measurement, signal conditioning, and communication of validated sensor readings to the controller.
	* Responsible team member and rationale: Skyler was assigned this subsystem because her background in Electronics and Computer Engineering Technology provides relevant knowledge of electrical connections and hardware components. Her experience assembling electrical panels and working with wiring during her internship will help her connect sensors, integrate their wiring with the microcontroller, and ensure the hardware is properly assembled. Her troubleshooting experience will also be useful for identifying faulty connections and resolving issues that could affect the accuracy and reliability of collected data. Additionally, her current Control Systems coursework provides relevant knowledge.
  
* Subsystem 2 — Group Effort, with Jocelyn Smith proposed as lead. Jocelyn will coordinate the control algorithm documentation and integrate the control software with the simulation and data recording requirements. Skyler will contribute sensor interface information, Danielle will contribute pump command and hydraulic limit requirements, and Kendall will contribute test and verification requirements. The final lead designation and individual contributions will be confirmed by the team.
	* Responsible team member and rationale: Jocelyn was assigned this subsystem because of her experience with C/C++, Assembly, Python, and control system analysis. These skills will be very useful when developing the programming needed to process sensor data and adjust pump speed based on the system's operating conditions. Her background in circuit analysis will also help with understanding the connections between the microcontroller, sensors, and pump control hardware.

* Subsystem 3 — Danielle Wolford. Danielle will lead the combined pump, motor control, and hydraulic design, including the compatible speed command interface, water loop requirements, hydraulic model, and minimum flow safeguards.
	* Responsible team member and rationale: Danielle was assigned this subsystem because her experience assembling electrical panels and troubleshooting electrical hardware provides a foundation for integrating the pump's motor control components. Her background in Electronics and Computer Engineering Technology will help her work with electrical connections between the pump, motor control hardware, and microcontroller. Her troubleshooting skills will also be valuable for diagnosing wiring problems, addressing hardware malfunctions, and helping ensure the pump control system operates reliably during testing.
  
* Subsystem 4 — Kendall Arnold. Kendall will lead the physical bench test plan and performance evaluation, including repeatable operating conditions, matched baseline and controlled trials, temperature and power measurements, and safety verification evidence.
	* Responsible team member and rationale: Kendall was assigned this subsystem because of her background in applied physics and experience conducting experimental projects involving data collection, analysis, and comparison of results. She is also experiences with C/C++, assembly, and currently in Control Systems. These skills will be valuable when evaluating system performance under different operating conditions and determining whether the proposed control strategy reduces electrical energy consumption without compromising the performance of the heater.

* Subsystem 5 — Jocelyn Smith. Jocelyn will lead simulation development, data recording and storage design, model to bench comparison, and reporting of model error. This subsystem will provide datasets to Kendall for performance evaluation rather than taking over operation of the bench experiment.
	* Responsible team member and rationale: Jocelyn was assigned this subsystem because of her experience with MATLAB, Python, and control system analysis. These skills will help her organize experimental data, develop simulations, and analyze how changes in pump speed affect the water heating system. Because this subsystem works closely with the Microcontroller and Control Logic subsystem, assigning both to the same team member will also help maintain consistency between the controller design and performance analysis.


### Timeline

<p align="center">
<img width="1481" height="683" alt="image" src="https://github.com/user-attachments/assets/9c039826-889b-4d0b-a2d1-7609de5e0b7d" />

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

[12] IEEE, “IEEE Code of Ethics,” IEEE Circuits and Systems Society. [Online]. Available: [https://ieee-cas.org/about/ieee-code-ethics]. [Accessed: Nov. 14, 2026].

## ADD 2 REFERENCES

[15] Grundfos, *UPMS Data Booklet*, "UPMS 15-78 130: Performance Curves and Technical Data," p. 11. [Online]. Available: [https://api.grundfos.com/literature/Grundfosliterature-6910086.pdf]. [Accessed: Nov. 18, 2026].
[16] U.S. Department of Energy, *DOE Fundamentals Handbook: Thermodynamics, Heat Transfer, and Fluid Flow*, vol. 1, DOE-HDBK-1012/1-92, 1992. [Online]. Available: [https://www.energy.gov/sites/default/files/2026-04/DOE-HDBK-1012-92_VOL1.pdf]. [Accessed: Nov. 18, 2026].

[17] Grundfos, "How to Find Installation and Operation Manuals Online," Grundfos Support. [Online]. Available: [https://www.grundfos.com/us/support/how-to-guides/how-to-find-installation-and-operation-manuals-online]. [Accessed: Nov. 18, 2026].

## Statement of Contributions


Jocelyn Smith: High Level Solution, Atomic Subsystems 2 and 5 (Microcontroller and Control Logic, Data Logic and Simulation Subsystem), Divison of Labor

Skyler Raines: Timeline, Ethical, Professional, and Standards Considerations, Atomic Subsystem 1 (Sensor and Data Acquisition Subsystem)

Kendall Arnold: Introduction, Restating the Fully Formulated Problem, Atomic Subsystem 4 (Monitoring, Performance Evaluation, and Bench Testing Subsystem), Division of Labor, Budget

Danielle Wolford: Comparative analysis of potential solutions, Atomic Subsystem 3 (Pump, Motor Control, and Hydraulic System)

