# KD_Trees
Implementation of K-D tree in C++ programming language
<div>
<img src=https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Kdtreeogg.ogv/436px--Kdtreeogg.ogv.jpg>
 </div>
 Image source : WIKI
[Read more about the K-D Trees](https://www.cs.cmu.edu/~ckingsf/bioinfo-lectures/kdtrees.pdf)
<img src=https://github.com/DrCybernotix/KD_Trees/blob/main/kd%20tree/kdtree_I0.png width=256> <img src=https://github.com/DrCybernotix/KD_Trees/blob/main/kd%20tree/kdtree_I1.png width=256> <img src=https://github.com/DrCybernotix/KD_Trees/blob/main/kd%20tree/kdtree_I2.png width=256>

## What's in this repository anyway?
- This is a C++(PL) implementation of [K-D Trees](https://en.wikipedia.org/wiki/K-d_tree)
- - Implementation ensures the nearest neighbour search facilities : 
  - Nearest neighbor search
  - K-nearest neighbor search
  - Radius search
- A header file (custom). Library

## How do we actually use the K-D Tree class?
- As you might have erad from the source above, the class included of the K-D Tree inputs a user-defined point type as its template parameter, a default parameter.
- The point you pass has to be put through the following constraints : 
  - Implementation of operator[] <= accessor to its coordinates.
  - Static member variable DIM <= dimension of the input.
- Passing point cloud to KDTree constructor starts to build K-D Tree.
- After implementation of K-D Tree, you can use Nearest neighbor search functions.

## Procedure : 
You need to get CMake tools for generating the executable, you can download it from [here](https://cmake.org/download/)
OR, you can also use the CMake tools extension in Visual Studio, provided by Microsoft.

```
#include "kdtree.h"

// user-defined point type (inherits std::array in order to use operator[])
class MyPoint : public std::array<double, 2>
{
public:

	// dimension of the Point
	static const int DIM = 2;

	// As you want
	// ...
};

int main()
{
	// generate point cloud
	std::vector<MyPoint> points = ...;

	// build k-d tree
	kdt::KDTree<MyPoint> kdtree(points);

	// K-nearest neighbor search (gets indices to neighbors)
	int k = 10;
	MyPoint query = ...;
	std::vector<int> indices = kdtree.knnSearch(query, k);

	return 0;
}

```

## Requirement

- OpenCV (For running sample code)

## Following is the sample code for the Built : 

### How to build ? 

Go to command prompt and change the directory to your desired location for cloning the repository using the 
```sh
cd <location>
```
command.
After this procedure, stay in the command prompt and clone this repository, using the commands :  
```
$ git clone https://github.com/DrCybernotix/KD_Trees.git
$ cd KD_Trees
$ mkdir build
$ cd build
$ cmake ../
$ make
```

### How to run
```
./kdtree [seed]
```
- seed
    - Seed of rand() in generating random point cloud

## Implemented throughout DSA CP

