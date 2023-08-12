- use ReLU, [[Local Response Normalization]] (LRN)
- 8 layers
	- 5 conv layers non-incresing kernel sizes
	- 3 denses
	 - 1, 3, 5 layer use max pooling	  
	 - 1,2  -> LRN, ReLU
	 - others -> ReLU
  - **60 million parameters**

