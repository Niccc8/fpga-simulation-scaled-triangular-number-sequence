# x72 Processor FPGA Hardware Simulation

A web-based simulation of the x72 Processor FPGA hardware, demonstrating the calculation of a scaled triangular number sequence.

## 🌟 Features

- **FPGA Hardware Simulation**: Visualizes 7-segment displays, LEDs, and system state.
- **Instruction Memory**: Shows the assembly code execution in real-time with a program counter (PC) tracker.
- **Data Path Monitor**: Displays internal register values (R0, R1, R2, R7) and FSM states (T1-T4).
- **Visualization Panel**:
  - **Formula Display**: Break down of the formula `S(n) = [n × (n+1) ÷ 2] × 10`.
  - **Interactive Chart**: Real-time bar chart showing the growth of the sequence values.
- **Controls**:
  - **Step (KEY1)**: Execute one clock cycle.
  - **Run Program**: Automatically run the simulation.
  - **Reset (KEY0)**: Reset the processor to the initial state.
  - **Clock Speed**: Adjustable simulation speed.

## 🚀 How to Run

Simply open `fpga_simulation.html` in any modern web browser. No installation or server is required.

## 🛠️ Tech Stack

- **HTML5**: Structure and semantic markup.
- **CSS3**: Glassmorphism design, animations, and responsive layout.
- **JavaScript (ES6+)**: Simulation logic, DOM manipulation, and state management.

## 📝 Assembly Program

The simulation runs the following assembly program to calculate the sequence:

```assembly
start: movi R0, 1   // Init n=1
loop:  movi R1, 0   // Clear Acc
       add R1, R0   // Acc += n
       movi R2, 1   // R2 = 1
       add R2, R0   // R2 = n+1
       mul R1, R2   // Acc = n*(n+1)
       ssi R1, -1   // Acc >> 1 (Acc / 2)
       mul R1, 10   // Scale by 10
       disp R1      // Show Result
       addi R0, 1   // n++
       bez R7, loop // Loop back
```

## 🎨 Design

The interface features a **Monochrome Glassmorphism** aesthetic with:
- Dark mode optimization.
- Cyan accents for active elements.
- Smooth transitions and animations.
- Rounded corners and frosted glass effects.

## 👤 Author

**Nicholas Choong Chen Juin**
