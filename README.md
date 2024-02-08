# File-permissions-in-Linux
Project description
Viewing Permissions: Use ls -l to display detailed information about files and directories, including their permissions. The output shows permissions in the form of -rwxr-xr-- where each character represents specific permissions for the file's owner, group, and others.

Changing Permissions: chmod command is used to change permissions. You can modify permissions by using symbolic mode (u for user/owner, g for group, o for others) along with symbols like + to add permissions, - to remove permissions, and = to set them explicitly. For instance:

chmod u+rwx file.txt grants the file owner read, write, and execute permissions.
chmod go-w file.txt removes write permissions for the group and others.
Changing Ownership: chown command changes the owner of a file or directory. For example:

chown user1 file.txt changes the owner of file.txt to user1.
chown user1:group1 file.txt changes both the owner to user1 and the group to group1.
Changing Group Ownership: chgrp command changes the group ownership of a file or directory. For example:

chgrp group2 file.txt changes the group of file.txt to group2.
Special Permissions: For directories, the chmod command can also set special permissions like +x for allowing access to contents or +s for setting the setuid or setgid bit, which modifies how permissions are applied.

Understanding and managing file permissions is crucial for security and access control in Linux systems, ensuring that the right users or processes have appropriate access to files and directories.
Check file and directory details

Describe the permissions string
The permission string "drwx--x---" represents the following:

The first character d indicates that this entry is a directory. If it were a regular file, the initial character would be -.
The next three characters rwx refer to the permissions for the owner of the directory:
r represents read permission.
w represents write permission.
x represents execute permission.
Therefore, the owner of the directory has read, write, and execute permissions.

The subsequent three characters --x denote the permissions for the group associated with this directory:
The first - means no read permission.
The second x represents execute permission.
Hence, the group has no read permission but does have execute permission.

The last three characters --- represent the permissions for others (users not in the owner's group):
All three dashes (---) indicate no permissions—neither read nor execute permissions are granted.
In summary, for the directory with permissions "drwx--x---":

The owner has read, write, and execute permissions.
The group has execute permission only.
Others have no access permissions to this directory.
Change file permissions
The permission string "drwx--x---" indicates that the directory grants execute permission to the "others" category. To modify this permission and revoke the execute permission for others, you can use the chmod command in Linux.

Change file permissions on a hidden file
The command chmod u-w,g-w,g+r .project_x.txt can be succinctly described as:

u-w,g-w: Removes write (w) permission for the user and group.
g+r: Adds read (r) permission for the group.
.project_x.txt: The file on which these permission changes are applied.

Change directory permissions

Summary
Project Description:
The scenario entails auditing and adjusting file permissions in a Linux environment. Through Linux commands, the goal is to manage access control to files and directories. Tasks include verifying permissions, modifying access levels for users and groups, and ensuring appropriate read, write, and execute permissions. Strengthening security measures and restricting unauthorized access to sensitive files form the core objectives.

Summary:
Throughout this exercise, various tasks were performed to secure file permissions within a Linux system. Initial steps involved examining permissions for specific files, identifying incorrect permissions, and subsequently modifying them. By adjusting access rights for users and groups, the aim was to enhance security and control unauthorized write access to critical files, aligning with best practices for managing file permissions in Linux environments.
