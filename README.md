# Unauthenticated Basic Network Scan: Windows 11 VM

<img width="711" height="347" alt="TenableWindows" src="https://github.com/user-attachments/assets/1d8a2be7-82ea-42fb-a69d-8c8b4ec375e1" />


---

## Overview

The purpose of this lab was to complete an ***Unauthenticated Basic Network Scan***. An Unauthenticated Basic Network Scan is used to identify possible vulnerabilities that can be discovered without credentials. This type of scan is considered superficial since it does not go in depth vs a ***Authenticated Network Scan***. 

In this lab I provisioned a Windows 11 virtual machine, created a Network Security Group (NSG), associated the NSG with our virtual machine, created an inbound rule in our NSG to allow connections from the Tenable Scanner, created an inbound network traffic rule for Windows firewall in the virtual machine, created the Unauthenticated Basic Network Scan, reviewed the results from the scan, deleted the virtual machine. 

---

## Lab Objectives

By the end of this lab, I was able to:

- Provision a Windows 11 Virtual Machine
- Configure the NSG and associate it to the VM
- Create NSG inbound rule
- Create Windows Firewall inbound rule
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

The second step was to create an NSG, associate the NSG with the virtual machine and create an inbound rule to allow connections from the Tenable Scan Engine with IP address ```10.0.0.8```.

This was completed by following the steps outlined below:

1. Portal.azure.com/#home ***Exhibit 2***
2. Network Security Groups ***Exhibit 2***
3. Create ***Exhibit 3***
4. Review + Create ***Exhibit 4***
5. Vm-windows11-NSG ***Exhibit 5***
6. Associate ***Exhibit 6***
7. Inbound Rule IP Address ```10.0.0.8``` ***Exhibit 7***


### Exhibit 2
<img width="1921" height="982" alt="lab2" src="https://github.com/user-attachments/assets/abbd9be6-804c-4fe8-b6b9-460c0e8598f7" />



### Exhibit 3
<img width="1918" height="940" alt="lab3" src="https://github.com/user-attachments/assets/84dc7f20-0fe8-4db6-ba5f-c2519600292d" />



### Exhibit 4
<img width="1928" height="939" alt="lab4" src="https://github.com/user-attachments/assets/b1294cff-a91c-491b-ad38-0b1084321518" />



### Exhibit 5
<img width="1918" height="935" alt="lab5" src="https://github.com/user-attachments/assets/a7f29f43-bf8a-466f-811a-34477b8ae7d7" />



### Exhibit 6
<img width="1918" height="978" alt="lab6" src="https://github.com/user-attachments/assets/106dc2a3-b206-48c7-828f-b7ca0a4a0778" />



### Exhibit 7
<img width="1925" height="977" alt="lab7" src="https://github.com/user-attachments/assets/543fc0d1-4b7f-499f-b5f8-0fd21291e35b" />


### Why This Matters?

An NSG acts like an additional firewall that controls inbound and outbound network traffic. It is necessary to allow inbound traffic from Tenable's Scan Engine IP address ```10.0.0.8``` to allow Tenable reach our virtual machine. Without the inbound rule the NSG may block Tenable's connection resulting in incomplete or inaccurate scan results. 

---

### Step 3: Create Windows Firewall Inbound Rule

The third step was to create a Windows Firewall inbound rule inside of the virtual machine allowing network traffic from Tenable's Scan Engine IP address ```10.0.0.8``` . ***Exhibit 8***.

### Why This Matters?

Windows Firewall controls inbound and outbound network traffic to and from the endpoint. It is necessary to allow inbound traffic from Tenable's Scan Engine IP address ```10.0.0.8```. Without the inbound rule Windows Firewall may block Tenable's connection resulting in incomplete or inaccurate scan results. 

This was completed by following the steps outlined below shown in ***Exhibit 8***

1. Log into Virtual Machine
2. Open Firewall configurations
3. Inbound Rules
4. New Rule
5. Custom Rule

### Exhibit 8
<img width="1313" height="849" alt="lab8" src="https://github.com/user-attachments/assets/2eb0f1e4-ddca-4ca4-8769-91747233ae10" />

