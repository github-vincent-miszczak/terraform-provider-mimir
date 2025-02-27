---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "mimir_rule_group_recording Resource - terraform-provider-mimir"
subcategory: ""
description: |-
  
---

# mimir_rule_group_recording (Resource)

Manage prometheus recording rule group.

For full documention on prometheus recording rule, see [here](https://prometheus.io/docs/prometheus/latest/configuration/recording_rules/)

## Basic Example

```hcl
resource "mimir_rule_group_recording" "record" {
  name      = "test1"
  namespace = "namespace1"
  rule {
    expr   = "sum by (job) (http_inprogress_requests)"
    record = "job:http_inprogress_requests:sum"
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Recording Rule group name
- `rule` (Block List, Min: 1) (see [below for nested schema](#nestedblock--rule))

### Optional

- `namespace` (String) Recording Rule group namespace

### Read-Only

- `id` (String) The ID of this resource.

<a id="nestedblock--rule"></a>
### Nested Schema for `rule`

Required:

- `expr` (String) The PromQL expression to evaluate.
- `record` (String) The name of the time series to output to.

Optional:

- `labels` (Map of String) Labels to add or overwrite before storing the result.


