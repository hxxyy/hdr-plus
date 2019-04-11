Note: I now work for Google's computational photography research group, which developed and published HDR+. Therefore, to avoid conflicts of interest, I no longer maintain the code in this repository. If you are interested in continuing this open source project, I would love to transfer ownership to another open source contributor. Please reach out to me if you are interested!

# HDR+ Implementation
Please see: http://timothybrooks.com/tech/hdr-plus

To compile, follow these steps:
1. Install Halide from http://halide-lang.org/.
2. Set `HALIDE_ROOT_DIR` in CMakeLists.txt to the Halide directory path.
3. From the project root directory, run the following commands:
```
mkdir build
cd build
cmake ..
make

Usage: ./hdrplus [-c comp -g gain (optional)] dir_path out_img raw_img1 raw_img2 [...]

```

## 格式问题
原代码不支持dng格式图片，只支持CR2格式图片
代码只支持输入rggb格式的图片，为了使用google的数据集，将这里改为bggr格式，现支持dng格式。

## 参数问题
原代码参数固定
现已通过 GetImageDimensios和GetBWLevels自动获取输入图片的width、height、black level、white level.

## 还存在的问题
finish中锐化好像有点严重，正在想办法解决。。
