---
description: What's AD?
---

# Basics

Microsoft's Active Directory is the **backbone of the corporate world** (no matter how much you hate Microsoft). It makes the world a better place by <mark style="color:yellow;">simplifying the management of devices and users</mark>.

Imagine a scenario, you're administering a business network with 2,000 employees and 5,000 computers. If there's a security patch that needs to be installed on every device, are you going to manually configure them? No, that would take forever. You would use a **Windows Domain**.

Windows Domain basically centralizes the administration of common components of a windows computer network in a single repository called Active Directory. The server that runs the AD service is **Domain Controller**.

## Active Directory Domain Service

The core of Windows Domain.

There're plenty of objects:

* Users
* Groups
* Machines
* etc.

These objects are organized into **Organizational Units** (basically just a container).

### Manage Users

#### Delete OUs and users

You can't delete the OU directly, because OUs are protected against accidental deletion. You need to enable the **Advanced Features** in the View menu.

Then, disable the accidental deletion protection.

#### Delegation

Give specific users some control over some OUs. Meaning, delegation allows you to grant users specific privileges to perform advanced tasks on OUs without needing a Domain Administrator to step in. For example:

* Give the head of IT the privilege to reset some users' passwords.

### Manage Computers

It's the best practice that divides computers into categories like:

* Workstations
* Servers
* Domain Controllers

This step would be very helpful for implementing group policies.

## Group Policies

Use **Group Policy Management** to configure **Group Policy Objects**.

