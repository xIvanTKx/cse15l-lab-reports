# Lab Report 3: Part 1 - Bugs

* A failure-inducing input for the buggy program, as a JUnit test and any associated code
```
@Test
public void testReverseInPlaceFail() {
    int[] arr = {1, 2, 3, 4, 5};
    ArrayExamples.reverseInPlace(arr);
    assertArrayEquals(new int[]{5, 4, 3, 2, 1}, arr);
}

@Test
public void testReversedFail() {
    int[] arr = {1, 2, 3, 4, 5};
    int[] result = ArrayExamples.reversed(arr);
    assertArrayEquals(new int[]{5, 4, 3, 2, 1}, result);
}
```
* An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
```
@Test 
public void testReverseInPlace() {
    int[] arr = { 6 };
    ArrayExamples.reverseInPlace(arr);
    assertArrayEquals(new int[]{ 6 }, arr);
}

@Test
public void testReversed() {
    int[] arr = { };
    int[] result = ArrayExamples.reversed(arr);
    assertArrayEquals(new int[]{ }, result);
}
```
* The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
  ![image](https://github.com/xIvanTKx/cse15l-lab-reports/assets/110268085/aecdfe4c-d310-4819-beae-c13dc83b4457)
* The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
```
// Before
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}

static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
}
```
```
// After
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
        int temp = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = temp;
    }
}

static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
}
```
* Briefly describe why the fix addresses the issue:
  * The original `reverseInPlace` method was overwriting the first half of the array before it could swap those elements with the second half of the array. The fix addresses this by only iterating over the first half of the array and swapping the `i`th element with the `arr.length - i - 1`th element. This correctly reverses the array in place. The temporary variable `temp` is used to hold the value of `arr[i]` before it gets overwritten. This way, both `arr[i]` and `arr[arr.length - i - 1]` can be swapped without losing any information. This fix ensures that the array is correctly reversed in place.
  * The original `reversed` method was incorrectly trying to modify the input array `arr` instead of the new array `newArray`. The fix addresses this by correctly assigning the reversed elements of `arr` to `newArray`. The `testReversed` test now passes with this fix. The returned array is a new array with the elements of the input array in reversed order. The input array `arr` remains unchanged.
