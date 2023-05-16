# Azure Identities and Governance

# 1. Azure Active Directory

**Azure Active Directory:** 

- AAD has Four editions:
  - Free: MFA, SSO, Basic Security and Usage Reports, User Management
  - Office 365 Apps: Company Branding, SLA, Two-Sync between On-Premises and Cloud
  - Premium 1: Hybrid Architecture, Advanced Group Access, Conditional Access
  - Premium 2: Identity Protection, Identity Governance

- Azure Active Directory is Microsoft's cloud-based identity and access management service

- Helps your employees sign in and access resources

- User information such as name, ID, email, password and address is stored in Azure AD

- Identity: represents user, organization or applications(require authentication via secret keys or certificates)

**Default Directory:**

![image-20230213102255503](Azure Identities and Governance.assets/image-20230213102255503.png)

**Name of AAD can be changed:**

![image-20230326142532269](Azure Identities and Governance.assets/image-20230326142532269.png)

**Tenant:**

​	Represents an organization, or a user, or a branch company which belongs to the organization

​	Tenant is automatically created when your organization signs up for Azure

​	The term Tenant means a single instance of Azure AD, representing a single user/organization/company

​	**Important: One tenant -- One company -- One AAD**

​	The terms Tenant, Directory and AAD are often used interchangeably

**Tenant Example:**

​	When you create **an Azure account**, Azure by default creates **a Tenant** for you. This tenant has **one to one replationship** with **Azure AAD**. **Default Tenant -- Default AAD**

​	**One Azure** account can have **many Tenants** and **each Tenant can represent one organization** and they are separate. For example, an organization can have many companies. and it can create multiple Tenants under this organization's Global Admin Account.

​	Within a Tenant/AAD, you can create multiple users, group them together and give them different permissions

​	If you create another Tenant, this Tenant will also be linked to a new AAD instance and these two Tenants are completely isolated and will not affect each other

​	**Important: Every Tenant has one to one relationship with one AAD instance**

![image-20230328115537329](Azure Identities and Governance.assets/image-20230328115537329.png)

**Manage Tenant:**

![image-20230213110359582](Azure Identities and Governance.assets/image-20230213110359582.png)

**Default Directory(Default) is created when Creating Azure Global Admin Account**

![image-20230213110434708](Azure Identities and Governance.assets/image-20230213110434708.png)

![image-20230213111937878](Azure Identities and Governance.assets/image-20230213111937878.png)

**Example: Create an new Azure Tenant**

![image-20230213110957562](Azure Identities and Governance.assets/image-20230213110957562.png)

![image-20230213111019595](Azure Identities and Governance.assets/image-20230213111019595.png)

![image-20230213111030342](Azure Identities and Governance.assets/image-20230213111030342.png)

![image-20230213111732116](Azure Identities and Governance.assets/image-20230213111732116.png)

![image-20230213111821383](Azure Identities and Governance.assets/image-20230213111821383.png)

![image-20230213111840218](Azure Identities and Governance.assets/image-20230213111840218.png)

![image-20230213111849888](Azure Identities and Governance.assets/image-20230213111849888.png)

![image-20230213112004412](Azure Identities and Governance.assets/image-20230213112004412.png)

Once you create a new Tenant, a new user belongs this Tenant/Directory will be created automatically, under the new domain

- Tenant: DaveITOne

![image-20230327150525423](Azure Identities and Governance.assets/image-20230327150525423.png)

- Tenant: Default

![image-20230327150711368](Azure Identities and Governance.assets/image-20230327150711368.png)

**Switch Tenant:**

![image-20230326142937057](Azure Identities and Governance.assets/image-20230326142937057.png)

**Swtich Directory:**

![image-20230326143026197](Azure Identities and Governance.assets/image-20230326143026197.png)

![image-20230326143040998](Azure Identities and Governance.assets/image-20230326143040998.png)

# 2. Windows Server AD(ADDS) vs Azure AD

![image-20230213130915250](Azure Identities and Governance.assets/image-20230213130915250.png)

Windows Server AD: Provides an identity and access management service that's managed by your own organization in **on-premises environment**

Azure Active Directory: **cloud-based** service

Communication Protocols: 

​	Azure AD is **HTTP/HTTPS** based, it does not use Kerberos/NTLM(Windows AD authentication method) authentication

​	Azure Authentication: **SAML**, WS-Federation, and OpenID Connect

​	Azure Authorization: **OAuth**

![image-20230213131009860](Azure Identities and Governance.assets/image-20230213131009860.png)

**Azure AD Connect** synchronizes user identities between on-premises Active Directory and Azure AD

Azure AD provides extra features(for example, MFA, Single single-on, Self-service, etc)

AAD has flat structure, whereas Windows AD has OU structure

# 3. Create New User in Azure AD

In Default Directory:

![image-20230213131826358](Azure Identities and Governance.assets/image-20230213131826358.png)

Example: Create a new user under Default Directory(Default Tenant)

![image-20230213134543281](Azure Identities and Governance.assets/image-20230213134543281.png)

![image-20230213140748146](Azure Identities and Governance.assets/image-20230213140748146.png)

![image-20230213140813365](Azure Identities and Governance.assets/image-20230213140813365.png)

![image-20230213141138927](Azure Identities and Governance.assets/image-20230213141138927.png)

**.onmicrosoft.com**: is a default domain that Microsoft assigned

You can also create your custom domain if you have your own public domain

![image-20230213141329749](Azure Identities and Governance.assets/image-20230213141329749.png)

