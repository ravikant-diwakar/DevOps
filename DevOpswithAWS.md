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
- Each service is accessed from a central dashboard, making it easy to launch, monitor, and manage your resources.

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
  - Confirm all settings and launch the instance.

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
















Got it ✅ Ravikant! I’ll **keep your previous AWS EC2 tutorial notes as-is** and now add the **Key Pair creation section** into them.
Here’s your **full updated notes**:

---

# 🌐 AWS Account Setup with EC2 – Beginner Tutorial

## ☁️ Cloud Computing Basics

### What is AWS?

Amazon Web Services (AWS) is a **cloud platform** offering IT resources like compute power, storage, networking, databases, and security **on demand via the internet**.

✅ Key features:

* **Pay-as-you-go** model (no upfront cost)
* **Highly scalable** (grow/shrink resources as needed)
* **Global availability** (data centers worldwide)

### Why AWS for DevOps?

* Automates infrastructure with **Infrastructure as Code (IaC)**
* Enables **fast, scalable deployments**
* Provides **reliable global services**
* Helps engineers test, build, and manage applications efficiently

---

## 🔑 Step 1: Create Your AWS Account

1. Go to 👉 [AWS Signup Page](https://aws.amazon.com/)
2. Enter **email, password, and account name**.
3. Provide **contact information** (name, address, phone).
4. Add **payment details** (debit/credit card). *(No charges for Free Tier usage)*
5. Choose **Basic Support (Free)**.
6. Verify account through OTP/email.

---

## 🖥️ Step 2: Explore the AWS Console

* Login via 👉 [AWS Console](https://console.aws.amazon.com/)
* **AWS Management Console** = Control panel for all AWS services.
* **Key services for DevOps**:

  * **EC2** → Virtual servers (compute)
  * **S3** → Storage
  * **RDS** → Databases
  * **IAM** → Identity & Access Management

---

## 🔑 Step 3: Create Key Pair (For EC2 Connection)

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

---

## 🚀 Step 4: Launch Your First EC2 Instance

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

---

## 🔗 Step 5: Connect to EC2 Instance

1. Find **Public IP** of your instance in AWS Console.
2. Connect via SSH:

```bash
ssh -i ~/path/to/my-ec2-key.pem ubuntu@<public-ip>
```

3. You now have a **Linux server running in AWS**!

---

## 📌 Best Practices

* Keep your **AWS credentials & SSH key** secure.
* Stick to **Free Tier** (`t2.micro`, limited storage, etc.).
* **Terminate instances** when not in use to avoid charges.
* Practice with:

  * Deploying a sample web app
  * Running Linux commands
  * Setting up Apache/Nginx server

---

## 📊 Summary Table

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

⚡ Now you have **complete notes with Key Pair details included**.

Do you want me to also add a **mini hands-on exercise** (like setting up Apache on EC2 and hosting a "Hello World" webpage) to these notes? That would give you practical practice right after connecting.
