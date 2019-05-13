# AlexNet-model-in-TensorflowLite
TensorFlow’s lightweight solution for mobile for AlexNet model

Thanks to kratzert.
https://github.com/kratzert/finetune_alexnet_with_tensorflow

Paper::http://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf


Ussage::
1) Download the pretrained weights "bvlc_alexnet.npy" from the https://github.com/kratzert/finetune_alexnet_with_tensorflow and place under savedFile folder
   
2)  train_file = 'data/train.txt'
    val_file = 'data/val.txt'
    train_file and val_file should contain the path to the train and val txt files.
    Both train_file and val_file should look like as {pathtofile/nameoftheFile class}
    For example..
    data/8713394070_b24561b0a9.jpg 3
    data/8713396140_5af8136136.jpg 3
    data/8713397358_0505cc0176_n.jpg 3
    data/8713397694_bcbcbba2c2_n.jpg 3
    data/8713398114_bc96f1b624_n.jpg 3
    files path and class should be separated by space.
    
 3) modify the train_layers list to change the no of layer you want to train from scratch.
    For Example if you want to train "fc8" and "fc7" then set train_layers = ['fc8','fc7']. These two layers
    will not be loaded by pretrained values so these two layers will train from scratch.
    
    
  4) All files tensorflow grapg(.pbtx file) and meta files will be saved under savedFile folder.
  
  5) Once the model is trained TensorflowLite is used to conver it to compress the model. For compression 
     "Post training Quantatization" technique is used.
     
  6) .ftlite file(converted file after quantization) can be visualized using https://lutzroeder.github.io/netron/ 
  
    
    






