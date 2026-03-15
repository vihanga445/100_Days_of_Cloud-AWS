# Day 11: Attaching an Elastic Network Interface (ENI) 🔌

## 📖 The Concept
An **Elastic Network Interface (ENI)** is a logical networking component in a VPC that represents a virtual network card.

* **Dual-Homing:** By attaching a second ENI, an instance can communicate on two different subnets simultaneously.
* **Portability:** You can detach an ENI from one instance and attach it to another, allowing network attributes (like Private IPs and MAC addresses) to follow the configuration rather than the hardware.

---

## 🏢 Business Scenario
The **Nautilus DevOps team** is configuring a multi-tier network architecture. They require the `datacenter-ec2` instance to have a dedicated interface for back-end data processing. By attaching the `datacenter-eni`, they are providing the server with the necessary hardware link to participate in the "Datacenter" sub-network.

---

## 🛠️ Tasks Performed

1.  **Health Check:** Verified that `datacenter-ec2` passed all initialization status checks (2/2 passed).
2.  **Navigation:** Accessed **EC2 > Network & Security > Network Interfaces**.
3.  **Attachment:** * Identified the `datacenter-eni` in an `available` state.
    * Used the **Attach** action to link the interface to the `datacenter-ec2` instance.
4.  **Verification:** Confirmed the interface status changed to `in-use`.


To attach a network interface via the command line, use the following:

```bash
aws ec2 attach-network-interface --network-interface-id eni-12345678 --instance-id i-12345678 --device-index 1
