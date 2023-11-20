# Lab Report 3
# Part 1

## A failure-inducing input as a JUnit test.

```ruby
@Test
  public void testReverseInPlace2Var() {
    int[] input1 = {1,2};
    int [] expected = {2,1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(expected, input1);
  }
```
## A failure-inducing input as code.
```ruby
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length ; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```

## An input that doesn’t induce a failure as a JUnit test
```ruby
@Test
  public void testReverseInPlace1Var() {
    int[] input1 = {1};
    int [] expected = {1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(expected, input1);
  }
```

## The code that doesn't induce a failed test.
```ruby
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length ; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```

## The symptom as the output of running the tests.
![Image](Cse15lLab3FirstErrorOutput.png)


## The bug, as the before-and-after code.


```ruby
static void reverseInPlace(int[] arr) {
  for(int i = 0; i < arr.length ; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
}
```

```ruby
static void reverseInPlace(int[] arr) {
    int j = arr.length - 1;
    for(int i = 0; i < arr.length / 2; i ++) {
      int temp = arr[i];
      arr[i] = arr[j];
      arr[j] = temp;
      j --;
    }
  }
```
## Explanation for the fix.
The fix addresses the issue of poorly reversing the order of the array. In the original code for our example, the first element of the reversed array was 2, the next element was also 2. The reason this happened is because what the original code did was set the 0th element (1) to 1st element of the array (2), now the 0th element is (2). Then it set the 1st element to the 0th element and since the 0th element is (2), the array would be filled with {2, 2}. What my corrected implementation does, is it sets a int j to keep track of the end of the array, then it iterates through half of the array,  then sets the element i to a temp int, then sets the element in array[i] to the element in array[j], then it sets the element in array[j] to the temp int, and then decrement j by 1. What this better implementation does, it will get an array, for out example {2, 2}, set j to 1, iterate through half the length of the array, set int temp to 1, then set the element of the array[0](1) = array[1](2), then set arr[1] = (1). This implementation will return the array {2, 1}.

# Part 2
## Find command-line options
To understand what the find command-line options are/do I used the man find command in the terminal. I also asked chat gpt how to use the find -"command" in the terminal.


