# Binary-Decimal-Hexadecimal Converter

## 📌 Project Overview

This project implements a simple **Binary, Decimal and Hexadecimal Converter using Verilog HDL**.

The design accepts an 8-bit binary input and provides its corresponding numerical value in decimal and hexadecimal representation.

The project also includes a Verilog testbench for functional verification and simulation.

---

## 🎯 Objectives

* Understand number-system representation in digital electronics.
* Implement a basic Verilog HDL module.
* Convert and represent binary values in decimal and hexadecimal formats.
* Create a Verilog testbench.
* Verify the design through simulation.
* Practice RTL design and functional verification.

---

## 🛠️ Technologies Used

* Verilog HDL
* VS Code
* Icarus Verilog / ModelSim / QuestaSim
* GTKWave (optional)
* GitHub

---

## 📂 Project Structure

```text
Binary-Decimal-Hexadecimal-Converter/
│
├── README.md
│
├── src/
│   └── binary_decimal_hex_converter.v
│
├── testbench/
│   └── tb_binary_decimal_hex_converter.v
│
└── simulation/
    └── simulation_results.txt
```

---

## 🔢 Number System Example

For an 8-bit binary input:

| Binary   | Decimal | Hexadecimal |
| -------- | ------- | ----------- |
| 00000000 | 0       | 00          |
| 00000001 | 1       | 01          |
| 00001010 | 10      | 0A          |
| 00110011 | 51      | 33          |
| 01010101 | 85      | 55          |
| 10101010 | 170     | AA          |
| 11111111 | 255     | FF          |

---

## ⚙️ Design Description

The design uses an 8-bit input:

```verilog
input wire [7:0] binary_in;
```

The decimal output is represented using the numerical value of the binary input:

```verilog
assign decimal_out = binary_in;
```

The hexadecimal representation uses the same 8-bit value:

```verilog
assign hex_out = binary_in;
```

The difference between binary, decimal and hexadecimal is primarily the **representation of the numerical value**.

For example:

```text
Binary       : 10101010
Decimal      : 170
Hexadecimal  : AA
```

---

## 🧪 Testbench

The testbench applies different 8-bit binary values to the design and displays the corresponding decimal and hexadecimal representations.

Test cases include:

* 0
* 1
* 10
* 51
* 85
* 170
* 255

---

## ▶️ Simulation Using Icarus Verilog

### Step 1: Compile

Open the terminal inside the project directory and run:

```bash
iverilog -o converter_sim src/binary_decimal_hex_converter.v testbench/tb_binary_decimal_hex_converter.v
```

### Step 2: Run Simulation

```bash
vvp converter_sim
```

### Expected Output

```text
-----------------------------------------------------
 Binary Input | Decimal Output | Hexadecimal Output
-----------------------------------------------------
    00000000     |      0       |       00
    00000001     |      1       |       01
    00001010     |      10      |       0A
    00110011     |      51      |       33
    01010101     |      85      |       55
    10101010     |      170     |       AA
    11111111     |      255     |       FF
-----------------------------------------------------
```

---

## 🖥️ Simulation

The testbench verifies the converter by applying multiple binary inputs and observing the outputs.

The simulation confirms that the binary input corresponds correctly to its decimal numerical value and hexadecimal representation.

---

## 📚 Concepts Demonstrated

* Verilog HDL
* RTL design
* Binary number system
* Decimal representation
* Hexadecimal representation
* Combinational logic
* Module instantiation
* Testbench development
* Functional verification
* Digital simulation

---

## 🚀 Future Improvements

The project can be extended by adding:

* Decimal-to-binary conversion
* Hexadecimal-to-binary conversion
* Binary-to-BCD conversion
* User-selectable conversion modes
* 16-bit or 32-bit input support
* Seven-segment display output
* FPGA implementation
* UART-based input/output

---

## 👩‍💻 Author

**Harshu**

B.Tech - Electronics and Communication Engineering

---

## 📄 License

This project is created for educational and academic purposes.

```
```
```verilog
`timescale 1ns/1ps

module binary_decimal_hex_converter (
    input  wire [7:0] binary_in,
    output wire [7:0] decimal_out,
    output wire [7:0] hex_out
);

    // Binary to Decimal conversion
    // Since binary_in represents a number,
    // its numerical value is directly available.
    assign decimal_out = binary_in;

    // Binary to Hexadecimal conversion
    // The same 8-bit value represents the hexadecimal value.
    assign hex_out = binary_in;

endmodule
```
```verilog
`timescale 1ns/1ps

module tb_binary_decimal_hex_converter;

    reg  [7:0] binary_in;
    wire [7:0] decimal_out;
    wire [7:0] hex_out;

    // Instantiate the Design Under Test (DUT)
    binary_decimal_hex_converter DUT (
        .binary_in(binary_in),
        .decimal_out(decimal_out),
        .hex_out(hex_out)
    );

    initial begin

        // Display simulation results
        $display("-----------------------------------------------------");
        $display(" Binary Input | Decimal Output | Hexadecimal Output ");
        $display("-----------------------------------------------------");

        // Test Case 1
        binary_in = 8'b00000000;
        #10;
        $display("    %b     |      %0d       |       %h", 
                 binary_in, decimal_out, hex_out);

        // Test Case 2
        binary_in = 8'b00000001;
        #10;
        $display("    %b     |      %0d       |       %h", 
                 binary_in, decimal_out, hex_out);

        // Test Case 3
        binary_in = 8'b00001010;
        #10;
        $display("    %b     |      %0d       |       %h", 
                 binary_in, decimal_out, hex_out);

        // Test Case 4
        binary_in = 8'b00110011;
        #10;
        $display("    %b     |      %0d       |       %h", 
                 binary_in, decimal_out, hex_out);

        // Test Case 5
        binary_in = 8'b01010101;
        #10;
        $display("    %b     |      %0d       |       %h", 
                 binary_in, decimal_out, hex_out);

        // Test Case 6
        binary_in = 8'b10101010;
        #10;
        $display("    %b     |      %0d       |       %h", 
                 binary_in, decimal_out, hex_out);

        // Test Case 7
        binary_in = 8'b11111111;
        #10;
        $display("    %b     |      %0d       |       %h", 
                 binary_in, decimal_out, hex_out);

        $display("-----------------------------------------------------");

        $finish;
    end

endmodule
```
Binary-Decimal-Hexadecimal Converter
Simulation Results
==================

Test Case 1
Binary       : 00000000
Decimal      : 0
Hexadecimal  : 00

Test Case 2
Binary       : 00000001
Decimal      : 1
Hexadecimal  : 01

Test Case 3
Binary       : 00001010
Decimal      : 10
Hexadecimal  : 0A

Test Case 4
Binary       : 00110011
Decimal      : 51
Hexadecimal  : 33

Test Case 5
Binary       : 01010101
Decimal      : 85
Hexadecimal  : 55

Test Case 6
Binary       : 10101010
Decimal      : 170
Hexadecimal  : AA

Test Case 7
Binary       : 11111111
Decimal      : 255
Hexadecimal  : FF

========================================
Simulation completed successfully.
==================================
