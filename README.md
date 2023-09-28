# Montana Tech GitHub Basics Lab
In this lab, you will become familiar with GitHub as well as the importance of it.

## Objectives
- Learn how to fork a repository
- Learn how to clone a repository
- Learn how to modify README.md file
- Learn how to get changes to cloned GitHub repository on local machine
- Learn how to create .gitignore file
- Learn how to add local changes to GitHub repository

## Downloads
- Git: [download link](https://git-scm.com/downloads)
  - On the school computers, use the Windows Standalone Installer (64-bit)
  - **Keep clicking 'next' in installer until the install begins**
 
- Visual Studio Code: [download link](https://code.visualstudio.com/download)
  - This is not needed but is recommended when dealing with a Git repository locally
  - [Visual Studio Community](https://visualstudio.microsoft.com/vs/community/) is recommended when manipulating C++/C# code or when dealing with project solutions (``.sln`` file endings). Since we are not manipualting any of the code in this lab, Visual Studio Code will suffice.

## Instructions

### Forking A Repository
1. Click the "fork" button in the upper right
   - This will create a copy of the main repository (by Will Augustine) into your account so you can modify and update the files.<br>
   
**Since you have your own repository now, I need access to it for grading. To do this, add me as a collaborator:**

1. Within your new repository, click the ``Settings`` button at the top of the page
2. In the left menu under **Access**, click ``Collaborators``
3. Click the green ``Add people`` button
4. Use my email to add me as a collaborator: **william_augustine@hotmail<span>.</span>com**
  
### Cloning A Repository To Your Local Machine
**NOTE: You will have to download Git before proceeding** (see [above](https://github.com/WillAugustine/MontanaTech-CSCI232#downloads) for instructions)
1. Decide where you want the repository to live on your local machine (Desktop is recommended). **DO NOT use a flash drive**
2. Copy the path of your chosen directory (easiest to use file explorer for Windows)
   - Example: C:\Users\willa\OneDrive\Desktop
3. Open your command prompt
4. Navigate to your chosen directory using `cd <chosen directory path>`
5. Ensure Git is downloaded to your machine by using `git --version`
6. If Git is downloaded, go to the repository you want to clone on GitHub and click the green code button
7. Copy the link in the **HTTPS** tab
8. Back in your command prompt window, copy the repository files to your local machine by using `git clone <link you copied>`
9. If successful, the files should now be on your local machine

### Modifying The README.md File
1. On GitHub, navigate to the main page of your forked repository
2. Click the pencil button at the top right of the README.md file
3. Add a section header titled "Submission Information" before the "Objectives" section (make it a second-level header)
4. Within the "Submission Information" section, add the following:<br>
   **NOTE: All information in this section should have a bolded title** (ex. "**Name:** Will Augustine")
   - Name: Your name
   - Course: Course number, section number, and course name
   - Due: Assignment due date
   - GitHub: Have the text "view the rest of my GitHub here" be a link that, when clicked, takes them to your GitHub profile page.
   - Favorites: Say what you are ranking (ex. ice cream flavors) followed by a numbered list of your **top three** favorites
5. Click the "Commit changes..." button
6. Add a description about the changes you made (it can be brief)
7. Keep the "Commit directly to the main branch" button checked and click "Commit changes"
  
### Getting Changes From GitHub To Your Local Machine
Since you made changes to your README.md file, you need to sync those changes with the files that are on your local machine. This will make sure that you are up-to-date and can add your changes from your local machine to your GitHub when the time comes.
1. Copy the path of your chosen directory **including your repository name** that you chose in the "Cloning A Repository To Your Local Machine" section
   - Example: C:\Users\willa\OneDrive\Desktop\MontanaTech-CSCI232
2. Open your command prompt
3. Navigate to your chosen directory using `cd <chosen directory path>`
4. Run the command `git pull`
   - This will give pull all files from your GitHub repository and add all changes to your local machine
   - Since your local machine is behind your GitHub (you made changes on GitHub without syncing them on your local machine) you should see:
     ```
     ...
     from <GitHub link>
       <version number> <branch name (most likely 'main')> -> origin/<branch name>
     Updating <version number>
     Fast-forward
       <file name> | <number of changes> + (for file insertion) - (for file deletion)
       <# of files changed> changed, <# of insertions> insertions(+), <# of deletions> deletions(-)
     ```
     For example, mine looks like:
     ```git
     ...
     From https://github.com/WillAugustine/MontanaTech-CSCI232
       461f6fe..70c64d1 main    -> origin/main
     Updating 461f6fe..70c64d1
     Fast-forward
       README.md | 24 ++++++++++++++++++++++++-
       1 file changes, 23 insertions(+), 1 deletion(-)
     ```
     Now your local machine has the same files as your online GitHub repository

### Creating The .gitignore File
**NOTE: It is recommended to download Visual Studio Code before proceeding** (see [above](https://github.com/WillAugustine/MontanaTech-CSCI232#downloads) for instructions)<br>
Sometimes, there are files or folders on your local machine that you do not want to be on your online GitHub repository. Adding a .gitignore file to your local machine's files will make it so, when you want to add your local changes to your GitHub repository, it will not add the files specified in the .gitignore file.
1. Open Visual Studio Code
2. Open the folder that contains all of your GitHub files on your local machine in Visual Studio Code
   - Example: C:\Users\willa\OneDrive\Desktop\MontanaTech-CSCI232
3. In the "Explorer" tab, you should see all files in your selected folder
4. Add a new file to the base directory named ``.gitignore``
   - Your new .gitignore file should be highlighted green in the Visual Studio Code Explorer tab with a ``U`` to the right of the file name
5. Add information to the ``.gitignore`` file to prevent the following from being on GitHub:
   - The whole ``NOT-Important`` directory and its contents
   - All Python files (files ending in ``.py`` in the ``SEMI-Important`` directory
   - The ``.vs`` directory in the ``Important`` directory
   - The ``Important.vcxproj.filters`` file from the ``Important`` directory
   - The ``Important.vcxproj.user`` file from the ``Important`` directory<br>
     **NOTE: Follow the above instructions very closely. For example, when it says to remove all Python files, remove all Python files in one line not one file at a time.**
6. Since the files we want to ignore are already on the online GitHub, we need to tell the local files to forget everything that is on the online GitHub. This way we can remove the files listed in our .gitignore file from the online GitHub. To do this, we need to run the command ``git rm --cached -r .``. This removes (``rm``) **ALL** known files (``.``) from the online GitHub (the ``--cached`` files) recursively or including the files in sub-directories (``-r``). Now, all of your file should be green (untracked) or red (deleted). The files that are red are the files from your .gitignore file. <br>
**NOTE: Deleted files will not be deleted from your local files, just from the online GitHub**

### Adding Local Changes to GitHub
When you created your ``.gitignore`` file in Visual Studio Code, you may have noticed the file turned green with a ``U`` appearing to the right of the file name. This is because you are modifying the files in your GitHub repository on your local machine. Here are the following symbols and what they mean:
- ``U``: Untracked file - a file you have on your local machine but not on your online GitHub
- ``M``: Modified file - a file you have on both your local machine and your online GitHub, but there are differences between the files
- ``D``: Deleted file - a file you have on your online GitHub but it was removed or ignored from your local machine
If you have any of these symbols next to your files, that means there are changes on your local machine that need to be added to your online GitHub. To add these local changes to your online GitHub, follow these steps:
1. If you have Visual Studio Code still open, you can open a new terminal within Visual Studio Code by clicking ``New Terminal`` in the ``Terminal`` drop down menu. If you closed Visual Studio Code already, you can either reopen it and the file where your local repository is, or you can open a command prompt and navigate to your local GitHub files using the ``cd`` command like in the [Modifying the README.md File](https://github.com/WillAugustine/MontanaTech-CSCI232#modifying-the-readmemd-file) section
2. It is recommended to get all changes from your online GitHub to your local machine before you add your local changes to your online GitHub. To do this, in the command prompt or the Visual Studio Code terminal, run the command ``git pull``
3. Check the differences between your local files and your online GitHub files. This can be done by running the command ``git status``. You should see information like your branch name, if you are ahead or behind, and any files or directories that are modified, untracked, or deleted.
4. To add your local changes to your online GitHub, you first need to specify what files you want to add from your local machine. This can be done by adding all of the file names to the command, or you can use the shortcut to add all files that have been modified, added, and deleted in one simple command. **Select and run either of these commands**. Here are the commands for each option:
   - For selecting certain files: ``git add <file name> <file name>``
     - For this lab, the command would be ``git add .gitignore``
   - For selecting all modified, added, and deleted files: ``git add -A``<br>
5. After selecting the file(s) you want to sync with your online GitHub, you need to add a brief message describing the changes you made. To do this, you create a **commit** which will contain information including the commit number, the files you are modifying, and the message about your changes. If you cannot fit a description of your changes in one or two brief but descriptive sentences, you may need to split up your commit.
   - To create a commit, use the ``git commit -m "<message>"`` command.
     - For this lab, an example would be ``git commit -m "Added .gitignore file to remove unnecessary files and folders"``
6. Now you need to add the commit to the online GitHub. To do this, you will **push** your changes by using the ``git push`` command.
