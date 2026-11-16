# Week 01: Linux User & Permission Management

## 🎯 Objective
Demonstrate the ability to set up a secure, isolated development environment by managing users, groups, and strict file permissions, simulating a real-world freelance SysAdmin task.

## ✅ Tasks Completed
- Created a dedicated group for the development team: `web_admins`
- Created a new restricted user account: `web_user` with a home directory
- Assigned `web_user` to the `web_admins` group
- Created a shared project directory: `website_files`
- Transferred ownership of the directory to `web_user:web_admins`
- Applied strict Principle of Least Privilege (PoLP) permissions: `750`

## 🛠️ Commands Executed
```bash
# 1. Create group and user
sudo groupadd web_admins
sudo useradd -m web_user

# 2. Assign user to group
sudo usermod -aG web_admins web_user

# 3. Create directory and set ownership
mkdir website_files
sudo chown web_user:web_admins website_files

# 4. Apply strict permissions (Owner: rwx, Group: r-x, Others: ---)
sudo chmod 750 website_files
