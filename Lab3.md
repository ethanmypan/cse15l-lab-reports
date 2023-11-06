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
