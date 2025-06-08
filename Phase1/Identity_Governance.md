===# Phase 1: Identity & Governance (AZ-104)

## Objective
- Create a resource group
- Add Azure AD users and groups
- Assign RBAC roles
- Apply a policy and a lock for governance

## Tasks Performed

### ✅ 1. Created Resource Group
- Name: "RG-AZ104"
- Region: "(US) East US"
- Tag: "Project = AZ-104-Lab"

### ✅ 2. Created Azure AD Users
- user1: user1@ethanielranderson2005gmail.onmicrosoft.com
- user2: user2@ethanielranderson2005gmail.onmicrosoft.com
- user3: user3@ethanielranderson2005gmail.onmicrosoft.com

### ✅ 3. Assigned Roles
- user1 = assigned **Reader** role on RG-AZ104
- user2 = assigned **Contributor** role on RG-AZ104

### ✅ 4. Created Group
- Group name: az104-admins
- Users added: user3@ethanielranderson2005gmail.onmicrosoft.com
- Role assigned: **Owner** role to the group on RG-AZ104

### ✅ 5. Applied Azure Policy
- Policy Name: Require a tag and its value
- Scope: RG-AZ104
- Tag Enforced: Owner = Me
  
### ✅ Policy Test
- Attempted to create a storage account in RG-AZ104 without the Owner tag
- Result: ❌ Blocked by policy as expected
- Re-attempted creation with tag Owner = Me → ✅ Successful

#### Screenshot: ![image](https://github.com/user-attachments/assets/cf5156f3-b621-483b-a7e4-68f9f44af4f7)

### ✅ 6. Applied Lock
- Lock Name: rg-delete-lock
- Lock type: ReadOnly
- Scope: Resource group RG-AZ104
- Purpose: Prevent accidental deletion of lab resources

#### Lock Enforcement Test
- Attempted to deploy a resource in RG-AZ104
- Result: ❌ Deployment blocked by lock
- Removed lock, reattempted with correct tag → ✅ Successful
#### Screenshot: ![image](https://github.com/user-attachments/assets/2d39da3b-adcc-4bea-acc7-ebd45e0455ca)
  
## Screenshots
1. Created Resource Group ![image](https://github.com/user-attachments/assets/f3bf3492-2f85-43d8-8d24-da6da23fb8af)
2. Created Azure AD Users ![image](https://github.com/user-attachments/assets/96bfbbb7-7ec7-494e-853d-aef74e1b44a6)
3. Assigned Roles ![image](https://github.com/user-attachments/assets/5d40d01e-4c31-48d3-a74c-d5d1d3bb1809)
4. Created Group ![image](https://github.com/user-attachments/assets/30dc4b82-b3ce-45f8-8d9b-f513990afa90)
5. Applied Azure Policy ![image](https://github.com/user-attachments/assets/b199a7d2-873f-4dd4-8dda-e356f178aa18) 
6. Applied Lock ![image](https://github.com/user-attachments/assets/5a3b814d-a8a8-47fe-834e-b369f25bb122)



## Reflections

This phase helped me understand how Azure manages identity, access, and governance at scale. I didn’t just click through — I had to troubleshoot real constraints like policy enforcement and lock behavior.

Key takeaways:
- RBAC is scoped and layered — roles assigned to users vs. groups matters
- Azure Policies are case-sensitive and enforce rules **before** resource creation
- Locks override everything, even valid deployments
- Working in the portal made these concepts **stick** way more than just reading about them

Running into errors like policy enforcement failures and lock errors actually helped me understand how powerful these governance tools are — and why large orgs rely on them.


## Clean-Up Notes
- Kept RG-AZ104 intact for use in Phase 2 (VM and Compute Labs)
- Removed rg-delete-lock temporarily to allow deployment — will reapply later if needed
- Validated that no extra resources were deployed or left running
- Policy assignment left active to reinforce tag usage going forward
- Budget monitoring set at $10 to protect remaining Azure credit
