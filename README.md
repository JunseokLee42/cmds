## Multi-gpu

storage
```
$ df
```
print current working directory
```
$ pwd
```
Check your CUDA version
```
$ nvcc -V
```
Output directory's capacity
```
$ du -sh .
```
Check all running processes' id and command.
```
$ nvidia-smi | grep python | awk '{print $5}' | xargs -I{} ps -p {} -o pid,cmd
```

```
$ tail -f output.log
```

```
$ jobs
```

```
$ top
```

```
$ htop
```

## conda
```
conda install pytorch=='your version' torchvision=='version' torchaudio=='version' pytorch-cuda='cuda-version' -c pytorch -c nvidia
```

```
cuda_is_available() module in pytorch
```

```
conda env list
```

```
conda create -n (env name)
```

```
conda env remove --name (env name) --all
```

```
conda activate/deactivate
```

## vs code
**1. Cwd path setting**
```
ctrl+shift+p
```

**2. KeyInterrupt during code execution**
```
ctrl+c
```

## zip file

-q: quiet mode, -qq: without any output
```
unzip -qq (your zip file name)
```

for files stored in google drive
```
pip install gdown
gdown --fuzzy (google drive link)
```

```
wget <your_url>
```

```
curl -0 <your_url>
```

```
file_name.zip -d /path/to/directory
```

## Git
print all branches
```
git branch
```

move other branch
```
git checkout <branch_name>
```

create a branch and move to it
```
git checkout -b <branch_name>
```

```
# How to set user name and email
git config user.name "Your Name"
git config user.email "you@example.com"
```

```
git config --global --list
```

```
git log # print commit logs
```

clone not all but certain directories (you can test it via huggingface/transformers repository)
```
git clone --no-checkout <repo_url>
```
```
cd repo_dir
```
```
git sparse-checkout init --cone
```
```
git sparse-checkout set dir1 dir2 ..
```
```
git checkout main
```

## pip
```
pip freeze > requirements.txt
```

## csv, xlsx extension
If you change the file which extension is csv, then you might as well save xlsx extension to ensure that changes are applied in terms of visualization.
(csv 파일의 세팅을 변경했다면, 시각화 측면에서 변경사항이 반영되도록 xlsx 확장자로 저장하는 게 낫다.)

## linux
Open file
```
vi file-name
```

insert mode
```
i
```

When you press ESC, then linux will be changed to command mode.

Save
1) save changes and exit
```
:wq
```

2) save changes without exit
```
:w
```

3) exit without saving
```
:qa!
```

Delete
1) delete one character
```
x
```

2) delete a word
```
dw
```

3) delete a line after cursor
```
d$
```

create an empty file which called in file-name
```
touch
```

output result or log
```
filename > result.txt
```

check owner, group, and others permission on [r]ead, [w]rite, and e[x]ecution
```
ls -l (file_name)
```

modify the file called in file-name. Before executing this command, you might as well check your permission on read, write, and execution.
```
vi (file-name)
```
Although you chanage your file's mode via chmod command, it cannot be changed because of parent directory's permission. Therefore, you could check the upper directory's permission.

print function - printk is used in kernel mode instead of printf.
```
printk
```

copy file
```
cp <target-file> <target-directory>
```

clear kernel log
```
dmesg -C
```

transfer file or directory of virtualbox(guestOS) to local computer(HostOS)
```
$scp -r source-path HostOS's username@host_ip:destination-path
```
ex. scp -r /hw js@192.x.x.x:/Users/JS/Desktop/

log last access time, modified time and last change mode time
```
stat file-name
```

# Reference
[Github Docs](https://docs.github.com/ko/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)
