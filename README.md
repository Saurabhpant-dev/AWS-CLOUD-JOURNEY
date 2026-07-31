# AWS-CLOUD-JOURNEY
Daily AWS and DevOps hands-on practice notes and projects
1. AWS Account & EC2 Instance Launching
• Region Selected: Asia Pacific (Mumbai) ap-south-1

• Instance Name: MY-FIRST-LINUX-SERVER

• AMI (Amazon Machine Image): Amazon Linux 2023

• Instance Type: t3.micro (Chosen for Free Tier eligibility / cost-effective testing)

• Key Pair (.pem): RSA Key Pair created and downloaded for SSH authentication.

• Security Group (Firewall): Configured inbound rule to allow SSH traffic (Port 22).

• Storage Allocation: 8.0 GiB GP3 EBS volume attached as root partition (/dev/nvme0n1p1).

---

2. Server Status & Inspection
• Instance ID: i-0cf7195ef878a01e2

• Instance State: Running

• Status Checks: Passed 3/3 system & instance health checks.

• Network Details:

  • Public IPv4 Address: 13.201.188.0

  • Private IPv4 Address: 172.31.9.129

---

3. EC2 Terminal Connection
• Connected to server using EC2 Instance Connect (Browser-based SSH terminal).

• Terminal Username: ec2-user

• Hostname Format: ip-172-31-9-129

---

4. Linux Commands Executed & Core Concepts Learned
System Information Commands

• whoami: Displays current logged-in user (ec2-user).

• uname -a: Displays Linux kernel version (6.18.38-76.139.amzn2023.x86_64).

• df -h: Shows disk space usage in human-readable format (Verified 8GB root drive at /dev/nvme0n1p1).

• pwd: Prints absolute current working directory path.

• ls: Lists files and directories in current location.

File & Directory Management

• mkdir <dir_name>: Creates new directory.

• cd <dir_name>: Changes directory.

• touch <filename>: Creates empty file.

• rm -rf <file/folder>: Force removes files or directory trees recursively.

Important Realizations & Common Pitfalls Identified

• Linux Space Handling:

  • Running mkdir aws day without quotes creates two separate directories (aws and day) instead of one named aws day.

  • Trying cd aws day fails with -bash: cd: too many arguments.

  • Best Practice: Use underscores (aws_day) or hyphen (aws-day) for directory naming.

• Command Syntax Errors Observed:

  • cdaws day fails with -bash: cdaws: command not found (Space missing after cd).

  • Searching for non-existent merged directory awsday returns No such file or directory.

---

5. Cleanup & Cost Control (Termination)
• Action Taken: Terminate (delete) instance initiated from AWS EC2 Console (Instance State -> Terminate instance).

• Status Transition: Running -> Shutting-down -> Terminated.

• Reason: Permanent deletion prevents unnecessary background charges and enforces fresh deployment practice for future sessions.
