
2024-08-13 21:13

Status: 

Tags: #UOM #L2S2-S4 #CA-CO 

# CO&CA - Input and Output Devices and Methods

## Inputs & Outputs (I/O)

**Inputs and Outputs (I/O)** are how a computer interacts with the outside world. This involves both hardware and software components.

### [[Basic IO Hardware]]

*Computer communicate with outside world using Basic I/O hardware*
- **Ports**: Connection points for devices (like USB ports).
- **Buses**: Pathways that transfer data between different parts of the computer.
- **Devices**: External components like keyboards, mice, and printers.
- **Controllers**: Manage the data flow between the computer and its devices.

### I/O Software

Software helps manage these hardware interactions. Key types include:

1. **Interrupt Handlers**: Respond to signals from devices needing attention.
	
	- **How it works**: When a device needs attention (e.g., a keyboard key is pressed), it sends an interrupt signal to the CPU. The CPU stops its current task and jumps to the interrupt handler to address the event.
	
	*example*: When you press a key on the keyboard, a hardware interrupt is generated, which causes the CPU to stop what it’s doing and execute the corresponding interrupt handler to capture the keypress and pass it to the operating system.
	
2. **Device Drivers**: Software that controls specific hardware devices.
	
	- **How it works**: The operating system uses the driver to send commands to the device and receive responses. Drivers act as translators between the hardware and software.
	
	*example*: A printer driver allows the OS to send print jobs to a printer. Without the driver, the OS wouldn't know how to communicate with the printer, making printing impossible.
	
3. **Device-Independent Software**: General software that works with various devices.
	
	- **How it works**: This software handles common tasks like file management, buffering, and error handling, regardless of the specific devices involved.
	
	*example*: A file system is a classic example of device-independent software. It manages files on various storage devices, whether they are hard drives, SSDs, or removable USB drives, without needing to know the specifics of how each device works.
	
4. **User-Space I/O Software**: Software that allows user applications to interact with hardware.
	
	In a computer system, there are two main areas where software can run: **Kernel Space** and **User Space**
	1. **Kernel Space** is where the core of the operating system runs, managing hardware and system resources.
	2. **User Space** is where all the applications and software you interact with on a daily basis run, like your web browser, games, or text editors.
	
	**User-Space I/O Software** refers to the tools and libraries that help these user applications interact with hardware (like your keyboard, mouse, printer, or network) without directly accessing the core parts of the operating system (the kernel).
	
	- **How it works**: User-space I/O software handles I/O requests from applications and communicates with the operating system to execute these requests.
	
	*example*: Video games use graphics libraries (like OpenGL or DirectX) to render images on the screen. These libraries are part of user-space I/O software. They make it easier for the game to display graphics without dealing directly with the hardware details of your graphics card.
	

### Ways to Perform I/O Operations

There are three main methods for handling I/O operations:

#### 1. **Polling**
Polling is a method where the CPU repeatedly checks the status of an I/O device to see if it needs attention. This method is simple but can be inefficient because it requires constant CPU attention.

- **How it works**: The CPU continuously queries the I/O device's status register in a loop, waiting for the device to be ready for an operation.

  *Example*: A program might continuously check if a printer is ready to receive more data, which can waste CPU resources if the printer is not ready for a long time.

- **Disadvantages**: Polling is CPU-intensive and can lead to wasted processing time, as the CPU cannot perform other tasks while polling.

#### 2. **Interrupts**
Interrupts allow I/O devices to signal the CPU when they need attention, freeing the CPU to perform other tasks until the interrupt occurs.

- **How it works**: When a device needs attention, it sends an interrupt signal to the CPU. The CPU interrupts its current tasks, processes the interrupt, and then resumes its previous tasks.

  *Example*: When a network packet arrives at a computer, the network card sends an interrupt to the CPU, triggering it to process the incoming data.

- **Advantages**: Interrupts are more efficient than polling because they allow the CPU to focus on other tasks until an interrupt occurs, reducing idle time.

#### 3. **Direct Memory Access (DMA)**
DMA is a method where a dedicated controller (DMA controller) transfers data directly between memory and an I/O device, bypassing the CPU. This allows for faster data transfer and frees the CPU for other tasks.

