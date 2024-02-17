```bash
#!/bin/bash
# Switch to the root user to gain full administrative privileges
sudo su
```
This script starts by switching to the root user using `sudo su`. However, running `sudo su` in a script may not be the best practice, as it may require manual input for the sudo password, which disrupts the automation flow.

```bash
# Update all installed packages to their latest versions
yum update -y
```
This command updates all installed packages to their latest versions using `yum` package manager with the `-y` flag to automatically answer yes to all prompts.

```bash
# Install Apache HTTP Server
yum install -y httpd
```
This command installs the Apache HTTP Server using `yum`, again with the `-y` flag to automatically answer yes to all prompts.

```bash
# Change the current working directory to the Apache web root
cd /var/www/html
```
This changes the current working directory to `/var/www/html`, the default root directory for Apache web server.

```bash
# Install Git
yum install git -y
```
This command installs Git version control system.

```bash
# Clone the project GitHub repository to the current directory
git clone htps://github.com/ascendesys/host-a-static-website-on-aws.git
```
Here, you're attempting to clone a GitHub repository. However, there's a typo in the URL ("htps" instead of "https"), which will cause the command to fail.

```bash
# Copy all files, including hidden ones, from the cloned repository to the Apache web root
cp -R host-a-static-website-on-aws/. /var/www/html/
```
This command recursively copies all files, including hidden ones, from the cloned repository to the Apache web root directory.

```bash
# Remove the cloned repository directory to clean up unnecessary files
rm -rf host-a-static-website-on-aws
```
This removes the cloned repository directory to clean up unnecessary files after copying them to the web root.

```bash
# Enable the Apache HTTP Server to start automatically at system boot
systemctl enable httpd
```
This command enables the Apache HTTP Server to start automatically at system boot time.

```bash
# Start the Apache HTTP Server to serve web content
systemctl start httpd
```
Finally, this command starts the Apache HTTP Server to begin serving web content.

