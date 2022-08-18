# AzureAD

## Authentication

### Client credentials

When using [Microsoft Graph to manage Azure AD](https://docs.microsoft.com/en-us/graph/api/resources/azure-ad-overview?view=graph-rest-1.0) in a custom [NetIQ Identity Manager REST driver](https://www.netiq.com/documentation/identity-manager-48-drivers/generic_rest/data/driver-for-rest.html) use these settings to authenticate with client credentials:

- Authentication Method: `OAuth2.0`
  - OAuth2.0 Token Management: `Generate Bearer Token`
    - Access Token URL: `https://login.microsoftonline.com/{domain}/oauth2/v2.0/token`
    - Authorization Query Options
      - `grant_type`: `client_credentials`
      - `scope`: `https://graph.microsoft.com/.default`
      - `client_id`: `{id}`
    - Secret Authorization Query Options
      - `client_secret`: `{secret}`
    - Authorization Header Fields
      - `Content-Type`: `application/x-www-form-urlencoded`
- Truststore file: `/opt/netiq/common/jre/lib/security/cacerts`
- Base URL for REST Resources: `https://graph.microsoft.com/v1.0/directory`

Replace `{domain}`, `{id}`, and `{secret}` with the values specific to your tenant.

### Certificate (JWT)

_TBD_

## Resource types

### Administrative Units

See <https://docs.microsoft.com/en-us/graph/api/resources/administrativeunit?view=graph-rest-1.0>.
