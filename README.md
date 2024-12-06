# Race Condition in VHDL Register Transfer
This repository demonstrates a potential race condition in a simple VHDL register transfer. The issue arises from the lack of synchronization between the clock signal and the input data, which can result in unpredictable output values. 

## Bug Description
The `my_entity` VHDL code implements a simple register that transfers `data_in` to `data_out` on the rising edge of `clk`.  However, if `data_in` changes very close to the rising edge of `clk`, there's a race condition; the value captured in `data_reg` might not be the intended value. This is especially critical in high-speed designs.

## Solution
The solution introduces a synchronizing register to ensure that `data_in` is stable before it's sampled by the main register. This eliminates the race condition.