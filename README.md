# Computer Vision for Ankle Replacement Surgery
 The code associated with the paper of the same name
## Image Pre-Processing & Masking
 Can be found under the the file full_image_processing.ipynb
 Set the model path using either your own model (which you can create in object_detection_test.ipynb)
 Set the source path to your folder containing your images
 Set the destination path to know where your files will end up
 In the section Functions --> def Trasform(self) you can choose which of the functions you want to use

## Detection Model
 Use the code object_detection_test.ipynb to create your own detection model
 Go to config.yaml and set the home, train, val, and test paths to fit with yours.
 Name the labels in the names section
 Check to make sure CUDA works on your gpu (if not, ignore CUDA code)
 Set base model to yolov8m.pt by writing model = YOLO("yolov8m.pt")
 Use config.yaml under model.train(data="config.yaml", epochs=1000)
 Run
 To test the model, set a test image path and the new model path and then run
 This model can be used in the image preprocessing to automate masking

## Segmentation Model
 To make your own segmentation model, use the same system as the object detection model but instead configure config-seg.yaml
 Configure config-seg.yaml the same way you would for detection
 Set the model to yolov8m-seg by having model = YOLO("yolov8m-seg.pt")
 Set the new model to train segementation using the code model.train(data="config-seg.yaml", epochs=1000)

## Curve Fitting
 Provide paths to each of the models for each of the bones
 Provide the oath to the image you want to analyze
 Run the code, you will get an image and text output showing the lines and giving the angles.
