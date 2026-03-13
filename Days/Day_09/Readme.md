# Day 09: Enabling EC2 Termination Protection 🛡️🏗️

## 📖 The Concept
**Termination Protection** is a critical safety feature that prevents an EC2 instance from being accidentally deleted. 

* **The Risk:** Termination is permanent. When an instance is terminated, its root volume (OS) is typically deleted, and the instance cannot be started again.
* **The Solution:** By enabling this protection, the `Terminate` command will fail in both the AWS Console and the CLI until the protection is explicitly disabled.

---

## 🏢 Business Scenario
The **Nautilus DevOps team** is managing the `datacenter-ec2` instance, which houses foundational infrastructure for their migration. Because this instance is difficult to rebuild and critical for ongoing operations, they have mandated **Termination Protection** to prevent any accidental "wrecking ball" moments during their incremental migration process.

---

## 🛠️ Tasks Performed

1.  **Navigation:** Logged into the AWS Management Console and navigated to the **EC2 Instances** page.
2.  **Resource Identification:** Located the pre-existing instance named `datacenter-ec2`.
3.  **Applying Safety Rules:** * Selected **Actions > Instance Settings > Change termination protection**.
    * Toggled the setting to **Enable**.
4.  **Verification:** Confirmed that the attribute was saved successfully.

---

## 📸 Screenshots

### Modifying Termination Protection
<img width="912" height="727" alt="Screenshot 2026-03-14 001107" src="https://github.com/user-attachments/assets/d0949481-64f0-47c3-9b8a-e8bb504bde52" />

### Confirmation of Setting


<img width="1565" height="325" alt="Screenshot 2026-03-14 001127" src="https://github.com/user-attachments/assets/83b670ec-d637-410f-b050-5a1653f71aba" />



---

To check if an instance is protected from termination using the terminal:

```bash
aws ec2 describe-instance-attribute --instance-id YOUR_INSTANCE_ID --attribute disableApiTermination
