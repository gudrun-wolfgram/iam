---

copyright:

  years: 2015, 2018
lastupdated: "2018-08-02"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Managing service ID access policies
{: #serviceidpolicy}

When you create a service ID, you can assign service policies for that service ID to control the level of access that is allowed when it is used to authenticate with your services. You can update these assigned access policies at any time by changing an existing policy, deleting a policy, or assigning a new one.

**Note**: If you delete or edit an existing policy for a service ID currently being used, it might cause service interruption.

## Assigning new access

To assign access to all resources in a resource group or to just one service within a resource group, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access** &gt; **Service IDs**.
2. Select the service ID from the table that you want to assign a service policy for.
3. Click **Assign access**.
4. Select to **Assign by resource group**.
5. Select a resource group.
6. Choose a role for the **Assign access to resource group** field. This option allows the user to view the resource group on their dashboard, edit the resource group name, or manage user access to the group. You can select **No access**, if you want the user to have access to only the resource that you specify and not the group that it is assigned to.
7. Select a service within the resource group, or select to provide access to all services within the selected group.
8. Choose any combination of roles to assign the wanted access for the user. This access applies only to the resources that you selected for the policy. It does not give access to the actual container that is the resource group.
9. Select **Assign**.

To assign access to an individual resource in the account, complete the following steps:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access** &gt; **Service IDs**.
2. Select the service ID from the table that you want to assign a service policy for.
3. Click **Assign access**.
4. Select to **Assign by resource**.
5. Select a service.
6. Select **All current regions** or a specific region, if your are prompted.
7. Select **All current service instances** or select a specific service instance.
8. Depending on the service that you selected, you might see the following fields. If you do not enter values for these fields, the policy is assigned at the service instance level instead of the bucket level.
    * **Resource type**: Enter **bucket**.
    * **Resource ID**: Enter the name of your bucket.
9. Choose any combination of roles to assign the desired access for the user.
10. Select **Assign**.



## Editing existing access

To edit an existing policy:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access** &gt; **Service IDs**.
2. Select the service ID from the table that you want to edit a service policy for.
3. Identify the row of the policy that you want to edit, and select **Edit policy** from the **Actions** menu.
4. Make your changes, and then save the policy.

To update a service policy using the CLI, you can use the [ibmcloud iam service-policy-update](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_update) command.
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID [-v, --version VERSION] {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```
{: codeblock}

## Removing access

To remove an existing policy:

1. From the menu bar, click **Manage** &gt; **Security** &gt; **Identity and Access** &gt; **Service IDs**.
2. Select the service ID from the table that you want to delete a service policy for.
3. Identify the row of the policy that you want to delete, and select **Remove** from the **Actions** menu.
4. Review the details of the policy that you are about to remove, and then click **Remove** to confirm.

To delete a service policy using the CLI, you can use the [ibmcloud iam service-policy-delete](/docs/cli/reference/ibmcloud/cli_api_policy.html#ibmcloud_iam_service_policy_delete) command.
```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```
{: codeblock}
