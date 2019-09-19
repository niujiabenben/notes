# The Linux Command Line

Fifth Internet Edition: http://linuxcommand.org/tlcl.php

### Redirection



### shell 中的特殊字符

| 符号  |                 含义                 |         示例          |
|:-----:|:------------------------------------:|:---------------------:|
|   *   |  match any characters in a filename  |        echo *         |
|   ~   |            home directory            |     echo ~chenli      |
| $(()) |         Arithmetic expansion         |      $((2 + 2))       |
|  {}   |   逗号隔开的可选项; 数字或字母范围   |  Front-{A,B,C}-Back   |
|  ${}  |         Parameter Expansion          |        ${USER}        |
|  $()  |         Command Substitution         |    $(which emacs)     |
|  ""   | 去掉除$, \\, `之外所有特殊字符的含义 | ls -l "two words.txt" |
|  ''   |        去掉所有特殊字符的含义        |   echo '$((2 + 2))'   |

其他:

1. 空格, tab, 换行符被认为是shell命令参数的分隔符. ""中这些字符就是其本身.
   *  `echo $(cat README.txt)`   输出一行
   *  `echo "$(cat README.txt)"` 输出多行

2. Brace Expansion的其他示例:
   * `Number_{1..5}` :  展开成: Number_1 Number_2 ...
   * `echo {001..15}` : 展开成: 001 002 003 ...
   * `echo {Z..A}` :    展开成: Z Y X W V U ...

3. 双引号中可执行的操作有: , ,
   1. Arithmetic expansion : `echo "$((2 + 2))"`
   2. Parameter Expansion :  `echo "$USER"`
   3. Command Substitution : `echo $(cal)`

###  two types of shell sessions

1. **login shell session**: A login shell session is one in which we are prompted for
   our username and password. This happens when we start a virtual console session,
   for example. 本地配置文件包括:
   1. /etc/profile
   2. ~/.bash_profile
   3. ~/.bash_login
   4. ~/.profile

2. **non-login shell session**: A non-login shell session typically occurs when we
   launch a terminal session in the GUI.  本地配置文件包括:
   1. /etc/bash.bashrc
   2. ~/.bashrc
   3. environment inherited from their parent process, usually a login shell
