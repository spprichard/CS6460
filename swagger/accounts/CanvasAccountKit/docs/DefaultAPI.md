# DefaultAPI

All URIs are relative to *https://canvas.instructure.com/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createNewSubAccount**](DefaultAPI.md#createnewsubaccount) | **POST** /v1/accounts/{account_id}/sub_accounts | Create a new sub-account
[**deleteSubAccount**](DefaultAPI.md#deletesubaccount) | **DELETE** /v1/accounts/{account_id}/sub_accounts/{id} | Delete a sub-account
[**deleteUserFromRootAccount**](DefaultAPI.md#deleteuserfromrootaccount) | **DELETE** /v1/accounts/{account_id}/users/{user_id} | Delete a user from the root account
[**getSingleAccount**](DefaultAPI.md#getsingleaccount) | **GET** /v1/accounts/{id} | Get a single account
[**getSubAccountsOfAccount**](DefaultAPI.md#getsubaccountsofaccount) | **GET** /v1/accounts/{account_id}/sub_accounts | Get the sub-accounts of an account
[**listAccounts**](DefaultAPI.md#listaccounts) | **GET** /v1/accounts | List accounts
[**listAccountsForCourseAdmins**](DefaultAPI.md#listaccountsforcourseadmins) | **GET** /v1/course_accounts | List accounts for course admins
[**listActiveCoursesInAccount**](DefaultAPI.md#listactivecoursesinaccount) | **GET** /v1/accounts/{account_id}/courses | List active courses in an account
[**returnsTermsOfServiceForThatAccount**](DefaultAPI.md#returnstermsofserviceforthataccount) | **GET** /v1/accounts/{account_id}/terms_of_service | Returns the terms of service for that account
[**updateAccount**](DefaultAPI.md#updateaccount) | **PUT** /v1/accounts/{id} | Update an account


# **createNewSubAccount**
```swift
    open class func createNewSubAccount(accountId: String, accountName: String, accountSisAccountId: String? = nil, accountDefaultStorageQuotaMb: Int64? = nil, accountDefaultUserStorageQuotaMb: Int64? = nil, accountDefaultGroupStorageQuotaMb: Int64? = nil, completion: @escaping (_ data: Account?, _ error: Error?) -> Void)
```

Create a new sub-account

Add a new sub-account to a given account.

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let accountId = "accountId_example" // String | ID
let accountName = "accountName_example" // String | The name of the new sub-account.
let accountSisAccountId = "accountSisAccountId_example" // String | The account's identifier in the Student Information System. (optional)
let accountDefaultStorageQuotaMb = 987 // Int64 | The default course storage quota to be used, if not otherwise specified. (optional)
let accountDefaultUserStorageQuotaMb = 987 // Int64 | The default user storage quota to be used, if not otherwise specified. (optional)
let accountDefaultGroupStorageQuotaMb = 987 // Int64 | The default group storage quota to be used, if not otherwise specified. (optional)

// Create a new sub-account
DefaultAPI.createNewSubAccount(accountId: accountId, accountName: accountName, accountSisAccountId: accountSisAccountId, accountDefaultStorageQuotaMb: accountDefaultStorageQuotaMb, accountDefaultUserStorageQuotaMb: accountDefaultUserStorageQuotaMb, accountDefaultGroupStorageQuotaMb: accountDefaultGroupStorageQuotaMb) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accountId** | **String** | ID | 
 **accountName** | **String** | The name of the new sub-account. | 
 **accountSisAccountId** | **String** | The account&#39;s identifier in the Student Information System. | [optional] 
 **accountDefaultStorageQuotaMb** | **Int64** | The default course storage quota to be used, if not otherwise specified. | [optional] 
 **accountDefaultUserStorageQuotaMb** | **Int64** | The default user storage quota to be used, if not otherwise specified. | [optional] 
 **accountDefaultGroupStorageQuotaMb** | **Int64** | The default group storage quota to be used, if not otherwise specified. | [optional] 

### Return type

[**Account**](Account.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteSubAccount**
```swift
    open class func deleteSubAccount(accountId: String, id: String, completion: @escaping (_ data: Account?, _ error: Error?) -> Void)
```

Delete a sub-account

Cannot delete an account with active courses or active sub_accounts. Cannot delete a root_account

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let accountId = "accountId_example" // String | ID
let id = "id_example" // String | ID

// Delete a sub-account
DefaultAPI.deleteSubAccount(accountId: accountId, id: id) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accountId** | **String** | ID | 
 **id** | **String** | ID | 

### Return type

[**Account**](Account.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **deleteUserFromRootAccount**
```swift
    open class func deleteUserFromRootAccount(accountId: String, userId: String, completion: @escaping (_ data: User?, _ error: Error?) -> Void)
```

Delete a user from the root account

Delete a user record from a Canvas root account. If a user is associated with multiple root accounts (in a multi-tenant instance of Canvas), this action will NOT remove them from the other accounts.  WARNING: This API will allow a user to remove themselves from the account. If they do this, they won't be able to make API calls or log into Canvas at that account.

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let accountId = "accountId_example" // String | ID
let userId = "userId_example" // String | ID

// Delete a user from the root account
DefaultAPI.deleteUserFromRootAccount(accountId: accountId, userId: userId) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accountId** | **String** | ID | 
 **userId** | **String** | ID | 

### Return type

[**User**](User.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getSingleAccount**
```swift
    open class func getSingleAccount(id: String, completion: @escaping (_ data: Account?, _ error: Error?) -> Void)
```

Get a single account

Retrieve information on an individual account, given by id or sis sis_account_id.

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let id = "id_example" // String | ID

// Get a single account
DefaultAPI.getSingleAccount(id: id) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String** | ID | 

### Return type

[**Account**](Account.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **getSubAccountsOfAccount**
```swift
    open class func getSubAccountsOfAccount(accountId: String, recursive: Bool? = nil, completion: @escaping (_ data: [Account]?, _ error: Error?) -> Void)
```

Get the sub-accounts of an account

List accounts that are sub-accounts of the given account.

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let accountId = "accountId_example" // String | ID
let recursive = true // Bool | If true, the entire account tree underneath this account will be returned (though still paginated). If false, only direct sub-accounts of this account will be returned. Defaults to false. (optional)

// Get the sub-accounts of an account
DefaultAPI.getSubAccountsOfAccount(accountId: accountId, recursive: recursive) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accountId** | **String** | ID | 
 **recursive** | **Bool** | If true, the entire account tree underneath this account will be returned (though still paginated). If false, only direct sub-accounts of this account will be returned. Defaults to false. | [optional] 

### Return type

[**[Account]**](Account.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listAccounts**
```swift
    open class func listAccounts(include: [String]? = nil, completion: @escaping (_ data: [Account]?, _ error: Error?) -> Void)
```

List accounts

A paginated list of accounts that the current user can view or manage. Typically, students and even teachers will get an empty list in response, only account admins can view the accounts that they are in.

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let include = ["inner_example"] // [String] | Array of additional information to include.  \"lti_guid\":: the 'tool_consumer_instance_guid' that will be sent for this account on LTI launches \"registration_settings\":: returns info about the privacy policy and terms of use \"services\":: returns services and whether they are enabled (requires account management permissions) (optional)

// List accounts
DefaultAPI.listAccounts(include: include) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **include** | [**[String]**](String.md) | Array of additional information to include.  \&quot;lti_guid\&quot;:: the &#39;tool_consumer_instance_guid&#39; that will be sent for this account on LTI launches \&quot;registration_settings\&quot;:: returns info about the privacy policy and terms of use \&quot;services\&quot;:: returns services and whether they are enabled (requires account management permissions) | [optional] 

### Return type

[**[Account]**](Account.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listAccountsForCourseAdmins**
```swift
    open class func listAccountsForCourseAdmins(completion: @escaping (_ data: [Account]?, _ error: Error?) -> Void)
```

List accounts for course admins

A paginated list of accounts that the current user can view through their admin course enrollments. (Teacher, TA, or designer enrollments). Only returns \"id\", \"name\", \"workflow_state\", \"root_account_id\" and \"parent_account_id\"

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit


// List accounts for course admins
DefaultAPI.listAccountsForCourseAdmins() { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**[Account]**](Account.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **listActiveCoursesInAccount**
```swift
    open class func listActiveCoursesInAccount(accountId: String, withEnrollments: Bool? = nil, enrollmentType: [String]? = nil, published: Bool? = nil, completed: Bool? = nil, blueprint: Bool? = nil, blueprintAssociated: Bool? = nil, byTeachers: [Int]? = nil, bySubaccounts: [Int]? = nil, hideEnrollmentlessCourses: Bool? = nil, state: [String]? = nil, enrollmentTermId: Int64? = nil, searchTerm: String? = nil, include: [String]? = nil, sort: Sort_listActiveCoursesInAccount? = nil, order: Order_listActiveCoursesInAccount? = nil, searchBy: SearchBy_listActiveCoursesInAccount? = nil, completion: @escaping (_ data: [Course]?, _ error: Error?) -> Void)
```

List active courses in an account

Retrieve a paginated list of courses in this account.

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let accountId = "accountId_example" // String | ID
let withEnrollments = true // Bool | If true, include only courses with at least one enrollment.  If false, include only courses with no enrollments.  If not present, do not filter on course enrollment status. (optional)
let enrollmentType = ["inner_example"] // [String] | If set, only return courses that have at least one user enrolled in in the course with one of the specified enrollment types. (optional)
let published = true // Bool | If true, include only published courses.  If false, exclude published courses.  If not present, do not filter on published status. (optional)
let completed = true // Bool | If true, include only completed courses (these may be in state 'completed', or their enrollment term may have ended).  If false, exclude completed courses.  If not present, do not filter on completed status. (optional)
let blueprint = true // Bool | If true, include only blueprint courses. If false, exclude them. If not present, do not filter on this basis. (optional)
let blueprintAssociated = true // Bool | If true, include only courses that inherit content from a blueprint course. If false, exclude them. If not present, do not filter on this basis. (optional)
let byTeachers = [123] // [Int] | List of User IDs of teachers; if supplied, include only courses taught by one of the referenced users. (optional)
let bySubaccounts = [123] // [Int] | List of Account IDs; if supplied, include only courses associated with one of the referenced subaccounts. (optional)
let hideEnrollmentlessCourses = true // Bool | If present, only return courses that have at least one enrollment. Equivalent to 'with_enrollments=true'; retained for compatibility. (optional)
let state = ["inner_example"] // [String] | If set, only return courses that are in the given state(s). By default, all states but \"deleted\" are returned. (optional)
let enrollmentTermId = 987 // Int64 | If set, only includes courses from the specified term. (optional)
let searchTerm = "searchTerm_example" // String | The partial course name, code, or full ID to match and return in the results list. Must be at least 3 characters. (optional)
let include = ["inner_example"] // [String] | - All explanations can be seen in the {api:CoursesController#index Course API index documentation} - \"sections\", \"needs_grading_count\" and \"total_scores\" are not valid options at the account level (optional)
let sort = "sort_example" // String | The column to sort results by. (optional)
let order = "order_example" // String | The order to sort the given column by. (optional)
let searchBy = "searchBy_example" // String | The filter to search by. \"course\" searches for course names, course codes, and SIS IDs. \"teacher\" searches for teacher names (optional)

// List active courses in an account
DefaultAPI.listActiveCoursesInAccount(accountId: accountId, withEnrollments: withEnrollments, enrollmentType: enrollmentType, published: published, completed: completed, blueprint: blueprint, blueprintAssociated: blueprintAssociated, byTeachers: byTeachers, bySubaccounts: bySubaccounts, hideEnrollmentlessCourses: hideEnrollmentlessCourses, state: state, enrollmentTermId: enrollmentTermId, searchTerm: searchTerm, include: include, sort: sort, order: order, searchBy: searchBy) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accountId** | **String** | ID | 
 **withEnrollments** | **Bool** | If true, include only courses with at least one enrollment.  If false, include only courses with no enrollments.  If not present, do not filter on course enrollment status. | [optional] 
 **enrollmentType** | [**[String]**](String.md) | If set, only return courses that have at least one user enrolled in in the course with one of the specified enrollment types. | [optional] 
 **published** | **Bool** | If true, include only published courses.  If false, exclude published courses.  If not present, do not filter on published status. | [optional] 
 **completed** | **Bool** | If true, include only completed courses (these may be in state &#39;completed&#39;, or their enrollment term may have ended).  If false, exclude completed courses.  If not present, do not filter on completed status. | [optional] 
 **blueprint** | **Bool** | If true, include only blueprint courses. If false, exclude them. If not present, do not filter on this basis. | [optional] 
 **blueprintAssociated** | **Bool** | If true, include only courses that inherit content from a blueprint course. If false, exclude them. If not present, do not filter on this basis. | [optional] 
 **byTeachers** | [**[Int]**](Int.md) | List of User IDs of teachers; if supplied, include only courses taught by one of the referenced users. | [optional] 
 **bySubaccounts** | [**[Int]**](Int.md) | List of Account IDs; if supplied, include only courses associated with one of the referenced subaccounts. | [optional] 
 **hideEnrollmentlessCourses** | **Bool** | If present, only return courses that have at least one enrollment. Equivalent to &#39;with_enrollments&#x3D;true&#39;; retained for compatibility. | [optional] 
 **state** | [**[String]**](String.md) | If set, only return courses that are in the given state(s). By default, all states but \&quot;deleted\&quot; are returned. | [optional] 
 **enrollmentTermId** | **Int64** | If set, only includes courses from the specified term. | [optional] 
 **searchTerm** | **String** | The partial course name, code, or full ID to match and return in the results list. Must be at least 3 characters. | [optional] 
 **include** | [**[String]**](String.md) | - All explanations can be seen in the {api:CoursesController#index Course API index documentation} - \&quot;sections\&quot;, \&quot;needs_grading_count\&quot; and \&quot;total_scores\&quot; are not valid options at the account level | [optional] 
 **sort** | **String** | The column to sort results by. | [optional] 
 **order** | **String** | The order to sort the given column by. | [optional] 
 **searchBy** | **String** | The filter to search by. \&quot;course\&quot; searches for course names, course codes, and SIS IDs. \&quot;teacher\&quot; searches for teacher names | [optional] 

### Return type

[**[Course]**](Course.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **returnsTermsOfServiceForThatAccount**
```swift
    open class func returnsTermsOfServiceForThatAccount(accountId: String, completion: @escaping (_ data: TermsOfService?, _ error: Error?) -> Void)
```

Returns the terms of service for that account

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let accountId = "accountId_example" // String | ID

// Returns the terms of service for that account
DefaultAPI.returnsTermsOfServiceForThatAccount(accountId: accountId) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accountId** | **String** | ID | 

### Return type

[**TermsOfService**](TermsOfService.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **updateAccount**
```swift
    open class func updateAccount(id: String, accountName: String? = nil, accountSisAccountId: String? = nil, accountDefaultTimeZone: String? = nil, accountDefaultStorageQuotaMb: Int64? = nil, accountDefaultUserStorageQuotaMb: Int64? = nil, accountDefaultGroupStorageQuotaMb: Int64? = nil, accountSettingsRestrictStudentPastViewValue: Bool? = nil, accountSettingsRestrictStudentPastViewLocked: Bool? = nil, accountSettingsRestrictStudentFutureViewValue: Bool? = nil, accountSettingsRestrictStudentFutureViewLocked: Bool? = nil, accountSettingsLockAllAnnouncementsValue: Bool? = nil, accountSettingsLockAllAnnouncementsLocked: Bool? = nil, accountSettingsRestrictStudentFutureListingValue: Bool? = nil, accountSettingsRestrictStudentFutureListingLocked: Bool? = nil, accountServices: AnyType? = nil, completion: @escaping (_ data: Account?, _ error: Error?) -> Void)
```

Update an account

Update an existing account.

### Example 
```swift
// The following code samples are still beta. For any issue, please report via http://github.com/OpenAPITools/openapi-generator/issues/new
import CanvasAccountKit

let id = "id_example" // String | ID
let accountName = "accountName_example" // String | Updates the account name (optional)
let accountSisAccountId = "accountSisAccountId_example" // String | Updates the account sis_account_id Must have manage_sis permission and must not be a root_account. (optional)
let accountDefaultTimeZone = "accountDefaultTimeZone_example" // String | The default time zone of the account. Allowed time zones are {http://www.iana.org/time-zones IANA time zones} or friendlier {http://api.rubyonrails.org/classes/ActiveSupport/TimeZone.html Ruby on Rails time zones}. (optional)
let accountDefaultStorageQuotaMb = 987 // Int64 | The default course storage quota to be used, if not otherwise specified. (optional)
let accountDefaultUserStorageQuotaMb = 987 // Int64 | The default user storage quota to be used, if not otherwise specified. (optional)
let accountDefaultGroupStorageQuotaMb = 987 // Int64 | The default group storage quota to be used, if not otherwise specified. (optional)
let accountSettingsRestrictStudentPastViewValue = true // Bool | Restrict students from viewing courses after end date (optional)
let accountSettingsRestrictStudentPastViewLocked = true // Bool | Lock this setting for sub-accounts and courses (optional)
let accountSettingsRestrictStudentFutureViewValue = true // Bool | Restrict students from viewing courses before start date (optional)
let accountSettingsRestrictStudentFutureViewLocked = true // Bool | Lock this setting for sub-accounts and courses (optional)
let accountSettingsLockAllAnnouncementsValue = true // Bool | Disable comments on announcements (optional)
let accountSettingsLockAllAnnouncementsLocked = true // Bool | Lock this setting for sub-accounts and courses (optional)
let accountSettingsRestrictStudentFutureListingValue = true // Bool | Restrict students from viewing future enrollments in course list (optional)
let accountSettingsRestrictStudentFutureListingLocked = true // Bool | Lock this setting for sub-accounts and courses (optional)
let accountServices = TODO // AnyType | Give this a set of keys and boolean values to enable or disable services matching the keys (optional)

// Update an account
DefaultAPI.updateAccount(id: id, accountName: accountName, accountSisAccountId: accountSisAccountId, accountDefaultTimeZone: accountDefaultTimeZone, accountDefaultStorageQuotaMb: accountDefaultStorageQuotaMb, accountDefaultUserStorageQuotaMb: accountDefaultUserStorageQuotaMb, accountDefaultGroupStorageQuotaMb: accountDefaultGroupStorageQuotaMb, accountSettingsRestrictStudentPastViewValue: accountSettingsRestrictStudentPastViewValue, accountSettingsRestrictStudentPastViewLocked: accountSettingsRestrictStudentPastViewLocked, accountSettingsRestrictStudentFutureViewValue: accountSettingsRestrictStudentFutureViewValue, accountSettingsRestrictStudentFutureViewLocked: accountSettingsRestrictStudentFutureViewLocked, accountSettingsLockAllAnnouncementsValue: accountSettingsLockAllAnnouncementsValue, accountSettingsLockAllAnnouncementsLocked: accountSettingsLockAllAnnouncementsLocked, accountSettingsRestrictStudentFutureListingValue: accountSettingsRestrictStudentFutureListingValue, accountSettingsRestrictStudentFutureListingLocked: accountSettingsRestrictStudentFutureListingLocked, accountServices: accountServices) { (response, error) in
    guard error == nil else {
        print(error)
        return
    }

    if (response) {
        dump(response)
    }
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **String** | ID | 
 **accountName** | **String** | Updates the account name | [optional] 
 **accountSisAccountId** | **String** | Updates the account sis_account_id Must have manage_sis permission and must not be a root_account. | [optional] 
 **accountDefaultTimeZone** | **String** | The default time zone of the account. Allowed time zones are {http://www.iana.org/time-zones IANA time zones} or friendlier {http://api.rubyonrails.org/classes/ActiveSupport/TimeZone.html Ruby on Rails time zones}. | [optional] 
 **accountDefaultStorageQuotaMb** | **Int64** | The default course storage quota to be used, if not otherwise specified. | [optional] 
 **accountDefaultUserStorageQuotaMb** | **Int64** | The default user storage quota to be used, if not otherwise specified. | [optional] 
 **accountDefaultGroupStorageQuotaMb** | **Int64** | The default group storage quota to be used, if not otherwise specified. | [optional] 
 **accountSettingsRestrictStudentPastViewValue** | **Bool** | Restrict students from viewing courses after end date | [optional] 
 **accountSettingsRestrictStudentPastViewLocked** | **Bool** | Lock this setting for sub-accounts and courses | [optional] 
 **accountSettingsRestrictStudentFutureViewValue** | **Bool** | Restrict students from viewing courses before start date | [optional] 
 **accountSettingsRestrictStudentFutureViewLocked** | **Bool** | Lock this setting for sub-accounts and courses | [optional] 
 **accountSettingsLockAllAnnouncementsValue** | **Bool** | Disable comments on announcements | [optional] 
 **accountSettingsLockAllAnnouncementsLocked** | **Bool** | Lock this setting for sub-accounts and courses | [optional] 
 **accountSettingsRestrictStudentFutureListingValue** | **Bool** | Restrict students from viewing future enrollments in course list | [optional] 
 **accountSettingsRestrictStudentFutureListingLocked** | **Bool** | Lock this setting for sub-accounts and courses | [optional] 
 **accountServices** | [**AnyType**](AnyType.md) | Give this a set of keys and boolean values to enable or disable services matching the keys | [optional] 

### Return type

[**Account**](Account.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