- **How it works**: The CPU initiates the DMA transfer by specifying the memory address and the I/O device. The DMA controller then handles the transfer, allowing the CPU to continue with other operations.

  *Example*: Transferring data from a hard drive to memory during a file read operation without involving the CPU in each byte of data transfer.

- **Advantages**: DMA improves system efficiency by offloading data transfer tasks from the CPU, allowing it to perform other operations simultaneously.
## Peripheral Devices

**Peripheral Devices** are external devices that connect to a computer to either input data into the system or output data from it.

![[Pasted image 20240813224237.png | 700]]
#### I/O Subsystem

- **Explanation**: The I/O (Input/Output) Subsystem is the part of the computer that manages communication between the computer's core components (like the CPU and memory) and external devices (like keyboards, monitors, and printers). 

- It ensures that data can flow smoothly between the computer and peripherals, allowing for tasks like printing documents or displaying images on a monitor.

- **Example**: When you type on a keyboard, the I/O subsystem handles the input and ensures that the characters appear on your monitor.
#### Types of Peripheral Devices

1. **Monitor (Visual Output Device)**: Displays information visually. Examples include:
    - **CRT (Cathode Ray Tube)**: Older, bulky monitors.
    - **LCD (Liquid Crystal Display)**: Modern, flat-screen monitors.

2. **KBD (Input Device)**: Devices used to input data into the computer. Examples include:
    - **Light Pen**: A pen-like device used to draw on the screen.
    - **Mouse**: A device to point and click on items on the screen.
    - **Touch Screen**: A screen that responds to touch.
    - **Joystick**: A device used mainly for gaming.
    - **Digitizer**: A device that converts analog information into digital form.

3. **Printer (Hard Copy Device)**: Devices that produce physical copies of documents. Examples include:
    - **Dot Matrix (Impact)**: Uses pins to strike an ink ribbon and create characters.
    - **Thermal**: Uses heat to produce images on special paper.
    - **Ink Jet**: Sprays tiny droplets of ink onto paper.
    - **Laser (Non-Impact)**: Uses a laser to produce high-quality text and images.

4. **Storage Device**: Devices used to store data. Examples include:
    - **Magnetic Tape**: Used for backup and archival storage.
    - **Magnetic Disk**: Hard drives and floppy disks.
    - **Optical Disk**: CDs, DVDs, and Blu-ray discs.

#### ASCII (American Standard Code for Information Interchange)

- **Explanation**: ASCII is a standardized way of encoding text characters so that computers can understand and manipulate text. Each character (like 'A', '1', or '!') is represented by a specific numerical value.

    1. **7-bit ASCII**: Uses 7 bits to represent characters, allowing for 128 different characters (numbers, letters, and control characters).
    2. **Extended ASCII**: Uses 8 bits, allowing for 256 characters, which includes additional symbols, foreign language characters, and graphical symbols.

- **Example**: When you type the letter 'A' on your keyboard, it is represented by the number 65 in ASCII. This allows different computers and systems to exchange text data consistently.

Let's dive deeper into each concept of **I/O Organization** and explain them with simple examples to make the ideas more clear.

## I/O Organization

**I/O Organization** deals with how a computer system manages input and output operations. It ensures smooth communication between the CPU (Central Processing Unit) and external devices, also known as peripherals, like keyboards, monitors, printers, etc. This is crucial for the overall functioning of a computer, as it involves how data is transferred and processed between internal components and external devices.

### Input-Output Interface

#### 1. **Interface**:
   - **Explanation**: An interface is the point where the CPU connects with peripheral devices. It's like a translator that allows the CPU and peripherals to communicate effectively.
   - **Key Functions**:
     - **Signal Conversion**: Peripherals might send data in a format that the CPU doesn't understand directly. The interface converts these signals into a format that the CPU can process.
		- **Example**: A USB keyboard sends electrical signals when keys are pressed. The interface converts these signals into data that the CPU can understand.
     - **Synchronization**: Peripherals often operate at different speeds compared to the CPU. The interface helps synchronize data transfer so that communication happens smoothly.
	    - **Example**: A printer operates much slower than a CPU. The interface ensures that the CPU doesn't overwhelm the printer with data too quickly.
     - **Data Codes and Formats**: Different devices might use different ways to represent data. The interface standardizes this data for the CPU to use.
	    - **Example**: A barcode scanner might read codes differently from how the CPU expects to process them, so the interface translates the code format.
     - **Operating Modes**: Peripherals have different modes of operation (like reading, writing, or waiting). The interface manages these modes to avoid conflicts.
	    - **Example**: A hard drive might be in 'read' mode, and a scanner in 'input' mode, and the interface ensures these modes don't conflict with each other.

