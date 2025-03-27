# swagger-java-client

Selling Partner API for Data Kiosk
- API version: 2023-11-15
  - Build date: 2025-03-27T14:05:24.705650800+08:00[Asia/Shanghai]

The Selling Partner API for Data Kiosk lets you submit GraphQL queries from a variety of schemas to help selling partners manage their businesses.

  For more information, please visit [https://sellercentral.amazon.com/gp/mws/contactus.html](https://sellercentral.amazon.com/gp/mws/contactus.html)

*Automatically generated by the [Swagger Codegen](https://github.com/swagger-api/swagger-codegen)*


## Requirements

Building the API client library requires:
1. Java 1.7+
2. Maven/Gradle

## Installation

To install the API client library to your local Maven repository, simply execute:

```shell
mvn clean install
```

To deploy it to a remote Maven repository instead, configure the settings of the repository and execute:

```shell
mvn clean deploy
```

Refer to the [OSSRH Guide](http://central.sonatype.org/pages/ossrh-guide.html) for more information.

### Maven users

Add this dependency to your project's POM:

```xml
<dependency>
  <groupId>io.swagger</groupId>
  <artifactId>swagger-java-client</artifactId>
  <version>3.0</version>
  <scope>compile</scope>
</dependency>
```

### Gradle users

Add this dependency to your project's build file:

```groovy
compile "io.swagger:swagger-java-client:3.0"
```

### Others

At first generate the JAR by executing:

```shell
mvn clean package
```

Then manually install the following JARs:

* `target/swagger-java-client-3.0.jar`
* `target/lib/*.jar`

## Getting Started

Please follow the [installation](#installation) instruction and execute the following Java code:

```java
import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.QueriesApi;

import java.io.File;
import java.util.*;

public class QueriesApiExample {

    public static void main(String[] args) {
        
        QueriesApi apiInstance = new QueriesApi();
        String queryId = "queryId_example"; // String | The identifier for the query. This identifier is unique only in combination with a selling partner account ID.
        try {
            apiInstance.cancelQuery(queryId);
        } catch (ApiException e) {
            System.err.println("Exception when calling QueriesApi#cancelQuery");
            e.printStackTrace();
        }
    }
}
import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.QueriesApi;

import java.io.File;
import java.util.*;

public class QueriesApiExample {

    public static void main(String[] args) {
        
        QueriesApi apiInstance = new QueriesApi();
        CreateQuerySpecification body = new CreateQuerySpecification(); // CreateQuerySpecification | The body of the request.
        try {
            CreateQueryResponse result = apiInstance.createQuery(body);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling QueriesApi#createQuery");
            e.printStackTrace();
        }
    }
}
import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.QueriesApi;

import java.io.File;
import java.util.*;

public class QueriesApiExample {

    public static void main(String[] args) {
        
        QueriesApi apiInstance = new QueriesApi();
        String documentId = "documentId_example"; // String | The identifier for the Data Kiosk document.
        try {
            GetDocumentResponse result = apiInstance.getDocument(documentId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling QueriesApi#getDocument");
            e.printStackTrace();
        }
    }
}
import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.QueriesApi;

import java.io.File;
import java.util.*;

public class QueriesApiExample {

    public static void main(String[] args) {
        
        QueriesApi apiInstance = new QueriesApi();
        List<String> processingStatuses = Arrays.asList("processingStatuses_example"); // List<String> | A list of processing statuses used to filter queries.
        Integer pageSize = 10; // Integer | The maximum number of queries to return in a single call.
        OffsetDateTime createdSince = new OffsetDateTime(); // OffsetDateTime | The earliest query creation date and time for queries to include in the response, in ISO 8601 date time format. The default is 90 days ago.
        OffsetDateTime createdUntil = new OffsetDateTime(); // OffsetDateTime | The latest query creation date and time for queries to include in the response, in ISO 8601 date time format. The default is the time of the `getQueries` request.
        String paginationToken = "paginationToken_example"; // String | A token to fetch a certain page of results when there are multiple pages of results available. The value of this token is fetched from the `pagination.nextToken` field returned in the `GetQueriesResponse` object. All other parameters must be provided with the same values that were provided with the request that generated this token, with the exception of `pageSize` which can be modified between calls to `getQueries`. In the absence of this token value, `getQueries` returns the first page of results.
        try {
            GetQueriesResponse result = apiInstance.getQueries(processingStatuses, pageSize, createdSince, createdUntil, paginationToken);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling QueriesApi#getQueries");
            e.printStackTrace();
        }
    }
}
import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.QueriesApi;

import java.io.File;
import java.util.*;

public class QueriesApiExample {

    public static void main(String[] args) {
        
        QueriesApi apiInstance = new QueriesApi();
        String queryId = "queryId_example"; // String | The query identifier.
        try {
            Query result = apiInstance.getQuery(queryId);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling QueriesApi#getQuery");
            e.printStackTrace();
        }
    }
}
```

## Documentation for API Endpoints

All URIs are relative to *https://sellingpartnerapi-na.amazon.com/*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*QueriesApi* | [**cancelQuery**](docs/QueriesApi.md#cancelQuery) | **DELETE** /dataKiosk/2023-11-15/queries/{queryId} | 
*QueriesApi* | [**createQuery**](docs/QueriesApi.md#createQuery) | **POST** /dataKiosk/2023-11-15/queries | 
*QueriesApi* | [**getDocument**](docs/QueriesApi.md#getDocument) | **GET** /dataKiosk/2023-11-15/documents/{documentId} | 
*QueriesApi* | [**getQueries**](docs/QueriesApi.md#getQueries) | **GET** /dataKiosk/2023-11-15/queries | 
*QueriesApi* | [**getQuery**](docs/QueriesApi.md#getQuery) | **GET** /dataKiosk/2023-11-15/queries/{queryId} | 

## Documentation for Models

 - [CreateQueryResponse](docs/CreateQueryResponse.md)
 - [CreateQuerySpecification](docs/CreateQuerySpecification.md)
 - [Error](docs/Error.md)
 - [ErrorList](docs/ErrorList.md)
 - [GetDocumentResponse](docs/GetDocumentResponse.md)
 - [GetQueriesResponse](docs/GetQueriesResponse.md)
 - [GetQueriesResponsePagination](docs/GetQueriesResponsePagination.md)
 - [Query](docs/Query.md)
 - [QueryList](docs/QueryList.md)
 - [QueryPagination](docs/QueryPagination.md)

## Documentation for Authorization

All endpoints do not require authorization.
Authentication schemes defined for the API:

## Recommendation

It's recommended to create an instance of `ApiClient` per thread in a multithreaded environment to avoid any potential issues.

## Author


