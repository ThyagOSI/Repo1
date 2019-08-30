---
uid: restRequestReference
---

# `REST request reference`

The following REST requests can be used for configuring the Edge Data Store, Edge Adapters (including Modbus TCP connectivity and OPC UA connectivity), and Storage.

| **Endpoint**          | **HTTP Method**    | **Description** |
|-------------------|----------------|-------------|
| `http://localhost:5590/api/v1/configuration` | GET | Get all components configurations in Edge System|
| **System Routes** |  |  |
| `http://localhost:5590/api/v1/configuration/System/Logging`  | GET | Get logging configuration for the Edge System |
| | PUT | Replace logging configuration for the Edge Data Store |
| **Diagnostics** | | |
| `http://localhost:5590/api/v1/Diagnostics/System`  | GET |Retrieve current system level diagnostics information |
| `http://localhost:5590/api/v1/Diagnostics/ProductInformation` | GET |Retrieve current product information |
| **Component Configuration** | | |
| `http://localhost:5590/api/v1/configuration/<ComponentId>`  | GET | Get all configurations for the ComponentId |
| `http://localhost:5590/api/v1/configuration/<ComponentId>/DataSource`  | GET |Get data source configuration of Adapter component |
| | POST | Create data source configuration for Adapter component |
| | PUT | Replace data source configuration for Adapter component |
| | DELETE | Delete data source configuration for Adapter component |
| `http://localhost:5590/api/v1/configuration//<ComponentId>/DataSelection`  | GET | Get data selection configuration of Adapter component |
| | POST | Create data selection configuration for Adapter component |
| | PUT | Replace data selection configuration for Adapter component |
| | DELETE | Delete data selection configuration for Adapter component |
| `http://localhost:5590/api/v1/configuration/{ComponentId}/Logging`  | GET | Get logging configuration of Adapter component |
| | PUT | Replace logging configuration for Adapter component |
| **Periodic Egress Endpoints** | | |
| `http://localhost:5590/api/v1/configuration/Storage/PeriodicEgressEndpoints` | GET | Get all periodic egress targets |
| | POST | Creates egress endpoints if not present, otherwise fails |
| | PUT | Replaces all egress endpoints |
| | DELETE | Deletes all egress endpoints |
| `http://localhost:5590/api/v1/configuration/Storage/PeriodicEgressEndpoints/{Id}` | GET | Get an individual periodic egress endpoint |
| | PUT | Replaces periodic egress endpoint |
| | DELETE | Deletes periodic egress endpoint |
| **Storage Runtime** | | |
| `http://localhost:5590/api/v1/configuration/Storage/Runtime` | GET | Get Runtime Configuration for Edge Storage - stream limits and Ingress debug |
| | PUT | Replace Runtime Configuration to Edge Storage - stream limits and egress debug |
| **Systeminfo** | | |
| `http://localhost:5590/api/v1/Systeminfo/Storage` | GET | Get Stream Count, Type Count, and View Count |

## Note:
The difference between the POST and the PUT method is that POST allows to create a
configuration and PUT replaces a configuration. If you use POST on an existing
configuration, the request will fail.