#### 2. **Interface Components**:
   - **Explanation**: These are special hardware components that help manage the data transfer between the CPU and peripherals. They handle the complex tasks of coordinating data flow, ensuring data integrity, and managing signals.
   - **Example**: A network interface card (NIC) in a computer is a hardware component that manages data transfer between your computer and a network, handling the complexities of converting digital signals to packets of data for transmission over the internet.

### I/O Bus

An **I/O Bus** is like a highway that allows data to travel between the CPU and peripherals. It consists of three types of lines:

1. **Data Lines**:
   - **Explanation**: These lines carry the actual data being transferred between the CPU and peripherals.
   - **Example**: When you save a file to a USB drive, the data lines carry the data from your computer’s memory to the USB drive.

2. **Address Lines**:
   - **Explanation**: These lines specify where the data is going to or coming from. They tell the CPU which peripheral device is involved in the data transfer.
   - **Example**: If the CPU needs to send data to a printer, the address lines ensure the data goes to the correct location (the printer) rather than another device like a hard drive.

3. **Control Lines**:
   - **Explanation**: These lines manage the operations of data transfer, telling the CPU when to send or receive data and how to handle it.
   - **Example**: When you click ‘print’, the control lines send a signal to the printer to start the printing process.


![[Pasted image 20240814042411.png | 700]]

### Interface Modules

These are specific types of interfaces used to connect different peripherals to the computer. Each type of interface module is designed for a specific kind of peripheral or a set of peripherals.

1. **SCSI (Small Computer System Interface)**:
   - **Explanation**: SCSI is used to connect multiple devices like hard drives, scanners, and printers to a single computer, allowing them to communicate and transfer data.
   - **Example**: In servers, SCSI can connect several hard drives, allowing them to work together for large-scale data storage and retrieval.

2. **IDE (Integrated Device Electronics)**:
   - **Explanation**: IDE is commonly used to connect storage devices like hard drives and optical drives (CD/DVD drives) directly to the computer’s motherboard.
   - **Example**: Older desktop computers often used IDE cables to connect their hard drives to the motherboard.

3. **RS-232**:
   - **Explanation**: RS-232 is a standard for serial communication, often used to connect computers to modems or other communication devices.
   - **Example**: In older computer systems, RS-232 was used to connect the computer to a modem for dial-up internet access.

### I/O Commands

These are instructions used by the CPU to manage and control input/output operations with peripherals.

1. **Control Command**:
   - **Explanation**: This command is used to control the operation of a device, telling it what to do.
   - **Example**: When you press the ‘eject’ button on a CD drive, a control command is sent to the drive to open.

2. **Status Command**:
   - **Explanation**: This command checks the status of a device to see if it is ready for an operation or if there are any errors.
   - **Example**: Before printing, a status command might check if the printer is online and has enough paper.

3. **Input Command**:
   - **Explanation**: This command is used to read data from a peripheral device.
   - **Example**: When you scan a document using a scanner, an input command reads the data from the scanner and sends it to the computer.

4. **Output Command**:
   - **Explanation**: This command is used to send data to a peripheral device.
   - **Example**: When you send a document to a printer, an output command transfers the document data from the computer to the printer.

### Summary

- **I/O Organization** ensures smooth communication between the CPU and peripherals.
- **Input-Output Interface** helps manage data flow and synchronization between the CPU and devices.
- **I/O Bus** is the pathway that carries data, addresses, and control signals between the CPU and peripherals.
- **Interface Modules** are specialized connections for different types of peripherals.
- **I/O Commands** control, check, and manage the data transfer process between the CPU and peripherals.

## Polling

**Polling** is a technique used by the CPU to continuously check the status of an I/O device to see if it needs attention.

#### How Polling Works

