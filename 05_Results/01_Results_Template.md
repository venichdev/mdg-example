# Results

**Chapter Purpose:** Present your findings objectively without interpretation

**Important:**
- Do NOT interpret results here (save for Discussion chapter)
- Present data clearly and systematically
- Use appropriate visualizations
- Include statistical summaries where applicable
- All figures and tables must have clear captions

---

## 1. Simulation Environment Verification

### 1.1 Model Validation

**[BEFORE SHOWING YOUR RESULTS, VALIDATE YOUR MODEL]**

**Purpose:** Demonstrate that your simulation model is realistic and reliable

**What to include:**
- Comparison with literature data (if available)
- Physical plausibility checks
- Steady-state validation
- Dynamic response validation

**Template:**
```
Table 1.1: Vehicle Model Parameters Validation

| Parameter | Your Model | Literature/Standard | Source | Deviation |
|-----------|-----------|---------------------|---------|-----------|
| [e.g., Mass] | [1500 kg] | [1450-1550 kg] | [Citation] | [±3.4%] |
| [Wheelbase] | | | | |
| [Iz] | | | | |

Figure 1.1: Steady-state cornering validation
[Plot: Your model vs. reference data or physical principles]

Figure 1.2: Step steering response validation
[Plot: Compare transient response with expected behavior]
```

---

## 2. Baseline Performance

### 2.1 Reference Method Results

**[ESTABLISH BASELINE BEFORE SHOWING YOUR METHOD]**

**Purpose:** Provide comparison reference

**For each baseline method, present:**

#### 2.1.1 Baseline 1: [Name of method, e.g., "Equal Torque Distribution"]

**Description:** [Brief description]

**Scenario 1: [e.g., Lane Change at 80 km/h]**

```
Figure 2.1: Path tracking performance - Equal torque distribution
[Plot: Desired vs. actual trajectory]

Figure 2.2: Energy consumption - Equal torque distribution
[Plot: Power over time, or cumulative energy]

Table 2.1: Performance metrics - Equal torque distribution

| Metric | Value | Unit |
|--------|-------|------|
| Total energy consumption | [INSERT] | [kWh] |
| RMS path tracking error | [INSERT] | [m] |
| Max lateral acceleration | [INSERT] | [m/s²] |
| Computation time | [INSERT] | [ms] |
```

**[REPEAT FOR OTHER SCENARIOS]**

---

## 3. Proposed Method Results

### 3.1 Algorithm Configuration

**Control Parameters:**
```
Table 3.1: Proposed controller parameters

| Parameter | Value | Unit | Justification |
|-----------|-------|------|---------------|
| [e.g., Prediction horizon] | [INSERT] | [steps] | [Why this value] |
| [e.g., Weight w1] | [INSERT] | [-] | [Tuning rationale] |
| [e.g., Weight w2] | [INSERT] | [-] | [Tuning rationale] |
```

### 3.2 Performance by Scenario

#### 3.2.1 Scenario 1: [Scenario name]

**Test Conditions:**
- Speed: [value]
- Road friction: [value]
- Other parameters: [specify]

**Results:**

```
Figure 3.1: Path tracking - Proposed method (Scenario 1)
[Plot: Trajectory comparison]

Figure 3.2: Torque distribution - Proposed method (Scenario 1)
[Plot: Individual wheel torques over time]

Figure 3.3: Vehicle states - Proposed method (Scenario 1)
[Plot: Velocity, yaw rate, sideslip angle, etc.]

Figure 3.4: Energy metrics - Proposed method (Scenario 1)
[Plot: Power consumption, battery SOC]

Table 3.2: Quantitative results - Proposed method (Scenario 1)

| Metric | Value | Unit |
|--------|-------|------|
| Total energy consumption | [INSERT YOUR DATA] | [kWh] |
| Energy per distance | [INSERT] | [kWh/km] |
| RMS tracking error | [INSERT] | [m] |
| Max tracking error | [INSERT] | [m] |
| RMS yaw rate error | [INSERT] | [rad/s] |
| Max lateral acceleration | [INSERT] | [m/s²] |
| Max tire slip ratio | [INSERT] | [-] |
| Avg computation time | [INSERT] | [ms] |
| Max computation time | [INSERT] | [ms] |
```

#### 3.2.2 Scenario 2: [Scenario name]

**[REPEAT STRUCTURE AS ABOVE]**

#### 3.2.3 Scenario 3: [Scenario name]

**[REPEAT FOR ALL SCENARIOS]**

---

## 4. Comparative Analysis

### 4.1 Direct Comparison Across Methods

```
Table 4.1: Energy consumption comparison across all scenarios

| Scenario | Equal Distribution | Rule-Based | Literature Method | Proposed Method | Improvement |
|----------|-------------------|------------|-------------------|-----------------|-------------|
| Lane change 50 km/h | [INSERT] kWh | [INSERT] kWh | [INSERT] kWh | [INSERT] kWh | [X]% |
| Lane change 80 km/h | | | | | |
| Slalom test | | | | | |
| Low friction | | | | | |

Figure 4.1: Energy consumption comparison bar chart
[Bar chart comparing all methods across scenarios]

Figure 4.2: Tracking performance comparison
[Comparison plot or bar chart]
```

### 4.2 Multi-Objective Performance

```
Figure 4.3: Pareto front - Energy vs. Tracking accuracy
[Scatter plot showing trade-off for different methods]

Figure 4.4: Radar chart - Multi-dimensional performance
[Radar/spider chart showing performance across multiple metrics]
```

