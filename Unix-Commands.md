# Chapter 1	Accessing the command line 

1.	date    -    See the date
Sat Sep  8 16:34:48 IST 2018

2.	date "+DATE: %Y-%m-%d%nTIME: %H:%M:%S"
DATE: 2018-09-08
TIME: 16:36:40

3.	create a file with vi and save it with  escape - > :wq -> enter
4.	head -n 3 filename // by default first 10 lines but with -n = first three lines
5.	tail -n 3 filename // by default last 10 lines but with -n = last three lines
6.	wc -l filename – total lines in a file. 
7.	wc -w filename – total words in a  file.
8.	wc -c filename – total characters in a file.
9.	Press tab to quickly complete the filenames or commands.
10.	ls -ltr = down all files 
11.	history – previously executed commands and command number.
12.	Ctrl + a = Jump to the beginning of the command line
13.	Ctrl + e = jump to the end of the command line
14.	Ctrl + u = clear from the cursor to the beginning of the command line.
15.	Ctrl + k = clear to the cursor to the end of the command line.
16.	Ctrl + left arrow = Jump to the beginning of the previous word on the command line.
17.	Ctrl + right arrow = Jump to the beginning of the word on the command line.
18.	History
19.	!<Command line no>

# Chapter 2 	Managing files from the command line

File system in unix.
Root – parent folder of all unix files and folders. 
Under root, below given libraries are present.

/usr – Installed software shared libraries includes files and static read only program data
	/usr/bin – user commands
	/usr/sbin – system administration commands
	/usr/local – locally customized software.
/etc = Config files specific to the system.
/var = variable data specific to this system that should persist between boots. Files that dynamically change may be found under /var. – DB , CACHE , Log etc.
/run = Runtime data for processors started since the last boot. This includes process ID files and lock files, among other  things.
/home = Home directories where regular users store their personal data and configuration files.
/root – home directory where regular users store their personal data and config files.
/tmp – A world – writable space for temporary files. 
/boot – files needed in order to start the boot process.
/dev – contain special devices files which are used by the system to access hardware.


Path - Path of a file or directory specifies its unique file system location.

Absolute path – Fully qualified name beginning at the root directory and specifying each sub directory traversed to reach and uniquely represent a file.

Relative path – It identifies a unique file specifying only the path necessary to reach the file from the working directory. 

pwd – Present working directory.
ls – shows all files in current working directory.
Mkdir – create the directory
Cd – change the directory.
Touch – update the timestamp of the file with current data and time.
Ls – 
-I  = long listing format
-a = hidden files
-r = recursively shows all files unders its directories and subdirectories .

Ls .  = refers to current working directory.
Ls ..  = refers to parent directory.

mkdir -p my/my1/my2 – create directory -> my -> my1 -> my2.
Cp file1 file2
Cp -r dire1 dire2
Mv  file1 file2
Rm -r 
Rm -l
Rm -f

File creation & displaying all files

touch aira bravo charlie delta echo able baker cast dog easy
ls a*
ls *a*
ls [ac]*
ls ???
ls ????
ls ~/a
ls ~/a*
ls ?????

Tilde Expression – The tilde character (~) when followed by a slash delimiter , match the current user’s home directory.

ls ~/glob
pwd
ls ~/glob
ls ~/my/

Braces expansion –  It is used to generate discretionary strings of characters. 

echo {Sunday,Monday,Tuesday,Wednesday} .log
echo {Sunday,Monday,Tuesday,Wednesday}.log
echo {1..3}.txt
echo file{1..3}.txt
echo file{a..c}{1..3}.txt
history

Command Substitution – Command substitution allows the output of a command to replace the command itself.

$(command)
`command`

echo The time is `date +%A`
echo The time is $(date +%A)

echo $(hostname -s) 

# Chapter 3 
	
su - 

-> If currently working as a non-root user , switch to root.



# Chapter 4   Creating , viewing and editing text files.

A running program or process needs to read input from somewhere and write output to the screen or to files.

stdin - read
stdout - write
stderr - write
fielname  - read and write

### Redirecting output 
I/O replication replaces the default channel designations with file name representing either output files or devices.

> file   redirect stdout to overwrite a file  and stderr - 
>> file redirectstdout to append to a file.
2>file redirect stderr to overwrite a file .
2>/dev/null - discard stderr messages by redirecting /dev/null.

>file 2>&1 - redirect stdout and stderr to overwrite the same file.
&>file - same

>>file 2>&1 - redirect stdout and stderr to append the same file.
&>>file - same


date > filename

tail -n 100 filename1 > filename2 

cat file1 file2 file3 > file4

ls -a > file5

echo "I am writing into the file" >> file1
diff prefile currfile >> newfile

find /etc -name passwd > file1 2>/dev/null

find /etc -name passwd &> /tmp/save-both

find /etc -name passwd >> file1 2>&1 

### constructing pipeline
a pipeline is a sequence of one or more commands sepreated by |.
output to one is input of another.

ls -a 

 0 process 1 --------tee ------------ 0  process 1
           2   	      |			    	 2
	    	   file or 
		   terminal



# Files 

## file owner ,  permissions 

Every process on the system runs as a particular user. Every file is owned by a particular user. Access of files are restricted by a user  


ls - l - List of all files
ps -a , ps -u - process related info.


su - Switching between users.

sudo - allow a normal user to be permitted to run a command as a root or any other user based on /et/sudoers files.

visudo - edit the sudoers file

useradd - add the user
usermod - used to modify an user
userdel - remove the user

Access to files by users are controlled by file permissions.
Files have three categories of user to which permissions apply.

1. File is owned by a user the one who created it.
2. File is also own a single group

permissions of the file
 
1. r  read = contents of the file can be read
2. w  write = content of the file can be changed.
3. x  execute =  file can be executed as command

viewing file/ permission and ownership

ls -l filename 


## change file / directory permissions

 chmod who what which file|directory

who - u = user , g = group , o = other , a = all.
what - + = add , - = remove , = > replace the permission
which - r , w , x

chmod ### file|directory


 hash - sum => r =4 , w =2 x=1

eg

chmod go-rw file1

chmod a+x file2

chmod 750 sampledir

for directory

chmod -R g+rwx dir`


## change the file directory user or group ownership

chown user filename

eg
file
chown student foofile

directory
chown -R student foodir





# Process

Running instance of a launched executable program. It consists of 
• an address space of allocated memory.
• security properties including ownership credentials and privileges.
• one or more execution threads of program code.
• process state

The environment of a process.

local and global variable
current scheduling context.
allocated system resources such as file desciptors and network ports

an existing parent process dulicates its own address space (fork) to create a new child process structure. Every new process is assigned a unique process ID (PID) for tracking and secuirty.
pid and parent process pid - element of new process env.
all process are descendants of the first system process , which is systemd (1) .

States 

R - task_running
S - Task Interruptible 
D - Task_Uninterruptible
K - Task Killable
T - Task stopped 
T - Task tracced
Z - Zommbie
X - Dead


ps aux

ps lax

ps -ef


