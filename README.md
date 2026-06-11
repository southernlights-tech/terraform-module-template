# Terraform Module Template

Standard template for Southern Lights Tech Terraform modules.

## Usage

```hcl
module "example" {
  source = "github.com/southernlights-tech/terraform-module-template"
  
  # variables
}
```

## Requirements
| Name | Version |
|------|---------|
| terraform | >= 1.0 |

## Providers
No providers.

## Modules
No modules.

## Resources
No resources.

## Inputs
No inputs.

## Outputs

All modules in the Southern Lights Tech ecosystem follow the **Aggregated Map Pattern**. Instead of multiple individual outputs, the module exports a single `outputs` object.

| Name | Description |
|------|-------------|
| `outputs` | Aggregated map of all module outputs. Access via `module.<name>.outputs.<attr>` |

### Usage in Loops (`for_each`)
When using this module with `for_each`, you may need to explicitly cast or access the specific key to avoid type inference issues in complex dependencies:

```hcl
output "example" {
  value = { for k, v in module.my_module : k => v.outputs.some_id }
}
```
