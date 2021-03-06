# yolo-v2-ava-0001

## Use Case and High-Level Description

This is a reimplemented and retrained version of the [YOLO v2](https://arxiv.org/abs/1612.08242) object detection network trained with the VOC2012 training dataset.

## Example

## Specification

| Metric                          | Value                                     |
|---------------------------------|-------------------------------------------|
| Mean Average Precision (mAP)    | 63.9%                                     |
| Flops                           | 48.29Bn\*                                  |
| Source framework                | TensorFlow\*                              |

For Average Precision metric description, see [The PASCAL Visual Object Classes (VOC) Challenge](https://doi.org/10.1007/s11263-009-0275-4).
Tested on the VOC 2012 validation dataset.

## Performance

## Inputs

Name: `input`, shape: [1x3x416x416] - An input image in the format [BxCxHxW],
  where:
    - B - batch size
    - C - number of channels
    - H - image height
    - W - image width
Expected color order is BGR.

## Outputs

The net outputs a blob with the shape [1, 21125], which can be reshaped to [5, 25, 13, 13],
where each number corresponds to [`num_anchors`, `cls_reg_obj_params`, `y_loc`, `x_loc`] respectively:
- `num_anchors`: number of anchor boxes, each spatial location specified by `y_loc` and `x_loc` has five anchors
- `cls_reg_obj_params`: parameters for classification and regression. The values are made up of the following:
  * Regression parameters (4)
  * Objectness score (1)
  * Class score (20)
- `y_loc` and `x_loc`: spatial location of each grid

## Legal Information
[*] Same as the original implementation.

[**] Other names and brands may be claimed as the property of others.
