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

Energy efficiency involves meeting the required system performance while using as little energy as possible. In a hot water system, the circulation pump does not necessarily need to operate at maximum speed under all operating conditions. Reducing pump speed when demand is lower can reduce unnecessary electrical power consumption.

In addition to controlling pump speed, evaluating energy efficiency requires measuring the actual electrical power consumed by the pump. Electrical power can be estimated using voltage and current. However, for AC powered equipment, their product represents apparent power rather than actual real power because of power factor. Therefore, a true RMS power meter capable of measuring real power will be used at the pump's electrical input to account for consumption and losses associated with the motor and its internal drive electronics. This provides a more accurate measurement of total electrical consumption and allows energy use to be compared between constant speed and variable speed operation to determine whether adjusting pump speed produces measurable energy savings.

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

The controller design is based on the relationship between pump speed, circulation flow, electrical power, and heat transfer. These relationships will first be used to estimate system behavior and develop the simulation model. The actual bench equipment will then be used to test the predictions. The proposed Grundfos UPMS 15-78 130 AR is a candidate pump, but the exact model and supported control interface must be confirmed before its published ratings are treated as the installed system's ratings.

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

### Regent Heat-Transfer Model

The relationship between circulation flow rate and temperature rise can also be evaluated using the published specifications of the Lochinvar Regent IWH0500, the intended application for this project. This model has a rated heating input of 500,000 Btu/h and a thermal efficiency of 96%, resulting in an approximate heat output of 480,000 Btu/h.

Using the heat-transfer relationship:

$$
\Delta T = \frac{\dot{Q}_h}{500(GPM)}
$$

At an illustrative flow rate of 40 GPM:

$$
\Delta T = \frac{480,000}{500(40)}
$$

$$
\boxed{\Delta T = 24^\circ F}
$$

At an illustrative flow rate of 20 GPM:

$$
\Delta T = \frac{480,000}{500(20)}
$$

$$
\boxed{\Delta T = 48^\circ F}
$$

These calculations assume that the full 480,000 Btu/h heat output is transferred to the water. They demonstrate that reducing water flow increases the temperature rise required across the heat exchanger when the heat-transfer rate remains constant. This relationship is important when evaluating how much circulation flow can be reduced without exceeding the water heater's allowable temperature limits. The flow rates used in these examples are illustrative and do not represent verified operating points for the selected circulation pump.

During bench testing, circulation flow, inlet and outlet water temperatures, and pump electrical power will be monitored at different pump speeds. These measurements will be used to evaluate changes in flow rate, temperature rise, and pump energy consumption. The manufacturer's minimum required flow rate will also be established to identify the lowest acceptable operating condition while maintaining the required system performance.

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


### 3) Pump, Motor Control, and Hydraulic System

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


### ----------------------------------------------------old 4--------------

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


### 4) Monitoring, Performance Evaluation, and Bench Testing Subsystem

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


### 5) Data Logging and Simulation Subsystem

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

The variable speed circulation pump controller will be developed and evaluated using a dedicated physical bench test rather than depending on access to commercial heating equipment. The bench will include a variable-speed pump, heat source, water circulation loop, sensors, power connections, and the actual controller. Because the experiment involves electricity, moving water, and heat, the team must consider the standards and safety procedures that apply to the equipment actually selected for the bench. The standards will guide component selection, wiring, plumbing, control limits, fault responses, and testing methods.

The following table explains how each standard or regulation may influence the design and what evidence the team plans to collect. Applicability depends on the final equipment, installation, jurisdiction, and institutional requirements. The team will confirm the relevant editions and provisions with the faculty supervisor and authorized laboratory personnel before implementation. The verification activities described here are part of the capstone design process; they do not constitute formal certification or a claim of full code compliance.



