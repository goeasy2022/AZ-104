# Azure Role Based Access Control

# 1. RBAC

RBAC means providing users access based on the **Role** they have

Azure RBAC is a system that allows control over who has access to which Azure resources, and what these users can do with those resources

Azure admin can assign a Role to a user based on different levels of accesses, Resource Level, Resource Group Level, Subscription Level, Management Group Level

It consists of three elements:

- Who has access to Azure resources?

  - Security Principal - An identity that gets the permissions. It could be a user, group, or a service principal

  ![image-20230320142153902](Azure Role Based Access Control.assets/image-20230320142153902.png)

- What they can do with those resources?

  - Role definition - A collection of permissions
  - **Reader:** Read Access
  - **Contributor:** Read, Update and Delete
  - **Owner:** Read, Update, Delete, Grant Access to other users
  - **Resource Specific:** Only give a user Administrator Role for virtual machine, not for other services
  - **Custom:** If none of the above roles meet the requirement, Azure administrators can create Custom Roles 

  ![image-20230320142215694](Azure Role Based Access Control.assets/image-20230320142215694.png)

- What is the Scope of access?

  - A way to constrain where those permissions are applicable
  - The role assigned to user,  can apply on which level; scope defines at what level that we are providing the access
  - management group > subscription > resource group > resource
  - If user is the admin for one particular resource, for example a virtual machine, then he/she cannot manage other virtual machines
  - We can also provide user access to the whole resource group, so the user can manage all resources in the resource group

- You can assign multiple Azure Roles to a user

  - if a user has been assigned both Reader and Contributor roles, then the Contributor role will take effective

- You can create your own Custom Azure Roles to assign Custom Permissions

- You can assign Roles using the Azure portal, Azure CLI, Azure PowerShell, Azure SDKs, or REST APIs

# 2. Demo RBAC

Reader - **View Only**

Contributor - **Read + Manage(Update/Delete)**

Owner - **Read+Manage+Grant Access to other users**

**User Access Administrator** - Specific Role to manage user access

**Deny Assignments**

- Similiar to Windows Deny Files Permission
- Blocks users from performing specific actions even if a role assignment allows it
- **Deny assignments** can only be created using **Azure Blue Prints** or **Managed Apps**

**Demo:**

1. Create a Resource Group **RG_RBAC_DEMO**

![image-20230320212247146](Azure Role Based Access Control.assets/image-20230320212247146.png)

![image-20230320212322152](Azure Role Based Access Control.assets/image-20230320212322152.png)

![image-20230320212345378](Azure Role Based Access Control.assets/image-20230320212345378.png)

![image-20230320212429086](Azure Role Based Access Control.assets/image-20230320212429086.png)

2. Create a VM and a Storage Account in the Resource Group

- Create a VM

![image-20230320212746309](Azure Role Based Access Control.assets/image-20230320212746309.png)

![image-20230320212905465](Azure Role Based Access Control.assets/image-20230320212905465.png)

![image-20230320212927375](Azure Role Based Access Control.assets/image-20230320212927375.png)

![image-20230320213138158](Azure Role Based Access Control.assets/image-20230320213138158.png)

![image-20230320213146382](Azure Role Based Access Control.assets/image-20230320213146382.png)

![image-20230320213204090](Azure Role Based Access Control.assets/image-20230320213204090.png)

![image-20230320213513139](Azure Role Based Access Control.assets/image-20230320213513139.png)

![image-20230320213712577](Azure Role Based Access Control.assets/image-20230320213712577.png)

- Create a Storage Account

![image-20230320213904299](Azure Role Based Access Control.assets/image-20230320213904299.png)

![image-20230320214332624](Azure Role Based Access Control.assets/image-20230320214332624.png)

![image-20230320214345689](Azure Role Based Access Control.assets/image-20230320214345689.png)

![image-20230320214359903](Azure Role Based Access Control.assets/image-20230320214359903.png)

![image-20230320214519271](Azure Role Based Access Control.assets/image-20230320214519271.png)

- Verify Resources created in the **RG_RBAC_DEMO** Resource Group

![image-20230320214916503](Azure Role Based Access Control.assets/image-20230320214916503.png)

3. Assign **Read Role** to user **Demo User-2** to this VM at **Resource Level**

**Access control(IAM)** in every Resource is used to control access to this Resource

