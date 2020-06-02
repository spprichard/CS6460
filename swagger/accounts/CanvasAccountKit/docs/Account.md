# Account

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**defaultGroupStorageQuotaMb** | **Int** | The storage quota for a group in the account in megabytes, if not otherwise specified | [optional] 
**defaultStorageQuotaMb** | **Int** | The storage quota for the account in megabytes, if not otherwise specified | [optional] 
**defaultTimeZone** | **String** | The default time zone of the account. Allowed time zones are {http://www.iana.org/time-zones IANA time zones} or friendlier {http://api.rubyonrails.org/classes/ActiveSupport/TimeZone.html Ruby on Rails time zones}. | [optional] 
**defaultUserStorageQuotaMb** | **Int** | The storage quota for a user in the account in megabytes, if not otherwise specified | [optional] 
**id** | **Int** | the ID of the Account object | [optional] 
**integrationId** | **String** | The account&#39;s identifier in the Student Information System. Only included if the user has permission to view SIS information. | [optional] 
**ltiGuid** | **String** | The account&#39;s identifier that is sent as context_id in LTI launches. | [optional] 
**name** | **String** | The display name of the account | [optional] 
**parentAccountId** | **Int** | The account&#39;s parent ID, or null if this is the root account | [optional] 
**rootAccountId** | **Int** | The ID of the root account, or null if this is the root account | [optional] 
**sisAccountId** | **String** | The account&#39;s identifier in the Student Information System. Only included if the user has permission to view SIS information. | [optional] 
**sisImportId** | **Int** | The id of the SIS import if created through SIS. Only included if the user has permission to manage SIS information. | [optional] 
**uuid** | **String** | The UUID of the account | [optional] 
**workflowState** | **String** | The state of the account. Can be &#39;active&#39; or &#39;deleted&#39;. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