---

### Step 4: Create Unauthenticated Basic Network Scan

The fourth step was to Create Unauthenticated Basic Network Scan.

This was completed by following the steps outlined below:

1. Log into Tenable Vulnerability Management
2. Scans - Vulnerability Management Scans ***Exbihit 9***
3. Create Scan ***Exbihit 10***
4. Basic Network Scan ***Exbihit 11***
5. Target ```10.1.0.11``` ***Exbihit 12***
6. Credentials - None ***Exbihit 13***

### Exhibit 9

<img width="1929" height="982" alt="lab9" src="https://github.com/user-attachments/assets/7866e488-6912-4d57-8d8f-d3bd2f89d8f7" />


### Exhibit 10

<img width="1918" height="977" alt="lab10" src="https://github.com/user-attachments/assets/0939bf4e-a0bc-4d5a-8533-1a29139bca70" />


### Exhibit 11

<img width="1918" height="977" alt="lab11" src="https://github.com/user-attachments/assets/82085312-90bb-4ba1-bfdb-d24f0b36270d" />


### Exhibit 12

<img width="1918" height="976" alt="lab12" src="https://github.com/user-attachments/assets/6b7c9911-5be6-4f4f-b3e5-78f6901c16b8" />


### Exhibit 13

<img width="1918" height="985" alt="lab13" src="https://github.com/user-attachments/assets/aaad1be3-0027-41dd-90bf-5a9ba7bda55c" />


### Why This Matters?

You need to set the IP address of the target endpoint for the scan to yield accurate results. You need to leave credentials blank because it is a **Unauthenticated Basic Network Scan**.

---

### Step 5: Review Results

The fifth step was to review the results of the scan. Tenable returned the following results:

| Severity | Vulnerabilities |
|---|---|
| High | 0 |
| Medium | 4 |
| Low | 1 |

The Unauthenticated Basic Network Scan was finished in approximately 10 minutes ***Exibit 14***. The results showed the vulnerabilities that were found ***Exibit 15*** , the description for each vulnerability, the affected assets, the risk information such as CVSS scores, the solution to remediate the vulnerability ***Exhibit 16***  and an optional executive PDF summary ***Exhibit 17***.

### Exhibit 14

<img width="1918" height="981" alt="lab14" src="https://github.com/user-attachments/assets/bd141e01-a591-4c80-9c6d-483f474422a2" />


### Exhibit 15

<img width="1918" height="977" alt="lab15" src="https://github.com/user-attachments/assets/d5fb6ed1-ff26-4db3-83ac-1ad2f2d9f805" />


### Exhibit 16

<img width="1918" height="980" alt="lab16" src="https://github.com/user-attachments/assets/5d802de1-84b6-4012-96ac-c595cafc5d15" />

### Exhibit 17

<img width="873" height="468" alt="lab17" src="https://github.com/user-attachments/assets/ab469abb-465b-4d81-be40-8a430d620bfd" />


### Why This Matters?

It is important  to review the results of scans to learn about any possible vulnerabilities an organization  may have and take the necessary steps to implement the organization's **Playbook** if necessary. 

---

### Step 6: Clean Up

The final step was to perform cleanup by deleting the virtual machine to prevent unnecessary resource usage.

---

## Key Takeaways

- Credentials are not needed to perform a Unauthenticated Basic Network Scan.
- Create custom inbound network traffic rules to minimize incomplete scans.
- Unauthenticated Basic Network Scan is not as detailed as a Authenticated Basic Network Scan.
- Always review scan results for possible vulnerabilities.

---

## Conclusion

In this lab I successfully completed an Unauthenticated Basic Network Scan, created custom NSG and  Windows Firewall inbound rules to allow network traffic from Tenable and reviewed the results from the scan.

This lab help me enforce my understanding for Unauthenticated Basic Network Scan, NSG configurations, firewall inbound rule configurations and review scan results.  

---
```
Author        : Manuel Aguirre
LinkedIn      : linkedin.com/in/mannyaguirre/
GitHub        : github.com/mannyaguirre
Date Created  : May 8, 2026
Last Modified : May 13, 2026
Version       : 1.0
```
