# EdgeForge Linux Data Gateway

## 1. Project Goals and Motivation

EdgeForge Linux Data Gateway is an embedded Linux platform demonstrating the development and integration of userspace applications, Linux kernel modules, and a customized embedded Linux distribution.

The system receives data over TCP/IP and stores it through a custom Linux character device implementing a circular buffer.

The project aims to demonstrate practical expertise in:

- Embedded Linux image construction using Yocto.
- Linux application and system programming.
- Linux character-device driver development.
- TCP/IP communication and concurrent client handling.
- Kernel-module and application integration through Yocto recipes.
- Automated testing, deployment, and technical documentation.

The project is the first implementation milestone of EdgeForge, a larger embedded systems portfolio project.

## 2. Target Build System

**Build system:** Yocto Project / OpenEmbedded.

A project-specific Yocto layer will integrate the application, kernel module, and runtime configuration into the target Linux image.

The existing Buildroot implementation will be retained as a development reference but will not be maintained as a second complete distribution for this milestone.

## 3. Hardware Platform

**Target:** STM32MP157DK development board.

The initial implementation targets the Cortex-A7 processor running Linux. The Cortex-M4 processor is outside the scope of this course milestone.

The project will document the selected board configuration, supported Yocto/BSP components, bootloader, kernel, device tree, networking, and image-deployment procedure.

Official platform references:

- STMicroelectronics STM32MP157 documentation:
  [https://www.st.com/en/microcontrollers-microprocessors/stm32mp157/documentation.html](https://www.st.com/en/microcontrollers-microprocessors/stm32mp157/documentation.html)

- STM32MP1 OpenSTLinux Developer Package:
  [https://www.st.com/en/embedded-software/stm32mp1dev.html](https://www.st.com/en/embedded-software/stm32mp1dev.html)

- STM32MP1 developer documentation:
  [https://wiki.st.com/stm32mpu/index.php/STM32MP1_Developer_Package](https://wiki.st.com/stm32mpu/index.php/STM32MP1_Developer_Package)

## 4. Open-Source Projects and Dependencies

The implementation will use the Yocto/OpenEmbedded build system, the selected STM32MP1 board-support components, and the Linux kernel.

The project will also use standard Linux userspace and development tools required to build, deploy, and test the gateway.

Additional dependencies will be documented with their official references and licenses.

No additional networking framework is required for the initial implementation; the gateway will use the existing TCP server and Linux socket APIs.

## 5. Previous Assignment Content

The project will reuse and extend the following work:

- TCP server and client-handling implementation from previous Linux system-programming assignments.
- POSIX threading and synchronization.
- The AESD character-device driver and circular-buffer implementation.
- Kernel-module compilation and loading.
- Buildroot package integration and Yocto recipe development.
- Previous QEMU-based integration and debugging work.

The existing QEMU implementation will serve as a development baseline. Its driver integration, device-node handling, and read/write behavior will be validated before deployment to physical hardware.

## 6. Course Content Covered by the Project

### Application Programming

The TCP server will receive data from network clients and interface with the character device.

### System Programming

The implementation will use Linux sockets, POSIX threads, synchronization primitives, file operations, and error-handling mechanisms.

### Kernel Programming

The custom character driver will expose a device interface and manage a circular buffer with appropriate synchronization.

### Yocto and Embedded Linux

A custom Yocto layer will package the driver and application, configure startup behavior, and produce the target Linux image.

### Networking and Deployment

The system will be deployed on physical hardware and tested over Ethernet.

### Software Testing

Automated tests will validate the driver's behavior, TCP communication, concurrent access, and system integration.

### Agile Development

The implementation will be divided into three sprints, each with defined deliverables, acceptance criteria, and a Definition of Done.

## 7. Additional Topics

The project will prioritize integration, testing, and deployment rather than introducing many new frameworks.

Potential future extensions include MQTT-based telemetry, a read-only root filesystem, over-the-air updates, and integration with the Cortex-M4 processor.

These extensions are not required for the initial course milestone.

## 8. Relationship to Other Projects

This implementation is part of the broader EdgeForge portfolio project.

The Coursera-specific deliverables are:

- A customized Linux image running on physical hardware.
- The integrated TCP server and character-device driver.
- Reproducible build and deployment instructions.
- Automated tests and a final demonstration.
- Three-sprint planning and project documentation.

Future EdgeForge capabilities will be implemented incrementally and will not be prerequisites for evaluating this milestone.

## 9. Source-Code Organization

The main project repository will contain the Yocto layer, userspace application, kernel-module source, tests, deployment scripts, and technical documentation.

The repository will provide a README linking to this Project Overview wiki page.

Additional repositories will be introduced only if there is a clear need to separate independently maintained components.

## 10. Team

This is an individual project. All implementation, integration, testing, and documentation will be completed by the project author.

## 11. Schedule

The implementation will use three sprints of approximately 12 hours each.

- Sprint 1: Yocto image and hardware bring-up.
- Sprint 2: Character-driver and TCP gateway integration.
- Sprint 3: Automated testing, reliability, and final demonstration.

The Schedule wiki page will link to the project board and the issues tracking each sprint's deliverables.
