# Research Methodology

**Research Topic:** Torque Vectoring Control for Energy-Efficient Autonomous Electric Vehicles
**Institution:** Naresuan University
**Research Approach:** [Simulation / Experimental / Hybrid]

---

## 1. Research Design Overview

### 1.1 Research Type
- [ ] **Experimental Research** (physical testing)
- [ ] **Simulation-Based Research** (computer modeling)
- [ ] **Analytical Research** (mathematical derivation)
- [ ] **Hybrid Approach** (combination of above)

**Selected Approach:** [DEFINE YOUR APPROACH]

**Justification:**
```
[WHY THIS APPROACH IS APPROPRIATE FOR YOUR RESEARCH]
- Addresses research questions effectively
- Feasible with available resources
- Allows for validation and verification
- Industry-standard methodology
```

---

## 2. System Architecture

### 2.1 Vehicle System Overview

**Vehicle Type:** [e.g., Four-wheel independent motor EV]

**System Components:**
```
[DESCRIBE YOUR SYSTEM]

Example structure:
├── Vehicle Dynamics Model
│   ├── Tire models
│   ├── Chassis dynamics
│   └── Aerodynamics
├── Powertrain System
│   ├── Electric motors (specify: number, type, power)
│   ├── Battery system
│   └── Power electronics
├── Control System
│   ├── Upper-level controller (torque distribution)
│   ├── Lower-level controllers (motor control)
│   └── ADAS integration module
└── Sensor System
    ├── Vehicle state sensors
    ├── ADAS sensors
    └── Environment perception
```

### 2.2 Control Architecture Block Diagram

```
[INSERT YOUR CONTROL ARCHITECTURE DIAGRAM]

Typical structure:
ADAS/Autonomous System → Trajectory Planning → Upper-Level Controller
    ↓                                                ↓
Environment Data                          Optimal Torque Distribution
    ↓                                                ↓
Vehicle State Estimator ← Lower-Level Controllers → Individual Motors
                              ↓
                         Vehicle Dynamics
```

---

## 3. Control Algorithm Design

### 3.1 Control Objectives

**Primary Objective:**
[e.g., Minimize energy consumption while maintaining vehicle stability and tracking performance]

**Secondary Objectives:**
1. [e.g., Ensure passenger comfort]
2. [e.g., Maximize battery life]
3. [e.g., Maintain safety margins]

### 3.2 Control Method Selection

**[YOUR CHOSEN CONTROL METHOD]**

Options to consider:
- Model Predictive Control (MPC)
- Optimal Control (LQR/LQG)
- Sliding Mode Control
- Fuzzy Logic Control
- Neural Network Control
- Hybrid approaches

**Selected Method:** [SPECIFY]

**Advantages for your application:**
-
-

**Implementation considerations:**
- Computational requirements
- Real-time feasibility
- Tuning complexity

### 3.3 Mathematical Formulation

**[DETAIL YOUR CONTROL FORMULATION]**

#### State Variables
```
x = [state variables]
Example:
- Vehicle position (X, Y)
- Yaw angle (ψ)
- Longitudinal velocity (vx)
- Lateral velocity (vy)
- Yaw rate (r)
- Wheel speeds (ω1, ω2, ω3, ω4)
```

#### Control Inputs
```
u = [control inputs]
Example:
- Individual wheel torques (T1, T2, T3, T4)
or
- Total torque demand (Ttotal)
- Torque distribution ratios
```

#### System Dynamics
```
[YOUR VEHICLE DYNAMIC MODEL]

ẋ = f(x, u)

[Provide equations or reference to model]
```

#### Cost Function / Objective Function
```
[YOUR OPTIMIZATION OBJECTIVE]

J = ∫[...] dt

Example components:
- Energy consumption term: w1 * P_total
- Tracking error term: w2 * (x_ref - x)^2
- Comfort term: w3 * |a_lateral|
- Tire slip term: w4 * (λ - λ_optimal)^2

Where w1, w2, w3, w4 are weighting factors
```

#### Constraints
```
[YOUR SYSTEM CONSTRAINTS]

Examples:
- Motor torque limits: Tmin ≤ Ti ≤ Tmax
- Tire friction constraints: |Fx| ≤ μ*Fz
- Battery power limits: P ≤ Pmax
- Slip ratio limits: λ ≤ λcritical
- Computational time: Δt ≤ sampling_period
```

---

## 4. Simulation Environment

### 4.1 Software Tools

**Primary Simulation Platform:**
- [ ] MATLAB/Simulink
- [ ] Python (libraries: [specify])
- [ ] CarSim
- [ ] IPG CarMaker
- [ ] VI-grade
- [ ] Other: [specify]

**Version:** [Specify software version]

**Supplementary Tools:**
- Optimization: [e.g., MATLAB Optimization Toolbox, CVXPY]
- Visualization: [e.g., MATLAB plots, Python matplotlib]
- Data processing: [e.g., Python pandas, MATLAB]

