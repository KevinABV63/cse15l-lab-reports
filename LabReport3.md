# Part 1

## Failure-Inducing Input

```

import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {

  @Test
  public void testReverseInPlace() {
    // Test case 1: Empty array
    int[] input1 = { };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ }, input1);

    // Test case 2: Array with multiple elements
    int[] input2 = { 1, 2, 3, 4 };
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{ 4, 3, 2, 1 }, input2);
  }

  @Test
  public void testReversed() {
    // Test case 1: Empty array
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));

    // Test case 2: Array with multiple elements
    int[] input2 = { 1, 2, 3, 4 };
    assertArrayEquals(new int[]{ 4, 3, 2, 1 }, ArrayExamples.reversed(input2));
  }
}


```
## Non-Failure Input Test

```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}


  @Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }
  
}

```
## The Symptom


## Before and After the Bug

### Bug in `reverseInPlace` method:

Before:
```
for (int i = 0; i < arr.length; i += 1) {
  arr[i] = arr[arr.length - i - 1];
}
```
After:
```
for (int i = 0; i < arr.length / 2; i++) {
  int temp = arr[i];
  arr[i] = arr[arr.length - i - 1];
  arr[arr.length - i - 1] = temp;
}
```

Issue: The original code incorrectly iterated over the entire array and directly assigned elements from the end of the array to the beginning, resulting in incorrect values.

Fix: The corrected code iterates only halfway through the array, swapping elements between the current position and its corresponding position from the end. This ensures a proper reversal without overwriting elements.

### Bug in `reversed` method:

Before:
```
for (int i = 0; i < arr.length; i += 1) {
  arr[i] = newArray[arr.length - i - 1];
}
```
After:
```
for (int i = 0; i < arr.length; i++) {
  newArray[i] = arr[arr.length - i - 1];
}
```
Issue: The original code incorrectly assigned values from the original array to the new array in a way that did not produce the desired reversed order.

Fix: The corrected code correctly assigns values from the original array to the new array in a reversed order, ensuring that the new array reflects the desired reversal of the input array.
These changes ensure that the elements are correctly swapped or assigned during the reversal process, fixing the bugs in the original code.







# 
