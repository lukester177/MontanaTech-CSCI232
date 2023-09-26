# Montana Tech GitHub Basics Lab
In this lab, you will become familiar with GitHub as well as the importance of it.

## Objectives
- Learn how to fork
- Learn how to clone a repository
- Learn how to modify README.md file
- Learn how to get changes to cloned GitHub repository on local machine
- Learn how to create .gitignore file
- Learn how to add local changes to GitHub repository

## Downloads
- Git: [download link](https://git-scm.com/downloads)
  - On the school computers, use the Windows Standalone Installer (64-bit)
  - **Keep clicking 'next' in installer until the install begins**
 
- Visual Studio Community: [download link](https://visualstudio.microsoft.com/vs/community/)
  - This is not needed but is recommended when dealing with C++ code.

## Instructions

### Forking A Repository
1. Click the "fork" button in the upper right
   - This will create a copy of the main repository (by Will Augustine) into your account so you can modify and update the files.
  
### Cloning A Repository To Your Local Machine
**NOTE: You will have to download Git before proceeding** (see [above](https://github.com/WillAugustine/MontanaTech-CSCI232/edit/main/README.md#downloads) for instructions)
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
4. Run the command `git status`
   - This will give you the status of your local files compared to your GitHub repository
   - Since your local machine is behind your GitHub (you made changes on GitHub without syncing them on your local machine) you should see:
     
