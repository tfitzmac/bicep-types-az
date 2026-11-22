# Microsoft.Sovereign @ 2026-10-31-preview

## Resource Microsoft.Sovereign/sovereignViews@2026-10-31-preview
* **Valid Scope(s)**: ResourceGroup
### Properties
* **apiVersion**: '2026-10-31-preview' (ReadOnly, DeployTimeConstant): The resource api version
* **id**: string (ReadOnly, DeployTimeConstant): The resource id
* **identity**: [SystemAssignedServiceIdentity](#systemassignedserviceidentity): The managed service identities assigned to this resource.
* **location**: string (Required): The geo-location where the resource lives
* **name**: string {pattern: "^[a-zA-Z0-9-]{3,64}$"} (Required, DeployTimeConstant): The resource name
* **properties**: [SovereignViewResourceProperties](#sovereignviewresourceproperties): The resource-specific properties for this resource.
* **systemData**: [SystemData](#systemdata) (ReadOnly): Azure Resource Manager metadata containing createdBy and modifiedBy information.
* **tags**: [TrackedResourceTags](#trackedresourcetags): Resource tags.
* **type**: 'Microsoft.Sovereign/sovereignViews' (ReadOnly, DeployTimeConstant): The resource type

## SovereignViewDataResidencyDimensionSettings
### Properties
* **parameters**: [SovereignViewDataResidencyParameters](#sovereignviewdataresidencyparameters) (Required): Parameters used by the Data Residency evaluation.
* **resourceEvaluationScope**: 'Residency360' | 'ResourceOnly' | string (Required): The resource scope evaluated for the Data Residency dimension.

## SovereignViewDataResidencyParameters
### Properties
* **allowedLocations**: string[] (Required): Azure regions in which the resource and its linked resources are allowed to reside.

## SovereignViewDimensionSettings
### Properties
* **dataResidency**: [SovereignViewDataResidencyDimensionSettings](#sovereignviewdataresidencydimensionsettings): Settings for the Data Residency dimension.

## SovereignViewManagementGroupScope
### Properties
* **id**: string (Required): The resource identifier of the management group.
* **name**: string: The management group name. This is a purely client side label that the service does not validate, normalize, or use for any lookup.

## SovereignViewPolicyInitiativeDetail
### Properties
* **dimension**: 'BusinessContinuity' | 'ControlledNetworkExposure' | 'DataResidency' | 'EncryptionAtRest' | 'EncryptionInTransit' | 'EncryptionInUse' | string (Required): The compliance dimension associated with the policy initiative.
* **policyAssignmentIds**: string[] (Required): The resource identifiers of existing policy assignments association with the policy initiative and scopes in the sovereign view.
* **policyInitiativeId**: string (Required): The fully qualified id of the policy initiative.
* **policyVersion**: string (Required): The version of the policy initiative.

## SovereignViewResourceProperties
### Properties
* **dimensionSettings**: [SovereignViewDimensionSettings](#sovereignviewdimensionsettings): Optional per-dimension evaluation settings.
* **isWorkload**: bool: Indicates whether the Sovereign View is considered a workload.
* **policyInitiatives**: [SovereignViewPolicyInitiativeDetail](#sovereignviewpolicyinitiativedetail)[] (Required): The policy initiatives selected for the sovereign view.
* **provisioningState**: 'Canceled' | 'Creating' | 'Deleting' | 'Failed' | 'Succeeded' | 'Updating' | string (ReadOnly): The status of a user-initiated, control-plane operation on the sovereign view resource type.
* **regulatoryDocumentName**: 'SovereignControlBaseline' | string: Stable regulatory-document key selected when this Sovereign View was created.
* **scope**: [SovereignViewScope](#sovereignviewscope) (Required): The scope to apply for configuration.

## SovereignViewScope
### Properties
* **managementGroups**: [SovereignViewManagementGroupScope](#sovereignviewmanagementgroupscope)[]: The management groups in scope.
* **subscriptions**: [SovereignViewSubscriptionScope](#sovereignviewsubscriptionscope)[]: The subscriptions in scope.

## SovereignViewSubscriptionScope
### Properties
* **id**: string {minLength: 36, maxLength: 36, pattern: "^[0-9a-fA-F]{8}-([0-9a-fA-F]{4}-){3}[0-9a-fA-F]{12}$"} (Required): The subscription id.
* **name**: string: The subscription name. This is a purely client side label that the service does not validate, normalize, or use for any lookup.

## SystemAssignedServiceIdentity
### Properties
* **principalId**: string {minLength: 36, maxLength: 36, pattern: "^[0-9a-fA-F]{8}-([0-9a-fA-F]{4}-){3}[0-9a-fA-F]{12}$"} (ReadOnly): The service principal ID of the system assigned identity. This property will only be provided for a system assigned identity.
* **tenantId**: string {minLength: 36, maxLength: 36, pattern: "^[0-9a-fA-F]{8}-([0-9a-fA-F]{4}-){3}[0-9a-fA-F]{12}$"} (ReadOnly): The tenant ID of the system assigned identity. This property will only be provided for a system assigned identity.
* **type**: 'None' | 'SystemAssigned' | string (Required): Type of managed service identity (either system assigned, or none).

## SystemData
### Properties
* **createdAt**: string: The timestamp of resource creation (UTC).
* **createdBy**: string: The identity that created the resource.
* **createdByType**: 'Application' | 'Key' | 'ManagedIdentity' | 'User' | string: The type of identity that created the resource.
* **lastModifiedAt**: string: The timestamp of resource last modification (UTC)
* **lastModifiedBy**: string: The identity that last modified the resource.
* **lastModifiedByType**: 'Application' | 'Key' | 'ManagedIdentity' | 'User' | string: The type of identity that last modified the resource.

## TrackedResourceTags
### Properties
### Additional Properties
* **Additional Properties Type**: string

