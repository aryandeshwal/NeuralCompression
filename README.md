Three main steps 
1. Conversion from Keras .h5 file to tensorflow .pb file (courtesy of (here)[https://github.com/amir-abdi/keras_to_tensorflow])
Use following command : 
python3 keras_to_tensorflow.py -input_model_file <name of the .h5 file>


2. Conversion to tensorflow .tflite file (courtesy of (here)[https://www.tensorflow.org/lite/devguide])
Use following command :
toco --input_file=<path to generated .pb file> \
  --input_format=TENSORFLOW_GRAPHDEF \
  --output_format=TFLITE \
  --output_file=<path with name of output file> \
  --inference_type=FLOAT \
  --input_type=FLOAT \
  --input_arrays=<name of your input layer (according to tensorflow naming)> \ 
  --output_arrays=<name of your output layer (according to tensorflow naming)> \
  --input_shapes=1,224,224,3 <shape of input data>
  
  
3. Inference on mobile (courtesy of (here)[https://github.com/tensorflow/tensorflow/tree/master/tensorflow/contrib/lite/tools/benchmark#on-android])
