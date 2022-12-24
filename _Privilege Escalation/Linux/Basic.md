- - -
Our ultimate goal with privilege escalation in Linux is to gain a shell running as the root user.
Privilege escalation can be simple (e.g. a kernel exploit) or require a lot of reconnaissance on the compromised system.
In a lot of cases, privilege escalation may not simply rely on a single misconfiguration, but may require you to think, and combine
multiple misconfigurations.

When focusing on privilege escalations in Linux, Understanding how Linux handles permissions is very important.

Users can belong to multiple groups.
Groups can have multiple users.
Every file and directory defines its permissions in terms of a user, a group, and “others” (all other users).

## Users.
User accounts are configured in the /etc/passwd file.
User password hashes are stored in the /etc/shadow file.
Users are identified by an integer user ID (UID).
The “root” user account is a special type of account in Linux.
It has an UID of 0, and the system grants this user access to every file.

## Groups.
Groups are configured in the /etc/group file.
Users have a primary group, and can have multiple
secondary (or supplementary) groups.
By default, a user’s primary group has the same name as their user account.

## Files & Directories.
All files & directories have a single owner and a group.
There are three sets of permissions, one for the owner, one for the group, and one for all “other” users (can also be referred to as “world”).

## File Permissions.
File permissions are self explanatory:
[•] Read – when set, the file contents can be read.
[•] Write – when set, the file contents can be modified.
[•] Execute – when set, the file can be executed 

## Directory Permissions.
Directory permissions are slightly more complicated:
[•] Execute – when set, the directory can be entered. Without this
permission, neither the read nor write permissions will work.
[•] Read – when set, the directory contents can be listed.
[•] Write – when set, files and subdirectories can be created in the directory.


## Special Permissions.
setuid (SUID) bit :
When set, files will get executed with the privileges of the file owner.
setgid (SGID) bit :
When set on a file, the file will get executed with the privileges of the file group.
When set on a directory, files created within that directory will inherit the group of the directory itself.


