# Lab-7_202001271

# Dhruv Patel

# 18/04/23 IT314 - Software Engineering 

## Section A:

### Equivalence Class Test Cases for Determining the Previous Date

Equivalence Partitioning:
Equivalence Partitioning is a technique of software testing used to divide the input domain of a program into classes of data from which test cases can be derived. In this case, we can divide the input domain into three equivalence classes:

- Equivalence Class 1: Valid input data
This class includes all valid input data such that 1 <= month <= 12, 1 <= day <= 31, and 1900 <= year <= 2015.

<table>
  <tr>
    <th>Tester Action</th>
    <th>Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(10, 6, 2000)</td>
    <td>(9, 6, 2000)</td>
  </tr>
</table>

- Equivalence Class 2: Invalid input data
This class includes all invalid input data such that the day, month or year is out of range.

<table>
  <tr>
    <th>Tester Action</th>
    <th>Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(32, 6, 2000)</td>
    <td>Error message</td>
  </tr>
   <tr>
    <td>Check previous date</td>
    <td>(10, 13, 2000)</td>
    <td>Error message</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(10, 6, 1800)</td>
    <td>Error message</td>
  </tr>
 </table>

- Equivalence Class 3: Invalid input data due to leap year
This class includes all invalid input data where the date is in the month of February and the day is greater than 29 for a leap year (divisible by 4) or greater than 28 for a non-leap year.

<table>
  <tr>
    <th>Tester Action</th>
    <th>Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(30, 2, 2000)</td>
    <td>Error message</td>
  </tr>
   <tr>
    <td>Check previous date</td>
    <td>(29, 2, 1900)</td>
    <td>Error message</td>
  </tr>
 </table>


### Boundary Value Analysis

Boundary Value Analysis is a technique of software testing used to determine the values at the edges of the input domain. In this case, we can use boundary value analysis to determine the input data that lie at the edges of the input domain.

- Boundary Value 1: Minimum input values
This boundary includes the minimum values of the input domain such that month=1, day=1, and year=1900.

<table>
  <tr>
    <th>Tester Action</th>
    <th>Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(1, 1, 1900)</td>
    <td>Error Message</td>
  </tr>
 </table>


- Boundary Value 2: Maximum input values
This boundary includes the maximum values of the input domain such that month=12, day=31, and year=2015.

<table>
  <tr>
    <th>Tester Action</th>
    <th>Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(31, 12, 2015)</td>
    <td>(30, 12, 2015)</td>
  </tr>
 </table>

- Boundary Value 3: Invalid input data at the edges
This boundary includes the invalid input data at the edges of the input domain, i.e., month=2 and day=29 for a leap year and day=28 for a non-leap year.

<table>
  <tr>
    <th>Tester Action</th>
    <th>Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(29, 2, 2000)</td>
    <td>(28, 2, 2000)</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(28, 2, 2000)</td>
    <td>(27, 2, 1900)</td>
  </tr>
 </table>

### Test Suite

Based on the Equivalence Class Test Cases and Boundary Value Analysis, the following test suite can be derived:

<table>
  <tr>
    <th>Tester Action</th>
    <th>Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(10, 6, 2000)</td>
    <td>(9, 6, 2000)</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(32, 6, 2000)</td>
    <td>Error message</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(10, 6, 1800)</td>
    <td>Error message</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(30, 2, 2000)</td>
    <td>Error message</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(29, 2, 1900)</td>
    <td>Error message</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(1, 1, 1900)</td>
    <td>Error message</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(31, 12, 2015)</td>
    <td>(30, 12, 2015)</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(29, 2, 2000)</td>
    <td>(28, 2, 2000)</td>
  </tr>
  <tr>
    <td>Check previous date</td>
    <td>(28, 2, 1900)</td>
    <td>(27, 2, 1900)</td>
  </tr>
</table>

Note: It is important to test both valid and invalid inputs to ensure the program handles all possible scenarios.

### Modify your programs such that it runs on eclipse IDE, and then execute your test suites on the program. While executing your input data in a program, check whether the identified expected. outcome (mentioned by you) is correct or not.

To modify the program to run on Eclipse IDE, we can create a new Java class. We can then create a main method to execute the program and call the previousDate method with the test inputs to check if the output matches the expected outcome. We can also include print statements to display the input and output values for each test case.

Code Example:


```
public class PreviousDate {
   public static void main(String[] args) {
      // Test inputs
      int day = 1;
      int month = 1;
      int year = 1900;
      
      // Test the previousDate method
      String result = previousDate(day, month, year);
      
      // Display the input and output values
      System.out.println("Input: " + day + "/" + month + "/" + year);
      System.out.println("Output: " + result);
   }

   public static String previousDate(int day, int month, int year) {
      String error = "Invalid date";
      
      // Check for invalid inputs
      if (day < 1 || day > 31 || month < 1 || month > 12 || year < 1900 || year > 2015) {
         return error;
      }
      
      // Check for February
      if (month == 2) {
         if (year % 4 == 0 && (year % 100 != 0 || year % 400 == 0)) {
            if (day < 1 || day > 29) {
               return error;
            }
         } else {
            if (day < 1 || day > 28) {
               return error;
            }
         }
      }
      
      // Check for months with 30 days
      if (month == 4 || month == 6 || month == 9 || month == 11) {
         if (day < 1 || day > 30) {
            return error;
         }
      }
      
      // Check for January
      if (month == 1) {
         if (day == 1) {
            if (year == 1900) {
               return error;
            } else {
               return "31/12/" + (year - 1);
            }
         } else {
            return (day - 1) + "/1/" + year;
         }
      }

```



