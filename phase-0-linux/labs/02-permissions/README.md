## Lab Goal

Understand how Linux permissions and ownership work, and how they enforce security in a multi-user operating system.

## Topics Covered

- User and group concepts (UID, GID)
- System files (`/etc/passwd`, `/etc/group`, `/etc/shadow`)
- File and directory permissions (r, w, x)
- Permission representation (symbolic and octal)
- Default permissions (`umask`)
- Ownership management
- Privilege escalation (`su`, `sudo`)
- Password management
- Special permissions (setuid, setgid, sticky bit)

## Key Observations

- Linux is designed as a **multi-user system**, which is why permissions exist.
- Every user has a **UID and GID**, visible using `id`.
- User and group data are stored in:
  - `/etc/passwd`
  - `/etc/group`
- Passwords are securely stored in `/etc/shadow`.
- Every file/directory has **read, write, execute** permissions.
- Permissions are split into **user, group, others**.
- Permissions can be written in:
  - Symbolic form → `rwx`
  - Octal form → `7 6 4`
- `umask` controls default permissions for new files.
- Ownership is controlled via `chown` and `chgrp`.
- `su` and `sudo` allow privilege escalation.
- Special permissions exist:
  - `setuid`
  - `setgid`
  - `sticky bit`

## Commands Used

```bash
id      # Display user identity
chmod   # Change file permissions
umask   # Set default permissions
su      # Switch user
sudo    # Execute as another user
chown   # Change file owner
chgrp   # Change group ownership
passwd  # Change user password
```

## Key Takeaway

Permissions are not just rules —  
they are the **core security mechanism of Linux**.

Understanding them is essential before moving to:

- Docker (container isolation)
- Kubernetes (security contexts)
- System security and hardening
