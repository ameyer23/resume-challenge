# Access and Credentials Setup

Professional cloud engineers generally avoid configuring AWS credential files on their machines due to security concerns and the need to manage multiple AWS accounts. Instead, modern cloud environments leverage AWS Organizations to handle dozens or even hundreds of accounts. Here’s a guide to setting up AWS Organizations:


![Organization Diagram ](https://github.com/ameyer23/resume-challenge/blob/77b11dd734600cefca8df41a013b08981094f677/AccessCredentials/org_diagram.png)

**Step 1: Create an Initial AWS Account**
This account is solely for AWS Organizations/SSO setup and not for application development. Secure the root password with a reliable password manager.

**Step 2: Set Up Your AWS Organization**
Organization was created in AWS console.

**Step 3: Create Organizational Units (OUs)**
Establish at least two OUs, one for "production" and one for "test" environments.

**Step 4: Create New AWS Accounts Within Each OU**
Use these accounts for actual development. Utilize the + suffix on your root email address to simplify email management and ensure passwords are securely managed. This Organization’s setup was accomplished using the open-source tool org-formation, which is more efficient and cost-effective than AWS-native tools. Orgs-formation yml files are located in the AccessCredentials folder. Orgs-formation documentation repo link [here](https://github.com/org-formation/org-formation-cli/blob/master/docs/organization-resources.md#organizationalunit) for reference.

**Step 5: Set Up IAM Identity Center** 
Configure IAM Identity Center (formerly known as AWS Single Sign-On) in your root account to manage access across your organization. This can be done without third-party services and should include setting up MFA for enhanced security.

**Step 6: Access AWS IAM Identity Center from the Command Line**
Use the official AWS AM Identity Center CLI. This allows you to open AWS consoles from your command line without using long-lived credentials.

Following these steps will align your AWS management with professional cloud practices, enhancing security and efficiency.