# find "path" -ls 
## find "path" -ls with directory as an argument
find /Users/ethanmypan/docsearch/technical -ls
- Shortend the output since it was multiple pages long.
```ruby
(base) ethanmypan@Ethans-MacBook-Air-4 technical % find /Users/ethanmypan/docsearch/technical -ls
pan/docsearch/technical/911report/chapter-13.3.txt
18536376      520 -rwxr-xr-x    1 ethanmypan       staff              264360 Oct 31 12:39 /Users/ethanmypan/docsearch/technical/911report/chapter-3.txt
18536375      160 -rwxr-xr-x    1 ethanmypan       staff               79803 Oct 31 12:39 /Users/ethanmypan/docsearch/technical/911report/chapter-2.txt
18536366      232 -rwxr-xr-x    1 ethanmypan       staff              118656 Oct 31 12:39 /Users/ethanmypan/docsearch/technical/911report/chapter-1.txt
```
Explanation: find /Users/ethanmypan/docsearch/technical -ls, this command searches files in the provided path. It also provides useful information on each file, this is important since it can help display the owners of the file, file size, and other important information.
## find "path" -ls with file as an argument
find /Users/ethanmypan/docsearch/technical/biomed/1471-2202-3-20.txt -ls
```ruby
(base) ethanmypan@Ethans-MacBook-Air-4 biomed % find /Users/ethanmypan/docsearch/technical/biomed/1471-2202-3-20.txt -ls
18536659       72 -rwxr-xr-x    1 ethanmypan       staff               36617 Oct 31 12:39 /Users/ethanmypan/docsearch/technical/biomed/1471-2202-3-20.txt
```
Explanation: find /Users/ethanmypan/docsearch/technical/biomed/1471-2202-3-20.txt -ls, this command uses the file path it was given to display specific detail information on the file. It is important since it displays the owner of the file, the file size, 
# find "path" -size -"size to filter by"
- Shortend the output since it was multiple pages long.
## find "path" -size with directory as argument
find /Users/ethanmypan/docsearch/technical -size -1k 
```ruby
(base) ethanmypan@Ethans-MacBook-Air-4 technical % find /Users/ethanmypan/docsearch/technical -size -1k 
/Users/ethanmypan/docsearch/technical
/Users/ethanmypan/docsearch/technical/government
/Users/ethanmypan/docsearch/technical/government/About_LSC
/Users/ethanmypan/docsearch/technical/government/Env_Prot_Agen
/Users/ethanmypan/docsearch/technical/government/Alcohol_Problems
/Users/ethanmypan/docsearch/technical/government/Post_Rate_Comm
/Users/ethanmypan/docsearch/technical/plos/pmed.0020191.txt
/Users/ethanmypan/docsearch/technical/plos/pmed.0020226.txt
/Users/ethanmypan/docsearch/technical/911report
```
Explanation: find /Users/ethanmypan/docsearch/technical -size -1k, this command searches for files or directories in the path it was provided and filtered by files or directories that are smaller than 1 kilobyte and then it lists their path. This is important since it is a good way to filter out files that are too big, it can help search for files that are a specific size.
## find "path" -size with file as argument
find /Users/ethanmypan/docsearch/technical/plos/pmed.0020226.txt -size -1k
```ruby
(base) ethanmypan@Ethans-MacBook-Air-4 technical % find /Users/ethanmypan/docsearch/technical/plos/pmed.0020226.txt -size -1k
/Users/ethanmypan/docsearch/technical/plos/pmed.0020226.txt
```
Explanation: find /Users/ethanmypan/docsearch/technical/plos/pmed.0020226.txt -size -1k, this command searches for the file it was provided that is smaller than 1 kilobyte, then it displays the file path of the filtered file. This is important to filter out possible files with the same name but different sizes. 
# find "path" -delete
## find "path" -delete with file as argument
find /Users/ethanmypan/docsearch/technical/911report -name "chapter-2.txt" -delete
```ruby
(base) ethanmypan@Ethans-MacBook-Air-4 911report % find /Users/ethanmypan/docsearch/technical/911report -name "chapter-2.txt" -delete
(base) ethanmypan@Ethans-MacBook-Air-4 911report % ls
chapter-10.txt          chapter-13.3.txt        chapter-6.txt
chapter-11.txt          chapter-13.4.txt        chapter-7.txt
chapter-12.txt          chapter-13.5.txt        chapter-8.txt
chapter-13.1.txt        chapter-3.txt           chapter-9.txt
chapter-13.2.txt        chapter-5.txt           preface.txt
```
Explanation: find /Users/ethanmypan/docsearch/technical/911report -name "chapter-2.txt" -delete, this command searches for a file from the provided directory and the provided file name, if it finds the file, then it deletes it from the directory. This is important since it is a simple way to delete a file from a directory.
## find "path" -delete with directory as argument
find /Users/ethanmypan/docsearch/technical/911report -delete
```ruby
(base) ethanmypan@Ethans-MacBook-Air-4 911report % find /Users/ethanmypan/docsearch/technical/911report -delete
(base) ethanmypan@Ethans-MacBook-Air-4 technical % ls
biomed          government      plos
```
Explanation: find /Users/ethanmypan/docsearch/technical/911report -delete, this command searches for the provided directory and if found it will delete the directory. This is important since it is a simple and fast way to delete a directory. 
# find "path" -name
## find "path" -name with directory as argument
find /Users/ethanmypan/docsearch/technical -type d -name "government"
```ruby
(base) ethanmypan@Ethans-MacBook-Air-4 technical % find /Users/ethanmypan/docsearch/technical -type d -name "government"
/Users/ethanmypan/docsearch/technical/government
```
Explanation: find /Users/ethanmypan/docsearch/technical -type d -name "government",
this command searches through the file path and then uses the -name "government" to find the government directory. It then returns the directory path if it is found. This is important to see if a directory exists and to get its path.
## find "path" -name with file as argument
find /Users/ethanmypan/docsearch/technical/biomed -name "1471-2431-3-6.txt"
```ruby
(base) ethanmypan@Ethans-MacBook-Air-4 biomed % find /Users/ethanmypan/docsearch/technical/biomed -name "1471-2431-3-6.txt"
/Users/ethanmypan/docsearch/technical/biomed/1471-2431-3-6.txt
```
Explanation: find /Users/ethanmypan/docsearch/technical/biomed -name "1471-2431-3-6.txt", this command searches through the provided path and then uses -name "1471-2431-3-6.txt" to find the specified .txt file. This is important to see if a txt file exists in the provided file path.