![image-20230213141350299](Azure Identities and Governance.assets/image-20230213141350299.png)

![

](Azure Identities and Governance.assets/image-20230213141418804.png)

![image-20230213141440490](Azure Identities and Governance.assets/image-20230213141440490.png)

New created Azure user needs to change their password at first logon

![image-20230213145921167](Azure Identities and Governance.assets/image-20230213145921167.png)

![image-20230213145934612](Azure Identities and Governance.assets/image-20230213145934612.png)

ZZyy522927. - zzYY522927.

![image-20230213150056548](Azure Identities and Governance.assets/image-20230213150056548.png)

Choose **Skip for now** to skip MFA setup

But after 14 days for initial login, user needs to set up MFA

![image-20230213150113689](Azure Identities and Governance.assets/image-20230213150113689.png)

![image-20230213150331214](Azure Identities and Governance.assets/image-20230213150331214.png)

![image-20230213150355383](Azure Identities and Governance.assets/image-20230213150355383-6261035.png)

New account with Roles and Groups unchanged doesn't have access to any services

![image-20230213151149945](Azure Identities and Governance.assets/image-20230213151149945.png)

**By default, new users don't have access to any services except for Azure portal, for example SQL databases. If access is required, we can use RBAC to assign proper role to user and provide access**

**Each user can also create its own Tenant structure, and all users of this Global Admin Account have the Default Directory as the Global Admin Account does**

![image-20230214132122833](Azure Identities and Governance.assets/image-20230214132122833.png)

Each Azure user can create its own Tenant

![image-20230327161219930](Azure Identities and Governance.assets/image-20230327161219930.png)

**demouser1** creates a new Tenant **demouser1tenant1**

![image-20230214132142895](Azure Identities and Governance.assets/image-20230214132142895.png)

**Within these Tenants, users and groups can be created**

# 4. Azure B2B - Create External or Guest User in Azure AD

**B2B:** Invite external users from other organization to work in your Azure

It can be users from other company's AAD tenant, or External user from partner, vendor, supplier without using Microsoft Account

Azure Cloud Identities:

- Users exist only in Azure AD

- your AAD or external AAD

Guest Identities(External Identities):

- B2B collaboration:
  -  External User
  - Other organization's Tenant

Directory-synchronized(Hybrid Identities)

![image-20230213155242867](Azure Identities and Governance.assets/image-20230213155242867.png)

User type example:

![image-20230213155322187](Azure Identities and Governance.assets/image-20230213155322187.png)

**User type:**

- **Guest**: user comes from **other organization's AAD tenant** or **external users(none MS email)**

- Member-Yes: user comes from your on-premises Windows AD, and synced to your AAD

- Member-No: user is created directly through your AAD 

**Demo:** B2B collaboartion

![image-20230213160108200](Azure Identities and Governance.assets/image-20230213160108200.png)

Steps to invite B2B users:

- admin sends invitation to external user

- external user accepts invitation

- verify **myapps** login

- create Microsoft Account manually

- login Azure


Example: Invite external user

1. invite external user by email 

External user means user with none Microsoft account - davidwangmelvic@gmail.com

Create with Global Admin Account, under Default Directory

![image-20230327220700287](Azure Identities and Governance.assets/image-20230327220700287.png)

![image-20230327220820256](Azure Identities and Governance.assets/image-20230327220820256.png)

![image-20230327220833990](Azure Identities and Governance.assets/image-20230327220833990.png)

2. Guest email Accept invitation

![image-20230327221016635](Azure Identities and Governance.assets/image-20230327221016635.png)

3. Azure account configuration

![image-20230327221039659](Azure Identities and Governance.assets/image-20230327221039659.png)

![image-20230327221057527](Azure Identities and Governance.assets/image-20230327221057527.png)

![image-20230327221110424](Azure Identities and Governance.assets/image-20230327221110424.png)

![image-20230327221122621](Azure Identities and Governance.assets/image-20230327221122621.png)

![image-20230327221131839](Azure Identities and Governance.assets/image-20230327221131839.png)

4. choose **Ask later**, otherwise MFA setup is required

![image-20230327221147556](Azure Identities and Governance.assets/image-20230327221147556.png)

It will login https://myapplications.microsoft.com/#optIn be default 

**External user has no apps available at default**

![image-20230327221210069](Azure Identities and Governance.assets/image-20230327221210069.png)

5. Create Microsoft Account manually

![image-20230327222155502](Azure Identities and Governance.assets/image-20230327222155502.png)

![image-20230327222235983](Azure Identities and Governance.assets/image-20230327222235983.png)

![image-20230327222304565](Azure Identities and Governance.assets/image-20230327222304565.png)

![image-20230327222315008](Azure Identities and Governance.assets/image-20230327222315008.png)

davidwangmelvic@gmail.com -- ning0803030221

![image-20230327222406092](Azure Identities and Governance.assets/image-20230327222406092.png)

![image-20230327222423688](Azure Identities and Governance.assets/image-20230327222423688.png)

![image-20230327222454214](Azure Identities and Governance.assets/image-20230327222454214.png)

![image-20230327222507891](Azure Identities and Governance.assets/image-20230327222507891.png)

![image-20230327222531944](Azure Identities and Governance.assets/image-20230327222531944.png)

![image-20230327222540971](Azure Identities and Governance.assets/image-20230327222540971.png)

![image-20230327222607490](Azure Identities and Governance.assets/image-20230327222607490.png)

**Once Microsoft Account Created, this external user will be exactly same as other AAD users and external user can use the external email to login Azure**

