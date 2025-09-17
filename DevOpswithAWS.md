# AWS account setup with EC2 Tutorial

**AWS & Cloud Computing Basics**

- **What is AWS?**
  - Amazon Web Services (AWS) is a cloud platform providing a wide range of IT resources (compute, storage, database, security, and more) over the internet.
  - AWS is highly used in the industry and is essential knowledge for DevOps engineers.
  - Through AWS, you can create resources as needed (scalable, pay-as-you-go).

- **Why AWS for DevOps?**
  - Seamless infrastructure automation, scalable deployments, fast provisioning.
  - Enables engineers to deploy, test, and manage applications globally and reliably.

***

**Step 1: AWS Account Setup**

- Go to the AWS website and initiate account creation.
- Enter email, set a strong password, and choose an account name.
- Enter personal details (Name, Address, etc.).
- Provide payment details (debit/credit card). No charges if you use only free tier services.
- Select a support plan (Free Basic Support is recommended for students/learners).
- Complete account verification.

***

**Step 2: Exploring the AWS Console**

- **Login to AWS Console** using your new credentials.
- AWS Console Dashboard shows all available AWS services.
  - *Key services for DevOps:* EC2 (servers), S3 (storage), RDS (databases), IAM (users/roles).
- Each service is accessed from a central dashboard, making it easy to launch, monitor, and manage your resources.[1][2]

***

**Step 3: Launch Your First EC2 Instance**

- **Navigate to EC2 service** (Elastic Compute Cloud) from AWS Console.
- Click on “Launch Instance.”
- **Choose an OS image:** Select Ubuntu Server for Linux setups (recommended for DevOps).
- **Select Instance Type:** For beginners, t2.micro (1 vCPU, 1 GB RAM) is free tier eligible.
- **Configure Storage:** Default (8 GB) is enough; modify if needed.
- **Configure Security Group:** Set rules for SSH (port 22) and other ports (if web server, open port 80/443).
- **Review and Launch:**
  - Download the SSH key pair provided—required for connecting to your instance.
  - Confirm all settings and launch the instance.[3][4][5]

***

**Step 4: Connect to EC2 Instance**

- Once the instance is running:
  - Copy the **public IP address** from AWS Console.
  - Use an SSH client to connect:
    ```bash
    ssh -i /path/to/your-key.pem ubuntu@<public-ip>
    ```
  - On successful SSH, you have full access to your virtual Linux machine for installations, deployment, and management.

***

**Key Points and Best Practices**

- Always keep your AWS credentials and SSH key safe.
- Use the “free tier” options unless explicitly needed to avoid charges.
- Terminate unused instances to avoid unnecessary costs.
- For practice, try deploying small sample apps or running basic Linux commands.

***

**Summary Table**

| Step        | Description                                                  |
|-------------|-------------------------------------------------------------|
| 1. Sign Up  | Create AWS account and verify                                |
| 2. Console  | Explore dashboard, understand key services                   |
| 3. EC2      | Launch instance (Ubuntu, t2.micro, default settings)         |
| 4. Security | Configure Security Group (SSH, HTTP/HTTPS if web server)     |
| 5. Connect  | SSH into instance using provided key                         |
| 6. Practice | Deploy/test applications, terminate when done                |

