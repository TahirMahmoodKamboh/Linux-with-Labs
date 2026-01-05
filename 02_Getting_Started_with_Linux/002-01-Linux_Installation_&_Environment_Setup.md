

# Module 2: Getting Started with Linux

# Linux Installation on VMware (Ubuntu / Red Hat)

---

## 2.1 Introduction to Virtualization

**Virtualization** allows multiple operating systems to run on a single physical machine using a hypervisor.

### Why Use VMware for Learning Linux?

* No risk to host OS
* Easy snapshots and rollback
* Industry-accepted virtualization tool
* Ideal for practice and labs

---

## 2.2 VMware Products (For Learning)

| VMware Product            | Use Case              |
| ------------------------- | --------------------- |
| VMware Workstation Player | Free for personal use |
| VMware Workstation Pro    | Free Advanced features|
| VMware Fusion             | macOS users           |

**Recommended:** VMware Workstation Pro

---

## 2.3 Linux Distributions Used in This Course

### Ubuntu (Debian-based)

* Beginner-friendly
* Large community support
* Common in cloud and DevOps

### Red Hat–Based (Enterprise Linux)

* Red Hat Enterprise Linux (RHEL)
* Rocky Linux / AlmaLinux (free alternatives)
* RHCSA exam oriented

---

## 2.4 System Requirements for Virtual Machine

### Minimum VM Configuration

* CPU: 1–2 vCPUs
* RAM:

  * Ubuntu Server: 2 GB
  * Ubuntu Desktop: 4 GB
  * RHEL/Rocky: 2–4 GB
* Disk: 20–30 GB
* Network: NAT (default)

---

## 2.5 Download Required Software

### VMware

* Download VMware Workstation Player from VMware official site

### Linux ISO

* Ubuntu: ubuntu.com/download
* Rocky Linux: rockylinux.org
* RHEL: access.redhat.com (developer account)

---

## 2.6 Creating a New Virtual Machine in VMware

1. Open VMware
2. Click **Create a New Virtual Machine**
3. Select **Installer disc image file (ISO)**
4. Browse and select Linux ISO
5. Choose Guest OS:

   * Linux
   * Ubuntu Linux / Red Hat Linux
6. Set VM name and location
7. Assign disk size (recommended 30 GB)
8. Customize hardware:

   * Memory
   * Processor
9. Finish setup

---

## 2.7 Installing Ubuntu on VMware

### Installation Steps

1. Start the VM
2. Select **Install Ubuntu**
3. Choose language and keyboard layout
4. Select **Normal Installation**
5. Choose **Erase disk and install Ubuntu**

   * (Affects VM disk only)
6. Set timezone
7. Create user account and password
8. Begin installation
9. Reboot after completion

---

## 2.8 Installing Red Hat / Rocky Linux on VMware

### Installation Steps

1. Start the VM
2. Select **Install Red Hat Enterprise Linux**
3. Choose language
4. Configure:

   * Installation destination (Automatic partitioning)
   * Network & hostname
5. Set root password
6. Create a normal user
7. Begin installation
8. Reboot system

**Exam Note:**
RHCSA prefers **minimal/server installation (no GUI)**.

---

## 2.9 Network Configuration (Default)

* Default VMware network mode: **NAT**
* VM automatically gets IP address
* Internet access available

---

## 2.10 Login and First Boot

After reboot:

* Login using username/password
* For server installations, CLI prompt appears
* For desktop installations, GUI login screen appears

---

## 2.11 Post-Installation Verification

### Check OS Version

```bash
cat /etc/os-release
```

### Check Kernel Version

```bash
uname -r
```

### Check IP Address

```bash
ip a
```

---

## 2.12 Snapshot and VM Management (Important)

* Take snapshot after successful installation
* Use snapshot before experiments
* Easy recovery if system breaks

---

## 2.13 Common Installation Mistakes

* Assigning insufficient RAM
* Selecting wrong ISO
* Forgetting to enable network
* Installing GUI for server practice
* Not taking snapshots

---

## 2.14 Practical Teaching Points

* Why VMware is safer than dual boot
* Ubuntu vs Red Hat in real jobs
* Server installation without GUI
* Importance of snapshots
* VM resource optimization

---

## 2.15 Exam-Oriented Notes (RHCSA / LPIC)

* Installation should be **minimal**
* Understand automatic partitioning
* Know difference between Ubuntu and RHEL-based installs
* Be comfortable with CLI-only login
* Understand VMware networking (NAT)

---

## 2.16 Learning Outcomes

After this module, learners will be able to:

* Install Ubuntu or Red Hat–based Linux on VMware
* Configure basic VM resources
* Perform initial login and verification
* Prepare a Linux VM for further learning

---

If you want next (still **Module 2 only**), I can add:

* **Step-by-step screenshots checklist**
* **Ubuntu vs Red Hat comparison table**
* **30 MCQs for Module 2**
* **Lab assignment for students**
* **RHCSA-style installation questions**

Tell me what you want to add.