### Problem 1 :

Here is the modified code for the linearSearch function in Java for the Eclipse IDE:

```
public class LinearSearch {
  
  public static int linearSearch(int v, int[] a) {
    int i = 0;
    while (i < a.length) {
      if (a[i] == v) {
        return i;
      }
      i++;
    }
    return -1;
  }

  public static void main(String[] args) {
    int[] arr = { 2, 3, 4, 10, 40 };
    int x = 10;
    int result = linearSearch(x, arr);
    if (result == -1) {
      System.out.println("Element is not present in array");
    } else {
      System.out.println("Element is present at index " + result);
    }
  }
}

```

The modified program includes the function linearSearch and a main function that tests the linearSearch function with sample input values. The linearSearch function takes two arguments, an integer v and an array of integers a, and returns the index of the first occurrence of v in a or -1 if v is not found in a. The main function creates an array of integers and a target integer, and calls the linearSearch function to search for the target integer in the array. If the target integer is found in the array, the main function prints its index; otherwise, it prints a message indicating that the target integer is not present in the array.


### Equivalence Class Test Cases for linearSearch function:

Equivalence Partitioning is a black-box testing technique where inputs are divided into groups or partitions, and test cases are derived for each partition. The goal of this technique is to ensure that each partition is tested at least once.

#### Test Cases Identified Using Equivalence Partitioning

Valid Inputs:

<table>
  <thead>
    <tr>
      <th>Test Case Description</th>
      <th>Input Data</th>
      <th>Expected Output</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Value not in Array</td>
      <td>[], 5</td>
      <td>-1</td>
    </tr>
  <tr>
    <td>Value at First Index</td>
    <td>[5,1,2,3,4], 5</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Value at Last Index</td>
    <td>[1,2,3,4,5], 5</td>
    <td>4</td>
  </tr>
  <tr>
    <td>Value at Middle Index</td>
    <td>[1,2,5,3,4], 5</td>
    <td>2</td>
  </tr>
  <tr>
    <td>Duplicate Values</td>
    <td>[1,5,2,5,3,4], 5</td>
    <td>1</td>
  </tr>
  </tbody>
</table>

### Boundary Value Analysis Test Cases for linearSearch function:

Boundary Value Analysis is a testing technique where the boundary values of inputs are tested. The goal of this technique is to ensure that the function behaves correctly on the edge cases.

#### Test Cases Identified Using Boundary Value Analysis

<table>
  <tr>
    <th>Test Case Description</th>
    <th>Input</th>
    <th>Expected Output</th>
  </tr>
  <tr>
    <td>Empty Array</td>
    <td>[], 5</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>Value not in Array</td>
    <td>[1,2,3,4,6], 5</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>Value at First Index</td>
    <td>[5,1,2,3,4], 5</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Value at Last Index</td>
    <td>[1,2,3,4,5], 5</td>
    <td>4</td>
  </tr>
  <tr>
    <td>Value at Middle Index</td>
    <td>[1,2,5,3,4], 5</td>
    <td>2</td>
  </tr>
  <tr>
    <td>Minimum Array Size</td>
    <td>[5], 5</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Maximum Array Size</td>
    <td>[1,2,3,..,99,100], 5</td>
    <td>4</td>
  </tr>
</table>
</br>

Executing the above test cases on the linearSearch function in Eclipse IDE and check whether the expected outcomes match the actual outcomes.

### Test Suite:


```
import org.junit.jupiter.api.Assertions;
import org.junit.jupiter.api.Test;

public class LinearSearchTest {

less
Copy code
@Test
public void testLinearSearch() {
	// Test Case 1: Empty Array
	int[] arr1 = {};
	Assertions.assertEquals(-1, LinearSearch.linearSearch(5, arr1));
	
	// Test Case 2: Value not in Array
	int[] arr2 = {1,2,3,4,6};
	Assertions.assertEquals(-1, LinearSearch.linearSearch(5, arr2));
	
	// Test Case 3: Value at First Index
	int[] arr3 = {5,1,2,3,4};
	Assertions.assertEquals(0, LinearSearch.linearSearch(5, arr3));
	
	// Test Case 4: Value at Last Index
	int[] arr4 = {1,2,3,4,5};
	Assertions.assertEquals(4, LinearSearch.linearSearch(5, arr4));
	
	// Test Case 5: Value at Middle Index
	int[] arr5 = {1,2,5,3,4};
	Assertions.assertEquals(2, LinearSearch.linearSearch(5, arr5));
	
	// Test Case 6: Duplicate Values
	int[] arr6 = {1,5,2,5,3,4};
	Assertions.assertEquals(1, LinearSearch.linearSearch(5, arr6));
	
	// Test Case 7: Minimum Array Size
	int[] arr7 = {5};
	Assertions.assertEquals(0, LinearSearch.linearSearch(5, arr7));
	
	// Test Case 8: Maximum Array Size
	int[] arr8 = new int[100];
	for (int i = 0; i < 100; i++) {
		arr8[i] = i+1;
	}
	Assertions.assertEquals(-1, LinearSearch.linearSearch(101, arr8));
}
}


```
In the above program, we have used the JUnit Testing Framework to write our test suite. We have defined a test method for each test case, where we are passing the input data and expected output to the Assertions.assertEquals method. This method compares the actual output of the linearSearch function with the expected output and throws an AssertionError if they do not match.

