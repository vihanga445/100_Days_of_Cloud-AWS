# Day 21: Deploying EC2 with Static Elastic IP 🚀📍

## 📖 The Concept
This task demonstrates the implementation of **Static Networking** in the cloud. While EC2 instances are dynamic, business applications often require a fixed entry point.

* **Elastic IP (EIP):** A reserved public IPv4 address that remains attached to your AWS account.
* **Association:** The process of mapping a public EIP to a specific instance's private network interface.

---

## 🏢 Business Scenario
The **Nautilus Development Team** requires a stable environment for their new application. To avoid disruption during maintenance or reboots, the DevOps team has provisioned a **t2.micro** instance and assigned it a permanent **Elastic IP**. This ensures the application endpoint remains `nautilus-eip` regardless of the instance's underlying lifecycle events.

---

## 🛠️ Tasks Performed

1.  **Server Provisioning:** Launched `nautilus-ec2` using the Ubuntu Linux AMI.
2.  **IP Reservation:** Allocated a new Elastic IP from Amazon's pool and tagged it as `nautilus-eip`.
3.  **Network Mapping:** Successfully associated the EIP with the `nautilus-ec2` instance.
4.  **Verification:** Confirmed that the instance's public IPv4 address reflects the static EIP.

---

## 📸 Screenshots
*Insert your lab screenshots here.*

### Instance Configuration

<img width="1906" height="807" alt="Screenshot 2026-03-28 005521" src="https://github.com/user-attachments/assets/1505180f-77d1-43df-8a4d-102bba51180b" />


### Elastic IP Mapping

<img width="1910" height="806" alt="Screenshot 2026-03-28 011420" src="https://github.com/user-attachments/assets/3f9f5ddc-ce2c-44fd-9e54-ace3b9d7f132" />
<img width="1919" height="788" alt="Screenshot 2026-03-28 011441" src="https://github.com/user-attachments/assets/2f235254-c875-4d64-8ed6-1b137b2054e7" />

---

Verification command to ensure the EIP is correctly linked:

```bash
aws ec2 describe-addresses --filters "Name=tag:Name,Values=nautilus-eip" --query "Addresses[*].InstanceId"