1. **Busy Waiting**: The CPU repeatedly checks the status bits of an I/O device to see if it is ready for data transfer. This is known as busy waiting because the CPU is actively waiting and not performing any other tasks during this time.
2. **Data Transfer**: Once the device is ready, the CPU feeds data into the device’s controller register one byte at a time.

#### Characteristics of Polling

- **Resource Intensive**: Polling can be very resource-intensive, especially for large data transfers, because the CPU is occupied with checking the device status instead of performing other tasks.
- **Limited Use**: Due to its inefficiency, polling is generally only acceptable for small, dedicated systems that do not run multiple processes.

#### Example of Polling

Imagine a scenario where a computer is connected to a printer via a parallel port. The computer needs to send data to the printer. Using polling, the CPU would continuously check if the printer is ready to receive the next byte of data. This involves checking a specific status bit in the printer’s controller register. Once the printer is ready, the CPU sends the next byte of data. This process repeats until all data is sent.

#### Advantages and Disadvantages

**Advantages**:

- **Simplicity**: Polling is straightforward to implement.
- **Control**: The CPU has direct control over the timing of data transfers.

**Disadvantages**:

- **Inefficiency**: The CPU spends a lot of time checking the status of the device, which can be wasteful.
- **Scalability**: Polling does not scale well with multiple devices or large data transfers.


## Interrupts


![[Pasted image 20240814050802.png | 700]]


**Interrupts** are signals sent to the CPU by hardware or software indicating an event that needs immediate attention.

#### How Interrupts Work

1. **Interrupt Lines**: Devices use interrupt lines on the bus to signal the CPU, rather than dedicated wires.
2. **Interrupt Report Line**: The CPU hardware has an interrupt report line that it senses after executing every instruction.
3. **Raising an Interrupt**: When a device needs attention, it raises an interrupt.
4. **Handling the Interrupt**:
    - The CPU catches the interrupt and saves its current state (e.g., the instruction pointer).
    - The CPU dispatches the interrupt handler.
    - The interrupt handler determines the cause, services the device, and clears the interrupt.

#### Why Interrupts?

Interrupts are essential because I/O devices need timely attention. Without interrupts, the CPU would have to use inefficient polling methods to check device status continuously.

#### Real-Life Analogy

Think of an interrupt like an alarm that goes off when your food is ready. You can do other things while waiting for the alarm, and when it rings, you know it’s time to attend to the food.

#### Support for Interrupts

- **Deferring Handling**: The system needs the ability to defer interrupt handling during critical processing.
- **Efficient Dispatch**: Interrupts come with an address (offset in the interrupt vector) that selects a specific interrupt handler.
- **Multi-Level Interrupts**: Systems often need multi-level interrupts to prioritize different types of interrupts.

#### Interrupt Handler

- **Boot Time**: At boot time, the OS probes the hardware buses to determine what devices are present and installs corresponding interrupt handlers into the interrupt vector.
- **During I/O Interrupt**: The controller signals that the device is ready, and the interrupt handler takes over.

#### Types of Interrupts

- **Hardware Interrupts**: Triggered by hardware devices like keyboards, mice, or network cards.
- **Software Interrupts**: Triggered by software instructions or system calls.

#### Examples of Interrupts

- **Division by Zero**: An arithmetic error that triggers an interrupt.
- **Virtual Memory Paging**: When the system needs to load a page from disk into memory.
- **System Calls**: Software interrupts triggered by programs to request services from the OS.

### Advantages and Disadvantages of Interrupts

#### Advantages

1. **Efficiency**: Interrupts allow the CPU to perform other tasks instead of continuously polling devices, making better use of CPU time.
2. **Responsiveness**: Devices can signal the CPU immediately when they need attention, leading to faster response times.
3. **Scalability**: Interrupts can handle multiple devices more effectively than polling, especially in systems with many I/O devices.
4. **Prioritization**: Interrupts can be prioritized, allowing critical tasks to be addressed promptly while less critical tasks wait.

#### Disadvantages

1. **Complexity**: Implementing interrupt handling can be more complex than polling, requiring careful design to manage interrupt priorities and handlers.
2. **Overhead**: Each interrupt incurs overhead as the CPU must save its state, handle the interrupt, and then restore its state. This can be significant if interrupts are frequent.
3. **Interrupt Latency**: There can be a delay (latency) between when an interrupt is raised and when it is serviced, especially if the system is handling multiple interrupts.
4. **Resource Contention**: If multiple devices generate interrupts simultaneously, it can lead to contention and require sophisticated handling to ensure all devices are serviced appropriately.

