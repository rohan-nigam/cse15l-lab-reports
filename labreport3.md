## Lab Report 3

# Part 1

chose: reversed(int[] arr) method

**Failure-Inducing Input for Buggy Program**
```
@Test
public void testReversed() {
  int[] input1 = {1, 2, 3, 4, 5};
  assertArrayEquals(new int[]{0, 0, 0, 0, 0}, ArrayExamples.reversed(input1));
```
**Non-Failure-Inducing Input for Buggy Program**
```
@Test
public void testReversed1() {
  int[] input2 = { };
  assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input2));
```
**Before and After Code**
*Before*
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

*After*
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
}
```

The error was that elements were being assigned from the NewArray to the original arr, instead of the other way around. Therefore, this would produce the wrong output. However, now that the last two lines have been altered, it now correctly assigns the numbers in the array to produce the desired output.

# Part 2


