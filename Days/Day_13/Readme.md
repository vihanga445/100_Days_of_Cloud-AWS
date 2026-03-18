# Day 13: Creating a Custom AMI (Amazon Machine Image) 💿📸

## 📖 The Concept
An **AMI (Amazon Machine Image)** provides the information required to launch an instance. It is essentially a "Master Template" for your servers.

* **Reusability:** Once you configure a server perfectly, an AMI allows you to replicate that exact environment instantly.
* **Backup & Recovery:** AMIs serve as a full-system backup. If your server crashes, you can launch a new one from your AMI in minutes.
* **Consistency:** It ensures that every server in your "fleet" is running the exact same version of software and configurations.

---

## 🏢 Business Scenario
The **Nautilus DevOps team** has finished configuring the `xfusion-ec2` instance with all necessary application dependencies. To ensure they can scale their infrastructure and recover quickly from errors, they are creating a "Golden Image" named `xfusion-ec2-ami`. This allows the team to move from manual configuration to automated deployment.

---

## 🛠️ Tasks Performed

1.  **Navigation:** Accessed the **EC2 Dashboard > Instances** in the `us-east-1` region.
2.  **Image Creation:** * Selected the `xfusion-ec2` instance.
    * Used the **Actions > Image and templates > Create image** feature.
    * Named the image `xfusion-ec2-ami`.
3.  **Monitoring:** Navigated to the **AMIs** section under the Images menu.
4.  **Verification:** Monitored the creation process until the AMI status transitioned from `pending` to **`available`**.

---

## 📸 Screenshots

### Image Creation Settings


<img width="797" height="407" alt="Screenshot 2026-03-18 002123" src="https://github.com/user-attachments/assets/2201ad20-27d3-4c50-8d4a-57d963d1cd63" />


<img width="1446" height="608" alt="Screenshot 2026-03-18 002030" src="https://github.com/user-attachments/assets/ffc68af2-5489-4bfd-a370-5a365da6694d" />



### AMI Status: Available


<img width="1087" height="242" alt="Screenshot 2026-03-18 102033" src="https://github.com/user-attachments/assets/9328fa2b-c8a7-4d9f-bbba-81c95954945c" />


---

To create an image via the terminal and check its status:

```bash
# Create the image
aws ec2 create-image --instance-id i-12345678 --name "xfusion-ec2-ami"

# Check the status
aws ec2 describe-images --filters "Name=name,Values=xfusion-ec2-ami" --query "Images[*].State"
