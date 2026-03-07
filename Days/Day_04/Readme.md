# Day 04: Enabling S3 Bucket Versioning 🕒

## 📖 The Concept
**S3 Versioning** is like a **Time Machine** for your data. 

* **The Problem:** If you delete a file in a standard folder, it's gone.
* **The Solution:** With Versioning enabled, AWS keeps a "hidden copy" of every version of a file. If you delete something by mistake, you can just go back in time and restore it!


---

## 🏢 Business Scenario
The **Nautilus DevOps team** is focused on data protection. They need to ensure that even if a developer accidentally overwrites a configuration file or deletes a backup, the data can be recovered instantly. For this task, I enabled versioning on the `datacenter-s3-10942` bucket.

---

## 🛠️ Tasks Performed

1.  **Navigation:** Logged into the AWS Console and opened the **S3 Service**.
2.  **Bucket Selection:** Identified the target bucket: `datacenter-s3-10942`.
3.  **Configuration:** * Navigated to the **Properties** tab of the bucket.
    * Located the **Bucket Versioning** card.
    * Clicked **Edit** and switched the status to **Enabled**.
4.  **Verification:** Saved changes and verified that the status now shows "Enabled."

---

## 📸 Screenshots
*Insert your screenshots here to show your progress!*


<img width="1916" height="804" alt="Screenshot 2026-03-07 231040" src="https://github.com/user-attachments/assets/5f7b146e-37d8-4462-98bb-26a576e78ead" />


<img width="1891" height="818" alt="Screenshot 2026-03-07 231240" src="https://github.com/user-attachments/assets/44e02200-ee5d-4e7e-9e18-dc5f4465e284" />

<img width="1918" height="823" alt="Screenshot 2026-03-07 231251" src="https://github.com/user-attachments/assets/581c68e5-f333-4384-a08f-77ae53683cfc" />


<img width="1919" height="831" alt="Screenshot 2026-03-07 231300" src="https://github.com/user-attachments/assets/f7199620-b0a0-42b7-a9b6-1e502635038d" />


<img width="979" height="766" alt="Screenshot 2026-03-07 231351" src="https://github.com/user-attachments/assets/debd9e7e-457f-4ab8-aaf6-e2c4f7354d4b" />


## CLI


```bash
aws s3api get-bucket-versioning --bucket datacenter-s3-10942
