<!-- BEGIN_TF_DOCS -->
## Modules

No modules.

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_project_id"></a> [project\_id](#input\_project\_id) | The GCP project you want to enable APIs on | `string` | n/a | yes |
| <a name="input_activate_api_identities"></a> [activate\_api\_identities](#input\_activate\_api\_identities) | The list of service identities (Google Managed service account for the API) to force-create for the project (e.g. in order to grant additional roles).<br>    APIs in this list will automatically be appended to `activate_apis`.<br>    Not including the API in this list will follow the default behaviour for identity creation (which is usually when the first resource using the API is created).<br>    Any roles (e.g. service agent role) must be explicitly listed. See https://cloud.google.com/iam/docs/understanding-roles#service-agent-roles-roles for a list of related roles. | <pre>list(object({<br>    api   = string<br>    roles = list(string)<br>  }))</pre> | `[]` | no |
| <a name="input_activate_apis"></a> [activate\_apis](#input\_activate\_apis) | The list of apis to activate within the project | `list(string)` | `[]` | no |
| <a name="input_disable_dependent_services"></a> [disable\_dependent\_services](#input\_disable\_dependent\_services) | Whether services that are enabled and which depend on this service should also be disabled when this service is destroyed. https://www.terraform.io/docs/providers/google/r/google_project_service.html#disable_dependent_services | `bool` | `true` | no |
| <a name="input_disable_services_on_destroy"></a> [disable\_services\_on\_destroy](#input\_disable\_services\_on\_destroy) | Whether project services will be disabled when the resources are destroyed. https://www.terraform.io/docs/providers/google/r/google_project_service.html#disable_on_destroy | `bool` | `true` | no |
| <a name="input_enable_apis"></a> [enable\_apis](#input\_enable\_apis) | Whether to actually enable the APIs. If false, this module is a no-op. | `bool` | `true` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_enabled_apis"></a> [enabled\_apis](#output\_enabled\_apis) | Enabled APIs in the project |
| <a name="output_project_id"></a> [project\_id](#output\_project\_id) | The GCP project you want to enable APIs on |
<!-- END_TF_DOCS -->