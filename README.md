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

### 4. Select Plans
- Enable the **Servers** plan to extend Microsoft Defender for Servers coverage to your AWS EC2 instances.
- Review and click **Next**.

### 5. Review and Create the Connector
- Validate the configuration details.
- Click **Create** to finalize the connector.

### 6. Deploy the CloudFormation Template
1. Once the connector is created, Azure generates a **CloudFormation template**.
2. Deploy the template in your AWS account:
   - Log in to the **AWS Management Console**.
   - Navigate to **CloudFormation**.
   - Deploy the template to set up the necessary IAM roles and permissions.

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
