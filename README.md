<!---
{
  "depends_on": [],
  "author": "Stephan Bökelmann",
  "first_used": "2025-04-01",
  "keywords": ["linux", "users", "groups", "permissions", "sudo"]
}
--->

# Users and Groups in *NIX Systems

## 1) Introduction

Modern operating systems, such as Linux, provide a user-friendly interface for managing users, groups, and file permissions.

In the era of room-sized computers, multiple terminals were connected to a single system. Thus, OSes introduced **multi-user** capabilities, allowing each user to have their own settings, files, and permission boundaries.

These features are still foundational today. Users are grouped together via **groups**, which allow shared access to resources.

- **Users**: Individual accounts like `alice`, `bob`, or `root`
- **Groups**: Collections of users like `developers` or `admins`

Each user is identified by a username and user ID (UID), and can belong to one or more groups.

A special user, the `root` user (also known as the *superuser*), has full access to the system. Regular users can temporarily gain elevated privileges using the `sudo` command, depending on their configuration in the `sudoers` file.

Permissions for files and directories fall into three categories:

1. **Owner**
2. **Group**
3. **Others**

In this challenge, you will:

- Learn how to view the current user and groups using `id`
- Understand file ownership and permissions with `ls -l`
- Explore the necessity of `sudo` for administrative tasks

## 2) Tasks

1. **Identify User and Groups**

    ```bash
    id
    whoami
    ```

    - Note your UID, primary group, and supplementary groups.

2. **Explore File Ownership and Permissions**

    ```bash
    cd ~
    ls -l
    ```

    - Look at each file's owner, group, and permissions (e.g., `-rw-r--r--`).

3. **Try the `sudo` Command**

    ```bash
    ls /root
    sudo ls /root
    ```

    - The first command should result in "Permission denied", the second should succeed after password confirmation.

## 3) Questions

- What does the `id` command display?
- What is the difference between a primary group and supplementary groups?
- Why might a user belong to multiple groups?
- Who owns the files in your home directory?
- What is the group associated with those files and why?
- What do the file permissions mean in symbolic form (e.g., `rwxr-x---`)?
- Why were you denied access to `/root` initially?
- What does `sudo` do, and why is it required?
- Why is it important to restrict access to sensitive directories like `/root`?

## 4) Advice

Use `sudo` responsibly. It grants temporary administrative privileges and misuse can have system-wide consequences. Always double-check your commands when using elevated permissions.

