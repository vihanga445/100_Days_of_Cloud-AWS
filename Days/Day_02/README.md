# Day 02: Creating a Security Group 🛡️

## 📖 The Concept
In the cloud, we don't just leave our servers "naked" to the internet. We use a **Security Group**, which acts as a **Virtual Firewall**. 

Think of it like a **Security Guard** standing at the entrance of your office:
* **The Rules:** The guard has a list of who is allowed to come in and through which door.
* **Inbound Rules:** These control the traffic coming **into** your server.
* **Ports:** Different "doors" for different tasks (e.g., Door 80 for website visitors, Door 22 for the maintenance crew).



---

## 🏢 Business Scenario
The **Nautilus DevOps team** is migrating their infrastructure to AWS in small, manageable steps. Before launching their application servers, they need to define the security boundaries. By creating the `nautilus-sg`, they are ensuring that only web traffic (HTTP) and administrative traffic (SSH) can reach their servers, keeping everything else blocked by default.

---

## 🛠️ Tasks Performed

1.  **Region Selection:** Logged into the AWS Console and ensured the region was set to **us-east-1** (N. Virginia).
2.  **Navigation:** Navigated to **VPC Dashboard > Security Groups**.
3.  **SG Creation:** Created a new Security Group with these details:
    * **Name:** `nautilus-sg`
    * **Description:** `Security group for Nautilus App Servers`
    * **VPC:** Selected the **Default VPC**.
4.  **Inbound Rules Configuration:**
    * **HTTP (Port 80):** Source set to `0.0.0.0/0` (Allows public web access).
    * **SSH (Port 22):** Source set to `0.0.0.0/0` (Allows remote terminal access).

> **Pro-Tip:** In a real-world job, you should never leave SSH (Port 22) open to `0.0.0.0/0`. You should restrict it to your specific IP address to prevent brute-force attacks!

---

## 📸 Screenshots

### Security Group Settings
 <img width="1884" height="500" alt="Screenshot 2026-03-05 202710" src="https://github.com/user-attachments/assets/1f89b97a-63e3-4dd8-94d6-31c2fe0c29ae" />


### Inbound Rules Configured

<img width="1602" height="330" alt="Screenshot 2026-03-05 202927" src="https://github.com/user-attachments/assets/41bb4794-b4e7-4a4b-bbef-eea16fbe4f68" />


## 💻 AWS(CLI)
 Verify the creation of this security group using the **AWS CLI** with the following command:

```bash
aws ec2 describe-security-groups --group-names nautilus-sg
