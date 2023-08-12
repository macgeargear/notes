- The generator and the discriminator composes of many layers of convolutional layers, batch norm and ReLU with skip connection

## Some cool applications 
- #### Pose Guided Person Image Generation
	- composes of a 2-stage image generator and a discriminator.
	- The generator -> reconstruct an image using mata-data(opse) and original image.
	- The discriminator uses the original image as part of the label input to a **CGAN** design
 - #### CycleGAN
	 Cross-domain transfer GANs
	 These GANs transform images from one domain to another domain.
	  ex. scenery to Monet paintings or Van Gogh, Zebras to Horses.
	builds 2 betworks **G** and **F** to construct images from one domain to another and in the reverse direction.	
		  