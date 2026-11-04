# Generative AI and the Paradox of Human Capabilities

## A System Dynamics Model of Human Capability Reinforcement and Erosion in Organizations

This repository contains the system dynamics model and simulation scenario datasets developed for the research study:

**"Generative AI and the Paradox of Human Capabilities: A System Dynamics Model of Human Capability Reinforcement and Erosion in Organizations."**

The model examines the dynamic interactions between generative AI adoption, human capability development and erosion, AI dependency, and organizational learning capacity. It investigates how different organizational AI-use strategies and policy configurations may influence the long-term evolution of human capabilities in organizations.

## 1. Model Overview

The model is developed using a system dynamics approach and represents the feedback relationships between human capabilities, AI capabilities, organizational learning, and AI dependency.

The model includes four principal stock variables:

- Human Capability
- AI Capability
- AI Dependency
- Organizational Learning Capacity

The model also incorporates behavioral and organizational mechanisms, including cognitive offloading, cognitive engagement, independent practice, training and capability investment, human–AI task allocation, and organizational learning.

The simulation covers a 30-year time horizon.

## 2. Model Files

The repository is organized as follows:

- `model/`: Contains the system dynamics model source file (`.mdl`).
- `scenarios/`: Contains the six scenario-specific simulation datasets (`.vdfx`).
- `documentation/`: Contains supplementary model and scenario documentation.

The model source file is provided in Vensim `.mdl` format.

## 3. Simulation Scenarios

Six scenarios are developed to examine alternative configurations of organizational AI adoption, human capability development, and human–AI task allocation.

Scenario / Name / Description

S0 / Baseline / Balanced current use, with baseline settings for AI adoption, training, independent practice, and task allocation.
S1 / Augmentation / Human-in-the-loop use supported by increased training investment and protected independent practice.
S2 / Automation-first / Rapid delegation to AI accompanied by reduced training and independent practice.
S3 / Late correction / Automation-first settings are maintained until year 10, after which augmentation-oriented settings are introduced and delegation returns to its baseline level.
S4 / Delegation only / Human–AI task delegation increases over time, while all other policy levers remain at baseline settings.
S5 / AI capability surge / AI development accelerates through a reduction in AI development time, while human-side organizational policies remain at baseline settings.

### Scenario Configuration

The scenario selector variable (`Scenario`) determines which scenario is simulated.

- S0: `Scenario = 0`
- S1: `Scenario = 1`
- S2: `Scenario = 2`
- S3: `Scenario = 3`
- S4: `Scenario = 4`
- S5: `Scenario = 5`

The late-correction intervention in S3 occurs at year 10.

## 4. Simulation Settings

The model uses the following simulation settings:

| Parameter / Value |

| Initial Time / 0 years |
| Final Time / 30 years |
| Time Step / 0.0625 years |
| Save Period / 0.25 years |

## 5. How to Use the Model

1. Download or clone this repository.
2. Open the `.mdl` model source file using a compatible version of Vensim.
3. Set the `Scenario` variable to the desired scenario number (0–5).
4. Run the simulation.
5. Examine the resulting behavior of the model variables over the simulation horizon.

For reproducibility, use the same model equations, initial conditions, simulation settings, and scenario configurations reported in the associated research study.

## 6. Reproducibility and Research Use

The model and associated scenario datasets are made available to support transparency, inspection, replication, and further research on the organizational implications of generative AI adoption.

Researchers are encouraged to examine the model structure, reproduce the simulation scenarios, and extend the model for related investigations.

## 7. Related Publication

**Article title:** Generative AI and the Paradox of Human Capabilities: A System Dynamics Model of Human Capability Reinforcement and Erosion in Organizations.

The full bibliographic information and publication link will be added following publication.

## 8. Author

Hojat Tangesirasl

## 9. License

This repository is distributed under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.

Users may share and adapt the materials with appropriate attribution to the original author.

## 10. Contact

For questions regarding the model, its structure, or its simulation scenarios, please contact the corresponding author.
