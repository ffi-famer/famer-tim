# Famer TIM

A Traceability Information Model (TIM) for AI-based perception systems in safety-critical automotive applications, developed as part of the [FAMER](https://ffi-famer.github.io/) project.

## Table of Contents

- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [Graphical Model](#graphical-model)
- [Repository Structure](#repository-structure)
- [Core Artifacts](#core-artifacts)
- [Authors and Acknowledgment](#authors-and-acknowledgment)
- [Project Status](#project-status)
- [License](#license)

## Description

FAMER TIM defines the artifact types and traceability links needed to demonstrate compliance with ISO safety standards when developing AI-based
perception systems. It connects functional safety concepts, AI safety requirements, dataset and annotation requirements, AI models, and validation results into a single traceable model.

The model is implemented using [Treqs](https://pypi.org/project/treqs/), a tool for managing requirements and traceability in markdown documents.


## Installation

Treqs is published on PyPI and requires Python 3.

```bash
pip install treqs
```

Verify the installation:

```bash
treqs --help
```

It's recommended to install it inside a virtual environment:

```bash
python -m venv venv
source venv/bin/activate   # on Windows: venv\\Scripts\\activate
pip install treqs
```

## Usage
Clone this repository and run the following commands from the project root.

**1. Check the model is valid (no broken links):**
```bash
treqs check
```

**2. List all elements of a given type**, e.g. all annotation requirements:
```bash
treqs list --type annotation-requirement
```

**3. Trace everything related to a specific element**, e.g. a compliance requirement:
```bash
treqs list --outlinks --uid d13a197ac7ce11f0ae0a467a017f3d7d
```

**4.Generate the graphical traceability model:**
```bash
treqs list --plantuml --outlinks tim-documentation/famer-tim-rationale.md
```

**5. Generate a standards-to-element overview**, e.g. for annotation requirements:
```bash
treqs list --plantuml --inlinks --followlinks True --type annotation-requirement
```

## Repository Structure

```bash
famer-tim/
├── example/                           # Concrete example artifacts 
├── method/
│   └── research-method.md             # Research method description
├── standards-treqs/                   # Compliance requirements derived from
│                                       # ISO standards, linked to TIM elements
├── templates/                         # Reusable templates for new TIM elements
├── tim-documentation/
│   ├── famer-tim-design-decisions.md  # Documented modeling decisions
│   └── famer-tim-rationale.md         # TIM elements, links, and design rationale
└── ttim.yaml                          # Type and trace information model schema
```


## Core Artifacts

| Type | Description |
|---|---|
| `operational-design-domain` | Operating conditions and boundaries |
| `intended-functionality` | High-level description of system behavior |
| `functional-safety-concept` | How safety goals are achieved at system level |
| `functional-safety-requirement` | Specific system-level safety requirements |
| `ai-safety-requirement` | Safety requirements for the AI component, including measurable KPIs |
| `dataset-requirement` | Definition of the input space needed for training/validation |
| `annotation-requirement` | Abstract specification of what must be labeled |
| `annotation-guideline` | Concrete labeling instructions and examples |
| `annotation-tool` | Tool used to produce annotations |
| `dataset-annotation` | Concrete labeled dataset |
| `ai-model` | Trained model instance, with architecture/version/configuration attributes |
| `dataset-annotation-check` | Test scenario used to validate annotation/model quality |
| `dataset-annotation-check-result` | Outcome of a check, including pass/fail status |

Full type definitions and allowed links are specified in [`ttim.yaml`](./ttim.yaml).

## Authors and acknowledgment
Created by:

- Claudia Sevilla Eslava
- Hina Saeeda
- Erik Knauss

Supervisor: Eric Knauss

## Project Status
This is a research-in-progress model. Various elements and link directions are still under expert evaluation.

## License
Licensed with the [MIT License](https://opensource.org/licenses/MIT). 



