# Unauthenticated-Basic-Network-Scan-Windows-11

---

## Overview

The purpose of this lab was to complete an ***Unauthenticated Basic Network Scan***. An Unauthenticated Basic Network Scan is used to identify possible vulnerabilities within a network that may be facing the internet. This type of scan is considered superficial since it does not go in depth vs a ***Authenticated Network Scan***. 

In this lab I provisioned a Windows 11 virtual machine, created a Network Security Group (NSG), associated the NSG with our virtual machine, created an inbound rule in our NSG to allow connections from the Tenable Scanner, disabled the Windows firewall in the virtual machine, created the Unauthenticated Basic Network Scan, reviewed the results from the scan, deleted the virtual machine. 

---

## Lab Objectives

By the end of this lab, I was able to:

- Provision a Windows 11 Virtual Machine
- Configure the NSG and associate it to the VM
- Create NSG inbound rule
- Disable the Windows Firewall of the VM
- Create Unauthenticated Basic Network Scan
- Review the scan results
- Clean up the virtual machine

---

## Tools Used

- Tenable Vulnerability Management
- Microsoft Azure
- Network Security Groups (NSG)
- Windows 11 Virtual Machine
- Remote Desktop Connection (RDC)
- Nessus Scanner
- Basic Network Scan
- Powershell

----

## Lab Environment

| Component | Description |
|---|---|
| Endpoint | Windows 11 Virtual Machine |
| Platform | Tenable Vulnerability Management |
| Platform | Microsoft Azure |
| Scanner Type | Nessus Scanner |
| Scan Type | Basic Agent Scan |
| Authentication Type | Unauthenticated |
| NSG Configuration | IP ```10.0.0.8``` allowed |

---

## Lab Steps

### Step 1: Provision Windows 11 Virtual Machine

The first step in this lab was to configure a Windows 11 Virtual Machine using Microsoft Azure shown in ***Exhibit 1***.

### Why This Matters?

The virtual machine will serve as our endpoint for the Unauthenticated Basic Network Scan. 

### Exhibit 1
<img width="1918" height="976" alt="lab1" src="https://github.com/user-attachments/assets/62c9de6b-c872-4dfe-b872-89be613d59a4" />

---

### Step 2: Create a Network Security Group (NSG), Association & Inbound Rule

The second step was to create an NSG, associate the NSG with the virtual machine and create an inbound rule to allow connections from the Tenable Scan Engine with IP address ```10.0.0.8```

This was completed by following the steps outlined below:

1. Portal.azure.com/#home ***Exhibit 2***
2. Network Security Groups ***Exhibit 2***
3. Create ***Exhibit 3***
4. Review + Create ***Exhibit 4***
5. Vm-windows11-NSG ***Exhibit 5***
6. Associate ***Exhibit 6***
7. Inbound Rule IP Address ```10.0.0.8``` ***Exhibit 7***

---

### Exhibit 2
<img width="1921" height="982" alt="lab2" src="https://github.com/user-attachments/assets/abbd9be6-804c-4fe8-b6b9-460c0e8598f7" />

---

### Exhibit 3
<img width="1918" height="940" alt="lab3" src="https://github.com/user-attachments/assets/84dc7f20-0fe8-4db6-ba5f-c2519600292d" />

---

### Exhibit 4
<img width="1928" height="939" alt="lab4" src="https://github.com/user-attachments/assets/b1294cff-a91c-491b-ad38-0b1084321518" />

---

### Exhibit 5
<img width="1918" height="935" alt="lab5" src="https://github.com/user-attachments/assets/a7f29f43-bf8a-466f-811a-34477b8ae7d7" />

---

### Exhibit 6
<img width="1918" height="978" alt="lab6" src="https://github.com/user-attachments/assets/106dc2a3-b206-48c7-828f-b7ca0a4a0778" />

---

### Exhibit 7
<img width="1925" height="977" alt="lab7" src="https://github.com/user-attachments/assets/543fc0d1-4b7f-499f-b5f8-0fd21291e35b" />

---

### Why This Matters?

An NSG acts like an additional firewall that controls inbound and outbound network traffic. It is necessary to allow inbound traffic from Tenable's Scan Engine IP address ```10.0.0.8``` to allow Tenable reach our virtual machine. Without the inbound rule the NSG may block Tenable's connection resulting in incomplete or inaccurate scan results. 

---

### Step 3: Disable Windows Firewall for the Virtual Machine

The third step was to disable the windows firewall inside of the virtual machine. ***Exhibit 8***

### Why This Matters?


### Exhibit 8
<img width="1571" height="1005" alt="lab8" src="https://github.com/user-attachments/assets/5c5ddad4-b02f-406d-ac6d-43a8a4137da5" />


## Key Takeaways

## Conclusion

```
Author        : Manuel Aguirre
LinkedIn      : linkedin.com/in/mannyaguirre/
GitHub        : github.com/mannyaguirre
Date Created  : May 8, 2026
Last Modified : May 8, 2026
Version       : 1.0
```
