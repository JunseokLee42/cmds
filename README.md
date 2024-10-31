## Multi-gpu

```
nohup
```

```
tail -f output.log
```

```
jobs
```

```
top
```

```
htop
```
storage
```
df
```
Current working directory
```
pwd
```
Check your CUDA version
```
nvcc -V
```
Output directory's capacity
```
du -sh .
```
Check all running processes' id and command.
```
nvidia-smi | grep python | awk '{print $5}' | xargs -I{} ps -p {} -o pid,cmd
```

## conda
1. conda install pytorch=='your version' torchvision=='version' torchaudio=='version' pytorch-cuda='cuda-version' -c pytorch -c nvidia
2. cuda_is_available() module in pytorch
3. conda env list
4. conda create -n (your env name)
5. conda env remove --name (your env name) --all
6. conda activate/deactivate

## vs code
13. ctrl+shift+p -> Cwd path setting
14. Ctrl+c: Occur KeyInterrupt during code execution.

## zip file
1. unzip -qq (your zip file name) # -q: quiet mode, -qq: without any output
2. gdown --fuzzy (drive link) # for files stored in google drive
3. wget <your_url>
4. curl -0 <your_url>
5. unzip file_name.zip -d /path/to/directory

## Git
1. git branch # print all branches
2. git checkout <branch_name> # move other branch
3. git checkout -b <branch_name> # create a branch and move to it

4. How to set username and email
1) git config user.name "Your Name"
2) git config user.email "you@example.com"

5. git config (--global) --list # () means that it is optional
6. git log # print commit logs

7. clone not all but certain directories (you can test it via huggingface/transformers repository)
1) git clone --no-checkout <repo_url>
2) cd repo_directory
3) git sparse-checkout init --cone
4) git sparse-checkout set directory1 directory2 ..
5) git checkout main

## pip
1. pip freeze > requirements.txt

## csv, xlsx extension
If you change the file which extension is csv, then you might as well save xlsx extension to ensure that changes are applied in terms of visualization.
(csv 파일의 세팅을 변경했다면, 시각화 측면에서 변경사항이 반영되도록 xlsx 확장자로 저장하는 게 낫다.)

## linux
1. vi file-name # open file
2. i # insert mode
3. When you press ESC, then linux is changed to command mode
4. Save
4-1) :wq # save changes and exit
4-2) :w # save changes without exit
4-3) :qa! # exit without saving
5. Delete
5-1) x # delete one character
5-2) dw # delete a word
5-3) d$ # delete a line after cursor
6. touch (file-name) # create an empty file which called in file-name
6-1) filename > result.txt # output result or log
7. ls -l (file_name) # check owner, group, and others permission on [r]ead, [w]rite, and e[x]ecution
8. vi (file-name) # modify the file called in file-name. Before executing this command, you might as well check your permission on read, write, and execution via number 7 cmd
9. Although you chanage your file's mode via chmod command, it cannot be changed because of parent directory's permission. Therefore, you could check the upper directory's permission.
10. print function
- printf isn't used in kernel mode, instead printk is done.
11. copy file
cp <target-file> <target-directory>
12. dmesg -C # clear kernel log
13. $scp -r source-path HostOS's username@host_ip:destination-path # transfer file or directory of virtualbox(guestOS) to local computer(HostOS)
ex. scp -r /hw js@192.x.x.x:/Users/JS/Desktop/
14. stat file-name # log last access time, modified time and last change mode time

# Reference
[Github Docs](https://docs.github.com/ko/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)
