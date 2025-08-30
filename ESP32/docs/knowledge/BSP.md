<h1 align="center">Board Support Package (BSP)</h1>

# What is a BSP?
A **Board Support Package (BSP)** is a collection of **software components, drivers, and configuration files** that make an operating system or firmware run correctly on a specific **hardware board**.

It acts as a **bridge between the hardware (SoC + peripherals)** and the **application software**.

---

# What Does a BSP Include?
A typical BSP contains:

1. **Bootloader**  
   - Initializes the hardware (CPU, clocks, memory).  
   - Loads the operating system or firmware into RAM/Flash.  

2. **Device Drivers**  
   - GPIO, UART, SPI, I²C, ADC, DAC, timers, etc.  
   - Board-specific drivers (LEDs, sensors, displays, buttons).  

3. **Startup Code**  
   - Low-level assembly/C code that sets up the CPU, stack pointer, interrupt vector table.  

4. **Hardware Abstraction Layer (HAL)**  
   - Provides a standard API so higher-level software doesn’t need to know exact register addresses.  

5. **Configuration Files**  
   - Pin mappings, memory layout, clock frequencies, board-specific parameters.  

---

# Why BSP is Needed
- Each board has **different wiring and peripherals** (even if it uses the same SoC).  
- Without a BSP, you’d have to manually set registers for every pin, clock, peripheral.  
- BSP allows the **same application code** to run on multiple boards by abstracting hardware differences.  

---

# Example: ESP32 BSP
For ESP32, the **ESP-IDF** (Espressif IoT Development Framework) is basically the **official BSP + OS abstraction**.  

It includes:
- **Bootloader** (`bootloader/`)  
- **Startup code** (`components/esp_system/`)  
- **Peripheral drivers** (`driver/gpio.h`, `driver/adc.h`, etc.)  
- **Board configs** (e.g., DevKitC, ESP32-WROVER, ESP32-S3)  
- **HAL layer** (common APIs for GPIO, UART, SPI regardless of board variant)  

For Arduino on ESP32, the **Arduino Core for ESP32** plays the role of a BSP.  

---

# Real-Life Analogy
Think of the **SoC** as the "engine,"  
the **board** as the "car frame,"  
and the **BSP** as the "wiring manual + driver interface" that lets you drive the car without needing to know the exact wiring of every cable.

---

# In short
**BSP = the software layer that adapts your OS/firmware to the specific hardware board.**

