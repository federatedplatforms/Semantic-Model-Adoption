# Cargo iQ Milestone Catalogue and Event Responsibility Chain
**Source:** Cargo iQ Master Operating Plan (MOP) v3.4, 9 May 2022

## Overview

Cargo iQ defines:

> "Milestone = Name for a planned time by which related event(s) should happen"

and

> "KPI: Cargo iQ measure by which the performance of the milestone should be evaluated"

The MOP defines an end-to-end shipment lifecycle from shipper to consignee covering:

1. Origin Forwarder Activities
2. Origin Carrier Activities
3. Transport Activities
4. Destination Carrier Activities
5. Destination Forwarder Activities

## Relevant for FEDeRATED

Not all the milestones are required to be reported. In the previous pilots only the milestones **ARR, BKD, BSL, CF, DECL, DEP, DLV, FHL, FIW, FOH, FOW, FWB, MAN, NFD, RCS, and RFT** have been used.

Only the description of these milestones is provided, while the end-to-end event chain contains the other milestones as well.

All the milestone events represent a Freight Status Update (FSU) and all point to the same JSON schema and RML

---

# End-to-End Event Chain

```text
SHIPPER
  ↓
FORWARDER (Origin)
  BKD → PUP → REW → DEW → REH → DEH
  ↓
FORWARDER → CARRIER
  FWB → DOC
  ↓
CARRIER (Origin)
  FOH/LAT → RCS
  ↓
CARRIER (Transport)
  FOW → DEP → ARR → FIW → RCF/AWR
  ↓
CARRIER (Destination)
  NFD → TOA → AWD → DLV
  ↓
FORWARDER (Destination)
  RIH → DIH → RIW → TPN
  ↓
   ├─ Airport Pickup: SPC/HDP
   └─ Door Delivery: OFD → POD
```

---

# Event Catalogue

## BKD - Booked

### Responsible Actor
Carrier

### Description

Carrier confirms requested capacity and initiates route-map creation.

### Status Change

```text
Booked
```

### Process

```text
P01 Book & Plan Shipments
```

---

## FWB - Electronic Master Air Waybill Sent

### Responsible Actor

Forwarder

### Description

Shipment information transmitted electronically to carrier and authorities.

### Status Change

```text
Forwarder's Electronic (Master) Air Waybill transmitted to carrier
```

---

# Origin Carrier Events

## FOH - Freight on Hand

### Responsible Actor

Carrier / Ground Handling Agent (GHA)

### Description

Freight unloaded from accepted truck or transfer vehicle and is physically under carrier control.

### Status Change

```text
Freight on Hand
```

### Custody Transfer

```text
Forwarder → Carrier
```

---

## RCS - Ready for Carriage

### Responsible Actor

Carrier

### Description

Carrier validates:

- Security requirements
- Customs requirements
- Booking information
- Weight
- Dimensions
- Documentation

Shipment is formally accepted for carriage.

### Status Change

```text
Ready for Carriage
```

---

# Transport Events

## FOW - Freight Out of Warehouse

### Responsible Actor

Carrier Warehouse / GHA

### Description

Freight moves from warehouse control to ramp control.

### Status Change

```text
Freight Out from Warehouse Control
```

---

## DEP - Departure

### Responsible Actor

Operating Carrier

### Description

Aircraft departs.

Wheels-up time captured.

Movement message transmitted.

### Status Change

```text
Departure of Shipment on Flight
```

---

## ARR - Arrival

### Responsible Actor

Operating Carrier

### Description

Aircraft arrives.

On-block and arrival times captured.

Movement message transmitted.

### Status Change

```text
Arrival of Shipment on Flight
```

---

## FIW - Freight Into Warehouse

### Responsible Actor

Carrier Warehouse / GHA

### Description

Freight transferred from ramp control into warehouse control.

### Status Change

```text
Freight Into Warehouse Control
```

---

## TOA - Time of Availability

### Responsible Actor

Carrier

### Description

Expected shipment availability for pickup.

Cargo iQ introduced TOA to support paperless destination handover processes.

---

## AWD = DECL - Documents Available

### Responsible Actor

Carrier

### Description

Paper or electronic shipment documentation made available.

### Status Change

```text
Document / Data Handover at Destination
```

---

## DLV - Delivered to Forwarder

### Responsible Actor

Carrier

### Description

Freight physically handed over to destination forwarder.

Driver acknowledges receipt.

### Status Change

```text
Delivery of Freight at Destination
```

### Custody Transfer

```text
Carrier → Forwarder
```

---


# Responsibility Matrix

| Event | Responsible Actor |
|---------|---------|
| BKD | Carrier |
| RMI | Forwarder |
| RMP | CDMP-C / CDMP-F |
| PUP | Forwarder |
| REW | Forwarder |
| DEW | Forwarder |
| REH | Forwarder |
| DEH | Forwarder |
| FWB | Forwarder |
| DOC | Forwarder |
| FOH | Carrier / GHA |
| LAT | Carrier |
| RCS | Carrier |
| RCT | Carrier |
| FOW | Carrier / GHA |
| DEP | Carrier |
| ARR | Carrier |
| FIW | Carrier / GHA |
| RCF | Carrier / GHA |
| AWR | Carrier |
| TFD | Carrier |
| NFD | Carrier / GHA |
| TOA | Carrier |
| AWD | Carrier |
| DLV | Carrier |
| RIH | Forwarder |
| DIH | Forwarder |
| RIW | Forwarder |
| TPN | Forwarder |
| SPC | Forwarder |
| HDP | Forwarder |
| OFD | Forwarder |
| POD | Forwarder |

---

# Custody Transfer Summary

```text
Shipper
  │
  └── PUP
        ↓
Forwarder
  │
  └── FOH
        ↓
Carrier
  │
  ├── TFD (optional)
  │       ↓
  │   Another Carrier
  │
  └── DLV
        ↓
Forwarder
  │
  ├── SPC/HDP
  │       ↓
  │   Consignee
  │
  └── POD
          ↓
      Consignee
```

---

# Source

Cargo iQ Master Operating Plan (MOP) v3.4  
International Air Transport Association (IATA) Cargo iQ  
Version dated 9 May 2022.