**Azure Global Administrator** is the **Owner** of all resources, therefore Azure Global Administrator account can Grant access to other users for all Resources

![image-20230320215518510](Azure Role Based Access Control.assets/image-20230320215518510.png)

**Demo User-2** doesn't have any access to this VM

![image-20230320215657278](Azure Role Based Access Control.assets/image-20230320215657278.png)

Assign Read Access at Resource Level to Demo User-2

![image-20230320220849566](Azure Role Based Access Control.assets/image-20230320220849566.png)

![image-20230320220902609](Azure Role Based Access Control.assets/image-20230320220902609.png)

![image-20230320220915723](Azure Role Based Access Control.assets/image-20230320220915723.png)

![image-20230320220946005](Azure Role Based Access Control.assets/image-20230320220946005.png)

![image-20230320221000047](Azure Role Based Access Control.assets/image-20230320221000047.png)

![image-20230320221014281](Azure Role Based Access Control.assets/image-20230320221014281.png)

![image-20230320221037113](Azure Role Based Access Control.assets/image-20230320221037113.png)

**This Resource Level Read Access Role is restricted to this Virtual Machine Resource, Demo User-2 can only Read this Virtual Machine Resource, cannot Read the rest Resoureces such as Network Interface, Disk and other Resources**

**Resource Level access will be applied to the actual Resource, which is RG-RBAC-DEMO-VM1**

![image-20230320223813723](Azure Role Based Access Control.assets/image-20230320223813723.png)

4. Verify user can only Read VM, but not able to change VM or Read Storage Account

![image-20230320222159417](Azure Role Based Access Control.assets/image-20230320222159417.png)

![image-20230320222346279](Azure Role Based Access Control.assets/image-20230320222346279.png)

In **All resources** tab, this user can only see this Virtual Machine, but not able to see the **Storage Account**

![image-20230320222503567](Azure Role Based Access Control.assets/image-20230320222503567.png)

This user cannot manage this Virtual Machine, for example Restart VM

![image-20230320222625976](Azure Role Based Access Control.assets/image-20230320222625976.png)

This user can verify his access to this Virtual Machine Resource

![image-20230320223047599](Azure Role Based Access Control.assets/image-20230320223047599.png)

5. Assign Owner Role to Demo User-2 at Resource Group Level of RG_RBAC_DEMO Resource Group

Resource Group Level should be added within the Resource Group

![image-20230320223917880](Azure Role Based Access Control.assets/image-20230320223917880.png)

![image-20230320225001453](Azure Role Based Access Control.assets/image-20230320225001453.png)

![image-20230320225043051](Azure Role Based Access Control.assets/image-20230320225043051.png)

![image-20230320225055529](Azure Role Based Access Control.assets/image-20230320225055529.png)

![image-20230320225105982](Azure Role Based Access Control.assets/image-20230320225105982.png)

![image-20230320225117396](Azure Role Based Access Control.assets/image-20230320225117396.png)

**Demo User-2** will now have the **Owner** Role of RG_RBAC_DEMO Resource Group at Resource Group Level 

![image-20230320225313436](Azure Role Based Access Control.assets/image-20230320225313436.png)

![image-20230320225330338](Azure Role Based Access Control.assets/image-20230320225330338.png)

![image-20230320225427581](Azure Role Based Access Control.assets/image-20230320225427581.png)

6. Verify user can manage all Resources in the Resource Group

Restart VM

![image-20230320231432455](Azure Role Based Access Control.assets/image-20230320231432455.png)

![image-20230320231110564](Azure Role Based Access Control.assets/image-20230320231110564.png)

![image-20230320231121688](Azure Role Based Access Control.assets/image-20230320231121688.png)

![image-20230320231211944](Azure Role Based Access Control.assets/image-20230320231211944.png)

Delete all Resources in the Resource Group

![image-20230320231606635](Azure Role Based Access Control.assets/image-20230320231606635.png)

![image-20230320231658665](Azure Role Based Access Control.assets/image-20230320231658665.png)

![image-20230320231706376](Azure Role Based Access Control.assets/image-20230320231706376.png)

Delete Resource Group **RG_RBAC_DEMO**

![image-20230320232315228](Azure Role Based Access Control.assets/image-20230320232315228.png)

![image-20230320232331098](Azure Role Based Access Control.assets/image-20230320232331098.png)