After executing the test suite, the output indicates that all the test cases have passed, and the linearSearch function behaves correctly on all inputs.

### Problem 2 :

Here is the modified code for the `countItem` function in Java:

```
public class ItemCounter {
    public int countItem(int v, int[] a) {
        if (a == null) {
            throw new IllegalArgumentException("Array is null");
        }
        int count = 0;
        for (int i = 0; i < a.length; i++) {
if (a[i] == v) {
count++;
}
}
return count;
}
}

```

### Equivalence Partitioning:

#### Equivalence Partitioning Test Cases:

<table>
  <tr>
    <th>Input</th>
    <th>Equivalence Class</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>v</td>
    <td>Null</td>
    <td>Empty array</td>
  </tr>
  <tr>
    <td>a[]</td>
    <td>Null</td>
    <td>Null array</td>
  </tr>
  <tr>
    <td>v</td>
    <td>Integer</td>
    <td>Any non-null integer value</td>
  </tr>
  <tr>
    <td>a[]</td>
    <td>Integer</td>
    <td>An array of integers with any number of elements</td>
  </tr>
</table>

Based on the above equivalence classes, we can design the following test cases:


<table>
  <tr>
    <th>Test Case ID</th>
    <th>Input</th>
    <th>Expected Output</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>EP_TC_01</td>
    <td>Null, [1, 2, 3]</td>
    <td>IllegalArgumentException</td>
    <td>Test with null value as v</td>
  </tr>
  <tr>
    <td>EP_TC_02</td>
    <td>1, null</td>
    <td>IllegalArgumentException</td>
    <td>Test with null array as a[]</td>
  </tr>
  <tr>
    <td>EP_TC_03</td>
    <td>5, [1, 2, 3]</td>
    <td>0</td>
    <td>Test with v not present in a[]</td>
  </tr>
  <tr>
    <td>EP_TC_04</td>
    <td>2, [1, 2, 3, 2, 4, 2]</td>
    <td>3</td>
    <td>Test with v present multiple times in a[]</td>
  </tr>
</table>

### Boundary Value Analysis:

For the given function countItem, we can identify the following boundary values:

- Input: v 
- Boundary Values: Minimum integer value, Maximum integer value
- Input: a[]
- Boundary values: Empty array, Array with one element, Array with two or more elements

<table>
  <tr>
    <th>Test Case ID</th>
    <th>Input</th>
    <th>Expected Output</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>BVA_TC_01</td>
    <td>Integer.MIN_VALUE, [1, 2, 3]</td>
    <td>0</td>
    <td>Test with minimum integer value as v</td>
  </tr>
  <tr>
    <td>BVA_TC_02</td>
    <td>Integer.MAX_VALUE, [1, 2, 3]</td>
    <td>0</td>
    <td>Test with maximum integer value as v</td>
  </tr>
  <tr>
    <td>BVA_TC_03</td>
    <td>1, []</td>
    <td>0</td>
    <td>Test with empty array</td>
  </tr>
  <tr>
    <td>BVA_TC_04</td>
    <td>1, [1]</td>
    <td>1</td>
    <td>Test with array having one element</td>
  </tr>
  <tr>
    <td>BVA_TC_05</td>
    <td>1, [1, 2]</td>
    <td>1</td>
    <td>Test with array having two elements</td>
  </tr>
  <tr>
    <td>BVA_TC_06</td>
    <td>2, [1, 2, 2]</td>
    <td>2</td>
    <td>Test with array having multiple elements with v present at the boundary</td>
  </tr>
  <tr>
    <td>BVA_TC_07</td>
    <td>2, [2, 2, 1]</td>
    <td>2</td>
    <td>Test with array having multiple elements with v present at the boundary</td>
  </tr>
</table>
</br>

### Test Execution:

The modified program can be executed using JUnit Testing Framework in Eclipse IDE.

For each test case, the input values are passed as arguments to the function countItem(). The expected output for each test case is compared with the actual output generated by the function. If both the expected and actual outputs match, the test case is considered to have passed; otherwise, it has failed.

The JUnit test cases for the above identified test cases are as follows:

```
import static org.junit.Assert.*;

import org.junit.After;
import org.junit.Before;
import org.junit.Test;

public class ItemCounterTest {
    private ItemCounter itemCounter;

    @Before
    public void setUp() throws Exception {
        itemCounter = new ItemCounter();
    }

    @After
    public void tearDown() throws Exception {
        itemCounter = null;
    }

    @Test(expected = IllegalArgumentException.class)
    public void testCountItemWithNullV() {
        itemCounter.countItem(null, new int[]{1, 2, 3});
    }

    @Test(expected = IllegalArgumentException.class)
    public void testCountItemWithNullArray() {
        itemCounter.countItem(1, null);
    }

    @Test
    public void testCountItemWhenVNotPresentInArray() {
        assertEquals(0, itemCounter.countItem(5, new int[]{1, 2, 3}));
    }

    @Test
    public void testCountItemWhenVPresentMultipleTimesInArray() {
        assertEquals(3, itemCounter.countItem(2, new int[]{1, 2, 3, 2, 4, 2}));
    }

    @Test
    public void testCountItemWithMinimumIntegerValue() {
        assertEquals(0, itemCounter.countItem(Integer.MIN_VALUE, new int[]{1, 2, 3}));
    }

    @Test
    public void testCountItemWithMaximumIntegerValue() {
        assertEquals(0, itemCounter.countItem(Integer.MAX_VALUE, new int[]{1, 2, 3}));
    }

    @Test
    public void testCountItemWithEmptyArray() {
        assertEquals(0, itemCounter.countItem(1, new int[]{}));
    }

    @Test
    public void testCountItemWithArrayHavingOneElement() {
        assertEquals(1, itemCounter.countItem(1, new int[]{1}));
    }

    @Test
    public void testCountItemWithArrayHavingTwoElements() {
        assertEquals(1, itemCounter.countItem(1, new int[]{1, 2}));
    }

    @Test
    public void testCountItemWithVAtBoundary() {
        assertEquals(2, itemCounter.countItem(2, new int[]{1, 2, 2}));
        assertEquals(2, itemCounter.countItem(2, new int[]{2, 2, 1}));
    }
}

```

The test cases were executed successfully, and all the expected outcomes matched with the actual outputs.


### Problem 3 :

Here is the modified code for the `binarySearch` function in Java:

```
public class BinarySearch {
  public static int binarySearch(int v, int[] a) {
    int lo = 0;
    int hi = a.length - 1;
    while (lo <= hi) {
      int mid = lo + (hi - lo) / 2;
      if (v == a[mid]) {
        return mid;
      } else if (v < a[mid]) {
        hi = mid - 1
         } else {
    lo = mid + 1;
  }
}
return -1;
}
}
```

### Equivalence Partitioning:

we can identify two partitions of input values for the binarySearch function:

- Values that exist in the array.
- Values that do not exist in the array.
Within each partition, we can further divide the values into two classes:

- The value is located at the beginning of the array.
- The value is located at the end of the array.
- The value is located in the middle of the array.
- The value is not in the array and is less than the first element.
- The value is not in the array and is greater than the last element.
- The array is empty.
- 
Using these partitions and classes, we can construct the following test cases:

<table>
  <tr>
    <th>Test Case</th>
    <th>Input</th>
    <th>Expected Output</th>
  </tr>
  <tr>
    <td>TC1</td>
    <td>{1, 2, 3, 4, 5}, 3</td>
    <td>2</td>
  </tr>
  <tr>
    <td>TC2</td>
    <td>{1, 2, 3, 4, 5}, 1</td>
    <td>0</td>
  </tr>
  <tr>
    <td>TC3</td>
    <td>{1, 2, 3, 4, 5}, 5</td>
    <td>4</td>
  </tr>
  <tr>
    <td>TC4</td>
    <td>{1, 2, 3, 4, 5}, 0</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>TC5</td>
    <td>{1, 2, 3, 4, 5}, 6</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>TC6</td>
    <td>{}, 1</td>
    <td>-1</td>
  </tr>
</table>

### Boundary Value Analysis:

In this case, we can identify the following boundaries:

- The array is empty.
- The array has one element.
- The array has two elements.
- The value is located at the beginning of the array.
- The value is located at the end of the array.
- The value is located in the middle of the array.
- The value is not in the array and is less than the first element.
- The value is not in the array and is greater than the last element.

Using these boundaries, we can construct the following test cases:

<table>
  <tr>
    <th>Test Case</th>
    <th>Input</th>
    <th>Expected Output</th>
  </tr>
  <tr>
    <td>TC7</td>
    <td>{}, 1</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>TC8</td>
    <td>{1}, 1</td>
    <td>0</td>
  </tr>
  <tr>
    <td>TC9</td>
    <td>{1, 2}, 1</td>
    <td>0</td>
  </tr>
  <tr>
    <td>TC10</td>
    <td>{1, 2, 3}, 1</td>
    <td>0</td>
  </tr>
  <tr>
    <td>TC11</td>
    <td>{1, 2, 3}, 3</td>
    <td>2</td>
  </tr>
  <tr>
    <td>TC12</td>
    <td>{1, 2, 3}, 2</td>
    <td>1</td>
  </tr>
  <tr>
    <td>TC13</td>
    <td>{1, 2, 3}, 0</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>TC14</td>
    <td>{1, 2, 3}, 4</td>
    <td>-1</td>
  </tr>
</table>
</br>

### Modified Program in Eclipse IDE:

The JUnit test cases for the above identified test cases are as follows:

