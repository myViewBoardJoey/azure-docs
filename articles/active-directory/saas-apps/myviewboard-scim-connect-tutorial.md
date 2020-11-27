**Tutorial: Configure myViewBoard for automatic user provisioning**
The objective of this tutorial is to demonstrate the steps to be performed in myViewBoard and Azure Active Directory (Azure AD) to configure Azure AD to automatically provision and de-provision users and/or groups to [myViewBoard](https://myviewboard.com/). For important details on what this service does, how it works, and frequently asked questions, see [Automate user provisioning and deprovisioning to SaaS applications with Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/user-provisioning).

**Capabilities supported**
- Create users in myViewBoard
- Remove users in myViewBoard when they do not require access anymore
- Keep user attributes synchronized between Azure AD and myViewBoard
- Provision groups and group memberships in myViewBoard

**Prerequisites**
The scenario outlined in this tutorial assumes that you already have the following prerequisites:
- [An Azure AD tenant](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-create-new-tenant)
- A user account in Azure AD with [permission](https://docs.microsoft.com/en-us/azure/active-directory/roles/permissions-reference) to configure provisioning (e.g. Application Administrator, Cloud Application administrator, Application Owner, or Global Administrator)
- [A myViewBoard entity](https://myviewboard.com/contact/)
- A user account in myViewBoard with Admin permissions

**Step 1. Plan your provisioning deployment**
1. Learn about [how the provisioning service works](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/user-provisioning).
1. Determine who will be in [scope for provisioning](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/define-conditional-rules-for-provisioning-user-accounts).
1. Determine what data to [map between Azure AD and myViewBoard](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/customize-application-attributes).

**Step 2. Configure myViewBoard to support provisioning with Azure AD**
1. Sign in to myviewboard.com with your administrator account.
1. Navigate to **Entity Management** > **Single Sign On** > Select **SCIM**
1. Copy the **SCIM URL** and **SCIM Token** which will be entered in the **Tenant URL** and **Secret Token** fields in the **Provisioning** tab of your myViewBoard application in the Azure AD portal respectively.
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial.png)
3
**Step 3. Add myViewBoard SCIM Connect from the Azure AD application gallery**
Add **myViewBoard SCIM Connect** from the Azure AD application gallery to start managing provisioning to myViewBoard. Learn more about adding an application from the gallery [here](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/add-application-portal).

**Step 4. Define who will be in scope for provisioning**
The Azure AD provisioning service allows you to scope who will be provisioned based on assignment to the application and or based on attributes of the user / group. If you choose to scope who will be provisioned to your app based on assignment, you can use the following [steps](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/assign-user-or-group-access-portal) to assign users and groups to the application. If you choose to scope who will be provisioned based solely on attributes of the user or group, you can use a scoping filter as described [here](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/define-conditional-rules-for-provisioning-user-accounts).

- When assigning users and groups to myViewBoard, you must select a role other than **Default Access**. Users with the Default Access role are excluded from provisioning and will be marked as not effectively entitled in the provisioning logs. If the only role available on the application is the default access role, you can [update the application manifest](https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) to add additional roles.

- Start small. Test with a small set of users and groups before rolling out to everyone. When scope for provisioning is set to assigned users and groups, you can control this by assigning one or two users or groups to the app. When scope is set to all users and groups, you can specify an [attribute based scoping filter](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/define-conditional-rules-for-provisioning-user-accounts).

**Step 5. Configure automatic user provisioning to myViewBoard** 
This section guides you through the steps to configure the Azure AD provisioning service to create, update, and disable users and/or groups in myViewBoard based on user and/or group assignments in Azure AD.

**To configure automatic user provisioning for myViewBoard in Azure AD:**
1. Sign in to the [Azure portal](https://portal.azure.com/) and select **Enterprise Applications**, then select **All applications**.
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial1.png)
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial2.png)
1. In the applications list, select **myViewBoard SCIM Connect**.
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial3.png)
1. Select the **Provisioning** tab. Click on **Get started**.
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial4.png)
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial5.png)
1. Set the **Provisioning Mode** to **Automatic**.
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial6.png)
1. Copy **SCIM URL** and **SCIM token** from myviewboard.com and then paste them in **Tenant URL** and **Secret Token**
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial7.png)
1. In the Azure portal, click **Test Connection** to ensure Azure AD can connect to myViewBoard. If the connection fails, ensure your myViewBoard account has Admin permissions and try again.
1. Click **Save**.
1. In the **Mappings** section, there are two sets of attribute mappings: one for **Users object** and the other for **Groups object**. Select each one to review the attributes which are synchronized from Azure Active Directory to myViewBoard.
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial8.png)
1. To configure scoping filters, refer to the following instructions provided in the [Scoping filter tutorial](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/define-conditional-rules-for-provisioning-user-accounts).
1. To enable the Azure AD provisioning service for myViewBoard, change the **Provisioning Status** to **On** in the **Settings** section.
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial9.png)
1. Define the users and/or groups that you would like to provision to myViewBoard by choosing the desired values in **Scope** in the **Settings** section.
![image.png](media/myviewboard-scim-connect-tutorial/myviewboard-scim-connect-tutorial10.png)
1. When you are ready to provision, click **Save**.

This operation starts the initial synchronization cycle of all users and groups defined in **Scope** in the **Settings** section. The initial cycle takes longer to perform than subsequent cycles, which occur approximately every 40 minutes as long as the Azure AD provisioning service is running.

**Step 6. Monitor your deployment**
Once you've configured provisioning, use the following resources to monitor your deployment:

1. Use the [provisioning logs](https://docs.microsoft.com/en-us/azure/active-directory/reports-monitoring/concept-provisioning-logs) to determine which users have been provisioned successfully or unsuccessfully
1. Check the [progress bar](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/application-provisioning-when-will-provisioning-finish-specific-user) to see the status of the provisioning cycle and how close it is to completion
1. If the provisioning configuration seems to be in an unhealthy state, the application will go into quarantine. Learn more about quarantine states [here](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/application-provisioning-quarantine-status).

**Additional resources**
[Managing user account provisioning for Enterprise Apps](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/configure-automatic-user-provisioning-portal)
[What is application access and single sign-on with Azure Active Directory?](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/what-is-single-sign-on)

**Next steps**
[Learn how to review logs and get reports on provisioning activity](https://docs.microsoft.com/en-us/azure/active-directory/app-provisioning/check-status-user-account-provisioning)
