### This is a sample repository that showcases GitHub Markdown formatting. 

It provides a good understanding of how the [basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) is applied/used. 

Hope this is helpful :+1:

# Why Terraform ?

> There are multiple reasons why Terraform is used over other IaC tools but below are the **main** reasons.

1. **Multi-Cloud Support**
2. *Large Ecosystem*
3. **Declarative** _Syntax_
4. ***State Management***
5. Plan <sub>and</sub> Apply
6. _Community Support_
7. **Integration with Other Tools** ~~such~~
8. **HashiCorp Configuration Language** `HCL Language`


# Getting Started 

> To get started with Terraform it's important to understand some key terminology and concepts. Here are some fundamental terms and explanations.

`Provider:` A provider is a plugin for Terraform that defines and manages resources for a specific cloud or infrastructure platform. Examples of providers include AWS, Azure, Google Cloud, and many others. You configure providers in your Terraform code to interact with the desired infrastructure platform.

`Resource:` A resource is a specific infrastructure component that you want to create and manage using Terraform. Resources can include virtual machines, databases, storage buckets, network components, and more. Each resource has a type and configuration parameters that you define in your Terraform code.

`Module:` A module is a reusable and encapsulated unit of Terraform code. Modules allow you to package infrastructure configurations, making it easier to maintain, share, and reuse them across different parts of your infrastructure. Modules can be your own creations or come from the Terraform Registry, which hosts community-contributed modules.

`Configuration File:` Terraform uses configuration files (often with a .tf extension) to define the desired infrastructure state. These files specify providers, resources, variables, and other settings. The primary configuration file is usually named main.tf, but you can use multiple configuration files as well.

`Variable:` Variables in Terraform are placeholders for values that can be passed into your configurations. They make your code more flexible and reusable by allowing you to define values outside of your code and pass them in when you apply the Terraform configuration.

`Output:` Outputs are values generated by Terraform after the infrastructure has been created or updated. Outputs are typically used to display information or provide values to other parts of your infrastructure stack.

`State File:` Terraform maintains a state file (often named terraform.tfstate) that keeps track of the current state of your infrastructure. This file is crucial for Terraform to understand what resources have been created and what changes need to be made during updates.

`Plan:` A Terraform plan is a preview of changes that Terraform will make to your infrastructure. When you run terraform plan, Terraform analyzes your configuration and current state, then generates a plan detailing what actions it will take during the apply step.

`Apply:` The terraform apply command is used to execute the changes specified in the plan. It creates, updates, or destroys resources based on the Terraform configuration.

`Workspace:` Workspaces in Terraform are a way to manage multiple environments (e.g., development, staging, production) with separate configurations and state files. Workspaces help keep infrastructure configurations isolated and organized.

`Remote Backend:` A remote backend is a storage location for your Terraform state files that is not stored locally. Popular choices for remote backends include Amazon S3, Azure Blob Storage, or HashiCorp Terraform Cloud. Remote backends enhance collaboration and provide better security and reliability for your state files.

> [!CAUTION] 
These are some of the essential terms you'll encounter when working with Terraform. As you start using Terraform for your infrastructure provisioning and management, you'll become more familiar with these concepts and how they fit together in your IaC workflows.

# Install Terraform

> Links with instructions according to your OS:

## Windows

- Install Terraform from the Downloads [Page](https://developer.hashicorp.com/terraform/downloads)

## Linux

- Follow the steps provided in the Downloads [Page](https://developer.hashicorp.com/terraform/downloads) for Linux.

## macOS

- Follow the steps provided in the Downloads [Page](https://developer.hashicorp.com/terraform/downloads) for macOS.

  
# Setup Terraform for AWS
![Terraform+AWS](https://www.pedroalonso.net/static/2a6861df2748123c1a77570b3ecf385b/e9d78/tf-aws.webp)

> To configure AWS credentials and set up Terraform to work with AWS, you'll need to follow these steps:

1. Install AWS CLI (Command Line Interface):

> [!IMPORTANT]
> Make sure you have the AWS CLI installed on your machine. You can download and install it from the AWS CLI download page.

2. Create an AWS IAM User:
To interact with AWS programmatically, you should create an IAM (Identity and Access Management)
> [!TIP]
> user must be  with appropriate permissions.
Here's how to create one:

  - [x] [Log in to the AWS Management Console with an account that has administrative privileges]([url](https://aws.amazon.com/console/)).

  - [ ] [Navigate to the IAM service]([url](https://aws.amazon.com/iam/)).

  - [ ] Click on "Users" in the left navigation pane and then click "Add user."
  
        - Choose a username, select "Programmatic access" as the access type, and click "Next: Permissions."
    
          - Attach policies to this user based on your requirements. At a minimum, you should attach the "AmazonEC2FullAccess" policy for basic EC2 operations. If you need access to other AWS services, attach the relevant policies accordingly.
      
            - Review the user's configuration and create the user. Be sure to save the Access Key ID and Secret Access Key that are displayed after user creation; you'll need these for Terraform.

3. Configure AWS CLI Credentials using the terminal[^1].

[^1]: Use the AWS CLI to configure your credentials. Open a terminal and run:`aws configure`

> [!Note]
> It will prompt you to enter your AWS Access Key ID, Secret Access Key, default region, and default output format [reference link](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html).



