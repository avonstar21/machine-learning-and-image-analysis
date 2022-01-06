-----------------Operation of MLIA Final Project Code for Harris, Garg, and Scaife----------------

1.) Code should be put in the same directory as the "Segmentation_data" folder.
2.) In the code, change the variable  "data_path" to the location of the Segmentation_data folder.
3.) To train a model other than InputCascadeCNN, in the training code block change the following:
	A.) In the call to data_gen, change the final parameter to the desired model
            (The guide for this is a comment next to said function call)
	B.) On the last two lines, change "m1" to "mx", where x is the same number
	    as A.).

----------------------------------------------NOTICE----------------------------------------------
	Due to how this model is created, training takes days and cannot fit inside a GPU, even 
	with a reduced data set, since there are numerous patches created per image, resulting in
	training for 2 epochs for each image on the hundreds of generated slices. This is after
	reducing both the number of patches (by removing patches with insufficient data and 
	increasing the step size between patches) and amount of images to train on.