![image-20230327222656099](Azure Identities and Governance.assets/image-20230327222656099.png)

![image-20230327222708574](Azure Identities and Governance.assets/image-20230327222708574.png)

![image-20230327222720408](Azure Identities and Governance.assets/image-20230327222720408.png)

**Be default, external account doesn't belong to any Directory**

![image-20230327222755620](Azure Identities and Governance.assets/image-20230327222755620.png)

**Be default, external account doesn't have any access to any service or resource**

![image-20230327223217332](Azure Identities and Governance.assets/image-20230327223217332.png)

# 5. Azure AD B2C vs B2B

![image-20230214132636575](Azure Identities and Governance.assets/image-20230214132636575.png)

- Azure AD B2C is **a separate service** from Azure Active Directory(Azure AD)
- It is built on the same technology as Azure AD but for a different purpose
- It allows business to build customer facing applications, and then allow anyone to sign up into those applications with no restrictions on user account

![image-20230214153417498](Azure Identities and Governance.assets/image-20230214153417498.png)

**B2B VS B2C:**

- B2B: your organization admin will invite user from external organization and this user will become a part of your organization's AAD
- B2C: your organization admin will need to create a B2C tenant, then register applications/software into this B2C tenant, then end user can register your apps with existing account allowed in the list
- B2C tenant: It is an app of your organization

**Resgister Azure Free Accout to Microsoft AzureActiveDirectory**

![image-20230214160729460](Azure Identities and Governance.assets/image-20230214160729460.png)

![image-20230214160932209](Azure Identities and Governance.assets/image-20230214160932209.png)

![image-20230214161036793](Azure Identities and Governance.assets/image-20230214161036793.png)

**Create B2C tenant**

![image-20230214160324886](Azure Identities and Governance.assets/image-20230214160324886.png)

![image-20230214160343512](Azure Identities and Governance.assets/image-20230214160343512.png)

![image-20230214160706319](Azure Identities and Governance.assets/image-20230214160706319.png)

![image-20230214160722290](Azure Identities and Governance.assets/image-20230214160722290.png)



![image-20230214161407358](Azure Identities and Governance.assets/image-20230214161407358.png)

![image-20230214161506428](Azure Identities and Governance.assets/image-20230214161506428.png)

**Identity Providers:**

![image-20230214161542459](Azure Identities and Governance.assets/image-20230214161542459.png)

**Everytime you login Azure, you will login as one tenant, and you need to switch between different tenant**

![image-20230214163717267](Azure Identities and Governance.assets/image-20230214163717267.png)

# 6. Bulk User Create

## 6.1 Download user in Bulk

![image-20230214164146624](Azure Identities and Governance.assets/image-20230214164146624.png)

![image-20230214164233582](Azure Identities and Governance.assets/image-20230214164233582.png)

Bulk operation results

![image-20230214170941519](Azure Identities and Governance.assets/image-20230214170941519.png)

![image-20230214171034144](Azure Identities and Governance.assets/image-20230214171034144.png)

![image-20230214171043685](Azure Identities and Governance.assets/image-20230214171043685.png)

## 6.2 Create user in Bulk

![image-20230214171247843](Azure Identities and Governance.assets/image-20230214171247843.png)

![image-20230214171349617](Azure Identities and Governance.assets/image-20230214171349617.png)

Required: mandatory column

![image-20230214171435140](Azure Identities and Governance.assets/image-20230214171435140.png)

**user should come from one of the verfied domain name of the organization/tenant**

![image-20230214205824721](Azure Identities and Governance.assets/image-20230214205824721.png)

![image-20230214211152801](Azure Identities and Governance.assets/image-20230214211152801.png)

If organization's domain is davidwangazuregmail.onmicrosoft.com, then user must also come from this domain

![image-20230214210106629](Azure Identities and Governance.assets/image-20230214210106629.png)

upload file

![image-20230214171822485](Azure Identities and Governance.assets/image-20230214171822485.png)

**must be in .csv format, and edit file from the one downloaded**

![image-20230214172220644](Azure Identities and Governance.assets/image-20230214172220644.png)

![image-20230214172229536](Azure Identities and Governance.assets/image-20230214172229536.png)

![image-20230214210239507](Azure Identities and Governance.assets/image-20230214210239507.png)

check result

![image-20230214210652492](Azure Identities and Governance.assets/image-20230214210652492.png)

# 7. Azure AD FREE vs Premium Licensing

https://www.microsoft.com/en-au/security/business/identity-access/azure-active-directory-pricing

![image-20230215092922172](Azure Identities and Governance.assets/image-20230215092922172.png)

Check current AAD plan

![image-20230215093324886](Azure Identities and Governance.assets/image-20230215093324886.png)

Check features for current license

![image-20230215093704019](Azure Identities and Governance.assets/image-20230215093704019.png)

![image-20230215123849511](Azure Identities and Governance.assets/image-20230215123849511.png)

![image-20230220160435136](Azure Identities and Governance.assets/image-20230220160435136.png)

![image-20230220160451196](Azure Identities and Governance.assets/image-20230220160451196.png)

![image-20230220160502069](Azure Identities and Governance.assets/image-20230220160502069.png)

After 30 days Free trial, Azure will disable any active licenses and won't charge you, unless you manually active them.

AD premium P2 30 days trial only can be used once.

![image-20230220160649083](Azure Identities and Governance.assets/image-20230220160649083.png)

# 8. Azure AD Groups

Two different Azure groups:

- Security: assign permission to a group and all users in the same group will inherit group permission
- Microsoft 365: invite people who are outside our organization, and we share out mailbox, calendar and other resoureces to external users and organisations

