# Open3D

## Introduction:  
Solution to assignment for GSOC 2022. Assignmnet PDF is attached in the repository.  

### How to use  
Installing Cmake (Skip this steps if already Installed)  
Cmake version required > 3.19  
`cmake -version`  
`sudo apt remove cmake` (if Cmake version < 3.19)  
Get new version from website directly https://cmake.org/download/ and unzip and make excecutable  
`cd Cmake <version>`  
`sudo apt-get install build-essential`  
`sudo apt-get install libssl-dev`  
`./bootstrap`  
`sudo make`  
`sudo make install`  

### Build from source  
`git clone https://github.com/isl-org/Open3D'`  
Install Dependicies  
`cd Open3D`  
`util/install_deps_ubuntu.sh`  
`-DPython3_ROOT=/path/to/python`  (Set Cmake flag to python file location)  
Create build folder in Open3D  
`mkdir build`  
`cd build`  
`cmake ..`  
`make -j$(nproc)`  
`sudo make install`  
`sudo make python-package`  
### Python Installation 
`pip install open3d`  


## Algorithm  
We approached the problem statement using DFS(Depth First Search) Algorithm.  
1. Import mesh file and extract mesh information like vertex color and triangles 
2. We created a adjacency list for all the vertices having same color. 
3. We iterate through all the unvisied vertex and append them to list keeping a track of unvisited vertices.
4. All the connected components are sorted in ascending before storing to main list. 
5. Return the Identically Colored Connected Components. 


### Program 
#### C++
Copy the Solution.cpp and test_mesh.ply to Open3D/examples/cpp  
`cd Open3D/examples/cpp/`  
Run `./Solution.cpp test_mesh.ply`  
Outputs Will be stored in examples/result.txt
### Python 
Copy the solution.py and test_mesh.ply to Open3D/examples/python   
`cd Open3D/examples/python/`  
`python solution.py --test_mesh.ply`  
Outputs Will be stored in examples/result.txt
