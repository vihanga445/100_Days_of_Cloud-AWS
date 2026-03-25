# Day 19: Attaching an IAM Policy to a User 🔑👤

## 📖 The Concept
In AWS, an identity (User, Group, or Role) has no permissions by default. To grant access, you must **Attach** a policy to that identity.

* **Direct Attachment:** This is the process of linking a specific set of rules (Policy) to a specific individual (User).
* **Identity-Based Policy:** This type of policy "lives" with the user. Wherever the user goes in AWS, these permissions follow them.
* **The Result:** The user `iamuser_yousuf` now has the specific powers defined inside `iampolicy_yousuf`.

---

## 🏢 Business Scenario
The **Nautilus DevOps team** is finalizing the access setup for their engineer, Yousuf. They have already created his account and a custom security policy tailored to his specific job duties. To complete his onboarding, the team is now formally attaching the `iampolicy_yousuf` to his account, ensuring he has exactly the "Least Privilege" access required to assist with the cloud migration.

---

## 🛠️ Tasks Performed

1.  **Navigation:** Accessed the **IAM Dashboard > Users** section.
2.  **User Selection:** Located and selected the profile for `iamuser_yousuf`.
3.  **Permission Linking:** * Selected **Add permissions > Attach policies directly**.
    * Searched for the pre-existing customer-managed policy: `iampolicy_yousuf`.
    * Confirmed the selection and attached it to the user.
4.  **Verification:** Verified that the policy appears under the "Permissions policies" list for the user.

---

## 📸 Screenshots

### Selecting the Policy

<img width="1898" height="807" alt="Screenshot 2026-03-25 120931" src="https://github.com/user-attachments/assets/8708a5c7-dab4-4c26-8ef7-4999588822bf" />

<img width="1892" height="807" alt="Screenshot 2026-03-25 120643" src="https://github.com/user-attachments/assets/bf71d729-a26c-4c91-b7ed-b34b738d8952" />

### Permissions Summary

<img width="1909" height="811" alt="Screenshot 2026-03-25 120756" src="https://github.com/user-attachments/assets/31649b4b-02c6-4411-b3fa-0e44ac603920" />

<img width="1901" height="807" alt="Screenshot 2026-03-25 120854" src="https://github.com/user-attachments/assets/f2ca066d-3faf-4040-b5ed-5a7f883f563c" />



To attach a policy to a user via the terminal, you need the Policy ARN (Amazon Resource Name). The command looks like this:

```bash
aws iam attach-user-policy --user-name iamuser_yousuf --policy-arn arn:aws:iam::ACCOUNT_ID:policy/iampolicy_yousuf
