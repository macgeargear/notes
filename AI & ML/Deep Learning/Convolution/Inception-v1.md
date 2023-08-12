### Problem
- deep layer -> exploding/vanishing gradients
1. exploding gradient: large error gradients accumulate
 2. vanishing gradients: partial derivate of **loss function** close to zero -> neural net couldn't train
	
![[Screenshot 2023-02-08 at 7.44.47 PM.png]]


- adding 2 classifiers connected to intermediate layers -> increase gradients signal that get propagated back.