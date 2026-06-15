# -SmartUniversity-Lab-Resource-Management-System
Digital Logic Design Project | Proteus Simulation

---

## PROJECT OVERVIEW

Designed and simulated a complete Smart University Lab Resource Management System in Proteus using real digital ICs. The system manages lab resources intelligently using combinational and sequential logic circuits — without any microcontroller or software.

---

## PURPOSE / PROBLEM STATEMENT

A university lab has limited resources (computers, projectors, equipment). This system:
- Monitors availability of lab resources
- Controls access based on priority
- Displays status using output indicators
- Manages timing and counting of resource usage

---

## ICs USED & THEIR ROLE

| IC | Name | Role in Project |
|---|---|---|
| NE555 | Timer IC | Generates clock pulses for the counting circuit |
| 74LS93 | 4-bit Binary Counter | Counts resource usage / time slots |
| 74LS193 | Up/Down Counter | Tracks available vs used resources |
| 74LS153 | Dual 4:1 MUX | Selects which resource signal to monitor |
| 74LS148 | 8:3 Priority Encoder | Encodes highest priority resource request |
| 74LS279 | SR Latch | Stores state of resource (occupied/free) |
| LM339 | Voltage Comparator | Compares sensor input to decide resource state |
| 74LS138 | 3:8 Decoder | Activates specific resource output line |
| 74LS139 | Dual 2:4 Decoder | Secondary decoding for resource selection |

---

## HOW THE SYSTEM WORKS (Step by Step)

**STEP 1 — Clock Generation**
NE555 timer generates a continuous clock signal that drives the counting circuits.

**STEP 2 — Resource Request Detection**
When a student requests a resource, the 74LS148 Priority Encoder encodes the highest priority request into a 3-bit binary code.

**STEP 3 — Resource Selection**
74LS153 MUX uses the encoded signal to select which resource line to activate.

**STEP 4 — Resource State Storage**
74LS279 SR Latches store whether each resource is FREE or OCCUPIED. LM339 Comparator checks sensor voltage to confirm physical availability.

**STEP 5 — Resource Allocation**
74LS138 / 74LS139 Decoders activate the exact output line for the allocated resource.

**STEP 6 — Usage Counting**
74LS193 Up/Down Counter tracks how many resources are in use vs available. 74LS93 counts total usage time slots.

---

## CIRCUITS / CONCEPTS IMPLEMENTED

- MUX (Multiplexer) — 74LS153: Resource signal selection
- DEMUX (Demultiplexer) — 74LS138/74LS139: 1×16 DEMUX built hierarchically
- Priority Encoder — 74LS148: 8:3 encoding of resource requests
- SR Latch — 74LS279: State storage (free/occupied)
- MOD Counter — 74LS93 + 74LS193: Usage tracking
- Voltage Comparator — LM339: Analog threshold detection
- BCD Adder — 7483 IC: Floor/resource number addition
- Combinational Logic — AND/OR/NOT gates for control logic

---

## TOOLS USED

- Proteus Design Suite — Full circuit simulation
- 74LS Series ICs — Digital logic family
- LM339 — Analog comparator IC
