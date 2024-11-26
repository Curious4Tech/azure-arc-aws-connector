# azure-arc-aws-connector
Step-by-step guide to configure and manage AWS VMs using Azure Arc, including setup, prerequisites, and management options

# Azure Arc Connector for AWS VMs

This guide provides step-by-step instructions to create a connector in **Azure Arc** for managing and monitoring **AWS VMs**.

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
- **Download** or **Copy** the script provide.
- Click **Go to AWS CloudFormation Stacks** to finalize the connector.

![image](https://github.com/user-attachments/assets/6498a8e8-b469-4cb5-aada-ab192e185ef4)


### 6. Deploy the CloudFormation Template
1. Once the connector is created, Azure generates a **CloudFormation template**.
2. Deploy the template in your AWS account:
   - Log in to the **AWS Management Console**.
   - Navigate to **CloudFormation**.
   - Click on **Create Stack**

![image](https://github.com/user-attachments/assets/1fb6e830-ae77-435f-90c7-982d02f2ba43)

  - Choose as you see on this screenhot for the sake of this demo. Click on **upload file** to upload the script provided by Azure.

![image](https://github.com/user-attachments/assets/a85cb354-68ba-47a9-950c-c53872d8e123)

  - Give a name for your stack (e.g; WAS2AZURE)

![image](https://github.com/user-attachments/assets/68cc28d3-0556-4c38-9388-0f1dca6d2a86)

 - Follow the wizard and at the en click on **Submit**

![image](https://github.com/user-attachments/assets/ccca99a5-b54a-4a1a-8ae3-23e47acc599c)


### 7. Complete the Connector Setup
- Return to the Azure portal.
- Follow the instructions to finalize the connector setup.

### 8. Enable Arc Onboarding for AWS VMs
1. Ensure your AWS EC2 instances meet these prerequisites:
   - **IAM Role**: Attach the `ArcForServerSSMRole` to each EC2 instance.
   - **SSM Agent**: Installed on all EC2 instances.
   - **Connected Machine Agent**: Installed as part of the onboarding process.

2. Configure the connectivity method for the **Connected Machine agent**:
   - **Public Endpoint**: Use direct internet access.
   - **Proxy Server**: Configure a proxy for agent communication.

### 9. Configure Sync Options
- Set up periodic sync intervals to determine how frequently Azure scans and updates AWS account information.

---

## Validation and Management

After completing the setup:

1. **Verify AWS VMs**:
   - AWS VMs will appear under **Azure Arc > Servers** in the Azure portal.

2. **Enable Monitoring**:
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
