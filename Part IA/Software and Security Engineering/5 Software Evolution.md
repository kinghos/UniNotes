Software is never finished
Software maintenance is split into
- Corrective
- Adaptive
- Perfective
- Preventitive
Legacy code - without tests or afraid to modify
git blame - shows who changed what line and when
git log -S - search history for when a specific string was added or removed

#### SemVer
Major.Minor.Patch versioning
Major - Breaking changes
Minor - new features
Patch - Bug fixes
Zero versioning - 0.x.y is for initial versioning, where anything may change at any time
Bump to 1.0.0 as soon as the software is used in production
SemVer is important for package managers

#### Robustness Principle (Postel's Law)
"Be conservative in what you send, be liberal in what you accept"
Ensures the API contract is stuck to

Major version bumps are bad as not everyone will move, meaning you need to maintain multiple versions

#### Deprecation Cycles
- Announce to users that a feature will be removed
- Mark as deprecated
- Wait, before removing in a major version

#### Characterisation tests
When refactoring, if code has no tests, write a test that checks the output for a given input is the same as before refactoring

#### Strangler Fig Pattern
- Write a proxy/facade that "wraps around" old legacy code
- Gradually redirect traffic to this new proxy, any new functionality should point directly to this
- Eventually the original code has no traffic and can be deprecated
