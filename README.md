
# LEARNING BASH


A beginners list of bash commands. Be alarmed, I am no expert.

All commands below are things that worked for me and there's
no guarantee it will work for you. <br>This is pure exploration and
learning for me, know your system before using this list.
	
&nbsp;&nbsp;&nbsp;My system: MacBook Pro (Retina, 15-inch, Mid 2015)<br>
&nbsp;&nbsp;&nbsp;MacOS Sierra Version 10.12.6 running iTerm2 + ZSH

### SCREEN

| Key/Command   | Description   | 
| ------------- | ------------- | 
| ``` screen ```| create a new screen session | 
| ```screen -ls```| list all the current sessions | 
| ```screen -X -S``` | [session # you want to kill] quit kill entire session | 
| `screen -r` | reconnect to screen | 
| `screen -rd` | reconnect to a screen | 
| `screen Ctrl A -D` | disconnect from screen | 


### TMUX

in tmux use the prefix 'ctrl-b' in front of every command

#### CORE COMMANDS

| Key/Command   | Description   | 
| ------------- | ------------- |
| tmux | start new |
| tmux new -s myname | start new with name |
| tmux a  #  (or at, or attach) | attach |
| tmux a -t myname | attach to named |
| tmux ls | list sessions |
| tmux kill-session -t myname |	kill session name |

killall tmux sessions <br>
`tmux ls | grep : | cut -d. -f1 | awk '{print substr($1, 0, length($1)-1)}' | xargs kill `

#### SESSIONS

| Key/Command   | Description   | 
| ------------- | ------------- |
| s | list sessions |
| $ | name session |

#### WINDOWS (tabs)

| Key/Command   | Description   | 
| ------------- | ------------- |
| c | create window |
| w | list windows |
| n | next window |
| p | previous window |
| f | find window |
| , | name window |
| & | ill window |

#### PANES (splits)

| Key/Command   | Description   | 
| ------------- | ------------- |
| % | vertical split |
| " | horizontal split |
| o | swap panes |
| q | show pane numbers |
| x | kill pane |
| + | break pane into window (e.g. to select text by mouse to copy) |
| - | restore pane from window |
| ⍽ | space - toggle between layouts |
| <prefix> q | (Show pane numbers, when the numbers show up type the key to goto that pane) |
| <prefix> { | (Move the current pane left) |
| <prefix> } | (Move the current pane right) |
| <prefix> z | toggle pane zoom |

#### MISC

| Key/Command   | Description   | 
| ------------- | ------------- |
| d | detach |
| t | big clock |
| ? | list shortcuts |
| : | prompt |


## IRSSI

| Key/Command   | Description   | 
| ------------- | ------------- |
| `irssi` | launch irssi |
| `irssi -n test123` | change nickname |
| `/connect irc.oftc.net` | connect to server |
| `/connect irc.freenode.net` | connect to freenode server |
| `/server irc.snoonet.org` | connect to Reddit |
| `/join #facebookisdead` | join channel |
| `/who` | list users |
| `/whois` | display userinfo |
| `/wc` | close window |
| `/save` | save irssi settings after customized |
| `/SET user_name NickHere` | set username |
| `/SET real_name RealNameHere` | set realname |
| ```/IGNORE * QUITS PARTS JOINS NICKS``` | ignores users quits/joins etc. |

highlight nickname by writing name in front, ex: zuyos: “string of text”

| Key/Command   | Description   | 
| ------------- | ------------- |
| Alt -1/2/3/4 | switch windows |
| Ctrl A ? | show all key binds |
| Ctrl A | switch windows |
| Ctrl A c | create new window |
| /exec | executes a command within irssi |
| /exec imgur-screenshot.sh | allows you to take a screenshot and upload

#### SCRIPTS

autorun scripts by putting them into ~/.irssi/scripts/autorun/

## CORE COMMANDS

| Key/Command   | Description   | 
| ------------- | ------------- |
| ⌘ shift i |	switch to iTerm2 from any app (you can define your own keybind in the settings) |
| ⌘[1,2,3,4] |	switch between terminal windows |
| ⌘ n |		create new window |
| ⌘ w |		close current window |
| clear |	clears all text from window |
| ; |		put in between 2 commands to run both |
| `shutdown -h +30` | shutdown comp. in 30 min |
| `poweroff` | shutdown |
| Ctrl A |		go to beginning of the line you are typing |
| Ctrl U |		Undo last command |
| Ctrl E |		go to the end of the line you are typing |
| Ctrl L |		clear the screen |
| Ctrl K |		delete everything forward to end of line |
| Ctrl U |		delete everything backwards to end of line |
| Ctrl C |		cancel whatever you are running |
| Ctrl P | 		move up 1 line |
| Ctrl N | 		move down 1 line |
| Ctrl W | 		This deletes the word before the cursor only |

## NAVIGATION

| Key/Command   | Description   | 
| ------------- | ------------- |
| cd 		| 	 change directory |
| cd .. 	| 	 move up one directory |
| cd - 		| 	 move to (previous) directory |
| cd ../.. 	|	 move up two directory |
| pwd 		| 	 print working directory (show where u are) |
| pushd 	|	 bookmark a directory |
| popd 		|	 jump back to bookmark |

## TRASH FILES

| Key/Command   | Description   | 
| ------------- | ------------- |
| brew install trash |		installs trash |
| trash <filename> <filename> |	send files to trash |
| trash -l |			list files in trash |
| trash -lv |			list files in trash with more info (size) |
| trash -e |			empty trash |

## AUTOJUMP (EXT. PLUGIN)

| Key/Command   | Description   | 
| ------------- | ------------- |
| brew install autojump |	installs autojump |
| autojump -s |			show all saved dirs in database |
| j <dir name> |		jump to directory |
| jo <dir name> |		open directory in Finder |
| jo pwd |			open current directory in Finder |

### GOOGLER

| Key/Command   | Description   | 
| ------------- | ------------- |
| googler hi |				starts google and googles hi |
| googler -h |				brings up help |
| filetype:mp3 adelele |	  	googles only mp3 named adele |
| googler --colors bjdxxy google |	fixes colors (im using dark solarized theme, gets hard to read) |


## LIST 

| Key/Command   | Description   | 
| ------------- | ------------- |
| ls 			| list files |
| ls -S 		| list files by size |
| ls -l 		| list files details |
| ls -lhS		| list files by size small to biggest |
| ls -R			| list entire content of directory |
| ls ..			| list parent directory of folder |
| du			| display disk usage |
| du -sh		| display entire size of dir |
| du -sh * | gsort -h	| list all files by size small to biggest |
| tree -L [1,2] 	| list files as tree with 1 or 2 dir deep |


## FILE MANAGEMENT

| Key/Command   | Description   | 
| ------------- | ------------- |
| open			| open single file |
| open * 		| open all the files in the current dir |
| open *.JPG		| open all jpgs in one directory with their default applications. |
| open -a preview ./	| open current dir with app preview |
| stat <name of file>	| display details of the file |
| file <name of file>	| display format, size, color-profile (info about a file) |
| mdfind <filename>	| spotlight search |
| df -h			| display disk usage (default) |
| dfc			| display disk usage (homebrew) |

| mkdir				| create directory |
| touch	<name of file>		| create new |
| mv oldfilename newfilename	| rename file |
| mv <file> <directory>		| move file to directory |
| mv <file> <"directory">	| move file to directory containing spaces |
| source			| update that file |
| brew info <package name>	| show info about pkg path etc. |


## DISK UTILITY

| Key/Command   | Description   | 
| ------------- | ------------- |
| diskutil list			| list all drives |
| diskutil unmount <path>	| unmount disk |
| diskutil unmountDisk <path>	| unmount all partitions |
| diskutil unmount /dev/disk2	| example |

## BASH PROFILE CUSTOMIZATION

| Key/Command   | Description   | 
| ------------- | ------------- |
| nano ~/.bash_profile		| opens and edit profile in nano |
| nano ~/.bashrc		| opens and edit bashrc in nano |
| nano ~/.dir_colors		| open and customise file colors |
| source “<path to file>”	| ource for instance .bashrc on start so all changes are in use |

### COLOR CHANGES
| Key/Command   | Description   | 
| ------------- | ------------- |
| Text color codes in dir_colors: |

| 30=black | 
| 31=red | 
| 32=green | 
| 33=yellow | 
| 34=blue | 
| 35=magenta | 
| 36=cyan | 
| 37=white | 

| Background color codes: | 

| 40=black | 
| 41=red | 
| 42=green | 
| 43=yellow | 
| 44=blue | 
| 45=magenta | 
| 46=cyan | 
| 47=white | 


## ITERM 2 IMGCAT & IMGLS

| Key/Command   | Description   | 
| ------------- | ------------- |
| imgcat <filename>	| show image in terminal |
| imgls			| list images as thumbnails |
| imgls *png		| list all pngs |
| imgls *jpg		| list all jpgs |


## YOUTUBE-DL

| Key/Command   | Description   | 
| ------------- | ------------- |
| youtube-dl -F <URL>		     	| list all available formats |
| youtube-dl -f <format> <URL>  	| download audio/video > YT |
| example: youtube-dl -f 140  		| this downloads m4a audio |


## WGET (dl files from webpage)

| brew install wget		| install wget |
| -e robots.off			| ignore robots.txt files (be careful) |
| -e robots=off --wait 1	| ignore/override robots and wait 1 sec in between |	
| -nd 				| no directories |
| -A png,jpg			| only accept this file extension |
| -nc, —-no-clobber		| skip dl if file exist |
| -np				| dont follow links to parent dirs |
| –k				| convert html links to local files |
| -r				| recursive, for dl files from dir listing |

example: 			wget -r -np -k -A jpeg,jpg <URL>
				wget -nd -r -P -A jpeg,jpg,bmp,gif,png
				wget -r -A .jpg http://site.with.images/url/
grab a file from website:	wget http://example.com/file.iso

working example of dl images:
wget -r -nd -A “*.jpg" <url>


## ZSH TERMINAL FRAMEWORK

–source it on startup	

[[ -s `brew --prefix`/etc/autojump.sh ]] && . `brew —prefix`/etc/autojump.sh

paste this in your .zshrc to make autojump work

function chwpd() {		makes cd auto ls
	emulate -L zsh
	ls -a
}

another function doing same thing

function cdls() {
cd "1" && ls "$1";
}

default path given when installing zsh

# export PATH=$HOME/bin:/usr/local/bin:$PATH
coming from bash I customised to
export PATH=“/usr/local/bin:$PATH"

so home-brew installation works etc

PATH to zsh
/usr/local/share/zsh/


### ZSH PLUGINS

Auto Suggestions


ZSH ALIAS

#fast shortcuts

alias c='clear'
alias cd..='cd ..'
alias ..='cd ..'
alias ...='cd ../..'
alias .3='../../../'
alias .4='../../../../'
alias o='open'
alias sortsize='du -sh * | gsort -h’

## CONVERT (FFMPEG)

to convert jpg to png go to dir with file, write:

convert <filepath>.jpg <filepath>.png

batch convert entire folder (converting tifs to jpg):

mogrify -format jpg ./*.tif

to convert all files with same filetype write:

convert *.tif newNameGoesHere.jpg

command for batch converting movies this case (mov->mp4):
(need to cd to right directory first)

for i in *.mov; do ffmpeg -i "$i" "${i%.*}.mp4"; done


convert single vid

ffmpeg -i youtube.flv -c:v libx264 filename.mp4

merge video + audio together

ffmpeg -i video.mp4 -i audio.wav \
-c:v copy -c:a aac -strict experimental output.mp4

merge video + audio without re-encoding audio

ffmpeg -i video.mp4 -i audio.wav -c copy output.mkv

replacing audio stream if it already exists

ffmpeg -i video.mp4 -i audio.wav \
-c:v copy -c:a aac -strict experimental \
-map 0:v:0 -map 1:a:0 output.mp4

## LEARNING EMACS

M-x package-list-packages	install new packages to emacs
C-x 	C-c			quit emacs session (logout)
C-z				temp. exit emacs
C-l				center in screen
n				next page
p				previous page
b				beginning of page
space 				navigate down

C-f     	Move forward a character
C-b     	Move backward a character

M-f     	Move forward a word
M-b     	Move backward a word
M-backspace	kill previous word

C-n     	Move to next line
C-p     	Move to previous line

C-a     	Move to beginning of line
C-e    	 	Move to end of line

M-a    	 	Move back to beginning of sentence
M-e    		Move forward to end of sentence
C-/		Undos last action
C-g		cancel mini buffer input
C-x C-s		saves a file
C-x C-b		show buffer list
C-x b		switch between buffers
C-x 1		remove buffer list
C-x C-f foo <Return> 		create new file named foo

C-x C-f         Find file
C-x C-s         Save file
C-x s           Save some buffers
C-x C-b         List buffers
C-x b           Switch buffer
C-x C-c         Quit Emacs
C-x 1           Delete all but one window
C-x u           Undo
M-x text mode <Return>		change mode to text mode

C-s		search file, hit C-s again to go to next
C-M(meta)-v 	scroll other window down
C-k 		kill buffer (window)

### ADDING MODES (EMACS)

M-x httpd-start		start web server
impatient-mode		start impatient mode
rainbow-mode		start rainbow mode
M-x emmet-mode		start emmet mode
FlyC


EMMET

C-j			turn into tags/auto suggest etc.



(require 'web-beautify) ;; Not necessary if using ELPA package
    (eval-after-load 'js2-mode
      '(define-key js2-mode-map (kbd "C-c b") 'web-beautify-js))
    (eval-after-load 'json-mode
      '(define-key json-mode-map (kbd "C-c b") 'web-beautify-js))
    (eval-after-load 'sgml-mode
      '(define-key html-mode-map (kbd "C-c b") 'web-beautify-html))
    (eval-after-load ‘css-mode
(require 'mmm-auto)
(setq mmm-global-mode 'maybe)
(setq mmm-submode-decoration-level 1)
(set-face-background 'mmm-default-submode-face "gray70")
(mmm-add-mode-ext-class 'html-mode "\\.php\\'" 'html-php)
(mmm-add-mode-ext-class 'html-mode "\\.php\\'" 'html-js)
(mmm-add-mode-ext-class 'html-mode "\\.php\\'" ‘html-css)



## GIT
| Key/Command   | Description   | 
| ------------- | ------------- |
| git status					| list info about GitHub repository |
| git remote add origin 			| example: https://github.com/username/myproject.git |
| git remote -v					| check online version of repo |
| git push					| update files, make changes |
| git commit -m "Here is my commit message" |
| git commit --amend —-reset-author |
| git config --global --edit |

| git config --global user.name "Your Name" |
| git config --global user.email you@example.com |

| Update a file in repository: |
| make changes in your file, "index.html" etc. |

| 1. git add index.html 			| to update that file |
| 2. git commit -m "update version 1.0”		| commit file |
| 3. ´git status´				| check the current status |
| 4. git push					| upload changes |


## NODE.JS

| Key/Command   | Description   | 
| ------------- | ------------- |
| node -v	| checks current version |

### EXPRESS

| npm install express-generator -g	| installs express generator |
| express --view=pug myapp		| generates basic app called 'myapp' (with pug as init for views) |
| express --view=ejs myapp		| generates basic app called 'myapp' (with ejs as init for views) |
| cd myapp && npm install		| cds and installs dependencies |
| DEBUG=myapp:* npm start		| run the app (only on mac & linux) |
| set DEBUG=myapp:* & npm start		| same for Windows |


