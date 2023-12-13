# IS-04 interactions

The API availability MUST be advertised through existing IS-04 practices inside the controls array of an NMOS Device. Devices MUST include the `urn:x-nmos:control:configuration` control type.

```json
{ 
  ...
    "senders": [
        "a65c15a4-a52e-4960-8cd2-e05c31196e5f",
        "68f519a3-5523-4b2c-b72d-ec23cc80207d"
    ],
    "receivers": [
        "8a7bb1c1-4a82-4fd9-a4fb-96f68f560831",
        "ab450c07-ce54-44da-9ea9-c3e62e7b06d0"
    ],
    "controls": [
        {
            "type": "urn:x-nmos:control:configuration/v1.0",
            "href": "http://192.168.10.3/x-nmos/configuration/v1.0/"
        }
    ],
    "tags": {},
    "type": "urn:x-nmos:device:generic",
    "label": "NMOS Device",
    "version": "1529676926:000000000",
    "node_id": "d1713110-7343-4d9e-b3f4-456c8f6ce765",
    "id": "58f6b536-ca4c-43fd-880a-9df2501fc125",
    "description": "NMOS Device"
  ...
}
```

A given instance of the Configuration API MAY offer control of multiple Devices in a Node from a single URI. Alternatively there MAY be multiple instances of the API on one Node, for example, each corresponding to one Device.
In either case, the ‘control’ endpoint for each Device’s Configuration API instance MUST be advertised, even if the URI is the same.

This flexibility is to accommodate different relationships between Devices and Nodes. For example, some Devices may be loosely coupled to the Node, for example cards in a card frame.
These Devices are more likely to have an instance of the API for each card.
Others may be tightly coupled, for example a media processing pipeline on a server, where it is likely to be preferable to have one instance of the API that is advertised for each pipeline.

`TODO`: decide on `href` format and trailing slashes
