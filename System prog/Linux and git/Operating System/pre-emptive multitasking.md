1. CPU recives interrupt
2. interrupt stores program counter
3. interrupt invokes handler 
4. handler saves rest of state of the CPU for the process
5. handler does its business
6. handler invokes the scheduler
7. scheduler selects a process to run
8. scheduler restores state of the CPU for that process
9. scheduler jumps execution to that process