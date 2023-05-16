# Azure Subscriptions and Governance

# 1. Subscription

Subscription is a separate service in Azure



<img src="Azure Subscriptions and Governance.assets/image-20230321185716970.png" alt="image-20230321185716970" style="zoom:80%;" />

![image-20230321190722842](Azure Subscriptions and Governance.assets/image-20230321190722842.png)

A resource is created under one Subscription



Using Azure requires an Azure subscription, without a subscription, you cannot use Azure

An Azure subscription is a logical unit of Azure services that links to an Azure account. It also allows you to provision resources

A subscription provides you with authenticated and authorized access to Azure products and services

Azure generates separate billing reports and invoices for each subscription

There are two types of subscription boundaries:

- Billing boundary
- Access control boundary

Administrator can create sepearte subscription based on:

- Environment: Development, Testing, Security, or to isolate data for compliance reasons
- Organizational Structure: IT, HR, Admin and so on
- Billing: Manage and Track costs based on your needs, For example - Production, Test and Dev

One Azure account can have multiple Subscriptions. 

Each Subscription will decide two things:

- Billing: how you are charged by Azure 

  Each Subscriotion has its own monthly bill. For example, If you have 5 subscriptions, then you will have 5 bills each month.

- Access: define your access to different resources. For example, Free Subscription doesn't have access to create expensive virtual machines; how many virtual machine can be created, how much you can spend each month, etc.

- For example: One company can set up two subscriptions, one for Development environment and one for production environment. For Dev environment, monthly bill can be restricted within certain amount, as for Prod environment, there won't be such restriction.

 

![image-20230321191145000](Azure Subscriptions and Governance.assets/image-20230321191145000.png)

Different types of Subscription:

	- Free: An email address and a credit card are required to sign up for a free trial subscription that provides $200 credit for the first 30 days and 12 months of restricted access
	- Pay-Per-Use: Charges monthly based on Cloud resource use
	- Enterprise: A single Enterprise agreement is established for large subscription purchases, including savings for new licenses and software assurance
	- Student: This membership includes $100 for 12 months and may be activated without a credit card

**Use subscription to control billing and restrict access **

# 2. Create a Subscription

![image-20230321193957455](Azure Subscriptions and Governance.assets/image-20230321193957455.png)

![image-20230321194024695](Azure Subscriptions and Governance.assets/image-20230321194024695.png)

![image-20230321194321172](Azure Subscriptions and Governance.assets/image-20230321194321172.png)

![image-20230321194437668](Azure Subscriptions and Governance.assets/image-20230321194437668.png)

**One subscription** can only be associated with one **Active Directory**

![image-20230321194606824](Azure Subscriptions and Governance.assets/image-20230321194606824.png)

![image-20230321194644995](Azure Subscriptions and Governance.assets/image-20230321194644995.png)

![image-20230321194704620](Azure Subscriptions and Governance.assets/image-20230321194704620.png)

![image-20230321194712527](Azure Subscriptions and Governance.assets/image-20230321194712527.png)

![image-20230321200410689](Azure Subscriptions and Governance.assets/image-20230321200410689.png)

If you don't see the new subscription showing up, go to Switch Directory and tick the new subscrition created

![image-20230321200511260](Azure Subscriptions and Governance.assets/image-20230321200511260.png)

![image-20230321201012324](Azure Subscriptions and Governance.assets/image-20230321201012324.png)

Then go back to Subscription

![image-20230321201218268](Azure Subscriptions and Governance.assets/image-20230321201218268.png)

# 3. Trust Relation between AAD/Tenant and Subscription

An Azure subscription has a trust relationship with Azure Active Directory (Azure AD)

A Subscription trusts Azure AD to authenticate users, services and devices

**Multiple Subscriptions can trust the same Azure AD Directory**

**Each Subscription can only trust a single directory, and each Subscription has to be associated with one Azure Active Directory**

Azure tenant and Azure Active Directory has one to one relationship

![image-20230321211237768](Azure Subscriptions and Governance.assets/image-20230321211237768.png)

Example: **One subsction can only be associated to one Azure Active Directory**

