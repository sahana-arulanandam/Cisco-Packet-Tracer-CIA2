# Cisco-Packet-Tracer-CIA2

# Design and Setup of a Solar-Powered Battery System in Cisco Packet Tracer

### Aim
To design and set up a battery system that charges using energy from a solar panel within Cisco Packet Tracer, simulating a sustainable power generation and storage solution for IoT-based applications.

### Problem Statement
The objective is to create a functional simulation of a renewable energy system where a solar panel generates electricity, which is measured and distributed by a power meter to charge a battery. The system should support connected loads (e.g., LEDs) and be monitored via a network infrastructure. Challenges include ensuring proper power flow, configuring network connectivity for IoT devices, and troubleshooting connectivity or power generation issues within the Packet Tracer environment.


### Scope of the Solution

The solution encompasses the following:

Simulation of a solar panel generating power based on environmental conditions (e.g., sunlight).
Integration of a power meter to measure and distribute energy to a battery.
Storage of generated power in a battery, with the ability to supply connected loads (LEDs).
Establishment of a network using a switch, server, and PC for device registration and monitoring.
Configuration of DHCP for automatic IP assignment to IoT and network devices.
Testing and validation of the system in Simulation Mode to ensure power flow and network connectivity.The solution is limited to Packet Tracer’s IoT and power grid capabilities, focusing on a basic smart grid setup without advanced programming or external integrations.

### Required Components

- PT-Solar Panel: Generates power from simulated sunlight (End Devices > Power Grid).
- PT-Battery: Stores energy received from the power meter (End Devices > Power Grid).
- PT-Power Meter: Measures and distributes power between the solar panel and battery (End Devices > Power Grid).
- LEDs (4x): Act as loads to draw power from the battery, demonstrating energy usage (End Devices > Components or Power Grid).
- Switch (e.g., 2960): Facilitates network connectivity for IoT and monitoring devices (Switches).
- Server: Provides DHCP services and hosts the IoT registration server for monitoring (End Devices).
- PC: Used for network monitoring via a web browser (End Devices).
- IoT Custom Cables: Connect power devices (e.g., solar panel to power meter, battery to LEDs) (Connections panel).
- Straight-Through Ethernet Cables: Connect network devices (e.g., server to switch, PC to switch) (Connections panel).

### Design and Setup Process

1. Workspace Setup:
- Open Cisco Packet Tracer and create a new project.
- Drag the required components to the workspace from their respective categories.


2. Power Connections:
- Connect the Solar Panel (Port D0) to the Power Meter (Port D0) using an IoT Custom Cable.
- Connect the Power Meter (Port D1) to the Battery (Port D0) using an IoT Custom Cable.
- Connect the Battery (Ports D1-D4) to the four LEDs using IoT Custom Cables.


3. Network Connections:
- Enable Ethernet ports on power devices:
	- Solar Panel: Add PT-IOT-NM-1C GE adapter (Config > I/O Config).
	- Power Meter and Battery: Add PT-IOT-NM-1C FE adapter (Config > I/O Config).


- Connect devices to the switch:
	- Solar Panel → Switch Port Fa0/3.
	- Power Meter → Switch Port Fa0/4.
	- Battery → Switch Port Fa0/5.
	- Server → Switch Port Fa0/1.
	- PC → Switch Port Fa0/2.

- Use Straight-Through Ethernet Cables for all network connections.

4. Configuration:
- Server Configuration:
	- Set Static IP: 1.0.0.1, Subnet Mask 255.255.255.0 (Config > FastEthernet0).
	- Enable DHCP (Services > DHCP): Pool Name IoTNetwork, Gateway 1.0.0.1, DNS 1.0.0.1, Start IP 1.0.0.2, Subnet Mask 255.255.255.0, Maximum Users 10.
- IoT Devices and PC:
	- Set IP to DHCP (Config > [Ethernet Port]) for Solar Panel, Power Meter, Battery, and PC.
- IoT Registration:
	- For each power device: Set IoT Server Address to 1.0.0.1, Username admin, Password admin (Config > Settings > IoT Server > Connect).

5. Simulation:
- Go to Physical Workspace, set Environment to sunny/daytime (e.g., 12:00 PM, clear weather).
- Switch to Simulation Mode, run the simulation, and observe power flow from the solar panel to the battery and LEDs.
- Monitor via PC web browser (Desktop > Web Browser, enter 1.0.0.1, login: admin/admin).

### Expected Outcome

- The solar panel generates power under sunny conditions, measured by the power meter.
- The battery charges and supplies power to the LEDs, which turn on.
- The network enables monitoring of device statuses via the server’s web interface.

### Conclusion
This setup demonstrates a functional solar-powered battery system within Packet Tracer, suitable for IoT simulations. Proper configuration of power and network components ensures a reliable energy flow and monitoring capability, aligning with the aim of the project.