## Direct Memory Access (DMA)

**Direct Memory Access (DMA)** is a method that allows an I/O device to send or receive data directly to or from the main memory, bypassing the CPU to speed up memory operations. 

#### How DMA Works

1. **Assists in Data Exchange**: DMA assists in the exchange of data between the CPU and I/O controllers. Instead of the CPU handling data transfers byte by byte, which can be inefficient, especially for large transfers like disk data, DMA uses a special-purpose processor called a DMA controller.
2. **DMA Controller**: The DMA controller manages the data transfer process, allowing the CPU to perform other tasks. It operates the memory bus directly without the help of the main CPU.

#### DMA-CPU Protocol

1. **Programming the DMA Controller**: The CPU programs the DMA controller by setting registers to specify source and destination addresses, byte count, and control information (e.g., read/write).
2. **Data Transfer**: The DMA controller takes over and handles the data transfer directly between the I/O device and memory.
3. **Acknowledgment**: Once the data transfer is complete, the disk controller acknowledges the transfer to the DMA controller.

#### Example of DMA

Consider a scenario where data needs to be transferred from a disk to the main memory. The CPU sets up the DMA controller with the necessary parameters (source address, destination address, byte count) and then continues with other tasks. The DMA controller handles the data transfer directly, moving data from the disk to the main memory without further CPU intervention. Once the transfer is complete, the DMA controller signals the CPU.

#### DMA Issues

1. **Handshaking**: There needs to be proper handshaking between the DMA controller and the device controller to ensure data is transferred correctly.
2. **Cycle Stealing**: The DMA controller can take away CPU cycles when it uses the CPU memory bus, temporarily blocking the CPU from accessing the memory. This is known as cycle stealing.
3. **Performance Improvement**: Despite the potential for cycle stealing, the DMA controller generally improves overall system performance by offloading data transfer tasks from the CPU.

#### Advantages and Disadvantages of DMA

**Advantages**:

- **Efficiency**: Frees up the CPU to perform other tasks while data transfer is handled by the DMA controller.
- **Speed**: Faster data transfer rates compared to CPU-managed transfers.
- **Reduced CPU Overhead**: Minimizes the CPU’s involvement in data transfer, allowing it to focus on other processes.

**Disadvantages**:

- **Complexity**: Implementing DMA requires additional hardware and software complexity.
- **Cycle Stealing**: Can temporarily block the CPU from accessing memory, potentially impacting performance.

## Data Transfer Methods

![[Pasted image 20240814051732.png | 700]]

Data transfer methods are crucial for communication between devices in a computer system. Here’s a detailed explanation of the different types of data transfer methods:

#### 1) Synchronous Data Transfer

**Synchronous Data Transfer** occurs when data transfers are synchronized with a clock signal. This means that both the sender and receiver share a common clock, ensuring that data is transmitted at regular intervals.

- **Characteristics**:
    - **Simultaneous Transfers**: All data transfers occur simultaneously during the occurrence of a clock pulse.
    - **Common Clock**: Registers in the interface share a common clock with CPU registers, which is used as a reference point for data transmission.
    - **Efficiency**: Synchronous transmission is efficient for high-speed, continuous data transfer because there is no need for start and stop bits.
- ***Example***: Video conferencing, where data needs to be transmitted continuously and in real-time.

#### 2) Asynchronous Data Transfer

**Asynchronous Data Transfer** occurs without a common clock signal. Instead, data is sent one byte or character at a time, with start and stop bits indicating the beginning and end of each byte.

- **Characteristics**:
    - **Independent Timing**: Internal timing in each unit (CPU and Interface) is independent, meaning each unit uses its own private clock for internal registers.
    - **Start and Stop Bits**: Special bits are inserted at both ends of the character code to indicate the start and end of transmission.
    - **Flexibility**: Asynchronous transmission is used when data is sent sporadically, such as with a mouse or keyboard.
- ***Example***: Email communication, where data is sent intermittently rather than continuously.

![[Pasted image 20240814051921.png | 700]]