![image-20230321211111458](Azure Subscriptions and Governance.assets/image-20230321211111458.png)

Example: Associate one Subsctiption to another Azure Active Directory

![image-20230321212333509](Azure Subscriptions and Governance.assets/image-20230321212333509.png)

![image-20230321212351168](Azure Subscriptions and Governance.assets/image-20230321212351168.png)

![image-20230321212432721](Azure Subscriptions and Governance.assets/image-20230321212432721.png)

![image-20230321212456927](Azure Subscriptions and Governance.assets/image-20230321212456927.png)

Once this Subscription is changed to another Azure Active Directory, you will need to switch to the right Active Directory to see the Subscription

![image-20230321214658604](Azure Subscriptions and Governance.assets/image-20230321214658604.png)

![image-20230321214711081](Azure Subscriptions and Governance.assets/image-20230321214711081.png)

![image-20230321214750501](Azure Subscriptions and Governance.assets/image-20230321214750501.png)

Switch back to Default Directory

# 4. Azure Tags

Use Tags to categorize Resources and Resource Groups

Tag consists of **Name** and **Value**. With Tags, you can filter Resources and Resource Groups

Example: Create Tags for Resources, Edit view columns and add Filter

- demovm1-vnet

![image-20230321220958037](Azure Subscriptions and Governance.assets/image-20230321220958037.png)

- demovm1-ip

![image-20230321221144244](Azure Subscriptions and Governance.assets/image-20230321221144244.png)

![image-20230321221311084](Azure Subscriptions and Governance.assets/image-20230321221311084.png)

![image-20230321221326168](Azure Subscriptions and Governance.assets/image-20230321221326168.png)

You can organize the sequence by dragging the bar up and down

![image-20230321221431865](Azure Subscriptions and Governance.assets/image-20230321221431865.png)

![image-20230321221511479](Azure Subscriptions and Governance.assets/image-20230321221511479.png)

![image-20230321221619266](Azure Subscriptions and Governance.assets/image-20230321221619266.png)

![image-20230321221820307](Azure Subscriptions and Governance.assets/image-20230321221820307.png)

![image-20230321221853477](Azure Subscriptions and Governance.assets/image-20230321221853477.png)

Tags is also an Azure service, you can check all resources of one Tag

![image-20230321222021872](Azure Subscriptions and Governance.assets/image-20230321222021872.png)

![image-20230321222033302](Azure Subscriptions and Governance.assets/image-20230321222033302.png)

You can also analyze Cost information based on Tags

![image-20230321222215754](Azure Subscriptions and Governance.assets/image-20230321222215754.png)

**Tags will show up after in a day or 2 once created, so we cannot see Tags at the moment**

But, tomorrow, we can filter by Tags

![image-20230321222347570](Azure Subscriptions and Governance.assets/image-20230321222347570.png)

Summary:

- Azure Tags are the **name:value** pairs that help to organize the Azure Resources in the Azure Portal
- Azure Tags are simply **Labels** that you can attach to your Azure Resources
- You can use tags to easily group and classify Resources and Assets in Azure
  - For example, get the costs generated by Resources having the same Tag applied
  - Tagging is a Primary way to understand the data in any cost or Billling Report
- Resources don't inherit any Azure Tags applied at the Resource Group Level

Example: Apply Tag "Customer:Ebay" to Resource Group "demovm", this Tag won't be applied to Resources of **demovm** Resource Group

![image-20230321222919139](Azure Subscriptions and Governance.assets/image-20230321222919139.png)

![image-20230321222939565](Azure Subscriptions and Governance.assets/image-20230321222939565.png)

![image-20230321223020915](Azure Subscriptions and Governance.assets/image-20230321223020915.png)

Confirm Resources won't inherit the Tag applied at the Group Level

![image-20230321223112200](Azure Subscriptions and Governance.assets/image-20230321223112200.png)

![image-20230321223128924](Azure Subscriptions and Governance.assets/image-20230321223128924.png)

- It's a fundamental part of any well-managed environment. It's also the first step in establishing proper governance of any environment

- Azure Policy can be used to enforce Tagging Rules and Conventions
  - For example, you can require that certain tags must be added to new resources as they are provisioned

