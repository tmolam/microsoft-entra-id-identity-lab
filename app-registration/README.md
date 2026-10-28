# Employee Portal — Microsoft Entra ID App Registration

## Overview

As part of my Microsoft Entra ID Identity Lab, I created a mock application named **Employee Portal** to explore application registration, authentication configuration, and Microsoft Graph permissions.

The app registration served as the foundation for subsequent authentication testing using Postman.

## Configuration

### 1. Application Registration

I registered an application named `Employee Portal` in Microsoft Entra ID and configured it as **Single Tenant**, limiting the intended sign-in audience to users in the application's home tenant.

### 2. Redirect URI

I added Postman's callback URL as a redirect URI for the application. This configuration allows the authentication flow to return its response to the configured callback endpoint.

### 3. Microsoft Graph Permissions

I configured the Microsoft Graph `User.Read` permission to support validation of the authentication flow and access to the signed-in user's profile information.

This permission was relevant to testing whether the application could successfully authenticate and make the intended Microsoft Graph request.

### 4. Client Secret

For this lab, I created a client secret to support the application's authentication configuration and testing.

A client secret is a credential that must be protected and should never be committed to a public repository. For production applications, I would evaluate certificate-based credentials or other supported credential-management approaches based on the application's architecture and security requirements.

## Validation

The app registration was prepared for authentication testing using Postman. The subsequent testing documented separately in this repository covers the authentication process and validation of the intended behavior.

## Key Learnings

- How to register an application in Microsoft Entra ID.
- The purpose of choosing a single-tenant application configuration.
- How redirect URIs support authentication flows.
- How Microsoft Graph permissions enable access to specific resources.
- The security considerations associated with client secrets and production credentials.
