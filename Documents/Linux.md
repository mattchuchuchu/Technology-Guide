

# Linux

# Linux Directory

- root
  - bin
  - boot
  - dev
  - etc
    - fstab
    - hd
    - ...
    - hosts
  - home
    - .directory
    - dh
  - lib
  - lost+found
  - mnt
  - opt
  - proc
  - root
  - sbin
  - tmp
  - usr
  - var

常见目录说明：

/bin： 存放二进制可执行文件(ls、cat、mkdir 等)，常用命令一般都在这里；<br/>
/etc： 存放系统管理和配置文件；<br/>
/home： 存放所有用户文件的根目录，是用户主目录的基点，比如用户 user 的主目录就是/home/user，可以用~user 表示；<br/>
/usr ： 用于存放系统应用程序；<br/>
/opt： 额外安装的可选应用程序包所放置的位置。一般情况下，我们可以把 tomcat 等都安装到这里；<br/>
/proc： 虚拟文件系统目录，是系统内存的映射。可直接访问这个目录来获取系统信息；<br/>
/root： 超级用户（系统管理员）的主目录（特权阶级o）；<br/>
/sbin: 存放二进制可执行文件，只有 root 才能访问。这里存放的是系统管理员使用的系统级别的管理命令和程序。如 ifconfig 等；<br/>
/dev： 用于存放设备文件；<br/>
/mnt： 系统管理员安装临时文件系统的安装点，系统提供这个目录是让用户临时挂载其他的文件系统；<br/>
/boot： 存放用于系统引导时使用的各种文件；<br/>
/lib ： 存放着和系统运行相关的库文件 ；<br/>
/tmp： 用于存放各种临时文件，是公用的临时文件存储点；<br/>
/var： 用于存放运行时需要改变数据的文件，也是某些大文件的溢出区，比方说各种服务的日志文件（系统启动日志等。）等；<br/>
/lost+found： 这个目录平时是空的，系统非正常关机而留下“无家可归”的文件（windows 下叫什么.chk）就在这里<br/>

# Linux Command

## FILE Command
https://www.cnblogs.com/xzsj/archive/2020/11/18/Linux-OS.html

### DIRECTORY SWITCH
1. *Switch to user folder in current directory*<br/>
`cd user`<br/>
2. *Switch to upper level*<br/>
`cd..` or `cd../`<br/>
3. *Switch to root level*<br/>
`cd /`<br/>
4. *Switch to user main directory*<br/>
`cd ~`<br/>
5. *Switch to previous operated directory*<br/>
`cd -`<br/>

### DIRECTORY OPERATE
1. *Add directory*<br/>
`mkdir directory`<br/>
2. *Check directory details*<br/>
`ls or ll`<br/>
3. *Find directory*<br/>
`find [directory] [parameter]`<br/>
`find .`: list all the files/folders in current directory and all the sub directories.<br/>
`find /home -name "*.txt"`: find all the txt files in home folder<br/>
`find /home -iname "*.txt"`: ignore case<br/>
`find . \(-name "*.txt" -o -name "*.pdf")` or `find . -name "*.txt" -o -name "*.pdf"`: find txt and pdf files in current and sub directory.<br/>

4. *Modify directory name*<br/>
`mv dir newdir`<br/>
5. *Move directory location： Cut*<br/>
`mv dir newlocation`<br/>
6. *Copy directory*<br/>
`cp -r dir location`: r represents recursivly copy.<br/>
7. *Delete directory*<br/>
`rm[-rf] directory`<br/>

### FILE
1. *Create file*<br/>
`touch filename`<br/>
2. *Check file*<br/>
`cat/more/less/tail filename`<br/>
3. *Check file with monitoring file changes*<br/>
`tail -f catalina-2016-11-11.log`<br/>
4. *Modify file content*<br/>
`vim file`<br/>
*vim file -> open file -> command mode -> enter i to start edit mode -> edit file -> enter esc to start command mode -> input "wq / q!" to save or exit editing without saving.*<br/>
5. *Delete file*<br/>
`rm -rf filename`<br/>

### ZIP
Linux package file extension: .tar
Linux compress file extension: .gz
Linux zip (package + compress) file extension: .tar.gz

- z: invoke gzip compress commands to zip file
- c: package file
- v: show the progress
- f: name the file

- x: unzip file

1. *zip files in directory or zip directory*<br/>
`tar -zcvf test.tar.gz aaa.txt bbb.txt ccc.txt` or `tar -zcvf test.tar.gz /test/`<br/>
2. *unzip zipped file*
`tar -xvf test.tar.gz -C /usr`: -C define the unzip location

### SECURITY
Linux security include: readable, writable, excutable, map to owner/group/other

1. *check permission*
`ls -l`
-rwxrwxr--
```
[0]: means file type. 
d: directory
-: file
l: link (shortcut)
[1~3]: security for owner
[4~6]: security for group
[7~9]: security for other
r: readable, r could be replaced with 4.
w: writable, w could be replaced with 2.
x: executable, x could be replaced with 1.
```

| type | security | details |
| ---| ---- | ----- |
| file | r | can use cat to check file content |
| file | w | can edit file content |
| file | x | can execute the file as binary file |
| directory | r | can check directory list |
| directory | w | can create/delete files in the directory |
| directory | x | can use cd to enter the directory |

*Note: SuperAdmin will be an exception.*









