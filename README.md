
# LEARNING BASH


A beginners list of bash commands. Be alarmed, I am no expert.

All commands below are things that worked for me and there's
no guarantee it will work for you. <br>This is pure exploration and
learning for me, know your system before using this list.
	
	My system: MacBook Pro (Retina, 15-inch, Mid 2015)
	   	   MacOS Sierra Version 10.12.6	   
		   Using iTerm2 + ZSH
		   
····························································································································

SCREEN

`screen`		create a new screen session
screen -ls	list all the current sessions
screen -X -S 	[session # you want to kill] quit kill entire session
screen -rd	reconnect to a screen
screen -r 	reconnect to screen 

····························································································································

IRSSI

´irssi´				launch irssi
/connect irc.oftc.net 		connect to server
/connect irc.freenode.net 	connect to freenode server
/join #facebookisdead 		join channel
/who				list users

highlight nickname by writing name in front, ex: zuyos: “string of text”

Alt -1/2/3/4		switch windows
Ctrl A ?		show all key binds
Ctrl A 			switch windows
Ctrl A c 		create new window
/exec  			executes a command within irssi

/exec imgur-screenshot.sh
allows you to take a screenshot and upload

····························································································································

CORE COMMANDS

⌘ shift i	switch to iTerm2 from any app (you can define your own keybind in the settings)
⌘[1,2,3,4]	switch between terminal windows
⌘ n		create new window
⌘ w		close current window
clear		clears all text from window
;		put in between 2 commands to run both

Ctrl A		go to beginning of the line you are typing
Ctrl U		Undo last command
Ctrl E		go to the end of the line you are typing
Ctrl L		clear the screen
Ctrl K		delete everything forward to end of line
Ctrl U		delete everything backwards to end of line
Ctrl C		kill whatever you are running
Ctrl P 		move up 1 line
Ctrl N 		move down 1 line

····························································································································

NAVIGATION

cd 		change directory
cd .. 		move up one directory
cd - 		move to (previous) directory
cd ../..	move up two directory
pwd 		print working directory (show where u are)
pushd		bookmark a directory
popd		jump back to bookmark

····························································································································

AUTOJUMP (EXT. PLUGIN)

brew install autojump		installs autojump
autojump -s			show all saved dirs in database
j <dir name>			jump to directory
jo <dir name>			open directory in Finder

····························································································································

GOOGLER

googler hi				starts google and googles hi
googler -h				brings up help
filetype:mp3 adelele	  		googles only mp3 named adele
googler --colors bjdxxy google		fixes colors (im using dark solarized theme, gets hard to read)

····························································································································

LIST 

ls 			list files
ls -S 			list files by size
ls -l 			list files details
ls -lhS			list files by size small to biggest
ls -R			list entire content of directory
ls ..			list parent directory of folder
du			display disk usage
du -sh			display entire size of dir
du -sh * | gsort -h	list all files by size small to biggest
tree -L [1,2] 		list files as tree with 1 or 2 dir deep

····························································································································

FILE MANAGEMENT

open			open single file
open * 		 	open all the files in the current dir
open *.JPG		open all jpgs in one directory with their default applications.

mkdir				create directory
touch	<name of file>		create new
source				update that file
brew info <package name>	show info about pkg path etc.

····························································································································

BASH PROFILE CUSTOMIZATION

nano ~/.bash_profile		opens and edit profile in nano
nano ~/.bashrc			opens and edit bashrc in nano
nano ~/.dir_colors		open and customise file colors
source “<path to file>”		source for instance .bashrc on start so all changes are in use

COLOR CHANGES

Text color codes in dir_colors:

30=black
31=red
32=green
33=yellow
34=blue
35=magenta
36=cyan
37=white

Background color codes:

40=black
41=red
42=green
43=yellow
44=blue
45=magenta
46=cyan
47=white

····························································································································

ITERM 2 IMGCAT & IMGLS (dont work in zsh)

imgcat <filename>	show image in terminal
imgls			list images as thumbnails
imgls *png		list all pngs
imgls *jpg		list all jpgs

····························································································································

YOUTUBE-DL

youtube-dl -F <URL>		     	list all available formats
youtube-dl -f <format> <URL>  		download audio/video > YT
example: youtube-dl -f 140  		this downloads m4a audio

····························································································································

WGET (dl files from webpage)

brew install wget		install wget
-e robots.off			ignore robots.txt files (BE CAREFUL WITH THIS)
-e robots=off --wait 1		ignore/override robots and wait 1 sec in between	
-nd 				no directories
-A png,jpg			only accept this file extension
-nc, —-no-clobber		skip dl if file exist
-np				dont follow links to parent dirs
–k				convert html links to local files
-r				recursive, for dl files from dir listing

example: 	wget -r -np -k -A jpeg,jpg <URL>
		wget -nd -r -P -A jpeg,jpg,bmp,gif,png
		wget -r -A .jpg http://site.with.images/url/

working example of dl images:
wget -r -nd -A “*.jpg" <url>

····························································································································

ZSH TERMINAL FRAMEWORK

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

····························································································································

ZSH PLUGINS

Auto Suggestions

····························································································································

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

····························································································································

CONVERT (FFMPEG)

to convert jpg to png go to dir with file, write:

convert <filepath>.jpg <filepath>.png

command for batch converting movies this case (mov->mp4):
(need to cd to right directory first)

for f in *.mov;do ffmpeg -i "$f" -c:v libx264 “${f%mov}mp4";done

convert single vid

ffmpeg -i youtube.flv -c:v libx264 filename.mp4

····························································································································

LEARNING EMACS

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

····························································································································

ADDING MODES (EMACS)

M-x httpd-start		start web server
impatient-mode		start impatient mode
rainbow-mode		start rainbow mode
M-x emmet-mode		start emmet mode
FlyC

····························································································································

EMMET

C-j			turn into tags/auto suggest etc.

····························································································································

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

····························································································································

GIT

git status					list info about GitHub repository
git remote add origin 				example: https://github.com/username/myproject.git
git remote -v					check online version of repo
git push					update files, make changes
git commit -m "Here is my commit message"
git commit --amend —-reset-author
git config --global --edit

git config --global user.name "Your Name"
git config --global user.email you@example.com

Update a file in repository:
make changes in your file, "index.html" etc.

1. git add index.html 		to update that file
2. git commit -m 		"update version 1.0”
3. ´git status´			check the current status
4. git push			upload changes

····························································································································