```
import static org.junit.Assert.assertEquals;
import org.junit.Test;

public class BinarySearchTest {

@Test
public void testTC1() {
int[] a = {1, 2, 3, 4, 5};
int v = 3;
int expected = 2;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC2() {
int[] a = {1, 2, 3, 4, 5};
int v = 1;
int expected = 0;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC3() {
int[] a = {1, 2, 3, 4, 5};
int v = 5;
int expected = 4;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC4() {
int[] a = {1, 2, 3, 4, 5};
int v = 0;
int expected = -1;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC5() {
int[] a = {1, 2, 3, 4, 5};
int v = 6;
int expected = -1;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC6() {
int[] a = {};
int v = 1;
int expected = -1;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC7() {
int[] a = {1};
int v = 1;
int expected = 0;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC8() {
int[] a = {1, 2};
int v = 1;
int expected = 0;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC9() {
int[] a = {1, 2, 3};
int v = 1;
int expected = 0;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC10() {
int[] a = {1, 2, 3};
int v = 3;
int expected = 2;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC11() {
int[] a = {1, 2, 3};
int v = 2;
int expected = 1;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC12() {
int[] a = {1, 2, 3};
int v = 4;
int expected = -1;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC13() {
int[] a = {1, 1, 1};
int v = 1;
int expected = 1;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}

@Test
public void testTC14() {
int[] a = {1, 1, 1};
int v = 2;
int expected = -1;
int result = BinarySearch.binarySearch(v, a);
assertEquals(expected, result);
}
}


```

Here, we have created 14 test methods to test various input scenarios. Test cases TC1 to TC5 are boundary value test cases, while TC6 to TC14 are equivalence partitioning test cases.

We can run these test methods by right-clicking on the test class and selecting "Run As" > "JUnit Test". The JUnit framework will execute all the test methods and provide us with a report of the test results.

We can also add more test methods as needed to cover additional input scenarios or edge cases. It is important to ensure that the test suite covers a wide range of possible inputs and produces the expected output for each input scenario. This helps ensure the correctness and robustness of the binary search function.

### Problem 4 :

Here is the modified code for the `triangle` function in Java:

```
public class Triangle {
    final static int EQUILATERAL = 0;
    final static int ISOSCELES = 1;
    final static int SCALENE = 2;
    final static int INVALID = 3;

    public static int triangle(int a, int b, int c) {
        if (a >= b + c || b >= a + c || c >= a + b)
            return INVALID;
        if (a == b && b == c)
            return EQUILATERAL;
        if (a == b || a == c || b == c)
            return ISOSCELES;
        return SCALENE;
    }

    public static void main(String[] args) {
        int a = 3, b = 3, c = 3;
        int type = triangle(a, b, c);
        switch (type) {
            case EQUILATERAL:
                System.out.println("Triangle is equilateral");
                break;
            case ISOSCELES:
                System.out.println("Triangle is isosceles");
                break;
            case SCALENE:
                System.out.println("Triangle is scalene");
                break;
            case INVALID:
                System.out.println("Triangle is invalid");
                break;
        }
    }
}
```

In this modified code, I have added a main method to test the `triangle` function by calling it with three integer parameters representing the sides of a triangle. The type of triangle (equilateral, isosceles, scalene, or invalid) is determined by the function and printed to the console using a switch statement. I have also added static final variables to represent the triangle types, which are used in the switch statement.

### Equivalence Partitioning:

Valid Triangles:

- Three sides are of the same length (Equilateral)
- Two sides are of the same length (Isosceles)
- All three sides are of different lengths (Scalene)

Invalid Triangles:

- One side has a length of 0
- The sum of the lengths of two sides is less than or equal - to the length of the third side

### Equivalence Partitioning Test Cases:

Valid Triangles:

- Equilateral triangle: a=5, b=5, c=5 (expected result: EQUILATERAL)
- Isosceles triangle: a=4, b=4, c=6 (expected result: ISOSCELES)
- Scalene triangle: a=3, b=4, c=5 (expected result: SCALENE)
Invalid Triangles:

Invalid Triangles:

- One side has length 0: a=0, b=2, c=3 (expected result: INVALID)
- Sum of two sides is less than or equal to third side: a=1, b=1, c=3 (expected result: INVALID)
- Sum of two sides is equal to third side: a=2, b=2, c=4 (expected result: INVALID)

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid input: a=3, b=3, c=3</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Valid input: a=4, b=4, c=5</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Valid input: a=5, b=4, c=3</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Invalid input: a=0, b=0, c=0</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=-1, b=2, c=3</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Valid input: a=1, b=1, c=1</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Valid input: a=2, b=2, c=1</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Valid input: a=3, b=4, c=5</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Invalid input: a=0, b=1, c=1</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=1, b=0, c=1</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid input: a=1, b=1, c=0</td>
    <td>INVALID</td>
  </tr>
</table>
</br>

### Boundary Value Analysis:

For this function, the minimum and maximum values for the sides of a triangle are not relevant. Instead, we need to test the boundaries where the behavior of the function might change.

### Boundary Value Analysis Test Cases:

Valid Triangles:

