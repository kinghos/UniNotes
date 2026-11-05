Multiple nodes communicating via an unreliable network trying to achieve some task together
- Better reliability - if one node fails, the system keeps functioning
- Better performance - get data from a nearby node rather than one halfway round the world
- Solve bigger problems
#### Networking
- Abstract down to a node passing a message to another node
- Node could be a server, computer, phone, car etc.
- Can be transmitted in various different ways e.g. WiFi, Bluetooth, current, hard drives in a van
- A distributed system is concerned with solving goal, while networking is just how to get data from A to B
#### Remote Procedure Call
- Tell another node to call a function
- 