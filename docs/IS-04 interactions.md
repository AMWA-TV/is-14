# IS-04 interactions

The NMOS Device Configuration specification shares a data model with the NMOS IS-04 specification, and as a result is designed to be used alongside it.
The following implementation notes identify correct behavior for doing this.

When this API is used alongside IS-04 in a deployment, the IS-04 APIs SHOULD operate at version 1.1 or greater in order to ensure full interoperability.

## Discovery
The Configuration API MUST be advertised as a ‘control’ endpoint when publishing a compliant NMOS Device.
Control interfaces MUST use the URN `urn:x-nmos:control:configuration` to identify all Devices which implement the Configuration API, and the URLs required to access them.
For more details see [NMOS Device Control Types](https://specs.amwa.tv/nmos-parameter-registers/branches/main/device-control-types/).

**Example 1**: The ‘controls’ attribute of the NMOS Device of a simple Node with a single Configuration API instance.

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

**Example 2:** The 'controls' attribute of an NMOS Device of a Node which advertises a different Configuration API instance for each device.

```json
...
"controls": [
  {
    "type": "urn:x-nmos:control:configuration/v1.0",
    "href": "http://192.168.10.3/x-nmos/configuration/v1.0/slot2B/"
  }
]
...
```
In example 2, the path segment 'slot2B' is an `<api selector>` identifier as defined in [API Paths](APIs.md#api-paths).

**Note**: the API version is included in both the 'type', and in the 'href'.
As new versions of the Configuration API are published, further control endpoints may be advertised for Devices which support multiple versions simultaneously.
