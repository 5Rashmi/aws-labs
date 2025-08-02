# 🔐 AWS IAM User Lab

## 📘 Summary

This lab demonstrates how to create a custom IAM user in AWS with specific permissions and set up MFA (Multi-Factor Authentication).  
IAM (Identity and Access Management) enables secure access control by allowing you to create users, assign permissions, group users, and enforce MFA.

---

## 🛠️ Steps Performed to Create a User

### 1. Navigate to the IAM Users section

![Go to User](./screenshots/go-to-users.png)

### 2. Click on the **“Create User”** button

![Create User button](./screenshots/create-user-btn.png)

### 3. Specify User Details

![User Name](./screenshots/user-name.png)

- Entered a username
- Enabled **“Provide user access to the AWS Management Console”**
- Selected **“I want to create an IAM user”**

### 4. Click **Next**

![Next](./screenshots/next-1.png)

---

## 🔑 Set Permissions

### 5. Choose a Permission Setting

- Selected **“Add user to group”** (easier for managing multiple users)
- Clicked **“Create group”**

![Create Group Button](./screenshots/set-permissions.png)

### 6. Create User Group

![Create Policy Button](./screenshots/create-policy.png)  
You can choose from existing policies or create a custom one using the **“Create policy”** button.

---

## 🧾 Create Custom Policy

### 7. Define Permissions via JSON

![Specify Permissions](./screenshots/specify-permissions.png)

- Used the JSON editor to allow **all EC2 actions**
- Clicked **Next**

### 8. Review and Create

![Review and Create](./screenshots/review-n-create.png)

- Entered a policy name and description
- Clicked **Create policy**

---

### 9. Finish Creating the User Group

![Create User Group](./screenshots/create-user-group.png)

- Selected the custom policy
- Added it to the new group

### 10. Finalize User Creation

![Create User Next](./screenshots/create-user-next.png)

- Clicked **Next**, reviewed the configuration, and clicked **Create user**

### ✅ 11. User Created Successfully

![User created Successfully](./screenshots/user-created-successfully.png)

---

## 🔗 Accessing IAM User Console

### 12. Open the User

![Go to User](./screenshots/go-to-user.png)

### 13. Click the Username

![Click on username](./screenshots/click-on-username.png)

### 14. Go to the **Security Credentials** Tab

![Go Security Credentials](./screenshots/go-to-security-credentials.png)

### 15. Copy the Console Sign-In Link

![console signin link](./screenshots/copy-sign-in-link.png)

- Opened the link in a new tab
- Logged in using the username (e.g., **Elon**) and password

---

## 🔐 Enable MFA for the User

### 1. Go to IAM → Users

![Go to Users](./screenshots/mfa-go-to-users.png)

### 2. Open the **Security Credentials** Tab

![Go to Security Credentials](./screenshots/mfa-security-credentials.png)

### 3. Click **Assign MFA**

![Assign MFA button](./screenshots/assign-mfa.png)

### 4. Choose MFA Device Type

![MFA Device Name](./screenshots/mfa-device-name.png)  
![MFA Device](./screenshots/mfa-device.png)

- Entered a device name (can be anything)
- Selected **“Authenticator app”**
- Clicked **Next**

### 5. Complete MFA Setup

- Scanned the QR code using **Google Authenticator**
- Entered **two consecutive MFA codes**
- Clicked **Assign MFA**

---

## ✅ Summary

- Created a new IAM user with group-based permissions
- Designed a custom IAM policy for full EC2 access
- Enabled AWS Console sign-in
- Configured MFA using Google Authenticator

---

> 🧠 This README serves as proof-of-practice and demonstrates hands-on understanding of AWS IAM fundamentals.