# 5. Azure Resource Locks

With Resource Locks, accident resource modification and delete can be prevented.

## 5.1 Resource Lock

- Read Only Lock: No one can make any changes of this Resource, No one can delete this Resource

**demovm1-ip**: apply Tag will fail

![image-20230321232351690](Azure Subscriptions and Governance.assets/image-20230321232351690.png)

![image-20230321232619730](Azure Subscriptions and Governance.assets/image-20230321232619730.png)

![image-20230321233019266](Azure Subscriptions and Governance.assets/image-20230321233019266.png)

![image-20230321233032521](Azure Subscriptions and Governance.assets/image-20230321233032521.png)

![image-20230321233045857](Azure Subscriptions and Governance.assets/image-20230321233045857.png)

**demovm1-ip**: delete Resource will fail

![image-20230321233143601](Azure Subscriptions and Governance.assets/image-20230321233143601.png)

![image-20230321233159484](Azure Subscriptions and Governance.assets/image-20230321233159484.png)

- Delete Lock: No one can delete this Resource, but can modify

Delete Read Only Lock

![image-20230321233314235](Azure Subscriptions and Governance.assets/image-20230321233314235.png)

Add Delete Lock

![image-20230321233342123](Azure Subscriptions and Governance.assets/image-20230321233342123.png)

![image-20230321233412627](Azure Subscriptions and Governance.assets/image-20230321233412627.png)

![image-20230321233423094](Azure Subscriptions and Governance.assets/image-20230321233423094.png)

Unable to delete

![image-20230321233452312](Azure Subscriptions and Governance.assets/image-20230321233452312.png)

But able to modify, for example, apply Tag

![image-20230321233642012](Azure Subscriptions and Governance.assets/image-20230321233642012.png)

![image-20230321233710038](Azure Subscriptions and Governance.assets/image-20230321233710038.png)

With Lock, even the Owner of the Resource cannot perform actions

## 5.2 Resource Group Lock

Resource Group Lock will be applied to **ALL Resources** in the Resource Group

Remove ip Resource Delete Lock

![image-20230322003617019](Azure Subscriptions and Governance.assets/image-20230322003617019.png)

Apply Delete Lock to Resource Group

![image-20230322003738533](Azure Subscriptions and Governance.assets/image-20230322003738533.png)

![image-20230322003917584](Azure Subscriptions and Governance.assets/image-20230322003917584.png)

ip Resource can be managed by Lock, nsg and vnet cannot

![image-20230322003950584](Azure Subscriptions and Governance.assets/image-20230322003950584.png)

![image-20230322004027016](Azure Subscriptions and Governance.assets/image-20230322004027016.png)

# 6. Moving Resources

Move Resources between Resource Group and Subscription

Move any Resource from one RG to another RG

Move any Resource from one Subscription to another

The physical location of  Resources moved won't change as location information is managed by RG as meta data. For example, if a Virtual Machine is in East US, then we move it to another Resource Group and this Group is East-EU, the Virtual Machine's physical location is still in East-US

Therefore, the location of Resources can be different to their Resources Groups

East US:

![image-20230322004927115](Azure Subscriptions and Governance.assets/image-20230322004927115.png)

![image-20230322004936122](Azure Subscriptions and Governance.assets/image-20230322004936122.png)

![image-20230322005221890](Azure Subscriptions and Governance.assets/image-20230322005221890.png)

![image-20230322005422683](Azure Subscriptions and Governance.assets/image-20230322005422683.png)

![image-20230322005506490](Azure Subscriptions and Governance.assets/image-20230322005506490.png)

When moving a Resource, for example a Virtual Machine, it is suggested to move all Resources related together

![image-20230322005935697](Azure Subscriptions and Governance.assets/image-20230322005935697.png)

Move to West Europe

![image-20230322010058341](Azure Subscriptions and Governance.assets/image-20230322010058341.png)

![image-20230322010121962](Azure Subscriptions and Governance.assets/image-20230322010121962.png)

![image-20230322010152280](Azure Subscriptions and Governance.assets/image-20230322010152280.png)

