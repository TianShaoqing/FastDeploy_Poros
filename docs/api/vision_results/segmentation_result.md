English | [中文](segmentation_result_CN.md)
# Segmentation Result

The SegmentationResult code is defined in `fastdeploy/vision/common/result.h`, indicating the segmentation category and the segmentation category probability predicted in each pixel in the image.

## C++ Definition

``fastdeploy::vision::SegmentationResult``

```c++
struct SegmentationResult {
  std::vector<uint8_t> label_map;
  std::vector<float> score_map;
  std::vector<int64_t> shape;
  bool contain_score_map = false;
  void Clear();
  std::string Str();
};
```

- **label_map**: Member variable which indicates the segmentation category of each pixel in a single image. `label_map.size()` indicates the number of pixel points of a image.
- **score_map**: Member variable which indicates the predicted segmentation category probability value corresponding to the label_map one-to-one, the member variable is not empty only when `--output_op none` is specified when exporting the PaddleSeg model, otherwise the member variable is empty.
- **shape**: Member variable which indicates the shape of the output image as H\*W.
- **Clear()**: Member function used to clear the results stored in the structure.
- **Str()**: Member function used to output the information in the structure as string (for Debug).

## Python Definition

`fastdeploy.vision.SegmentationResult`

- **label_map**(list of int): Member variable which indicates the segmentation category of each pixel in a single image.
- **score_map**(list of float): Member variable which indicates the predicted segmentation category probability value corresponding to the label_map one-to-one, the member variable is not empty only when `--output_op none` is specified when exporting the PaddleSeg model, otherwise the member variable is empty.
- **shape**(list of int): Member variable which indicates the shape of the output image as H\*W.
