# GitHub Pages 部署说明

这是从线上已发布版本导出的静态运行文件，不是源仓库备份。未取得目标网站源仓库，因此无法核实未发布、未引用的文件；页面实际引用的资源均已下载。保留原有运行目录结构，新增 assets/vendor/mediapipe-hands 本地依赖和说明文件。

解压后 index.html 位于第一层。将全部文件上传到公开 GitHub 仓库根目录（包括 .nojekyll），在 Settings → Pages → Deploy from a branch 选择 main / (root)，保存并等待 GitHub 提供 HTTPS 网址。无需 npm 安装或构建，无需 ChatGPT 登录。

请通过 HTTPS 网站访问。直接双击 index.html 的 file:// 模式可能阻止 JSON 和模块加载。摄像头需用户授权，识别在浏览器本地完成；也可拖动图形或使用 A/D、J/L 键操作。

## 数据与素材

15 组档案及 17 张原件图片保存在 data.json 和 assets/ 内。视频保留原有 8 个 bin 分片及 video.json，合计 30,657,016 字节。当前线上手势程序使用 red-background.png、star.png、sickle.png、hammer.png 四张分层素材进行位置、角度及缩放变换，没有引用逐帧动画序列；无法确认源仓库中是否另存有未引用帧图。

## 外部 CDN

原程序依赖 cdn.jsdelivr.net 的 @mediapipe/hands@0.4.1675469240。此域名在中国大陆可能因网络、DNS 或 CDN 节点问题加载失败。

本包已将该 npm 版本的全部发布文件放入 assets/vendor/mediapipe-hands/，包括 JS、WASM、binarypb、data 和 tflite 模型。主脚本与 locateFile 均已改为相对路径。无运行时外部 CDN 依赖，无 ChatGPT 服务端接口依赖。第三方文件中的文档链接、命名空间或错误帮助网址不是运行时资源依赖。GitHub Pages 本身在国内仍可能较慢或无法访问，资源本地化不能保证其网络可达性。

## 验证范围

已核对全部页面引用的资源存在、档案数量、视频分片总大小、JS 语法和 ZIP 完整性。没有取得源仓库，不能声称包含未引用素材。预览服务因 relay readiness timeout 启动失败，尚未完成浏览器端视频播放和摄像头识别实测。

完整文件清单和 SHA-256 校验值见 FILES.txt。FILES.txt 的自身摘要未列出。
