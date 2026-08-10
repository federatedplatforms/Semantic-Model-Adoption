# Overview of Example Message Models

This directory contains example message models used in the FEDeRATED Semantic Model. The examples are divided into two categories: **Document Bearing Messages** and **Track & Trace Messages**. Understanding the distinction between these two types is essential for correctly modelling logistics data exchanges.

- [Document Bearing Messages](Document%20bearing%20messages/)
- [Track & Trace Messages](Track%20%26%20Trace%20messages/)

## Document Bearing Message Models

Document bearing message models represent the initial introduction of logistic data objects into the information space. These messages carry the substantive content of a logistics process by defining and registering new data entities, such as:

- **Transport Means** — the vehicles, vessels, aircraft, or other conveyances involved in the movement of goods.
- **Cargo** — the goods or consignments being transported, including descriptions, quantities, and packaging.
- **Legal Persons** — the parties involved in the logistics chain, such as shippers, consignees, freight forwarders, and carriers.
- **Locations** — the origin, destination, and intermediate points relevant to the logistics process.

Examples of document bearing messages include Air Waybills (AWB/HAWB/MAWB), Shipping Orders, Purchase Orders, and Container Loading instructions. Each of these messages establishes the existence of one or more data objects and defines their properties for the first time within a given logistics flow.

## Track & Trace Message Models

Track & Trace message models do not introduce new data objects. Instead, they update the state of already-existing logistic steps (as defined by a document bearing message) by recording **timestamps and milestones**. These messages answer questions such as:

- When did a transport means depart or arrive?
- When was cargo loaded, unloaded, or inspected?
- Which milestone in the logistics process has been reached, and at what time?

Track & Trace messages reference the data objects established by document bearing messages and enrich them with event-time information. They are essential for real-time visibility and status monitoring across the supply chain.

## Summary

| Aspect | Document Bearing | Track & Trace |
|---|---|---|
| Introduces new data objects | Yes | No |
| Updates timestamps / milestones | No | Yes |
| Examples | AWB, Shipping Order, Purchase Order | Departure event, Arrival event, Milestone update |

In short: a **document bearing message** defines *what* exists in the logistics process, while a **track & trace message** records *when* something happened to it.

Sources (in progress):
1. UNCEFACT Multimodal Transport Reference Data Model (MMT RDM): https://service.unece.org/trade/uncefact/publication/Transport-Logistics/MMT-RDM/HTML/001.htm
2. UNCEFACT Supply Chain Reference Data Model (SCRDM): https://service.unece.org/trade/uncefact/publication/SupplyChainMGMT/SCRDM/HTML/001.htm
3. DCSA Standards:

    a. Track & Trace - https://app.swaggerhub.com/apis/dcsaorg/DCSA_TNT/2.2.0

    b. Booking (mapped) - https://app.swaggerhub.com/apis/dcsaorg/DCSA_BKG/2.0.4

    c. Electronic Bill of Lading (mapped) - https://app.swaggerhub.com/apis-docs/dcsaorg/DCSA_EBL/3.0.3
    
    d. Arrival Notice - https://reference.dcsa.org/content/standards/releases/arrival-notice/v1-0-1/arrival-notice-v1-0-1-data-overview#excel-file

    e. Verified Gross Mass - https://reference.dcsa.org/content/standards/releases/verified-gross-mass/v1-0-1/verified-gross-mass-v1-0-1-data-overview

    f. Port Call - https://reference.dcsa.org/content/standards/releases/port-call/v2-0-0/port-call-v2-0-0-data-overview

    g. Operational Vessel Schedules - https://app.swaggerhub.com/apis/dcsaorg/DCSA_OVS/3.0.2
4. Open Trip Model (mapped) - https://otm-api-spec.redocly.app/api/5.8/otm
5. IATA (mapped) - https://github.com/IATA-Cargo/ONE-Record/tree/master
6. FIATA - Freight forwarding and multimodal transport documentation - https://github.com/FIATA/eFBL/tree/main
7. ERA Telematics-TSI - https://gitlab.com/era-europa-eu/public/era-telematics-tsi
8. World Customs Organization - https://www.wcoomd.org/DataModel

