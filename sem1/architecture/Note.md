# Boolean Algebra Simplification

1. 
![[Drawing 2025-01-17 11.47.23.excalidraw]]

3. **f=x(x+y)**
![[Drawing 2025-01-17 10.02.25.excalidraw]]


3. **f=(x+y)(x+z)**
![[Drawing 2025-01-17 10.11.26.excalidraw]]

4. **f = abc + ab'c + abc'**
![[Drawing 2025-01-17 10.28.29.excalidraw]]

5. **f = xy + x(y+z) + y(y+z)**
![[Drawing 2025-01-17 10.54.33.excalidraw]]

6. 
![[Drawing 2025-01-17 11.15.20.excalidraw]]

## Half Adder
With  the help of half adder, we can design circuit that are capable of performing simple addition with the help of logic gates. 
- 0+0 = 0
- 0+1 = 1
- 1+0 = 1
- 1+1 = 1

![[IMG20250120131512.jpg]]

![[Drawing 2025-01-20 13.25.48.excalidraw]]


## Full Adder
- The main difference between a half adder and a full adder is that the full adder has **three inputs and two outputs**. 
- The first **two inputs are A and B** and the *third input is an input carry designated as carry in*.

![[IMG20250120133545.jpg]]

![[IMG20250120133930.jpg]]

# Fetch Execution Cycle 

##### What is Fetch Execution Cycle?
- Fetch Execute Cycle is a procedure that show how computer system get instruction from the memory
![[IMG20250120134550.jpg]]


- During the fetch executed cycle, the computer retrieves as program instruction from it memory. it then establish and carries out the actions that are required for that instruction. 
- The cycle of fetching, decoding, and executing an instruction is continually related by the CPU whilst the computer is turned on. 

![[IMG20250120135532.jpg]]


## Memory Hierarchy 
- The memory is a computer can be discussed into five hierarchies based on the speed as well as use. 
- The processor can move from one level to another based on its requirements. 
- The five hierarchies in the memory are registers, cache, main memory, magnetic disks, and magnetic tapes.

![[IMG20250120140605.jpg]]

## Primary Memory

- The primary memory is also known as internal memory, and this is accessible by the processor straightly.
- This memory includes **main, cache, as well as CPU registers.**
- Primary Memory is computer memory that a **processor or computer access first or directly**.
- It allows a processor to access running Execution applications and services that are **temporarily stored in a specific memory location**.
- Primary Memory is also known as primary storage or main memory.

## Secondary Memory

- The secondary Memory is also known as external memory, and this is accessible by the processor thought an input/output module. 
- This memory includes an optical disk, magnetic disk, and magnetic tapes. 
- It is different from primary memory as it is not directly accessible through the CPU and it's noon volatile. 
- Secondary or external storage devices have a much larger storage capacity and the cost of secondary Memory is less as compared to primary memory. 
![[IMG20250120144054.jpg]]

# Central Processing unit 

- There are many such part of a computer CPU, but mainly the Central Processing unit has only three parts.
- There are three main parts of CPU (Central Processing unit), witch are given below. 
    - ALU
    - CU
    - Memory or storage unit

![[IMG20250120152242.jpg]]

Arithmetic and logical unit (ALU)
- The Arithmetic and logical unit (ALU) is a fundamental component in all computers that performs arithmetic and logical operations
- The ALU is used to addition, substraction, multiplication, division, comparison of two numbers, and Boolean operations. 
- It does not handle instruction sequencing or directly deal with memory. 
- The ALU has had some major advantages over the CPU because it only needs to be designed for one type of task instead of many. 

## Control Unit (CU)

- The Control Unit(CU) is the part of a computer that controls what happen inside it.

- It is like the brain of as computer, making decisions and controlling what goes on inside the machine. 

- The CPU reads the instructions that are stored in is memory and send it electrical signals to each component of the computer, telling them what to do with the data they've been given.

## Memory or Storage unit 

- A memory or storage unity in a computer is an electronic device that storages data, programs, and other information. 
- The two main types of memory are Ram and Hard Drive. Ram stands for Random access memory. 
- It is a volatile type of storage because it requires power to maintain is contents.
- It is mostly used for temporarily storing data while the computer is on. 


# Process

### What is Process ?
- Process is a fundamental concept in modern operating system.
- A process is basically a programming in execution 
- Process in not a program. A program may have many processes.

### Process Requirements
- The process must have (at least):
  - ID
  - Executable code
  - Data needed for execution
  - Execution context (PC, Priorities, waiting for I/O or not)

### Process creation 
- Reason for process creation:
  - New batch job
  - User starts a program 
  - Os creates process to provide a service
  - Running program starts another process 

### Process Termination
- On process termination, OS reclaim all resources assigned to the process.
- Reasons for process termination:
  - Normal termination
  - Execution time-limit exceeded
  - A resource requested is unavailable
  - An execution error
  - A memory access violation
  - An operating system or  parent process request
  - Parent process has terminated

### Interrupts 
- An interrupt is a signal to the processor emitted by hardware or software indicating an event that needs immediate attention.
- Whenever an interrupt occurs, the controller completes the execution of the current instruction and starts the execution of an Interrupt Service Routine (ISR) or Interrupt Handler.
- Interrupt is an event that alters the sequence of execution of process.
- interrupt can occur due to a time expiry an OS service request I/O completion.
  - For example when a disk driver has finished transferring the requested data, it generate an interrupt to the OS to inform the OS that task is over.
- Interrupts occur asynchronously to the ongoing activity of the processor.
- Thus the times at which interrupts occur are unpredictable. 