| Standard or regulation | How it affects the proposed bench design | Planned verification evidence | Applicability or detail still to confirm |
|---|---|---|---|
| NFPA 70 (National Electrical Code), including Article 430 where applicable | Guides the review of motor branch circuit wiring, conductor sizing, grounding, overcurrent protection, disconnecting means, and the selected pump or motor control equipment. Low voltage control circuits will be appropriately separated or isolated from hazardous-voltage circuits. | Power and control schematics, component ratings, protective device review, and an inspection by qualified or institutionally authorized personnel before energizing the bench. | Adopted code edition, relevant articles, the pump's electrical design, and whether Article 430 provisions apply to each installed component. |
| OSHA 29 CFR 1910.147 and Tennessee Tech hazardous energy procedures, as applicable | Informs the procedure for isolating electrical, thermal, pressure, and other hazardous energy before servicing, modifying, or repairing the bench setup. The team will not assume that switching off the controller makes the apparatus safe to work on. | Written isolation and verification procedure; authorized pre work checks and records where required. | Regulatory applicability to the educational laboratory and the institution's required procedures. |
| UL 60730-1, where applicable to the selected automatic electrical control | Provides a safety design reference for abnormal operation, loss of inputs, controller resets, and safe responses to faults. Software will not be treated as a substitute for independent equipment protection. | Documented fault response requirements, simulation of unsafe scenarios, and approved bench fault injection tests that do not defeat protective devices. | Applicable clauses, whether the controller falls within the standard's scope, and whether any product certification would be required for future commercialization. |
| Applicable plumbing and mechanical requirements; International Plumbing Code as a reference where appropriate | Informs the selection of temperature and pressure rated tubing, fittings, reservoir, valves, and connections. The water loop will be checked for leakage and safe operation within the selected components' ratings. | Component datasheets, bench loop schematic, approved connection review, and supervised leak inspection before heated operation. | Local code applicability, pressure relief and backflow requirements, and the approved configuration of the final bench loop. |
| ASHRAE Standard 188 | Relevant primarily to future building water system applications and water management responsibilities. The bench will not be presented as a commercial domestic hot water installation. If the controller is later connected to commercial equipment, it must not undermine existing water management protections. | Written applicability review, identification of the boundary between the bench experiment and a future building installation, and a future integration safety review if sponsor testing is approved. | Whether and how the standard applies to any eventual commercial installation; not automatically a direct bench-test requirement. |
| ASHRAE Standard 90.1 | Provides context for energy efficient building systems and future commercial use, but does not automatically establish a compliance requirement for the capstone bench prototype. | Measured pump and drive real electrical input power comparisons, documented test conditions, and a written applicability statement. | Applicable edition and whether specific provisions would apply to a future commercial product or installation. |
| Selected pump, heat source, and sensor manufacturer instructions | Establish the actual safe operating limits for the bench, including maximum temperature, permitted flow range, pressure, electrical ratings, and supported pump control interface. These equipment specific limits take priority over unverified assumptions. | Verified datasheets and nameplates, a documented limits table, wiring/interface review, calibrated measurements, and approved bench checks of temperature and minimum flow. | Final component models, approved minimum circulation flow in GPM, maximum temperature, pump-control method, and any required independent protective devices. |


#### Standards Verification and Documentation Procedure

* 1. Identify Applicable Requirements: Once the bench pump, heat source, sensors, and electrical components are selected, the team will review their manufacturer documentation and the relevant standards, codes, and Tennessee Tech laboratory procedures. Unconfirmed requirements will be listed as pending instead of being assigned assumed values.
 
* 2. Connect requirements to the design: Each applicable requirement will be linked to a specific design choice, such as electrical isolation, motor protection, pressure rated fittings, a minimum flow limit, a maximum temperature limit, or a defined controller fault response. The relevant requirement will also be linked to a verification method.

* 3. Review the bench before energizing it: The team will present the bench schematic, component ratings, wiring plan, hydraulic layout, heat source protection, and proposed test procedure to the faculty supervisor. Work requiring qualified electrical or plumbing personnel will be performed only by authorized individuals. The bench will not be energized until the required review and approval are complete.

* 4. Verify safety on the physical bench: The team will check electrical isolation and protective devices, inspect connections for leaks, confirm the documented temperature and minimum flow limits, and test defined fault responses through approved methods. Simulation may be used to explore dangerous conditions, but it will not replace the required physical verification of safety related limits. Fault testing must not bypass the heat source's or pump's independent protections.

