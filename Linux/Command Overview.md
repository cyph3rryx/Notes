→ man : shows you the documentation for any command after it 

```bash
man ls
```

→ ls : lists the contents of any directory

```bash
ls /home/user
```

→ touch : it is used to make a file but not open it

```bash
touch list.txt
```

→ cat: gives the output of the contents of a file to the terminal.

```bash
cat ryx.txt
```

→ grep: used to filter results of the file.

```bash
cat books.txt | grep Harry Potter
```

→ | : it  is called “pipe operator” and it is used for sending the output of the first command into the input of the next.

```bash
cat ryx.txt | httprobe
```

→ >> : this operator creates/”appends to” a file of the given name and write the output of the previous command into it

```bash
cat ryx.txt >> newryx.txt
```

→ > : this operator outputs to a file and will overwrite it instead of appending the information to the end of it

```bash
cat ryx.txt > ryx.txt
```

→ & : it runs the command after it without checking if the command before it is completed.

```bash
cat ryx.txt >> urls.txt & cat urls.txt
```

→ && : it executes the next command only and only if the command before it is completed without any errors. (better version of ‘&’)

```bash
sudo apt update && sudo apt upgrade
```

→ mv : it moves a file to a given location and it is the best way to rename a file in terminal

```bash
mv ryx.txt /home/user/nexus/gg.txt
```

→ cp : it is used to copy a file to a given location 

(same as mv)

```bash
cp ryx.txt /home/user/nexus/martin_garrix.txt
```

→ sudo : to run command as root

```bash
sudo cp ryx.txt ./ryx.txt
```

→ cut : this is a filer command and will cut information out with a given delimitor

```bash
cut -d "" -f 1
```

→ cd : change directories

```bash
cd /home/user/legos
```

→ sed : used to replace content in a file with content you want 

For example., if a file had the work full in it and you didn’t want to have to go through the whole file and change every full you would just do this

```bash
sed 's/notfull/full/' file.txt
```

→ awk:  awk is a programming language that runs inside of bash and most Linux distros its amazing to learn and we will dig into it throughout this session

```bash
awk 'program' input-file
```
