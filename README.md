# linux

명령어 - 명렁어에 대한 간단한 설명


1. 파일 시스템 탐색 기본 명령어

1) pwd - "print working diretory"의 준말로, 컴퓨터의 명령 줄 인터페이스ㅔㅇ서 현재 작업중인 디렉터리의 이름을 출력

$ pwd

 [vagrant@host1 ~]$ pwd
/home/vagrant

2) cd - "change directory"의 준말로, 현재의 작업 디렉터리의 위치를 바꾸는 명령 줄이다.

$ cd vagrant 

[vagrant@host1 home]$ cd vagrant
[vagrant@host1 ~]$

3) ls - "list segments"의 약자이며, 파일의 목록을 표시하는 기능을 수행하는 명령어이다. 도스에서의 dir과 유사한 명령어이다.

$ ls

[vagrant@host1 ~]$ ls
git

4) file - file 명령어는 유닉스와 유닉스 계열 운영 체제의 표준 프로그램이며 컴퓨터 파일에 포함된 데이터의 유형을 파악하기 위해 사용된다.

$ file b.txt

[vagrant@host1 bitcamp-ncp]$ file b.txt
b.txt: ASCII text

5) less - Less는 파일 또는 명령 출력의 내용을 한 번에 한 페이지씩 표시하는 명령줄 유틸리티입니다.
           more와 비슷하지만 고급 기능이 있어 파일을 앞뒤로 탐색할 수 있습니다.

$ less -N c.txt

[vagrant@host1 bitcamp-ncp]$ less -N c.txt

  1 1111
c.txt (END)


2. 파일과 디렉토리 조작 명령어

1) cp -  파일, 디렉토리를 복사합니다. 이런 복사 작업은 데이터를 백업할 때 유용하게 사용됩니다.

$ cp c.txt d.txt

[vagrant@host1 bitcamp-ncp]$ cp c.txt d.txt
[vagrant@host1 bitcamp-ncp]$ ls
 c.txt  d.txt 

2) mv - mv 명령을 이용하여 파일 이동(move)을 할 수 있습니다. 같은 폴더에서 파일, 디렉토리 이동을 하는 경우 이름변경 효과가 있습니다.

$ mv c.txt d1/

[vagrant@host1 bitcamp-ncp]$ mv c.txt d1/
[vagrant@host1 bitcamp-ncp]$ cd d1
[vagrant@host1 d1]$ ls
c.txt


3) mkdir - mkdir의 뜻은 make directory의 약자로 디렉토리(폴더)를 생성할 때 사용하는 명령어입니다.

$ mkdir d1

[vagrant@host1 bitcamp-ncp]$ mkdir d1
[vagrant@host1 bitcamp-ncp]$ ls
d1


4) rm - m 명령은 디렉토리에서 지정된 File 매개변수의 항목을 제거합니다. 

$ rm x.txt

[vagrant@host1 bitcamp-ncp]$ rm x.txt
[vagrant@host1 bitcamp-ncp]$ ls
b.txt  c.txt

5) ln - ln은 Link 의 약어로서 리눅스 파일시스템에서 링크파일을 만드는 명령어이다. 리눅스에서는 심볼릭링크와 하드링크의 두가지 링크 파일이 존재한다.

$ ln -s test link_test

[vagrant@host1 bitcamp-ncp]$ ln -s test link_test
lrwxrwxrwx. 1 vagrant vagrant    4 Nov 21 20:18 link_test -> test


3. 명령어를 다루는 명령어

1) type - type 명령은 명령 유형에 대한 정보를 표시하는 데 사용됩니다. 명령줄에 입력한 경우 지정된 명령을 해석하는 방법이 표시됩니다.

$ type cp

[vagrant@host1 bitcamp-ncp]$ type cp

cp is hashed (/usr/bin/cp)


2) which - which는 특정명령어의 위치를 찾아주는 명령어이다.

$ which find

[vagrant@host1 bitcamp-ncp]$ which find
/usr/bin/find

3) man - man 명령어(유틸리티)를 사용하여 각종 명령어, 프로그램의 사용법(매뉴얼)을 확인한다.

$ man rm

RM(1)                                               User Commands                                               RM(1)

NAME
       rm - remove files or directories

SYNOPSIS
       rm [OPTION]... FILE...

DESCRIPTION
       This  manual  page  documents the GNU version of rm.  rm removes each specified file.  By default, it does not
       remove directories.

       If the -I or --interactive=once option is given, and there are more  than  three  files  or  the  -r,  -R,  or
       --recursive  are  given,  then  rm  prompts the user for whether to proceed with the entire operation.  If the
       response is not affirmative, the entire command is aborted.

       Otherwise, if a file is unwritable, standard input is a terminal, and the -f or --force option is  not  given,
       or the -i or --interactive=always option is given, rm prompts the user for whether to remove the file.  If the
       response is not affirmative, the file is skipped.

OPTIONS
       Remove (unlink) the FILE(s).

       -f, --force
              ignore nonexistent files and arguments, never prompt

       -i     prompt before every removal

       -I     prompt once before removing more than three files, or when removing recursively;  less  intrusive  than

4) apropos - 검색어와 관련있는 명령어를 설명과 함께 출력한다.

$ apropos bin

[vagrant@host1 bitcamp-ncp]$ apropos bin
slabinfo (5)         - kernel slab allocator statistics
bind (1)             - bash built-in commands, see bash(1)
bind (2)             - bind a name to a socket
bind (3p)            - bind a name to a socket
bindresvport (3)     - bind a socket to a privileged IP port
binfmt.d (5)         - Configure additional binary formats for executables at boot
bsearch (3)          - binary search of a sorted array
bsearch (3p)         - binary search a sorted table
combinedeltarpm (8)  - combine multiple deltarpms to a single one
ctrlaltdel (8)       - set the function of the Ctrl-Alt-Del combination

5) info - 리눅스 명령어의 사용방법, 옵션 등을 나타냄

$ info

File: dir       Node: Top       This is the top of the INFO tree

  This (the Directory node) gives a menu of major topics.
  Typing "q" exits, "?" lists all Info commands, "d" returns here,
  "h" gives a primer for first-timers,
  "mEmacs<Return>" visits the Emacs topic, etc.

  In Emacs, you can click mouse button 2 on a menu item or cross reference
  to select it.

* Menu:

Archiving
* Cpio: (cpio).                 Copy-in-copy-out archiver to tape or disk.
* Tar: (tar).                   Making tape (or disk) archives.

Basics
* Common options: (coreutils)Common options.
* Coreutils: (coreutils).       Core GNU (file, text, shell) utilities.
* Date input formats: (coreutils)Date input formats.
* File permissions: (coreutils)File permissions.
                                Access modes.



6) whatis - 명령어에 대한 간단한 설명을 출력합니다.

$ whatis rm

[vagrant@host1 bitcamp-ncp]$ whatis rm
rm (1)               - remove files or directories
rm (1p)              - remove directory entries



7) alias -alias는 별칭이라는 뜻으로 리눅스에서 alias는 사용자가 명령어를 다른 이름으로 바꿔서 사용할 수 있는 쉘 내부 명령어를 말합니다.

$ alias

[vagrant@host1 bitcamp-ncp]$ alias
alias egrep='egrep --color=auto'
alias fgrep='fgrep --color=auto'
alias grep='grep --color=auto'
alias l.='ls -d .* --color=auto'
alias ll='ls -l --color=auto'
alias ls='ls --color=auto'
alias which='alias | /usr/bin/which --tty-only --read-alias --show-dot --show-tilde'


