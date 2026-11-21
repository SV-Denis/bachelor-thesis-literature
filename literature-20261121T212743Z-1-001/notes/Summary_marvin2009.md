Main problem:

natural language is unreliable for requirements:

It is: 
	- Ambiguous (a word or phrase can have multiple meanings)
	- Vague (lacks precision)
	- Complex (It compounds requirements)
	- Omission (can miss some requirements)
	- Wordiness (it is verbose, many words not describing the actual requirements)
	- Duplication (it can repeat the same requirement)
	- Inappropiate implementation (it can target how it should be build instead of what it should do)
	- Untestability (it can create requirements that cannot be proven true or false)

Other methods often Require complex translations of the source requirements creating language barriers.

Method:

-Built on the concept of ECA, it included rules of thumb such as the use of "when" (event-driven behaviour), "while" (state-driven behaviour), "if-then" (failures) 
	
(While < precondition >, When < trigger >, the < system name > shall < system response >)

- the paper cs-e 50 was used: 
	first phase: the clauses were broken into parts, all requirements were placed into a spreadsheet
	second phase: requirements were rewritten using EARS
- tested the effectiveness of the EARS ruleset

EARS templates:
- Ubiquitous: The < system name > shall < system response > (always active)

- Event-driven: When < trigger >, the < system name > shall < system response >

- Unwanted behavior: If < unwanted condition/trigger >, then the < system name > shall < system response >

- State-driven: While < in a specific state >, the < system name > shall < system response >

- Optional feature: Where < feature is included >, the < system name > shall < system response >

case-study:

Certification Specification for Engines (CS-E) [19] defines what must be achieved in order for an aero engine to achieve certification. 

Impact: Splitting compound regulatory text into EARS templates increased the total number of individual requirements (eliminating hidden compound behaviors) while reducing the average word count per requirement, making them easier for non-specialist engineers to read, reuse, and verify.

Open questions:

Does EARS work for heavier data sets of requirements? (in the paper the sample size is small, 36 original requirements)

Does Ears work for other types of requirements? (it was only tested on high-level safety related requirements)








Personal notes:

Relevance: Introduces EARS

Formal notations for specifying requirements:

	- Z
	- Petri Nets
	- Unified Modeling Language (UML)
	- Systems Modeling Language (SysML)
	- Table-Driven Requirements
	- ConCERT
	- Pseudocode

Problem with specified notations: 

Requires complex translation of the source requirements.
---------------------------------------------------------------------------


Work on "requirements": (the work focuses on requirements but makes no claim that its universally applicable to all levels of system decomposition, being most suitable for the definition of high-level stakeholder requirements)

	- "Writing Good Requirements":  characteristics of well formed requirements, and what should be included

Templates to check:

	- VOLERE
	- SL-07

Works on "constrained natural language": 

	- Simplified Technical English
	- Attempto Controlled English
	- Event-Condition-Action (the event specifies the signal that triggers the rule and the condition is a logical test that (if satisfied) causes the specified system action.)

---------------------------------------------------------------------------
case-study:

Certification Specification for Engines (CS-E) [19] defines what must be achieved in order for an aero engine to achieve certification. For this study, the section of CS-E most applicable to engine control systems (CS-E 50) was analysed. CS-E 50 contains a relatively small number of requirements, which was manageable quantity for a case study. In summary, not all engineer might be familiar with the notes in the document which are quite complex statements, and instead they might be more familiar with simple statements, which in turn it might reduce the chance in needing expensive alterations later on, it also can be reused later on.

method:

-Built on the concept of ECA, it included rules of thumb such as the use of "when" (event-driven behaviour), "while" (state-driven behaviour), "if-then" (failures)
- the paper cs-e 50 was used: 
	first phase: the clauses were broken into parts, all requirements were placed into a spreadsheet
	second phase: requirements were rewritten using EARS
- tested the effectiveness of the EARS ruleset

result: more clear and efficient statements, it increased the number of requirements while reducing the amount of words per requirement.
limitations: small sample size, restriction to only high-level safety-related requirements



	
