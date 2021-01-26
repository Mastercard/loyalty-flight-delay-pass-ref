# FlightDelayControllerApi

All URIs are relative to *http://localhost:8181*

Method | HTTP request | Description
------------- | ------------- | -------------
[**postRegistration**](FlightDelayControllerApi.md#postRegistration) | **POST** /loyalty/flight-delay-pass/registrations | 


<a name="postRegistration"></a>
# **postRegistration**
> RegistrionResponse postRegistration(xOpenapiClientid, userRequest)



### Example
```java
// Import classes:
//import com.mastercard.developer.flight_delay_pass_reference.ApiException;
//import com.mastercard.developer.flight_delay_pass_reference.api.FlightDelayControllerApi;


FlightDelayControllerApi apiInstance = new FlightDelayControllerApi();
String xOpenapiClientid = "xOpenapiClientid_example"; // String | 
UserRequest userRequest = new UserRequest(); // UserRequest | 
try {
    RegistrionResponse result = apiInstance.postRegistration(xOpenapiClientid, userRequest);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling FlightDelayControllerApi#postRegistration");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **xOpenapiClientid** | **String**|  |
 **userRequest** | [**UserRequest**](UserRequest.md)|  |

### Return type

[**RegistrionResponse**](RegistrionResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

