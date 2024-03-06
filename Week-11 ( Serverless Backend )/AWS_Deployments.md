# AWS Deployments

Absolutely! Let's break down AWS and its server rental capabilities.

**AWS: The Cloud Computing Giant**

* **Amazon Web Services (AWS):** It's a comprehensive cloud computing platform that provides a massive range of on-demand services to businesses, organizations, and individuals worldwide.
* **Why AWS?** 
    * **Flexibility:** Choose the operating systems, programming languages, databases, and tools you need.
    * **Scalability:** Quickly increase or decrease resources to match your workload demands.
    * **Cost-Effectiveness:** Pay only for what you use, no upfront investments for hardware.
    * **Reliability:** AWS has a global infrastructure designed for high availability and fault tolerance.

**Focus: Renting Servers (EC2)**

* **The Core: EC2 (Elastic Compute Cloud):**  This is the cornerstone of AWS server rental. With EC2, you can provision virtual machines (called "instances") in minutes.
* **Customization:**  
    * **Instance Types:** Choose from a wide variety of instance families optimized for compute, memory, storage, graphics, and other specialized workloads.
    * **Operating Systems:** Linux, Windows Server, and more.
    * **Storage:** Select the storage type (flexible SSD, high-performance HDD, etc.) and how much you need.
    * **Geographic Regions:** Launch instances closer to your target audience for lower latency.

**How Does Using EC2 Benefit You?**
1. **No Hardware Worries:** Eliminate the costs and maintenance of buying and running physical servers.
2. **Rapid Deployment:** Launch new web servers, application servers, etc. in minutes instead of waiting for on-premise hardware provisioning.
3. **Global Reach:** Easily spin up instances in different parts of the world to serve your customers better.
4. **Pay-As-You-Go:** No large upfront costs; you pay only for the time your instances are running.

Great explanation! Let's refine a few points about EC2 servers:

**Naming and Terminology**

* **EC2 Instances:** You're absolutely right that virtual machines on AWS are called EC2 instances, not strictly "EC2 servers".
* **Elastic Compute Cloud (EC2):** The term refers to the overall AWS service that provides these virtual machines.

**Elasticity: The Key Feature**

* **Beyond resizing:**  Elasticity in EC2 goes further than increasing/decreasing the size (CPU cores, memory) of an instance. You can:
    * **Change instance types:** Switch to a completely different instance family optimized for specific needs. 
    * **Auto Scaling:** Automatically add or remove EC2 instances based on demand, ensuring optimal performance and cost.

**Launching EC2 Instances**

* **More Than the Dashboard:** While the AWS Management Console provides a visual way to launch instances, you have other options for greater control and automation:
    * **AWS CLI (Command Line Interface):**  Perform actions through commands for power users.
    * **AWS SDKs:** Integrate EC2 management into your applications with various programming languages.
    * **Infrastructure as Code (IaC) tools:** Tools like Terraform and CloudFormation let you define your infrastructure in code for consistency and versioning.

That's a great outline of the EC2 instance creation process! Let's break it down and add some important details:

**Step 3 - Creating a new EC2 server**

1. **Click on Launch a new instance:**
   * You'll find this option in the Amazon EC2 section of your AWS Management Console.

2. **Give a name:**
   * This is for easy identification within your AWS account. Choose something meaningful (e.g., "webserver-production").

3. **Select an OS (AMI):**
   * **AMI (Amazon Machine Image):** This is the software bundle your instance starts with. Popular choices include:
      * Amazon Linux 2
      * Ubuntu Server
      * Windows Server
   * **Marketplace AMIs:** Find pre-configured AMIs with specific software for different scenarios.

4. **Select size (Instance type):**
   * **Instance families:** Groups like 't2' (general purpose), 'm5' (balanced), 'c5' (compute-optimized)...
   * **Specific types:**  Like 't2.micro' (small size) – research which are eligible for the AWS Free Tier if you are experimenting. 

5. **Create a new Key pair:**
   * **Essential for SSH access:** Securely connect to Linux instances (RDP for Windows). 
   * **Important:** Download and store this key pair safely; you can't retrieve it later.

6. **Select Size (Storage):**
   * **Volume type:** EBS provides choices like General Purpose SSD (gp2), Provisioned IOPS SSD (io1), Magnetic (standard) – consider performance needs. 
   * **Size:** How many gigabytes (GB) of storage you require.

