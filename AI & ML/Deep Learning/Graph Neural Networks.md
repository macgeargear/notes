- data for graph neural network
	- Image Video Text Speech
### Type of Prediction
- **Graph prediction**
	- predict molecular graph of the molecule if it can be a aproppriate `drug` 

- **Node prediction**
- **Edge prediction**


### Transfrom input into graph
- in CNNs or Transformers, input is described in vectors form or matrix or tensor and it depend on dimension of input
	- Example, 1 image can be 3D tensor of 512 * 512 * 3
	- but text maybe the sequence of bectors ( matrix = 2D tensor )
 - when input is in the graph, it consists two main part
	 1. node-input
	 2. edge-input
	so we can represent **Graph G = (X, A)** when **X** stands for `node vector` and **A** stands for `edges`
 