<p align="center">
<img src="https://i.imgur.com/ynXhouJ.jpg" alt="Linux Logo"/>
</p>

<h1>Managing File Permissions in Linux</h1>
In this home lab, my task is to practice examining existing permissions on a file system. I’ll need to determine if the permissions match the authorization that should be given and if they do not match, modify the permissions to authorize the appropriate users and remove any unauthorized access.<br />



<h2>Environments and Technologies Used</h2>

- Bash

<h2>Operating System Used </h2>

- Linux

<h2>High-Level Overview:</h2>

- <b>Navigate to the directory:</b> Start in the home directory, use 'pwd' command to confirm location, then 'ls' to view contents, and 'cd projects' to enter the "projects" directory.
- <b>Review file permissions:</b> Within "projects", use 'ls -la' to list all files (including hidden, which start with a . in their name) and their permissions, noting the 10-character permission string for each entry.
- <b>Modify file and direcory permissions:</b> Change specific permissions with 'chmod' for normal/hidden files and directories. 

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/uJHnegB.png" height="80%" width="80%" alt="Lab Steps"/>
</p>
<p>
First, I need to navigate to the "projects" directory. To do that, I need to know where I am starting from. To do that, I will use the 'pwd' command. This is asking the system "Where am I right now?". The response, /home/researcher2, tells me that I am in the "researcher2" user's home directory.

Next, I will use the 'ls' command to list the contents of the current directory. The system shows that there is a subdirectory named "projects", which is where I need to go. I use the 'cd projects' command to change to the "projects" directory. 

Once inside the correct directory, I need to list all files and permissions. I use the ‘ls -la’ command to do that. The output shows a 10-character string beginning each entry, which indicates how the permissions on the file are set. Let’s dive a little deeper into this: 

</p>
<br />

<p>
<img src="https://i.imgur.com/vZdFxQa.png" height="80%" width="80%" alt="Lab Steps"/>
</p>
<p>
The 1st character indicates the file type. When this character is a hyphen (-), it's a regular file. The 2nd-4th characters indicate the read (r), write (w), and execute (x) permissions for the user. The 5th-7th characters indicate the permissions for the group & The 8th-10th characters indicate the permissions for the ‘other’ type of owner. For example, a directory with full permissions for all owner types would be “drwxrwxrwx”.

In this scenario, we don’t want any ‘other’ type of owner to have write permissions on any files. I will use the ‘chmod o-w project_k.txt’ command to change the permissions of the file, then use the ‘ls -l’ to observe the changes. 
</p>
<br />

<p>
<img src="https://i.imgur.com/hNw4a0w.png" height="80%" width="80%" alt="Lab Steps"/>
</p>
<p>
The research team has archived .project_x.txt, which is why it’s a hidden file (hidden files are characterized with a period at the beginning of their name). This file should not have write permissions for anyone, but the user and group should be able to read the file. I will use the ‘chmod u=r, g=r project_x.txt’ command to make these changes. Keep in mind, 'ls -l' does not display hidden files so I must use 'ls -la' to observe the changes. 
</p>
<br />

<p>
<img src="https://i.imgur.com/SdpR7WF.png" height="80%" width="80%" alt="Lab Steps"/>
</p>
<p>
Finally, I need to change the permissions of the “drafts” directory to only be accessible to the user. I will use the ‘chmod g-x drafts’ command to make the appropriate changes and ‘ls -l’ to confirm my work.
</p>
<br />

<h1>Summary</h1>
In this home lab, I navigated and analyzed permissions within a Linux system. I adjusted permissions on specific files to enhance system security. Furthermore, I modified the accessibility of a directory, ultimately refining my skills in safeguarding Linux-based data.<br />
