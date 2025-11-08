# Implementation & Data Management

This folder contains your code, simulation models, data, and implementation documentation.

---

## Folder Organization

### Recommended Structure

```
04_Implementation/
├── README.md (this file)
├── code/
│   ├── models/
│   │   ├── vehicle_model.m/.py
│   │   ├── tire_model.m/.py
│   │   ├── motor_model.m/.py
│   │   └── battery_model.m/.py
│   ├── controllers/
│   │   ├── proposed_controller.m/.py
│   │   ├── baseline_equal_distribution.m/.py
│   │   ├── baseline_rule_based.m/.py
│   │   └── mpc_implementation.m/.py (if applicable)
│   ├── scenarios/
│   │   ├── lane_change.m/.py
│   │   ├── slalom.m/.py
│   │   ├── straight_line.m/.py
│   │   └── low_friction.m/.py
│   ├── utils/
│   │   ├── data_processing.m/.py
│   │   ├── plotting.m/.py
│   │   ├── metrics_calculation.m/.py
│   │   └── helpers.m/.py
│   └── main_simulation.m/.py
│
├── data/
│   ├── raw/
│   │   ├── [date]_[scenario]_[method]_raw.mat/.csv
│   │   └── README.md (describes data format)
│   ├── processed/
│   │   ├── [date]_[scenario]_[method]_processed.mat/.csv
│   │   └── README.md
│   └── results/
│       ├── figures/
│       ├── tables/
│       └── summary/
│
├── parameters/
│   ├── vehicle_parameters.yaml/.json/.mat
│   ├── controller_parameters.yaml/.json/.mat
│   └── simulation_settings.yaml/.json/.mat
│
├── tests/
│   ├── test_vehicle_model.m/.py
│   ├── test_controller.m/.py
│   └── test_scenarios.m/.py
│
└── docs/
    ├── code_documentation.md
    ├── model_validation.md
    └── implementation_notes.md
```

---

## Code Organization Best Practices

### 1. Modular Design

**Separate concerns:**
- Models (vehicle dynamics, tire, motor, battery)
- Controllers (your method, baselines)
- Scenarios (test cases)
- Utilities (plotting, data processing)
- Main scripts (orchestration)

**Benefits:**
- Easier to test
- Easier to modify
- Easier to understand
- Reusable components

### 2. Naming Conventions

**Files:**
```
use_lowercase_with_underscores.m
or
useCamelCaseForFunctions.m

Be consistent within your project!
```

**Variables:**
```
descriptive_variable_names
not: x, y, z (unless coordinates)
but: vehicle_velocity, yaw_rate, torque_fl (front-left)
```

**Functions:**
```
function_name_describes_action()

Examples:
- calculate_torque_distribution()
- simulate_vehicle_dynamics()
- plot_trajectory_comparison()
```

### 3. Documentation

**Every file should have a header:**
```matlab
% FILE: vehicle_model.m
% DESCRIPTION: 4-wheel vehicle dynamics model with independent motors
% AUTHOR: Your Name
% DATE: 2025-11-07
% INPUTS:
%   - state: [x, y, psi, vx, vy, r, omega1, omega2, omega3, omega4]
%   - torques: [T1, T2, T3, T4] (Nm)
%   - params: vehicle parameter structure
% OUTPUTS:
%   - state_dot: derivative of state vector
% NOTES:
%   - Uses double-track model
%   - Tire model: Pacejka Magic Formula
%   - Coordinate system: ISO 8855
```

**Every function should have docstring:**
```python
def calculate_torque_distribution(reference, vehicle_state, params):
    """
    Calculate optimal torque distribution for 4-wheel EV.

    Parameters
    ----------
    reference : dict
        Reference trajectory with keys: 'x', 'y', 'psi', 'v'
    vehicle_state : ndarray
        Current vehicle state vector
    params : dict
        Controller parameters including weights

    Returns
    -------
    torques : ndarray
        Optimal torque for each wheel [T1, T2, T3, T4] in Nm

    Notes
    -----
    Uses MPC with prediction horizon N=10, sampling time 0.01s.
    Energy minimization with tracking error penalty.
    """
```

### 4. Comments

**Good comments explain WHY, not WHAT:**
```matlab
% ❌ Bad: Increment i by 1
i = i + 1;

% ✓ Good: Skip first data point due to initialization transient
i = i + 1;
```

**Use comments for:**
- Explaining non-obvious logic
- Referencing equations from papers
- Noting assumptions
- Marking TODO items
- Explaining magic numbers