### Synchronous VS Asynchronous
![[Pasted image 20240814051858.png | 700]]
#### 2.1) Handshake Data Transfer

**Handshake Data Transfer** involves a more intricate process where devices go through a series of steps to ensure they are ready to communicate before any data is exchanged.

- **Characteristics**:
    - **Protocol**: Similar to a handshake between two people, there is a protocol to follow before the actual interaction begins.
    - **Reliability**: This method ensures that both devices are ready for data transfer, making it more reliable for complex and secure exchanges of information.
- ***Example***: USB communication, where devices negotiate the data transfer rate and other parameters before starting the actual data transfer.

![[Pasted image 20240814052032.png | 700]]
#### 2.2) Strobe Data Transfer

**Strobe Data Transfer** involves sending information in a rapid succession of pulses, similar to sending a signal with a flashlight.

- **Characteristics**:
    - **Quick Pulses**: Data is transmitted in quick flashes, allowing for rapid communication between devices.
    - **Simple Exchanges**: This type of transfer is often used for quick and simple exchanges of information.
- ***Example***: Simple sensor data transmission, where quick and short bursts of data are sent.

![[Pasted image 20240814051956.png | 700]]

## I/O Software Layers

I/O software layers are essential for managing communication between the CPU and peripheral devices. Here’s a detailed explanation of the concepts:

### Device Controller

**Device Controller** is a hardware component that manages the communication between the CPU and an I/O device. It typically consists of:

- **Mechanical Component**: The physical device itself.
- **Electronic Component**: The device controller or adapter that interfaces with the device.

**Interface**: The interface between the controller and the device is very low-level, handling basic operations like converting data formats and performing error correction.

**Example**: A disk controller converts the serial bit stream coming off the drive into a block of bytes and performs error correction.

### I/O Controller

**I/O Controller** is responsible for implementing the protocol for data transfer between the CPU and the device. For example, a disk controller handles:

- **Bad Error Mapping**: Identifying and managing errors in data.
- **Prefetching**: Loading data into memory before it is needed to improve performance.
- **Buffering**: Temporarily storing data to manage differences in data transfer rates.
- **Caching**: Storing frequently accessed data for quick retrieval.

**Communication**: The CPU and controllers communicate via I/O instructions and registers or through memory-mapped I/O.

### I/O Ports

**I/O Ports** are interfaces through which data is transferred between the CPU and peripheral devices. There are typically four registers associated with I/O ports:

1. **Status Register**: Holds information about the current status of the device, such as whether a command is completed, data is available, or an error has occurred.
2. **Control Register**: Allows the host to start a command or change the mode of the device.
3. **Data-in Register**: Used by the host to read input data from the device.
4. **Data-out Register**: Used by the host to send output data to the device.

**Size of Registers**: The size of these registers typically ranges from 1 to 4 bytes, determining the maximum amount of data that can be transferred or stored at once.

#### Examples

- **Keyboard**: When a key is pressed, the corresponding data is available for the host to read from the data-in register.
- **Printer**: The host writes printable data to the data-out register for the printer to receive and print.

### Interfacing Peripherals

Interfacing peripherals involves connecting external devices to a computer system to facilitate communication and data transfer. Here’s a detailed explanation of the concepts:

#### I/O-Mapped I/O

![[Pasted image 20240814054242.png | 700]]
**I/O-Mapped I/O** uses special CPU instructions to access peripheral devices. These instructions are different from those used to access memory.

- **Special Instructions**: Specific instructions like `IN` and `OUT` are used to read from and write to I/O ports.
- **Address Space**: Peripheral devices are assigned addresses within a separate I/O address space, distinct from the memory address space.
- **Operation**: When the CPU accesses an address corresponding to a peripheral device, it triggers a read or write operation on that device rather than accessing actual memory.
- **Programming**: This approach simplifies programming since the CPU interacts with devices in a consistent manner, but it can lead to contention between memory access and I/O access as both share the same address space.

**Example**: A keyboard connected to a computer might use I/O-mapped I/O. The CPU uses specific instructions to read key presses from the keyboard’s I/O port.

#### Memory-Mapped I/O

![[Pasted image 20240814054303.png | 700]]

![[Difference-Between-Memory-Mapped-IO-and-IO-Mapped-IO_Figure-1.webp | 700]]

