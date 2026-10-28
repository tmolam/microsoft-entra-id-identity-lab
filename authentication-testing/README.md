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

## Test Procedure and Results

### Step 1: Initiate Authentication

I initiated the OAuth 2.0 Authorization Code flow in Postman. The process redirected me to Microsoft Entra ID, where I was prompted to sign in using my Entra account.

### Step 2: Obtain an Access Token

After successfully signing in, Postman completed the authorization flow and obtained a token.

### Step 3: Apply the Token

I selected **Use Token** in Postman to apply the obtained token to the API request.

### Step 4: Retrieve the User Profile

I executed the request, and Postman successfully returned my user profile from Microsoft Graph.

### Results

The test demonstrated that:

- The interactive sign-in process completed successfully.
- Postman successfully obtained a token through the configured Authorization Code flow.
- The token could be used to make a successful request for the signed-in user's profile.
- The configured authentication and delegated permission setup worked for this test scenario.

### Evidence

The following screenshots can be added to document the successful test:

1. **Authentication:** The Postman OAuth 2.0 configuration, with sensitive values hidden.
2. **Token acquisition:** Evidence that Postman successfully obtained a token, without displaying the token itself.
3. **Profile response:** The successful Microsoft Graph response, with personal information redacted where appropriate.

## Conclusion

This test provided practical experience configuring an OAuth 2.0 Authorization Code flow with Microsoft Entra ID and using Postman to validate delegated access to Microsoft Graph. It also demonstrated how application registration settings, redirect URIs, scopes, and client credentials work together in an authentication scenario.

## Key Learnings

- How OAuth 2.0 Authorization Code works with Microsoft Entra ID.
- How authorization and token endpoints are used in the flow.
- How OpenID Connect scopes differ from Microsoft Graph API permissions.
- How client credentials are supplied during token acquisition.
- How Postman can be used to test authentication and delegated API access.
