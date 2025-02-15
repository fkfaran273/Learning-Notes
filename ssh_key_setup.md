
<!-- This command generates a new SSH key pair using the RSA algorithm with a key size of 4096 bits. -->
<!-- The -C flag adds a label (comment) to the key, typically an email address for identification. -->
# generate if not already generated
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"


# Start the SSH agent (Run this in PowerShell as Administrator):
> Get-Service ssh-agent | Set-Service -StartupType Automatic
> Start-Service ssh-agent


# Add your SSH key to the agent:
#  If successful, it will show: Identity added: C:\Users\YourUser\.ssh\id_rsa (your-email@example.com)

> ssh-add C:\Users\YourUser\.ssh\id_rsa



# Copy the SSH key to your clipboard after generating through below command:
# 2️ Select the key and copy it.
# Go to GitHub → Click on your profile (top-right corner) → Settings.
# Go to SSH and GPG keys → Click New SSH Key.
# Paste your SSH key and Save it.
# ✅ Your SSH key is now added to GitHub! 🎉

> cat ~/.ssh/id_rsa.pub


# Test SSH Connection
# if success it will show:
 <!-- Hi fkfaran273! You've successfully authenticated, but GitHub does not provide shell access. -->
> ssh -T git@github.com

<!-- // This command appends the SSH public key of GitHub's server to the known_hosts file.
// It ensures that the server's key is recognized and trusted, preventing man-in-the-middle attacks
// when connecting to GitHub via SSH. -->
ssh-keyscan github.com >> ~/.ssh/known_hosts