**Memory-Mapped I/O** assigns each device register to a memory address in the address space of the microprocessor.

- **Address Space**: I/O devices are assigned addresses within the same address space as the memory.
- **Instructions**: Native CPU load/store instructions (`LDR`, `STR`) are used to access these addresses.
- **Operation**: Reads and writes to these addresses are interpreted as operations on the I/O devices rather than on actual memory.
- **Separation**: This approach allows for better separation between memory and I/O operations, reducing contention between the two.

**Example**: A graphics card might use memory-mapped I/O. The CPU writes data to specific memory addresses that correspond to the graphics card’s registers, which then render the data on the screen.

### Comparison Between Memory-Mapped I/O and I/O-Mapped I/O


![[Pasted image 20240814053315.png | 700]]

#### Hybrid Approach

Some systems use a hybrid approach, combining aspects of both I/O-mapped and memory-mapped I/O to balance the benefits and drawbacks of each method.

> [!Interfacing Type]
> **(a)** Separate I/O and memory space
> **(b)** Memory-mapped I/O
> **(c)** Hybrid

![[Pasted image 20240814054203.png | 700]]


> [!Memory-Mapped I/O (2)]
> **(a)** A single-bus architecture
> **(b)** A dual-bus memory architecture

![[Pasted image 20240814053721.png | 700]]
#### Architectures

- **Single-Bus Architecture**: Both memory and I/O devices share the same bus, which can lead to contention.
- **Dual-Bus Architecture**: Separate buses for memory and I/O devices, reducing contention and improving performance.

### Device Drivers

![[Pasted image 20240814054507.png | 700]]

**Device drivers** are specialized software programs that allow the operating system (OS) to communicate with hardware devices. They act as a bridge between the hardware and the OS, translating high-level commands from the OS into low-level commands that the hardware can understand.

#### Logical Position and Communication

- **Logical Position**: Device drivers are typically part of the OS kernel. They are compiled with the OS and can be dynamically loaded during execution.
- **Communication**: Drivers communicate with device controllers over the bus. Each controller has device registers used to give commands. The number and nature of these registers vary by device (e.g., a mouse driver receives movement data, while a disk driver manages sectors, tracks, and heads).

#### Device-Specific Code

- **Manufacturer-Specific**: The code to control an I/O device is usually written by the device’s manufacturer. This ensures that the driver can handle the specific features and functions of the device.

#### Types of Device Drivers

- **Single Device Type**: Some drivers handle only one type of device (e.g., a mouse driver).
- **Class of Devices**: Others handle a class of closely related devices (e.g., a SCSI disk driver that manages multiple disks of different sizes and speeds).

#### Categories of Device Drivers

- **Block Devices**: These manage devices that store data in fixed-size blocks (e.g., hard drives, SSDs).
- **Character Devices**: These manage devices that transmit data as a stream of characters (e.g., keyboards, mice).

### Functions in Device Drivers

1. **Accept Abstract Read and Write Requests**: Device drivers receive high-level read and write requests from the device-independent layer above them.
2. **Initialize the Device**: They initialize the device to prepare it for operation.
3. **Manage Power Requirements and Log Events**: Drivers handle power management and log significant events.
4. **Check Input Parameters**: They validate input parameters to ensure they are correct.
5. **Translate Input**: Drivers convert abstract input (e.g., a linear block number) into concrete terms (e.g., head, track, sector, and cylinder number for disk access).
6. **Check Device Status**: They check if the device is in use by examining the status bit.
7. **Control the Device**: Drivers issue a sequence of commands to control the device, determining what commands will be issued based on the device’s state and the requested operation.

### Examples

- **Mouse Driver**: Accepts movement data from the mouse and translates it into cursor movements on the screen.
- **Disk Driver**: Manages read and write operations on a hard drive, converting high-level file system requests into low-level disk operations.

### Buffering

**Buffering** is a technique used to manage data transfer between two devices or between a device and an application. It involves using a memory area called a buffer to temporarily store data during the transfer process.

#### Reasons for Buffering

1. **Speed Mismatch**:
    - **Example**: When transferring data from a fast device (like a CPU) to a slower device (like a printer), buffering helps to manage the speed difference. Double buffering can be used to ensure that one buffer is being filled while the other is being emptied, thus maintaining a continuous flow of data.
