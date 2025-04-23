![image](https://github.com/user-attachments/assets/10a95152-a2a9-4d1b-b35b-47f02e76af01)# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```
### Display the content of the files
cat < file1
## OUTPUT
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
```


cat < file2
## OUTPUT
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
```

# Comparing Files
cmp file1 file2
## OUTPUT
```
file1 file2 differ: byte 1, line 1
```
 
comm file1 file2
 ## OUTPUT
 ```
anil aggarwal
	barun sengupta
chanchal singhvi
		c.k. shukla
	lalit chowdury
		s.n. dasgupta
comm: file 2 is not in sorted order
```

 
diff file1 file2
## OUTPUT
```
 chanchal singhvi
---
> anil aggarwal
> barun sengupta
2a4
> lalit chowdury
4d5
< sumit chakrobarty
```


#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```


cut -c1-3 file11
## OUTPUT
```
Hell
This
```



cut -d "|" -f 1 file22
## OUTPUT
```
1001 
1002 
1003
```

cut -d "|" -f 2 file22
## OUTPUT
```
Ram 
tom 
Joe
```
cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT
```
Hello world
```


grep hello newfile 
## OUTPUT
```

hello world
````




grep -v hello newfile 
## OUTPUT
```
Hello world
```

cat newfile | grep -i "hello"
## OUTPUT

![Screenshot from 2025-02-26 11-20-36](https://github.com/user-attachments/assets/e78a65bf-a75c-454b-8058-9612636c49cd)






cat newfile | grep -i -c "hello"
## OUTPUT

![Screenshot from 2025-02-26 11-17-34](https://github.com/user-attachments/assets/a77e5e66-6ef2-4e47-aced-55b5b26e4e06)






grep -R ubuntu /etc
## OUTPUT
![Screenshot from 2025-02-26 11-26-17](https://github.com/user-attachments/assets/a8098925-25cb-40e4-bf96-7316acb2bfbc)




grep -w -n world newfile   
## OUTPUT
![Screenshot from 2025-02-26 11-27-48](https://github.com/user-attachments/assets/97828033-feb4-42b7-b33a-6102b83129ad)



cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT
![Screenshot from 2025-02-26 11-30-32](https://github.com/user-attachments/assets/0519b9da-8633-437c-9aca-18cfb1dff84c)




egrep -w '(H|h)ello' newfile 
## OUTPUT
![Screenshot from 2025-02-26 11-32-11](https://github.com/user-attachments/assets/ade601ab-3b83-4e9b-b468-d55beae73c39)




egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
![Screenshot from 2025-02-26 11-33-35](https://github.com/user-attachments/assets/b82a191f-4cc5-4841-a8bf-3d6401a7058d)





egrep '(^hello)' newfile 
## OUTPUT
![Screenshot from 2025-02-26 11-34-48](https://github.com/user-attachments/assets/f78ac7cd-5d43-4cbf-8e53-e8fd56e5aa2a)




egrep '(world$)' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-16-54](https://github.com/user-attachments/assets/da41b83d-35d0-466a-93b6-645d59ba428d)




egrep '(World$)' newfile
## OUTPUT
![Screenshot from 2025-03-03 11-20-22](https://github.com/user-attachments/assets/beb2872f-7417-441e-82b0-79c9d516c48c)



egrep '((W|w)orld$)' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-23-06](https://github.com/user-attachments/assets/5a75b737-75de-495a-b550-3a9e98b3a77a)



egrep '[1-9]' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-24-32](https://github.com/user-attachments/assets/4e1f92e1-e3be-45b4-8120-ce3e08e7f23f)




egrep 'Linux.*world' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-26-54](https://github.com/user-attachments/assets/78d0965a-deb0-470e-833b-f51b69ddbceb)



egrep 'Linux.*World' newfile 
## OUTPUT
![Screenshot from 2025-03-03 11-28-24](https://github.com/user-attachments/assets/4eead13b-29de-4bbd-a18b-386d03f78f25)



egrep l{2} newfile
## OUTPUT
![Screenshot from 2025-03-03 11-29-36](https://github.com/user-attachments/assets/cf1175a8-43c5-4399-a7db-167322ffd800)


egrep 's{1,2}' newfile
## OUTPUT 
![Screenshot from 2025-03-03 11-30-22](https://github.com/user-attachments/assets/b39ec095-0413-44a6-8d2b-700cdd2ab17a)




cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
![Screenshot from 2025-03-03 11-32-01](https://github.com/user-attachments/assets/97634078-ce9e-4a5e-9772-202e81dc4b3f)




sed -n -e '$p' file23
## OUTPUT

![Screenshot from 2025-03-03 11-34-11](https://github.com/user-attachments/assets/d2e3e466-ca5d-4e8b-a9e0-64a5c8b22b69)


sed  -e 's/Ram/Sita/' file23
## OUTPUT
![Screenshot from 2025-03-03 11-35-52](https://github.com/user-attachments/assets/e405c035-bc50-4f39-a80a-69eb9a8cc66c)



sed  -e '2s/Ram/Sita/' file23
## OUTPUT

![Screenshot from 2025-03-03 11-36-27](https://github.com/user-attachments/assets/72841290-6175-44d6-88fc-58175845a05e)


sed  '/tom/s/5000/6000/' file23
## OUTPUT
![Screenshot from 2025-03-03 11-36-57](https://github.com/user-attachments/assets/333fef07-c0fc-4b5a-a7ce-dceaea17f8a8)



sed -n -e '1,5p' file23
## OUTPUT

![Screenshot from 2025-03-03 11-38-39](https://github.com/user-attachments/assets/ae07d716-09ee-487a-9c68-0871d6db740d)




sed -n -e '2,/Joe/p' file23
## OUTPUT

![Screenshot from 2025-03-03 11-40-01](https://github.com/user-attachments/assets/b784fdea-ea20-4d55-b41e-31531616af01)




sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
![Screenshot from 2025-03-03 11-40-48](https://github.com/user-attachments/assets/c8af116c-c196-4f16-98d9-ec490eba28f4)




seq 10 
## OUTPUT

![Screenshot from 2025-03-03 11-41-38](https://github.com/user-attachments/assets/8df1d3a5-34eb-45f3-a4dd-2d603e53aeeb)


seq 10 | sed -n '4,6p'
## OUTPUT
![Screenshot from 2025-03-03 11-42-18](https://github.com/user-attachments/assets/c7b39bf3-7267-4864-86d4-c8d6c70fd0e2)




seq 10 | sed -n '2,~4p'
## OUTPUT

![Screenshot from 2025-03-03 11-43-46](https://github.com/user-attachments/assets/31a89601-ab21-483b-bedf-0164e4479f79)



seq 3 | sed '2a hello'
## OUTPUT

![Screenshot from 2025-03-03 11-44-17](https://github.com/user-attachments/assets/81968fd3-2e9f-485e-b19c-9dca44573582)



seq 2 | sed '2i hello'
## OUTPUT

![Screenshot from 2025-03-03 11-45-03](https://github.com/user-attachments/assets/152743f5-91ef-4af3-b225-ed5d1121acb1)



seq 10 | sed '2,9c hello'
## OUTPUT

![Screenshot from 2025-03-03 11-45-53](https://github.com/user-attachments/assets/7ca193f5-edae-4bb0-b838-021b425e95a7)



sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
![Screenshot from 2025-04-23 10-12-47](https://github.com/user-attachments/assets/56b1bc00-44f3-42ed-af71-50f71e2d9568)




sed -n '2,4{s/$/*/;p}' file23


#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
![Screenshot from 2025-04-23 10-15-08](https://github.com/user-attachments/assets/435464f0-5756-483b-897f-9750ffd61aaf)



cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT
![image](https://github.com/user-attachments/assets/f51426ac-73d2-4c57-97fe-4a4c06016700)




#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
 ![image](https://github.com/user-attachments/assets/32f12753-b5fd-4c35-9d64-ab05528d0f70)


cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
![image](https://github.com/user-attachments/assets/97919f3d-798a-4dd5-8173-a4e17546628f)


 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
![image](https://github.com/user-attachments/assets/e0784014-7b39-4f77-85c3-9f1dda590eeb)




#Backup commands
tar -cvf backup.tar *
## OUTPUT
![image](https://github.com/user-attachments/assets/6eee9c46-fcbf-4c57-b2c3-bcb6068f0661)


mkdir backupdir
 
mv backup.tar backupdir
 
tar -tvf backup.tar
## OUTPUT
![image](https://github.com/user-attachments/assets/3e98bcc6-45f3-481f-871c-2e5881cac51c)



tar -xvf backup.tar
## OUTPUT
![image](https://github.com/user-attachments/assets/9b09d2c0-7f9c-4ea7-9c77-a47aa78d24d5)


gzip backup.tar

ls .gz
## OUTPUT

![Screenshot from 2025-04-23 10-24-30](https://github.com/user-attachments/assets/def4bb87-17a2-4dd8-9e74-2ad21d093465)

 
gunzip backup.tar.gz
## OUTPUT
![Screenshot from 2025-04-23 10-24-30](https://github.com/user-attachments/assets/1b682c36-af5b-4c65-a7c5-d5189f3b806b)


 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT

![image](https://github.com/user-attachments/assets/decce928-321f-4d5c-ab9c-ad1bb13843e1)

 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
![image](https://github.com/user-attachments/assets/a69d0620-b790-4c08-b990-8ed27d1321ca)



cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT
![image](https://github.com/user-attachments/assets/0b8f890e-0a53-4554-a800-6f8111dc4655)


 
ls file1
## OUTPUT
![image](https://github.com/user-attachments/assets/fe3b43f9-7d74-4a0f-a612-7f800dcc6b5e)


echo $?
## OUTPUT 
![image](https://github.com/user-attachments/assets/07fb997d-57b9-4201-a3d5-c466fb1f0ed4)

./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 
![image](https://github.com/user-attachments/assets/bc53d96b-a277-4a4f-ac2b-7c7bd16a046c)

 
abcd
 
echo $?
 ## OUTPUT
 ![image](https://github.com/user-attachments/assets/bb33a88e-3cad-4c53-a6a9-5ae16d62d510)



 
# mis-using string comparisons

cat iftest.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
##OUTPUT

![image](https://github.com/user-attachments/assets/c091c490-a325-46af-8016-047380344265)



chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT


![Screenshot from 2025-04-23 10-39-47](https://github.com/user-attachments/assets/5a137624-6a1c-4cc2-b911-f975221c6f4f)




# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT
![image](https://github.com/user-attachments/assets/2d841f16-a64c-48c8-94a5-129c984caea5)


# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/e36564b6-2dd9-48b9-8406-63207e039053)




# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
##OUTPUT
![image](https://github.com/user-attachments/assets/40b42e2b-9550-4864-9c02-572cf321cfb7)



# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
##OUTPUT
![image](https://github.com/user-attachments/assets/51062189-a708-45cf-a1b6-e107d2b04763)


# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/61a99e4f-2c36-45ed-82e2-80e30967a0d7)


# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/20be0b8d-3887-4ce2-af16-62d8d875594a)


# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
 
 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
 
 
 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
 
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 
 
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 
 
cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh

## OUTPUT
![image](https://github.com/user-attachments/assets/5f69dcbf-e7bd-4497-bd66-8c9e0e45f575)

cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT
![image](https://github.com/user-attachments/assets/1ee8a32e-0a34-4345-bebd-e59826f24d0e)



cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT

![image](https://github.com/user-attachments/assets/f3af8671-9fea-4950-8b20-d3290d0f3d31)

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype1.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/c18d3607-401b-4872-aeab-e6e9d4fdf11e)


cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
 ## OUTPUT
 ![image](https://github.com/user-attachments/assets/d08bd87f-67ad-4f33-9dce-f6ca4f377739)


 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
## OUTPUT
![image](https://github.com/user-attachments/assets/a883ee8c-ab3c-4dff-bbc3-0872b02248bf)


$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
 ![image](https://github.com/user-attachments/assets/974932d9-8a3b-42d6-a08f-4d5994352ffc)

cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/361f7c89-adad-4bba-8065-dbebb8744189)



 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT
![image](https://github.com/user-attachments/assets/964fca92-28a7-40d0-9276-07e506bd6116)




$ ./exread1.sh 
 
cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
![image](https://github.com/user-attachments/assets/76ac9600-3091-40aa-aaa5-c411636d4fab)

 ./funcex.sh 

 
 ./funcex.sh 1 2

 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
![image](https://github.com/user-attachments/assets/541789b5-f367-44d5-bb5d-2bda2d2233df)

$ ./argshift.sh 1 2 3
 
 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh
## OUTPUT
![image](https://github.com/user-attachments/assets/c60de700-8950-4ea7-b105-4d859706473c)

$ ./argshift.sh 1 2 3
 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
![image](https://github.com/user-attachments/assets/690dd330-ce08-4c45-804f-c965bfd5057b)

 ./argshift.sh 1 2 3
 
 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
![image](https://github.com/user-attachments/assets/4496ba36-ac4e-450b-a42f-dd6da02ee88b)

 
cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 
![image](https://github.com/user-attachments/assets/9177d3e8-8eb5-4a4a-b837-3dd1c8c8ded2)



# RESULT:
The Commands are executed successfully.
