---
layout: default
title: API Reference
---

# API Reference

Hourfleet is built on a broad foundation of HTTP REST API’s. This means that anything and everything that you and your customers can do in the Hourfleet Apps, can also be automated by any system on the internet, by calling HTTP methods to Hourfleet APIs. 

That's exactly how Hourfleet works under the covers.

These are the base URL's of the APIs that Hourfleet provides for your Car Share:

- `https://yourcarshare.hourfleet.com:4445/api` - all API's directly related to Car Sharing. (i.e. cars, bookings, driverlicenses, availabilities etc.)
- `https://yourcarshare.hourfleet.com:4431/api` - all API's for supporting services (i.e. verifications, profiles, locations, etc.)
- `https://yourcarshare.hourfleet.com:4432/api` - API's for authentication and identity.

### API Documentation

Detailed documentation about each of these API's can be found at the above URL's.

To see the documentation, swap `yourcarshare` in the above URL's with the name of your Car Share.

>Note: If you dont yet have your own Car Share, just replace `yourcarshare` with `demo`.

## API Patterns

All API's follow consistent patterns, conventions, and formats. This is deliberate to increase the usability and discovery of the APIs as you learn more about the Car Sharing domain, and the Hourfleet APIs that make it.

Here are some general notes about all API's in Hourfleet:

All APIs are HTTPS only. HTTP access is forbidden.

Hourfleet APIs only supports the following HTTP verbs: `POST`, `PUT`, `PATCH`, `DELETE`, and `GET`. Although not strictly REST, there are some other operations that reflect RPC-tyoe 'actions' in the API, such as locking a car (`PUT /cars/{Id}/lock`), or rating a user.