2. **Different Data-Transfer Sizes**:
    - **Example**: When transferring data between devices that have different data-transfer sizes, buffering helps to adapt the data to the required size. For instance, a network card might send data in packets of 1500 bytes, while the receiving application might process data in chunks of 512 bytes.
3. **Copy Semantics for Application I/O**:
    - **Example**: When an application writes data to an application buffer, the OS copies it to the kernel buffer and then writes it to the disk. This ensures that the application can continue processing without waiting for the I/O operation to complete.
4. **Unbuffered Input Inefficiency**:
    - **Example**: Without buffering, the user process must be started up with every incoming character, which is inefficient. Buffering allows the system to collect multiple characters before processing them.
5. **Output Buffering**:
    - **Example**: Buffering is also important for output operations. For instance, when printing a document, the data is buffered before being sent to the printer to ensure smooth and continuous printing.


### Caching

**Caching** is a technique where a region of fast memory holds copies of data to allow for more efficient access. It is often used to speed up data retrieval by storing frequently accessed data in a cache.

- **Example**: Web browsers use caching to store copies of frequently visited web pages, reducing the time it takes to load these pages on subsequent visits.
- **Reference**: Caching - Wikipedia)

### Buffering Strategies

1. **Unbuffered Input**:
    - **Description**: Data is processed as it arrives, without any intermediate storage.
    - **Example**: Reading a single character from a keyboard and processing it immediately.
    - **Reference**: Unbuffered Input
2. **Buffering in User Space**:
    - **Description**: Data is buffered in the user space before being processed.
    - **Example**: An application collects data in a buffer before sending it to the network.
    - **Reference**: User Space Buffering
3. **Buffering in the Kernel Followed by Copying to User Space**:
    - **Description**: Data is first buffered in the kernel space and then copied to the user space.
    - **Example**: A file read operation where data is first read into a kernel buffer and then copied to the application’s buffer.
    - **Reference**: Kernel Buffering
4. **Double Buffering in the Kernel**:
    - **Description**: Two buffers are used in the kernel space to allow continuous data transfer.
    - **Example**: While one buffer is being filled with incoming data, the other buffer is being processed.
    - **Reference**: Double Buffering

![[Pasted image 20240814054806.png | 700]]

## Error Reporting

Error reporting in operating systems is crucial for maintaining system stability and ensuring that errors are properly handled and communicated. 

#### Programming IO Errors

**Definition**: These errors occur when a process requests an operation that is not possible or logical for the device.

- **Example**: Attempting to write data to an input-only device like a keyboard or trying to read data from an output-only device like a printer.
- **Explanation**: Such errors are typically due to incorrect programming logic where the application or process makes invalid requests to the device. The operating system must detect these errors and handle them appropriately to prevent system crashes or undefined behavior.

#### Actual IO Errors

**Definition**: These errors occur at the hardware level, often due to physical issues with the device.

- **Example**:
    - **Read Disk Block Error**: Trying to read a disk block that has been damaged.
    - **Disconnected Device**: Attempting to read from a video camera that is switched off or disconnected.
- **Explanation**: These errors are usually detected by the device controller or the operating system. The OS must handle these errors by either retrying the operation, reporting the error to the user, or taking corrective actions such as marking the disk block as bad.

#### Device-Independent IO Software

**Definition**: This software layer is responsible for detecting and handling errors in a way that is independent of the specific devices involved.

- **Example**: When an error occurs, the device-independent IO software will detect it and report it to the user-space IO software, which can then take appropriate action such as notifying the user or logging the error.
- **Explanation**: This abstraction allows the operating system to handle errors uniformly across different types of devices, simplifying error management and improving system reliability.


Error reporting in operating systems involves detecting and handling both programming IO errors and actual IO errors. Programming IO errors are typically due to invalid requests made by processes, while actual IO errors are due to hardware issues. The device-independent IO software plays a crucial role in managing these errors and ensuring they are reported to the user-space IO software for appropriate handling.

<div style="width:100%;height:0;padding-bottom:66%;position:relative;"><iframe src="https://mymap.ai/share/mindmap-of-input-and-output-devices-and-methods-vnFZ4t1hzrmjt" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div>

# Reference
![[9. Input and output devices and methods (1).pdf]]