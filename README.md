> [!NOTE]
> This repo is about a set of commands which might be useful for coding.

<details>
<summary><h2><strong>tmux </strong></h2></summary>

tmux is useful when you have to utilize multiple terminals concurrently without termination.(i.e., efficient terminal usage!)

Multiple sessions can be created via tmux, and it results in more efficient terminal mangement than single one.

0. <strong>Prerequisite</strong>
```
sudo apt-get install tmux
```
1. <strong>Create a session</strong>
```
tmux new -s <sessions_name>
```
2. <strong>Print out information on session</strong>

Information includes in session name, the number of windows, and current attached session
```
tmux ls
```
3. <strong>Enter a session</strong>
```
tmux attach -t <session_name>
```
4. <strong>Detach from a session</strong>

If using this command, you need to the former and the latter separately not concurrently(i.e., 1) ctrl+b, 2) d
```
ctrl+b -> d
```
5. <strong>Create a new window</strong>
```
ctrl+b -> c
```

</details>

<details>
<summary><h2><strong>Multi-gpu</strong></h2></summary>

1. <strong>Check current storage capacity</strong>
```
df -h
```
2. <strong>print current working directory</strong>
```
pwd
```
3. <strong>Check your CUDA version</strong>
```
nvcc -V
```
4. <strong>Output current directory's capacity</strong>
```
du -sh .
```
5. <strong>Check all running processes' id and command</strong>
```
nvidia-smi | grep python | awk '{print $5}' | xargs -I{} ps -p {} -o pid,cmd
```
6. <strong>Print list of currently running prcoesses on background</strong>
```
jobs
```
7. <strong>Monitor resource usage and running processs</strong>
```
top
```
8. <strong>Similar to top, but better in terms of visualization</strong>
```
nvtop # recommended
htop
```
</details>

<details>
<summary><h2><strong>Conda</strong></h2></summary>
<strong>1. Install pytorch library with cuda</strong>

You might as well check whether cuda version is aligned with pytorch one.

