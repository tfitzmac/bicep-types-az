# Microsoft.Security @ 2026-01-01-preview

## Resource Microsoft.Security/defenderForStorageSettings@2026-01-01-preview
* **Valid Scope(s)**: Unknown
### Properties
* **apiVersion**: '2026-01-01-preview' (ReadOnly, DeployTimeConstant): The resource api version
* **id**: string (ReadOnly, DeployTimeConstant): The resource id
* **name**: string {pattern: "^current$"} (Required, DeployTimeConstant): The resource name
* **properties**: [DefenderForStorageSettingProperties](#defenderforstoragesettingproperties): Defender for Storage resource properties.
* **systemData**: [SystemData](#systemdata) (ReadOnly): Azure Resource Manager metadata containing createdBy and modifiedBy information.
* **type**: 'Microsoft.Security/defenderForStorageSettings' (ReadOnly, DeployTimeConstant): The resource type

## Resource Microsoft.Security/defenderForStorageSettings/malwareScans@2026-01-01-preview (ReadOnly)
* **Valid Scope(s)**: Unknown
### Properties
* **apiVersion**: '2026-01-01-preview' (ReadOnly, DeployTimeConstant): The resource api version
* **id**: string (ReadOnly, DeployTimeConstant): The resource id
* **name**: string {pattern: "^(latest|[a-f0-9]{8}-[a-f0-9]{4}-[a-f0-9]{4}-[a-f0-9]{4}-[a-f0-9]{12})$"} (Required, DeployTimeConstant): The resource name
* **properties**: [MalwareScanProperties](#malwarescanproperties) (ReadOnly): The resource-specific properties for this resource.
* **systemData**: [SystemData](#systemdata) (ReadOnly): Azure Resource Manager metadata containing createdBy and modifiedBy information.
* **type**: 'Microsoft.Security/defenderForStorageSettings/malwareScans' (ReadOnly, DeployTimeConstant): The resource type

## BlobsScanSummary
### Properties
* **failedBlobsCount**: int: The number of failed blob scans.
* **maliciousBlobsCount**: int: The number of malicious blobs that were detected during the scan.
* **scannedBlobsInGB**: int: The number of gigabytes of data that were scanned.
* **skippedBlobsCount**: int: The number of blobs that were skipped.
* **totalBlobsScanned**: int: The total number of blobs that were scanned.

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

## FilesScanSummary
### Properties
* **failedFilesCount**: int: The number of failed file scans.
* **maliciousFilesCount**: int: The number of malicious files that were detected during the scan.
* **scannedFilesInGB**: int: The number of gigabytes of data that were scanned.
* **skippedFilesCount**: int: The number of files that were skipped.
* **totalFilesScanned**: int: The total number of files that were scanned.

## MalwareScanningProperties
### Properties
* **automatedResponse**: 'BlobSoftDelete' | 'None' | string: Optional. Specifies the automated response action to take when malware is detected.
* **blobScanResultsOptions**: 'BlobIndexTags' | 'None' | string: Optional. Write scan result on BlobIndexTags by default.
* **onUpload**: [OnUploadProperties](#onuploadproperties): Properties of On Upload malware scanning.
* **operationStatus**: [CommonOperationStatus](#commonoperationstatus) (ReadOnly): Upon failure or partial success. Additional data describing Malware Scanning enable/disable operation.
* **scanResultsEventGridTopicResourceId**: string: Optional. Resource id of an Event Grid Topic to send scan results to.

## MalwareScanProperties
### Properties
* **scanEndTime**: string: The time at which the scan has ended. Only available for a scan which has terminated.
* **scanId**: string: The identifier of the scan.
* **scanStartTime**: string: The time at which the scan had been initiated.
* **scanStatus**: 'Canceled' | 'Canceling' | 'Completed' | 'Failed' | 'InProgress' | 'Queued' | 'WaitingForCompletion' | string: A status code of the scan operation.
* **scanStatusMessage**: string: A description of the status of the scan.
* **scanSummary**: [ScanSummary](#scansummary): A summary of the scan results.

## OnUploadFilters
### Properties
* **excludeBlobsLargerThan**: int: Optional. Specifies the maximum size in bytes for blobs to be scanned. This parameter accepts a single positive integer value. Blobs larger than this value will be excluded from scanning.
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

## ScanSummary
### Properties
* **blobs**: [BlobsScanSummary](#blobsscansummary): A summary of the scan results of the blobs that were scanned.
* **estimatedScanCostUSD**: int: The estimated cost of the scan. Only available for a scan which has terminated.
* **files**: [FilesScanSummary](#filesscansummary): A summary of the scan results of the files that were scanned.

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

