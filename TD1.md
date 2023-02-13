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
 sudo  vim .private_file.txt
 ls -la .private_file.txt
```

5. Change permissions to read, write and execute for all users
```
 sudo chmod u=rwx,g=rwx,o=rwx .private_file.txt
```