![image-20230322010203471](Azure Subscriptions and Governance.assets/image-20230322010203471.png)

**Disk cannot be moved**

![image-20230322010232534](Azure Subscriptions and Governance.assets/image-20230322010232534.png)

![image-20230322010428994](Azure Subscriptions and Governance.assets/image-20230322010428994.png)

**Resource and RGs with Read Only Lock cannot be moved**

![image-20230322011118576](Azure Subscriptions and Governance.assets/image-20230322011118576.png)

![image-20230322011420254](Azure Subscriptions and Governance.assets/image-20230322011420254.png)

**?????????**

# 7. Azure Policy

Apply restrictions, rules and enforcement to avoid mistake like creating a very expensive Virtual Machine

All services -- Management + governance - Policy

![image-20230322012600068](Azure Subscriptions and Governance.assets/image-20230322012600068.png)

![image-20230322012612587](Azure Subscriptions and Governance.assets/image-20230322012612587.png)

Click **Assignments** to assign policy/rule on our Resources

**Policy can be assigned at either Subscription Level or RG Level**

![image-20230322012749446](Azure Subscriptions and Governance.assets/image-20230322012749446.png)

![image-20230322012852580](Azure Subscriptions and Governance.assets/image-20230322012852580.png)

**Policy Definition**

![image-20230322012931787](Azure Subscriptions and Governance.assets/image-20230322012931787.png)

Only specific locations are allowed to choose when creating **Resource Group**

![image-20230322013121764](Azure Subscriptions and Governance.assets/image-20230322013121764.png)

![image-20230322013129911](Azure Subscriptions and Governance.assets/image-20230322013129911.png)

![image-20230322013236346](Azure Subscriptions and Governance.assets/image-20230322013236346.png)

![image-20230322013438059](Azure Subscriptions and Governance.assets/image-20230322013438059.png)

![image-20230322013519214](Azure Subscriptions and Governance.assets/image-20230322013519214.png)

![image-20230322013546861](Azure Subscriptions and Governance.assets/image-20230322013546861.png)

![image-20230322013557021](Azure Subscriptions and Governance.assets/image-20230322013557021.png)

**New Policy will take 30 mins to be effective**

Check All Existing Policies available

![image-20230322013921706](Azure Subscriptions and Governance.assets/image-20230322013921706.png)

There are two types of Definitios:

![image-20230322014010043](Azure Subscriptions and Governance.assets/image-20230322014010043.png)

- Policy
- Initiative: a group of different policies

![image-20230322014059196](Azure Subscriptions and Governance.assets/image-20230322014059196.png)

![image-20230322014112547](Azure Subscriptions and Governance.assets/image-20230322014112547.png)

**Remediation:** Enfore defined policies on defined RGs

![image-20230322014523284](Azure Subscriptions and Governance.assets/image-20230322014523284.png)

![image-20230322014530807](Azure Subscriptions and Governance.assets/image-20230322014530807.png)

**Once you apply a policy, those existing Resources that are not complied with this policy won't be deleted, but will show as Non-complaint**

![image-20230322014743607](Azure Subscriptions and Governance.assets/image-20230322014743607.png)

![image-20230322014832743](Azure Subscriptions and Governance.assets/image-20230322014832743.png)

![image-20230322014845481](Azure Subscriptions and Governance.assets/image-20230322014845481.png)

Summary:

Azure Policy can help you control or restrict or audit your resources

Enforce rules on Azure Resource configurations to make sure they remain complaint with corporate standards

You can apply individual policy or group of policy (Initiatives)

Two important task:

- Prevent Non-complaint resources from being created
- Highlights existing resources that aren't complaint with the policies

Examples:

- Allow only a certain size for the VMs to be provisioned
- Mandatory Tags to be created while provisioing Resources
- MFA should be enabled on accountw with write permissions on your subscription

Assign Policy within a specific scope(management group, a single subscription, or a resource group)

Policies assignments are inherited by all Child Resources within the scope

- You can exclude specific Child Resources you need to be exempt from the Policy assignment

You can review the Noncpmpliant Policy results and take any action that's needed

