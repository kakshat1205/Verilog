# Basic info on how to design FSM in Verilog
I will basically focus on Moore machine due to following reasons :
Output is syncronised with the clock
Output will change on clock edge irrespective of change in input(Important to avoid setup timing voilation)
So in case of Mealy machines as ouput can be changed at any time because of Input it is more prone to setup voilations(Hence glitches or wrong inputs of the FSM)


## FSM to be designed
![image](https://user-images.githubusercontent.com/49076977/123484931-c361cd00-d626-11eb-8cc8-f9b7b8a78440.png)

## Following steps are followed to design any FSM
- A state encoding for each step
- A mechanism to keep track of current state
- Transitions from state to state
- Output value based on current state

## Should we try to reduce the FSM to most optimised way possible:
It is not recommended applying state minimization techniques by hand. They have the tendancy to
introduce bugs and create cryptic FSMs that cannot be easily understood by human readers. This defeats
one of the large pros of Verilog: human readability. Furthermore, the Synthesis tools that ‘compile’ an
FSM, written in Verilog, perform state minimization automatically. Only perform state minimization
manually to the extent that the function of the FSM remains clear.
