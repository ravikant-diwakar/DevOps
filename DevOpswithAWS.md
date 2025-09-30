# Table of Contents

1. [AWS account setup with EC2 Tutorial](#1-aws-account-setup-with-ec2-tutorial)
2. [AWS EC2 (Elastic Compute Cloud)](#2-aws-ec2-elastic-compute-cloud)
3. [Step-by-Step Guide to Launch EC2 in a Custom VPC](#3-step-by-step-guide-to-launch-ec2-in-a-custom-vpc)

---

# 1. AWS account setup with EC2 Tutorial

**AWS & Cloud Computing Basics**

- **What is AWS?**
  - Amazon Web Services (AWS) is a cloud platform providing a wide range of IT resources (compute, storage, database, security, and more) over the internet.
  - AWS is highly used in the industry and is essential knowledge for DevOps engineers.
  - Through AWS, you can create resources as needed (scalable, pay-as-you-go).

- **Why AWS for DevOps?**
  - Seamless infrastructure automation, scalable deployments, fast provisioning.
  - Enables engineers to deploy, test, and manage applications globally and reliably.

**Step 1: AWS Account Setup**

- Go to the AWS website and initiate account creation.
- Enter email, set a strong password, and choose an account name.
- Enter personal details (Name, Address, etc.).
- Provide payment details (debit/credit card). No charges if you use only free tier services.
- Select a support plan (Free Basic Support is recommended for students/learners).
- Complete account verification.

**Step 2: Exploring the AWS Console**

- **Login to AWS Console** using your new credentials.
- AWS Console Dashboard shows all available AWS services.
  - *Key services for DevOps:* EC2 (servers), S3 (storage), RDS (databases), IAM (users/roles).
- Each service is accessed from a central dashboard, making it easy to launch, monitor, and manage your resources.

**Step 3: Create Key Pair (For EC2 Connection)**

1. Navigate to **EC2 → Key Pairs → Create Key Pair**.

2. Enter **Key Pair Name** (e.g., `my-ec2-key`).

   * Up to 255 characters, no spaces at start/end.

3. **Choose Key Pair Type**:

   * **RSA** → Widely supported, recommended for beginners.
   * **ED25519** → Faster, smaller, but limited support.

4. **Choose Private Key File Format**:

   * **.pem** → For Linux/macOS/WSL/Windows PowerShell (with OpenSSH).
   * **.ppk** → For PuTTY on Windows.
   * ✅ Most recommended: `.pem` (works with OpenSSH everywhere).

5. **Download the key file** (`.pem` or `.ppk`).

   * Can only be downloaded once—**store it securely**.

6. **Secure the key file (Linux/macOS/WSL users)**:

   ```bash
   chmod 400 my-ec2-key.pem
   ```

7. Use this key to connect later:

   ```bash
   ssh -i ~/path/to/my-ec2-key.pem ubuntu@<your-public-ip>
   ```

**Step 4: Launch Your First EC2 Instance**

1. Go to **EC2 service** in the console.
2. Click **Launch Instance**.
3. Configure settings:

   * **OS Image (AMI)** → Ubuntu Server (recommended).
   * **Instance Type** → `t2.micro` (Free Tier eligible).
   * **Storage** → Default 8 GB (increase if required).
   * **Security Group** → Allow:

     * SSH → Port 22
     * HTTP → Port 80
     * HTTPS → Port 443
4. **Key Pair** → Select the one you just created.
5. Click **Launch Instance**.

**Step 5: Connect to EC2 Instance**

1. Find **Public IP** of your instance in AWS Console.
2. Connect via SSH:

```bash
ssh -i ~/path/to/my-ec2-key.pem ubuntu@<public-ip>
```

3. You now have a **Linux server running in AWS**!

**Best Practices**

* Keep your **AWS credentials & SSH key** secure.
* Stick to **Free Tier** (`t2.micro`, limited storage, etc.).
* **Terminate instances** when not in use to avoid charges.
* Practice with:

  * Deploying a sample web app
  * Running Linux commands
  * Setting up Apache/Nginx server

**Summary Table**

| Step        | Description                                                 |
| ----------- | ----------------------------------------------------------- |
| 1. Sign Up  | Create AWS account, verify details                          |
| 2. Console  | Explore AWS Dashboard (EC2, S3, RDS, IAM)                   |
| 3. Key Pair | Create & download `.pem` or `.ppk` key for SSH              |
| 4. EC2      | Launch instance (Ubuntu, t2.micro)                          |
| 5. Security | Configure Security Group (SSH, HTTP/HTTPS)                  |
| 6. Connect  | SSH into instance using key pair                            |
| 7. Practice | Deploy apps, run Linux commands, terminate unused instances |

---


# 2. AWS EC2 (Elastic Compute Cloud) 
- **Type:** Infrastructure as a Service (IaaS)
- **What it is:** Traditional virtual machine (VM) on AWS cloud.
- **Features:**
  - rent a server (VM) and have full control over OS, networking, security, and deployment.
  - Manual setup for networking, security groups, inbound/outbound rules.
  - manage everything (server updates, scaling, security patches, etc.).
- **Pros:** 
  - Full flexibility.
  - Suitable for custom server environments and legacy apps.
- **Cons:**
  - High operational cost (maintenance, monitoring, scaling).
  - Higher management overhead.
  - Less abstraction compared to newer AWS offerings.

***

**2. AWS ECS (Elastic Container Service)**  
- **Type:** Container Orchestration Service (CaaS)
- **What it is:** AWS-managed container orchestration (uses Docker).
- **Features:**
  - Simplifies running containers (no need to manage server infrastructure directly).
  - Ideal for microservices and containerized applications.
  - Still need to provision EC2 instances for running containers (unless using Fargate).
  - Handles scaling, updates, and orchestration of containers.
- **Pros:**
  - Reduces infrastructure worries.
  - Automates container management.
- **Cons:**
  - Still need to manage and scale underlying EC2 instances (if not using Fargate).
  - Some operational tasks remain for servers.

***

**3. AWS Fargate**  
- **Type:** Serverless for Containers / Container as a Service (CaaS)
- **What it is:** Run containers directly without managing servers or EC2 instances.
- **Features:**
  - AWS manages all infrastructure, scaling, patching.
  - You specify container images, CPU, memory requirements.
  - Pay only for resources used (no server payments).
  - Removes need to think about underlying VMs.
- **Pros:**
  - No need to manage servers (truly serverless for containers).
  - Great abstraction, ideal for containerized workloads.
  - Easy to scale and maintain.
- **Cons:**
  - Potentially higher cost if continuously running large workloads.
  - Limited to containerized applications.
  - You still need to configure containers (resource allocation).

***

**4. AWS Lambda**  
- **Type:** Function as a Service (FaaS) / Serverless
- **What it is:** Run code in response to events without managing servers or containers.
- **Features:**
  - Code runs only when triggered by events (HTTP, S3, etc.).
  - Maximum execution time per invocation: 15 minutes.
  - Pay as you use: only for function execution time.
  - No server or infrastructure management.
- **Pros:**
  - Event-driven, cost-effective for sporadic workloads.
  - Ultra-low management (just write code and deploy).
  - Ideal for automation, cron jobs, API endpoints.
- **Cons:**
  - Not suitable for long-running processes.
  - Resource and execution time limits.
  - Not for heavy/constant workloads.

***

**SUMMARY COMPARISON**

| Feature           | EC2             | ECS                  | Fargate                | Lambda                  |
|------------------|-----------------|----------------------|------------------------|-------------------------|
| Server Management| Full (manual)   | Partial (less manual)| None (fully managed)   | None (fully managed)    |
| Scaling          | Manual/Auto     | Managed for containers | Automatic             | Automatic               |
| Abstraction      | Low             | Medium               | High                   | Very High (just code)   |
| Costing Model    | Per server-hour | Based on EC2+usage   | Pay-per container usage| Pay per invocation      |
| Suitability      | Custom workloads| Microservices, apps  | Containers of any scale| Event/trigger based     |
| Maintenance      | You do all      | You do some          | None                   | None                    |

- **Move from EC2 to Lambda** = Less management, more abstraction, automatic scaling, and "pay as you use" model.
- Choosing the right tool depends on your use-case:  
  - Full control/customization → EC2  
  - Containerized/microservices → ECS/Fargate  
  - Fully event-based, no infra → Lambda

***

# 3. Step-by-Step Guide to Launch EC2 in a Custom VPC

## *PART 1: VPC NETWORK SETUP*

### *Step 1: Create a VPC*

1. Go to *VPC Dashboard* → *Your VPCs* → Click *Create VPC*
2. Select *VPC only*
3. *Name*: MyVPC
4. *IPv4 CIDR block*: 10.0.0.0/16
5. Leave everything else default → Click *Create VPC*

### *Step 2: Create a Subnet*

1. Go to *Subnets* → Click *Create Subnet*
2. *Name*: MyPublicSubnet
3. *VPC*: Select MyVPC
4. *Availability Zone*: e.g., us-east-1a
5. *IPv4 CIDR block*: 10.0.0.0/24
6. Click *Create Subnet*

### *Step 3: Create and Attach Internet Gateway (IGW)*

1. Go to *Internet Gateways* → Click *Create internet gateway*
2. *Name*: MyIGW → Click *Create*
3. Click on the IGW → *Actions* → *Attach to VPC*

* Choose MyVPC → Attach

### *Step 4: Create a Route Table*

1. Go to *Route Tables* → Click *Create route table*
2. *Name*: MyPublicRouteTable
3. *VPC*: Select MyVPC
4. Click *Create*

### *Step 5: Add Route to Internet Gateway*

1. Click your new route table → *Routes* tab → *Edit routes*
2. *Add Route*:

* *Destination*: 0.0.0.0/0
* *Target*: Select your IGW (MyIGW)
3. Click *Save changes*

### *Step 6: Associate Route Table with Subnet*

1. Go to your Route Table → *Subnet Associations* tab → Click *Edit subnet associations*
2. Select MyPublicSubnet → Click *Save associations*

## *PART 2: LAUNCH EC2 INSTANCE*

### *Step 7: Create a Key Pair (for SSH access)*

1. Go to *EC2 Dashboard* → *Key Pairs* → Click *Create key pair*
2. *Name*: MyKeyPair
3. *File format*: .pem (for Linux/Mac) or .ppk (for PuTTY/Windows)
4. Click *Create key pair*
5. Save the .pem file safely — you'll need it to connect

### *Step 8: Create Security Group*

1. Go to *EC2 Dashboard* → *Security Groups* → Click *Create security group*
2. *Name*: MySG
3. *VPC*: Select MyVPC
4. In *Inbound rules*:

* Click *Add Rule*:

* *Type*: SSH
* *Port*: 22
* *Source*: My IP (or 0.0.0.0/0 for open access — less secure)
5. Click *Create security group*

### *Step 9: Launch EC2 Instance*

1. Go to *EC2 Dashboard* → Click *Launch instance*
2. *Name*: MyEC2Instance
3. *AMI*: Amazon Linux 2023 (or Ubuntu 22.04, etc.)
4. *Instance type*: t2.micro (Free tier eligible)
5. *Key pair*: Select MyKeyPair
6. *Network settings*:

* *VPC*: MyVPC
* *Subnet*: MyPublicSubnet
* *Auto-assign public IP*: Enabled
* *Firewall*: Select existing Security Group → Choose MySG
7. Leave storage default → Click *Launch Instance*

Your EC2 instance will now start. Wait until the status is *"Running"* and the *Status Checks = 2/2*.

## *PART 3: CONNECT TO EC2 INSTANCE*

### *Step 11: Connect via SSH (Linux/macOS)*

1. Open Terminal
2. Navigate to the folder with your .pem file
3. Run the following commands:

bash
chmod 400 MyKeyPair.pem

ssh -i "MyKeyPair.pem" ec2-user@<public-ip>


📌 Replace <public-ip> with your instance's actual public IP
📌 Use ubuntu@ instead of ec2-user@ if you used Ubuntu AMI

### You're in!

You've successfully launched an EC2 instance in your custom VPC and connected to it.

## Test EC2 Connection Using PuTTY

### PRE-STEP: Convert `.pem` to `.ppk` (if you haven't already)

PuTTY doesn’t accept `.pem` files directly. You must convert your key to `.ppk` format using **PuTTYgen**.

1. Open **PuTTYgen** (search in Start menu).
2. Click **Load**, change file type to *All Files*, then select your `MyKeyPair.pem`.
3. Click **Save private key** → Save as `MyKeyPair.ppk`.

### 1. Open **PuTTY**

Start PuTTY from the Start Menu.

### 2. In the **Host Name (or IP address)** field:

Enter your EC2 instance’s **public IPv4 address**.

Example:

```text
ec2-user@54.123.45.67
```

Or just:

```text
54.123.45.67
```

(Find your IP in EC2 Dashboard → Instances → Your Instance → “Public IPv4 address”)

### 3. In the **Category** tree on the left:

Navigate to:

```
Connection → SSH → Auth → Credentials
```

* Click **Browse**
* Select your `.ppk` file (`MyKeyPair.ppk`)

---

### 4. (Optional) Save session:

Back in **Session** (top of tree), type a **name** under “Saved Sessions” and click **Save** — so you don’t have to re-enter every time.

---

### 5. Click **Open**

If everything is configured correctly, you’ll see:

**Login prompt**

Example:

```bash
login as:
```

### 6. Enter the username:

Use:

* `ec2-user` for Amazon Linux
* `ubuntu` for Ubuntu
* `admin` for some other AMIs

So type:

```bash
ec2-user
```

and press **Enter**

## Success Looks Like This:

If connection is successful, you'll see:

```
[ec2-user@ip-10-0-1-xx ~]$
```

You’re now inside your EC2 instance terminal! 