By default, all responses are returned in JSON, although other formats are supported, the client can specify the format in the request. (see [Response Formats](#Response-Formats) below)

All operations support both JSON and URL encoded request body data, and also URL encoded query string parameters for passing in parameters to operations.

>Note: including body data in `GET` requests is not recommended.

Resources in API routes are always pluralised. For example the route for fetching a specfic car is: `GET /cars/{Id}`.

Updates to resources uses the 'partial update strategy', using the `PATCH` verb. Most update API's will specify precisely what properties of a resource can be updated, and many of them will be optional, so that you have fine grained control over which properties you specifically want to update in a single call. Some properties of some resource are not updatedable. Full update of resources with a `PUT` is generally not somrthing common in Hourfleet.

>Note: The optionality of parameters in any REST operation should be included in the documentation of the individual APIs.

`POST` operations will always create a new unique resource, and will always return a `Location` header with the URL to the newly created resource.

Generally speaking, `POST`, `PUT`, `PATCH`, `GET` operations will return a copy of the respective resource(s). `POST` returns a `HTTP 201` (Created) with a copy of the created resource. `PUT` and `PATCH` returns a `HTTP 202` (Accepted) with the updated resources. `DELETE` returns a `HTTP 204` (No Content) with no resource in the response.

All API's support rate limiting. Rate limits for individual APIs will vary however, based on both the caller and the frequency. An `HTTP 429` will be returned with a `Retry-After` header specifying the time when the limit will be lifted.

Most API operations wil be secured, and will require authorization in the form of a OAuth2 `Bearer` token, which must be present in the `Authorization`header. (see [Authorized Access](#Authorized-Access) below).

Most APIs will be restricted by role (RBAC) of the caller. Common roles include: `user`, `ops` and `clientapplication`.

### Response Formats

All APIs return JSON by default. To return other formats like: XML, CSV, JSV or HTML, specify the `format` property in the query, or in the `Accept` header.

For example, to return the a `Car` resource in XML, you could either specify: `GET /cars/{Id}?format=xml` or include the header: `Accept: application/xml`

### Case Sensitivity

All resources and all properties of resources will be returned in all responses with PascalCase property resource names and PascalCase property names.

However, all inbound data to the APIs (i.e. in POST, PUT, PATCH, GET or DELETE requests) can include resource and property names in any case, in either the body of the request or in the query string of the request, e.g. camelCase or PascalCase or snake-case.

### Resource ID's

All resources will have an `Id` property. The `Id` property will always be UUID of this format: `00000000-0000-0000-0000-000000000000`

### Dates and Times

All APIs that return dates and times, will do so in ISO8601 format, and those times will always be reprsented in UTC.

>Note: The clients will be responsible for converting UTC dates and times into local timezones formats.  

If the date has no value the date propery will be omitted from the response.

For example, a car has a `CreateDateUtc`, so the response to `GET /cars/{Id}` would include this date in this format:

```
{
    "Id": "12345678-1234-1234-1234-123456789012",
    "CreatedDateUtc": "2019-12-31T16:45:23.000Z"
}
```

When specifying dates and times in any operation, always specify the date and time in UTC. Only UTC dates and times will be acceptable.

>Note: All date peroperties in all resources will be suffixed with `Utc` as a reminder. For example, `CreatedDateUtc` and `LastModifiedDateUtc`


### Error Responses

All API responses will support structured error responses.

All error responses will return an appropriate HTTP status code. e.g. 200, 401, 404, 500

An error response will have a `ResponseStatus` property structure like this:

```
{
  ResponseStatus": {
    "ErrorCode": "string",
    "Message": "string",
    "Errors": [
      {
        "ErrorCode": "string",
        "FieldName": "string",
        "Message": "string",
        "Meta": {}
      }
    ],
    "Meta": {}
  }
}
```

where the `Errors` array may or may not include an array of error details. Such as when a request has multiple validation errors describing the problem with the request.

### Success Responses

All API responses will support either a single resource or an array of resources in the response (or no resource property in the response). The existance of this single resource or array of multiple resources is mutually exclusive with a `ResponseStatus` property in the response. 

All returned resources will have a top level property named for the specific resource, either as a single resource (singularized) or as an array of resources (pluralized).

For example, the response to fetching a car resource like `GET /cars/{Id}` will return a response like this, with a top level property called `Car`:

```
{
    "Car": {
        "Id":"12345678-1234-1234-1234-123456789012"
    }
}
```

For example, the response to fetching all car resources like `GET /cars` will return a response like this, with a top level array property called `Cars`:

```
{
    "Cars": [{
            "Id":"12345678-1234-1234-1234-123456789012"
        },
        {
            "Id":"12345678-1234-1234-1234-123456789013"
        }
    ]
}
```

### Search APIs

Some search type APIs resturn lists of multiple resources in one call. These search APIs have a bunch of things in common that are useful to know:

1. Date ranges, and other filtering options.
1. Filtering fields, sorting and distinct result sets
1. Pagination with: offsets and limits
1. Embedded resources, which is useful to minimize chatty requests for key dependent resources.
1. Metadata that summarize the returned result set, useful for summarising results, and pagination displays.

Some search APIs return different results based upon the caller or other environment conditions, for exmaple: the current time, or the state of the resource.

For example, if a car owner wants to see their list of bookings that are in a particular state, they can call: `GET /cars/{Id}/bookings?states=Approved,InUse`

The result set from that search would be very different if the borrower called the same API with the same parameters.

#### Ranges

Some search API's support ranges such as ranges in dates and times. 

Date ranges are always optional, and will have a default range if not specified. The default range may be different between APIs. The intention of having a default range is to keep the result set to a meaningful limit of results, as opposed to returning all resources for all time (which can be very expensive to compute and expensive to transport across HTTP).

>Note: Default ranges should be included in the documentation of the individual APIs.
 
#### Sorting and Filtering

All search APIs support sorting and filtering, by using the `Sort` and `Filter` properties.

You use sorting to arrange the results in a meaningful sort order. Sorting by one of the possible fields in the individual resource.

You specify one single value of the `Sort` property with an indication of which direction to sort. Different resources have different properties to sort on. Some resources will have a default sort value, depending on the calling context.

>Note: Default sort orders should be included in the documentation of the individual APIs.

For example, to sort the bookings for a car by `ApprovedDateUtc` in descending order (i.e. most recent first), you would specify: `GET /cars/{Id}/bookings?sort=-ApprovedDateUtc`

>Note: The `-` sign is required for decending order, the `+` sign is optional for ascending order. 

You use filtering to limit the properties being returned in the result set. This is one way to limit the actual data values transmitted over the wire.

You specify a comma-delimited list of fields that you wish to include in the results. 

For example, to return only the `ApprovedDateUtc` property of all bookings for a car, you would specify: `GET /cars/{Id}/bookings?filter=ApprovedDateUtc`. The returned results will include only the `Id` of the resource and the `ApprovedDateUtc` of the resource.

> Note: If you specify no `Filter` property, then no filter is applied. 

#### Limiting and Pagination

All search APIs support limiting results by just using the `Limit` property, or pagination of results, by using a combination of the `Offset` and `Limit` properties.

>Note: You can always Limit results without Pagination. For example, you may use the  `Sort` property and  `Limit`property together to narrow a set of specific resources.

For example, to simply limit the maximum number of bookings for car that you want to see, you could specify `GET /cars/{Id}/bookings?limit=10`

>Note: the `offset` is not required, and default sort orders and ranges will apply.

For example, to paginate results, and given 51 possible results, and a page size of 10:
    * If you want to see page 1 you would specify `GET /cars/{Id}/bookings?limit=10&offset=0`
    * If you want to see page 2 you would specify `GET /cars/{Id}/bookings?limit=10&offset=10`

#### Result Summaries

All search APIs will return metadata describing the set of multiple resources that are returned. This metadata will include any search options in the call as well (i.e. sort, limits, pagination, etc). 

This information is useful for displaying paginated results, or interpreting the original search request.

For example, the call to fetch all cars `GET /cars?sort=-CreatedDateUtc` will include the metadata in the response: 

```
{
    "Cars":[],
    Metadata": {
    "Total": 9,
    "Limit": 0,
    "Offset": 0,
    "Sort": {
      "By": "CreatedDateUtc",
      "Direction": "Descending"
    },
    "Filter": {
      "Fields": []
    },
    "Distinct": null
  }
}
```

### Embedded Resources

Applies only to `GET`operations.

Some primary resources (such as: `Car`, `CarBooking`, `UserAccount` etc) embed within them other descendant resources when featched with `GET`.

This is done as a (case by case) optimization to assist callers in reducing the need to aggregate these descendant resources in subsequent lookup queries. This strategy aims to reduce the need for chatty API calls to build object graphs of resources and their descendants, especially in the case of API's that return multiple resources (leading to N+1 lookups).

However, some clients (specifically mobile clients) will find this extra data included in the response unecessary in some cases, and/or expensive to add to the compute and transport of that resource, in their specific scenario.

There are two rules that apply to all embedded resources:

1. If the API is a `GET` for a single resource, then all embedded decendant resources (and their descendants) are included by default in the response. These embedded resources must be explictly omitted by the caller.
2. If the API is a `GET` for multiple resources, then all embedded descendant resources (and their descendants) are NOT included by default in the response. If embedded resources are required, they must be explicitly requested by the caller. 

Specifying the inclusion or omission of embedded resource is controlled by the `Embed` property.

>Note: each resource, could embed one or more descendant resources within it. The supported embedded resources should be included in the documentation of the individual APIs.

For single resource responses, you would omit the embedded resources by specifying `embed=none`.

For multiple resource responses, you would include all the embedded resources by specifying `embed=*` (or `embed=all`.

For either single resource or multiple resources, you could include only the specified embedded of interest by specifying `embed=resourcename.childresourcename` in a comma separated list.

For example, a `Car` resource will embed a `Rating` resource, and the `Verifications` resource for a `GET /cars/{Id}` call, but not embed those resources in the call to `GET /cars`. Callers that want to remove those embeddings in the call to the single car, would specify: `GET /cars/{Id}?embed=none`. Callers that do want to embed all resources in the call to multiple cars, would specify: `GET /cars?embed=all` 

### Response Caching

All `GET` API responses are cached by the API. Since fetched representations may vary for different callers, the cached responses are built once, and cached for either all callers or for specific callers.

>Note: all cached `GET`responses are cleared in the API whenever a `POST`, `PATCH`, `DELETE` operation is executed on that resource (or related resource) that could change the cached `GET` responses.

Cached responses all have a TTL, that also varies depending on the API.

Cached responses also are also returned with client caching headers that advise clients whether the responses should be cached by clients. The caching strategy is to use `ETag` and `If-None-Match` verification schemes. This means that clients should feel free to cache these responses for as long as the TTL advises, but whenever the resource is required again, always send the `ETag` in a `If-None-Match` header to see if the cached response has become stale in the interim. A `HTTP 304` (Not Modified) will be returned if the cached value has not changed in the interim. Otherwise a fresh value of the response will be cacluulated by the API and returned to the client, with a new `ETag`


## Webhooks

If you are interested in receiving notifications from Hourfleet for key events while your Car Share is operating, then you might want to subscribe to some of the webhooks that Hourfleet supports. See [Webhooks](webhooks.html) for more details.

## Authorized Access

> You need an *access_token* to call an API

Most of the API's that Hourfleet exposes require the caller to be authenticated, there are only a few that do not. You can see the security requirements of each API in the API documentation. 

Most *callers* (those who call API's) in Hourfleet are authenticated with credentials, such as a *username* and a *password* or with a *client_id* and *client_secret*.

Once authenticated, a caller will receive a ***token*** that needs to be transmitted along with the API call (typically in the 'Authorization' header of the call). 

`Authorization: Bearer AAIAAMqDamBCSU7ITHnyx.......`

This token is called an Authorization token, and Hourfleet uses the OAuth2.0 authorization scheme for its tokens (called *access_token*). Its an opaque token. You cannot decode it, or look inside it like other tokens.

Normally, users of the Hourfleet App (`https://yourcarshare.hourfleet.com`) are authenticated by giving their credentials (*username* + *password*) to the Hourfleet App. A 'Client Application' like the Hourfleet Web App itself then presents the user's credentials to Hourfleet servers (along with its credentials) to authenticate user, and an authorization token is issued and returned.

> Note: In all cases, in order for a user to authenticate, you also need a trusted 'Client Application' to manage the issuance of the token.

The token identifies the caller, and defines what the caller has access to. The token is then passed along with any call to authorize access to any API's in Hourfleet.

When using an API directly from other tools (like Postman) or from other systems or services on the internet, a users' credentials may not be directly available for you to use.

You have two standard choices in Hourfleet to get yourself an authorization token that will give you access to API's.

1. **Direct Authorization**:  You create a Client Application, that gives you a new set of credentials (`client_id` and `client_secret`) that you exchange for a token that gives you access to a restricted set of API's in Hourfleet. You store those credentials safely (never in public source code), and then use those credentials (*client_id* + *client_secret*) whenever you need to get a new authorization token.
2. **Delegated Authorization**: You create a Client Application, that gives you a new set of credentials that you use to ask an existing user of Hourfleet to grant you access to *their* API's (as them), by having them authenticate and then explicitly authorize you to obtain a token. This token grants you access to any API, as that user to access API's as that user.

> Note: Hourfleet support OAuth2 authorization. It supports the 'Client Credentials' grant and the 'Authorization Flow' grant. Other grant types are not available.

### Direct Authorization

This kind of authorization is granted to *Client Applications* directly.

Client Applications are created in the Hourfleet App by operators in the 'Operators' Dashboard. Their credentials are generated by Hourfleet, and stored by you safely. The credentials are used to obtain a token.

These `clientapplication` tokens will have access to a restricted set of permissions in Hourfleet. A subset of these permissions can also be requested and granted on each request for a token.

These tokens typically have access to API's that: control the configuration of your Car Share, manage its users, and have various administrative capabilities, reporting etc.

These tokens will not grant access to act as regular users (or API's that require a user to be known), since a client application will not have a user profile (They will not have: a name, an email address, a drivers license, nor verifications etc.). 

These tokens *cannot be used* to permit participation in booking, using or owning of cars, etc.

These tokens expire and cannot be renewed. (default expiry 15mins)

The OAuth2.0 flow that implements this kind of authorization is called the '[Client Credentials](https://medium.com/@darutk/diagrams-and-movies-of-all-the-oauth-2-0-flows-194f3c3ade85)' grant.

### Delegated Authorization

This kind of authorization is granted to *Client Applications* <u>indirectly</u> by an existing user in your Car Share. 

This is done by asking the user/person to grant the Client Application access to their account, and typically to some limited set of data within that account (i.e. my profile, my cars, my bookings, etc.). 

In this grant process a user (a person) is presented with a user interface that identifies who is requesting access (the Client Application), and what level of access is being requested. A user makes an explicit choice to approve the request or deny it. 

(This experience is a familiar experience for most people on the internet today, for example, when Twitter requests access to your Facebook friends list, you login to Facebook and grant Twitter access to your friends list).

![Code Grant](https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcQJNt7bWxtHA8FwyGFFIgThj6JxkbyBR1geC8SO8QV0MgnQhGdK)

Client Applications are created in the Hourfleet App by operators in the 'Operators' Dashboard.

These `user` tokens will have a subset of access to API's that relate to specific users of the Car Share, and as such the Client Application **acts on behalf of the user** who has granted them access. 

This token may have access to profile, verification data, etc. 

This token may allow participation in using and owning cars, etc.

These tokens expire (default expiry 15mins), but can be renewed by using a `refresh_token` which lasts for much longer. Typically, these tokens are stored and renewed so you can avoid involving the user giving their credentials again to you.

The OAuth2.0 flow that implements this kind of authorization is called the '[Authorization Code](https://medium.com/@darutk/diagrams-and-movies-of-all-the-oauth-2-0-flows-194f3c3ade85)' grant

### Obtaining Tokens

Use either the 'Client Credentials' grant or the 'Authorization Code' grant to obtain tokens from these URLs:

*	Authorization endpoint: `https://yourcarshare.hourfleet.com:4432/api/oauth/auth`

*	Token endpoint: `https://yourcarshare.hourfleet.com:4432/api/oauth/token`

> Note: Remember that tokens have a default expiry of 15mins.

You can use any tool like [PostMan](www.getpostman.com) to fetch a token.

#### Using Tokens

Once you have obtained a token using one of the methods above, you will need to include the token in every API call you make.

The token must be put into the `Authorization` header of the request in this format:

`Authorization: Bearer AAIAAMqDamBCSU7ITHnyx.....rest of the token......`

>  Note: If you use Delegated Authorization, you don't need to ask the user for permission once the token expires, you can use the `refresh_token` to obtain a fresh token and buy some more time.