![image-20230320232338470](Azure Role Based Access Control.assets/image-20230320232338470.png)

7. Assign **Contributor** role in the **Subscription Level**

Once a user is assigned **Contributor** role of a Subscription in the Subscription Level, this user will have access to manage(Read/Update/Delete) all Resource Groups and all Resources within this Subscription

![image-20230320233018550](Azure Role Based Access Control.assets/image-20230320233018550.png)

# 3. Azure RBAC - Custom Role

**Custom Role cannot be created at the Resource Level, it has to be created at minimum the Resource Group Level**

1. Create a Resource Group RG_RBAC_CUSTOM_ROLE

![image-20230321001333757](Azure Role Based Access Control.assets/image-20230321001333757.png)

2. Check Custom Role availability

Custom Role is available at minimum Resource Group Level

![image-20230321001401366](Azure Role Based Access Control.assets/image-20230321001401366.png)

Custom Role is not available at Resource Level

![image-20230321001510509](Azure Role Based Access Control.assets/image-20230321001510509.png)

3. Create Custom Role for Resource Group RG_RBAC_CUSTOM_ROLE

![image-20230321002614277](Azure Role Based Access Control.assets/image-20230321002614277.png)

- Clone a role

Clone an existing role then edit the permission

![image-20230321002638357](Azure Role Based Access Control.assets/image-20230321002638357.png)

![image-20230321002925109](Azure Role Based Access Control.assets/image-20230321002925109.png)

![image-20230321002718784](Azure Role Based Access Control.assets/image-20230321002718784.png)

![image-20230321002817911](Azure Role Based Access Control.assets/image-20230321002817911.png)

![image-20230321002833978](Azure Role Based Access Control.assets/image-20230321002833978.png)

![image-20230321002846126](Azure Role Based Access Control.assets/image-20230321002846126.png)

![image-20230321003014860](Azure Role Based Access Control.assets/image-20230321003014860.png)

![image-20230321003025888](Azure Role Based Access Control.assets/image-20230321003025888.png)

- Start from scratch

![image-20230321003115033](Azure Role Based Access Control.assets/image-20230321003115033.png)

![image-20230321003430178](Azure Role Based Access Control.assets/image-20230321003430178.png)

![image-20230321003458451](Azure Role Based Access Control.assets/image-20230321003458451.png)

Confirm the Roles required before creating Custom Roles

![image-20230321003543702](Azure Role Based Access Control.assets/image-20230321003543702.png)

![image-20230321003557200](Azure Role Based Access Control.assets/image-20230321003557200.png)

![image-20230321003617354](Azure Role Based Access Control.assets/image-20230321003617354.png)

Create this Role at Resource Group Level

![image-20230321003826564](Azure Role Based Access Control.assets/image-20230321003826564.png)

![image-20230321003904372](Azure Role Based Access Control.assets/image-20230321003904372.png)

![image-20230321003931312](Azure Role Based Access Control.assets/image-20230321003931312.png)

![image-20230321003946812](Azure Role Based Access Control.assets/image-20230321003946812.png)

![image-20230321004003626](Azure Role Based Access Control.assets/image-20230321004003626.png)

Verify the Custom Role created

![image-20230321004309991](Azure Role Based Access Control.assets/image-20230321004309991.png)

- Start from JSON

# 4. Quiz

![image-20230321004751044](Azure Role Based Access Control.assets/image-20230321004751044.png)

![image-20230321004758739](Azure Role Based Access Control.assets/image-20230321004758739.png)

![image-20230321004806282](Azure Role Based Access Control.assets/image-20230321004806282.png)



RBAC is assigned to Resource, Resource Group, Subscription and Management Group

Azure AD Role is assigned to Azure AD Resources such as User, Groups and Domains

**Azure AD Roles:**

- used for Azure AD related access
- roles only needed for Azure Active Directory, called Azure AD administrator roles
- Manage access to Azure Active Directory resources
- Scopt is at the **tenant** level
- Examples:
  - Creating users/Groups/Roles
  - Managing Password
  - Billing/Payment Info

**RBAC Roles:**

- used for non-Azure AD related access, such as SQL access, Virtual Machine access, etc
- RBAC Roles
- Manage access to Azure resources
- Scope can be specified at multiple levels(management group, subscription, resource group, resouce)
  - Create Database
  - Create/manage/delete VM and other resources
