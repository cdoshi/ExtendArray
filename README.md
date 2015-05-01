# ExtendArray
Tiny library (< 9Kb) to perform basic matrix operations using JavaScript.
Download the repo and open index.html to see it in action
## Usage
Include it in your application using following syntax
```javascript
<script type="text/javascript" src="js/extendArray.js"></script>
```

## Functions
Unless expicitly mentioned, the functions work for any higher dimensional array (A x B x C x ....). Some functions support only upto 2 dimensions (A x B). All operations return a new array and do not modify existing array

- dimensions(arr). Provide dimensions of the array.
- initialize(arr, type). Initialize an array with dimensions provided and filled with required type. type can be 'ones', 'zeros','rands' (for random numbers), 'undefined'. arr is an array
- dotOperation(arr, arr1, operation). Perform operation element by element array operation. operation can take 'multiply','divide','add','subtract'.
- scalarOperation(arr, operation, num). Perform element by element operation on array. num is a number. num is not required for 'abs','sqrt','log','log10','copy' operations. operation can take following values 'multiply','divide','add','subtract','power','abs','sqrt','log','log10','copy'. 
- stat(arr, operation, type). Perform basic statistics on rows of the array. operation can take values 'mean','max','min','absmax','absmin','popstd','samstd','add'. Use type 'vertical' when operations need to be performed on the columns. stat(arr,'mean') will compute mean of all numbers in each row of an array while stat(arr,'mean','vertical') will compute mean of columns. Use 'max' when need the maximum value (takes sign into account) and 'absmax' when need absolute maximum (considers only magnitude). 'popstd' is population standard deviation and 'samstd' is sample standard deviation. 'add' adds all elements in the row. 
- subset(arr,dimensions). Obtain subset of an array provided by dimensions. dimensions is an array. See example section below
- serialIndex(startInd,lastInd,jump,exclude). Construct an array with startInd (number) as first value,lastInd (number) as last value, jump (number) is increment value, exlude (array) are numbers you do not want to include in array. This function can be very useful in looping constructs
- crossProduct(arr, arr1). Compute cross product of two arrays. Supports upto 2D.
- determinant(arr). Compute determinant of array. The array has to be a 2D square matrix. TODO - way to calculate determinant of big 2D arrays (> 60 x 60)
- inverse(arr). Compute inverse of an array.The array has to be a 2D square non-singular matrix. 
- pseudoinverse(arr). Compute inverse of 2D non-square matrix
- adjoint(arr). Compute adjoint of the 2D square matrix
- print(arr). Return a string form of the array. Supports upto 2D matrix

## Examples
```javascript
var a = [[1,2,3],[6,3,2],[2,1,2]];
ExtendArray.initialize([3,3],'ones');      // Initializes 3x3 array filled with ones
ExtendArray.dimensions(a);                // Get dimensions of the array
ExtendArray.transpose(a);                // Transpose the array
ExtendArray.subset(a,[':',[0,1]]);      // Subset will have all rows of a and first and second column of a
ExtendArray.serialIndex(0,10,2,[4,5]); // [0,2,6,8,10]
```
Combine multiple operations to perform complex operations
```javascript
ExtendArray.dimensions(ExtendArray.transpose(a)); // Determine dimensions of transposed array
```

## Dependencies
None. The library uses native components for performing all operations

## License
Copyright (c) 2015, Chiran D. Doshi

ExtendArray is licensed under the MIT License: http://www.opensource.org/licenses/mit-license.php




