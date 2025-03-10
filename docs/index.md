---
layout: ""
page_title: "Provider: Event Store Cloud"
description: |-
  Terraform provider for Event Store Cloud
---

# Event Store Cloud Provider

The Event Store Cloud provider is used to interact with the resources supported by [Event Store Cloud][esc].
The provider needs to be configured with the proper credentials before it can be used.

Use the navigation to the left to read about the available resources.

## Configuration

The Event Store Cloud provider must be configured with an access token, however there are several additional
options which may be useful.

Provider configuration options are:

- `token` - (`ESC_TOKEN` via the environment) - *Required* - a refresh token for Event Store Cloud. This token can be created and displayed with the esc cli tool [esc cli](https://github.com/EventStore/esc), or via the "request refresh token" button on the [Authentification Tokens page](https://console.eventstore.cloud/authentication-tokens)  in the console. The token id displayed in the cloud console is not a valid token.
- `organization_id` - (`ESC_ORG_ID` via the environment) - *Required* - the identifier of the Event Store Cloud
  organization into which to provision resources.

- `url` - (`ESC_URL` via the environment) - *Optional* - the URL of the Event Store Cloud API. This defaults
  to the public cloud instance of Event Store Cloud, but may be overridden to provision resources in another
  instance.
- `token_store` - (`ESC_TOKEN_STORE` via the environment) - *Optional* - the location on the local filesystem
  of the token cache. This is shared with the Event Store Cloud CLI.

## Example Usage

```terraform
provider "eventstorecloud" {
  # optionally use ESC_TOKEN env var
  token = var.token

  # optionally use ESC_ORG_ID env var
  organization_id = var.organization_id

  # optionally use ESC_URL env var
  # you would normally not need to set it
  url = var.url

  # optionally use ESC_TOKEN_STORE env var
  # you would normally not need to set it
  token_store = var.token_store
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Optional

- **organization_id** (String)
- **token** (String, Sensitive)
- **token_store** (String)
- **url** (String)

[terraform]: (https://terraform.io)
[esc]: https://eventstore.com/event-store-cloud/
