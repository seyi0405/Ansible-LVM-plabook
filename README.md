# Ansible-LVM-plabook
# Creating an LVM on an existing disk with ansible playbook
# 📦 Ansible LVM Playbook

This project contains an Ansible playbook that automates the process of creating, formatting, and mounting a Logical Volume Manager (LVM) partition on a Linux system.

---

## 🚀 Features
- Creates a **Physical Volume** on `/dev/sdb`
- Creates a **Volume Group** (`vg`)
- Creates a **Logical Volume** (`lv`) of size **3GB**
- Formats the Logical Volume with `ext4`
- Mounts it at `/mount-point`
- Ensures persistence in `/etc/fstab`

---

## 📂 Project Structure
ansible-lvm-playbook/
├── lvm.yml # Ansible playbook
└── README.md # Documentation

yaml
Copy
Edit

---

## ⚙️ Requirements
- Ansible **2.9+**
- Target host(s) must have `lvm2` installed
- Required Ansible collections:
  ```bash
  ansible-galaxy collection install community.general ansible.posix
▶️ Usage
Clone this repository:

bash
Copy
Edit
git clone https://github.com/<your-username>/ansible-lvm-playbook.git
cd ansible-lvm-playbook
Update your inventory file with the target hosts.

Run the playbook:

bash
Copy
Edit
ansible-playbook -i inventory lvm.yml
🔍 Verification
After running the playbook, verify the setup:

bash
Copy
Edit
# Check LVM details
lsblk

# Check mounted filesystem
df -h /mount-point

# Confirm persistence in fstab
cat /etc/fstab
📖 Example Output
bash
Copy
Edit
$ lsblk
sdb          8:16   0   10G  0 disk
└─vg-lv     253:0   0    3G  0 lvm  /mount-point
bash
Copy
Edit
$ df -h /mount-point
Filesystem           Size  Used Avail Use% Mounted on
/dev/mapper/vg-lv    3.0G   24M  2.9G   1% /mount-point
🛠️ Skills Demonstrated
LVM management with Ansible

Persistent filesystem mounting

Infrastructure as Code (IaC) practices

Automation of Linux system administration tasks<img width="904" height="732" alt="homelab" src="https://github.com/user-attachments/assets/b021af0b-be9d-4eb0-a1ce-5c6b44507bdb" />
