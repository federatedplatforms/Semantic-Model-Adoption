# Air Waybill (AWB) Examples

An **Air Waybill (AWB)** is the primary transport document in air freight, issued by or on behalf of a carrier. It serves as a contract of carriage between the shipper and the airline, a receipt for the goods, and a certificate of insurance if applicable. Under the IATA standard, two distinct levels of AWB are defined depending on the role of the issuing party in the shipment chain.

## Master Air Waybill (MAWB)

The **Master Air Waybill (MAWB)** is issued by the **airline (carrier)** or its ground handling agent. It governs the contractual relationship between the airline and the freight forwarder (consolidator) who has booked cargo space on the aircraft. Key characteristics:

- Issued by the **main carrier** (e.g., an IATA-certified airline).
- Covers the **consolidated shipment** as a whole — i.e., multiple individual consignments grouped by a freight forwarder may appear under a single MAWB.
- The MAWB number follows the IATA format: a **3-digit airline prefix** followed by an **8-digit serial number** (e.g., `020-12345678` for Lufthansa).
- The freight forwarder is listed as the **shipper**, and the destination agent or forwarder is listed as the **consignee**.
- The MAWB is the document that airlines use for customs and cargo tracking across the entire flight segment.

## House Air Waybill (HAWB)

The **House Air Waybill (HAWB)** is issued by a **freight forwarder** or **Non-Vessel Operating Common Carrier (NVOCC)** to their individual customers. It governs the relationship between the forwarder and the actual shipper of a specific consignment within a consolidated shipment. Key characteristics:

- Issued by the **freight forwarder**, not the airline.
- Covers an **individual consignment** within a consolidated load that travels under a single MAWB.
- The HAWB number is assigned by the forwarder and does not follow a standardised IATA format, though many forwarders adopt similar conventions.
- The actual **shipper and consignee** of the goods are named on the HAWB.
- HAWBs are used for inland delivery, customs clearance at destination, and proof of receipt by the consignee.

## Relationship between MAWB and HAWB

In a consolidated air freight shipment, multiple HAWBs are grouped under a single MAWB:

```
MAWB (issued by airline)
 └── HAWB 1 (consignment from Shipper A → Consignee A)
 └── HAWB 2 (consignment from Shipper B → Consignee B)
 └── HAWB N (...)
```

A direct shipment (where the forwarder acts purely as agent) may have only a MAWB with no underlying HAWBs.

## Reference JSON Schemas

The following JSON schema files are included in this folder as **reference points only**. They are sourced from external collaborators and illustrate how AWB data may be structured in practice. They are not normative definitions of the FEDeRATED Semantic Model.

| File | Description |
|---|---|
| [Example external (M)AWB schema.json](./Example%20external%20(M)AWB%20schema.json) | Example schema for a Master Air Waybill, provided by an external collaborator. |
| [Example external HAWB schema.json](./Example%20external%20HAWB%20schema.json) | Example schema for a House Air Waybill, provided by an external collaborator. |

These schemas can be used as a starting point when mapping external data sources to the FEDeRATED Semantic Model, but the canonical representation is defined by the ontology modules in the [Ontology/](../../../Ontology/) folder.