7. **Allow traffic on http/https (Configure Security Group):**
   * **Firewall rules:** Control inbound traffic.
   * **Add rules:**  HTTP (port 80), HTTPS (port 443) for web servers.
   * **Source:** Limit to specific IP ranges for security, or 0.0.0.0/0 for public access (be cautious).

**Additional Considerations:**

* **Network settings (VPC, Subnet):** If you have advanced network setups, you'll need to choose the appropriate options during launch.
* **IAM Roles:** Grant EC2 instances permissions to access other AWS services.
* **Tags:** Add key-value labels to organize your resources.

**Ready to Launch**


You're on the right track for connecting to your new EC2 instance and setting up a project! Let's refine these steps and add some crucial security considerations:

**Step 4 - SSH into server**

1. **Give ssh key permissions (chmod 400 is recommended):**

   ```bash
   chmod 400 kirat-class.pem
   ```

   * This makes the key **readable only by you**, enhancing security.

2. **ssh into machine:**

   ```bash
   ssh -i kirat-class.pem ubuntu@ec2-65-0-180-32.ap-south-1.compute.amazonaws.com
   ```

   * **Important:** The default username for Amazon Linux 2 AMIs is 'ec2-user'. Adapt if using a different OS image.

3. **Clone repo:**

   ```bash
   git clone https://github.com/hkirat/sum-server 
   ```

**💡 Troubleshooting Network Errors:**

*  **Security Groups:** Double-check that your instance's security group allows inbound SSH traffic (port 22), ideally from a restricted source IP range.
*  **Internet Gateway:**  If your EC2 instance is in a private subnet, ensure it has a route to an internet gateway within your VPC.

**4. Install Node.js**

* **Best Practices:** Instead of manually downloading, use a version manager like 'nvm' for cleaner Node.js management on Linux: [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)
*  **Example (nvm installation + Node.js):**
      ```bash
      curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash 
      source ~/.bashrc  # or source your shell config file
      nvm install --lts  # Install a Long-Term Support version
      ```

**5. Install all dependencies**

   ```bash
   cd sum-server
   npm install
   ```

**6. Start Backend**

   ```bash
   node index.js 
   ```

**Additional Considerations**

*  **Background execution:** Use tools like 'screen', 'tmux,' or 'pm2' to keep the process running even after you disconnect your SSH session.
*  **Deployment:** Explore automating code deployment (e.g., AWS CodeDeploy) for streamlining updates.

You're absolutely right! Here's what's happening and how we can troubleshoot:

**Why can't you reach the website on your_domain:3000?**

1. **Node.js Process:**  By default, Node.js applications typically listen on a port like 3000.  This is fine internally within the EC2 instance.

2. **Security Groups:** AWS EC2 instances act like firewalls. You need to explicitly open port 3000 in the Security Group attached to your instance to allow traffic from the outside world.

**Solutions:**

**Option 1: Open Port 3000 in Security Group**

* This is the quickest solution for testing purposes.
* **Find your Security Group:** Navigate to the EC2 section in your AWS Console and locate the Security Group used by your instance.
* **Edit Rules:** Add an inbound rule allowing traffic on port 3000. You can limit the source IP if you wish.

**Option 2: Run the process on Port 80**

* Port 80 is the standard HTTP port; browsers will connect to this by default.
* **Caveats:** 
    * Typically, running processes directly on port 80 requires root/administrative privileges, which might not be ideal for security reasons.
    * You might need to configure your Node.js application to listen on port 80 instead of 3000.

**Option 3 (More Advanced): Reverse Proxy**

* Install a web server like Nginx or Apache on your instance.
* Configure them to listen on port 80 and forward requests to your Node.js process on port 3000.
* This offers more features (e.g., load balancing, SSL termination) for production-level setups.

**Security Considerations:**

* If you open port 3000 directly, carefully consider who you allow access to it (via the "Source" setting in the Security Group rule).
* Option 3 is generally preferred for production environments.

Sure, here is the summary of the article:

* NGINX is open source software that can be used for web serving, reverse proxying, caching, load balancing, and more.
* It is known for being fast and efficient.
* NGINX can also be used as a reverse proxy and load balancer.
* Companies like Netflix and Dropbox use NGINX.

Certbot, as mentioned on [its website](https://certbot.eff.org/), is a free, open-source tool that automates the process of obtaining and installing HTTPS certificates for your website. It simplifies the often complex task of securing your web server with TLS/SSL encryption, making it easier to protect user data and privacy.

\

