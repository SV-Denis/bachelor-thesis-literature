1. Ce problema..., 

turning EARS into fully precise formal specifications |Formalizing EARS using Linear Temporal Logic|  (to be used in code synthesis, formal verification, test case generation)

(The work also provides a direction towards having EARS requirements computer readable

Solves the problem of transforming EARS requirements in isolation by providing an algorithm that derives context from other requirements (ex: EARS requirements dont show for how long a requirement happens, but it can be derived from other requirements that switch the respective requirement off)


2. Cum se rezolva?, 

Transforming EARS specification to Linear Temporal logic, 

Transformation from EARS to LTL:

	- Ubiquitous  | The <system> shall <response>                                    | G(response)
	- Event-Driven| When <trigger> the <system> shall <response>                     | G(trigger → X(response))
	- State-Driven| While <in state> the <system> shall <response>                   | G(in state → response)
	- Option      | Where <feature> the <system> shall <response>                    | G(feature → response)
	- Complex     | While <in state>, when <trigger>, the <system> shall <response>  | G((in state ∧ trigger) → X(response))
	- Unwanted    | If <preconditions> <trigger>, the <system> shall <response>      | G((preconditions ∧ trigger) → X(response))


Static context analysis (algorithm to find overlapping requirements, 
ex when key is pressed, the keyboard writes space,  when key is released, the keyboard stops typing space):


untilClause = ∅
currentReq = requirement being transformed
contextReq = first requirement different from currentReq
while not all context requirements have been processed do
if currentReq.responses ∩ contextReq.responses
then
untilClause = untilClause ∪ contextReq.trigger
end if
end while




3. Exemple/use-cases, 

a system that includes a main engine, an auxiliary engine and an oil pump engine, the sequence to start the machine is to first run the old pump engine; after 10 seconds start the main engine; and after 5 more seconds start the auxiliary engine. The requirements have been written in EARS.

phase 1 translating to LPL, phase 2 connecting the requirements to stop an oil motor:
 (G(start button pressed → (X(start oil motor ∧ start 10 sec timer) U stop button pressed))




4. Open questions?

Could the algorithm be used for model checking or test case generation?


Personal notes:

to read

[4] A. Mavin and P. Wilkinson. Big Ears (The Return of ”Easy Approach to
Requirements Engineering”). In RE, pages 277–282. IEEE, 2010.
[5] A. Mavin, P. Wilkinson, S. Gregory, and E. Uusitalo. Listens Learned (8
Lessons Learned Applying EARS). In RE, pages 276–282. IEEE, 2016.

(they show that EARS work for heavy data sets of requirements as well)


IETS3 project ( synthesizing software controllers directly from EARS specifications) EARS -> Linear Temporal Logic

[1] EARS-CTRL Model Development Environment. https://github.com/
levilucio/EARS-CTRL.git.


case study:

a system that includes a main engine, an auxiliary engine and an oil pump engine, the sequence to start the machine is to first run the old pump engine; after 10 seconds start the main engine; and after 5 more seconds start the auxiliary engine. The requirements have been written in EARS.

method:

Transformation from EARS to LTL:

	- Ubiquitous  | The <system> shall <response>                                    | G(response)
	- Event-Driven| When <trigger> the <system> shall <response>                     | G(trigger → X(response))
	- State-Driven| While <in state> the <system> shall <response>                   | G(in state → response)
	- Option      | Where <feature> the <system> shall <response>                    | G(feature → response)
	- Complex     | While <in state>, when <trigger>, the <system> shall <response>  | G((in state ∧ trigger) → X(response))
	- Unwanted    | If <preconditions> <trigger>, the <system> shall <response>      | G((preconditions ∧ trigger) → X(response))

-mapping from EARS to LPL

1) after a trigger is received, will the response keep pro-
duced by the system for some period?

2) if so, until when?

answer: iterating through all requirements to find the exit requirements