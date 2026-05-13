#### Version Control
Centralised - single server
Distributed - every dev has the entire history
Can work in a Git Flow approach with lots of branches, or a trunk-based approach where everyone commits to `main`
Pull requests are used to review branch merges
Issue trackers track bugs and planned features
Manual testing vs Automated testing

#### Unit testing
Mocking: Don't call the API, instead use:
- Stub - return a hardcoded value
- Mock - verify the interaction (interrogate to see if the call was proper e.g. only called once)
Tests should cover as much code as possible, but also ensuring each test is comprehensive
Mutation testing - cause chaos in code and change values/conditions and see if tests still pass
#### Development styles
Test-driven development - write tests before code
Continuous integration - find bugs as soon as they are written
Continuous delivery - any version of the code is ready to ship at any time
Continuous deployment - automated path from code to customer
Manual deployment - human oversight feels safer, but risk of error and hard to roll back

Blue/Green deployment - switch between the latest version and a rollback. Canary is similar except some users are on the latest build instead of all on one or the other
