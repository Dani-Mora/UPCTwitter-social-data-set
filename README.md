###################################################################
##################### Summary set #################################
###################################################################

This is a near image replica data set consisting of 3.925 images: 50 source images, 1.600 replicas (32 images generated from each source image applying different transformations to them such as gaussian noise addition or resizing) and 2.275 background images

Images where extracted from the Twitter Streaming API. Replicas were generated using OpenCV for Java. The file "descriptor.csv" describes the transformation of each replica and links each replica with its original version.

###################################################################
################### Data set format ###############################
###################################################################

The first line of the descriptor is its header. Their columns, in order, are:

- 'id': Unique identifier of the image.
- 'path': Relative path of the image inside the data set.
- 'extension': Extension of the image.
- 'height': Height of the image (in pixels).
- 'width': Width of the image (in pixels).
- 'replicaType': Type of the replica. If the image is not a replica, this field is empty. Types of replica:

	- "Rotated": rotated version of the original image.
	- "Cropped_H": Horizontal Cropping of the original image.
	- "Cropped_V": Vertical Cropping of the original image.
	- "Compressed": JPEG compressiong of the original image.
	- "Gaussian": Gaussian noise addition on the original image.
	- "Resized": Resized version of the original image.
	- "Smoothed": Blurred version of the original image.
	- "Gamma": Gamma corrected version of the original image.
	- "ChannelS": Original image was converted into HSV, modificated its 'S' channel and reconverted to RGB.
	- "ChannelV": Original image was converted into HSV, modificated its 'V' channel and reconverted to RGB.
	- "HFlipped": Horizontal flipping of the original image.
	- "Text": Insertion of random text on the original image.
	- "Occluded": Occlusion using random positioned circles (black filled) on the image.

- 'param1': First parameter of the replica (if the image is a replica). For each replica type, we consider the following attributes as first parameter:

	- "Rotated": Rotation (in degrees, anti-clockwise) that the image was rotated.
	- "Cropped_H": Percentage [0.0, 1.0] of the image width that was cropped.
	- "Cropped_V": Percentage [0.0, 1.0] of the image height that was cropped.
	- "Compressed": Quality measure [0.0, 1.0] of the compression.
	- "Gaussian": Mean of the Gaussian distribution of the noise.
	- "Resized": Ratio of the transformation.
	- "Smoothed": Size of the kernel used.
	- "Gamma": Gamma parameter.
	- "ChannelS": Modification percentage of the channel [-1.0, 1.0].
	- "ChannelV": Modification percentage of the channel [-1.0, 1.0]..
	- "HFlipped": Not used.
	- "Text": Length of the text.
	- "Occluded": Number of black circles inserted in the image.

- 'param2': Second parameter of the replica (if the image is a replica). For each replica type, we consider the following attributes as second parameter:

	- "Rotated": Not used.
	- "Cropped_H": Not used.
	- "Cropped_V": Not used.
	- "Compressed": Not used.
	- "Gaussian": Standard deviation of the Gaussian distribution of the noise.
	- "Resized": Not used.
	- "Smoothed": Not used.
	- "Gamma": Resized version of the original image.
	- "ChannelS": Not used.
	- "ChannelV": Not used.
	- "HFlipped": Not used.
	- "Text": Not used.
	- "Occluded": Percentage of the largest side of the image [0.0, 1.0] that corresponds to the circle radius.

- 'source': If the image is a replica, this field contains the identifier of the original image,


###################################################################
################# License and contact #############################
###################################################################

We are not responsible for the content shared by the picture's owner though we tried to remove all those images that could be offensive. Please, if you encounter any image that you think should be deleted from the data set please email here: daniel.mora.checa@gmail.com

This data set is published under GPL license.

Work done by Daniel mora de Checa and Rubèn Tous.
