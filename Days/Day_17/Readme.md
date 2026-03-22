# Day 17: Creating an IAM User Group 👥🛡️

## 📖 The Concept
An **IAM User Group** is a collection of IAM users. Groups let you specify permissions for multiple users, which can make it easier to manage the permissions for those users.

* **Inheritance:** Any user added to the group automatically gains the permissions assigned to that group.
* **Efficiency:** Instead of managing individuals, DevOps engineers manage "Roles" or "Departments."
* **Security:** It reduces the chance of forgetting to remove permissions from a specific user because you manage the group as a single entity.

---

## 🏢 Business Scenario
The **Nautilus DevOps team** is scaling up their cloud operations. To prepare for a new team of engineers, they are setting up the organizational structure in IAM. By creating `iamgroup_rose`, they are establishing a container where they can later apply specific security policies that will govern how a whole team interacts with AWS resources.

---

## 🛠️ Tasks Performed

1.  **Navigation:** Accessed the **IAM Dashboard** and selected the **User groups** section.
2.  **Group Creation:** * Initiated the "Create group" process.
    * Assigned the group name: `iamgroup_rose`.
3.  **Policy & Membership:** Created the group as an empty container (no initial users or policies attached) to serve as a baseline for future configuration.
4.  **Verification:** Confirmed `iamgroup_rose` appears in the User groups list with 0 users and 0 attached policies.

---

## 📸 Screenshots

### Group Configuration

<img width="1547" height="720" alt="Screenshot 2026-03-22 231720" src="https://github.com/user-attachments/assets/2ca986e3-31b0-48f7-b679-b33ab7ada35e" />


### Final Groups List

<img width="1564" height="707" alt="Screenshot 2026-03-22 231729" src="https://github.com/user-attachments/assets/5b3249c9-5e82-4fc3-ac7d-f4d65e966f8c" />


To create a user group via the terminal, use this command:

```bash
aws iam create-group --group-name iamgroup_rose
