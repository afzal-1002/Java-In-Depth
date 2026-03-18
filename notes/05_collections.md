# Arrays

**Definition:**  
A container **object** that holds a **fixed** number of values of a **single type**.

- **Container** – a structure used to store elements
- **Object** – the array itself is treated as an object
- **Fixed number of values** – the size of an array cannot change after creation
- **Single type** – all elements in the array must be of the same data type

int arr[] = new int[4];
int arr[] = {1,2,3};
int arr[];

arr = new int[4];

int[] arrays = new int[5];
int[] arrays = new int[]{4,5,6,7,8};

arr.length;

---

## Functions:

**Access Element**
arr[0];

**Update Element**
arr[0] = 10;

**Traverse**
for(int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}

for(int value : arr) {
    System.out.println(value);
}

**Sort**
import java.util.Arrays;
Arrays.sort(arr);

**Search**
// Linear Search
for(int i = 0; i < arr.length; i++) {
    if(arr[i] == 3) break;
}

// Binary Search
Arrays.binarySearch(arr, 3);

**Copy**
int[] newArr = Arrays.copyOf(arr, arr.length);

**Compare**
Arrays.equals(arr1, arr2);

**Fill**
Arrays.fill(arr, 5);

**Convert to String**
Arrays.toString(arr);

**2D Array**
int[][] matrix = new int[2][3];

**Pass Array to Function**
void print(int[] arr) {
    for(int i : arr) {
        System.out.println(i);
    }
}

**Return Array**
int[] create() {
    return new int[]{1,2,3};
}