```
conda install pytorch=='your version' torchvision=='version' torchaudio=='version' pytorch-cuda='cuda-version' -c pytorch -c nvidia
```
You can refer to the following regarding to the version; [Pytorch previous version](https://pytorch.org/get-started/previous-versions/)

<strong>2. Check whether to be ready for running GPU or installed cuda on your OS </strong>
```
cuda_is_available() module in pytorch
```
<strong>3. List of conda virtual environments</strong>
```
conda env list
```
<strong>4. Create conda virtual environment python version is specified</strong>
```
conda create -n (env name) python='version'
```
<strong>5. Remove your conda virtual environment</strong>
```
conda env remove --name (env name) --all
```
<strong>6. Activate/Deactivate conda virtual environment</strong>
```
conda activate/deactivate
```
<strong>7. Create a new conda environment with old library</strong>
```
conda create --name <new_name> --clone <old_env_name>
e.g., conda create --name new_nev --clone llara
```
<strong>8. Create current environment.yml</strong>
```
conda env export > environment.yml
```
</details>

<details>
<summary><h2><strong>VS Code</strong></h2></summary>

<strong>1. Cwd path setting</strong>
```
ctrl+shift+p
```
<strong>2. KeyInterrupt during code execution</strong>
```
ctrl+c
```
or you can insert process termination call(i.e., exit()) into your code snippet 
```
exit()
```
</details>

<details>
<summary><h2><strong>Unzip</strong></h2></summary>

<strong>Unzip your file in specified directory</strong>
```
# -q: quiet mode, -qq: without any output
unzip file_name.zip -d /path/to/directory
unzip -qq (your zip file name)
```

<strong>Download files stored in google drive</strong>
```
pip install gdown
gdown --fuzzy (google drive link)
```

<strong>Alternative to the above</strong>
```
wget <your_url>
```

```
file_name.zip -d /path/to/directory
```

<strong>tar file</strong>
```
tar -xvzf file_name.tar.gz

tar -xvzf fine_name.tar.gz -C path/to/destination/
```
</details>

<details>
<summary><h2><strong>Git</strong></h2></summary>
  
<strong>1. Print all branches</strong>
```
git branch
```

<strong>2. move other branch</strong>
```
git checkout <branch_name>
```

<strong>3. Create a branch and move to it</strong>
```
git checkout -b <branch_name>
```

<strong>4. Setting user name and email</strong>
```
git config user.name "Your Name"
git config user.email "you@example.com"
```

<strong>5. Check git's global setting</strong>
```
git config --global --list
```

<strong>6. Print commit logs</strong>
```
git log
```

<strong>7. Clone not all but certain directories for big size repository(you can test it via [transformers](https://github.com/huggingface/transformers))</strong>
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
git sparse-checkout set dir1 dir2 ...
```
```
git checkout main
```

<strong>8. Git lfs installation</strong>

You can download [the specific version of lfs](https://github.com/git-lfs/git-lfs/releases) depending on your OS if you are not a root manager.
```
$ tar -xvzf <git-fls-tar.gz file_name>
$ cd <generated_tar.gz file_name>
 
$ ./install.sh

# You can check whether to succeed to install git lfs via the below command.
$ git lfs install
```
</details>

<details>
<summary><h2><strong>pip</strong></h2></summary>

<strong>1. Itemize installed libraries</strong>
```
pip freeze > requirements.txt
```

<strong>2. Check Pytorch and flash-attention version</strong>
```
python -c "import torch; print(torch.__version__)"
python -c "import flash_attn; print(flash_attn.__version__)"
```

```
pip install flash-attn --no-build-isolation # prevent from the dependency problem.
pip install flash-attn --no-cache-dir # don't refer to cache for possible mismatch library.
```
</details>

<details>
  <summary><h2><strong>csv, xlsx extension</strong></h2></summary>
If you change the file which extension is csv, then you might as well save xlsx extension to ensure that changes are applied in terms of visualization.
(csv 파일의 세팅을 변경했다면, 시각화 측면에서 변경사항이 반영되도록 xlsx 확장자로 저장하는 게 낫다.)
</details>

<details>
<summary><h2><strong>Linux</strong></h2></summary>

<strong>1. Open file</strong>
```
vi file-name
```
<strong>2. Access via insert mode</strong>
```
i
```

When you press ESC, then linux will be changed to command mode.

<h3><strong>3.Save</strong></h3>

<strong>3-1. Save changes and exit</strong>
```
:wq
```
<strong>3-2. Save changes without exit</strong>
```
:w
```
<strong>3-3. Exit without saving</strong>
```
:qa!
```

<h3><strong>4. Delete</strong></h3>

<strong>4-1. Delete one character</strong>
```
x
```
<strong>4-2. Delete a word</strong>
```
dw
```
<strong>4-3. Delete a line after cursor</strong>
```
d$
```
<strong>4-4. Create an empty file which called in file-name</strong>
```
touch
```
<strong>5. Output result or log</strong>
```
filename > result.txt
```
<strong>6. Check owner, group, and others permission on [r]ead, [w]rite, and e[x]ecution</strong>
```
ls -l (file_name)
```
<strong>7. Modify the file called in file-name. Before executing this command, you might as well check your permission on read, write, and execution.</strong>
```
vi (file-name)
```
Although you chanage your file's mode via chmod command, it cannot be changed because of parent directory's permission. Therefore, you could check the upper directory's permission.

<strong>8. printk is used in kernel mode instead of printf</strong>
```
printk
```
<strong>9. Copy target file</strong>
```
cp <target-file> <target-directory>
```
<strong>10. Clear kernel log</strong>
```
dmesg -C
```
<strong>11. Transfer file or directory of virtualbox(guestOS) to local computer(HostOS)</strong>
```
$scp -r source-path HostOS's username@host_ip:destination-path
e.g., scp -r /hw js@192.x.x.x:/Users/JS/Desktop/
```
<strong>(Recommended) 12. Another methods of 11.</strong>
```
$ssh serverA_username@ip # access serverA via ssh
$sftp -P port_num serverB_username@ip # Access serverA to serverB via sftp
```
<strong>13. Log last access time, modified time and last change mode time</strong>
```
stat file-name
```
<strong>14. remove contents in file but preserve file itself</strong>
```
> file-name
```
</details>
