# VHDL Counter Overflow Bug
This repository demonstrates a common bug in VHDL code: an integer counter that overflows without proper handling.  The `buggy_counter.vhdl` file contains the buggy code. The `fixed_counter.vhdl` file shows the corrected version.

## Bug Description
The original VHDL code implements a counter that increments on each rising clock edge. However, it lacks bounds checking. When the `internal_count` reaches its maximum value (15), it wraps around to 0, leading to unexpected behavior. This is a silent overflow that can be very difficult to debug.

## Solution
The corrected code in `fixed_counter.vhdl` uses a `mod` operator to prevent overflow.  When the counter reaches 15, the next increment resets it to 0.  This is the correct way to handle a counter that needs to wrap around to 0 after reaching a maximum value.  Alternatively one might use a std_logic_vector to avoid this issue altogether.