## Buffering Configuration
***Note***
This section talks about the global parameters used for on-disk buffering configuration. For enabling or disabling buffering at the individual egress endpoint level using the *bufferingEnabled* field please refer to: <</INSERT LINK HERE>>

The parameters for on-disk buffering for the adapters that can be configured are
- OnDiskMaxBufferSizeMB
- OnDiskBufferLocation

| Parameter                       | Required | Type      | Description   |

| OnDiskMaxBufferSizeMB           | Yes      | Integer   | This parameter defines the maximum size of the buffer file that will be persisted on disk. The unit is specified in MB (Mebibyte 1 MiB = 1048576 bytes). The capacity and type of the storage medium must be taken into account before determining an alternate value for this parameter.
If you do not want to specify the any maximum file size then a value of -1 indicates that the buffer size is restricted only by the available free disk space.
          |

OnDiskBufferLocation
|   

### OnDiskMaxBufferSizeMB
```
Type: Integer

Allowed values: -1 or [1, 2147483647]  

Default: -1
```
This parameter defines the maximum size of the buffer file that will be persisted on disk. The unit is specified in MB (Mebibyte 1 MiB = 1048576 bytes). The capacity and type of the storage medium must be taken into account before determining an alternate value for this parameter.
If you do not want to specify the any maximum file size then a value of -1 indicates that the buffer size is restricted only by the available free disk space.

### OnDiskBufferLocation
```
Type: String

Allowed Value: Path to an existing folder location in the file system

Default:  %ProgramData%\Adapters\Data (Windows OS)

         /usr/share/OSIsoft/Adapters/Data (Linux OS)
```
This parameter defines the location where the data buffer file(s) will be created for the Adapter. A valid location for the file(s) must exist on the file system when specifying the parameter. Parameter takes effect only during startup.

***Note***
It is strongly recommended *against modifying* the default buffer location value.

### Retrieving the buffering configuration via REST client
```
curl -X GET  http://localhost:{port}/api/v1/configuration/egress/buffering
```
Sample output:

```
{
    "onDiskBufferLocation": "C:\\ProgramData\\OSIsoft\\Adapters\\Data",
    "onDiskMaxBufferSizeMB": 10
}
```

### Configuring buffer via REST client
```
curl -X PUT  http://localhost:{port}/api/v1/configuration/egress/buffering  -H 'Content-Type: application/json' -d '{ "onDiskMaxBufferSizeMB": 25,
"onDiskBufferLocation": "C:\\ProgramData\\OSIsoft\\Data"
}'
```
In the above samples *port* refers to configured port for the Adapter to run.