Example: Create group

![image-20230217152342721](Azure Identities and Governance.assets/image-20230217152342721-6607823.png)

![image-20230217153923796](Azure Identities and Governance.assets/image-20230217153923796.png)

![image-20230217154029352](Azure Identities and Governance.assets/image-20230217154029352.png)

Example: Assign members and owner of the group

![image-20230217155013680](Azure Identities and Governance.assets/image-20230217155013680.png)

![image-20230217155048606](Azure Identities and Governance.assets/image-20230217155048606.png)

![image-20230217155654787](Azure Identities and Governance.assets/image-20230217155654787.png)

![image-20230217155732170](Azure Identities and Governance.assets/image-20230217155732170.png)

![image-20230220143305053](Azure Identities and Governance.assets/image-20230220143305053.png)

![image-20230220143337527](Azure Identities and Governance.assets/image-20230220143337527.png)

Wait for a bit and refresh

![image-20230220143428796](Azure Identities and Governance.assets/image-20230220143428796.png)

# 9. Azure AD Dynamic Groups

Dynamic Group: 

- there is no particularly group for Dynamic Group
- change Membership type to **Dynamic User**
- Dynamic means all users that meet a certain criteria(eg: Country is Australia), will be added to this group automatically, once created
- this will apply to both new users and existing users, once meet a certain criteria(eg: Country is Australia), users will be added to this Dynamic Group
- AD Dynamic Group feature requires Azure AD Premium P2 license

![image-20230220165623166](Azure Identities and Governance.assets/image-20230220165623166.png)

![image-20230220162441908](Azure Identities and Governance.assets/image-20230220162441908.png)

![image-20230220162541220](Azure Identities and Governance.assets/image-20230220162541220.png)

![image-20230220162610089](Azure Identities and Governance.assets/image-20230220162610089.png)

![image-20230220162624227](Azure Identities and Governance.assets/image-20230220162624227.png)

![image-20230220162701128](Azure Identities and Governance.assets/image-20230220162701128.png)

Change a user's country to Australia

![image-20230220163120749](Azure Identities and Governance.assets/image-20230220163120749.png)

![image-20230220163317525](Azure Identities and Governance.assets/image-20230220163317525.png)

![image-20230220163652499](Azure Identities and Governance.assets/image-20230220163652499.png)

![image-20230220163738361](Azure Identities and Governance.assets/image-20230220163738361.png)

Now, Demo User-2 and Demo User-3 both have Country or region as Australia

**Dynamic rule process** will action after a while, sometimes a few minutes, sometimes a few hours. Then Dynamic groups and users will sync

![image-20230221144646941](Azure Identities and Governance.assets/image-20230221144646941.png)

![image-20230221144702532](Azure Identities and Governance.assets/image-20230221144702532.png)

Normal/Assigned Group can also be converted to Dynamic Group

![image-20230220165513736](Azure Identities and Governance.assets/image-20230220165513736.png)

![image-20230220165535398](Azure Identities and Governance.assets/image-20230220165535398.png)

**rule is not case sensitive, country=Australia is same as country=AUSTRALIA**

# 10. Azure AD Roles

In Azure, we can manage user and group permission via Role

Each role gives a user different permission

**Example:** Assign **User administrator role** to DemoUse1

By default, users have no default and they cannot create other users, but they can see users within the same domain

Login DemoUser1

![image-20230223140808380](Azure Identities and Governance.assets/image-20230223140808380.png)

![image-20230223140902305](Azure Identities and Governance.assets/image-20230223140902305.png)

Assign role to user

![image-20230223140924752](Azure Identities and Governance.assets/image-20230223140924752.png)

![image-20230223140959968](Azure Identities and Governance.assets/image-20230223140959968.png)

![image-20230223141103576](Azure Identities and Governance.assets/image-20230223141103576.png)

Switch to DemoUser1

![image-20230223141227785](Azure Identities and Governance.assets/image-20230223141227785.png)

**Example:** Manage AD roles on a Group level

Azure AD group by default cannot be assigned any roles, we need to choose **Azure AD roles can be assigned to the group**

Once select, either it is YES or NO, it cannot be changed in the future

![image-20230223143059511](Azure Identities and Governance.assets/image-20230223143059511.png)

**Azure AD roles can be assigned to the group** must be selected while creating the group

![image-20230223143559957](Azure Identities and Governance.assets/image-20230223143559957.png)

![image-20230223150633867](Azure Identities and Governance.assets/image-20230223150633867.png)

add members to this new group demoGroupRole1

![image-20230223165653301](Azure Identities and Governance.assets/image-20230223165653301.png)

assign roles to the group

![image-20230223165738942](Azure Identities and Governance.assets/image-20230223165738942.png)

![image-20230223165806769](Azure Identities and Governance.assets/image-20230223165806769.png)

![image-20230223165827105](Azure Identities and Governance.assets/image-20230223165827105.png)

now, all users in this new grouo should have **User administraor** role

![image-20230223165942674](Azure Identities and Governance.assets/image-20230223165942674.png)

![image-20230223170011813](Azure Identities and Governance.assets/image-20230223170011813.png)

![image-20230223170023366](Azure Identities and Governance.assets/image-20230223170023366.png)

try login from these two users and try create users

**demo.user-1@davidwangazuregmail.onmicrosoft.com** ZZyy522927.

![image-20230224095254308](Azure Identities and Governance.assets/image-20230224095254308.png)

![image-20230224095927836](Azure Identities and Governance.assets/image-20230224095927836.png)

