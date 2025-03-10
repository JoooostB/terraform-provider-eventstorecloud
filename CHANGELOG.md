# 1.5.15 (May 18, 2022)

Enhancements:

* Added the ability to configure esoteric auth options

# 1.5.14 (April 27, 2022)

Enhancements:

* Added the ability to bypass local validation checks by setting the environment variable `ESC_BYPASS_VALIDATION`

# 1.5.13 (April 25, 2022)

Fixes:

* Server version `20.6` is now allowed again. While 20.6 cannot be used when creating new clusters, existing resources may already be using it, thus this plugin must allow it to avoid raising validation errors on otherwise innocuous actions such as "terraform plan"

# 1.5.12 (April 11, 2022)

Enhancements:

* Support added for gp3 disk types in AWS clusters, which includes the ability to set iops and throughput parameters

# 1.5.11 (January 19, 2022)

Enhancements:

* Allow server version "21.10" for managed clusters

# 1.5.10 (November 1, 2021)

Fixes:

* It's now possible to destroy defunct peering resources
* Updating a peering resource no longer causes the provider to enter into a loop

# 1.5.9 (October 18, 2021)

Enhancements:
* Add documentation for eventstorecloud_network data source
* Update documentation for eventstorecloud_project data source

# 1.5.8 (October 12, 2021)

Enhancements:

* Import functionality has been added for all resources
* Added a data source for networks
* General documentation and example improvements
* Improved error messages for peering resources in a defunct state
* Improved error messages for project data source
* Cluster names can now be updated

# 1.5.7 (September 2, 2021)

Enhancements:

* `resource/eventstorecloud_peering`: `provider_metadata` had been inadvertently changed into a set of maps. It's now back to being a map like before.

# 1.5.6 (August 4, 2021)

Enhancements:

* Allow server version "21.6" for managed clusters


# 1.5.5 (Jul 20, 2021)

Enhancements:

* Provider migrated to v2 Terraform plugin SDK
* Docs are now generated and made to fit the Terraform expected structure

# 1.5.4 (Jun 23, 2021)

Enhancements:

* Add `eventstorecloud_integration` resource

# 1.5.3 (Apr 8, 2021)

Enhancements:

* Add `eventstorecloud_scheduled_backup` resource

# 1.5.2 (Mar 26, 2021)

Fixes:

* Resources will now fail when encountering defunct state, instead of waiting for timeout

# 1.5.1 (Jan 26, 2021)

Enhancements:

* Add missing server version
* Add missing instance types
* Fix `ESC_ORG_ID` environment variable key

# 1.5.0 (Dec 11, 2020)

Enhancements:

* Publish to registry

# 1.4.0 (Dec 9, 2020)

Enhancements:

* Azure support

Fixes:

* Increase the allowed CIDR range for networks and peerings to accommodate GCP and Azure

# 1.3.0 (Nov 13, 2020)

Fixes:

* Pass the refresh token properly to ESC client 

# 1.2.0 (September 30, 2020)

Enhancements:

* `resource/eventstorecloud_managed_cluster`: `disk_size` can now be updated to expand the disk size of a cluster. ([#6](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/6))
* `resource/eventstorecloud_managed_cluster`: deleted managed clusters are correctly removed from state. ([#6](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/6))
* `resource/eventstorecloud_network`: deleted networks are correctly removed from state. ([#6](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/6))
* `resource/eventstorecloud_peering`: `provider_metadata` now contains `gcp_project_name` and `gcp_project_id`. `gcp_project_id` is suitable for passing to `google_compute_network_peering` resources. ([#6](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/6))
* `resource/eventstorecloud_peering`: deleted peerings are correctly removed from state. ([#6](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/6))

Fixes:

* ESC Client auth token directory gets created if it does not exist

## 1.1.0 (July 23, 2020)

Enhancements:

* `resource/eventstorecloud_peering`: Add computed property `provider_metadata`. ([#4](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/4))
* `resource/eventstorecloud_managed_cluster`: Correct `three-node-multi-zone` topology validation. ([#2](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/2))
* `resource/eventstorecloud_managed_cluster`: Add `projection_level` field. ([#5](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/5))
* Meaningful error messages from the Event Store Cloud API are now presented. ([#5](https://github.com/EventStore/terraform-provider-eventstorecloud/pull/5))

## 1.0.0 (June 28, 2020)

Features:

* Initial release of the provider
* **New Data Source:** `eventstorecloud_project`
* **New Resource:** `eventstorecloud_project`
* **New Resource:** `eventstorecloud_network`
* **New Resource:** `eventstorecloud_peering`
* **New Resource:** `eventstorecloud_managedcluster`
