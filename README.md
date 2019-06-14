# Ebay Oauth API

Fetch Oauth token for Ebay developer Api's using node js.

[![npm version](https://badge.fury.io/js/oauth-ebay.svg)](https://badge.fury.io/js/oauth-ebay)
[![Build Status](https://travis-ci.org/pajaydev/oauth-ebay.svg?branch=master)](https://travis-ci.org/pajaydev/oauth-ebay)

## Installation

```shell
npm install oauth-ebay
```
or 

```shell
yarn add oauth-ebay
```

## Useful links

Getting Client Id and Client Secret
```shell
https://developer.ebay.com/api-docs/static/oauth-credentials.html
```
Getting your redirect_uri value
```shell
https://developer.ebay.com/api-docs/static/oauth-redirect-uri.html
```
Specifying right scopes
```shell
https://developer.ebay.com/api-docs/static/oauth-scopes.html
```

## Oauth Access Tokens

* [Client credentials grant](#client-credentials-grant)
* [Authorization code grant](#authorization-code-grant)
* [Examples](#examples)


### Client credentials grant

#### Options

```javascript
const ebayAuthToken = new EbayAuthToken({
    clientId: "-- ClientID -- ", // required
    clientSecret: "-- Client Secret --", // required
    grantType: "-- Grant type --", // optional
    scope: scopes, // array of scopes
})
```
#### Example

```javascript
ebayAuthToken.getAccessToken().then((data) => {
    console.log(data);
}).catch((error) => {
    console.log(`Error to get Access token :${JSON.stringify(error)}`);
});
```

### Authorization code grant

#### Options

```javascript
const ebayAuthToken = new EbayAuthToken({ 
    clientId: "-- ClientID -- ", // required
    clientSecret: "-- CLient Secret --", // required
    grantType: "-- Grant type --", // optional
    scope: scopes,
    redirectUri: "-- redirect uri app name --" // required for getting user consent url.
})
```

#### Getting User Consent

```javascript
ebayAuthToken.getUserConsentUrl()
```

## Examples
[Click here](https://github.com/pajaydev/oauth-ebay/blob/master/example.js)

## Test
You can run using

```javascript
yarn add test
```