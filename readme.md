# RSApiClient Class

The `RSApiClient` class is a Java class that provides methods for making HTTP requests to specific API endpoints and retrieving predefined data from a remote server. This class uses the Apache HttpClient library to handle HTTP requests and responses. Here, we'll provide documentation in a markdown file for the methods available in the `RSApiClient` class.

## Class Overview

The `RSApiClient` class allows you to retrieve various predefined data sets from a remote server. Each method corresponds to a specific data set, and it makes an HTTP GET request to the respective API endpoint. The methods handle both successful responses (HTTP status code 200) and error responses, raising exceptions if necessary.

## Methods

### `RSApiClient()`

Constructor for the `RSApiClient` class. It initializes an instance of the class and creates an HttpClient for making HTTP requests.

```java
public RSApiClient()
```

### `getZipCodeList()`

Retrieves a list of zip codes from the remote server.

```java
public String getZipCodeList() throws IOException
```

### `getEmployeeSizeList()`

Retrieves a list of employee sizes from the remote server.

```java
public String getEmployeeSizeList() throws IOException
```

### `getRevenueAmountList()`

Retrieves a list of revenue amounts from the remote server.

```java
public String getRevenueAmountList() throws IOException
```

### `getJobTitleList()`

Retrieves a list of job titles from the remote server.

```java
public String getJobTitleList() throws IOException
```

### `getJobTitleLevelList()`

Retrieves a list of job title levels from the remote server.

```java
public String getJobTitleLevelList() throws IOException
```

### `getDepartmentFunctionList()`

Retrieves a list of department functions from the remote server.

```java
public String getDepartmentFunctionList() throws IOException
```

### `getSicCodeList()`

Retrieves a list of SIC (Standard Industrial Classification) codes from the remote server.

```java
public String getSicCodeList() throws IOException
```

### `getCountryList()`

Retrieves a list of countries from the remote server.

```java
public String getCountryList() throws IOException
```

### `getStateList()`

Retrieves a list of states from the remote server.

```java
public String getStateList() throws IOException
```

### `getCityList()`

Retrieves a list of cities from the remote server.

```java
public String getCityList() throws IOException
```

### `getIndustryList()`

Retrieves a list of industries from the remote server.

```java
public String getIndustryList() throws IOException
```

## Error Handling

Each method in the `RSApiClient` class performs error handling. If the HTTP response status code is not 200, an `IOException` is thrown with an error message indicating the failure and the specific HTTP status code.

```java
throw new IOException("Failed to retrieve the [data type] list. HTTP Status Code: " + response.getStatusLine().getStatusCode());
```

Additionally, if any other exceptions occur during the execution of the method, the exceptions are caught, and an `IOException` is thrown with a message indicating the failure and the underlying exception's message.

```java
throw new IOException("Failed to retrieve the [data type] list: " + e.getMessage(), e);
```

## Example Usage

Here's an example of how to use the `RSApiClient` class to retrieve a list of zip codes:

```java
RSApiClient apiClient = new RSApiClient();
try {
    String zipCodeList = apiClient.getZipCodeList();
    // Use the retrieved zip code data
} catch (IOException e) {
    // Handle the exception (e.g., log the error, display an error message)
}
```

Please note that you need to handle exceptions appropriately when using these methods, as they can throw `IOExceptions` in case of errors during the API request.

This documentation provides an overview of the `RSApiClient` class and its methods for retrieving predefined data sets from a remote server. You can use these methods to access various types of data for your application.