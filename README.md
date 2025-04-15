# Create-Test-a-Dynamic-Group 
In this lab, you will:

Create a Dynamic Group in Microsoft Entra (Azure AD).

Set up a membership rule to automatically add users who match specific criteria (e.g., department, job title, etc.).

Verify that the group updates membership automatically when a user’s attributes match the rule.

 Prerequisites

You have at least a Premium P1 or P2 license (Dynamic Groups is a premium feature).

You can access https://entra.microsoft.com or the Microsoft Entra admin center (formerly Azure AD admin center).

You have permissions to create and manage groups in Microsoft Entra ID

1. Navigate to Groups in Microsoft Entra
   
Sign in to the Microsoft Entra admin center using your admin or privileged account.

In the left navigation pane, select Groups.

![2025-04-14 19_52_54-Groups - Microsoft Entra admin center - Personal - Microsoft​ Edge](https://github.com/user-attachments/assets/b2ce6248-b451-40ec-a9d7-73ee5a4c4466)

2. Create a New Group
Click + New group.

![2025-04-14 19_56_13-Groups - Microsoft Entra admin center - Personal - Microsoft​ Edge](https://github.com/user-attachments/assets/ddefeec8-bdde-4799-9ee9-48857b2b73af)

Set Group type to Security (so we can control memberships easily).

Give it a Name (e.g., “Dynamic-Dept-Group”).

Under Membership type, select Dynamic User.

3. Define the Dynamic Membership Rule
Once you select Dynamic User as the Membership type:

Click Add dynamic query (or Add dynamic rule).

In the rule builder, choose an attribute to filter on. Common attributes include:

department

jobTitle

userPrincipalName

UsageLocation, etc.

For example, you might create a rule that automatically includes users who have Department = “Sales.”

Property: department

Operator: Equals

Value: Sales

Click Add expression (if using the rule builder) or OK to confirm.

The resulting syntax might look like department -eq "Sales".

Click Save to finalize the dynamic membership rule.

![2025-04-14 20_00_17-Dynamic-Dept-Group - Microsoft Entra admin center - Personal - Microsoft​ Edge](https://github.com/user-attachments/assets/faed3501-f320-4211-a7dd-e37124a01450)

Create and Review the Group

Click Create (or Save) to finish creating the group.

You’ll return to the Groups list, where you’ll see your new dynamic group.

Select your new group to view its Overview. Under Members, you might see No members initially (it can take a few minutes for Azure AD to process the new rule).

![2025-04-14 20_03_49-](https://github.com/user-attachments/assets/1f547789-49f4-47c7-b5c8-18c46dc6be38)

5. Verify Dynamic Membership
Pick a test user whose profile you can edit.

In Microsoft Entra ID > Users, choose a user that you want to place in the Sales department (or whatever attribute you used).

![2025-04-14 20_14_45-Dynamic-Dept-Group - Microsoft Entra admin center - Personal - Microsoft​ Edge](https://github.com/user-attachments/assets/6c3dcf76-5bb7-4def-920f-d6450007908e)

Edit their profile and change the Department attribute to Sales (or your chosen value).

Wait a few minutes (sometimes up to 30 minutes, but typically quicker).

![2025-04-14 20_17_09-](https://github.com/user-attachments/assets/3f4b5cf0-a7fc-4a05-8367-5d7084329c9c)

As you see from my audit log it verifies the user was added to my dynamic group


![2025-04-14 20_30_07-Audit Log Details - Microsoft Entra admin center - Personal - Microsoft​ Edge](https://github.com/user-attachments/assets/df97faac-ad7b-425c-b49c-8dcca93497a2)


![2025-04-14 20_35_36-](https://github.com/user-attachments/assets/f881f72d-6c5d-4765-ad9b-c3384d08e350)

By the end of this lab, you have:

Created a Dynamic Group in Microsoft Entra (Azure AD).

Configured membership rules so that users automatically join (or leave) the group based on attributes.

Verified the dynamic membership update by adjusting a user’s profile.

This demonstrates how Microsoft Entra can automatically manage group memberships, which is especially useful for scenarios like role-based access control, license assignments, and targeted application access — all without requiring a separate Azure subscription.
