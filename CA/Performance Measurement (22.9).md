>[!Definition] Metrics
>There are various types of metrics, two keys metrics are:
> 1. Response Time (Execution Time) - time to complete a task.
> 2. Throughput (Bandwidth) - tasks completed per unit of time

>[!Definition] Relations Between Response Time and Throughput
>Improving one often improves the other
>Given processor X:
>$$Performance_{X}=\frac{1}{\text{Execution Time}}_{X}$$
>
>We can use those 2 values to compare X with another processor Y.
If X is faster than Y:
>$$\text{Performance}_{X}>\text{Performance}_{Y} \Longleftrightarrow \text{Execution Time}_{X}<\text{Execution Time }_{Y} $$
>and vice versa

>[!Definition] Relative Performance
>To compare 2 computer, we have this **Performance Ratio** formula:
>$$\frac{\text{Performance}_{\mathbf{X}}}{\text{Performance}_{\mathbf{Y}}}=\frac{\text{Execution Time}_{\mathbf{Y}}}{\text{Execution Time}_{\mathbf{X}}}=n$$
>Now we can say computer X is *n* times faster than computer Y

>[!Definition] Measuring CPU Performance
>We can only use time to measure the performance of a CPU as it is the most reliable way to do so. The metric is often called CPU time or CPU **Execution Time**
>
>**The Story of Formulas**:
>Imagine Clock Cycles is the currency of your CPU, meaning that when executing an instruction, we have to spend a certain amount of Clock Cycles. In order to  simplify the process of calculating, some geniuses came up with CPI, a new currency that represent the avr number of clock cycles to execute each instruction. Like Euros which can be used in all Europe, CPI is what we used to calculate the total amount of of clock cycles of a whole instructions set architecture. Speaking of instruction set, it's like a list of thing our CPU need to spend "money" on. Therefore, the number of those set is called Instruction Count. Hence, CPU Clock Cycles is expressed as:
>
>$$\text{CPU Clock Cycles}=\text{Number of Intructions for a Program (Instruction Count or IC)} \times \text{Avr CPI}$$
>
>Stay with me eh? Here comes the Clock Cycle Time. Clock Cycles Time is like the amount of time our CPU need to print out those "money". And the Clock Rate is like the amount of money it print in 1 second. Hope this make you feel better with those below formulas
>
>Fundamental Relation:
>$$\text{CPU Time}=\frac{\text{CPU Clock Cycles}}{\text{Clock Rate (Hz)}}$$
>$$\text{CPU Time}=\text{CPU Clock Cycles} \times \text{Clock Cycle Time}$$
>$$\implies \text{Clock Cycle Time}=\frac{1}{\text{Clock Rate (Hz)}}$$
>
>**CPI (Clock Cycles per Instruction):**
>- Avr number of clock cycles each instruction takes
>- Different instructions take diff time, CPI is the avr
>- Useful for comparing difference implementations of the same ISA (Instruction Set Architect)
>  
>**TL;DR**
>  $$\text{CPU Times}=\text{Instruction Count} \times \text{CPI} \times\text{Clock Cycle Time}$$













