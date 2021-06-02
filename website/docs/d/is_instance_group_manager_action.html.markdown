---
subcategory: "VPC infrastructure"
layout: "ibm"
page_title: "IBM : instance_group_manager_action"
description: |-
  Get information about  IBM VPC Instance group manager action.
---

# ibm\_is_instance_group_manager_action

Retrive action info of an instance group manager

## Example Usage

```hcl
data "ibm_is_instance_group_manager_action" "ibm_is_instance_group_manager_action" {
  instance_group         = "r006-76770f94-f7654-11e9-96e7-a77724435315"
  instance_group_manager = "r006-76770f94-f8764-11e9-96e7-a77726534315"
  name                   = "testinstancegroupmanageraction"
}
```

## Argument Reference

The following arguments are supported:

* `instance_group` - (Required, string) The instance group identifier.
* `instance_group_manager` - (Required, string) The instance group manager identifier of type scheduled.
* `name` - (Required, string) The instance group manager action name.

## Attribute Reference

The following attributes are exported:

* `id` - Id is the combination of instance group ID, instance group manager ID and instance group manager action ID
* `action_id` - The unique identifier of the ibm_is_instance_group_manager_action.
* `auto_delete` - If set to `true`, this scheduled action will be automatically deleted after it has finished and the `auto_delete_timeout` time has passed.
* `auto_delete_timeout` - Amount of time in hours that are required to pass before the scheduled action will be automatically deleted once it has finished. If this value is 0, the action will be deleted on completion.
* `created_at` - The date and time that the instance group manager action was created.
* `name` - The user-defined name for this instance group manager action. Names must be unique within the instance group manager.
* `resource_type` - The resource type.
* `status` - The status of the instance group action
    `active`: Action is ready to be run
    `completed`: Action was completed successfully
    `failed`: Action could not be completed successfully
    `incompatible`: Action parameters are not compatible with the group or manager
    `omitted`: Action was not applied because this action's manager was disabled.
* `updated_at` - The date and time that the instance group manager action was modified.
* `action_type` - The type of action for the instance group.
* `cron_spec` - The cron specification for a recurring scheduled action. Actions can be applied a maximum of one time within a 5 min period.
* `last_applied_at` - The date and time the scheduled action was last applied. If empty the action has never been applied.
* `next_run_at` - The date and time the scheduled action will next run. If empty the system is currently calculating the next run time.
* `membership_count` - The number of members the instance group should have at the scheduled time.
* `target_manager` - The unique identifier for this instance group manager of type autoscale.
* `target_manager_name` - Name of instance group manager of type autoscale.
* `max_membership_count` - The maximum number of members the instance group should have at the scheduled time.
* `min_membership_count` - The minimum number of members the instance group should have at the scheduled time. Default value is set to 1.
