# azure-arc-aws-connector
Step-by-step guide to configure and manage AWS VMs using Azure Arc, including setup, prerequisites, and management options

# Azure Arc Connector for AWS VMs

This guide provides step-by-step instructions to create a connector in **Azure Arc** for managing and monitoring **AWS VMs** (AWS VMs onboading).

---

## Prerequisites

Before starting, ensure the following:

- **Azure Account**: An active Azure subscription.  
- **AWS Account**: An active Azure subscription
---

## Steps to Create an Azure Arc Connector for AWS VMs

### 1. Sign In to Azure Portal
- Go to the [Azure portal](https://portal.azure.com).
- Navigate to **Azure Arc > Azure Arc resources > Machines > Add/Create > Add a machine**

![image](https://github.com/user-attachments/assets/cd99131f-3d1c-4590-af6f-db3c9d21e613)


### 2. Configure Environment Settings
1. Click  **Add servers** in **Add servers from AWS**

![image](https://github.com/user-attachments/assets/21c7adde-431b-4611-9a9e-ba961537be3d)

### 3. Enter AWS Connector Details
Provide project details:

- **Subscription**: Select your Azure subscription.
- **Resource Group**: Choose an existing or create a new resource group.
- **Connector Name**: A descriptive name for the connector.
- **Azure region**: Select the Azure region.

![image](https://github.com/user-attachments/assets/51ad3e1a-f625-474a-b9f8-27138b2362e0)

Provide AWS account details: 
- **Account type** : Single account or Organisation account.
- **AWS Account ID**: Enter your AWS account ID.
- Click **Next**.

![image](https://github.com/user-attachments/assets/6d28e98f-76e1-449b-a0cd-cb8ff91c4ea5)

### 4. Solution
- Click on **+Add** in **Arc onboarding** section.

![image](https://github.com/user-attachments/assets/4ed203aa-8a5f-4c94-bad0-654e2125e494)

- A new window will open, for the sake of this demo, don't change anything, now click on **Save**.

![image](https://github.com/user-attachments/assets/1c0998fb-03a4-4073-b5b8-8d0b78fc0cbc)

- Review and click **Next**.

![image](https://github.com/user-attachments/assets/9398ce44-9c23-4ab1-88d9-72683c7c4d62)


### 5. Add AWS connector
- **Download** or **Copy** the script generated.
- Click **Go to AWS CloudFormation Stacks** to finalize the connector.

![image](https://github.com/user-attachments/assets/6498a8e8-b469-4cb5-aada-ab192e185ef4)


### 6. Deploy the CloudFormation Template
1. Once the connector is created, Azure generates a **CloudFormation template**.
2. Deploy the template in your AWS account:
   - Log in to the **AWS Management Console**.
   - Navigate to **CloudFormation**.
   - Click on **Create Stack**

![image](https://github.com/user-attachments/assets/1fb6e830-ae77-435f-90c7-982d02f2ba43)

  - Choose as you see on this screenhot for the sake of this demo. Click on **choose file** to upload the script provided by Azure that you have already downloaded.

![image](https://github.com/user-attachments/assets/a85cb354-68ba-47a9-950c-c53872d8e123)

  - Give a name for your stack (e.g; WAS2AZURE)

![image](https://github.com/user-attachments/assets/68cc28d3-0556-4c38-9388-0f1dca6d2a86)

 - Follow the wizard and at the end click on **Submit**

![image](https://github.com/user-attachments/assets/ccca99a5-b54a-4a1a-8ae3-23e47acc599c)

 - Your stack creation is in progress, it will take few minutes to fully be created.

![image](https://github.com/user-attachments/assets/b9573adf-a471-4cea-988f-1ef780aed6c4)


### 7. Complete the Connector Setup
- Return to the Azure portal.
- Click on **Next**.
- **Review and create**: Verify if everything is correct and then click on **Create**

![image](https://github.com/user-attachments/assets/9d539ac7-cc31-453d-815b-cf92a06e08d9)

### 8. **Verify AWS VMs**
  - Go to your created connector, AWS VMs will appear under **Resources**. You should see your AWS servers (VMs).
  
![image](https://github.com/user-attachments/assets/cc56ebcc-82bd-40bf-9df0-c152698c374f)

  - If you go back to your **Azure Arc > Azure arc resources > Machines**, you should also see your AWS servers (VMs).

![image](https://github.com/user-attachments/assets/6115e868-4ab5-49ca-97c3-ddb66dcc4341)

## 9. **Validation and Management**

After completing the setup:

1. **Enable Monitoring**:
   - Use tools like **Azure Policy**, **Azure Monitor**, and **Microsoft Defender for Cloud** to manage and monitor AWS resources.

---

## Resources

- [Azure Arc Documentation](https://learn.microsoft.com/en-us/azure/azure-arc/)
- [Azure Monitor](https://learn.microsoft.com/en-us/azure/azure-monitor/)
- [Microsoft Defender for Cloud](https://learn.microsoft.com/en-us/azure/defender-for-cloud/)

---


## Conclusion

Great job setting up the Azure Arc connector for AWS VMs! You’ve successfully enabled unified management of your AWS and Azure resources, with access to tools like **Azure Policy**, **Azure Monitor**, and **Defender for Cloud**.  

If this repo helped you, please ⭐ star it and share your feedback or suggestions through an issue or pull request. Happy managing! 😊
