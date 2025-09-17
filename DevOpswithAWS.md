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

---

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

---

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

---

**Step 5: Connect to EC2 Instance**

1. Find **Public IP** of your instance in AWS Console.
2. Connect via SSH:

```bash
ssh -i ~/path/to/my-ec2-key.pem ubuntu@<public-ip>
```

3. You now have a **Linux server running in AWS**!

---

**Best Practices**

* Keep your **AWS credentials & SSH key** secure.
* Stick to **Free Tier** (`t2.micro`, limited storage, etc.).
* **Terminate instances** when not in use to avoid charges.
* Practice with:

  * Deploying a sample web app
  * Running Linux commands
  * Setting up Apache/Nginx server

---

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
