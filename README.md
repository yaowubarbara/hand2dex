# hand2dex — 手到灵巧手

手机浏览器里打开，对着镜头动手：

1. 实时检测手部 21 个 3D 关键点（Google MediaPipe Hand Landmarker）
2. 重定向成 6 自由度灵巧手的电机指令（每指一路屈曲 + 拇指旋转，0–1000）
3. 录 5 秒，当场验收这段采集能不能当训练数据：在画面、距离、出框、速度、抖动、置信度，给出可用帧比例和主要问题，可导出 JSON

全部在本地运行，画面不上传。重定向与验收规则是初版，阈值未经真实采集校准。

在线体验：https://yaowubarbara.github.io/hand2dex/

第三方：`vendor/` 内为 `@mediapipe/tasks-vision@0.10.14` 与 `hand_landmarker.task` 模型，Apache License 2.0，© Google。
