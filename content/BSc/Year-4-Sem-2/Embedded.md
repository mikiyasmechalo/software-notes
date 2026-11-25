---
title: Embedded Systems
teacher: Mr. Kassahun
---
# CH 1: Introduction to digital logic
#### Logic algebra
aka *Boolean algebra* 
 Key Concepts:
1. Binary Variables - 0 or 1, the absence (0) or presence (1) of a logical condition.
2. logical Operations - AND (∧, . ) (Conjunction), OR (∨, +) (Disjunction), NOT (¬, ' ) (Negation)
3. Boolean Expressions - used to represent and analyze the behavior of digital circuits and systems.
4. Truth Tables - used to represent the output of a Boolean expression for all possible combinations of input values.

**Basic Laws of Logic Algebra**: 
1. Identity Laws:
	- A+0=A
	- A⋅1=A
2. Domination Laws:
	- 1A+A′=1 , or 1+X=1
	- 0A⋅A′=0, or 0.X=0
3. Idempotent Laws:
	- A+A=A
4. Commutative Laws:
	- A+B=B+A
	- A⋅B=B⋅A
5. Associative Laws:
	- (A+B)+C=A+(B+C)
	- (A⋅B)⋅C=A⋅(B⋅C)
6. Distributive Laws:
	- A⋅(B+C)=(A⋅B)+(A⋅C)
	- A+(B⋅C)=(A+B)⋅(A+C)
7. De Morgan's Laws:
	- (A+B)′=A′⋅B′
	- (A⋅B)′=A′+B′

#### Logic Circuits
Use digital signals (binary, consisting of 0s and 1s) to process and manipulate information.

Key Components of Logic Circuits:
1. **Logic Gates**: AND, OR, NOT - the fundamental building blocks of logic circuits.
2. **Flip-flops** store binary information and are used as memory elements.
3. **Registers**: collections of flip-flops for temporary data storage.
4. *Multiplexers and Demultiplexers*:
	* Multiplexers select one of several input data lines and direct it to a single output line.
	* Demultiplexers direct one input to several output lines.
5. **Arithmetic Logic Units (ALUs)**: perform arithmetic and logic operations on binary numbers.
6. **Decoders and Encoders**: decoders convert binary information from one code to another, while encoders perform the opposite task.
	- They are essential for tasks such as data compression and decompression.

**Types of Logic Circuits** 
1. **Combinational Logic Circuits**: Produce output based solely on current input values. "combination of logic gates"
2. **Sequential Logic Circuits**: Include memory elements like flip-flops, output depends on current inputs and previous state.
	* Have a notion of time and memory.
3. **Digital Signal Processors (DSPs)**: Specialized processors for tasks like audio and image processing.
4. **Microprocessors and Microcontrollers**: Central processing units (CPUs) in computers and embedded systems.
	- extensive logic circuitry to execute instructions, manage memory, and control peripherals.

**Applications of Logic Circuits** 
1. **Computer Processors**: CPUs execute instructions and perform arithmetic and logic operations.
2. **Memory Systems**: Flip-flops and registers in logic circuits form the basis of memory systems.
3. **Control Systems**: Managing and coordinating components in industrial, automotive, and robotic applications.
4. **Communication Systems**: Signal modulation, demodulation, and error detection and correction.
5. **Consumer Electronics**: Smartphones, TVs, and digital cameras use logic circuits for processing and control.
6. **Automotive Electronics**: Engine control, airbag deployment, and entertainment systems.
7. **Embedded Systems**: Controlling and coordinating functions in devices like IoT devices, medical instruments, and industrial controllers.

#### Logic Devices
1. **Counters** - are sequential logic circuits that count in a prescribed sequence.
	* Types of Counters
		+ **Binary Counters**: 000, 001, 010, ...
		+ **Decade Counters**: 0, 1, 2, ..., 9
		+ **Up Counters** 
		+ **Down Counters** 
		+ **Synchronous Counters** - The state of each flip-flop is updated simultaneously.
		+ **Asynchronous Counters** - Asynchronous Counters: The state of each flip-flop is updated sequentially
			**Example:** 
			*  **Synchronous Watch:** Displays time with a clean, simultaneous update of all digits (e.g., `10:59:59` to `11:00:00` instantly).
			*  **Asynchronous Watch:** Would show a staggered, "ripple" effect as digits change sequentially (e.g., `10:59:59` might momentarily show `10:59:00`, then `10:00:00`, before `11:00:00`).
2. **Timers** 
	* Measure the duration of time intervals, used for precise time control and scheduling of events.
	* Types of Timers
		+ **Monostable Multivibrators**: Output stays high for a fixed duration after triggering
		+ **Astable Multivibrators**: Produce a continuous square wave output
		+ **Digital Timers**: Implemented using digital logic circuits for more accurate timing
3. **Finite State Machines (FSMs)**
	* Model the behavior of systems that can exist in a finite number of states
	* Types of FSMs
		+ **Moore Machines**: Output depends only on the current state
		+ **Mealy Machines**: Output depends on both the current state and inputs
	* Key Components of FSMs:
		+ **States**: Represent different modes or conditions
		+ **Transitions**: Define conditions triggering state changes
		+ **Inputs**: External signals influencing state transitions
		+ **Outputs**: Actions or signals produced by the FSM in different states

# CH 2: Introduction to Embedded Systems
Any device that includes a programmable computer but is not itself a general-purpose computer.

- ES - a computing device that does a specific focused job within a larger system.
	- e.g. air conditioner, CD-DVD Player, Printer ...
- Each has a processor and a specialized hardware along with an embedded software executed by the processor.
- The embedded software is called a **firmware**.

An embedded system combines five fundamental components:
1. User
2. Procedure
3. Hardware (HW)
4. Software (SW)
5. Data

**Features of Embedded Systems** 
- They do a specific task and cannot be programmed to do different things(by the end user).
- They have limited resources, particularly memory.
- They don't have secondary storage.
- They work against deadlines. a job has to be completed within a specific time.
- Some embedded systems, called *real time* systems, the dead lines are *stringent*/ strict.
- Embedded systems are constrained for power. since most use battery's.
- They need to be highly reliable. Resetting the embedded system is very difficult.
- Some of them has to operate in extreme environments.

**Characteristics of an Embedded System** 
* **Real-Time Operation** - **Reactive**: computations must occur in response to external events.
	+ Correctness is partially a function of time
* Small Size, Low Weight
* Low Power 
* **Harsh Environment** - Exposure to heat, vibration, shock, power fluctuations, RF interference, lightning, and corrosion
* **Safety-Critical Operation** - Must function correctly, mustn't function incorrectly 
* **Extreme Cost Sensitivity** - Small costs can add up over large quantities

### Components of Embedded Systems
1. **Microcontroller or Microprocessor**: a CPU tailored for the specific application.
2. **Memory**: to store program and data required for operation.
3. **I/O interface**: connect the ES to sensors, actuators and external devices.
4. **Real-time operating system (RTOS)**: manages time critical operations in real time ES.
5. **Power Supply**: designed to operate within specific power constraints.
6. **Connection interfaces**: to interact with other devices or systems.

Processor Modes:
- Minimum Mode: The processor works to execute a specific task independently.
- Maximum Mode: Used for multitasking or multi-purpose processing.

**Microcomputer vs ES** 

| Feature          | General-Purpose System                                                                   | Embedded System                                                                                                      |
| ---------------- | ---------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Task / Purpose   | Multi-purpose                                                                            | Dedicated task                                                                                                       |
| Speed            | Fast execution for varied tasks                                                          | Optimized speed for a specific task                                                                                  |
| Memory           | "Unlimited" / highly expandable memory                                                   | Limited memory                                                                                                       |
| Core Device      | Microprocessor based                                                                     | Microcontroller based                                                                                                |
| Operating System | Standard OS (e.g., Windows, macOS) designed for multi-tasking; uses traditional kernels. | Embedded OS (e.g., Android) or RTOS (Real-Time Operating System) designed for specific tasks with real-time kernels. |
| Hardware Layers  | Application → Middleware → Device Driver → Hardware                                      | Application → Middleware → Hardware                                                                                  |
| e.g.             | Personal computers, laptops, workstations                                                | Automotive control systems, medical devices, smart appliances                                                        |
Microprocessors vs. Microcontrollers: * A Microprocessor contains just the CPU on the chip.
- A Microcontroller is considered the "brain of the ES" and is fully integrated (integrating RAM, ROM, ALU, CPU, and Control Unit onto a single chip).

**Four General Embedded Systems Types** 
*General Computing* - Applications similar to desktop computing, but in an embedded package.
* Video games, set-top boxes, wearable computers, automatic tellers
*Control Systems* - Closed-loop feedback control of real-time systems
* Vehicle engines, chemical processes, nuclear power, flight control
*Signal Processing* - Computations involving large data streams
* Radar, Sonar, video compression
*Communication & Networking* - Switching and information transmission
* Telephone systems, Internet

### Categories of ES
1. Stand alone embedded system
2. Real time systems
3. Networked information appliances
4. Mobile devices

##### Standalone alone embedded systems
- Can function independently without relying on a host system.
- performs a dedicated task or set of tasks on its own, with no or minimal human intervention.
- Take inputs, process them and produce the desired output.
- Input can be electrical signal from transducers or commands from a human being such as the pressing of the button.
*Example*: digital watches, mp3 player, digital cameras, washing machines ..

##### Real time systems 
- Work has to be done in a specific time period (strict deadlines).
- hard real time systems - missing a deadline can be catastrophic.
- In some embedded systems, deadlines are imposed, but not adhering to them.
- Missing a deadline may result in catastrophic failure.
- Applications like industrial automation, medical devices, and automotive control systems.
*Example*: Video Streaming, Online Gaming, Voice Assistants

##### Networked Information Appliance
Provided with network interfaces and accessed by networks such as Local Area Network (LAN).
These systems run the protocol TCP / IP stack and get connected either through *Point to Point Protocol* (PPP) or Ethernet to a network and communicate with other nodes in the network.
e.g. a camera connected to the internet, smart door lock.

##### Mobile Devices
(PDAs), smart phones, etc. Are a special category of embedded systems.
The limitations of the mobile devices- memory constraints, small size, lack of good user interface such as full fledged keyboard and display etc. Are same as those found in the embedded system.

### Overview of ES Architecture
 Every embedded system consists of custom built hardware built around a Central Processing Unit (CPU). The software/ firmware is loaded into memory chips.
The operating system runs above the hardware, and the application software runs above the operating system.
The same architecture is applicable to any computer including desktop.
However, they are significant differences. It is not compulsory to have an operating system in every embedded system.

*Layers:* 
Hardware -> Operating Systems -> Application Software

The various building blocks of the hardware of an embedded system: (all are connected to CPU)
- Central Processing Unit (CPU)
- Memory (RAM and ROM)
- Input Devices
- Output Devices
- Communication interfaces
- Application specific circuitry

**CPU** 
- Can be Microprocessor, microcontroller or digital signal processor.
- Microcontroller usually includes memory, serial interfaces, ADC etc.
- Microcontrollers are preferred rather than Microprocessors because they require less external components. 
- DSP is used mainly for application in which signal processing is involved such as audio and video processing.

**Memory** 
- Firmware is stored in ROM, w/c the processor accesses on power on, the contents are then transferred to RAM to execute the program.

**Input Devices** 
- Input devices for ES have limited capabilities. no keyboard or mouse.
- Many embedded systems used in process control do not have any input device for user interaction, they take inputs from sensors or transducers and produce electrical signals that are in turn fed to the other systems.

**Output Devices** 
- Output devices also have very limited capability.
- Some embedded system will have a few (LEDs) to indicate the health status of the system modules, or for visual indication of alarms.
- A small Liquid Crystal Display (LCD) may also be used to display the parameters.

**Communication Interfaces** 
- To interact with other embedded systems or to transmit data to a desktop.
- RS232, RS422, RS485, Universal Serial Bus (USB), IEEE 1394, Ethernet, etc,.


**Input/Output (I/O) Units**
* I/O units facilitate communication between the embedded system and the external world.
* Characteristics:
	+ Peripheral Interfaces: Connect the system to external devices.
	+ Data Transfer: Manage data flow between CPU and peripherals.
	+ Interrupt Handling: Handle external events requiring immediate attention.
* Types of I/O Units:
	1. **Serial Communication Interfaces** 
		- Used for communication with devices like sensors and GPS modules.
		- Examples: UART, SPI, I2C.
	2. **Parallel I/O Ports** 
		- Used for connecting to devices requiring multiple data lines.
		- Examples: GPIO ports.
	3. **Analog-to-Digital Converters (ADC)** - Convert analogue signals to digital signals.
	4. **Digital-to-Analog Converters (DAC)** - Convert digital signals to analogue for output.
* Applications:
	+ Sensor Integration: Collect data from the environment.
	+ Actuator Control: Drive external devices.
	+ Communication: Establish communication with other systems or devices.

### Processor architectures, microcontrollers used in embedded systems

**Architectural Classifications**
Embedded processor architectures handle how data and instructions are fetched from memory differently.
1. **Von Neumann Architecture** 
    * Data and instructions are stored together in a single, shared memory space.
    * Uses a single shared bus system to transmit both data and instructions.
    * Requires 2 clock cycles to complete an operation (1 cycle to fetch the instruction, 1 cycle to fetch the data).
    * Note: By using a control bus, it becomes bi-directional to ensure both types of transfers can occur. It is generally hard-wired.
    * Used in: x86 PCs, general-purpose computers

2. **Harvard Architecture** 
    * Data and instructions are stored separately in distinct physical memory spaces.
    * Uses 2 separate buses (one for data, one for instructions).
    * Operates on a single set of clock cycles because it can fetch data and instructions simultaneously.
    * Supports pipelining for faster instruction processing due to simultaneous data/instruction access.
    * Used in: AVR (Arduino Uno), PIC, DSPs, most microcontrollers

3. **Super Harvard Architecture**
    * An advancement that combines the Harvard Architecture + Cache Memory.
    * Includes internal cache memory to control and accelerate transmission speeds even further.

##### Processor architectures
In embedded systems, the choice of processor architecture is crucial, as it directly impacts the system's performance, power consumption, and overall capabilities.
1. **ARM (Acorn RISC Machine) Architecture** 
	- known for its Reduced Instruction Set Computing (RISC) design.
	- *Characteristics:*
		- Power-efficient and suitable for battery-powered devices.
		- Found in a variety of applications, from mobile devices to IoT devices.
		- Scalable architecture with different performance levels (e.g., Cortex-M, 	Cortex-A).

2. **x86 Architecture** 
	- originally developed by Intel, is a complex instruction set computing (CISC).
	- *Characteristics:* 
		- Commonly found in personal computers and servers.
		- Offers high performance but may consume more power compared to RISC.
		- Supports a wide range of software applications.

3. **MIPS (Microprocessor without Interlocked Pipeline Stages) Architecture** 
	- another RISC architecture widely used in embedded systems.
	- *Characteristics:* 
		- Often used in networking equipment, routers, and communication devices.
		- Known for its simplicity and efficiency in certain applications.

4. **Power Architecture** 
	- initially developed by IBM, is used in various embedded systems, particularly in automotive and industrial applications.
	- *Characteristics:* 
		- Known for its high performance and power efficiency.
		- Widely used in automotive engine control units (ECUs) and industrial controllers.

5. **RISC-V Architecture** 
	- RISC-V is an open-source RISC architecture that has gained popularity for its flexibility and openness.
	- *Characteristics:* 
		- Open standard architecture, allowing for customization and innovation.
		- Increasingly used in research, education, and some commercial applications.

##### Microcontrollers
Microcontrollers are integrated circuits that include a processor, memory, and input/output peripherals, all on a single chip.
They are specifically designed for embedded systems and are commonly used in applications where a dedicated, low-power, and cost-effective solution is needed.

1. **Arduino**:
	- uses various microcontrollers from different manufacturers. e.g. the `ATmega` series from Microchip.
	- *Characteristics*:
		- Easy to use, suitable for beginners and rapid prototyping.
		- Well-supported with a large community and a vast collection of libraries.

2. **PIC** Microcontrollers: manufactured by Microchip.
	- *Characteristics*:
		- Widely used in industrial control, automotive, and consumer electronics.
		- Known for their versatility and cost-effectiveness.

3. **STM32** (ARM Cortex-M):
	- based on ARM Cortex-M architecture
	- *Characteristics*:
		- High-performance ARM Cortex-M cores.
		- Extensive support and documentation from STMicroelectronics.

4. **ESP8266/ESP32**:
	- Developed by `Espressif`, these microcontrollers are designed for IoT applications.
	- *Characteristics*:
		- Integrated Wi-Fi capabilities.
		- Commonly used in IoT devices and home automation.

5. **Raspberry Pi** (BCM283x): 
	- often considered a single-board computer, it includes a microcontroller (BCM283x) for various GPIO and control purposes.
	- *Characteristics*:
		- Combines the capabilities of a microcontroller with those of a small computer.
		- Used in various educational and DIY projects.

### Interrupts
- An interrupt is a signal sent to the processor, typically by an external device or a special internal condition, to request the processor's attention and immediate handling of a specific event or task.
- Allow the processor to respond quickly to external events or conditions without constantly polling for them.
- They enable the system to handle asynchronous events and improve overall responsiveness. 

##### Types of Interrupt
1. **Hardware Interrupts** (INT1)
	a. *External Interrupts* 
	- Triggered by external devices or peripherals. Button presses, sensor signals ...
	b. *Timer Interrupts* 
	- Generated by an internal timer or counter.
	- Used for scheduling tasks, measuring time intervals, or periodic events.
	c. *DMA (Direct Memory Access) Interrupts* 
	- Raised by DMA controllers after data transfer completion.

2. **Software Interrupts** (Traps) (INT2)
	- Allows the software to request specific services from the operating system or kernel.

**Maskable Interrupt (MI) vs. Non-Maskable Interrupt (NMI)**:
- Maskable Interrupt: Can be ignored or disabled by the CPU using software registers.
- Non-Maskable Interrupt (NMI): Cannot be ignored by the CPU; reserved for critical system actions (e.g., power failure).

**Vector Interrupt vs. Non-Vector Interrupt**:
- Vector Interrupt: The CPU automatically knows where the Interrupt Service Routine (ISR) is located via a Vector Interrupt Table (stores the start address). This provides fast interrupt handling (also known as edge-triggered).
- Non-Vector Interrupt: The CPU does not automatically know the address and must manually poll or branch to find the source, making it slower than vector interrupts.

**Polling vs. Interrupts**:
- *Polling*: Continuously checking all devices sequentially to see if they need attention. This happens if no interrupt mechanism is implemented, which wastes CPU cycles.
- *Interrupt*: The device actively alerts the CPU only when it needs attention, maximizing CPU efficiency.

##### Interrupt Handling Process
1. **Interrupt Request (IRQ)**:
	- An external event occurs, generating an interrupt request.
	- The interrupt request is sent to the processor.
2. **Interrupt Controller**:
	- Manages and prioritizes interrupt requests.
	- Routes the interrupt to the appropriate interrupt service routine (ISR).
3. **Context Switching**:
	- The processor saves the current state of the program being executed.
	- Switches to the interrupt service routine.
4. **Interrupt Service Routine (ISR)**:
	- A specialized function that handles the interrupt.
	- Performs tasks related to the interrupting event.
5. **Return from Interrupt (RTI)**:
	- Restores the saved context and resumes the interrupted program.

##### Advantages of Interrupts
- *Efficiency*: Reduces the need for constant polling, saving processing resources.
- *Responsiveness*: Enables quick response to time-sensitive events.
- *Prioritization*: Allows the system to prioritize and handle critical events first.
- *Concurrency*: Permits the processor to perform multiple tasks simultaneously.

##### Common Uses of Interrupts
- *Input Handling*: Responding to button presses, sensor readings, or external signals.
- *Communication*: Handling data arrival or transmission in communication interfaces.
- *Timer-based Tasks*: Scheduling periodic tasks or measuring time intervals.
- *Error Handling*: Responding to error conditions or exceptional events.

##### Interrupts and Real-Time Systems
* In real-time systems, interrupt latency and priorities are crucial to meeting performance requirements.
* Interrupts provide a mechanism for handling asynchronous events efficiently and improving system responsiveness.

# CH 3: Hardware level programming of embedded systems
PT 1

**Design of an Embedded System** (steps)
1. *Specifying hardware required* - processor, interface, power supply, reset circuit
2. *Specifying sensors and actuators* to be used - digital or analog,...
3. *System integration and writing the code* - with system inputs, external ports, sensors, actuators.
	- compiling, debugging, simulating, downloading the written code to the target device. 
	- Consider interrupt configurations during this phase.
4. *Testing the system performance* , debugging

### Assembly Programming
Assembly programming uses mnemonics, which have four columns:
* **Label**: a name given to a program line
* **Mnemonic**: specific code for the task to be performed
* **Operand**: data needed to complete the instruction
* **Comment**: clarification

**Assembler Directives**
Assembler directives are instructions for the assembler that it uses to process the assembly language program. Some common directives are:
* `ORG`: start address of a program
* `EQU`: define a constant
* `END`: end program
* `LIST`: specify processor type
* `#include`: include additional files

**Flow Control**
Flow control is done by using subroutines and branching instructions.
* **Branching Instructions**:
	+ Conditional or unconditional
	+ Examples: `JMP`, `JC`, `JNZ` 
* **Subroutine**:
	+ A small program repeatedly used in a program
	+ May be a delay or other special function code

**Writing Delays**
Writing delays involves:
* Loading a register by a data value that can give a specified time delay
* Decrementing the data
* Looping back

**Table Look Up** 
Table look up involves accessing a list of data stored in a separate memory location. This is used when displaying or manipulating a list of data values.

### C Programming
Most microcontrollers have available C compilers.
C is a modular programming language ( NOT an object oriented language )

Of higher level languages, C is the closest to assembly.
- bit manipulation instructions
- pointers (indirect addressing)

A C program contains
- Comment
- Declaration
- Main directive
- Program statements

Each task can be encapsulated as a function.
Entire program is encapsulated in “main” function.

```
#include <c8051F020.h> /* define SFR 
Unsigned char counter;
void main (void)
{ 
	P1=0;
	Counter=1; 
	P1=counter;
}
```

Variable types:
- int (16-bits in our compiler)
- char (8-bits)
- short (16-bits)
- long (32-bits)
- `sbit` (1-bit)

**Keywords** 
`volatile` - a variable which can be changed by factors other than the program code.
`typedef` - creates a new name for existing data type

`auto` - variable exists only within block within which it is defined.
`extern` - declares data defined elsewhere
`register` - variable to be stored in a CPU register, thus address operator (&) has no effect.
`static` - declares a variable that exists throughout program execution.

**Comparison of Assembly and C**

Example program for adding two 16-bit numbers
```assembly
$INCLUDE (c8051f020.inc)

XL equ 0x78
XH equ 0x79
YL equ 0x7A
YH equ 0x7B

ljmp Main

Main:
; Disable watchdog timer
mov 0xFF, #0DEh
mov 0xFF, #0ADh
	mov a, XL
	add a, YL
	mov XL, a
mov a, XH
	addc a, YH
	mov XH, a
	nop
end
```

A breakdown of what each part does:
* `$INCLUDE (c8051f020.inc)`: This line includes a header file named `c8051f020.inc` that contains definitions and macros specific to the 8051 microcontroller.
* `XL equ 0x78` and similar lines: These lines define memory locations for the 8051's X and Y registers. `XL` and `XH` are the lower and upper bytes of the X register, and `YL` and `YH` are the lower and upper bytes of the Y register.
* `ljmp Main`: This line jumps to the `Main` label, which is the entry point of the program.
* `Main:`: This is the label that the program starts at. It's where the program's main code begins.
* `mov 0xFF, #0DEh` and `mov 0xFF, #0ADh`: These lines disable the watchdog timer by writing the values `0xDE` and `0xAD` to the watchdog timer control register (`0xFF` is the address of this register).
* `mov a, XL` and similar lines: These lines move the values of the X and Y registers into the accumulator (`a`).
* `add a, YL` and similar lines: These lines add the values of the Y registers to the accumulator.
* `mov XL, a` and similar lines: These lines move the result of the addition back into the X and Y registers.
* `nop`: This line is a no-operation instruction, which does nothing.

```c
#include <c8051f020.h>

void main (void) {
  int x, y, z;
  z = x + y;
}
```

##### Pre-processor Directives in C
Are instructions to the compiler that are not part of the program code but are used to control the compilation process. These directives are used to include header files, define macros, and control the flow of the compilation process.

| Directive  | Description                                         | Example                                                 |
| ---------- | --------------------------------------------------- | ------------------------------------------------------- |
| `#include` | Includes a header file.                             | `#include <stdio.h>`                                    |
| `#define`  | Defines a macro.                                    | `#define PI 3.14159`                                    |
| `#undef`   | Undefines a macro.                                  | `#undef PI`                                             |
| `#ifdef`   | Checks if a macro is defined.                       | `#ifdef DEBUG`                                          |
| `#ifndef`  | Checks if a macro is not defined.                   | `#ifndef DEBUG`                                         |
| `#if`      | Checks a condition.                                 | `#if 1 == 1`                                            |
| `#else`    | Specifies an alternative if the condition is false. | `#if 1 == 1 #else #error "Condition is false"`          |
| `#elif`    | Specifies an alternative if the condition is true.  | `#if 1 == 1 #elif 2 == 2`                               |
| `#endif`   | Ends a conditional directive.                       | `#if 1 == 1 #endif`                                     |
| `#line`    | Specifies the line number.                          | `#line 10`                                              |
| `#error`   | Generates an error message.                         | `#error "Error message"`                                |
| `#pragma`  | Provides additional information to the compiler.    | `#pragma GCC diagnostic ignored "-Wmissing-prototypes"` |
|            |                                                     |                                                         |
Example Use Cases
```c
#include <stdio.h>

#define DEBUG 1

#ifdef DEBUG
    printf("Debug mode is enabled\n");
#endif

#if DEBUG == 1
    printf("Debug mode is enabled\n");
#else
    printf("Debug mode is disabled\n");
#endif

int main() {
    #ifdef DEBUG
        printf("Debug message\n");
    #endif

    #pragma GCC diagnostic ignored "-Wmissing-prototypes"

    return 0;
}
```

In this example, the `#ifdef` directive is used to check if the `DEBUG` macro is defined. If it is, the `printf` statement is executed. The `#if` directive is used to check a condition. The `#pragma` directive is used to provide additional information to the compiler.

# CH 3: Hardware level programming of embedded systems
PT 2

Involves writing software that directly interacts with the underlying hardware components without the abstraction provided by operating systems.
Often done in languages like Assembly or utilizing low-level languages like C to access specific registers and control hardware peripherals.  

**Key aspects of hardware-level programming for embedded systems:** 
1. **Understanding the Hardware**
	* Have a deep understanding of the embedded system's hardware architecture before writing software.
	* Know the microcontroller or microprocessor, memory organization, I/O ports, and other peripherals.
2. **Choosing the Right Language**
	* Assembly language is direct but complex and platform-specific
	* C - allows for more abstraction while still providing control over hardware components.
3. **Accessing Memory and Registers**
	* Embedded systems have specific memory addresses and registers for hardware components.
	* Hardware-level programming involves directly manipulating these addresses and registers.
4. **Peripheral Programming**  ^6db2cf
	* Embedded systems often include peripherals such as timers, GPIO (General Purpose Input/Output) pins, UART (Universal Asynchronous Receiver-Transmitter), SPI (Serial Peripheral Interface), I2C (Inter-Integrated Circuit), ADC (Analog-to-Digital Converter), and more.
	* Hardware-level programming involves configuring and controlling these peripherals.
	* **Example (Using C)**:
```C
// Configuring GPIO pins as output
#define GPIO_PORTA_DIR_REG *((volatile uint32_t*) 0x40004000)
GPIO_PORTA_DIR_REG |= 0x01;  // Set pin 0 as output
// Writing to GPIO pins
#define GPIO_PORTA_DATA_REG *((volatile uint32_t*) 0x400043FC)
GPIO_PORTA_DATA_REG |= 0x01;  // Set pin 0 high
```

- Explanation of Above code
	Configuring GPIO Pins as Output
	```c
	#define GPIO_PORTA_DIR_REG *((volatile uint32_t*) 0x40004000)
	```
	*   `GPIO_PORTA_DIR_REG` is a macro that defines the symbolic name for the **Direction Register** of GPIO Port A.
	*   The **Direction Register** is used to configure whether each pin in a port acts as an input or an output.
	- The address 0x40004000 is not RAM — it is the physical GPIO direction register of Port A.
	
	Setting a Pin as Output
	```c
	GPIO_PORTA_DIR_REG |= 0x01;  // Set pin 0 as output
	```
	*   `|= 0x01` performs a bitwise OR operation between the current value of `GPIO_PORTA_DIR_REG` and `0x01`, setting the least significant bit (Bit 0) to '1', which configures the corresponding GPIO pin (Pin 0 of Port A) as an output.
	
	Writing to GPIO Pins
	```c
	#define GPIO_PORTA_DATA_REG *((volatile uint32_t*) 0x400043FC)
	```
	*   `GPIO_PORTA_DATA_REG` is a macro that defines the symbolic name for the **Data Register** of GPIO Port A.
	*   The **Data Register** is used to set the high/low state of the pins (if they are configured as outputs) or to read their state (if they are configured as inputs).
	Setting a Pin High
	```c
	GPIO_PORTA_DATA_REG |= 0x01;  // Set pin 0 high
	```
	*   `|= 0x01` performs a bitwise OR operation between the current value of `GPIO_PORTA_DATA_REG` and `0x01`, setting the least significant bit (Bit 0) to '1', which causes the physical Pin 0 of Port A to output a high voltage level.

5. **Interrupt Handling**  ^6e7fc8
* Hardware-level programming includes managing interrupts directly.
* This involves configuring interrupt registers, writing interrupt service routines (ISRs), and handling interrupt requests from peripherals or external events.
* **Example (Using C)**:
```c
// Configuring and enabling interrupts for a timer
#define TIMER0_CTL_REG *((volatile uint32_t*) 0x4003000C)
#define NVIC_EN0_REG *((volatile uint32_t*) 0xE000E100)
TIMER0_CTL_REG |= 0x01;    // Enable timer
NVIC_EN0_REG |= 1 << 19;    // Enable interrupt for Timer 0
```
- **Line-by-Line Explanation** 
	1. `#define TIMER0_CTL_REG *((volatile uint32_t*) 0x4003000C)`
		* This is a preprocessor directive that replaces `TIMER0_CTL_REG` with `*((volatile uint32_t*) 0x4003000C)`
	2. `#define NVIC_EN0_REG *((volatile uint32_t*) 0xE000E100)`
		* This line defines a macro for the NVIC Enable Register 0
	3. `TIMER0_CTL_REG |= 0x01;` 
		* Sets bit 0 of the Timer 0 Control Register to 1, starting the timer
	4. `NVIC_EN0_REG |= 1 << 19;`
		* Enables the interrupt corresponding to Timer 0's interrupt request
	- **In Summary:** The code sets up a periodic timer interrupt by enabling Timer 0 and allowing the microcontroller to respond to its interrupt requests.
	- "19" in this case is hardware dependent

6. **Memory Management** 
	* In embedded systems, memory management is crucial.
	* Hardware-level programming involves managing both RAM and ROM effectively, considering factors like data storage, program execution, and optimization.

7. **Real-time Constraints** 
	* Many embedded systems have real-time constraints, requiring careful consideration of timing and responsiveness.
	* Hardware-level programming allows for precise control over timing-critical operations.

8. **Testing and Debugging** 
	* Debugging at the hardware level can be challenging.
	* Techniques such as using debugging tools, logic analyzers, and in-circuit emulators can aid in identifying and fixing issues.

9. **Energy Efficiency** 
	* Optimizing code for energy efficiency is often a consideration in embedded systems.
	* Hardware-level programming allows for fine-tuning to minimize power consumption.

10. **Documentation and Standards**
	* Maintain clear documentation of memory addresses, register configurations, and other hardware-related information.
	* Adhere to hardware-specific standards and guidelines to ensure portability and maintainability.
	* **Challenges:**
		- Lack of portability due to hardware-specific code.
		- Steeper learning curve, especially when dealing with Assembly language.
	* **Advantages:**
		- Fine-grained control over hardware resources.
		- Efficient code execution.


### Specific Devices
"Harvard Architecture" - separate instruction and data memory

**Microcontroller Comparison** 
* **AVR ATMEGA328P**: 8-bit RISC, Harvard Architecture, widely used in Arduino Uno and hobbyist platforms. good for timing-sensitive applications
* **ARM CORTEX M4 and STM32F4**: 32-bit RISC, Harvard Architecture with pipelining and Thumb-2 instruction set, used in real-time control systems and industrial applications
* **8051 MICROCONTROLLER**: CISC, single accumulator-based CPU - limited registers, popular in education and legacy systems
* **MSP430 AND PIC16F877A**: MSP430: 16-bit RISC, ultra-low power design, modified Harvard, PIC16F877A: 8-bit microcontroller with Harvard Architecture, Both are popular for low-cost and energy-sensitive applications
* **ESP32**: Tensilica Xtensa LX6 Dual-Core, custom RISC, integrated Wi-Fi and Bluetooth, popular in IoT applications
* **RASPBERRY PI 4**: 64-bit ARM Cortex-A72, high-performance, runs full Linux OS, Used in multimedia, AI applications, edge computing.
* **NPX LPC1768 AND ARDUINO DUE**: ARM Cortex-M3, 32-bit RISC architecture, suitable for industrial applications and accessibility, excellent interrupt handling and low power


**CISC (Complex Instruction Set Computing)** 
* Large number of instructions, some very specific and powerful
* Designed to complete tasks with fewer lines of assembly code
* Slower clock speeds and more complex decoding logic
* Examples: x86 processors, 8051 microcontroller

**RISC (Reduced Instruction Set Computing)** 
* Small set of simple instructions, each executes in one clock cycle
* Optimized for pipelining and high-speed operation
* Requires more instructions for complex tasks, but simpler hardware
* Examples: ARM Cortex cores, AVR, MIPS, RISC-V


### PROGRAMMING IN C
C allows you to write code that directly interacts with the hardware, making it well-suited for resource-constrained devices.

**Key Considerations for Programming in C for Embedded Systems** 
* **Toolchain Setup**: Set up a C compiler and development environment tailored for your embedded system, including tools such as compilers, linkers, and debuggers.
* **Memory Management**: Be mindful of stack and heap usage, and allocate memory efficiently using *static memory* allocation where possible. e.g. Static mem. allocation `int buffer[100];` 
* **Data Types**: Understand the data types provided by C and their representation in memory, and choose appropriate data types to conserve memory and ensure efficient data handling.
* **Bit Manipulation**: C allows manipulation of individual bits, a common requirement in embedded systems for configuring registers and controlling hardware.
* **I/O Operations**: Directly access and manipulate I/O ports and peripherals using C to control external devices like sensors, LEDs, or communication interfaces. e.g. [[#^6db2cf|peripheral programming example]]  
* **Interrupt Handling**: Write Interrupt Service Routines (ISRs) to handle interrupts from peripherals or external events. e.g. [[#^6e7fc8|Interrupt Handling]] 
* **Debugging Techniques**: Use techniques like printf debugging, LEDs, or serial communication for debugging, as embedded systems may not have sophisticated debugging tools.
* **Testing on Target Hardware**: Frequently test your code on the target hardware to ensure compatibility and identify issues early in the development process.

### DEVELOPMENT PLATFORMS FOR EMBEDDED SOFTWARE
* Provide tools, libraries, and frameworks for firmware and application development
* Typically include IDEs, compilers, debuggers, and embedded-specific libraries

**Popular Development Platforms** 
* **Arduino** 
	+ Open-source hardware and software platform for prototyping and embedded systems
	+ Beginner-friendly and supports extensive libraries for sensors, actuators, and more
* **Raspberry Pi** 
	+ Single-board computers for embedded projects, IoT applications, and education
	+ Features: GPIO pins, Raspberry Pi OS (Linux based), and diverse applications
* **Platform IO** 
	+ Open-source ecosystem for IoT development compatible with various platforms, including Arduino, ESP8266, ESP32, Raspberry Pi, and many others. 
	+ Cross-platform IDE, library manager, and built-in support for debugging and testing
* **STM32CubeIDE** 
	+ Integrated development environment for STM32 microcontrollers
	+ Eclipse-based IDE with STM32CubeMX and hardware debugging support
* **Keil µVision** 
	+ IDE for developing firmware for microcontrollers, particularly ARM Cortex-M architectures
	+ Includes ARM compiler, simulation, and debugging tools, as well as RTOS support
* **Espressif IoT Development Framework (ESP-IDF)** 
	+ Official development framework for ESP32 and ESP8266 microcontrollers
	+ Built on `FreeRTOS` with command-line tools and rich peripheral support (GPIO, UART, SPI...)
* **NI LabVIEW** 
	+ Graphical programming environment for test, measurement, and control applications
	+ Supports real-time and FPGA modules, as well as hardware integration with NI platforms

### INTRODUCTION TO ARDUINO
**Arduino Overview**
* Arduino is an open-source platform for creating interactive electronic projects.
* It consists of physical microcontroller boards and a software development environment.
* Are widely used in various fields, including electronics, robotics, IoT (Internet of Things), automation, and education.

**Overview of Arduino Key Aspects** 
1. **Hardware**
	* **Microcontroller**: The heart of the Arduino board, responsible for executing code and controlling attached peripherals. (e.g., ATmega328 for Arduino Uno)
	* **Input/Output (I/O) Pins**: Allow the Arduino to interface with external devices such as sensors, LEDs, motors, and displays. usually both digital and analog pins.
	* **Power Supply**: Can be powered via USB, battery, or an external power supply.
	* **USB Interface**: Enables communication to a computer for programming and serial communication.

**2. Software Development Environment**
The Arduino IDE (Integrated Development Environment), provides a user-friendly platform for writing, compiling, and uploading code to Arduino boards. Key features include:
* **Code Editor** 
* **Compiler**: translates sketches into machine code compatible with the target microcontroller.
* **Library Support**: libraries providing pre-written code for interfacing with various sensors, actuators, communication modules, and other peripherals.
* **Serial Monitor**: A tool for debugging and serial communication between the Arduino board and a connected computer.

**3. Programming with Arduino** 
- Sketches are small programs written in C/C++ syntax.
- Each sketch typically consists of two main functions:
	* **setup()**: Called once when the Arduino board is powered on or reset. It is used to initialize variables, configure pins, and perform setup tasks.
	* **loop()**: Runs continuously after the setup function completes. It contains the main logic of the program and is where most of the action happens.
```c
// sketch that blinks an LED connected to pin 13:
void setup() {
  pinMode(13, OUTPUT); // Set pin 13 as output
}
void loop() {
  digitalWrite(13, HIGH);   // Turn on the LED
  delay(1000);              // Wait for 1 second
  digitalWrite(13, LOW);    // Turn off the LED
  delay(1000);              // Wait for 1 second
}
``` 

**4. Community and Ecosystem**
Arduino has a large and active community of users, makers, educators, and developers.
* Arduino-compatible boards and components are widely available from various vendors, providing flexibility and compatibility with different hardware configurations.

**5. Applications of Arduino**
Arduino boards are used in a wide range of applications, including:
* *DIY Electronics Projects*: robots, home automation systems, weather stations, and interactive art.
* *Educational Purposes*: Teaching electronics, programming, and robotics in schools, colleges.
* *Prototyping and Product Development*: Rapid prototyping of electronic prototypes and proof-of-concept projects for commercial products.


# CH 4: Introduction to Microcomputer Interfaces
**Microcomputer interfaces** 
Essential components for communication between microcontroller/microprocessor and external devices
* Allow microcontroller to interact with sensors, actuators, and other components
* Facilitate data transfer, control signals, and communication across various protocols.

### Digital IO
**Digital Input**:
* allows microcomputers to interact with external devices and peripherals.
* Digital inputs enable microcomputers to receive digital signals from various sources, such as sensors, switches, and communication modules.
* transmission and reception of *binary signals*.

**Operation** 
* Digital input pins are set as inputs, allowing the microcomputer to detect whether the signal is high or low.
* Digital inputs can be polled regularly or used to trigger interrupts upon state changes.

**Applications** 
* *User Interaction*: Reading input from buttons, switches, or keypads to execute specific commands or trigger actions.
* *Event Detection*: Detecting events such as motion, position, or temperature changes.
* *Control Systems*: Collecting signals from sensors to maintain control loops, automate processes, or adjust system parameters.

**Digital Output**:
- allow microcomputers to send digital signals to control external devices, like LEDs, motors, or relays. 
- The output state can be high or low, depending on the desired action.

**Operation** 
* Digital output pins are set as outputs, allowing the microcomputer to send signals to other components.
* The microcomputer can control the voltage state on these pins to drive external devices or communicate with other systems.
* Digital outputs can also generate pulse signals for use in applications like *Pulse Width Modulation* (PWM).

**Applications** 
* *Actuator Control*: Controlling devices like LEDs, motors, relays, and solenoids to create specific effects or actions.
* *Communication*: Sending signals to other devices or microcontrollers for coordination and communication.
* *PWM Generation*: Generating PWM signals for motor control, LED dimming, or audio generation.

Key Considerations for Digital I/O
* Configuration: setting pins as input or output and configuring internal pull-up/pull-down resistors to stabilize the signal.
* Voltage Levels: Digital logic levels in microcomputers vary based on the design and technology used. essential to ensure compatibility with external devices.
* Interrupts: Interrupt-driven digital I/O allows for efficient event handling without constant polling.

Key Considerations
* **Debouncing**: When dealing with mechanical switches or buttons, debouncing is necessary to eliminate false triggers caused by mechanical noise or bouncing.
* **Isolation and Protection**: In industrial or high-voltage environments, isolating digital I/O and adding protection circuits, such as diodes or resistors, is critical to prevent damage.

### Serial I/O
refers to data transmission methods where information is sent one bit at a time, sequentially, over a communication channel.
it requires fewer physical connections, allows for longer communication distances, and supports a wide range of protocols and standards. 

**Key Characteristics**: 
1. *Sequential Transmission*: Data is transmitted one bit at a time in a sequential manner, with a defined order and timing. 
	- This is in contrast to parallel communication, where multiple bits are transmitted simultaneously.
2. *Fewer Wires*: reducing complexity and cost, and allowing for simpler hardware designs.
3. *Longer Distances*: compared to parallel communication, which can be susceptible to signal degradation over longer cables.
4. *Protocols*: Various serial communication protocols exist, each with specific characteristics, such as speed, synchronization, error handling, and data framing.

**Common Serial Communication Protocols:** 
Terms:
*Asynchronous* - data is sent without a shared clock signal.
*Synchronous* - relies on a clock signal to synchronize data transmission.

1. **UART (Universal Asynchronous Receiver-Transmitter)** 
	* Asynchronous data transmission with start and stop bits.
	* Widely used for simple communication.

2. **SPI (Serial Peripheral Interface)** 
	* Synchronous serial protocol with master-slave configuration,
	* High-speed full-duplex communication with peripherals like displays, memory chips...

3. **I2C (Inter-Integrated Circuit)** 
	* Synchronous serial protocol with multi-master and multi-slave support
	* allows multiple devices to share the same bus, making it suitable for communication in complex systems 
	* Communication with sensors, EEPROM, and integrated circuits

4. **CAN (Controller Area Network)** 
	* designed for automotive and industrial applications. It supports multi-node communication and has built-in error detection mechanisms.
	* used in environments where reliability and noise immunity are critical, such as automotive networks and industrial automation.

5. **USB (Universal Serial Bus)** 
	* a widely used standard for connecting peripherals to computers and microcomputers.
	* supports different transfer modes, like: control, bulk, interrupt, and isochronous transfers.

**Applications of Serial I/O in Microcomputers** 
* **Data Communication**: Microcomputers can communicate with other devices using serial I/O, enabling data transfer and interaction within embedded systems.
* **Peripheral Connectivity**: Serial communication connects peripherals to microcomputers, allowing flexible system design and easy integration with external components.
* **Debugging and Programming**: UART is used for debugging and programming microcomputers, providing a simple serial console for outputting debug information or loading firmware.
* **Communication Networks**: Serial protocols like CAN and I2C create communication networks in automotive, industrial, and IoT applications, enabling reliable data exchange among multiple nodes.

### Timers
* They provide precise timing and counting functionalities.
* They enable microcomputers to manage time-dependent tasks, create delays, generate periodic signals, measure time intervals, and implement various control mechanisms.

**Types of Timers** 
1. **Interval Timers (General Purpose Timers)** 
	* Count clock cycles or other time units to create delays or measure elapsed time.
	* These timers can be configured for specific intervals, allowing the microcomputer to execute code at regular intervals or after a certain delay.
2. **Watchdog Timers** 
	* are designed to detect and recover from system malfunctions or software faults.
	* They count down from a set value and reset the microcomputer if not refreshed periodically, preventing system hangs or crashes.
	* Used in safety-critical systems and embedded applications where reliability is crucial.
3. **Real-Time Clock (RTC)** 
	* RTC modules provide accurate timekeeping, maintaining date and time information, and supporting time-based triggers or alarms.
	* Often used to keep time even when the main system is off, typically with a backup battery.

**Applications of Timers in Microcomputers**
1. *Delay Generation* 
	* Timers can create precise delays or time intervals.
	* Useful for debouncing switches and controlling timing sequences.
2. *Periodic Interrupts* 
	* Timers can generate periodic interrupts.
	* Useful for tasks like sampling sensors and updating displays.
3. *PWM Generation* 
	* Timers can generate Pulse Width Modulation (PWM) signals.
	* PWM is used for motor control and LED dimming.
4. *Watchdog Functionality* - Watchdog timers help ensure system stability.
5. *Time-Based Events* 
	* Timers can trigger time-based events, such as executing specific tasks at regular intervals.

**Configuration and Control of Timers** 
* **Initialization**: Timers must be initialized with specific settings, such as prescalers, count values, and interrupt configurations.
* **Prescalers**: Prescalers divide the timer's clock source to achieve lower frequencies, allowing for longer time intervals and greater flexibility in timing.
* **Interrupts**: Timers can be configured to generate interrupts when they reach a certain count or overflow.
* **Resetting and Clearing**: Timers can be reset or cleared to restart the timing sequence.
* Timers are a versatile and critical component of microcomputers, enabling precise timing control and management of time-based tasks. generating PWM signals and creating delays...

### Analog-to-digital conversion
* a process by which analog signals (continuous signals with infinite resolution) are converted into digital signals (discrete, quantized signals).
* Microcomputers, especially in embedded systems, often need to interact with real-world signals, such as temperature, pressure, light, or sound, which are inherently analog.
* ADC allows these signals to be processed, stored, and transmitted by digital systems.

*Analog-to-Digital Conversion* 
Analog-to-Digital Conversion involves sampling an analog signal at regular intervals and quantizing it into a finite number of discrete levels.

The process generally involves two key operations:
1. **Sampling**: Capturing the value of an analog signal at specific time intervals.
	* The rate at which samples are taken is called the **sampling rate** or **sampling frequency**.
2. **Quantization**: Mapping the continuous range of analog values into discrete levels, which are then represented as digital data.
	* The precision of quantization is determined by the number of bits used to represent the digital value.

**Common Parameters in ADC**
1. **Resolution**: The number of bits used to represent the digital output, with common resolutions ranging from 8-bit to 16-bit or more. Higher resolution allows for finer precision.
2. **Sampling Rate**: The rate at which the analog signal is sampled, typically measured in samples per second (SPS) or hertz (Hz).
3. **Input Range**: The range of analog voltages that the ADC can convert. can be fixed or adjustable.
4. **Linearity**: The degree to which the ADC's output accurately reflects the analog input.
5. **Noise**: Unwanted variations or fluctuations in the ADC output that do not correspond to changes in the analog input.

**Applications of ADC in Microcomputers**
1. **Sensor Data Acquisition**: Read data from analog sensors.
2. **Data Acquisition Systems**: Collect and process real-world data.
3. **Audio Processing**: Convert analog audio signals into digital format.
4. **Control Systems**: Read analog inputs for feedback control, enabling precise adjustments in motor control or robotics.
5. **Signal Analysis**: Analyze analog signals using digital tools, such as oscilloscopes and spectrum analyzers.

**Key Considerations for ADC in Microcomputers**
* **Choosing the Right ADC**: Select an ADC with suitable resolution, sampling rate, and input range.
* **Configuration and Calibration**: ADCs may require configuration and calibration to ensure accurate readings. This includes setting reference voltages, gain, and input range.
* **Signal Conditioning**: Condition analog signals to reduce noise.
* **Handling Noise and Interference**: Implement proper grounding, shielding, and filtering techniques.
* **Integrating with Digital Systems**: Process, analyze, or transmit digital data efficiently.

By converting analog signals into digital form, microcomputers can process, store, and communicate real-world data effectively.

### Pulse Width Modulation (PWM)
Is a technique used in microcomputers and embedded systems to generate variable analog-like signals using digital means. 
- widely employed to control the power delivered to various devices, such as motors, LEDs, and other actuators. 

It involves creating a digital signal with a specific frequency and varying the duty cycle (the proportion of the signal that is high versus low) to achieve the desired output.

**PWM Basics** 
* **Signal Characteristics**: PWM generates a digital signal that oscillates between high and low states.
	* The frequency of oscillation determines the rate at which the signal changes, while the duty cycle indicates the proportion of the signal that is high during each cycle.
* **Duty Cycle**: The duty cycle is expressed as a percentage and represents the fraction of time the signal is high during each cycle.
	* A 50% duty cycle means the signal is high for half of the cycle and low for the other half.
	* **Higher duty cycle** results in more power or intensity, while a lower duty cycle reduces it.
* **Frequency**: The frequency of the PWM signal is the number of cycles per second, typically measured in hertz (Hz).
	* This frequency affects the smoothness and responsiveness of the PWM output.

**Applications of PWM in Microcomputers**
1. **Motor Control** - to control DC motor speed by adjusting duty cycle without complex hardware.
	* also used in servo motors for specific positions based on PWM pulse width.
2. **LED Dimming** - Control LED brightness by varying duty cycle
3. **Audio Generation** - Generate audio signals by creating *varying pulse patterns*,
4. **Power Regulation** - Regulate voltage and current in power supply circuits by rapidly switching electronic components.
5. **Heating Control**: allows for temperature control by varying the average power delivered.

**Pulse Width Modulation (PWM)**
* PWM can be implemented using either hardware support or software control.
	+ Hardware support is more efficient and precise, but software control is more resource-intensive.
	+ Configuring PWM involves setting the frequency, duty cycle, and other parameters to achieve the desired output.
	+ Signal conditioning may be necessary to amplify or isolate the PWM signal.

**Key Considerations for PWM in Microcomputers**
* **Choosing the Right Frequency** - A higher frequency provides smoother output but may increase power dissipation, while a lower frequency can cause visible flickering.
* **Maintaining Stability** - Hardware-based PWM is generally more stable than software-based.
* **Noise and Interference** - Proper filtering and shielding techniques can help minimize issues.





# AI SLOP

Here is an in-depth guide to microcontroller addressing modes. Since the handwritten notes only listed the names of a few modes, this comprehensive breakdown includes missing standard modes, detailed operational definitions, step-by-step effective address ($EA$) calculations, and practical assembly examples (using standard 8051/generic assembly notation).


## Understanding Key Concepts

Before diving into the calculations, it is critical to understand two terms:

* **Operand:** The actual data that needs to be processed.
* **Effective Address ($EA$):** The actual physical address in memory (RAM, ROM, or Registers) where the operand is located.
 
1. **Immediate Addressing Mode**
	The operand is a constant value explicitly specified directly within the instruction itself. No memory or register lookup is required to find the data.
	
	* **Calculation:** 
	$$\text{Operand} = \text{Value specified in instruction}$$
	
	
	*(There is no Effective Address to calculate because the data is embedded in the instruction code).*
	* **Example:**
	```assembly
	MOV A, #25H    ; Loads the hexadecimal value 25 into the Accumulator (A)
	ADD A, #10H    ; Adds the value 16 (10H) directly to the Accumulator
	```
	
	* **Key Identifier:** The `#` symbol typically denotes an immediate value in assembly.

2. **Register Direct Addressing Mode**
	The operand is stored inside one of the internal CPU registers ($R_0$ through $R_7$, or the Accumulator). The instruction specifies the register name directly.
	
	* **Calculation:** 
	$$\text{Operand Source} = \text{Specified Register}$$
	
	
	* **Example:**
	```assembly
	MOV A, R1      ; Copies the contents of register R1 into the Accumulator
	ADD A, R2      ; Adds the contents of register R2 to the Accumulator
	```

3. **Direct Addressing Mode (Absolute Addressing)**
	The instruction explicitly contains the exact 8-bit or 16-bit memory address of the operand. The CPU directly reads or writes to that specific RAM or Special Function Register (SFR) slot.
	
	* **Calculation:** 
	$$EA = \text{Address specified in the instruction}$$
	* **Example:**
	```assembly
	MOV A, 30H     ; Copies data from RAM address 30H into the Accumulator
	MOV 40H, A     ; Copies data from the Accumulator into RAM address 40H
	```
	* **Calculation Walkthrough:** If RAM location `30H` contains the value `55H`, executing `MOV A, 30H` sets $EA = 30H$. The CPU fetches the value at $30H$, resulting in $A = 55H$.

4. **Register Indirect Addressing Mode**
	The instruction specifies a pointer register ($R_0$ or $R_1$ in 8051) that holds the actual memory address where the operand resides.
	
	* **Calculation:** 
	$$EA = [R_n]$$
	*(The Effective Address is the content of register $R_n$).*
	* **Example:**
	```assembly
	MOV A, @R0     ; Moves data from the RAM address pointed to by R0 into A
	```
	
	* **Calculation Walkthrough:**
	1. Assume Register $R_0 = 40H$.
	2. Assume RAM location $40H = 99H$.
	3. The CPU checks $R_0$, finds $40H$. Therefore, $EA = 40H$.
	4. The CPU reads $40H$, and copies the value $99H$ into the Accumulator ($A = 99H$).
	
	* **Key Identifier:** The `@` symbol denotes indirection (pointing).

4. **Base Relative Addressing Mode (Indexed Addressing)**
	This mode is primarily used to access look-up tables stored in program memory (ROM). It calculates the source address dynamically by adding a base pointer register to an offset value stored in the Accumulator.
	* **Calculation:** 
	$$EA = \text{Base Register} + \text{Offset Register (Accumulator)}$$
	In architectures like 8051, the base register can be the **Program Counter ($PC$)** or the **Data Pointer ($DPTR$)**.
	* **Example:**
	```assembly
	MOVC A, @A+DPTR  ; Moves a byte from ROM address (A + DPTR) into A
	MOVC A, @A+PC    ; Moves a byte from ROM address (A + PC) into A
	```
	
	* **Calculation Walkthrough:**
	1. Assume Data Pointer $DPTR = 1000H$ (Base address of a lookup table).
	2. Assume Accumulator $A = 05H$ (The index/offset you want to access).
	3. Calculate $EA$ 
	$$EA = 1000H + 05H = 1005H$$
	4. The CPU fetches the byte stored at ROM location $1005H$ and loads it into $A$.

6. **Base Relative Indexing Mode**
	Commonly found in more complex microcontrollers or x86/ARM architectures, this mode combines a base register, an index register, and an optional constant displacement factor to find the final address. It is heavily utilized when parsing multi-dimensional arrays or structures in memory.
	* **Calculation:** 
	$$EA = \text{Base Register} + \text{Index Register} + \text{Displacement}$$
	* **Generic/ARM-style Example:**
	```assembly
	LDR R0, [R1, R2]     ; EA = R1 + R2 (Base + Index)
	LDR R0, [R1, R2, #4] ; EA = R1 + R2 + 4 (Base + Index + Displacement)
	```
	
	* **Calculation Walkthrough:**
	1. Assume Base Register $R_1 = 2000H$.
	2. Assume Index Register $R_2 = 0010H$.
	3. Assume Displacement constant $= 0004H$.
	4. Calculate $EA$:
	$$EA = 2000H + 0010H + 0004H = 2014H$$
	5. The processor reads the data payload physically located at address $2014H$.

7. **Implicit / Implied Addressing Mode (Missing from note text)a**

The instruction itself explicitly dictates the operand because the operation can only happen to one specific component of the CPU. No registers or addresses need to be specified because there is no alternative destination.

* **Calculation:** 
$$\text{Operand Location} = \text{Hardcoded by opcode logic}$$


* **Example:**
```assembly
CLR A    ; Clears the Accumulator (Sets A = 0). Accumulator is implied.
CPL A    ; Complements (inverts) the bits of the Accumulator.
NOP      ; No Operation. Performs no memory cycles or changes.
```

## Quick Reference Summary Table

| Addressing Mode       | How to find $EA$                                   | Best Used For...                         | Efficiency                       |
| --------------------- | -------------------------------------------------- | ---------------------------------------- | -------------------------------- |
| **Immediate**         | No address; data is in instruction                 | Loading constant variables / flags       | Fast (No memory access)          |
| **Register Direct**   | Internal Register internal address                 | High-speed processing of temporary data  | Fast (No memory access)          |
| **Direct**            | Stored inside instruction bits                     | Accessing global variables or I/O ports  | Medium (1 Memory cycle)          |
| **Register Indirect** | Stored inside a pointer register                   | Accessing arrays or data loops in RAM    | Medium (1 Memory cycle)          |
| **Base Relative**     | $\text{Base} + \text{Offset}$                      | Look-up tables / Flash ROM reading       | Slower (Requires addition step)  |
| **Relative Indexing** | $\text{Base} + \text{Index} + \text{Displacement}$ | Complex structures or matrix offsets     | Slower (Requires multi-addition) |
| **Implicit**          | Hardcoded by architecture design                   | Control operations (Clearing, inverting) | Fast (No data mapping)           |



Here are the three questions extracted from the quiz, along with worked solutions (computed independently of the handwritten answers):

**Question 1:**
Assume SP = 0500h and the following execute: PUSH AX, PUSH BX, and POP CX. If each PUSH decreases SP by 2 and POP increases SP by 2, what is the final SP?

*Solution:*
- Initial SP = 0500h
- PUSH AX → SP = 0500h − 2 = 04FEh
- PUSH BX → SP = 04FEh − 2 = 04FCh
- POP CX → SP = 04FCh + 2 = 04FEh

**Final SP = 04FEh**

**Question 2:**
Data is stored at segment 0200h, specific memory location offset 0100h. Compute the starting (physical) address of the memory location.

*Solution:*
Physical Address = (Segment × 10h) + Offset
PA = (0200h × 10h) + 0100h
PA = 02000h + 0100h

**PA = 02100h**

**Question 3:**
The next data to be executed is located at 5000:0200 (segment:offset). Compute the exact memory location (physical address) of the data.

*Solution:*
Physical Address = (Segment × 10h) + Offset
PA = (5000h × 10h) + 0200h
PA = 50000h + 0200h

**PA = 50200h** 






### Understanding Pipelining Efficiency

Pipelining efficiency is a measure of how effectively the pipeline stages are utilized. Ideally, we want all stages to be busy all the time, processing different parts of different instructions concurrently.

**Formula for Pipelining Efficiency:**

Efficiency (E) = (Speedup) / (Number of pipeline stages)

Where:
*   **Speedup (S)** is the ratio of execution time without pipelining to execution time with pipelining.
*   **Number of pipeline stages (k)** is the number of individual stages in the pipeline (e.g., Fetch, Decode, Execute, Memory, Write-back).

Alternatively, and often more directly calculated:

Efficiency (E) = (n / (k + n - 1))

Where:
*   **n** = Number of instructions to be executed.
*   **k** = Number of stages in the pipeline.
*   **(k + n - 1)** = The total number of clock cycles required to execute 'n' instructions in a 'k'-stage pipeline (assuming no stalls).

**Example Calculation** 

Let's consider a scenario:

**Scenario:**
*   You have a processor with a **5-stage pipeline** (k = 5). The stages are Instruction Fetch (IF), Instruction Decode (ID), Execute (EX), Memory Access (MEM), and Write-Back (WB).
*   You want to execute **10 instructions** (n = 10).
*   Assume **each stage takes 1 clock cycle** to complete its task, and there are no pipeline stalls or hazards.

**Steps:**

1.  **Calculate Time without Pipelining:**
    *   If there were no pipelining, each instruction would take `k` clock cycles to complete.
    *   So, one instruction takes 5 clock cycles.
    *   For 10 instructions, the total time would be `n * k` = `10 * 5 = 50 clock cycles`.

2.  **Calculate Time with Pipelining (Ideal):**
    *   In an ideal k-stage pipeline, the first instruction takes `k` clock cycles to complete.
    *   After the first instruction, one new instruction completes every subsequent clock cycle.
    *   So, the total time for `n` instructions is `k + (n - 1)` clock cycles.
    *   Time with pipelining = `5 + (10 - 1) = 5 + 9 = 14 clock cycles`.

3.  **Calculate Speedup (S):**
    *   Speedup = (Time without pipelining) / (Time with pipelining)
    *   S = `50 / 14` = `3.57` (approximately)

4.  **Calculate Efficiency (E) using the first formula:**
    *   Efficiency (E) = Speedup / k
    *   E = `3.57 / 5` = `0.714` or `71.4%`

5.  **Alternatively, calculate Efficiency (E) using the second formula:**
    *   Efficiency (E) = n / (k + n - 1)
    *   E = `10 / (5 + 10 - 1)`
    *   E = `10 / 14` = `0.714` or `71.4%`

**Interpretation of the Result**

An efficiency of `71.4%` means that, under ideal conditions, the pipeline is utilized `71.4%` of the time for useful work when executing 10 instructions.

**Why isn't it 100%?**
It's not 100% because of the "startup" and "shutdown" phases of the pipeline. The pipeline needs `k` cycles to "fill up" before it reaches its maximum throughput of one instruction per cycle. Similarly, after the last instruction enters the pipeline, it still needs `k-1` more cycles to "drain out." For a small number of instructions, this overhead is more significant.

**What happens with more instructions?**
As the number of instructions (n) increases, the efficiency approaches 1 (or 100%). This is because the initial `k-1` overhead cycles become negligible compared to the total number of cycles.

For example, if n = 1000 instructions:
*   Time without pipelining = `1000 * 5 = 5000` cycles
*   Time with pipelining = `5 + (1000 - 1) = 5 + 999 = 1004` cycles
*   Speedup = `5000 / 1004 = 4.98`
*   Efficiency = `4.98 / 5 = 0.996` or `99.6%`
    (Using the second formula: `1000 / (5 + 1000 - 1) = 1000 / 1004 = 0.996`)

As you can see, for a large number of instructions, the efficiency gets very close to 100%.

**Real-world Considerations** 

It's important to remember that this calculation assumes an **ideal pipeline with no stalls or hazards**. In reality, factors like:
*   **Data Hazards:** When an instruction needs data that has not yet been produced by a preceding instruction.
*   **Control Hazards:** When branches or jumps disrupt the sequential flow, making it unclear which instruction to fetch next.
*   **Structural Hazards:** When multiple instructions need the same hardware resource at the same time (less common in Harvard architecture for memory access, but can occur for other shared units).

These hazards cause pipeline stalls, reducing the actual speedup and, consequently, the efficiency. More complex efficiency calculations would need to factor in the average number of stall cycles per instruction.