* 5. Document the evidence: For each requirement, the team will record the source, expected result, test procedure, measured result, uncertainty where relevant, and any corrective action. Incomplete or failed checks will remain visible in the documentation until resolved.
 
* 6. Review changes: If the selected heat source, pump, controller, sensor, or interface changes, the team will revisit the affected limits, schematics, test procedures, and applicable standards before repeating the relevant verification steps. Any optional testing at Lochinvar's laboratory will require a separate equipment-specific review and approval.
 
#### Remaining Standards Related Confirmations

The final bench heat source, pump configuration, supported speed control interface, safe minimum circulation flow, maximum operating temperature, and required independent protections have not all been confirmed. These values must be obtained from the selected equipment and approved test design before heated operation. The team must also confirm which electrical, plumbing, and institutional procedures apply to the final setup.

Testing at Lochinvar's laboratory near the end of Capstone 2 remains an optional stretch goal. If it becomes possible, the team will review the actual equipment's operating limits, electrical and signal interfaces, water management protections, and site specific safety requirements before attempting integration. Successful bench testing will not be described as certification or as proof of compliance for a commercial installation.

By linking the standards to specific design decisions and recorded bench checks, the team can demonstrate that safety and professional engineering requirements have influenced the controller's development rather than simply appearing in a reference list.

#### Project Specific Ethics and Sustainability Actions (E1)
--- 

The goal of this project is to determine whether a variable-speed circulation pump controller can reduce electrical power use without sacrificing safe water flow or acceptable temperature performance. The team will evaluate the controller through a physical bench experiment, using simulation to plan initial operating conditions and compare predicted results with measured behavior. This approach creates ethical responsibilities in the way the system is designed, tested, documented, and presented to Lochinvar.

The team will use the IEEE Code of Ethics as a guide for prioritizing public safety, reporting technical results accurately, recognizing the limits of its expertise, and considering the environmental and social effects of engineering decisions. A lower pump-power reading will not be treated as a successful outcome if the test violates an approved flow, temperature, or safety limit.


#### Public Safety and Engineering Responsibility

The bench loop will contain heated water, electrical power, and pressurized or circulating components. Reducing pump speed too far could cause inadequate circulation or excessive water-temperature rise, depending on the selected heat source and loop design. The controller will therefore enforce the documented safe minimum flow and operating limits of the actual bench equipment, rather than relying on a limit assumed from a different heater or pump.

Before the bench is energized, the team will review the design and test plan with the faculty supervisor. Authorized personnel will inspect the electrical and plumbing arrangements where required. Independent heat-source and electrical protections will remain active. The team will also define how the controller should respond to failed sensors, invalid measurements, communication loss, and abnormal temperature or flow readings. Unsafe conditions will first be evaluated in simulation or through an approved isolated test; the team will not intentionally defeat protective devices to demonstrate a fault.

If the bench cannot maintain the approved minimum flow, temperature limits, or other safety requirements at a proposed pump setting, that setting will be rejected even if it uses less electrical power. Any later testing on Lochinvar equipment will require a separate safety and interface review because the bench results do not automatically establish safe operation on a commercial system.

#### Accuracy, Data Integrity, and Technical Reporting

The project's main conclusions will come from measured bench data, not simulation results alone. The team plans to record real pump and drive electrical input power, water flow, inlet and outlet temperatures, pump commands, applied heating-demand conditions, controller status, and timestamps. Measurements will be accompanied by equipment identification, calibration information, test conditions, and known uncertainty.

The preliminary testing plan includes five paired baseline and controlled runs at each of three operating conditions. The team will report the average percentage electrical power savings, variation between runs, and a 95% confidence interval where the data and assumptions support it. Temperature stability and response time will also be reported using defined measurement windows. Unsuccessful trials, unexpected behavior, and excluded or incomplete measurements will be documented rather than hidden.

