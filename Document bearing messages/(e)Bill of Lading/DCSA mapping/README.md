# DCSA eBL Mapping Examples

This folder contains standard example JSON payloads from the [DCSA eBL API](https://dcsa.org/standards/ebill-of-lading/) used as reference inputs for mapping to the FEDeRATED Semantic Model.

## GET Shipping Instructions – STD Example

### Overview

The file [`GET Shipping Instructions STDExample.json`](./GET%20Shipping%20Instructions%20STDExample.json) represents a response from the DCSA eBL `GET /v3/shipping-instructions/{documentReference}` endpoint. It contains the shipper's declared cargo details, party information, consignment items, and transport document type before a transport document has been issued.

### Mapping of relevant attributes:


| DCSA | FEDeRATED |
|----------|----------|
| partyContactDetails    | Actor<br>actorRole = "issuingParty"    |
| |
| documentParties.shipper | Actor<br>actorRole = "shipper" |
| |
| utilizedTransportEquipments | Equipment |
| .equipmentReference | equipmentTypeCode |
| seals.number | sealNumber |
| |
| consignmentItems | PiecesGoods |
| .descriptionOfGoods | .goodsDescription |
| .HSCodes | .ExternalIdentifier <br> *externalIdentifierDescription* = "HSCode" & *externalIdentifierValue*
| |
| consignmentItems.cargoItems | Equipment.involvesGoods |
| .cargoGrossWeight.value |  .weightValue <br> .weightDescription = "Gross" |
| .cargoGrossWeight.unit | .weightUnitOfMeasure |
| |
| consignmentItems.outerPackaging.numberOfPackages | PiecesGoods.numberOfPackages |
| consignmentItems.outerPackaging.packageCode | PiecesGoods.packageCode |
| consignmentItems.outerPackaging.description | PiecesGoods.packageTypeName |



## GET Transport Documents – STD Example

### Overview

The file [`GET Transport Documents STDExample.json`](./GET%20Transport%20Documents%20STDExample.json) represents a response from the DCSA eBL `GET /v3/transport-documents/{transportDocumentReference}` endpoint. It contains the issued transport document reference, routing details (port of loading, port of discharge, vessel voyage), charges, and the full terms and conditions associated with the Bill of Lading.
