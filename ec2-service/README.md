# AWS EC2 Service

**EC2 (Elastic Compute Cloud)** is an AWS service that provides virtual servers (called instances) for hosting applications. It is region-based and ideal for deploying scalable applications, learning Linux, hosting websites, and more.

---

## 🚀 Launching an EC2 Instance

### Step 1: Click on "Launch Instance" button

![Launch Instance](./screenshots/launch-instance.png)

### Step 2: Provide a name for the instance

![Name Instance](./screenshots/name-instance.png)

### Step 3: Choose an AMI (Amazon Machine Image)

> AMI: Amazon Machine Image is a pre-configured template for your instance.

Select **Amazon Linux AMI**, which is Free Tier eligible.

![AMI Selection](./screenshots/ami-selection.png)

### Step 4: Select Instance

> Instance = Virtual server

Choose the default free-tier eligible t2.micro instance.

![Select Instance](./screenshots/instance-type.png)

### Step 5: Create New Key Pair

Click **Create new key pair**, add a name, and download the `.pem` file.

![Create New Key Pair](./screenshots/create-new-key-pair.png)

![Create key pair](./screenshots/create-key-pair.png)

### Step 6: Allow HTTP Traffic from the Internet

To make your instance accessible via a browser, enable HTTP in the firewall settings.

![Allow HTTP traffic](./screenshots/network-settings.png)

### Step 7: Add User Data Script (Optional)

To auto-install Apache and serve a simple HTML page, go to **Advanced Details → User data**, and paste:

```
sudo yum update -y
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd

echo "<html><h1>Hello World</h1></html>" > /var/www/html/index.html
```

![User data](./screenshots/user-data.png)

### Step 8: Click on "Launch Instance"

![Launch Instance btn](./screenshots/summary-launch-instance.png)

### Step 9: View Running Instance

![Instance Running](./screenshots/instance-running.png)

![Instance Id](./screenshots/instance-id.png)

Open the public IP in your browser.
If https:// doesn't work, try http://

![Instance Output](./screenshots/instance-output.png)

## 🔐 Configure Security Group

### Step 1: Go to Instance → Security Tab → Click on Security Group Link

![Security Group](./screenshots/security-groups.png)

### Step 2: Click "Edit Inbound Rules"

![Inbound Rule](./screenshots/inbound-rules.png)

### Step 3: Delete HTTP Rule (Optional – To See What Happens)

![HTTP delete](./screenshots/delete-http.png)

Now, accessing the public IP will show an error:

![Error](./screenshots/error.png)

### Step 4: Re-Add HTTP Rule

Click "Add Rule" → Select Type: HTTP → Save

![Add Rule](./screenshots/add-rule.png)

![New Rule](./screenshots/new-rule.png)

Your site should now be accessible again:

![Instance Output](./screenshots/instance-output.png)

## 🧑‍💻 Connect to EC2 Remotely

## ✅ Option 1: EC2 Instance Connect (Browser-Based)

### Step 1: Go to EC2 → Select Instance → Click "Connect"

![EC2 ssh](./screenshots/connect-ssh.png)

A browser-based Linux shell will open:

![SSH](./screenshots/ssh.png)

### Step 2: Modify HTML Page

```
$ cd /var/www/html
$ ls
$ sudo nano index.html
```

![Nano](./screenshots/nano.png)

Press Ctrl + O → Enter (Save)

Press Ctrl + X (Exit)

![Nano Edit](./screenshots/nano-edit.png)

Press `Ctrl` + `O`, click `Enter` to save the file, and `Ctrl` + `X` to exit the nano file editor

Changes are now visible:

![Instance Edited Output](./screenshots/instance-edited-output.png)

## ✅ Option 2: SSH Client (Windows - PuTTY)

### Step 1: Download [Putty](https://apps.microsoft.com/detail/xpfnzksklbp7rj?hl=en-US&gl=US)

### Step 2: Open PuTTYgen from Start Menu

![PuttyGen](./screenshots/putty-gen.png)

### Step 3: Load the .pem File You Downloaded Earlier

![Putty Load](./screenshots/putty-load.png)

Set file picker to All Files:

![All Files](./screenshots/file-picker-select-all.png)

Select the PEM file:

![PEM file](./screenshots/pem-file.png)

### Step 4: Save the Private Key (.ppk)

![Save Private Key](./screenshots/save-private-key.png)

![Putty file](./screenshots/putty-file.png)

### Step 5: Open PuTTY → SSH → Auth → Browse .ppk File

![Browse .ppk](./screenshots/putty-ssh-credentials.png)

### Step 6: Paste the EC2 Public IPv4 Address

![Copy IPv4 address](./screenshots/copy-ipv4-address.png)

![Paste IPv4 address](./screenshots/paste-ipv4-address.png)

### Step 7: Save and Open the Session

![Save session](./screenshots/save-session.png)
![Open session](./screenshots/open-session.png)

### Step 8: Login as ec2-user

![ec2-user](./screenshots/ec2-user.png)

## 🗑️ Terminate EC2 Instance

> 💡 If you're using EC2 only for testing, terminate the instance to avoid charges.

![EC2 Terminate](./screenshots/terminate-instance-1.png)

![terminate](./screenshots/terminate-instance-2.png)

---

## ✅ Summary

- Launch and configure an EC2 instance
- Allow public access via HTTP
- Connect using EC2 Instance Connect or PuTTY
- Automate setup with User Data
- Safely terminate the instance

---

> 🧠 This README serves as proof-of-practice and demonstrates hands-on understanding of AWS EC2.
