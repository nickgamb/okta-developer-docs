* **Name**: Enter a name for the Identity Provider configuration.
* **Client Id**: Paste the client ID that you obtained from Azure AD when you configured the Identity Provider in the previous section.
* **Client Secret**: Paste the secret that you obtained in the previous section.
* **Authentication method reference (AMR) claims**: When `Trust AMR claims from this identity provider` is selected, Okta will evaluate any AMR claims sent in the request from the IdP to meet sign-on policy requirements. If the IdP does not support AMR claims, this option should not be enabled. 
* **Scopes**: Leave the defaults. These scopes are included when Okta makes an OpenID Connect request to Azure AD.

    > **Note:** By default, Okta requires the `email` attribute for a user. The `email` scope is required to create and link the user to Okta's Universal Directory.

In the **Endpoints** section:

Add the following endpoint URLs for the Azure AD Identity Provider that you are configuring. You obtained these in the previous section.

* **Issuer**: The identifier of the Azure AD Identity Provider: `https://login.microsoftonline.com/${Directory(tenant)ID}/v2.0`
* **Authorization endpoint**: The URL of the Azure AD OAuth 2.0 authorization endpoint. For example: `https://login.microsoftonline.com/${Directory(tenant)ID}/oauth2/v2.0/authorize`
* **Token endpoint**: The URL of the Azure AD token endpoint for obtaining access and ID tokens. For example: `https://login.microsoftonline.com/${Directory(tenant)ID}/oauth2/v2.0/token`
* **JWKS endpoint**: The URL of the Azure AD JSON Web Key Set document. This document contains signing keys that are used to validate the signatures from the provider. For example: `https://login.microsoftonline.com/${Directory(tenant)ID}/discovery/v2.0/keys`