![image-20230224095955315](Azure Identities and Governance.assets/image-20230224095955315.png)

![image-20230224100014503](Azure Identities and Governance.assets/image-20230224100014503.png)

![image-20230224100402368](Azure Identities and Governance.assets/image-20230224100402368.png)

![image-20230224100536520](Azure Identities and Governance.assets/image-20230224100536520.png)

# 11. Azure AD Roles vs RBAC Roles

![image-20230224134815378](Azure Identities and Governance.assets/image-20230224134815378.png)

Azure AD Roles:

- used for Azure AD related access
- roles only needed for Azure Active Directory, called Azure AD administrator roles
- Manage access to Azure Active Directory resources
- Scopt is at the **tenant** level
- Examples:
  - Creating users/Groups/Roles
  - Managing Password
  - Billing/Payment Info

RBAC Roles:

- used for non-Azure AD related access, such as SQL access, Virtual Machine access, etc
- RBAC Roles
- Manage access to Azure resources
- Scope can be specified at multiple levels(management group, subscription, resource group, resouce)
  - Create Database
  - Create/manage/delete VM and other resources

Azure Administrator Role example:

**Assigned roles** are Azure Administrative roles

![image-20230224141241400](Azure Identities and Governance.assets/image-20230224141241400.png)

RBAC Role example:

**Azure role assignments** are RBAC roles

![image-20230224141346112](Azure Identities and Governance.assets/image-20230224141346112.png)

# 12. Administrative Units

Azure AD administrator roles scope is at the tenant level. If one user has **User Administrator** role, then this user can manage all users within the same tenant/AAD/organization

![image-20230224161207918](Azure Identities and Governance.assets/image-20230224161207918.png)

**Administrative Units** can break down administrative access

For example, Admin A can only manage users in office A, and Admin B can only manage users in Office B, etc

We can create Adminitrative Unit Office A, then add users to Office A, then assign Admin A to this Administrative A

![image-20230224161245370](Azure Identities and Governance.assets/image-20230224161245370.png)

# 13. Demo Administrative Units

![image-20230307135931473](Azure Identities and Governance.assets/image-20230307135931473.png)

Steps:

1. Create a Administrative Unit - Office A
2. Create a User, called Admin A, then assign User Administrator role to this Admin A user
3. Add usera1, usera2 to this Administratibe Unit - Office A
4. Create group grpOfficeB and add this group to Administrative Unit - Office A, then add userb1 and userb2 to this group grpOfficeB
5. leave userc1 as individual user
6. Result: 
   - Admin A will be able to manage usera1, usera2 and grpOfficeB itself
   - Admin A will not be able to manage userc1, userb1 and userb2. This is because userb1 and userb2 are not added into Office A, it is the group which is added to Office A Adminstrative Unit
   - User must be added into Administrative Unit directly, so that it can be managed by Administrative Unit admiin, such as Admin A in this case
   - From the organization level, there is  an organizational administrator who can manage all users and groups no matter if they have been added to Administrative Unit or not

Demo：

1. Upload bulk user creation file 

![image-20230307150607665](Azure Identities and Governance.assets/image-20230307150607665.png)

![image-20230307150634531](Azure Identities and Governance.assets/image-20230307150634531.png)

![image-20230307151505782](Azure Identities and Governance.assets/image-20230307151505782.png)

![image-20230307151618739](Azure Identities and Governance.assets/image-20230307151618739.png)

2. Create group grpOfficeB and add userb1 and userb2 into this group

![image-20230307152849915](Azure Identities and Governance.assets/image-20230307152849915.png)

![image-20230307152942176](Azure Identities and Governance.assets/image-20230307152942176.png)

3. Create an Administrative Unit

![image-20230307161307741](Azure Identities and Governance.assets/image-20230307161307741.png)

![image-20230307161330319](Azure Identities and Governance.assets/image-20230307161330319.png)

Administrative Unit only have certain roles available

![image-20230307161614767](Azure Identities and Governance.assets/image-20230307161614767.png)

![image-20230307161638930](Azure Identities and Governance.assets/image-20230307161638930.png)

Administrator of an Administrative Unit is assigned when creating the unit

![image-20230307161657816](Azure Identities and Governance.assets/image-20230307161657816.png)

![image-20230307161720632](Azure Identities and Governance.assets/image-20230307161720632.png)

![image-20230307161733415](Azure Identities and Governance.assets/image-20230307161733415.png)

![image-20230307161750756](Azure Identities and Governance.assets/image-20230307161750756.png)

4. Assign members to this unit

![image-20230307161953594](Azure Identities and Governance.assets/image-20230307161953594.png)

![image-20230307162318393](Azure Identities and Governance.assets/image-20230307162318393.png)

![image-20230307162447858](Azure Identities and Governance.assets/image-20230307162447858.png)

![image-20230307162518680](Azure Identities and Governance.assets/image-20230307162518680.png)

5. Assign AD group to this unit

![image-20230307162627850](Azure Identities and Governance.assets/image-20230307162627850.png)

![image-20230307162713238](Azure Identities and Governance.assets/image-20230307162713238.png)

![image-20230307162756124](Azure Identities and Governance.assets/image-20230307162756124.png)

6. Login Azure with Admin A user and verify access 

admina@davidwangazuregmail.onmicrosoft.com

- usera1 and usera2 in OfficeA Administrative Unit can be managed by Admin A as they are added directly into Office A

![image-20230307163659669](Azure Identities and Governance.assets/image-20230307163659669.png)

