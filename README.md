# Osinachi Project Landing Page  

**Website**: osinachiproject.online  
**IP Address**: [http://13.61.25.145/](http://13.61.25.145/)  

---

## **Project Overview**  

The **Osinachi Project Landing Page** is a demonstration of deploying a static web page on an Nginx web server hosted on an AWS EC2 instance. This project highlights the following key skills and configurations:  
- Setting up a Linux server environment.  
- Installing and configuring the Nginx web server.  
- Deploying a custom HTML page.  
- Securing the web server with SSL certificates using Certbot for HTTPS access.  

The deployed landing page introduces the project creator and provides relevant project details.  

---

## **Setup Instructions**  

Follow the steps below to replicate the setup of the **Osinachi Project Landing Page**.  

### **1. Provision an AWS EC2 Instance**  
- Log in to your AWS account and launch an EC2 instance.  
- Choose an Ubuntu 20.04 AMI for the server.  
- Select an appropriate instance type (e.g., `t3.micro`).  
- Configure the security group to allow the following traffic:  
  - HTTP (Port 80) for web traffic.  
  - HTTPS (Port 443) for secure web traffic.  
  - SSH (Port 22) for remote server access.  

### **2. Install the Nginx Web Server**  
Run the following commands on the server to install and start Nginx:  
```bash
sudo apt update
sudo apt install nginx -y
```  

### **3. Deploy the HTML Landing Page**  
1. Navigate to the default web root directory of Nginx:  
   ```bash
   cd /var/www/html
   ```  
2. Backup the default Nginx welcome page:  
   ```bash
   sudo mv index.nginx-debian.html index.html.bak
   ```  
3. Upload the custom `index.html` file to the directory.  
4. Restart Nginx to apply the changes:  
   ```bash
   sudo systemctl restart nginx
   ```  

### **4. Configure SSL with Certbot**  
1. Install Certbot and the Nginx plugin:  
   ```bash
   sudo apt install certbot python3-certbot-nginx -y
   ```  
2. Obtain and configure an SSL certificate for your domain:  
   ```bash
   sudo certbot --nginx -d osinachiproject.online
   ```  
3. Follow the prompts to:  
   - Enter your email address.  
   - Agree to the Terms of Service.  
   - Decline (optional) sharing your email address with the EFF.  

Certbot will automatically update Nginx configurations to redirect HTTP traffic to HTTPS.  

### **5. Verify Setup**  
- Open a browser and navigate to [https://osinachiproject.online](https://osinachiproject.online) to confirm the secure connection.  
- Test SSL auto-renewal:  
   ```bash
   sudo certbot renew --dry-run
   ```  

---

## **Usage**  

To access the landing page, visit [https://osinachiproject.online](https://osinachiproject.online).  

---

## **Contributors**  

- **Osinachi Egbuna** – Project creator and primary contributor.  

---

## **License**  

This project is distributed under the MIT License. For more details, refer to the `LICENSE` file.  

---

## **Steps to Add the README to Your Repository**  

1. **Create a README File**:  
   - Run the following command in your project directory:  
     ```bash
     touch README.md
     ```  

2. **Edit the README File**:  
   - Open the file using your preferred text editor.  
   - Copy and paste the content of this documentation into the file.  

3. **Commit and Push the README to GitHub**:  
   ```bash
   git add README.md
   git commit -m "Added README documentation"
   git push
   ```  

---

## **Process Summary**  

1. **Server Setup**: Provisioned an EC2 instance and configured security groups for HTTP, HTTPS, and SSH traffic.  
2. **Web Server Installation**: Installed and started the Nginx web server.  
3. **Landing Page Deployment**: Uploaded a custom `index.html` file to the server's web root directory.  
4. **SSL Configuration**: Secured the website with Certbot-generated SSL certificates.  
5. **Verification**: Tested the website’s accessibility and SSL auto-renewal functionality.  

Should you require additional information or assistance, please do not hesitate to reach out.  
