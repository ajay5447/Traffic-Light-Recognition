# Traffic-Light-Recognition
Develop a model to recognize traffic-light state in the car driving direction.

This dataset contains 13427 camera images at a resolution of 1280x720 pixels and contains about 24000 annotated traffic lights. The annotations include bounding boxes of traffic lights as well as the current state (active light) of each traffic light. The camera images are provided as raw 12bit HDR images taken with a red-clear-clear-blue filter and as reconstructed 8-bit RGB color images. The RGB images are provided for debugging and can also be used for training. However, the RGB conversion process has some drawbacks. Some of the converted images may contain artifacts and the color distribution may seem unusual.

Network: The R-CNN detector first generates region proposals using an algorithm such as Edge Boxes. The proposal regions are cropped out of the image and resized. Then, the CNN classifies the regions which were cropped and resized. Finally, the region proposal bounding boxes are refined by a support vector machine (SVM) that is trained using CNN features. The Fast R-CNN detector also uses an algorithm like Edge Boxes to generate region proposals. Unlike the R-CNN detector, which crops and resizes region proposals, the Fast R-CNN detector processes the entire image. Whereas an R-CNN detector must classify each region, Fast R-CNN pools CNN features corresponding to each region proposal. Fast R-CNN is more efficient than RCNN, because in the Fast R-CNN detector, the computations for overlapping regions are shared.
A post processing technique of Non-maximal suppression is used to select the bounding box with the highest probability of the object being there. The image is scaled back up and this box is displayed.


![image](https://user-images.githubusercontent.com/55333854/117563297-da4a6100-b072-11eb-96ad-1cd653ca8163.png)

