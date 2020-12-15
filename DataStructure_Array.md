## Introduction of Array
An array is a set of elements that represented by a single variable name and stored at contiguous memory addresses. This makes it easy to calculate the address of each element by adding an offset to a base value, i.e., the memory address of the first element of the array, which is usually denoted by the name of the array.

## Concepts of Array
1. Element </br>
   An individual data item of an array is called an element. All elements of an array must be of the same type or derived from the same type.
    ```C#
    int[] arr = new int[] { 1, 2, 3.0 }; // compile ok
    double[] arr = new double[] { 1, 2, 3.0 }; // compile ok. 1 and 2 are implicitly converted to double type.
    double[] arr = new double[] { 1, 2, 3.0 }; // compile ok
    int[] arr = new int[] { 1, 2, 3.0 }; // complie error. Can't implicitly convert type 'double' to 'int'.
    ``` 

2. Rank/Dimension </br>
   Array can have any positive number of dimensions. The number of dimensions is called rank (秩).
    ```C#
    int[] arr1 = new int[] { 1, 2, 3 };
    int rank1 = arr1.Rank; // 1

    int[,] arr2 = new int[,] { { 1, 2, 3 }, { 4, 5, 6 } };
    int rank2 = arr2.Rank; // 2
    ```
3. Dimension length </br>
   The number of elements of given dimension.
    ```C#
    int[,] arr = new int[,] { { 1, 2, 3 }, { 4, 5, 6 } };
    int length0 = arr.GetLength(0); // 2
    int length1 = arr.GetLength(1); // 3
    ```
    
4. Array length </br>
   The total number of elements contained in an array, in all dimensions.
    ```C#
    int[,] arr = new int[,] { { 1, 2, 3 }, { 4, 5, 6 } };
    int length = arr.Length; // 6
    ```

## Array is reference data structure
Although elements of Array can be either value type or reference type, Array itself is reference type. Reference type varaible uses a reference holding the memory address of the object but not the object itself. Assigning a reference variable to another creates a copy of the reference instead of copying the objects, thus changing objects by using one reference will impact the other reference.

  ```C#
  int[] arr1 = new int[] { 1, 2, 3 };
  int[] arr2 = arr1;
  arr2[0] = 4;
  Console.WriteLine(arr1[0]); // 4
  ```

## Access Array Element
An array element can be accessed by using the index, which denotes the relative position to the start memory address. For example, ```arr[0]``` is 0 position away from the start memory address, ```arr[3]``` is 3 positions away from the start memory address, etc.

Each dimension uses 0-based indexing and the main reason is this can avoid ```-``` operations when calculating elements' actual memory addresses. For example, first element's memory address is ```&arr```. If we count the indexes starting from 1, then the memory address of the first element ```arr[1]``` will be calculated as ```&arr + 1```, which is incorrect. In order to get the correct memory address, CPU will have to execute a ```-``` operation, i.e., ```&arr + 1 - 1```. 

Dijkstra also explains why we should use 0-based indexing in https://www.cs.utexas.edu/users/EWD/transcriptions/EWD08xx/EWD831.html.
