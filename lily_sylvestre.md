
notes in this file as demonstrated by my instructor 

cd: change directory (change where you are)
ls: list all of the stuff in the working directory 
pwd: shows you where your CWD is 

2/16/24
ls -a: hidden 
/ : root directory 
mkdir: makes a directory 
mkdir -p: creates a parent directory 
rmdir: remove directory (MUST BE EMPTY) (CANNOT BE RECOVERED)
mv: moves and/or renames
    mv bad_file_name good_file_name : renames the file 
    mv ../notes.txt ~/notebook : mores notes.tst into the notebook
    mv /tmp/important_data.fasta : moves the file from tmp directory to CWD
cp : copy (NEEDS TO HAVE _R FLAG TO COPY DIRECTORIES)
    cp file1.txt file1_cope.txt : copies the file and renames it 
    cp -R fastas .. : copies fastas from CWD into parent directory
    cp test.txt .. : coppies text.txt into parent directory and keeps the same name 
touch : creats empty file if it doesn't already exist 
    touch newfile.txt : creates newfile.txt 
rm : removes PERMANENTLY 
    needs -R flad to rm directories 
    rm file.fasta : deletes file.fasta 
    rm -R ~ : comepletely erases your home directory 
if you press up arrow it brings you to all of the commands youve done before or you can edit it
cat : combines and displays files 
> : redirects the output of a command to the file specidied, overwriting it 
>> : rediects the outpit of a commmand to the file specified, appending to it (stick it at the end)
head and tail 
    head shows the first 10 lines of file 
    tail shows the last 10 lines of file 
    -n with number : shows you that that number either of beginning or end 
command c stops it 
* is the wildcard character
    will match any character and any amount of characers 

3 ways to change directories to HOME from untrimmed_fastq
1) cd /home
2) cd ~
3) cd 

How many programs in /bin
1922

single command to list all of the files in /Applications that start with c
ls C* /applications 
single command to list all of the files in /Applications that contain a
ls *lA* /applications 
single command to list all of the files in /Applications that end with o
ls *o /applicaitons 
using the line number for the command that lists all of the fastq files using the absolute path 
ls *.fastq

2/23/24
less: scrollable file veiwer
    more suitable for veiwing large files or files with long lines
    Main controls are the up and down arrow to scroll
    q to exit 
    capital G will bring you to the end 
    lowercase g will bring you to the beginning 
nano: easy to use text editor 
    perferred for quick edits 
    Ctrl X: exit 
    nano newnotes.txt opens new notes 
*: is a wild card character 
    it will match any character 
    it will match any amount of characters 
grep: extremley useful program that when given a search term, it will find all the instances of that term within a given search area 
    Flags: a whole bunch in grep
        -B: before 
        -A: after
        -o: prints only the part of the line you are looking for
        -v: leaves out the line that matches the search tearm 
    put pretty much everything in quotes 
there are many ways to open a file, right now plz just use less
all commands have two things: input and output 
stdin: input into a program, will usually be from the keyboard DOESN'T HAVE TO BE 
stdout: the output fo a program, usually goes to the terminal screen 
piping: chains commands together 
| - pipe key
    this will put the output of the first input into the next command and then give the output for the next command based on the input of the first command (and so on depending on how many commands there are)
wc: word count 
    #lines / #words / #bytes (kinda like the number of characters but not really)
    -l : only shows # of lines 
    -w : only shows # of words
    -c : only shows # of bytes 

3/8/2024
using PuTTY this week 
using tmux 
    can show you how to use a bunch of stuff all at once 
    man tmux- manual for tmux 
    tmux list-commands -shows commands 
    tmux new -s- opens new terminal 
            you can come back to a tmux session after it has closed out or can continue running the programs for long periods of time 
    control b -gets you set up to type into the tmux not the terminal
    shift " -gets you to a new terminal below 
    control b, d -gets you out a tmux session 
    tmux list-sessions- shows you what sessions are open 
    tmux attach -t (name of session) -opens previous session 
    tmux kill-session -t (name) -kills the session 
    control b X- kills a frame 
    control b %- opens to side 
z cat- opens file 
z less- 
z grep- uncompress while looking through 
how to figure out how many reads
    zgrep "@" * | wc -l 
conda manages different stuff within the computer
    conda deactivate;

4/5/24
running everythign on putty 
echo "hello"
    will print whatever you just typed out right below

 permissions - ls -l will show you what permissions you have on the directories or files 
 to have the permissions 
    chmod- change mode 
        chmod u+x then path 

BIOINFORMATICS PIPELINE
used fastqc to do something  

SFTP transfers files from local to remote devices  

4/12/24
final project notes 
can be in groups of 3
make a github repo with all the information 
read me file 
need to write down all of the codes into a .SH file 
look into Qiime
Matt, Noah, Me as a group 
Doing the Genome assembly one 

most prodjects are following similar pathway as the bioimformatics pipeline kaleb has shown 
(very rough overveiw)


raw reads
if shitty fastqc to make better

trimmomatic to cut the bad reads 

prep for analysis 
something like an alignment (to a reference)

do a quality analysis 

4/19/24
how to create a sh file:
    
Final project 

Noah ran fastqc on raw reads, and attempted to run trimmomatic but didn't work last night 