### Seven status in process
In a normal execution method create new process then moves in to the ready queue 
process will take the process from the ready queue and execute the process and release the resources and terminate.

![[Drawing 2025-01-27 14.01.45.excalidraw]]


### Context Switch

- A context switch is the mechanism to store and restore the state or context of a CPU in Process Control block so that a process execution can be resumed from the same point at a later time.
- Using this technique a context switcher enables multiple processes to share a single CPU. Context switching is an essential part of a multitasking operating system feature.
- When the scheduler switches the CPU from executing one process to execute another, the context switcher saves the content of all processor registers for the process being removed from the CPU, in its process control block.
- Context switch time is pure overhead.

![[Drawing 2025-01-27 14.32.08.excalidraw]]

### Types of Scheduling
- Long-Term Scheduling (Job Scheduling)
- Medium-Term Scheduling
- Short-Term Scheduling

#### Long-term Scheduling (Job scheduling)
- It determines which programs are admitted to the system for processing.
- Job scheduler selects processes from the queue and loads them into memory for execution. Process loads into the memory for CPU Scheduling. 

#### Medium-term Scheduling
- Medium term scheduling is in charge of  swapping processes between the main memory and the secondary storage.

#### Short-term scheduling (low-level scheduling)
- Determines which ready process will be assign the CPU when it next becomes available.

### Process Schedulers
- Turnaround time: Time required for a particular process to complete, from submission time to completion.
- Response time: The time taken in an interactive program from the issuance of a command to the commence of a response to that command.
- Throughput: Number of processes completed per unit time.
- Waiting time: How much time a process spend in the ready queue waiting its turn to get on the CPU.





# Assignment
---
## Operator
As job role
1. Welcoming Visitors
    - Slack
2. Answering Phones
    - qx3
3. Scheduling Meetings
    - zoom
4. Visitor Management
    - ms365



---
## Software engineer
As job role
1. Develop a site

  - windows 10
    - **Processor**: 1 GHz or faster with at least 2 cores on a compatible 64-bit
    - **RAM**: 2 GB RAM
    - **Hard Disk**: 20 GB for 64-bit OS

  - vscode
    - **Processor**: 1.6 GHz or faster
    - **RAM**: 1 GB RAM
    - **Hard Disk**: 200 MB of available space

  - jet brain
    - **Processor**: 2 GHz or faster
    - **RAM**: 4 GB
    - **Hard Disk Space**: 2.5 GB of free disk space, SSD recommended for optimal performance

  - java
    - **Processor**: 1 GHz or faster
    - **RAM**: 512 MB
    - **Hard Disk Space**: At least 300 MB of free disk space

  - mysql
    - **Processor**: 1 GHz or faster
    - **RAM**: 1 GB RAM
    - **Hard Disk Space**: At least 1 GB of free disk space

2. Local host website 
  - windows 10
    - **Processor**: 1 GHz or faster with at least 2 cores on a compatible 64-bit
    - **RAM**: 2 GB RAM
    - **Hard Disk**: 20 GB for 64-bit OS

  - apache
      - **Processor**: 1 GHz or faster
      - **RAM**: 512 MB
      - **Hard Disk Space**: At least 100 MB of free disk space

  - docker
    - **Processor**: 64-bit processor with Second Level Address Translation (SLAT)
    - **RAM**: 4 GB
    - **Hard Disk Space**: At least 1 GB of free disk space

  - postman
    - **Processor**: 1.8 GHz or faster
    - **RAM**: 4 GB
    - **Hard Disk Space**: At least 500 MB of free disk spac

3. Software Development
  - visual studio 
    - **Processor**: 1.8 GHz or faster
    - **RAM**: 4 GB
    - **Hard Disk Space**: Minimum 850 MB
  - ms office
    - **Processor**: 1.6 GHz or faster, 2-core processor
    - **RAM**: 4 GB
    - **Hard Disk Space**: At least 4 GB of available disk space
  - python
    - **Processor**: 1 GHz or faster
    - **RAM**: 1 GB
    - **Hard Disk Space**: At least 100 MB of free disk space
4. Testing and Debugging
  - xcode
    - **Processor**: 1 GHz or faster
    - **RAM**: 8 GB
    - **Hard Disk Space**: At least 12.5 GB of available disk space
  - dbForge SQL Tool
    - **Processor**: 1 GHz or faster
    - **RAM**: 4 GB
    - **Hard Disk Space**: At least 1 GB of free disk space
  - Selenium
    - **Processor**: 2 GHz or faster
    - **RAM**: 4 GB
    - **Hard Disk Space**: Sufficient space for the operating system, browser, and any test data.
5. Maintenance and Support
  - Slack
    - **Processor**: 1 GHz or faster
    - **RAM**: 4 GB
    - **Hard Disk Space**: At least 500 MB of free disk space
  - zoom
    - **Processor**: Dual-core 1 GHz or higher
    - **RAM**: 4 GB
    - **Hard Disk Space**: At least 1 GB of free disk space



---
## Graphic designer
As job role
6. Concept Development
    - Adobe ai
    - penpot
    - sketch 
7. Branding
    - Adobe Photoshop
    - canva
8. Typography
    - InVision
    - google-fonts
9. Digital Design
    - figma
    - motion
10. Software Proficiency
    - adobe xd



---
## Project manager
As job role
11. Project Planning
    - Trello
    - slack
12. Team Leadership
    - Microsoft Teams
    - zoom
13. Stakeholder Communication
    - Google Workspace
    - meet
14. Quality Assurance
    - JIRA
    - Asana
15. Problem-Solving
    - monday
    - Basecamp