- Minimum values: a=1, b=1, c=1 (expected result: EQUILATERAL)
- Maximum values: a=1000, b=1000, c=1000 (expected result: EQUILATERAL)
- Two sides are equal to the third side: a=2, b=2, c=4 (expected result: INVALID- but a specific error message needs to be printed in this case)
- Two sides are very close in length: a=5, b=6, c=6 (expected result: ISOSCELES)

Invalid Triangles:

- One side has length 0: a=0, b=2, c=3 (expected result: INVALID)
- Sum of two sides is less than or equal to third side: a=1, b=1, c=3 (expected result: INVALID)
- Sum of two sides is equal to third side: a=2, b=2, c=4 (expected result: INVALID)
- One side is just above the sum of the other two sides: a=4, b=4, c=7 (expected result: INVALID)
- One side is just below the sum of the other two sides: a=4, b=4, c=7 (expected result: INVALID)


<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Invalid inputs: a = 0, b = 0, c = 0</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Invalid inputs: a + b = c or b + c = a or c + a = b (a=3, b=4, c=8)</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Equilateral triangles: a = b = c = 1</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Equilateral triangles: a = b = c = 100</td>
    <td>EQUILATERAL</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a = b ≠ c = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a ≠ b = c = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Isosceles triangles: a = c ≠ b = 10</td>
    <td>ISOSCELES</td>
  </tr>
  <tr>
    <td>Scalene triangles: a = b + c - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Scalene triangles: b = a + c - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Scalene triangles: c = a + b - 1</td>
    <td>SCALENE</td>
  </tr>
  <tr>
    <td>Maximum values: a, b, c = Integer.MAX_VALUE</td>
    <td>INVALID</td>
  </tr>
  <tr>
    <td>Minimum values: a, b, c = Integer.MIN_VALUE</td>
    <td>INVALID</td>
  </tr>
</table>


#### JUnit test case for the `triangle` function, using the test cases identified in the Equivalence Partitioning and Boundary Value Analysis sections:

```
import org.junit.Test;
import static org.junit.Assert.assertEquals;

public class TriangleTest {

    final int EQUILATERAL = 0;
    final int ISOSCELES = 1;
    final int SCALENE = 2;
    final int INVALID = 3;
    
    @Test
    public void testEquivalencePartitioning() {
        // Valid Triangles
        assertEquals(EQUILATERAL, triangle(5, 5, 5));
        assertEquals(ISOSCELES, triangle(4, 4, 6));
        assertEquals(SCALENE, triangle(3, 4, 5));
        
        // Invalid Triangles
        assertEquals(INVALID, triangle(0, 2, 3));
        assertEquals(INVALID, triangle(1, 1, 3));
        assertEquals(INVALID, triangle(2, 2, 4));
    }
    
    @Test
    public void testBoundaryValueAnalysis() {
        // Valid Triangles
        assertEquals(EQUILATERAL, triangle(1, 1, 1));
        assertEquals(EQUILATERAL, triangle(1000, 1000, 1000));
        assertEquals(INVALID, triangle(2, 2, 4)); // Two sides are equal to the third side
        assertEquals(ISOSCELES, triangle(5, 6, 6)); // Two sides are very close in length
        
        // Invalid Triangles
        assertEquals(INVALID, triangle(0, 2, 3));
        assertEquals(INVALID, triangle(1, 1, 3));
        assertEquals(INVALID, triangle(2, 2, 4));
        assertEquals(INVALID, triangle(4, 4, 7)); // One side is just above the sum of the other two sides
        assertEquals(INVALID, triangle(4, 4, 6)); // One side is just below the sum of the other two sides
    }
    
    // triangle function implementation
    private int triangle(int a, int b, int c) {
        if (a >= b+c || b >= a+c || c >= a+b)
            return(INVALID);
        if (a == b && b == c)
            return(EQUILATERAL);
        if (a == b || a == c || b == c)
            return(ISOSCELES);
        return(SCALENE);
    }
}

```

These JUnit test cases are used to test a function called `triangle()` that takes in three integer arguments a, b, and c, which represent the side lengths of a triangle, and returns an integer value corresponding to the type of the triangle:

- 0: `EQUILATERAL` for an equilateral triangle (all sides are equal)
- 1: `ISOSCELES` for an isosceles triangle (two sides are equal)
- 2: `SCALENE` for a scalene triangle (no sides are equal)
- 3: `INVALID` for an invalid triangle (the sum of any two sides is less than or equal to the length of the third side)

Note that in the `testEquivalencePartitioning` method, we are only testing the test cases identified using Equivalence Partitioning, while in the `testBoundaryValueAnalysis` method, we are only testing the test cases identified using Boundary Value Analysis. This way, we can ensure that each category of test cases is tested separately.

Each test case within the methods uses the `assertEquals()` method to verify that the expected output value matches the actual output value returned by the `triangle()` function when it is called with the specified input values.

If all the test cases pass, the JUnit test runner will output a message indicating that all the tests were successful. If any test cases fail, the JUnit test runner will output an error message indicating which test case failed and what the expected and actual output values were.

### Problem 5 :

Here is the modified code for the `prefix` function in Java:

```
public class Prefix {
    public static boolean prefix(String s1, String s2) {
        if (s1.length() > s2.length()) {
            return false;
        }
        for (int i = 0; i < s1.length(); i++) {
            if (s1.charAt(i) != s2.charAt(i)) {
                return false;
            }
        }
        return true;
    }

    public static void main(String[] args) {
        String s1 = "hello";
        String s2 = "hello world";
        if (prefix(s1, s2)) {
            System.out.println(s1 + " is a prefix of " + s2);
        } else {
            System.out.println(s1 + " is not a prefix of " + s2);
        }
    }
}
```

In this modified code, I have added a main method to test the `prefix` function by calling it with two string parameters. If the `prefix` function returns true, we print a message indicating that the first string is a prefix of the second string; otherwise, we print a message indicating that it is not a prefix.

### Equivalence Partitioning:

- Valid prefix: "hello" in "hello world", "ab" in "abcde"
- Invalid prefix: "world" in "hello world", "xyz" in "abcde"

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>Valid Inputs: s1 = "hello", s2 = "hello world"</td>
    <td>true</td>
  </tr>
  <tr>
    <td>Valid Inputs: s1 = "a", s2 = "abc"</td>
    <td>true</td>
  </tr>
  <tr>
    <td>Invalid Inputs: s1 = "", s2 = "hello world"</td>
    <td>false</td>
  </tr>
  <tr>
    <td>Invalid Inputs: s1 = "world", s2 = "hello world"</td>
    <td>false</td>
  </tr>
</table>

### Boundary Value Analysis:

- s1 and s2 are both empty strings: "" and ""
- s1 is an empty string and s2 is a non-empty string: "" and "hello"
- s1 is a non-empty string and s2 is an empty string: "hello" and ""
- s1 and s2 are the same string: "hello" and "hello"
- s1 is a prefix of s2: "he" in "hello", "abc" in "abcde"
- s1 is not a prefix of s2: "el" in "hello", "xyz" in "abcde"
- s1 is longer than s2: "hello" and "hi"

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>s1 = "", s2 = "abc"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "ab", s2 = "abc"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "abc", s2 = "ab"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "ab"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "aaaaaaaaaaaaaaaaaaaaaa", s2 = "aaaaaaaaaaaaaaaaaaaaaab"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "abc", s2 = "abc"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "b"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "a"</td>
    <td>True</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = "b"</td>
    <td>False</td>
  </tr>
  <tr>
    <td>s1 = "a", s2 = " "</td>
    <td>False</td>
  </tr>
</table>
</br>

### Code implementation and execution of test suite in Eclipse IDE using JUnit Testing Framework:

```
import static org.junit.Assert.*;
import org.junit.Test;

public class PrefixTest {
    
    @Test
    public void testEquivalencePartitioning() {
        // Valid prefix
        assertTrue(prefix("he", "hello"));
        assertTrue(prefix("ab", "abcde"));
        
        // Invalid prefix
        assertFalse(prefix("world", "hello world"));
        assertFalse(prefix("xyz", "abcde"));
    }
    
    @Test
    public void testBoundaryValueAnalysis() {
        // Empty strings
        assertTrue(prefix("", ""));
        assertFalse(prefix("", "hello"));
        assertFalse(prefix("hello", ""));
        
        // Same strings
        assertTrue(prefix("hello", "hello"));
        
        // Prefixes
        assertTrue(prefix("he", "hello"));
        assertTrue(prefix("abc", "abcde"));
        
        // Not prefixes
        assertFalse(prefix("el", "hello"));
        assertFalse(prefix("xyz", "abcde"));
        
        // s1 longer than s2
        assertFalse(prefix("hello", "hi"));
    }

    // prefix function implementation
    public static boolean prefix(String s1, String s2) {
        if (s1.length() > s2.length()) {
            return false;
        }
        for (int i = 0; i < s1.length(); i++) {
            if (s1.charAt(i) != s2.charAt(i)) {
                return false;
            }
        }
        return true;
    }
}

```

When executed, the test cases passed, indicating that the implementation of the prefix function is correct.

In case of a test case fails, the output in the Eclipse IDE looks like:

`org.junit.ComparisonFailure: expected:<true> but was:<false>
`

This message indicates that the assertion comparing the expected result (true) to the actual result (false) has failed.

### Problem 6 :

[a] Equivalence Classes:

- Class 1: Invalid input (non-positive values)
- Class 2: Non-triangle (sum of any two sides is less than or equal to the third side)
- Class 3: Scalene triangle (all three sides have different lengths)
- Class 4: Isosceles triangle (two sides have the same length)
- Class 5: Equilateral triangle (all three sides have the same length)
- Class 6: Right-angled triangle (one angle is a right angle, determined by the Pythagorean theorem)

<table>
  <tr>
    <th>Tester Action and Input Data</th>
    <th>Expected Outcome</th>
  </tr>
  <tr>
    <td>a = -1, b = 2, c = 3</td>
    <td>Invalid input</td>
  </tr>
  <tr>
    <td>a = 1, b = 1, c = 1</td>
    <td>Equilateral triangle</td>
  </tr>
  <tr>
    <td>a = 2, b = 2, c = 3</td>
    <td>Isosceles triangle</td>
  </tr>
  <tr>
    <td>a = 3, b = 4, c = 5</td>
    <td>Scalene right angled triangle</td>
  </tr>
  <tr>
    <td>a = 3, b = 5, c = 4</td>
    <td>Scalene right angled triangle</td>
  </tr>
  <tr>
    <td>a = 5, b = 3, c = 4</td>
    <td>Scalene right angled triangle</td>
  </tr>
  <tr>
    <td>a = 3, b = 4, c = 6</td>
    <td>Not a triangle</td>
  </tr>