---

## Version Control with Git

### Initial Setup
```bash
cd Test_Thesis_Topic_01/04_Implementation
git init
```

### Create .gitignore
```
# MATLAB
*.asv
*.m~

# Python
__pycache__/
*.pyc
*.pyo
.ipynb_checkpoints/

# Data (large files)
data/raw/*.mat
data/raw/*.csv
# Keep small example data, ignore large datasets

# OS
.DS_Store
Thumbs.db

# IDE
.vscode/
.idea/
*.swp
```

### Commit Strategy
```bash
# Stage changes
git add code/models/vehicle_model.m

# Commit with meaningful message
git commit -m "Implement 4-wheel vehicle dynamics model with Pacejka tire model"

# Regular commits (daily or after each significant change)
git commit -m "Fix bug in torque saturation limits"
git commit -m "Add validation test for vehicle model"
```

### Branching (Optional but Good Practice)
```bash
# Create branch for new feature
git checkout -b feature/mpc-implementation

# Work on feature, commit changes

# Merge back to main when ready
git checkout main
git merge feature/mpc-implementation
```

### Remote Backup (Highly Recommended)
```bash
# Create private repo on GitHub/GitLab
# Link and push
git remote add origin <your-repo-url>
git push -u origin main
```

---

## Data Management

### 3-2-1 Backup Rule
- **3 copies** of your data
- **2 different** storage media
- **1 offsite** backup

Example:
1. Copy on computer (working copy)
2. Copy on external hard drive
3. Copy on cloud (Google Drive, OneDrive, Dropbox)

### Data Organization

#### Raw Data
**NEVER modify raw data!**
- Store exactly as generated from simulation
- Read-only permissions if possible
- Include metadata (date, conditions, software version)

#### Processed Data
- Derived from raw data via documented scripts
- Keep processing scripts in version control
- Document all processing steps

#### Data README Files
Each data folder should have README:
```markdown
# Data Description

## File Format
- Extension: .mat (MATLAB) / .csv (CSV)
- Variables:
  - time: [N x 1] simulation time in seconds
  - state: [N x 10] vehicle state [x, y, psi, vx, vy, r, w1, w2, w3, w4]
  - torques: [N x 4] applied torques [T1, T2, T3, T4] in Nm
  - power: [N x 1] total power in W
  - energy: cumulative energy in J

## Collection Details
- Date: 2025-11-07
- Software: MATLAB R2023a
- Scenario: Lane change at 80 km/h
- Controller: Proposed MPC method
- Parameters: See parameters/controller_params_v1.yaml

## Notes
- Sampling frequency: 100 Hz
- Simulation duration: 10 seconds
- Initial conditions: v0 = 80 km/h, straight line
```

### File Naming Convention
```
YYYY-MM-DD_scenario_method_parameters_version.ext

Examples:
2025-11-07_lanechange_proposed_v80_mu08_v1.mat
2025-11-07_slalom_baseline_v60_mu09_v1.mat
2025-11-08_straight_rulebased_v100_mu09_v2.mat
```

**Components:**
- Date: ISO format (YYYY-MM-DD)
- Scenario: descriptive name (no spaces)
- Method: controller type
- Parameters: key variables (v=velocity, mu=friction)
- Version: iteration number

---

## Parameter Management

### Use Configuration Files

**YAML Example:**
```yaml
# vehicle_parameters.yaml
vehicle:
  mass: 1500  # kg
  wheelbase: 2.7  # m
  track_width: 1.6  # m
  inertia_z: 2500  # kg*m^2
  cg_height: 0.5  # m

motor:
  max_torque: 250  # Nm per wheel
  max_power: 50000  # W per wheel
  efficiency: 0.95

tire:
  model: "Pacejka"
  parameters:
    B: 10
    C: 1.9
    D: 1.0
    E: 0.97
```

**Load in code:**
```python
import yaml
with open('parameters/vehicle_parameters.yaml', 'r') as f:
    params = yaml.safe_load(f)
```

**Benefits:**
- Easy to modify without changing code
- Version control tracks parameter changes
- Can maintain multiple parameter sets
- Easy to document

---

## Testing and Validation

### Unit Tests

**Test individual components:**
```matlab
% test_vehicle_model.m
function test_vehicle_model()
    % Test 1: Steady-state straight line
    % Expected: zero lateral velocity
    [result] = test_straight_line_steady_state();
    assert(abs(result.vy) < 1e-6, 'Lateral velocity should be zero');

    % Test 2: Conservation of energy
    % Expected: Energy in = Energy out + losses
    [result] = test_energy_conservation();
    assert(result.energy_error < 0.01, 'Energy should be conserved');

    fprintf('All tests passed!\n');
end
```