Simulation will be used to select initial controller settings and test conditions. After the bench experiments, predicted and measured responses will be compared under equivalent conditions, and model error will be reported. The team will distinguish between initial predictions, updated simulation results, and physical measurements. The preliminary goal of at least 10% electrical-power reduction will be described as a design target, not a result already achieved. Any conclusions about future use in the Regent will be identified as potential applications rather than proven commercial performance.

#### Intellectual Property and Confidentiality

Because Lochinvar is sponsoring the project, the team may receive technical information, software resources, specifications, or guidance that should not be distributed publicly. The team will review what may be included in public reports, presentations, and GitHub repositories, and will follow sponsor and university requirements for confidential or proprietary material.

Manufacturer information and outside research will be cited appropriately. The team will acknowledge contributions from individual members, faculty, and Lochinvar personnel. If optional testing at Lochinvar's laboratory takes place, any resulting data, photographs, or equipment details will be shared only with the necessary permission.

#### Environmental Sustainability and Energy Efficiency

Reducing unnecessary circulation pump electrical consumption could reduce energy use, but lower pump speed does not guarantee lower overall energy consumption. A change in flow may affect temperature response, heating time, or the amount of energy required by the heat source. For this reason, the team will measure pump-and-drive real electrical input power under matched bench conditions and will discuss any observed tradeoffs in thermal performance.

The project will report electrical-power savings for the tested pump and operating conditions without assuming the same savings will occur in every commercial installation. Any estimate of longer term energy or emissions reductions will state its assumptions and distinguish measured values from projections. The team will also consider the cost and environmental impact of sensors, electronics, wiring, water use, and replacement parts. Where practical and safe, compatible existing equipment will be reused.

#### Economic and Social Responsibility

The controller could provide a practical benefit if electrical savings justify the added hardware, integration, and maintenance requirements. The team will therefore consider component costs and implementation complexity alongside the measured savings. The current bench budget is incomplete until the final pump, heat source, and supporting equipment are confirmed, and any economic comparison will acknowledge those missing costs.

The bench experiment is not itself a commercial hot water installation, but the intended future application could affect building operators, maintenance personnel, and people who rely on hot water. The team will therefore consider reliability, serviceability, temperature control, and safety when judging whether the control strategy is worth developing further. Optional testing at Lochinvar's laboratory may help evaluate these questions in a more representative setting, but the project will not depend on that opportunity.

#### Ethical Verification and Accountability

The following table connects the team's ethical responsibilities to actions and evidence that can be reviewed at the end of Capstone 2.



| Ethical consideration | Planned action | Verification evidence |
|---|---|---|
| Public safety | Maintain the selected bench equipment's approved flow and temperature limits, preserve independent protections, and obtain a faculty review before energizing. | Approved test plan, equipment-limit records, inspection notes, and bench safety-test results. |
| Responsible fault testing | Define sensor, communication, and abnormal condition responses without bypassing protective devices. | Simulation records, approved fault-injection procedures, and measured controller responses. |
| Data integrity | Record calibrated measurements, operating conditions, timestamps, uncertainty, unsuccessful runs, and data processing steps. | Raw datasets, calibration records, test logs, and analysis files. |
| Honest reporting | Distinguish simulation predictions, measured bench results, preliminary targets, and optional future application claims. | Model error comparisons, technical report, plots, and clearly labeled results. |
| Intellectual property | Respect Lochinvar's restrictions and cite technical information and outside research appropriately. | Reviewed public documents, repository contents, and reference list. |
| Environmental sustainability | Measure real electrical input power and evaluate changes in thermal performance rather than assuming lower speed always means better overall efficiency. | Paired bench measurements, energy calculations, and stated assumptions. |
| Economic responsibility | Compare measured benefits with the cost and complexity of the proposed hardware and test setup. | Updated budget, component list, and preliminary cost benefit discussion. |
| Stakeholder welfare | Consider safe temperature, reliable circulation, maintainability, and the limits of bench to commercial transfer. | Temperature and flow results, safety checks, and documented limitations. |



The team will review these responsibilities throughout design development and before physical testing. If a safety concern, measurement problem, or equipment incompatibility is discovered, the affected test or design decision will be reconsidered before the result is presented as acceptable. This approach will help ensure that the project produces useful engineering evidence while maintaining the professional responsibility expected of a sponsor supported capstone design.

