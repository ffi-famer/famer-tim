
## Data collection

```plantuml
class qualitative_data
class interview_data
class precog_interview_data
class projx_interview_data
class information_model
class information_model_glossary
class information_model_validation
class standards
class 8800

qualitative_data <|-- interview_data

interview_data <|-- precog_interview_data
interview_data <|-- projx_interview_data
projx_interview_data <|-- information_model_validation
projx_interview_data  <|-- REFSQ25_data
projx_interview_data  <|-- RE25_ICSE_JSS_data

information_model <.. information_model_validation
standards <. information_model
information_model <.. information_model_glossary
standards <.. information_model_glossary
standards <|-- ISO8800
standards <|-- ISO21448
```

1. Created an **information model** _(a _domain schema_ or ontology (informal) that establishes the vocabulary for our perception system projects and how they relate to relevant standards)_
2. Created a **glossary** where all elements of the information model are defined based on a relevant standard

We treat these two as the superset of information that can be traceable.
Thus, any more detailed TIM candidate from other data sources must be aligned.

```plantuml
start
:Create Information Model;
:Define Information Model Elements in Glossary;
repeat
  :Derive critical tracelinks and elements from data source;
  :Align derived tracelinks and elements with IM;
if (can be aligned with minor changes) then (yes)
    :align wording where needed;
else (no)
    :phrase questions for expert evaluation;
endif
repeat while (more data sources \n(standard or qualitative data)?) is (yes) not (no)
:expert evaluation to finalize TIM; 
stop
```

We then go through the other data sources and tried to derive from each examples of artifacts as well as implied tracelinks and elements.
We then tried to align each with the growing TIM as well as with the information model.
Where this was not possible, we phrase questions for a final round of expert evaluation.
Generally, we were happy to omit or add additional detail, while keeping the structure of the information model.
Some terms were used differently in different contexts.
Process related trace artifacts where often not found in the information model, e.g. test results.
These were then typical candidates for questions in the expert evaluation.
