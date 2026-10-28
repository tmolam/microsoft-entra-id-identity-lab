# OAuth 2.0 Authentication Testing with Postman

## Overview

I used Postman to configure and test an OAuth 2.0 Authorization Code flow for the `Employee Portal` application registered in Microsoft Entra ID.

The purpose was to explore how an application obtains tokens through an interactive authorization flow and how the resulting access token can be used to test Microsoft Graph access.

## Postman Configuration

I created an OAuth 2.0 API authorization configuration with the following settings:

| Setting | Configuration |
|---|---|
| Grant Type | Authorization Code |
| Authorization URL | Microsoft Entra ID tenant authorization endpoint |
| Access Token URL | Microsoft Entra ID tenant token endpoint |
| Scopes | `openid profile email User.Read` |
| Client Authentication | Send client credentials in request body |

The authorization and token endpoints were configured using my Microsoft Entra ID tenant endpoints.

## Scope Selection

I configured the following scopes:

- `openid` — requests OpenID Connect authentication.
- `profile` — requests access to standard profile claims.
- `email` — requests the email claim when available.
- `User.Read` — requests delegated permission to read the signed-in user's Microsoft Graph profile.

The OpenID Connect scopes support the sign-in process, while `User.Read` supports testing access to the Microsoft Graph API.

## Client Authentication

I configured Postman to send the client credentials in the request body when requesting a token. This configuration was used with the client secret created for the Employee Portal app registration.

The client secret is sensitive information and must not be included in screenshots, exported Postman collections, or public repository files.

## Validation

This setup provides a way to test the authorization flow and, after obtaining an access token, make a Microsoft Graph request to validate the intended delegated access.

The final documentation should record the actual outcome of the test, including whether token acquisition succeeded and whether the Microsoft Graph request returned the expected user profile information.

## Key Learnings

- How OAuth 2.0 Authorization Code works with Microsoft Entra ID.
- How authorization and token endpoints are used in the flow.
- How OpenID Connect scopes differ from Microsoft Graph API permissions.
- How client credentials are supplied during token acquisition.
- How Postman can be used to test authentication and delegated API access.