#### Benefits and Disadvantages (J1)
---

The development of the Variable-Speed Circulation Pump Controller could provide economic, environmental, and societal benefits to the population. By adjusting the circulation pump speed according to heating demand, water flow rate, and outlet temperature, the proposed system aims to reduce unnecessary electrical energy consumption while maintaining reliable hot-water performance. Some stakeholders may face disadvantages due to the implementation of additional control hardware, sensors, and software. Explaining these disadvantages will be essential to ensuring that the proposed project will benefit its intended users without compromising the safety, reliability, or economic feasibility. 

1. Building Occupants and Hot-Water Users(Societal Impact)

This project would benefit commercial building occupants through improved hot-water temperature stability and more reliable circulation during demand changes. The controller could help maintain consistent system performance while reducing unnecessary pump speed operation. This could help reduce the energy the pump needs to circulate at certain times. 

However, building occupants could be disadvantaged if the pump operates below the required circulation flow or fails to respond appropriately to changing demand. A controller malfunction or failure of the system's safety protections could result in inconsistent water temperatures, insufficient hot-water availability, or unsafe operating conditions. These disadvantages could negatively affect commercial facilities with high or fluctuating hot water demands [4].


2. Maintenance and Service Technicians (Economic and Societal Impact)

Maintenance technicians could benefit from the additional operating measurements that could be collected by the controller. The flow rate, temperature, and pump operating data could assist the technician in identifying any abnormal conditions as well as troubleshooting the system performance [2]. 

However, introducing additional sensors, wiring, electronic control, and software could also be a disadvantage to the technician. Adding these components could make the system more complex for maintenance and troubleshooting. Technicians may require additional training to understand the controller's operation and diagnose potential sensor or control-system failures, increasing maintenance time and labor costs. Having incorrect maintenance procedures could affect the equipment's reliability and its safe operation.

3. Commercial Facility Owners and Building Operators (Economic Impact)

Commercial facility owners could benefit from reduced electrical operating expenses if the variable speed pump consumes less power during lower demand conditions. Reduced pump operations may also improve energy management and provide opportunities for long-term operating cost savings [4].

However, additional controller hardware, sensors, installation requirements, and maintenance could increase the initial cost of implementing the system. If the electrical savings are smaller than anticipated, the cost of the system could outweigh its financial benefits. Unexpected controller failures could also create additional maintenance expenses or equipment downtime.


4. Lochinvar Engineering Team and Company (Economic and Societal Impact)

Lochinvar could benefit from a control strategy that demonstrates reduced pump electrical consumption while maintaining acceptable temperature and flow conditions. Successful experimental results could provide useful data for future commercial water-heating applications and potential improvements in energy efficiency. 

However, Lochinvar could also be at a disadvantage if the controller has reliability problems, inaccurate measurements, or equipment failure in the future. A controller failure could result in additional warranty expenses, engineering modification, customer dissatisfaction, or any potential liability associated with inadequate performance.

5. Environment and Local Communities (Environmental and Economic Impact)

The environment and surrounding communities could benefit from reduced electricity consumption. Reduced energy demand could contribute to lower greenhouse gas emissions, depending on the electricity generation source, while supporting more efficient resource utilization in commercial facilities.

However, the additional sensors, electronic components, and controller hardware introduce material consumption and eventual electronic waste. If the equipment has a short operating life or the controller fails to provide measurable energy savings, the environmental benefits could be reduced or offset by the resources required to manufacture, maintain, and replace the additional components.

 
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

The revised design contains five subsystems. Each team member has a primary subsystem responsibility, while Subsystem 2 will be a group effort with a designated documentation lead. The proposed lead below should be confirmed by the team before the updated ownership list is submitted to the professor.

