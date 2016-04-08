<!-- section start -->
<!-- attr: { id:'', class:'slide-title', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Multidimensional Arrays
## Processing Matrices and Multidimensional Tables
<img class="slide-image" src="imgs/pic00.png" style="top:52.89%; left:66.12%; width:36.44%; z-index:-1" />
<img class="slide-image" src="imgs/pic01.png" style="top:5%; left:5%; width:16.03%; z-index:-1" />
<img class="slide-image" src="imgs/pic03.png" style="top:40%; left:0%; width:26.89%; z-index:-1" />




<!-- section start -->
<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Table of Contents
- Matrices and Multidimensional Arrays
  - Declaring
  - Usage 
- Jagged Arrays
  - Declaring
  - Usage
- The **Array** Class
  - Sorting
  - Binary Search
<img class="slide-image" src="imgs/pic04.png" style="top:45%; left:73.92%; width:27.99%; z-index:-1" />
<img class="slide-image" src="imgs/pic05.png" style="top:20%; left:79.78%; width:13%; z-index:-1" />




<!-- section start -->
<!-- attr: { id:'', class:'slide-section', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Multidimensional Arrays 
## Using Array of Arrays, Matrices and Cubes
<img class="slide-image" src="imgs/pic06.png" style="top:55%; left:34%; width:30%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# What is Multidimensional Array?
- **Multidimensional arrays** have more than one dimension (2, 3, …)
  - The most important multidimensional arrays are the 2-dimensional
    - Known as **matrices** or **tables**
- _Example_ of matrix of integers with 2 rows and 4 columns:
<img class="slide-image" src="imgs/example-marray.png" style="top:60%; left:30%; width:40%; z-index:-1" />

<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Declaring and Creating Multidimensional Arrays
- Declaring multidimensional arrays:
```cs
int[,] intMatrix;
float[,] floatMatrix;
string[,,] strCube;
```
- Creating a multidimensional array
  - Use **new** keyword
  - Must specify the size of each dimension
```cs
int[,] intMatrix = new int[3, 4];
float[,] floatMatrix = new float[8, 2];
string[,,] stringCube = new string[5, 5, 5];
```



<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Initializing Multidimensional Arrays with Values
- Creating and initializing with values multidimensional array:
```cs
int[,] matrix = 
{
    {1, 2, 3, 4}, // row 0 values
    {5, 6, 7, 8}, // row 1 values
}; // The matrix size is 2 x 4 (2 rows, 4 cols)
```
  - Matrices are represented by a list of rows
    - Rows consist of list of values
  - The first dimension comes first, the second comes next (inside the first)



<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Accessing The Elements of Multidimensional Arrays
- Accessing N-dimensional array element:
```cs
nDimensionalArray[index1, … , indexn]
```
- Getting element value example:
```cs
int[,] array = {{1, 2}, {3, 4}}
int element11 = array[1, 1]; // element11 = 4
```
- Setting element value example:
```cs
int[,] array = new int[3, 4];
for (int row=0; row<array.GetLength(0); row++)
  for (int col=0; col<array.GetLength(1); col++)
    array[row, col] = row + col;
```

<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Reading a Matrix – _Example_
- Reading a matrix from the console

```cs
int rows = int.Parse(Console.ReadLine());
int columns = int.Parse(Console.ReadLine());

int[,] matrix = new int[rows, columns];

for (int row = 0; row  <rows; row++)
{
  for (int column = 0; column < cols; column++)
  {
    Console.Write("matrix[{0},{1}] = ", row, column);
    matrix[row, column] = int.Parse(Console.ReadLine());
  }
}
```



<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Printing Matrix – _Example_
- Printing a matrix on the console:

```cs
for (int row = 0; row < matrix.GetLength(0); row++)
{
  for (int col = 0; col < matrix.GetLength(1); col++)
  {
    Console.Write("{0, 4}", matrix[row, col]);
  }
  
  Console.WriteLine();
}
```



<!-- attr: { id:'', class:'slide-section demo', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Reading and Printing Matrices
## [Live Demo]()
<img class="slide-image" src="imgs/pic07.png" style="top:55%; left:35%; width:30%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Maximal Platform – _Example_
- Finding a 2 x 2 platform in a matrix with a maximal sum of its elements

```cs
int[,] matrix = 
{
  {7, 1, 3, 3, 2, 1},
  {1, 3, 9, 8, 5, 6},
  {4, 6, 7, 9, 1, 0} 
};
int bestSum = int.MinValue;
for (int row = 0; row < matrix.GetLength(0) - 1; row++)
{
  for (int col = 0; col < matrix.GetLength(1) - 1; col++)
  {
    int sum = matrix[row, col] + matrix[row, col+1] + 
              matrix[row+1, col] + matrix[row+1, col+1];
    if (sum > bestSum)
      bestSum = sum;
  }
}
```



<!-- attr: { id:'', class:'slide-section demo', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Maximal Platform
## [Live Demo]()
<img class="slide-image" src="imgs/pic08.png" style="top:55%; left:35%; width:30%; z-index:-1" />




<!-- section start -->
<!-- attr: { id:'', class:'slide-section', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Jagged Arrays
## What are Jagged Arrays and How to Use Them?
<img class="slide-image" src="imgs/pic09.png" style="top:54%; left:62%; width:30%; z-index:-1" />
<img class="slide-image" src="imgs/pic10.png" style="top:55%; left:13.02%; width:44.15%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Jagged Arrays
- Jagged arrays are like multidimensional arrays
  - But each dimension has different size
  - A jagged array is array of arrays
  - Each of the arrays has it's own length
- How to create jagged array?
<div style="position: absolute; top: 60%; left: 0%; width: 60%">
```cs
int[][] jagged = new int[3][];
jagged[0] = new int[3];
jagged[1] = new int[2];
jagged[2] = new int[5];
```
</div>
<img class="slide-image" src="imgs/pic11.png" style="top:29.48%; left:75.79%; width:27.16%; z-index: 1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Initialization of Jagged Arrays
- When creating jagged arrays
  - Initially the array is created of **null** arrays
    - all .NET arrays are reference types - [**read more**](https://msdn.microsoft.com/en-us/library/bb985948.aspx)
  - Need to initialize each one of them

```cs
int n = int.Parse(Console.ReadLine());
int[][] jaggedArray = new int[n][];

for (int i = 0; i < n; i++)
{
   jaggedArray[i] = new int[i];
}
```



<!-- attr: { id:'', class:'slide-section demo', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Jagged Arrays
## [Live Demo]()
<img class="slide-image" src="imgs/pic12.png" style="top:55%; left:45.38%; width:30%; z-index:-1" />
<img class="slide-image" src="imgs/pic13.png" style="top:55%; left:25%; width:15%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# _Example_ of Jagged Arrays
- Check a set of numbers and group them by their remainder when divided by 3 (0, 1 and 2)
- _Example_: 0, 1, 4, 113, 55, 3, 1, 2, 66, 557, 124, 2
- First we need to count the numbers
  - Done with a iteration
- Allocate jagged arrays with the appropriate size
- Each number is addedinto its jagged array
<img class="slide-image" src="imgs/pic14.png" style="top:65%; left:66.93%; width:33.91%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# _Example_ of Jagged Arrays

```cs
int[] numbers = {0, 1, 4, 113, 55, 3, 1, 2, 66, 557, 124, 2};
int[] sizes = new int[3];
int[] offsets = new int[3];
foreach (var number in numbers)
{
   int remainder = number % 3;
   sizes[remainder]++;
}
int[][] numbersByRemainder = new int[3][] 
{ 
  new int[sizes[0]], 
  new int[sizes[1]],
  new int[sizes[2]] 
};
foreach (var number in numbers)
{
   int remainder = number % 3; 
   int index = offsets[remainder];
   numbersByRemainder[remainder][index] = number;
   offsets[remainder]++;
}
```

<img class="slide-image" src="imgs/pic15.png" style="top:30%; left:65.50%; width:33.91%; z-index: 1" />


<!-- attr: { id:'', class:'slide-section demo', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Remainders of 3
## [Live Demo]()
<img class="slide-image" src="imgs/pic16.png" style="top:55%; left:25%; width:50%; z-index:-1" />




<!-- section start -->
<!-- attr: { id:'', class:'slide-section', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Array Class
## What Can We Use?
<img class="slide-image" src="imgs/pic17.png" style="top:55%; left:42.5%; width:15%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# The Array Class
- The **System.Array** class
  - Parent of all arrays
  - All arrays inherit from it
  - All arrays have the same:
    - Basic functionality
    - Basic properties
    - E.g. **Length** property
<img class="slide-image" src="imgs/pic18.png" style="top:15.87%; left:74.85%; width:25.81%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Methods of Array
- Important methods and properties of **System.Array**
  - **Rank** – number of dimensions
  - **Length** – number of all elements through all dimensions
  - **GetLength(index)** – returns the number of elements in the specified dimension
    - Dimensions are numbered from 0
    - **_Example_**: for a 2D array, GetLength(0) returns the rows count and GetLength(1) returns the columns count


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
<!-- # Methods of Array -->
- **GetEnumerator()** – returns **IEnumerator** for the array elements 
- **BinarySearch(…)** – searches for a given element into a sorted array (uses binary search)
- **IndexOf(…)** – searches for a given element and returns the index of the first occurrence (if any)
- **LastIndexOf(…)** – searches for a given element and returns the last occurrence index
- **Copy(src,** **dest,** **len)** – copies array elements; has many overloads


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
<!-- # Methods of Array -->
- **Reverse(…)** – inverts the arrays elements upside down
- **Clear(…)** – assigns value 0 (null) for each elements
- **CreateInstance(…)** – creates an array
  - Accepts as parameters the number of dimensions, start index and number of elements
- Implements **ICloneable**, **IList**, **ICollection** and **IEnumerable** interfaces




<!-- section start -->
<!-- attr: { id:'', class:'slide-section', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Sorting Arrays
<img class="slide-image" src="imgs/pic19.png" style="top:40%; left:30%; width:40%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Sorting Arrays
- Sorting in .NET is usually done with **System.Array.Sort()**
  - **Sort(Array)** – sorts array elements
    - Elements should implement **IComparable**
  - **Sort(Array,** **IComparer)** – sorts array elements by given external **IComparer**
  - **Sort(Array,** **Comparison<T>)** – sorts array elements by given comparison operation
    - Can be used with lambda expression


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Sorting Arrays – _Example_ 

```cs
static void Main()
{
    string[] beers =
    {
        "Zagorka", "Ariana", "Shumensko",
        "Astika", "Kamenitza", "Bolqrka",
        "Amstel"
    };
    Console.WriteLine("Unsorted: {0}", string.Join(", ", beers));
    // Elements of beers array are of string type,
    // which implement IComparable
    Array.Sort(beers);
    Console.WriteLine("Sorted: {0}", string.Join(", ", beers));
    // Result: Sorted: Amstel, Ariana, Astika,
    // Bolyarka, Kamenitza, Shumensko, Zagorka
}
```

<img class="slide-image" src="imgs/pic20.png" style="top:50%; left:90%; width:19.76%; z-index: 1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Sorting with IComparer<T> and Lambda Expressions – _Example_

```cs
class Student 
{
    public int Age { get; set; }
    …
}
public class StudentAgeComparer : IComparer<Student>
{
    public int Compare(Student first, Student second)
    {
       return first.Age.CompareTo(second.Age);
    }
}
…
// using IComparer<Student>
Array.Sort(students, new StudentAgeComparer());
…
// using lambda expression
Array.Sort(students, (x, y) => x.Name.CompareTo(y.Name));
```



<!-- attr: { id:'', class:'slide-section demo', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Sorting with **IComparer<T>** and Lambda Expressions
## [Live Demo]()
<img class="slide-image" src="imgs/pic21.png" style="top:65%; left:25%; width:14.5%; z-index:-1" />
<img class="slide-image" src="imgs/pic22.png" style="top:65%; left:53.83%; width:23%; z-index:-1" />




<!-- section start -->
<!-- attr: { id:'', class:'slide-section', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Binary Search
<img class="slide-image" src="imgs/pic23.png" style="top:45%; left:30%; width:40%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Binary Search
- Binary search is a fast method for searching for an element in a sorted array
  - Has guaranteed running time of **O(log(n))** for searching among arrays of with **n** elements
- Implemented in the **Array.BinarySearch( Array,** **object)** method
  - Returns the index of the found object or a negative number when not found


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
<!-- # Binary Search -->
- All requirements of the **Sort()** method are applicable for **BinarySearch()**
  -  Either all elements should implement **IComparable<T>** or instance of **IComparer<T>** should be passed


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Binary Search – _Example_

```cs
static void Main()
{
    string[] beers = 
    {
      "Zagorka", "Ariana", "Shumensko",
      "Astika", "Kamenitza", "Bolqrka",
      "Amstel"
    };
    Array.Sort(beers);
    
    string target = "Astika";
    
    int index = Array.BinarySearch(beers, target);
    Console.WriteLine("{0} found at index {1}", target, index);
    // Result: Astika found at index 2
    
    target = "Heineken";
    index = Array.BinarySearch(beers, target);
    Console.WriteLine("{0} not found (index={1})", target, index);
    // Result: Heineken not found (index=-5)
}
```



<!-- attr: { id:'', class:'slide-section demo', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Binary Search
## [Live Demo]()
<img class="slide-image" src="imgs/pic25.png" style="top:55%; left:15%; width:70%; z-index:-1" />




<!-- section start -->
<!-- attr: { id:'', class:'slide-section', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Working with Arrays
## Best Practices
<img class="slide-image" src="imgs/pic26.png" style="top:52%; left:30%; width:40%; z-index:-1" />


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'False', style:'font-size: 42px' } -->
# Advices for Working with Arrays
- When given method returns an array and should return an empty array (array with 0 elements) instead of **null**
- Arrays are passed by reference
  - To be sure that given method will not change the passed array, pass a copy of it
- **Clone()** returns shallow copy of the array
  - You should implement your own deep clone when working with reference types


<!-- attr: { id:'', class:'', showInPresentation:'True', hasScriptWrapper:'True', style:'font-size: 42px' } -->
# Arrays
<img class="slide-image" src="https://raw.githubusercontent.com/TelerikAcademy/Common/master/revealjs-theme/css/imgs/questions-ninja.png" style="width:70%; top:15%; left:10%" />
<div style="position: absolute; bottom: 1em; right: 0; font-size: 26px;">http://academy.telerik.com</div>