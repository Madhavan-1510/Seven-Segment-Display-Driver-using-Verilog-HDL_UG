# Seven-Segment-Display-Driver-using-Verilog-HDL
# EXP NO: 2.A Seven-Segment Display Driver using Verilog HDL
# Aim
To design and simulate a seven-segment display driver using Verilog HDL, and verify its functionality through a testbench in the Vivado 2023.1 environment. The objective is to implement the logic that converts a 4-bit binary input into the corresponding 7-segment display output for the digits 0 to 9.

# Apparatus Required
Vivado 2023.1

# Procedure

1. Launch Vivado 2023.1
Open Vivado and create a new project.
2. Design the Verilog Code
Write the Verilog code for the seven-segment display, defining the logic that maps a 4-bit binary input to the corresponding segments (a to g) of the display.
3. Create the Testbench
Write a testbench to simulate the seven-segment display behavior. The testbench should apply various 4-bit input values and monitor the corresponding output on the seven-segment display.
4. Create the Verilog Files
Create both the design module and the testbench in the Vivado project.
5. Run Simulation
Run the behavioral simulation to verify the output. Ensure the seven-segment display behaves correctly for binary inputs 0000 to 1001 (decimal 0 to 9).
6. Observe the Waveforms
Analyze the output waveforms in the simulation window, and verify that the correct segments light up for each digit.
7. Save and Document Results
Capture screenshots of the waveform and save the simulation logs. These will be included in the lab report.

# Verilog Code for Seven-Segment Display
```
`timescale 1ns / 1ps

module seven_segment_display (
    input wire [3:0] binary_input,
    output reg [6:0] seg_output
);

    always @(*) begin
        case (binary_input)

            4'b0000: seg_output = 7'b1111110; // 0
            4'b0001: seg_output = 7'b0110000; // 1
            4'b0010: seg_output = 7'b1101101; // 2
            4'b0011: seg_output = 7'b1111001; // 3
            4'b0100: seg_output = 7'b0110011; // 4
            4'b0101: seg_output = 7'b1011011; // 5
            4'b0110: seg_output = 7'b1011111; // 6
            4'b0111: seg_output = 7'b1110000; // 7
            4'b1000: seg_output = 7'b1111111; // 8
            4'b1001: seg_output = 7'b1111011; // 9
            4'b1010: seg_output = 7'b1110111; // A
            4'b1011: seg_output = 7'b0011111; // b
            4'b1100: seg_output = 7'b1001110; // C
            4'b1101: seg_output = 7'b0111101; // d
            4'b1110: seg_output = 7'b1001111; // E
            4'b1111: seg_output = 7'b1000111; // F

            default: seg_output = 7'b0000000; // blank

        endcase
    end

endmodule
```
# Testbench for Seven-Segment Display
```
`timescale 1ns / 1ps

module seven_segment_display_tb;

    // Inputs
    reg [3:0] binary_input;

    // Outputs
    wire [6:0] seg_output;

    // Instantiate the Unit Under Test (UUT)
    seven_segment_display uut (
        .binary_input(binary_input),
        .seg_output(seg_output)
    );

    // Test procedure
    initial begin

        // Test 0
        binary_input = 4'b0000;
        #10;

        // Test 1
        binary_input = 4'b0001;
        #10;

        // Test 2
        binary_input = 4'b0010;
        #10;

        // Test 3
        binary_input = 4'b0011;
        #10;

        // Test 4
        binary_input = 4'b0100;
        #10;

        // Test 5
        binary_input = 4'b0101;
        #10;

        // Test 6
        binary_input = 4'b0110;
        #10;

        // Test 7
        binary_input = 4'b0111;
        #10;

        // Test 8
        binary_input = 4'b1000;
        #10;

        // Test 9
        binary_input = 4'b1001;
        #10;

        // Test A
        binary_input = 4'b1010;
        #10;

        // Test B
        binary_input = 4'b1011;
        #10;

        // Test C
        binary_input = 4'b1100;
        #10;

        // Test D
        binary_input = 4'b1101;
        #10;

        // Test E
        binary_input = 4'b1110;
        #10;

        // Test F
        binary_input = 4'b1111;
        #10;

        $display("Seven segment display simulation completed.");

        $finish;
    end

endmodule
```

# Simulated Output
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/be72f8bb-8bbd-41e1-ab70-e186171488aa" />


# Conclusion
In this experiment, a seven-segment display driver was successfully designed and simulated using Verilog HDL. The simulation results confirmed that the display correctly represented the digits 0 to 9 based on the 4-bit binary input. The testbench effectively verified the functionality of the seven-segment display by applying various input combinations and observing the corresponding segment outputs.

This experiment highlights how Verilog HDL can be used to control hardware components like a seven-segment display in digital systems.
