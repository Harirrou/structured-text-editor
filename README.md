# ST Programming Learning Platform

A web-based editor and simulator for Structured Text (ST) programming. This platform allows users to learn and practice ST programming for PLCs directly in the browser without requiring any special software.

## 🚀 [Try It Now](https://harirrou.github.io/structured-text-editor/)

## Features

- **Interactive Code Editor** with syntax highlighting
- **Code Snippets** for common ST structures (IF, FOR, WHILE, etc.)
- **Simulation Engine** to execute ST code directly in the browser
- **Variable Monitor** to track variable values during simulation
- **Force Values** functionality to manipulate variables during runtime
- **Syntax Checking** for ST code validation

## Usage Guide

### Code Editor

1. Write your ST code in the editor or start with the sample program
2. Use the snippet buttons (IF, FOR, WHILE, etc.) to insert code templates
3. The editor provides syntax highlighting to make code easier to read

### Simulation

1. Click "Check Syntax" to validate your code before running
2. Click "Run Simulation" to start the program execution
3. Watch the output panel to see execution results
4. Use the variable monitor to track changing values
5. Click "Stop Simulation" to halt execution at any time

### Variable Monitoring

1. Variables are automatically extracted from your code
2. During simulation, their values update in real-time
3. Use the "Force" button to manually change variable values
4. Forced values will affect the program's execution

## Sample Programs

### Counter Example
```
PROGRAM HelloWorld
VAR
  Counter : INT := 0;
  MaxCount : INT := 10;
  Running : BOOL := TRUE;
  Message : STRING := 'Hello, PLC World!';
END_VAR

WHILE Running DO
  Counter := Counter + 1;
  
  IF Counter >= MaxCount THEN
    Running := FALSE;
  END_IF;
END_WHILE;

END_PROGRAM
```

### Temperature Controller Example
```
PROGRAM TemperatureController
VAR
  CurrentTemp : REAL := 22.5;
  TargetTemp : REAL := 25.0;
  HeaterOutput : BOOL := FALSE;
  CoolerOutput : BOOL := FALSE;
  Hysteresis : REAL := 0.5;
END_VAR

IF CurrentTemp < (TargetTemp - Hysteresis) THEN
  HeaterOutput := TRUE;
  CoolerOutput := FALSE;
ELSIF CurrentTemp > (TargetTemp + Hysteresis) THEN
  HeaterOutput := FALSE;
  CoolerOutput := TRUE;
ELSE
  HeaterOutput := FALSE;
  CoolerOutput := FALSE;
END_IF;

END_PROGRAM
```

## About Structured Text (ST)

Structured Text is a high-level programming language used for programming Programmable Logic Controllers (PLCs). It is one of the five languages defined by IEC 61131-3 standard and resembles Pascal or C programming languages.

ST is widely used in industrial automation for:
- Process control
- Motion control
- Batch processing
- Safety systems

## Technologies Used

- HTML5, CSS3, and JavaScript
- [CodeMirror](https://codemirror.net/) for the code editor
- GitHub Pages for hosting

## Development

This project is open source. Feel free to fork and contribute!

1. Clone the repository
2. Open `index.html` in your browser
3. Make changes to improve the platform
4. Submit a pull request with your improvements

## License

MIT License