# VHDL Race Condition Example

This repository demonstrates a potential race condition in VHDL code.  The example showcases an issue where updating two signals within the same process and in quick succession can lead to unexpected behavior due to timing discrepancies in signal propagation.

## Bug Description
The original code attempts a simple assignment, however, due to the timing behavior of the assignment to `internal_data` and `data_out` there's a chance that `data_out` might get the value from the previous clock cycle. 

## Solution
The solution addresses this by using an intermediate signal that's updated in one process and read in another, guaranteeing correct timing.