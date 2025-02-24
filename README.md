# RBAC with Active Directory Setup

  <img src="https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image1.png" alt="Description" width="35%">

## 📌 Overview
A Comprehensive Guide to Setting Up Role-Based Access Control (RBAC) with Active Directory. 
<br>

## 🐷 Why Use RBAC with Active Directory?
Role-Based Access Control (RBAC) simplifies permission management in Active Directory by assigning access based on job roles. This approach enhances security, maintains organisation and prevents unauthorised access. This guide will walk you through setting up and implementing RBAC on Windows Server.
<br>

## ✨ How This Helps
- **Organised Access Control**  
RBAC assigns permissions based on roles, keeping access structured and manageable.

- **Easy Resource Management**  
 Simplifies control over who can access specific resources, reducing manual adjustments.

- **Enhanced Security**  
Minimises the risk of unauthorised access to sensitive data, strengthening network security.

- **Flexible Role Management**  
Makes it easy to update permissions when employees change roles, saving time and effort. 

## 🛠️ Installation
### Step 1: Install Active Directory on Windows Server
- Start by opening Server Manager.
- Click Add Roles and Features.
- When prompted, choose Role-based or feature-based installation.
- Select your server from the server pool.
- Find and select Active Directory Domain Services (AD DS), then follow the prompts to install it.
- After it’s installed, you’ll need to promote the server to a domain controller to complete the setup.

  ![Description](https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image6.png)
  ![Description](https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image3.png)

### Step 2: Identify Roles and Permissions Needed
- Begin by defining the roles in your company based on job functions—think Sales, Management, IT, and Customer Support.
- For each role, decide what level of access they’ll need, like:
    - Access to shared folders on the server.
    - Permissions for applications and resources on the Synology NAS.
    - Any additional file or system access needed to do their job.

  
### Step 3: Set Up Security Groups in Active Directory
- In Active Directory Users and Computers, create a security group for each role:
    - Right-click on the Organizational Unit (OU) or domain where you want the group.
    - Select New > Group and name it to match the role (like Sales_Group or Management_Group).
- Now, add users to their groups:
    - Right-click each user, select Add to a Group, and add them to the right security group.


  ![Description](https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image2.png)
  ![Description](https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image11.png)

### Step 4: Set Permissions on Folders and Resources
- Open File Explorer on the server that holds the shared folders.
- Right-click on the folder, select Properties, and go to the Security tab.
- Click Edit to open the permissions options.
Here, add the security groups:
    - Click Add, enter the group name (like Sales_Group or Management_Group), and confirm.
- Assign permissions for each group:
    - For read-only access, check “Read & execute,” “List folder contents,” and “Read.”
    - For full control, check all options.
- Click Apply and OK to save.


  ![Description](https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image7.png)

### Step 5: Set Up Group Policies (GPOs) for Access Control
- Go to Server Manager > Tools > Group Policy Management.
- Create a New GPO:
    - Right-click the OU or domain where you want to apply the GPO.
    - Choose Create a GPO in this domain, and Link it here, then give it a name that describes its purpose (e.g., Sales_Access_Policy).

- Configure Logon Hours:
    - In the GPO, go to Computer Configuration or User Configuration > Policies > Windows Settings > Security Settings.
    - Set Logon Hours to control when each role can access the network.

- Add Software Restrictions:
    -  In the GPO, go to User Configuration > Policies > Administrative Templates > System > Don’t Run Specified Windows Applications.
    -  List applications that should be restricted, depending on the role.

- Set Network Access Restrictions:
    - Go to Computer Configuration > Windows Settings > Security Settings > Windows Defender Firewall.
    - Configure inbound and outbound rules to limit network access as necessary for each role.

- Link and Apply the GPO:
    - Right-click the OU or domain where you want the GPO and select Link an Existing GPO.
    - Choose the GPO you created and link it to the correct location.


  ![Description](https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image10.png)
  ![Description](https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image5.png)
  ![Description](https://raw.githubusercontent.com/itstonypham/-RBAC-with-Active-Directory/refs/heads/images/image9.png)
<br>

## 🔚 Conclusion
- With RBAC in place, managing access across the network becomes more efficient and secure. By assigning permissions based on roles, users only have the access they need, reducing the risk of excessive privileges and protecting sensitive data. Regularly reviewing and updating roles ensures ongoing security and keeps access aligned with business needs.

## 👤 Author
- **Tony Pham** – [GitHub](https://github.com/itstonypham) | [LinkedIn](https://www.linkedin.com/in/itstonypham/)

## 🤝 Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss.  


## ⭐ Acknowledgments
- Thanks to contributors and resources that helped with the project.

---
