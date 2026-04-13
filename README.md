# GuardLogix-Safety-PLC-Program
GuardLogix safety PLC program with ESTOP, light curtain, safety door, and two-hand control using safety task architecture.


This project demonstrates a GuardLogix safety PLC application built in Studio 5000 using a dedicated Safety Task and Standard Task architecture.
-----------------------------------------------------------------------------------------------------------------------------------------------
The system simulates a guarded machine with:

Emergency Stop
Safety Light Curtain
Safety Door Switch
Two-Hand Control Station
Manual Safety Reset
Safe Run Permit
Standard Machine Control Logic

-----------------------------------------------------------------------------------------------------------------------------------------------
Safety Inputs
   ├── ESTOP
   ├── Light Curtain (DCS)
   ├── Safety Door (DCS)
   └── Two-Hand Control (THRSe)
        │
        ▼
   Safety Chain Validation
        │
        ▼
   Manual Reset Logic
        │
        ▼
   Safe Run Permit
        │
        ▼
   Standard Machine Control

-----------------------------------------------------------------------------------------------------------------------------------------------

   Controller
├── Standard_Task
│   └── Std_Program
│       └── Std_Main_LAD
│
└── Safety_Task
    └── Safety_Program
        └── Safe_Main_LAD
-----------------------------------------------------------------------------------------------------------------------------------------------

Safety Routine Overview
Rung 0 — ESTOP

Dual channel emergency stop monitoring

Rung 1 — Light Curtain (DCS)

Dual channel light curtain validation

Rung 2 — Safety Door (DCS)

Dual channel safety gate monitoring

Rung 3 — Two-Hand Enable

Enable two-hand control when safety OK

Rung 4 — Two-Hand (THRSe)

Two-hand validation with discrepancy timing

Rung 5 — Safety Chain

Combine all safety outputs

Rung 6 — Manual Reset

Operator reset after safety trip

Rung 7 — Safe Run Permit

Final permission for machine operation

-----------------------------------------------------------------------------------------------------------------------------------------------

Two-Hand Control Configuration

Instruction: THRSe

Discrepancy Time: 500 ms
Enable: S_TwoHand_Enable
Left Button: S_TH_LeftPB
Right Button: S_TH_RightPB
Reset: S_TH_ResetPB
Output: S_TH_OK

Both buttons must be pressed within 500 ms.

-----------------------------------------------------------------------------------------------------------------------------------------------

Light Curtain Configuration

Instruction: DCS

Input Type: Equivalent Active High
Restart Type: Automatic
Discrepancy Time: 100 ms

Dual channel OSSD simulation.
-----------------------------------------------------------------------------------------------------------------------------------------------

Signal Flow:
Safety Devices
     ↓
Safety Instructions
     ↓
Safety Chain
     ↓
Manual Reset
     ↓
Safe Run Permit
     ↓
Standard Machine Logic
     ↓
Machine Outputs

-----------------------------------------------------------------------------------------------------------------------------------------------
Skills Demonstrated:

GuardLogix Safety Programming
Safety Task Architecture
ESTOP Safety Instruction
DCS Light Curtain Monitoring
Safety Door Monitoring
THRSe Two-Hand Control
Manual Reset Logic
Safe Run Permit Design
Standard vs Safety Separation
Industrial Machine Safety Design

-----------------------------------------------------------------------------------------------------------------------------------------------

Industrial Applications:

This safety architecture applies to:

Robot cells
Press stations
Assembly machines
Packaging equipment
CNC guarding
Automated workcells

-----------------------------------------------------------------------------------------------------------------------------------------------
Author[Daryl Sanders]
GuardLogix Safety PLC Portfolio Project
Studio 5000 Logix Designer