![image-20230307163721254](Azure Identities and Governance.assets/image-20230307163721254.png)

- Admin A can manage grpOfficeB, as this group is added directly into the Administrative Unit

![image-20230307163809505](Azure Identities and Governance.assets/image-20230307163809505.png)

- Admin A cannot manage userb1, userb2 and userc1, as userc1 is not added into the unit and both userb1 and userb2 are added into the grpOfficeB, rather than the unit directly

![image-20230307163959781](Azure Identities and Governance.assets/image-20230307163959781.png)

![image-20230307164052354](Azure Identities and Governance.assets/image-20230307164052354.png)

![image-20230307164121606](Azure Identities and Governance.assets/image-20230307164121606.png)

# 14. Quiz - User and Group accounts

![image-20230307165021958](Azure Identities and Governance.assets/image-20230307165021958.png)

![image-20230307165036194](Azure Identities and Governance.assets/image-20230307165036194.png)

![image-20230307165050205](Azure Identities and Governance.assets/image-20230307165050205.png)



# 15. Demo Custom Domain

When registering in Azure, a personal or business email is often used, such as 123@hah.com or admin@google.com

This account will be working as a global admin account and there will be admin users created to manage access and normal users created to use Azure services

By default, when creating other users within this global admin account(for example 123@nah.com), a default domain nah.onmicrosoft.com will be used. Therefore, if username is user1, then login name with be user1@nah.onmicrosoft.com

You can also customize the domain name, but you will need to have a public domain name registered in public DNS provider

For example, if you have a domain called `daveit.com`, you just need to register this domain in Azure and the domain provider , then you will be able to choose this domain when creating users

![image-20230310163219798](Azure Identities and Governance.assets/image-20230310163219798.png)

![image-20230310163258365](Azure Identities and Governance.assets/image-20230310163258365.png)

![image-20230310163328244](Azure Identities and Governance.assets/image-20230310163328244.png)

To user Cloudgita.com with your Azure AD, create a new `TXT` record with your domain name registra using the info below. For example, Google Domain

![image-20230310163622658](Azure Identities and Governance.assets/image-20230310163622658.png)

Wait for a few minutes, because ometimes, it may take time to reflect in Azure

![image-20230310163644249](Azure Identities and Governance.assets/image-20230310163644249.png)

Click Verify

![image-20230310163816288](Azure Identities and Governance.assets/image-20230310163816288.png)

![image-20230310163837223](Azure Identities and Governance.assets/image-20230310163837223.png)

Go back to custom domain, the one just created will show up

![image-20230310164029134](Azure Identities and Governance.assets/image-20230310164029134.png)



Next time when you create a user, you can choose the one just created

![image-20230310165135756](Azure Identities and Governance.assets/image-20230310165135756.png)

You can also make this one as the default/primary domain, so it will be picked up automatically

![image-20230310165259083](Azure Identities and Governance.assets/image-20230310165259083.png)

![image-20230310165322502](Azure Identities and Governance.assets/image-20230310165322502.png)

![image-20230310165347444](Azure Identities and Governance.assets/image-20230310165347444.png)

# 16. Azure AD Device Management

Azure AD - Identity and access management service

- Identity - users, groups, applications or **devices**

Make sure devices are secure, compliant and not vulnerable

Capabilities: SSO, Conditional Access

There are three ways to register a device into Azure:

- Azure AD **registration**: Users want to use their own devices to login corporate resources
  - **User-owned devices (BYOD)**
  - Use **local user account** to login in to device, then use **corporate account** to access resources
  - No access to **on-premises** infrastructure, for example on-premises Active Directory
  - Limited management
  - Windows 10 or newer, iOS, Android, and MacOS
  - Example: A user in your organization wants to access your benefits enrollment tool from their home PC

![image-20230317123546111](Azure Identities and Governance.assets/image-20230317123546111.png)

- Azure AD **join**: Join device to Azure AD, then user can use their Azure ID to login this device
  - **Corporate-owned devices**
  - **Corporate user account**
  - Full Intune management
  - Windows 11 and Windows 10 devices, Windows Server 2019 Virtual Machines running in Azure
  - Example: workers who work from home or are in remote branche offices with limited on-premises infrastructure

![image-20230317124224705](Azure Identities and Governance.assets/image-20230317124224705.png)

- Hybrid Azure AD join
  - Suitable for hybrid organizations with existing on-premises AD infrastructure
  - Joined to on-premises AD and Azure requiring organizational account to sign in to the device
  - Gives your all the benefits of being cloud enabled with still having full access to your on-prem infrastructure

![image-20230317124251822](Azure Identities and Governance.assets/image-20230317124251822.png)

# 17. Demo - Azure AD Device join

Device Management - Corporate Device Join into Azure AD - So user can login this device using their Azure ID

![image-20230317125056618](Azure Identities and Governance.assets/image-20230317125056618.png)

![image-20230317125258299](Azure Identities and Governance.assets/image-20230317125258299.png)

![image-20230317125502108](Azure Identities and Governance.assets/image-20230317125502108.png)

![image-20230317134335336](Azure Identities and Governance.assets/image-20230317134335336.png)

![image-20230317134347744](Azure Identities and Governance.assets/image-20230317134347744.png)

Example: Create a **Free** Virtual Machine and Join it into Azure AD

**Must go to Free Services first, then create VMs, otherwise it will be charged**

Create VM

![image-20230317160706467](Azure Identities and Governance.assets/image-20230317160706467.png)

![image-20230317160952759](Azure Identities and Governance.assets/image-20230317160952759.png)

