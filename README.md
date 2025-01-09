# GarbageOS
How to design an OS from first principles

A lot of operating system development guides stress the ***SUPER INTENSE*** and *scarryyyy* difficulty of writing your own OS. But here we like to keep things fun and friendly. Want to write something you could *technically* call an OS in 100 lines of code and call it done? Sure! IDGAF. (Future note: OS dev is definitely scary. But don't be afraid to make something fun and small!)

## LICENSE

[MIT](https://mit-license.org/)

## Need to know

- Algorithms
- Data Structures
- Programming best practices
- Assembly
- C/C++
- Linux
- Toolchains
- Emulators and VMs
- Executables
- Target platform
  - Instruction Set
  - Chipset
  - Privledge levels
  - Memory
  - *Registers*

## Descisions (not strictly in order)

- Target platform (START HERE)
- Supported toolchain (OR HERE)
- Initial toolchain
- Portability and compatabiltiy
- Use of BIOS
- Bootstrapping
- Interrupts
- Memory
- Processes and scheduling (mutlitasking?)
- Device drivers
- Program ABI/API (system calls)
- File System
- Programs
- UI
- Networking
- Security
- 

### Target platform

Do you imagine your operating system running on a SNES? Your laptop? Here's where you decide that.
There's several different avenues to take here. If you want to explore different architectures, here's the place to do that.
But if you know what system you want, all you need to do is find some manuals and start reading.

#### CPUs

- Motorolla 68000
- MOS 65xx
- x86
- Power PC
- Zilog Z80
- RISC-V
- ARM

#### What can ya make an OS on?

- Smart watch
- Ya moms frigde
- Game consoles
- Phone
- PC/Desktop

### Supported toolchains

What development toolchains does your OS support?

A common goal of many homebrew enthusiasts is a "self hosting" operating system.
You may also want to write some programs on your OS.
That's why this is important.

While C has been commonly used for hobby OS dev, in OS development history, a given language/toolchain was heavily associated with a given family of operating systems. Currently, UNIX and C are the survivours of a turbulent battle of languages and OS. But notable from back in the day are Forth and Lisp. They are both very easy to create and very powerful in their own way and well suited for OS dev.

### Initial toolchain

What toolchain are you writing your OS with?

  - This is a very important step, but is mostly important for implementation, less so for design/planning.
  - This can match your supported tools

### Portability and compatability

todo!();

## Example

- Lets say we want to create a single user, single threaded OS, that can run on my x64 lenovo laptop.
- Additionally, the entire OS runs in real mode and has no concept of OS privledge.
- We want the OS to be based on Forth.
- First implement some functions to support creating a Forth (linked list, threaded code, input/output).
- Next we implement serial output for debugging.
- Then we implement a interrupt handler, for both software and hardware interrupts.
- If we haven't already we can create some rudimentary heap allocation for good meassure (VERY helpful, not necessary)
- Then we can implement an interpreter, that runs Forth as we input command by command. (This could be considered a resident monitor, a rudimentary OS)
- From here we could use our Forth to implement a text editor or any other programs we may like.
- This is probably the bare minimum to create something that is usable that can be called an OS.
