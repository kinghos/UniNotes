#### Software Engineering
Software engineering relies on teams of developers at a massive scale, with a long lifespan and a focus on maintainability and security.

*"Adding manpower to a late software project makes it later"*
Increasing team size means you need to spend time training new hires and communication gets vastly harder
It is extremely difficult to predict software as anything could happen; there is no way to predict and test every state

Effect of Moore's Law - humans could not keep up with the rate of improvement while managing complexity

Software is built as systems - components combine to provide emergent behaviour (acting in ways individual components do not)
Bugs most often lie in the interaction between perfectly written components

Maintenance:
- Corrective - fixing bugs
- Adaptive - making it work in a new environment e.g. OS
- Perfective - adding new features
- Preventive - refactoring code to prevent future decay

20% of a software's total cost is spent on initial development, while 80% is spent on maintenance and evolution over its lifetime

"Bit rot" - environments, protocols, APIs all change and hence software that isn't maintained will change

Methodology and planning helps survive the complexity

### Failures
#### Therac-25
- Medical linear accelerator used for radiation therapy, designed to destroy tumours
- Its predecessor, Therac-20, had hardware interlocks that prevented the electron beam from firing. This was replaced by software control
- Pressing X to go into high-power X-ray mode, and then quickly pressing up and E to switch to electron mode, it caused a race condition that configured the beam but did not deploy the shield
- A malfunction error was displayed but it was cryptic, and simply offered an option to proceed
Takeaways:
 - Never rely on a single software check for safety
 - Concurrency is dangerous
 - UX is safety
#### Mars Climate Orbiter
- Space probe launched by NASA and Lockheed Martin to study Martian climate and atmosphere
- Once the spacecraft passed Mars its radio signal was lost
- Lockheed wrote the thruster software using Imperial units, while NASA wrote the navigation software expecting metric units
- The specification explicitly required metric units - but NASA did not test this
- Each component was tested in isolation but did not run end-to-end simulations together
Takeaways
- Type safety - modern programming practices catch unit errors
- Integration Testing - boundaries between teams are where systems fail
- Process over Blame - systemic process breakdown, not just one person's mistake
#### London Ambulance Service
- Roll-out of Computer Aided Dispatch system for the LAS
- Goal was to automate ambulance dispatch to improve response times across London
- The contract was awarded to a company with no prior experience because they underbid the competition
- System was overloaded, ambulances were sent to the wrong locations and some places didn't get any
- Within 36 hours the system locked up entirely and many people died in the process
Takeaways
- Phase our roll-outs
- Users must be involved in the design process
- Test systems under extreme loads
#### Horizon
- Horizon by Fujitsu was meant to automate accounting for thousands of local post offices
- Subpostmasters began reporting inexplicable financial shortfalls in their accounts
- The Post Office insisted Horizon was robust and effectively infallible, and blamed the subpostmasters for missing money
Takeaways
- Audit trails in financial or legal systems - actions should be transparent
- Management

Choice of two from Fast, Good, and Cheap
