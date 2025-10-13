<h1 align="center">⚙️ STM32F103C8T6 Custom PCB in Kicad</h1>

<hr>

<h2>📘 Overview</h2>
<p>
This project presents a fully designed and routed PCB based on the <b>STM32F103C8T6</b> microcontroller — a popular ARM Cortex-M3 based MCU used widely in embedded systems, control units, and IoT applications. 
The design covers schematic creation, PCB layout, 3D rendering, and Gerber file generation using <b>KiCad 9.0.4</b>. 
The board integrates essential power regulation, programming/debugging headers, and communication interfaces, making it suitable for both learning and prototyping environments.
</p>

<hr>

<h2>🧩 Features</h2>
<ul>
  <li>Microcontroller: <b>STM32F103C8T6</b> (ARM Cortex-M3, 72 MHz, 64 KB Flash)</li>
  <li>Interfaces: UART, I2C, USB, and SWD Debug</li>
  <li>16 MHz Crystal Oscillator for stable system clock</li>
  <li>AMS1117-3.3V linear regulator from USB VBUS (5V to 3.3V)</li>
  <li>On-board BOOT0 switch for flash and system memory booting</li>
  <li>Compact double-layer PCB with decoupling and bulk capacitors</li>
  <li>All standard headers exposed for breadboard-friendly prototyping</li>
</ul>

<hr>

<h2>🔧 Circuit Design Details</h2>

<h3>Microcontroller Section</h3>
<p>
The core of the design revolves around the <b>STM32F103C8T6</b>. Proper pin mapping and peripheral allocation were done using <b>STM32CubeIDE</b> before schematic creation in KiCad. 
The nomenclature follows standard STM32 conventions:
<ul>
  <li><b>VDD / VDDA</b>: 3.3V supply</li>
  <li><b>VSS / VSSA</b>: Ground reference</li>
  <li><b>VBAT</b>: Backup domain supply (optional in this design)</li>
</ul>
</p>

<h3>Power Supply</h3>
<p>
Power is supplied via the USB connector. The <b>AMS1117-3.3V regulator</b> converts 5V (VBUS) to 3.3V for the MCU and peripherals. 
A combination of <b>decoupling capacitors (100nF per VDD pin)</b> and a <b>bulk capacitor (22µF)</b> ensures voltage stability. 
A <b>ferrite bead (FB1)</b> is used for VDDA filtering to isolate analog noise.
</p>

<h3>Clock Circuit</h3>
<p>
A <b>16 MHz crystal oscillator</b> (Y1) provides the external clock source. Load capacitors (C12, C13) are calculated based on crystal datasheet using:
<code>CL = 2 × (C_L - C_stray)</code>. 
The crystal’s ground pads are tied to <b>Crystal_GND24</b> for EMI reduction.
</p>

<h3>Reset and Boot Configuration</h3>
<p>
The <b>NRST</b> pin is connected to a pull-up resistor and reset header, allowing manual or external resets. 
A <b>BOOT0 switch</b> lets users toggle between Flash memory boot and system memory boot modes for easy firmware flashing.
</p>

<h3>USB Interface</h3>
<p>
The <b>Micro USB Type-B connector</b> provides both power and data interface. 
Differential data lines (<b>USB_D+</b> and <b>USB_D−</b>) are routed as a <b>differential pair</b> in KiCad for signal integrity. 
The <b>VBUS</b> pin powers the regulator, and <b>USB shield</b> is tied to board ground through high-value resistance to reduce noise coupling.
</p>

<h3>Communication Interfaces</h3>
<p>
The board exposes the following interfaces:
<ul>
  <li><b>UART</b> – USART1_TX, USART1_RX for serial communication</li>
  <li><b>I2C</b> – I2C1_SCL, I2C1_SDA for sensor and peripheral interfacing</li>
  <li><b>SWD</b> – Serial Wire Debug (PA13, PA14) for programming and debugging</li>
</ul>
These headers simplify firmware upload and real-time debugging using ST-Link or similar tools.
</p>

<hr>

<h2>💻 KiCad Project Workflow</h2>
<p>
The PCB was designed in <b>KiCad</b> following standard embedded design practices. ERC (Electrical Rules Check) and DRC (Design Rules Check) were performed to ensure design integrity before Gerber generation.
</p>

<ul>
  <li><b>ERC:</b> Validates schematic-level connections and symbol consistency.</li>
  <li><b>DRC:</b> Checks trace clearances, copper spacing, and via placements.</li>
  <li><b>Gerber Files:</b> Generated for manufacturing and fabrication verification.</li>
</ul>

<hr>

<h2>🧠 Learnings</h2>
<p>
This project helped reinforce key embedded hardware design concepts:
<ul>
  <li>Understanding STM32 power domains (VDD, VDDA, VBAT)</li>
  <li>Implementing decoupling and bulk capacitors for stable operation</li>
  <li>Applying ferrite beads for analog noise isolation</li>
  <li>Routing differential USB pairs in KiCad</li>
  <li>Debugging using SWD and BOOT0 configuration</li>
  <li>Generating and verifying ERC/DRC-compliant Gerber files</li>
</ul>
It also provided insight into the workflow of transforming a schematic into a professional-grade PCB suitable for embedded applications.
</p>

<hr>

<h2>📷 Project Images</h2>
<h3>🔹 Schematic Design</h3>
<img src="https://github.com/utkarsh-kumar4/STM32F103C8T6-PCB-in-KiCad/blob/main/Schematic%20Design.png">

<h3>🔹 PCB Layout</h3>
<img src="https://github.com/utkarsh-kumar4/STM32F103C8T6-PCB-in-KiCad/blob/main/PCB%20Layout.png">

<h3>🔹 3D Board View</h3>
<img src="https://github.com/utkarsh-kumar4/STM32F103C8T6-PCB-in-KiCad/blob/main/3D%20Board%20View.png">

## Author 👤
[Utkarsh Kumar](https://github.com/utkarsh-kumar4) 👨🏻‍💻🎓
