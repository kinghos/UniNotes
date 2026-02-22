Any new processes created will be copies of existing processes.
Don't consider the OS as a constantly running program, rather as reacting to events live.

Cooperative multitasking - form of multitasking where multitasking relies on programs not getting stuck in an infinite loop.
Processor last resort is the processor idle task, which is the background task the CPU does when it runs out of tasks to run
For each CPU, there needs to be a copy of this idle task.

States:
New
Ready - all of the programs that could be run. Can be returned from the run state
Run - scheduling one of the ready processes
Blocking - waits for event, then returns to ready state
Exit - comes from run, program finishes execution and does not want to return to the queue, returns process status code