![image-20230317161035333](Azure Identities and Governance.assets/image-20230317161035333.png)

![image-20230317161106388](Azure Identities and Governance.assets/image-20230317161106388.png)

![image-20230317161117413](Azure Identities and Governance.assets/image-20230317161117413.png)

![image-20230317161137666](Azure Identities and Governance.assets/image-20230317161137666.png)

![image-20230317161206583](Azure Identities and Governance.assets/image-20230317161206583.png)

![image-20230317161330035](Azure Identities and Governance.assets/image-20230317161330035.png)

Connect to VM

![image-20230317161512460](Azure Identities and Governance.assets/image-20230317161512460.png)

![image-20230317161543892](Azure Identities and Governance.assets/image-20230317161543892.png)

![image-20230317161601022](Azure Identities and Governance.assets/image-20230317161601022.png)

![image-20230317161702515](Azure Identities and Governance.assets/image-20230317161702515.png)



# 18. Demo - Azure AD Device Register

**Register Windows Laptop BYOD** device to Azure AD

1. Search for **Access work or school**

![image-20230317163503792](Azure Identities and Governance.assets/image-20230317163503792.png)

2. Enter your own Azure Login ID

![image-20230317163536229](Azure Identities and Governance.assets/image-20230317163536229.png)

3. Click **Next** and it will load and finish
4. Go to Azure AD - Device and make sure device is there

# 19. Demo - Self-Service Password Reset(SSRP)

**Azure AD Premium P2** license is required for SSRP

Azure Free subscription can have free Azure AD Premium P2 license for 30 days and 100 licenses assigned to users

1. Assign P2 license to Demo User-2

![image-20230317164106583](Azure Identities and Governance.assets/image-20230317164106583.png)

![image-20230317164224523](Azure Identities and Governance.assets/image-20230317164224523.png)

![image-20230317164239073](Azure Identities and Governance.assets/image-20230317164239073.png)

![image-20230317164255496](Azure Identities and Governance.assets/image-20230317164255496.png)

![image-20230317164353749](Azure Identities and Governance.assets/image-20230317164353749.png)

![image-20230317164405099](Azure Identities and Governance.assets/image-20230317164405099.png)

![image-20230317164420005](Azure Identities and Governance.assets/image-20230317164420005.png)

![image-20230317222737651](Azure Identities and Governance.assets/image-20230317222737651.png)

The reason is some Microsoft offerings are not available in specific regions because of local laws and restrictions. So unless you specify a usage location for the user, you cannot assign those license offerings which are region specific

![image-20230317222912659](Azure Identities and Governance.assets/image-20230317222912659.png)

![image-20230317223031115](Azure Identities and Governance.assets/image-20230317223031115.png)

![image-20230317223044816](Azure Identities and Governance.assets/image-20230317223044816.png)

2. Enable self password reset policy

![image-20230317225803520](Azure Identities and Governance.assets/image-20230317225803520.png)

![image-20230317225903603](Azure Identities and Governance.assets/image-20230317225903603.png)

3. Choose Authentication Method, make sure only the user himself/herself can reset the password, not anyone else

![image-20230317230804329](Azure Identities and Governance.assets/image-20230317230804329.png)

![image-20230317231045675](Azure Identities and Governance.assets/image-20230317231045675.png)

![image-20230317231121380](Azure Identities and Governance.assets/image-20230317231121380.png)

4. On-premises integration

Azure AD and On-premises AD can sync between each other through Azure connect service

![image-20230317233550157](Azure Identities and Governance.assets/image-20230317233550157.png)

AAD -- AD: write back password to your on-premises directory

5. Make sure user has mobile number in his/her profile

6. Test SSPR

![image-20230317234525046](Azure Identities and Governance.assets/image-20230317234525046.png)

![image-20230317234324227](Azure Identities and Governance.assets/image-20230317234324227.png)

![image-20230317234340963](Azure Identities and Governance.assets/image-20230317234340963.png)

![image-20230317234417007](Azure Identities and Governance.assets/image-20230317234417007.png)

![image-20230317234432589](Azure Identities and Governance.assets/image-20230317234432589.png)

![image-20230317234448265](Azure Identities and Governance.assets/image-20230317234448265.png)

![image-20230317234459986](Azure Identities and Governance.assets/image-20230317234459986.png)

![image-20230317234534646](Azure Identities and Governance.assets/image-20230317234534646.png)

![image-20230317234705193](Azure Identities and Governance.assets/image-20230317234705193.png)





# 20. Multi-factor Authentication

Two processes that enable secure authentication: **Azure AD Multi-Factor Authentication** and **Conditional Access**

Multifactor authentication provides additional security for your identities by requiring two or more elements to fully authenticate

- Something the user knows: This might be an email address and password
- Something the user has: This might be a code that's sent to the user's mobile phone(OTP code, one-time passcode)
- Something the user is: This is typically some sort of biometric property, such as fingerprint or face scan that's used on many mobile devices

Multi-factor authentication is recommended for administrative accounts

Azure AD Multi-Factor Authentication: phone call or mobile app notification

There are 4 different ways to enforce MFA

- Security Defaults: Basic Azure License, user has 14 days to setup MFA from their first logon
- Conditional Access: P2 License, define **who** needs to setup MFA when logon **which** application from **where**
- Enable MFA per-user: MFA will be triggered whenever that user accesses any cloud service
- Enable MFA through Azure Identity Protection: P2 License required

![image-20230316164458329](Azure Identities and Governance.assets/image-20230316164458329.png)

Example: enable MFA for single user to login Azure

