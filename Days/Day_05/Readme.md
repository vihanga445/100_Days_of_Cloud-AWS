# Day 05: Creating an EBS Volume 💾

## 📖 The Concept
An **EBS (Elastic Block Store) Volume** is a durable, block-level storage device that you can attach to your instances. 

Think of it as a **Virtual Hard Drive**:
* **Detachable:** You can unplug it from one server and plug it into another (as long as they are in the same area).
* **GP3:** This is the latest generation of General Purpose SSDs. It allows you to scale performance (speed) without having to buy more storage space.
* **Persistence:** Even if you turn off your virtual computer, the data on this "drive" stays safe.

---

## 🏢 Business Scenario
As the **Nautilus DevOps team** continues their incremental migration, they need separate storage volumes to hold application logs and database files. By creating `nautilus-volume` as a **gp3** type, they are using a cost-effective, high-performance storage solution that can grow with their needs.

---

## 🛠️ Tasks Performed

1.  **Region Selection:** Confirmed the working region as **us-east-1**.
2.  **Navigation:** Accessed the **EC2 Dashboard** and navigated to **Elastic Block Store > Volumes**.
3.  **Volume Creation:** Configured a new volume with the following specs:
    * **Volume Type:** `gp3` (General Purpose SSD)
    * **Size:** `2 GiB`
    * **Availability Zone:** Selected a zone within `us-east-1`.
4.  **Tagging:** Added a Name tag with the value `nautilus-volume` for easy identification.

---



### Volume Configuration

<img width="1897" height="804" alt="Screenshot 2026-03-09 221615" src="https://github.com/user-attachments/assets/e1fe331e-d9f1-44bd-8f16-61a08526d259" />

<img width="1888" height="313" alt="Screenshot 2026-03-09 221625" src="https://github.com/user-attachments/assets/3d9344d5-af48-46d1-924e-3a8aee2d016f" />

### Volume Created Successfully

<img width="1915" height="808" alt="Screenshot 2026-03-09 221637" src="https://github.com/user-attachments/assets/5f8c5252-997a-4335-933b-4495b8ed7967" />


<img width="998" height="768" alt="Screenshot 2026-03-09 221718" src="https://github.com/user-attachments/assets/34ebdc2c-3df6-419d-b07d-e6ddb1736bcd" />



To see your newly created volume and its details via the terminal, use:

```bash
aws ec2 describe-volumes --filters "Name=tag:Name,Values=nautilus-volume"
