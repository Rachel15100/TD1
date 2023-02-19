# TD1

## EXERCISE 1 

1. List all files 
```
ls -a
```

2. Change directory 
```
cd 
```

3. Check location
```
pwd
```

4. Creation of a directory 
```
 
```

5. Go to the general home directory 
```
 cd /home
```

6. Go to my home directory 
```
 cd ~
```

7. Go back to the general home directory 
```
 cd .. 
#or, in this case 
 cd - 
```

8. Go to the root directory 
```
 cd /
```

9. Go to my home directory 
```
 cd ~
```

10. Create a directory named test
```
 mkdir test
```

11. Go into this new directory
```
 cd /home/rgomesse/test
```

12. Check location
```
 pwd
```

## EXERCISE 2

1. Go to my home directory
```
 cd ~
```

2. Check the location
```
 pwd
```

3. Create a folder named linux_ex_1
```
 mkdir linux_ex_1
```

4. Go into this folder 
```
 cd /home/rgomesse/linux_ex_1
```

5. Create an empty file text named rachel_gomesse.txt
```
 touch rachel_gomesse.txt
```

6. Create a new folder notes
```
 mkdir notes
```

7. Move the text file into the new folder 
```
 mv rachel_gomesse.txt notes
```

8. Rename the text file by rachel_gomesse_2023.txt
```
 mv rachel_gomesse.txt rachel_gomesse_2023.txt
```

9. Make a copy of the folder notes, name it notes_2022
```
 cd /home/rgomesse/linux_ex_1
 cp -r notes notes_2022
```

10. Delete the notes folder using the verbose option
```
 rm -rv /home/rgomesse/linux_ex_1/notes
```

## EXERCISE 3

1. Create a script script_1.sh in the folder linux_ex_1
```
 vim script_1.sh
```

2. Write the commands in the script
```
 #!/bin/bash
 echo "script running please wait ..."
 echo "done"
```

3. Save and quit the script
```
:wq
```

4. Display the script
```
ls
```

5. Run the script
```
cat script_1.sh
```

## EXERCISE 4.1

1. Create a confidential file, write something within the file, display the file content, display the current permissions
```
 touch confidential.txt
 cat > confidential.txt 
 cat confidential.txt
 ls -l confidential.txt
```

2. Change the current permissions to read only for all users, display the new permissions, modify and save the file, display the file content
```
 chmod u=r,g=r,o=r confidential.txt
 ls -l confidential.txt
 vim /home/rgomesse/linux_ex_1/confidential.txt
 #Impossible to modify the file beacause all users only can read it 
 #To save the file
 :wq 
 ls -l confidential.txt
```

3. Change the current permissions to read and write for all users, display the new permissions, modify and save the file
```
 chmod u=rw,g=rw,o=rw confidential.txt
 ls -l confidential.txt
 vim /home/rgomesse/linux_ex_1/confidential.txt
 :wq
 ls -l confidential.txt
```

4.Change the current permissions to read write and execute for the owner, display the new permissions, remove the read permission to other users, display the new permissions, change the permissions to read, write and execute for all users
```
 chmod u=rwx,g=rw,o=rw confidential.txt
 ls -l confidential.txt
 chmod u=rwx,g=w,o=w confidential.txt
 ls -l confidential.txt
 chmod u=rwx,g=rwx,o=rwx confidential.txt
```

## EXERCISE 4.2

1. Go to the root folder
```
 cd /
```

2. Create a file in root user mode named .private_file, write something in the file, display all the files in the folder including hidden files
```
 sudo mkdir .private_file.txt
 sudo  vim /home/rgomesse/linux_ex_1/.private_file.txt
 ls -la
```

3. Modify the file in normal mode, write some new information in the file
```
 #Impossible to modify the file in the normal mode ; the permission is read only 
```

4. Modify the file in root user mode, write some new information in the file
```
 sudo vim /home/rgomesse/linux_ex_1/.private_file.txt
 ls -la .private_file.txt
```

5. Change permissions to read, write and execute for all users, modify the file content in normal user mode, display the file content
```
 sudo chmod u=rwx,g=rwx,o=rwx .private_file.txt
 vim /home/rgomesse/linux_ex_1/.private_file.txt
 #To leave the file and save the modification : :wq!
```

## EXERCISE 4.3

1. Change permissions of .private_file to read and write for all users, in normal user mode
```
 chmod u=rw,g=rw,o=rw .private_file.txt
 #changing permissions of '.private_file.txt': Operation not permitted
```

2.Set the new file owner as the current user
```
 sudo chown rgomesse .private_file.txt
 chgrp rgomesse .private_file.txt
```

3. Change permissions of .private_file to read and write for all users, in normal user mode
```
 chmod u=rw,g=rw,o=rw .private_file.txt
```

## EXERCISE 4.4

1. Update your main package manager named apt
```
 sudo apt-get update
```

2. Update your main package manager named apt
```
 sudo apt-get upgrade
 Y
```

3. Install the package cmatrix
```
 sudo apt-get install cmatrix
```

4. Launch cmatrix
```
 cmatrix
```

5. Quit cmatrix
```
 #ctrl+c
```

6. Install the package tmux
```
 sudo apt-get install tmux
```

7. Launch tmux
```
 tmux
```

8. Say "Hello session 0" using bash in your current tmux session
```
 vim test.sh
 #!/bin/bash
 echo "Hello session 0"
```

9. Launch cmatrix in your current tmux session
```
 cmatrix
```

10. Detach from the current tmux session (without stopping cmatrix)
```
 #ctrl + B 
 #Then D
```

11. Create a new tmux session
```
 tmux
```

12. Say "Hello session 1" using bash in your new tmux session
```
 vim test_session_1.sh
 #!/bin/bash
 echo "Hello session 1"
```

13. Detach from the current tmux session
```
 #ctrl + B 
 #Then D
```

14. List all tmux session
```
 tmux ls
```

15. Attach again to session 0
```
 tmux attach -t 0
```

16. Detach again
```
 #ctrl + B
 #Then D
```

17. Attach again to session 1
```
 tmux attach -t 1
```

18. Detach again
```
 #ctrl + B
 #Then D
```

19. List all rummuning sessions 
```
 tmux ls
```

20. Kill all tmux sessions and quit tmux
```
 tmux kill-session -t 0
 tmux kill-session -t 1
```

21. List all sessions 
```
 tmux ls
```
