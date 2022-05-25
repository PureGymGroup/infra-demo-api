<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_azurerm"></a> [azurerm](#requirement\_azurerm) | 3.3.0 |
| <a name="requirement_cloudflare"></a> [cloudflare](#requirement\_cloudflare) | 3.15.0 |
| <a name="requirement_random"></a> [random](#requirement\_random) | 3.1.3 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_azurerm"></a> [azurerm](#provider\_azurerm) | 3.3.0 |
| <a name="provider_cloudflare"></a> [cloudflare](#provider\_cloudflare) | 3.15.0 |
| <a name="provider_random"></a> [random](#provider\_random) | 3.1.3 |
| <a name="provider_time"></a> [time](#provider\_time) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [azurerm_application_gateway.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/application_gateway) | resource |
| [azurerm_key_vault.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/key_vault) | resource |
| [azurerm_key_vault_secret.pgadmin](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/key_vault_secret) | resource |
| [azurerm_network_security_group.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/network_security_group) | resource |
| [azurerm_network_security_rule.rules](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/network_security_rule) | resource |
| [azurerm_postgresql_active_directory_administrator.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/postgresql_active_directory_administrator) | resource |
| [azurerm_postgresql_database.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/postgresql_database) | resource |
| [azurerm_postgresql_firewall_rule.backstage_pg_fw](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/postgresql_firewall_rule) | resource |
| [azurerm_postgresql_server.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/postgresql_server) | resource |
| [azurerm_public_ip.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/public_ip) | resource |
| [azurerm_resource_group.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/resource_group) | resource |
| [azurerm_role_assignment.akv_kubelet](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/role_assignment) | resource |
| [azurerm_role_assignment.k8s](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/role_assignment) | resource |
| [azurerm_role_assignment.service_principle](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/role_assignment) | resource |
| [azurerm_storage_account.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/storage_account) | resource |
| [azurerm_storage_account_network_rules.object](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/storage_account_network_rules) | resource |
| [azurerm_storage_container.backstage](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/storage_container) | resource |
| [azurerm_subnet.frontend](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/subnet) | resource |
| [azurerm_user_assigned_identity.k8s](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/resources/user_assigned_identity) | resource |
| [random_id.env](https://registry.terraform.io/providers/hashicorp/random/3.1.3/docs/resources/id) | resource |
| [random_password.password](https://registry.terraform.io/providers/hashicorp/random/3.1.3/docs/resources/password) | resource |
| [time_static.creationdate](https://registry.terraform.io/providers/hashicorp/time/latest/docs/resources/static) | resource |
| [azurerm_client_config.current](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/data-sources/client_config) | data source |
| [azurerm_kubernetes_cluster.this](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/data-sources/kubernetes_cluster) | data source |
| [azurerm_virtual_network.datatools](https://registry.terraform.io/providers/hashicorp/azurerm/3.3.0/docs/data-sources/virtual_network) | data source |
| [cloudflare_ip_ranges.cloudflare](https://registry.terraform.io/providers/cloudflare/cloudflare/3.15.0/docs/data-sources/ip_ranges) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_admin_username"></a> [admin\_username](#input\_admin\_username) | Admin username for postgres | `string` | n/a | yes |
| <a name="input_aks_cluster_ip"></a> [aks\_cluster\_ip](#input\_aks\_cluster\_ip) | IP address of the AKS cluster | `string` | `null` | no |
| <a name="input_aks_name"></a> [aks\_name](#input\_aks\_name) | Name of the AKS cluster to datasource | `string` | n/a | yes |
| <a name="input_aks_resource_group_name"></a> [aks\_resource\_group\_name](#input\_aks\_resource\_group\_name) | Resource group the aforementioned AKS cluster resides in. | `string` | n/a | yes |
| <a name="input_app_gateway_sku_capacity"></a> [app\_gateway\_sku\_capacity](#input\_app\_gateway\_sku\_capacity) | The Capacity of the SKU to use for this Application Gateway. When using a V1 SKU this value must be between 1 and 32, and 1 to 125 for a V2 SKU. This property is optional if autoscale\_configuration is set | `number` | n/a | yes |
| <a name="input_app_gateway_sku_name"></a> [app\_gateway\_sku\_name](#input\_app\_gateway\_sku\_name) | The Name of the SKU to use for this Application Gateway. Possible values are Standard\_Small, Standard\_Medium, Standard\_Large, Standard\_v2, WAF\_Medium, WAF\_Large, and WAF\_v2 | `string` | n/a | yes |
| <a name="input_app_gateway_sku_tier"></a> [app\_gateway\_sku\_tier](#input\_app\_gateway\_sku\_tier) | The Tier of the SKU to use for this Application Gateway. Possible values are Standard, Standard\_v2, WAF and WAF\_v2 | `string` | n/a | yes |
| <a name="input_cloudflare_api_token"></a> [cloudflare\_api\_token](#input\_cloudflare\_api\_token) | API token | `string` | n/a | yes |
| <a name="input_environment"></a> [environment](#input\_environment) | Environment to deploy into | `string` | n/a | yes |
| <a name="input_location"></a> [location](#input\_location) | Azure region to deploy resources | `string` | n/a | yes |
| <a name="input_nacls_bypass"></a> [nacls\_bypass](#input\_nacls\_bypass) | Specifies which traffic can bypass the network rules. Possible values are AzureServices and None. | `string` | `"AzureServices"` | no |
| <a name="input_nacls_default_action"></a> [nacls\_default\_action](#input\_nacls\_default\_action) | The Default Action to use when no rules match from ip\_rules / virtual\_network\_subnet\_ids. Possible values are Allow and Deny. | `string` | `"Allow"` | no |
| <a name="input_nacls_ip_rules"></a> [nacls\_ip\_rules](#input\_nacls\_ip\_rules) | One or more IP Addresses, or CIDR Blocks which should be able to access the Key Vault. | `set(string)` | `null` | no |
| <a name="input_postgres_firewall_ips"></a> [postgres\_firewall\_ips](#input\_postgres\_firewall\_ips) | Comma seperated list of IP's allowed to access postgres database | `string` | n/a | yes |
| <a name="input_postgres_sku"></a> [postgres\_sku](#input\_postgres\_sku) | SKU of postgres server | `string` | `"B_Gen5_2"` | no |
| <a name="input_postgres_version"></a> [postgres\_version](#input\_postgres\_version) | Postgres server version | `string` | `"11"` | no |
| <a name="input_service_principle_id"></a> [service\_principle\_id](#input\_service\_principle\_id) | The AzureRM datasource for azuread\_application object\_id does not output the correct ID. | `string` | n/a | yes |
| <a name="input_vnet_name"></a> [vnet\_name](#input\_vnet\_name) | Name of the VNET to deeploy the Application Gateway into. | `string` | n/a | yes |
| <a name="input_vnet_resource_group"></a> [vnet\_resource\_group](#input\_vnet\_resource\_group) | Resource Group of the aforementioned VNET. | `string` | n/a | yes |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_kv_id"></a> [kv\_id](#output\_kv\_id) | n/a |
| <a name="output_kv_name"></a> [kv\_name](#output\_kv\_name) | n/a |
| <a name="output_kv_vault_uri"></a> [kv\_vault\_uri](#output\_kv\_vault\_uri) | n/a |
| <a name="output_primary_access_key"></a> [primary\_access\_key](#output\_primary\_access\_key) | n/a |
| <a name="output_secondary_access_key"></a> [secondary\_access\_key](#output\_secondary\_access\_key) | n/a |
<!-- END_TF_DOCS -->