### 4.2 Vehicle Model

**Model Type:**
- [ ] Single-track (bicycle) model
- [ ] Double-track model
- [ ] Multi-body dynamics model
- [ ] High-fidelity commercial model

**Model Fidelity:** [Justify your choice]

**Key Model Parameters:**
```
[LIST YOUR VEHICLE PARAMETERS]

Examples:
- Mass: [m] kg
- Moment of inertia: [Iz] kg·m²
- Wheelbase: [L] m
- Track width: [w] m
- Tire model: [e.g., Pacejka Magic Formula]
- Motor characteristics: [specify]
```

**Source of Parameters:**
- [ ] Literature (cite source)
- [ ] Manufacturer data
- [ ] Standard vehicle parameters
- [ ] Experimental identification

### 4.3 Driving Scenarios

**Test Scenarios:** [DEFINE YOUR TEST CASES]

Examples:
1. **Straight-line acceleration**
   - Purpose: Energy efficiency baseline
   - Speed range: [specify]
   - Road condition: [dry/wet]

2. **Lane change maneuver**
   - Purpose: Stability and energy during lateral dynamics
   - Speed: [specify]
   - Maneuver severity: [specify]

3. **Slalom test**
   - Purpose: Agility and control performance

4. **Low-friction scenario**
   - Purpose: Stability on slippery roads

5. **Urban driving cycle**
   - Purpose: Real-world energy consumption

6. **Highway driving**
   - Purpose: High-speed efficiency

**[ADD YOUR SPECIFIC SCENARIOS]**

### 4.4 ADAS/Autonomous Driving Integration

**Autonomy Level:** [SAE Level 0-5]

**ADAS Features Integrated:**
- [ ] Adaptive Cruise Control (ACC)
- [ ] Lane Keeping Assist (LKA)
- [ ] Path following
- [ ] Collision avoidance
- [ ] Other: [specify]

**Integration Approach:**
```
[DESCRIBE HOW ADAS INTERFACES WITH TORQUE CONTROL]
- Reference trajectory source
- Sensor data utilization
- Decision hierarchy
```

---

## 5. Baseline Comparison Methods

**[DEFINE COMPARISON STRATEGIES]**

Your novel method should be compared against:

1. **Baseline 1:** [e.g., Equal torque distribution]
   - Description:
   - Expected performance:

2. **Baseline 2:** [e.g., Rule-based torque vectoring]
   - Description:
   - Expected performance:

3. **Baseline 3:** [e.g., Existing method from literature]
   - Citation:
   - Implementation details:

---

## 6. Performance Metrics

### 6.1 Energy Efficiency Metrics
- [ ] **Total energy consumption** [J or kWh]
- [ ] **Energy per distance** [kWh/km]
- [ ] **Battery State of Charge (SOC)** variation [%]
- [ ] **Motor efficiency** [%]
- [ ] **Regenerative braking energy** [J]

### 6.2 Vehicle Dynamics Metrics
- [ ] **Path tracking error** [m or deg]
- [ ] **Lateral acceleration** [m/s²]
- [ ] **Yaw rate tracking** [rad/s]
- [ ] **Sideslip angle** [deg]
- [ ] **Tire slip ratios** [-]

### 6.3 Control Performance Metrics
- [ ] **Response time** [s]
- [ ] **Settling time** [s]
- [ ] **Overshoot** [%]
- [ ] **Steady-state error** [unit depends on signal]

### 6.4 Safety Metrics
- [ ] **Stability margin** [defined by your criteria]
- [ ] **Tire force utilization** [% of friction limit]
- [ ] **Critical situation avoidance** [yes/no or count]

### 6.5 Computational Metrics
- [ ] **Computation time per control cycle** [ms]
- [ ] **Memory usage** [MB]
- [ ] **Real-time feasibility** [yes/no]

---

## 7. Experimental Design

### 7.1 Simulation Parameters

**Sampling Time:** [e.g., 10 ms] - justify choice

**Simulation Duration:** [per scenario]

**Number of Runs:**
- [ ] Single run per scenario
- [ ] Multiple runs for statistical analysis: [n] runs
- [ ] Monte Carlo analysis: [n] samples

**Variable Parameters:**
[What will you vary in your experiments?]
- Vehicle speed: [range]
- Road friction: [μ values]
- Vehicle mass: [range]
- Control weights: [range]

### 7.2 Design of Experiments (DOE)

**Approach:**
- [ ] One-factor-at-a-time (OFAT)
- [ ] Full factorial design
- [ ] Fractional factorial
- [ ] Response surface methodology
- [ ] Latin hypercube sampling

**Factors to Investigate:**
| Factor | Low Level | High Level | Purpose |
|--------|-----------|------------|---------|
| [e.g., velocity] | [30 km/h] | [120 km/h] | [Speed effect] |
| [e.g., road friction] | [0.3] | [0.9] | [Surface condition] |
| | | | |