![image-20230316164957771](Azure Identities and Governance.assets/image-20230316164957771.png)

![image-20230316165012033](Azure Identities and Governance.assets/image-20230316165012033.png)

![image-20230316165020298](Azure Identities and Governance.assets/image-20230316165020298.png)

![](Azure Identities and Governance.assets/image-20230316165029805.png)

![image-20230316165132190](Azure Identities and Governance.assets/image-20230316165132190.png)

![image-20230316165155526](Azure Identities and Governance.assets/image-20230316165155526.png)

![image-20230316165207784](Azure Identities and Governance.assets/image-20230316165207784.png)

Phone number method is through text message

![image-20230316165242554](Azure Identities and Governance.assets/image-20230316165242554.png)

![image-20230316165332352](Azure Identities and Governance.assets/image-20230316165332352.png)

login with Demo User-1

![image-20230316165427887](Azure Identities and Governance.assets/image-20230316165427887.png)

![image-20230316165444179](Azure Identities and Governance.assets/image-20230316165444179.png)

![image-20230316165454232](Azure Identities and Governance.assets/image-20230316165454232.png)

![image-20230316165517146](Azure Identities and Governance.assets/image-20230316165517146.png)

![image-20230316165535775](Azure Identities and Governance.assets/image-20230316165535775.png)

# 21. Conditional Access

Azure Active Directory uses Conditional Access to grant (or deny) resource access based on **identity signals**

- who the user is (Administrator or normal user)

- where the user is (usual or unexpected location)
- what device the user is requesting access from(is this a new device)

Based on signals, Azure Active Directory can decide to allow, deny, or require MFA access

Multi-authentication will be required, only if sign-in signals are unusual(for example unexpected location)

Conditional Access is not Free, it requires Azure AD Premium P1 or P2 license

![image-20230317101813937](Azure Identities and Governance.assets/image-20230317101813937.png)

# 22. Demo Conditional Access Policy

Example: Enable Conditional Access for User **Demo User-3**

![image-20230317103019515](Azure Identities and Governance.assets/image-20230317103019515.png)

Add authentication method for this user

![image-20230317103926470](Azure Identities and Governance.assets/image-20230317103926470.png)

Make sure multi-authentication is disabled

![image-20230317104013419](Azure Identities and Governance.assets/image-20230317104013419.png)

Create Conditional Policy

![image-20230317104132357](Azure Identities and Governance.assets/image-20230317104132357.png)

![image-20230317104150926](Azure Identities and Governance.assets/image-20230317104150926.png)

![image-20230317104251554](Azure Identities and Governance.assets/image-20230317104251554.png)

Apply Conditional Policy to which user or group

![image-20230317104428989](Azure Identities and Governance.assets/image-20230317104428989.png)

Apply Conditional Policy to which application

Microsoft Azure Management app is https://portal.azure.com/

When this user **Demo User-3** is logging in https://portal.azure.com/, Conditional Policy will be applied

![image-20230317104645422](Azure Identities and Governance.assets/image-20230317104645422.png)

How to define conditions

![image-20230317105034777](Azure Identities and Governance.assets/image-20230317105034777.png)

Directly grant access to Microsoft Azure Management app, but require Multi-factor authentication

![image-20230317105132972](Azure Identities and Governance.assets/image-20230317105132972.png)

![image-20230317105202899](Azure Identities and Governance.assets/image-20230317105202899.png)

Right now, we have a Conditional Policy for Demo User-3, when it is logging in Microsoft Azure Management portal, Multi-factor authentication is required

![image-20230317105337344](Azure Identities and Governance.assets/image-20230317105337344.png)

For this error, disable Security defaults and create Conditional Access policy again

![image-20230317110351909](Azure Identities and Governance.assets/image-20230317110351909.png)

![image-20230317110455822](Azure Identities and Governance.assets/image-20230317110455822.png)![image-20230317110543871](Azure Identities and Governance.assets/image-20230317110543871.png)



![image-20230317110602651](Azure Identities and Governance.assets/image-20230317110602651.png)

Create Conditional Access Policy again

![image-20230317110729176](Azure Identities and Governance.assets/image-20230317110729176.png)

Test login

![image-20230317110804526](Azure Identities and Governance.assets/image-20230317110804526.png)

![image-20230317110820237](Azure Identities and Governance.assets/image-20230317110820237.png)

![image-20230317110830960](Azure Identities and Governance.assets/image-20230317110830960.png)

![image-20230317110850819](Azure Identities and Governance.assets/image-20230317110850819.png)

![image-20230317110903563](Azure Identities and Governance.assets/image-20230317110903563.png)

**Delete Conditional Policy and Restore Security Default**

They cannot be used at the same time

![image-20230317111137846](Azure Identities and Governance.assets/image-20230317111137846.png)

![image-20230317111223217](Azure Identities and Governance.assets/image-20230317111223217.png)

![image-20230317111237004](Azure Identities and Governance.assets/image-20230317111237004.png)

![image-20230317111326270](Azure Identities and Governance.assets/image-20230317111326270.png)

![image-20230317111340766](Azure Identities and Governance.assets/image-20230317111340766.png) 

# 23. Monitor user sign-in

![image-20230321152218802](Azure Identities and Governance.assets/image-20230321152218802.png)



# 24. Quiz

![image-20230317235238946](Azure Identities and Governance.assets/image-20230317235238946.png)

![image-20230317235246687](Azure Identities and Governance.assets/image-20230317235246687.png)

![image-20230317235259186](Azure Identities and Governance.assets/image-20230317235259186.png)

