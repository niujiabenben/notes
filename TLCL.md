# The Linux Command Line

Fifth Internet Edition: http://linuxcommand.org/tlcl.php

## shell 中的特殊字符

|   符号   |                 含义                 |         示例          |
|:--------:|:------------------------------------:|:---------------------:|
|    *     |  match any characters in a filename  |        echo *         |
|    ~     |            home directory            |     echo ~chenli      |
|  $(())   |         Arithmetic expansion         |      $((2 + 2))       |
|    {}    |   逗号隔开的可选项; 数字或字母范围   |  Front-{A,B,C}-Back   |
|    []    |     候选列表, 只匹配一个, 不展开     |     [abc]*, [1-9]     |
|   ${}    |         Parameter Expansion          |        ${USER}        |
|   $()    |         Command Substitution         |    $(which emacs)     |
|    ""    | 去掉除$, \\, `之外所有特殊字符的含义 | ls -l "two words.txt" |
|    ''    |        去掉所有特殊字符的含义        |   echo '$((2 + 2))'   |
| &> / &>> |        stdout & stderr 重定向        |    ls &> hello.txt    |

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

4. Wildcards:
   1. `[[:alnum:]]` : Matches any alphanumeric character
   2. `[[:alpha:]]` : Matches any alphabetic character
   3. `[[:digit:]]` : Matches any numeral, equal to [0-9]
   4. `[[:lower:]]` : Matches any lowercase letter, equal to [a-z]
   5. `[[:upper:]]` : Matches any uppercase letter, equal to [A-Z]
   6. `*[[:lower:]123]` : Any file ending with a lowercase letter or the
      numerals “1”, “2”, or “3”

##  two types of shell sessions

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

## shell常用命令

sort命令:

| short option |      long option       |   description    |
|:------------:|:----------------------:|:----------------:|
|      -f      |     --ignore-case      |    忽略大小写    |
|      -n      |     --numeric-sort     | 用数字的方式排序 |
|      -r      |       --reverse        |    按降序排序    |
|      -k      | --key=field1[,field2]  |    按字段排序    |
|      -t      | --field-separator=char |  设置字段分隔符  |

uniq命令:

| short option |   long option   |      description       |
|:------------:|:---------------:|:----------------------:|
|      -c      |     --count     | 输出一行重复出现的次数 |
|      -d      |   --repeated    |     只输出重复的行     |
|      -f      | --skip-fields=n |     忽略前n个字段      |
|      -s      | --skip-chars=n  |     忽略前n个字符      |
|      -u      |    --unique     |    只输出不重复的行    |

cut命令:

| short option |    long option    |   description    |
|:------------:|:-----------------:|:----------------:|
|      -c      | --characters=list | 以字符的形式抽取 |
|      -f      |   --fields=list   | 以字段的形式抽取 |
|      -d      | --delimeter=delim |    字段分隔符    |
|              |   --complement    |       反选       |

## Here Documents

A here document is an additional form of I/O redirection in which we embed a
body of text into our script and feed it into the standard input of a command.
It works like this:

```shell
# command << token
# text
# token
###################
cat << __EOF__
hello world.
__EOF__
```

## flow control

shell脚本中, `[]`为最常用的条件判断语法, `[[]]`为`[]`的加强版, 支持正则表达式,
`(())`则支持数学运算. 有关各种条件判断语法极为复杂, 用的时候需要随时查.

shell中循环支持`break`和`continue`.

```shell
### while loop, 其中, condition是一个条件判断语句
while condition; do
    command
done

### for loop, words是一个list.
for variable in words; do
    commands
done

### or c-like format, expression*为数学表达式
for (( expression1; expression2; expression3 )); do
    commands
done

### 示例, 支持shell expansion
for i in A B C D; do echo $i; done
# for支持shell expansion
for i in {A..D}; do echo $i; done
for i in distros*.txt; do echo "$i"; done
# 读取所有命令行参数
for i in $@; do echo $i; done
# 类c格式
for ((i=0; i<5; i=i+1)); do echo $i; done

###  case示例
case $1 in
    -h | --help)    echo "Show this help message and exit." ;;
    -v | --version) echo "v 1.0.0" ;;
    * )             echo "unknwon argument: $1" ;;
esac
```

## shell中的list

```shell
### initialize array
for i in {0..23}; do hours[i]=0; done
### initialize array
animals=("a dog" "a cat" "a fish")
### access elements
for i in "${animals[@]}"; do echo $i; done
### number of array elements
echo ${#animals[@]}
### expand an array
animals+=(d e f)
```

## other tips

* 在写shell脚本时, 如果有命令参数含有变量, 最好是用引号将变量包起来, 这样避免变量为空
  的时候命令报参数错误, 如: `if [ -f "$FILE" ]; then echo "$FILE exists"; fi`

* Reading Files with Loops:
  * `while read line; do echo $line; done < file.txt`
  * `cat file.txt | while read line; do echo $line; done`

* 特殊shell变量:
  * `$?` : 上一个函数/命令的返回结果
  * `$#` : 传入参数的个数
  * `$@` 或者 `$*` : 传入的所有参数, 两者在有引号的时候有所不同.

* Parameter Expansion:
  * `${param:-word}` : param为空时, 返回word, 否则返回param
  * `${param:=word}` : param为空时, 返回word, 否则返回param, 并给param赋值为word
  * `${param:?word}` : param为空时, 程序退出, 并将word输出至stderr, 否则返回param
  * `${#param}`      : 返回param的长度, `${#@}`或者`${#@}`返回参数的个数
  * `${param:offset:length}` : 截取字符串, length可省略, offset可为负数,
    以上两种情况含义与python相同.
  * `${param#pattern}`  : 从开头除去param中与pattern匹配的字符串, 执行最小匹配
  * `${param##pattern}` : 从开头除去param中与pattern匹配的字符串, 执行最大匹配
  * `${param%pattern}`  : 从末尾除去param中与pattern匹配的字符串, 执行最小匹配
  * `${param%%pattern}` : 从末尾除去param中与pattern匹配的字符串, 执行最大匹配
  * `${param/pattern/string}`  : 字符串替换, 替换第一个匹配
  * `${param//pattern/string}` : 字符串替换, 替换所有匹配
  * `${param/#pattern/string}` : 字符串替换, 替换开头匹配
  * `${param/%pattern/string}` : 字符串替换, 替换末尾匹配