### Integration Tests

**Test complete workflow:**
- Load parameters
- Initialize vehicle model
- Run controller
- Generate results
- Verify outputs

### Validation Tests

**Compare with references:**
- Literature data
- Physical principles (e.g., tire friction circle)
- Known analytical solutions
- Expected behaviors

---

## Reproducibility Checklist

- [ ] All code is version controlled
- [ ] All parameters are documented
- [ ] Random seeds are set (if stochastic)
- [ ] Software versions documented
- [ ] Processing scripts are saved
- [ ] README files explain data formats
- [ ] Figures can be regenerated from data
- [ ] Computational environment documented

### Environment Documentation

**Create environment file:**
```yaml
# environment.yaml
name: thesis-simulation
dependencies:
  - python=3.9
  - numpy=1.21
  - scipy=1.7
  - matplotlib=3.4
  - pandas=1.3
```

Or for MATLAB:
```matlab
% environment_info.m
% MATLAB Version: R2023a (9.14)
% Required Toolboxes:
%   - Optimization Toolbox
%   - Control System Toolbox
%   - Statistics and Machine Learning Toolbox
% Operating System: macOS 13.0 / Windows 11 / Ubuntu 22.04
```

---

## Performance Optimization

### Profiling
**MATLAB:**
```matlab
profile on
main_simulation();
profile viewer
```

**Python:**
```python
import cProfile
cProfile.run('main_simulation()')
```

### Common Bottlenecks
- Unnecessary loops (vectorize when possible)
- Repeated calculations (cache results)
- Inefficient data structures
- Excessive plotting during simulation

### Optimization Tips
- Pre-allocate arrays
- Use compiled functions (MATLAB MEX, Python Numba)
- Parallel computing for independent runs
- Simplify model where appropriate

---

## Debugging Strategies

### Sanity Checks
- Print intermediate values
- Plot intermediate results
- Check dimensions/units
- Verify constraints are satisfied

### Common Issues
- **Simulation diverges**: Check time step, initial conditions, constraints
- **Optimization fails**: Check cost function, constraints, initial guess
- **Unexpected results**: Verify parameters, check units, plot states
- **Slow performance**: Profile code, identify bottlenecks

### Debugging Tools
- MATLAB: `keyboard`, `dbstop if error`, breakpoints
- Python: `pdb`, `breakpoint()`, IDE debuggers

---

## Documentation

### Code Documentation
Keep `docs/code_documentation.md` updated with:
- Overall architecture
- Key functions and their purposes
- Data flow diagram
- Important implementation details

### Implementation Notes
Keep `docs/implementation_notes.md` as a journal:
- Date, what you implemented
- Issues encountered and solutions
- Design decisions and rationale
- Things to remember for next time

---

## Before Running Experiments

### Pre-flight Checklist
- [ ] Code is tested and validated
- [ ] Parameters are verified
- [ ] Baseline methods are properly implemented
- [ ] Data storage is set up
- [ ] Backup system is in place
- [ ] Version control is up to date
- [ ] You understand what each parameter does
- [ ] You have a plan for analyzing results

---

## Useful Commands

### MATLAB
```matlab
% Save workspace
save('backup_workspace.mat');

% Clear all
clear all; close all; clc;

% Add paths
addpath(genpath('code/'));

% Suppress warnings (use carefully)
warning('off', 'specific:warning:id');
```

### Python
```python
# Save data
import pickle
with open('data.pkl', 'wb') as f:
    pickle.dump(data, f)

# Load data
with open('data.pkl', 'rb') as f:
    data = pickle.load(f)

# Print environment
import sys
print(sys.version)
import numpy
print(numpy.__version__)
```

---

## Final Notes

### Good Practices
✓ Write code as if someone else will read it (they will - including future you!)
✓ Comment non-obvious code
✓ Use meaningful variable names
✓ Test your code
✓ Back up regularly
✓ Document as you go (not at the end)
✓ Version control everything

### Avoid
✗ Hard-coding values (use parameters)
✗ Copy-paste code (write functions)
✗ Cryptic variable names (x1, x2, x3...)
✗ Code without comments
✗ Working without backups
✗ Ignoring warnings/errors

---

**Remember: Good code is not just code that works, it's code that is clear, maintainable, and reproducible!**

**Your future self will thank you for being organized now.**
