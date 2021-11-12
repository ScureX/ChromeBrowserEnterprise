# Authorization
Google APIs use the [OAuth 2.0 protocol](https://tools.ietf.org/html/rfc6749) for authentication and authorization. Google supports common OAuth 2.0 scenarios such as those for web server, client-side, installed, and limited-input device applications. All applications follow a basic pattern when accessing a Google API using OAuth 2.0. Check out [Using OAuth 2.0 to Access Google APIs ](https://developers.google.com/identity/protocols/oauth2) for more information.

## Authorize With Consent
Also known as '3-legged' OAuth without impersonation, is useful in scenarios where you want Google to handle user authentication, session selection, and user consent. The result is an authorization code, which the application can exchange for an access token and a refresh token. Postman collections in this repo are based on this authorization method. You can also use this method in scenarios for [Web server applications](https://developers.google.com/identity/protocols/oauth2/web-server), [desktop/mobile installed apps](https://developers.google.com/identity/protocols/oauth2/native-app), and (JavaScript applications)[https://developers.google.com/identity/protocols/oauth2/javascript-implicit-flow].

## Authorize With Impersonation
If you want request authorization without user consent, then use a service account for impersonation. Here the service account belongs to your application/service instead of to an individual end-user. Your application calls Google APIs on behalf of the service account, and user consent is not required. You can follow [this](https://developers.google.com/admin-sdk/directory/v1/guides/delegation) for creating a service account and getting the service account keys. Then grant (authorize) access by [delegating domain-wide authority](https://developers.google.com/admin-sdk/directory/v1/guides/delegation#delegate_domain-wide_authority_to_your_service_account) for the these scopes.
You can find a sample Postman request for impersonation using a service account in the [Google Service Account collection](/Google%20Service%20Account.postman_collection.json).

## Scopes
|Scope                          |Description                         |
|-------------------------------|-----------------------------|
| `https://www.googleapis.com/auth/admin.directory.device.chromebrowsers.readonly`|Chrome Browser Cloud Managment (CBCM) - get detailed information on enrolled browsers and enrollment tokens (read-only)|
| `https://www.googleapis.com/auth/admin.directory.device.chromebrowsers`|Chrome Browser Cloud Managment (CBCM) = lets you view and modify enrolled browsers and enrollment tokens|
| `https://www.googleapis.com/auth/chrome.management.reports.readonly`|Reports - Chrome versions and installed apps |
| `https://www.googleapis.com/auth/chrome.management.appdetails.readonly`|App Details- get detailed information about requested or specified apps |
| `https://www.googleapis.com/auth/chrome.management.policy.readonly`|Chrome Policy - lets you view Chrome policies for devices and users |
| `https://www.googleapis.com/auth/chrome.management.policy`|Chrome Policy - lets you view and modify Chrome policies for devices and users |
| `https://www.googleapis.com/auth/admin.directory.orgunit.readonly`|Org Units - lets you view organizational units |
| `https://www.googleapis.com/auth/admin.directory.orgunit`|Org Units - lets you view and modify organizational units |
| `https://www.googleapis.com/auth/admin.reports.audit.readonly`|Admin Console Reports - lets you view activities done by administrators using the Admin console and oAuth token acivities |

## Postman OAuth 2.0

For the sake of keeping things simple, the Postman collections use OAuth 2.0. You can configure that by following the [Authorization requests instructions](https://learning.postman.com/docs/sending-requests/authorization/#oauth-20).*