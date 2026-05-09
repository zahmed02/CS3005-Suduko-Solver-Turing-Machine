# Sudoku Multi-Tape Turing Machine Simulator

## Course: CS3005 Theory of Computation/Automata
## Instructor: Dr. Nasir Uddin

## Overview

A web-based interactive simulator that demonstrates how a **Multi-Tape Turing Machine** can solve **Sudoku puzzles**, built for a Theory of Computation/Automata (TOC/TOA) course project.

## Project Overview

This project visualizes a theoretical Turing Machine with **four tapes** that implements a backtracking algorithm to solve standard 9×9 Sudoku puzzles. The simulator breaks down the abstract computational process into step-by-step visualizations, making automata theory concepts tangible and interactive.

## Features

### Core Simulation
- **Multi-Tape TM Implementation**: Simulates a Turing Machine with four tapes:
  1. **Main Tape**: Represents the Sudoku grid in linear form
  2. **Fixed Tape**: Tracks original puzzle values (immutable cells)
  3. **Backtracking Position Tape**: Stores positions where choices were made
  4. **Backtracking Value Tape**: Stores values tried at those positions
- **State Transitions**: Implements states: `scan`, `try_value`, `accept`, `reject`
- **Backtracking Algorithm**: Demonstrates how TMs handle constraint satisfaction problems

### Interactive Visualization
- **Sudoku Grid Display**: Visual highlighting of:
  - Fixed cells (original puzzle values)
  - Filled cells (TM-placed values)
  - Current head position (animated pulse effect)
- **Main Tape Visualization**: Shows the linear representation of the grid with head tracking
- **State Diagram**: Interactive diagram showing current TM state and possible transitions
- **Backtracking Tape Display**: Shows the contents of auxiliary tapes in real-time

### User Controls
- **Step Execution**: Execute the TM one step at a time
- **Continuous Run**: Run the TM automatically with adjustable speed
- **Immediate Solve**: Solve the entire puzzle instantly (bypassing animation)
- **Reset**: Return to initial puzzle state
- **Puzzle Selection**: Choose from four difficulty levels (Easy, Medium, Hard, Expert)
- **Speed Control**: Adjust simulation speed via slider

## Puzzle Library

The simulator includes four sample Sudoku puzzles:
- **Easy**: Standard beginner puzzle with many given numbers
- **Medium**: Moderate difficulty with fewer clues
- **Hard**: Challenging puzzle requiring advanced techniques
- **Expert**: Very difficult puzzle with minimal clues

## Technical Implementation

### Architecture
- **Frontend**: Pure HTML, CSS, and JavaScript (no external dependencies)
- **TM Logic**: Custom JavaScript class implementing multi-tape TM semantics
- **UI Framework**: Responsive design with CSS Grid/Flexbox
- **Visualization**: SVG-based state diagram, CSS animations

### Key Components
1. **`SudokuTuringMachine` Class**: Core TM implementation with tape management
2. **`SudokuTMSimulator` Class**: Manages simulation state and UI updates
3. **Event-Driven UI**: Custom events synchronize TM state with visual elements
4. **Responsive Design**: Works on desktop and mobile devices

## Educational Value

This project demonstrates several key TOC/TOA concepts:
- **Multi-Tape Turing Machines**: How additional tapes simplify complex computations
- **Turing Completeness**: Solving NP problems (like Sudoku) with a TM
- **State Transition Systems**: Visualizing automata states and transitions
- **Backtracking Algorithms**: Implementing recursive algorithms iteratively
- **Tape Encoding**: Representing 2D structures in 1D tape format

## Getting Started

### Live Demo
Open `app.html` directly in any modern web browser.

### Usage Instructions
1. **Select a Puzzle**: Choose difficulty from the dropdown
2. **Load Puzzle**: Click "Load Puzzle" to initialize
3. **Control Execution**:
   - **Step**: Execute one TM transition
   - **Run**: Continuous execution (adjust speed with slider)
   - **Reset**: Return to initial state
   - **Solve Immediately**: Skip to solution
4. **Observe**: Watch tape movements, state changes, and grid updates

### Browser Compatibility
- Chrome 60+
- Firefox 55+
- Safari 11+
- Edge 79+

## Algorithm Overview

The TM implements a backtracking algorithm:
1. **Scan Phase**: Move right along tape, skipping fixed cells
2. **Try Value Phase**: When encountering empty cell, test values 1-9
3. **Validation**: Check row, column, and 3×3 box constraints
4. **Backtracking**: If no valid values, retreat to previous decision point
5. **Termination**: Accept when reaching end of tape; reject if backtracking fails

## Project Structure
```
app.html                    # Main application file (all-in-one HTML)
├── <style>                 # All CSS styles
├── <script>                # All JavaScript code
│   ├── SudokuTuringMachine # Core TM implementation
│   ├── SudokuTMSimulator   # Simulation controller
│   ├── UI Manager          # DOM manipulation and events
│   └── Puzzle Data         # Four sample Sudoku puzzles
└── <body>                  # HTML structure and UI elements
```
