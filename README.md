# YOLOv5 目标检测 Demo 复现与测试

## 项目简介
本项目是我在自学计算机视觉过程中的第一个动手实践。基于开源项目 `yolov5-object-tracking`，我独立完成了开发环境搭建，并在本地真实路口视频上跑通了目标检测流程。

## 环境配置
*   **操作系统**：Ubuntu 22.04 (VMware虚拟机)
*   **Python**：3.10
*   **深度学习框架**：PyTorch 2.5.1 (CPU版本)
*   **计算机视觉库**：OpenCV 4.5.4
*   **YOLOv5 版本**：v6.2

## 运行步骤
```bash
# 激活虚拟环境
source ~/pytorch_env/bin/activate

# 运行目标检测
python ob_detect.py --weights yolov5s.pt --source 你的视频路径.mp4

##检测效果
https://github.com/yaobao1126/yolov5_object_tracking_demo/blob/main/traffic_result_screenshot.png
(测试场景：真实红绿灯路口。成功识别出红绿灯、公交车、行人和雨伞。)

遇到的困难与解决
在复现过程中，我独立解决了两个典型的工程问题：

PyTorch版本兼容性报错：PyTorch 2.6+ 版本默认禁止加载旧版模型，导致加载 yolov5s.pt 失败。我通过查阅文档，将 PyTorch 降级到 2.5.1 版本解决。

跨系统文件传输：配置了 VMware 共享文件夹，并学会了使用 vmhgfs-fuse 命令进行手动挂载，实现了 Windows 与 Ubuntu 之间的文件互通。

后续计划
学习 YOLO 算法底层原理。

尝试调整置信度阈值（--conf-thres），减少低置信度的误检框。