| Subsystem | Primary owner or lead | Responsibility |
|---|---|---|
| 1. Sensor and Data Acquisition | Skyler Raines | Select and integrate flow and temperature sensors, condition measurements, verify sensor interfaces, and provide reliable inputs to the controller. |
| 2. Microcontroller and Control Logic | Group effort; **proposed lead: Jocelyn Smith** | Develop and document the controller, fault responses, command limits, and control algorithm; integrate contributions from all four members. |
| 3. Pump, Motor Control, and Hydraulic System | Danielle Wolford | Develop the pump interface, circulation-loop and hydraulic model, and minimum-flow protection for the bench setup. |
| 4. Monitoring, Performance Evaluation, and Bench Testing | Kendall Arnold | Plan and carry out the approved physical bench tests, coordinate repeated trials, and evaluate whether performance targets are met. |
| 5. Data Logging and Simulation | Jocelyn Smith | Develop the simulation, establish preliminary test conditions, record and store experimental data, compare model predictions with bench measurements, and report model error. |


* Subsystem 1 — Skyler Raines. Skyler will lead sensor selection and integration, including flow measurement, temperature measurement, signal conditioning, and communication of validated sensor readings to the controller.
	* Responsible team member and rationale: Skyler was assigned this subsystem because her background in Electronics and Computer Engineering Technology provides relevant knowledge of electrical connections and hardware components. Her experience assembling electrical panels and working with wiring during her internship will help her connect sensors, integrate their wiring with the microcontroller, and ensure the hardware is properly assembled. Her troubleshooting experience will also be useful for identifying faulty connections and resolving issues that could affect the accuracy and reliability of collected data. Additionally, her current Control Systems coursework provides relevant knowledge.
  
* Subsystem 2 — Group Effort, with Jocelyn Smith proposed as lead. Jocelyn will coordinate the control algorithm documentation and integrate the control software with the simulation and data recording requirements. Skyler will contribute sensor interface information, Danielle will contribute pump command and hydraulic limit requirements, and Kendall will contribute test and verification requirements. The final lead designation and individual contributions will be confirmed by the team.
	* Responsible team member and rationale: Jocelyn was assigned this subsystem because of her experience with C/C++, Assembly, Python, and control system analysis. These skills will be very useful when developing the programming needed to process sensor data and adjust pump speed based on the system's operating conditions. Her background in circuit analysis will also help with understanding the connections between the microcontroller, sensors, and pump control hardware.

* Subsystem 3 — Danielle Wolford. Danielle will lead the combined pump, motor control, and hydraulic design, including the compatible speed command interface, water-loop requirements, hydraulic model, and minimum-flow safeguards.
	* Responsible team member and rationale: Danielle was assigned this subsystem because her experience assembling electrical panels and troubleshooting electrical hardware provides a foundation for integrating the pump's motor control components. Her background in Electronics and Computer Engineering Technology will help her work with electrical connections between the pump, motor control hardware, and microcontroller. Her troubleshooting skills will also be valuable for diagnosing wiring problems, addressing hardware malfunctions, and helping ensure the pump control system operates reliably during testing.
  
* Subsystem 4 — Kendall Arnold. Kendall will lead the physical bench-test plan and performance evaluation, including repeatable operating conditions, matched baseline and controlled trials, temperature and power measurements, and safety verification evidence.
	* Responsible team member and rationale: Kendall was assigned this subsystem because of her background in applied physics and experience conducting experimental projects involving data collection, analysis, and comparison of results. She is also experiences with C/C++, assembly, and currently in Control Systems. These skills will be valuable when evaluating system performance under different operating conditions and determining whether the proposed control strategy reduces electrical energy consumption without compromising the performance of the heater.

* Subsystem 5 — Jocelyn Smith. Jocelyn will lead simulation development, data recording and storage design, model-to-bench comparison, and reporting of model error. This subsystem will provide datasets to Kendall for performance evaluation rather than taking over operation of the bench experiment.
	* Responsible team member and rationale: Jocelyn was assigned this subsystem because of her experience with MATLAB, Python, and control system analysis. These skills will help her organize experimental data, develop simulations, and analyze how changes in pump speed affect the water heating system. Because this subsystem works closely with the Microcontroller and Control Logic subsystem, assigning both to the same team member will also help maintain consistency between the controller design and performance analysis.


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

