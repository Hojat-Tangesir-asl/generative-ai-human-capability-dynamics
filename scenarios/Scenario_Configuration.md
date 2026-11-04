# Scenario Configuration

## 1. Overview

This document describes the six simulation scenarios developed for the system dynamics model presented in the study:

**Generative AI and the Paradox of Human Capabilities: A System Dynamics Model of Human Capability Reinforcement and Erosion in Organizations.**

The scenarios examine alternative organizational strategies for generative AI adoption and their implications for human capability development, AI dependency, and organizational learning capacity.

Six scenarios (S0–S5) are implemented through a scenario selector variable (`Scenario`) in the Vensim model.

## 2. Scenario Descriptions

### S0 – Baseline: Balanced Current Use

The baseline scenario represents a balanced configuration of organizational AI use. Training, independent practice, AI adoption, and human–AI task allocation remain at their baseline settings throughout the simulation.

### S1 – Augmentation

This scenario represents a human-in-the-loop approach to generative AI adoption. It emphasizes funded training and protected independent practice to support the development and maintenance of human capabilities.

### S2 – Automation-first

This scenario represents rapid delegation of tasks to AI systems, accompanied by reduced investment in training and reduced independent practice. It examines the potential long-term consequences of prioritizing automation over human capability development.

### S3 – Late Correction

This scenario initially follows the Automation-first configuration. At year 10, organizational policies shift toward augmentation-oriented settings. Training and independent practice increase, while human–AI task allocation returns to its baseline level.

### S4 – Delegation Only

This scenario isolates the effect of increasing human–AI task delegation. Task allocation to AI increases over time, while training, independent practice, and AI adoption parameters remain at their baseline settings.

### S5 – AI Capability Surge

This scenario examines the effects of accelerated AI development. AI development time decreases from 3 years to 1.5 years, while all human-side policy settings remain at baseline levels.

## 3. Scenario Parameters

The following parameters are used to configure the six scenarios:

- **Training Rate:** Controls the organizational investment multiplier associated with training and capability development.
- **Practice Policy:** Determines the policy level supporting independent human practice.
- **Adoption Coefficient:** Controls the rate at which organizational productivity translates into AI adoption.
- **Human–AI Task Allocation:** Represents the degree of task allocation to AI systems.
- **AI Development Time:** Determines the time required for AI capability development.

### Table 1. Scenario Parameter Configuration

| Parameter | S0 | S1 | S2 | S3 | S4 | S5 |
|---|---:|---:|---:|---:|---:|---:|
| Training Rate | 0.2 | 0.4 | 0.1 | 0.1 → 0.4 | 0.2 | 0.2 |
| Practice Policy | 1.0 | 1.5 | 0.5 | 0.5 → 1.5 | 1.0 | 1.0 |
| Adoption Coefficient | 0.3 | 0.3 | 0.45 | 0.45 → 0.3 | 0.3 | 0.3 |
| Human–AI Task Allocation | 0.2 | 0.2 | 0.2 → 0.6 | 0.2 → 0.6 → 0.2 | 0.2 → 0.5 | 0.2 |
| AI Development Time (years) | 3.0 | 3.0 | 3.0 | 3.0 | 3.0 | 1.5 |

*Note: Arrows indicate changes over simulation time. The numerical values represent the parameter settings implemented in the model.*

## 4. Timing of Scenario Interventions

The timing and transition rules are defined as follows:

- **S0:** All policy parameters remain at baseline values throughout the 30-year simulation.
- **S1:** Augmentation-oriented settings are applied throughout the simulation.
- **S2:** Human–AI task allocation increases linearly from 0.2 to 0.6 during the first five years and remains at 0.6 thereafter. Training Rate and Practice Policy remain at 0.1 and 0.5, respectively.
- **S3:** The Automation-first configuration is maintained until year 10. At year 10, Training Rate changes from 0.1 to 0.4, Practice Policy changes from 0.5 to 1.5, Adoption Coefficient returns from 0.45 to 0.3, and Human–AI Task Allocation returns to 0.2.
- **S4:** Human–AI task allocation increases linearly from 0.2 to 0.5 during the first five years and remains at 0.5 thereafter. All other policy parameters remain at baseline values.
- **S5:** AI Development Time is reduced from 3 years to 1.5 years throughout the simulation, while human-side policy parameters remain at baseline values.

## 5. Mathematical Implementation

The scenario interventions are implemented using conditional equations in Vensim.

The scenario selector variable determines the active configuration:

`Scenario = 0, 1, 2, 3, 4, or 5`

For S2 and S3, human–AI task allocation follows:

`0.2 + 0.4 × MIN(1, Time/5)`

before the correction point.

For S4, human–AI task allocation follows:

`0.2 + 0.3 × MIN(1, Time/5)`

For S3, the correction is triggered when:

`Time >= 10`

After this point, the model applies augmentation-oriented training and practice settings and restores task allocation to 0.2.

In S5, AI Development Time is set to 1.5 years instead of the baseline value of 3 years.

## 6. Simulation Horizon and Numerical Settings

All scenarios are evaluated using the same simulation horizon and numerical settings:

| Setting | Value |
|---|---:|
| Initial Time | 0 years |
| Final Time | 30 years |
| Time Step | 0.0625 years |
| Save Period | 0.25 years |
| Correction Time (S3) | 10 years |

Keeping these settings consistent across scenarios supports comparative analysis of their dynamic behavior.

## 7. Reproducibility

To reproduce the scenarios:

1. Open the model source file (`SFD_model_v2.mdl`) in Vensim.
2. Set the `Scenario` variable to the desired scenario identifier (0–5).
3. Run the simulation using the numerical settings specified above.
4. Examine the resulting time-series behavior of the model variables.
5. Compare the results across the six scenarios.

The model source file and scenario datasets are provided in this repository to support model inspection, simulation replication, and further research.
