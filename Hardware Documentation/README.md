
# Hardware Documentation

The following document describes the **Components and their Interactions**  before and after the Redesign of the Multicamera-Demonstrator to an Arduino-based Project. It's primarily meant as a guideline to enable the Development team **to implement cohesive and decoupled functions** for optimal code readability, reusability and debugging.

## Components before Redesign
### Component Signal Flowchart
```mermaid

graph TB

style A1 fill:#f9a,stroke:#333,stroke-width:4px
style B2 fill:#f9a,stroke:#333,stroke-width:4px
style A3 fill:#f9a,stroke:#333,stroke-width:4px

subgraph Train
A1[Train-µC] -- Direction, Speed --> B1[Engine Stepper Driver]
B1 -- Power -->C1[Train Engine]
A1 -- Position, Speed,Direction ---D1[Bluetooth-Module 1]
E1[LiPo Battery] -- Power -->A1
E1 -- Power -->B1
end

subgraph Station
A2[Power Supply] -- Power -->B2[EVA Board]
B2 -- Data Connection ---C2[PCB]
C2 -- Start -->D2[Cam - Trigger]
D2 -- Start -->E2[Laser - Linescanner]
C2 -- Color Red/Yellow -->F2[Traffic Light]
G2[Magnetic Field Sensor 1] -- Active/Inactive -->C2
H2[Magnetic Field Sensor 2] -- Active/Inactive -->C2
C2 -- Power -->I2[Halogen Lamp]
J2[Light Barrier] -- Active/Inactive -->C2
C2 -- Speed,Direction, Train Schedule -->K2[Bluetooth-Module 2]
end

subgraph PC
A3[PC] -- Active/Inactive --> B3[NIR - Cam]
A3 -- Active/Inactive --> C3[FIR - Cam]
A3 -- Active/Inactive --> D3[RGB - Cam]
A3 -- Picture Data -->E3[Display/GUI]
end

E2 -- Picture Data --> A3
D1-. Position, Speed,Direction .-K2

```
### Component List and Description (w\ Links)
#### Train
The Railcar housing these Components can be found under [3D-CAD Files](https://gitlab.tu-ilmenau.de/FakMB/QBV/systems/legocity/railroad-engine-3d-cad.git).

| Name  | Component | Description |
| ------------- | ------------- | ------------- |
| Train-µC  | -  | -  |
| Engine Stepper Driver  | -  | -  |
| Train Engine  | -  | -  |
| Bluetooth-Module 1  | -  | -  |
| LiPo Battery  | -  | -  |

#### Station

| Name  | Component | Description |
| ------------- | ------------- | ------------- |
| Power Supply  | -  | -  |
| EVA Board  | -  | -  |
| PCB  | -  | -  |
| Cam - Trigger  | -  | -  |
| LiPo Battery  | -  | -  |
| Laser - Linescanner  | -  | -  |
| Traffic Light  | -  | -  |
| Magnetic Field Sensor 1&2  | -  | -  |
| Halogen Lamp  | -  | -  |
| Light Barrier  | -  | -  |
| Bluetooth-Module 2  | -  | -  |

#### PC
| Name  | Component | Description |
| ------------- | ------------- | ------------- |
| PC  | -  | -  |
| NIR - Cam  | -  | -  |
| FIR - Cam  | -  | -  |
| RGB - Cam  | -  | -  |
| Display/GUI  | -  | -  |

### Current Pinout and Pin Requirements for the Redesign
## Components after Redesign