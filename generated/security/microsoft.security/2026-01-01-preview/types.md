# Microsoft.Security @ 2026-01-01-preview

## Resource Microsoft.Security/defenderForStorageSettings@2026-01-01-preview
* **Valid Scope(s)**: Unknown
### Properties
* **apiVersion**: '2026-01-01-preview' (ReadOnly, DeployTimeConstant): The resource api version
* **id**: string (ReadOnly, DeployTimeConstant): The resource id
* **name**: 'MCAS' | 'Sentinel' | 'WDATP' | 'WDATP_EXCLUDE_LINUX_PUBLIC_PREVIEW' | 'WDATP_UNIFIED_SOLUTION' | 'current' | string (Required, DeployTimeConstant): The resource name
* **properties**: [DefenderForStorageSettingProperties](#defenderforstoragesettingproperties): Defender for Storage resource properties.
* **systemData**: [SystemData](#systemdata) (ReadOnly): Azure Resource Manager metadata containing createdBy and modifiedBy information.
* **type**: 'Microsoft.Security/defenderForStorageSettings' (ReadOnly, DeployTimeConstant): The resource type

## CommonOperationStatus
### Properties
* **code**: string: The operation status code.
* **message**: string: Additional information regarding the success/failure of the operation.

## DefenderForStorageSettingProperties
### Properties
* **isEnabled**: bool: Indicates whether Defender for Storage is enabled on this storage account.
* **malwareScanning**: [MalwareScanningProperties](#malwarescanningproperties): Properties of Malware Scanning.
* **overrideSubscriptionLevelSettings**: bool: Indicates whether the settings defined for this storage account should override the settings defined for the subscription.
* **sensitiveDataDiscovery**: [SensitiveDataDiscoveryProperties](#sensitivedatadiscoveryproperties): Properties of Sensitive Data Discovery.

## MalwareScanningProperties
### Properties
* **automatedResponse**: 'BlobSoftDelete' | 'None' | string: Optional. Specifies the automated response action to take when malware is detected.
* **blobScanResultsOptions**: 'BlobIndexTags' | 'None' | string: Optional. Write scan result on BlobIndexTags by default.
* **onUpload**: [OnUploadProperties](#onuploadproperties): Properties of On Upload malware scanning.
* **operationStatus**: [CommonOperationStatus](#commonoperationstatus) (ReadOnly): Upon failure or partial success. Additional data describing Malware Scanning enable/disable operation.
* **scanResultsEventGridTopicResourceId**: string: Optional. Resource id of an Event Grid Topic to send scan results to.

## OnUploadFilters
### Properties
* **excludeBlobsLargerThan**: any: Optional. Specifies the maximum size in bytes for blobs to be scanned. This parameter accepts a single positive integer value. Blobs larger than this value will be excluded from scanning.
* **excludeBlobsWithPrefix**: string[]: Optional. A list of prefixes to exclude from on-upload malware scanning.
Format: `container-name/blob-name` (start with the container name; do not include the storage account name).
Exclude entire containers: Use prefix of container names you want to exclude without a trailing `/`.
Exclude a single container: Add a trailing slash `/` after the container name to avoid excluding other containers with similar prefixes.
* **excludeBlobsWithSuffix**: string[]: Optional. A list of suffixes to exclude from on-upload malware scanning. Suffixes match only the end of blob names, and should be used for file extensions or blob name endings only.

## OnUploadProperties
### Properties
* **capGBPerMonth**: int: Defines the max GB to be scanned per Month. Set to -1 if no capping is needed. If not specified, the default value is -1.
* **filters**: [OnUploadFilters](#onuploadfilters): Optional. Determine which blobs get scanned by On Upload malware scanning. An Or operation is performed between each filter type.
* **isEnabled**: bool: Indicates whether On Upload malware scanning should be enabled.

## SensitiveDataDiscoveryProperties
### Properties
* **isEnabled**: bool: Indicates whether Sensitive Data Discovery should be enabled.
* **operationStatus**: [CommonOperationStatus](#commonoperationstatus) (ReadOnly): Upon failure or partial success. Additional data describing Sensitive Data Discovery enable/disable operation.

## SystemData
### Properties
* **createdAt**: string: The timestamp of resource creation (UTC).
* **createdBy**: string: The identity that created the resource.
* **createdByType**: 'Application' | 'Key' | 'ManagedIdentity' | 'User' | string: The type of identity that created the resource.
* **lastModifiedAt**: string: The timestamp of resource last modification (UTC)
* **lastModifiedBy**: string: The identity that last modified the resource.
* **lastModifiedByType**: 'Application' | 'Key' | 'ManagedIdentity' | 'User' | string: The type of identity that last modified the resource.