**Delete assignment**

![image-20230322015854824](Azure Subscriptions and Governance.assets/image-20230322015854824.png)

![image-20230322015904114](Azure Subscriptions and Governance.assets/image-20230322015904114.png)

![image-20230322015917436](Azure Subscriptions and Governance.assets/image-20230322015917436.png)

**Delete of assignment will also take 30 mins to be effective**

# 8. Quiz - Azure Policy

![image-20230322020158566](Azure Subscriptions and Governance.assets/image-20230322020158566.png)

![image-20230322020207869](Azure Subscriptions and Governance.assets/image-20230322020207869.png)

# 9. Management Groups

Organize multiple subscriptions as a single management entity

![image-20230322200602622](Azure Subscriptions and Governance.assets/image-20230322200602622.png)

- Management groups let you organize multiple subscriptions as a single management entity to facilitate easier management
- You can create management groups in a hierarchical structure with the top level of the hierarchy at the tenant level and containing all subscriptions in the tenant

- **Root Management Group is the top level of the hierarchy**
- Any conditions applied to a management group apply to all subscriptions contained in that management group object

- Each management group and subscription can support only one parent
- Each management group can have many children
- The root management group can't be moved or deleted, unlike other management groups

Demo:

![image-20230322201734492](Azure Subscriptions and Governance.assets/image-20230322201734492.png)

![image-20230322201821908](Azure Subscriptions and Governance.assets/image-20230322201821908.png)

![image-20230322201841588](Azure Subscriptions and Governance.assets/image-20230322201841588.png)

![image-20230322202050628](Azure Subscriptions and Governance.assets/image-20230322202050628.png)

Be default , even the global admin doesn't have access to manage Root Management Group. 

We need to elevate Global Admin's access first

![image-20230322202455452](Azure Subscriptions and Governance.assets/image-20230322202455452.png)

![image-20230322202523161](Azure Subscriptions and Governance.assets/image-20230322202523161.png)

![image-20230322203838170](Azure Subscriptions and Governance.assets/image-20230322203838170.png)

Create child management group within IT management group

![image-20230322203627004](Azure Subscriptions and Governance.assets/image-20230322203627004.png)

![image-20230322203643386](Azure Subscriptions and Governance.assets/image-20230322203643386.png)

Add Subcription to DevOps management group. 

If there is subsciption that hasn't been associated to other management groups, then you can add it to a management group.

![image-20230322204129688](Azure Subscriptions and Governance.assets/image-20230322204129688.png)

Define Security and Policy at the management group level.

Security and Policy created at the management group level will be inherited to child management group and child subscription.

![image-20230322204244859](Azure Subscriptions and Governance.assets/image-20230322204244859.png)

![image-20230322204254930](Azure Subscriptions and Governance.assets/image-20230322204254930.png)

# 10. Azure Cost Management and Billing

![image-20230322204744440](Azure Subscriptions and Governance.assets/image-20230322204744440.png)

This is a built-in service that gives you a breakdown of the usage and cost of your Azure resources

This allows you to see what is costing you money and how it compares against your budget

You use Cost Management + Billing features to:

- Conduct billing administrative tasks such as paying your bill
- Manage billing access to costs
- Download cost and usage data that was used to generated your monthly invoice
- Proactively apply data analusis to your costs
- Set spending thresholds
- Identify opportunities for workload changes that can optimize your spending

Cost can be viewed based on Subscription, Resource Group, Region, etc

![image-20230322205715218](Azure Subscriptions and Governance.assets/image-20230322205715218.png)

Budget can also be configured according to Subscription, Resource Group and so on

![image-20230322205813113](Azure Subscriptions and Governance.assets/image-20230322205813113.png)

Advisor recommendations: Provide suggestion on how to reduce cost

![image-20230322210135153](Azure Subscriptions and Governance.assets/image-20230322210135153.png)

# 11. Quiz - Configure Subscriptions

![image-20230322210700379](Azure Subscriptions and Governance.assets/image-20230322210700379.png)

![image-20230322210741030](Azure Subscriptions and Governance.assets/image-20230322210741030.png)
