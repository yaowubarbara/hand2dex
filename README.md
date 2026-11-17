# hand2dex — 手到灵巧手

手机浏览器里打开，对着镜头动手：

1. 实时检测手部 21 个 3D 关键点（Google MediaPipe Hand Landmarker）
2. 重定向成 6 自由度灵巧手的映射控制值（每指一路屈曲 + 拇指旋转，0–1000；未接真机验证）
3. 录 5 秒，现场标出采集异常（手不在画面、太远、出框、动太快、关键点抖动、识别置信度低），给出规则通过帧占比，可按异常时间轴回看录像，可导出 JSON

它只做提醒，不删帧，也不判断数据能否用于训练；最终是否合格要按任务要求验收。

全部在本地运行，画面不上传。重定向与质检规则是初版，阈值未经真实采集校准。

在线体验：https://yaowubarbara.github.io/hand2dex/

第三方：`vendor/` 内为 `@mediapipe/tasks-vision@0.10.14` 与 `hand_landmarker.task` 模型，Apache License 2.0，© Google。