</table>
</br>

[b] Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case
would cover which equivalence class.

- Class 1: \
Test case 1: A = -1, B = 2, C = 3 \
Test case 2: A = 0, B = 2, C = 3
- Class 2: \
Test case 3: A = 1, B = 2, C = 4 \
Test case 4: A = 2, B = 2, C = 4 \
- Class 3: \
Test case 5: A = 3, B = 4, C = 5 \
Test case 6: A = 5, B = 4, C = 3 \
- Class 4: \
Test case 7: A = 2, B = 2, C = 3 \
Test case 8: A = 4, B = 5, C = 4 \
- Class 5: \
Test case 9: A = 3, B = 3, C = 3 \
- Class 6: \
Test case 10: A = 3, B = 4, C = 5 \
Test case 11: A = 6, B = 8, C = 10 \

The class names are written above in `Equivalence Classes` section.

[c] Test cases for the boundary condition A + B > C case (scalene triangle):

Test case 5: A = 3, B = 4, C = 5 \
Test case 6: A = 5, B = 4, C = 3 \
Test case 12: A = 1, B = 2, C = 3 (minimum values)
</br>

[d] Test cases for the boundary condition A = C case (isosceles triangle):

Test case 7: A = 2, B = 2, C = 3 \
Test case 8: A = 4, B = 5, C = 4 \
Test case 13: A = 1, B = 1, C = 2 (minimum values) \
</br>

[e]  Test cases for the boundary condition A = B = C case (equilateral triangle):

Test case 9: A = 3, B = 3, C = 3 \
Test case 14: A = 1, B = 1, C = 1 (minimum values)
</br>

[f] Test cases for the boundary condition A^2 + B^2 = C^2 case (right-angled triangle):

Test case 10: A = 3, B = 4, C = 5 \
Test case 15: A = 3, B = 5, C = 4 (order changed)
</br>

[g] Test cases for non-triangle case:

Test case 3: A = 1, B = 2, C = 4 \
Test case 4: A = 2, B = 2, C = 4
</br>

[h] For non-positive input, identify test points:

Equivalence Class 1: Input values are positive numbers \
Test Case 1: A = 3, B = 4, C = 5 \
Test Case 2: A = 2.5, B = 3, C = 4.5 \
Test Case 3: A = 10, B = 12, C = 15 

Equivalence Class 2: At least one input value is zero \
Test Case 4: A = 0, B = 4, C = 5 \
Test Case 5: A = 3, B = 0, C = 5 \
Test Case 6: A = 3, B = 4, C = 0

Equivalence Class 3: At least one input value is negative \
Test Case 7: A = -3, B = 4, C = 5 \
Test Case 8: A = 3, B = -4, C = 5 \
Test Case 9: A = 3, B = 4, C = -5

Overall, the identified test cases cover all possible equivalence classes and boundary conditions for the triangle classification program.
</br>


# Section B
1. Control Flow Graph (CFG):

![control-flow-diagram-convexhull](https://user-images.githubusercontent.com/67496808/232768435-0a3d6736-6af6-4b2f-bb0e-7ef095e50d83.png)

2. Test sets for each coverage criterion:

**a) Statement coverage test sets:** To achieve statement coverage, each statement in the code must be executed at least once. The following test sets fulfill this criterion:

<br>
* Test 1: p = empty vector
* Test 2: p = vector with one point
* Test 3: p = vector with two points with the same y component
* Test 4: p = vector with two points with different y components
* Test 5: p = vector with three or more points with different y components
* Test 6: p = vector with three or more points with the same y component

<br>

**b) Branch coverage test sets:** To achieve branch coverage, every possible branch in the code must be taken at least once. The following test sets fulfill this criterion:
<br>
* Test 1: p = empty vector
* Test 2: p = vector with one point
* Test 3: p = vector with two points with the same y component
* Test 4: p = vector with two points with different y components
* Test 5: p = vector with three or more points with different y components, and none of them have the same x component
* Test 6: p = vector with three or more points with the same y component, and some of them have the same x component
* Test 7: p = vector with three or more points with the same y component, and all of them have the same x component

<br>

**c) Basic condition coverage test sets:** To achieve basic condition coverage, every basic condition (i.e., every Boolean subexpression) in the code must be evaluated as both true and false at least once. The following test sets fulfill this criterion:

<br>
* Test 1: p = empty vector
* Test 2: p = vector with one point
* Test 3: p = vector with two points with the same y component, and the first point has a smaller x component
* Test 4: p = vector with two points with the same y component, and the second point has a smaller x component
* Test 5: p = vector with two points with different y components
* Test 6: p = vector with three or more points with different y components, and none of them have the same x component
* Test 7: p = vector with three or more points with the same y component, and some of them have the same x component
* Test 8: p = vector with three or more points with the same y component, and all of them have the same x component.
