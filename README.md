


# Mask R-CNN with additional Mobilenet backend
### This is an implementation of Mask R-CNN on Python 3, Keras, and TensorFlow with option for using Mobilenet as backend architecture


## Changes to the model.py file in mrcnn
   * Add Mobilenet specific imports
   * Add mobilenet assertion in the backbone.Config options in the ```compute_backbone_shapes``` funtion
   * Add mobilenet graph code
            ###   Mobilenet V1 graph's code adopted from [fchollet's](https://github.com/fchollet/deep-learning-models/blob/master/mobilenet.py) repo
            ###   Mobilenet V2 graph's code adopeted from [xiaochus's](https://github.com/xiaochus/MobileNetV2/blob/master/mobilenet_v2.py) repo
   * Add 'backone' parameter to the function ```build_fpn_mask_graph``` and parse it to the model building stage for building separate model for mobilenet backbone
   * Add option to call mobilenet graph in the ```build``` funtion apart from resnet graph
   * Set default value as True for the ```load_weights``` function's 'by_name' parameter 
   * Add separate path for imagenet weight for the mobilenet backbone
   * Add separate option for the layers regex for mobilenet backbones 
   * Add a Speedhack to mold /unmold image functions for mobilenet backbones

## Changes to the config.py file in mrcnn
   * Update the coco model weight path for mobilenet backbone
   * Update the coco configuration with the ones for mobilenet backbone
   
## Use separate model weights for mobilenet backbone from [here](https://github.com/gustavz/Mobile_Mask_RCNN/blob/master/mobile_mask_rcnn_coco.h5)


## References
   * Gustav's [repo](https://github.com/gustavz/Mobile_Mask_RCNN) for implementation of mobilenet using Mask RCNN
   
