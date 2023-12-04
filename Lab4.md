# Disclaimer 
I completed this lab report assuming I didn't have to say that I typed spaces, and '+' is used to symbolize using a combination of key presses. I also explained the keys I pressed. I also asked and I was told that I do not need to explicitly type <shift> + "letter" to signify that I capitalized the letter.
## Step 4:
Keys pressed:
```ruby
ssh <command+v>
```
Steps:
```ruby
ssh <command+v> = cs15lfa23op@ieng6.ucsd.edu,
then <enter>.
I had "cs15lfa23op@ieng6.ucsd.edu" coppied.
```
Output:

![Image](lab4Part1ss.png)

Explanation:
For this step, I SSH'd into my virtual machine using the ssh cs15lfa23op@ieng6.ucsd.edu command.
When you use this command you log into your virtual machine.

## Step 5:

Keys pressed:
```ruby
git clone <command+v><enter>
```
Steps:
```ruby
I typed git clone <command+v><enter>.
I had "git@github.com:ethanmypan/lab7.git" copied on my computer for this command.
```
Command: 
```ruby
git clone git@github.com:ethanmypan/lab7.git
```
Output:

![Image](lab4Part2SS.png)

Explanation:
For this step, git clone git@github.com:ethanmypan/lab7.git clones the forked repository onto my computer so I can access the files.

## Step 6:

Keys pressed:
```ruby
cd lab7<enter>,
bash test.sh<enter>
```
Steps:
```ruby
I typed cd lab7<enter>, then I typed bash test.sh<enter>. 
```
Command:
```ruby
cd lab7
bash test.sh
```
Output:
![Image](lab4Part3SS.png)

Explanation:
For this step, I use cd lab7 to change the directory to lab7, then I use bash test.sh which is a bash script to test the ListExamples.java file.

## Step 7: 

Keys pressed:
```ruby
vim ListExamples.java<enter>,
44 + G,
control + a,
<esc>,
:wq<enter>
```
Steps:
```ruby
I typed vim ListExamples.java<enter> in the terminal,
then once the file opened in vim I pressed 44 +<shift+g> = G,
then I pressed <control+a>, and after that,
I pressed <esc> then typed <shift+;> = : then wq.
```
Command:
```ruby
vim ListExamples.java
44G
control+a
:wq
```

Output:

![Image](vimListEx.png)
![Image](editVimListExamplesCode.png)

Explanation:
vim ListExamples.java opens the java file in vim so you can edit the file, then typing 44G will bring you to the 44th line, then I press control+a which increments the next closest number by 1 making the 1 into a 2, then I press <esc> so I leave the editing mode and the press:wq to save an close the file.


## Step 8:

Keys pressed:
```ruby
bash test.sh<enter>
```
Steps:
```ruby
I typed bash test.sh<enter> in the terminal.
```
Command:
```ruby
bash test.sh
```

Output:

![Image](listExamplesPassing.png)

Explanation:
bash test.sh runs the test bash script that contains the code to run the JUnit tests.

## Step 9:

Keys pressed:
```ruby
git add .<enter>,
git commit -m "fin"<enter>,
git push<enter>
```
Steps:
```ruby
I typed git add .<enter> into the terminal,
then I pressed git commit -m <shift+'> = ",
then I typed fin,
then I closed off the quotations with <shift+'> = ",
then I pressed <enter>,
then I typed git push<enter>.
```

Command:
```ruby
git add .
git commit -m "fin"
git push
```

Output:

![Image](gitaddcommitpush.png)

Explanation: 
```git add .```adds ListExamples.java to the git staging area, then ```git commit``` records the edits to git, then ```git push``` publishes the edits to your repository.


Commands Temp Save 

```ruby

```
![Image](vimListEx.png)
Keys pressed: <up><up><up><up><enter>, <up><up><up><up><enter> The javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java command was 4 up in the search history, so I used up arrow to access it. Then the java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ... command was 4 up in the history, so I accessed and ran it in the same way