---

## 5. Sensitivity Analysis

### 5.1 Parameter Sensitivity

**[SHOW HOW RESULTS CHANGE WITH KEY PARAMETERS]**

```
Figure 5.1: Energy consumption vs. control weight w1
[Line plot showing how performance varies]

Figure 5.2: Tracking error vs. control weight w2
[Line plot showing sensitivity]

Table 5.1: Sensitivity to vehicle mass variation

| Mass | Energy [kWh] | Tracking Error [m] | Notes |
|------|--------------|-------------------|-------|
| [80% nominal] | [INSERT] | [INSERT] | [Light load] |
| [100% nominal] | [INSERT] | [INSERT] | [Baseline] |
| [120% nominal] | [INSERT] | [INSERT] | [Heavy load] |
```

### 5.2 Robustness Analysis

```
Figure 5.3: Performance under varying road friction
[Plot showing robustness to road condition changes]

Table 5.2: Robustness to disturbances

| Disturbance Type | Baseline Method | Proposed Method | Improvement |
|-----------------|-----------------|-----------------|-------------|
| [e.g., Wind gust] | [Performance metric] | [Performance metric] | [%] |
| [e.g., Mass uncertainty] | | | |
```

---

## 6. Computational Performance

### 6.1 Real-time Feasibility

```
Figure 6.1: Computation time distribution
[Histogram of computation times across all control cycles]

Table 6.1: Computational requirements

| Metric | Value | Requirement | Feasible? |
|--------|-------|-------------|-----------|
| Average computation time | [INSERT] ms | < [sampling period] ms | [Yes/No] |
| 95th percentile time | [INSERT] ms | < [sampling period] ms | [Yes/No] |
| Maximum time observed | [INSERT] ms | < [sampling period] ms | [Yes/No] |
| Memory usage | [INSERT] MB | [Available] MB | [Yes/No] |

Computing Platform: [Specify: CPU, RAM, OS, MATLAB/Python version]
```

---

## 7. Special Cases and Edge Cases

### 7.1 Extreme Scenarios

**[TEST YOUR METHOD AT LIMITS]**

**Very low friction (μ = 0.3):**
```
Figure 7.1: Performance on icy road
[Show how your method handles extreme conditions]
```

**High-speed scenario:**
```
Figure 7.2: Performance at maximum speed
[Show behavior at limits]
```

**Emergency maneuver:**
```
Figure 7.3: Double lane change performance
[Show aggressive maneuver handling]
```

### 7.2 Failure Cases (if any)

**[BE HONEST ABOUT LIMITATIONS]**

If your method fails or performs poorly in certain conditions, document it here:

```
[Describe scenario where method struggles]
[Show the results objectively]
[Note: Interpretation goes in Discussion chapter]
```

---

## 8. Statistical Analysis (if applicable)

**[IF YOU RAN MULTIPLE TRIALS WITH VARIATIONS]**

```
Table 8.1: Statistical summary across Monte Carlo runs

| Metric | Mean | Std Dev | Min | Max | 95% CI |
|--------|------|---------|-----|-----|--------|
| Energy consumption | [INSERT] | [INSERT] | [INSERT] | [INSERT] | [±X] |
| Tracking error | | | | | |

Figure 8.1: Box plots of key metrics
[Show distribution of results across multiple runs]
```

---

## 9. Summary of Key Findings

**[OBJECTIVE SUMMARY - NO INTERPRETATION YET]**

Summarize main numerical results:

1. **Energy Efficiency:**
   - Proposed method achieved [X] kWh/km average across all scenarios
   - [Y]% improvement over baseline method
   - Range: [min] to [max] kWh/km across scenarios

2. **Control Performance:**
   - Average tracking error: [X] m
   - Maintained stability in all test scenarios
   - Computation time: [X] ms (within real-time constraints)

3. **Comparative Performance:**
   - Outperformed baseline in [X/Y] scenarios
   - Similar performance to literature method in [Z] scenarios
   - Trade-off observed between [metric1] and [metric2]

---

## Figure and Table Guidelines

### For ALL Figures:
- [ ] High resolution (300 DPI minimum)
- [ ] Axis labels with units
- [ ] Legible font size (minimum 10pt)
- [ ] Legend clearly identifying all curves/data
- [ ] Caption explaining what is shown
- [ ] Consistent color scheme
- [ ] Grid (if helpful for reading values)

### For ALL Tables:
- [ ] Clear column headers with units
- [ ] Appropriate precision (don't over-report decimal places)
- [ ] Consistent formatting
- [ ] Caption explaining content
- [ ] Highlight key values (optional)

---

## Checklist Before Moving to Discussion

- [ ] All claimed results are supported by data/figures
- [ ] No interpretation or explanation mixed in
- [ ] All figures are referenced in text
- [ ] All tables are referenced in text
- [ ] Statistical analysis is appropriate
- [ ] Reproducibility information is included
- [ ] Validation of simulation model shown
- [ ] Baseline comparisons are fair and complete
- [ ] Computational feasibility demonstrated
- [ ] Error bars or uncertainty shown where applicable

---

**Status:** Template - Ready for your experimental data
**Note:** This chapter should be purely factual and objective. Save interpretation, explanation, and comparison with literature for the Discussion chapter.

**Next Step:** After filling this with your data, proceed to Analysis & Discussion chapter.
