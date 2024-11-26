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

![image](https://github.com/user-attachments/assets/838a04d8-b9c9-4fa7-bda5-ba8f78731b07)


### 2. Configure Environment Settings
1. In the **Azure Arc** menu, select **Environment settings**.
2. Click **Add environment** and choose **Amazon Web Services**.

### 3. Enter AWS Connector Details
Provide the following details:

- **Connector Name**: A descriptive name for the connector.
- **Onboard**: Choose between:
  - **Single Account**: For one AWS account.
  - **Management Account**: For multiple accounts using AWS Organizations.
- **Subscription**: Select your Azure subscription.
- **Resource Group**: Choose an existing or create a new resource group.
- **Location**: Select the Azure region corresponding to your AWS account's region.
- **AWS Account ID**: Enter your AWS account ID.

Click **Next: Select plans**.

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
