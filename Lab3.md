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
The fix addresses the issue of poorly reversing the order of the array. In the original code for our example, the first element of the reversed array was 2, the next element was also 2. The reason this happend is because what the original code did was set the 0th element (1) to 1st element of the array (2), now the 0th element is (2). Then it set the 1st element to the 0th element and since the 0th element is (2), the array would be filled with {2, 2}. What my corrected immplementation does, is it sets a int j to keep track of the end of the array, then it itterates through half of the array,  then sets the element i to a temp int, then sets the element in array[i] to the element in array[j], then it sets the element in array[j] to the temp int, and then decrement j by 1. What this better implementation does, it will get an array, for out example {2, 2}, set j to 1, ittereate through half the length of the array, set int temp to 1, then set the element of the array[0](1) = array[1](2), then set arr[1] = (1). This implementation, will return the array {2, 1}.

# Part 2
## Grep command-line options