### 7.3 Validation Strategy

**How will you validate your approach?**

1. **Simulation validation:**
   - Compare with baseline methods
   - Analyze sensitivity to parameters
   - Test robustness under uncertainties

2. **Physical plausibility:**
   - Check constraints satisfaction
   - Verify causality
   - Inspect edge cases

3. **Literature benchmarking:**
   - Compare with published results (where applicable)
   - Use standard test scenarios
   - Compare performance metrics

4. **Statistical validation:**
   - Significance testing (if multiple runs)
   - Confidence intervals
   - Uncertainty quantification

---

## 8. Implementation Details

### 8.1 Algorithm Implementation

**Programming Language:** [MATLAB / Python / C++ / Simulink]

**Key Libraries/Toolboxes:**
- [e.g., MATLAB Optimization Toolbox]
- [e.g., Control System Toolbox]
- [e.g., Python SciPy]

**Code Structure:**
```
[DESCRIBE YOUR CODE ORGANIZATION]

Example:
├── main_simulation.m/py
├── vehicle_model/
│   ├── dynamics.m
│   ├── tire_model.m
│   └── motor_model.m
├── controllers/
│   ├── torque_distribution.m
│   ├── reference_tracking.m
│   └── adas_interface.m
├── scenarios/
│   └── [test scenario definitions]
└── analysis/
    ├── plot_results.m
    └── calculate_metrics.m
```

### 8.2 Solver Settings

**[SPECIFY YOUR SOLVER CONFIGURATION]**

- ODE solver: [e.g., ode45, RK4]
- Optimization solver: [e.g., fmincon, quadprog, CVXPY]
- Solver tolerances: [specify if critical]

---

## 9. Data Collection and Management

### 9.1 Data to be Collected

**Time-series Data:**
- Vehicle states (position, velocity, acceleration, etc.)
- Control inputs (torques, steering)
- Energy consumption (power, current, voltage, SOC)
- Sensor outputs (if ADAS integrated)

**Aggregate Metrics:**
- Total energy per scenario
- Maximum/minimum values
- Statistical summaries

### 9.2 Data Storage Format

**File Format:** [e.g., .mat, .csv, .h5, .pkl]

**Naming Convention:**
```
[scenario]_[method]_[parameters]_[date].ext

Example:
lanechange_proposed_v30_mu08_20250107.mat
```

### 9.3 Data Processing Pipeline

1. **Raw data** from simulation
2. **Filtering** [if applicable]
3. **Metric calculation**
4. **Statistical analysis**
5. **Visualization**

**Scripts for processing:** [List your analysis scripts]

---

## 10. Reproducibility Checklist

To ensure your research is reproducible:

- [ ] Document all software versions
- [ ] Provide complete parameter lists
- [ ] Include random seeds (if stochastic)
- [ ] Share code (or detailed pseudocode)
- [ ] Document hardware specifications (for computation time)
- [ ] Version control for code (Git/GitHub)
- [ ] README file with instructions
- [ ] Commented code
- [ ] Unit tests for critical functions

---

## 11. Safety and Ethical Considerations

### 11.1 Safety Validation

**[IMPORTANT FOR AUTONOMOUS VEHICLE RESEARCH]**

- [ ] Verify fail-safe mechanisms in control
- [ ] Test boundary cases
- [ ] Analyze worst-case scenarios
- [ ] Document any safety-critical assumptions

### 11.2 Limitations and Disclaimers

**Simulation Limitations:**
- Simulation is not reality
- Model fidelity limitations
- Assumptions that may not hold in real world

**Responsible Research:**
- Do not overstate real-world applicability
- Clearly state when results are preliminary
- Acknowledge uncertainties

---

## 12. Timeline

**[ADAPT TO YOUR SCHEDULE]**

| Phase | Duration | Deliverables |
|-------|----------|--------------|
| Methodology design | [weeks] | This document, advisor approval |
| Model development | [weeks] | Vehicle model, controller implementation |
| Baseline implementation | [weeks] | Reference methods coded |
| Initial testing | [weeks] | Preliminary results |
| Full experiments | [weeks] | Complete dataset |
| Analysis | [weeks] | Processed results, figures |
| Documentation | [weeks] | Methodology chapter draft |

---

## 13. Risk Assessment

**Potential Challenges and Mitigation:**

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| [e.g., Optimization doesn't converge] | [Medium] | [High] | [Use different solver, adjust parameters] |
| [e.g., Simulation too slow] | [Low] | [Medium] | [Simplify model, use parallel computing] |
| [YOUR RISKS] | | | |

---

## Next Steps

1. **Get advisor approval** for methodology
2. **Develop vehicle model** and validate against literature/data
3. **Implement control algorithm**
4. **Test on simple scenarios** first
5. **Iterate and refine**
6. **Proceed to full experiments**

---

**Status:** Template - Awaiting your specific methodology details
**Last Updated:** 2025-11-07
**Approval Status:** [Pending advisor review]
