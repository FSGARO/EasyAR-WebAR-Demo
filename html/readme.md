WebAR 项目文件目录

#### 目录说明

1. SimpleExample， 最简示例，主要展示了 WebAR  最基本的能力：识别。扫描识别图之后，会返回识别图的 targetId、meta等相关信息。

2. SimpleThreeJsExample，主要展示如何使用Three.js加载模型。

3. TokenThreeJsExample，使用WebAR Token访问云识别服务，识别成功后加载模型。

4. TokenVideoExample，使用WebAR Token访问云识别服务，识别成功后播放视频。


#### 备注

1. 在iOS12.2及以上的版本不能切换前/后摄像头的问题，解决方法如下：

    ```
    // 打开后置摄像头参数
    const constraints = {
        audio: false,
        video: {facingMode: {exact: "environment"}}
    };
    ```
    
    ```
    // 打开前置摄像头参数
    const constraints = {
        audio: false,
        video: {facingMode: {exact: "user"}}
    };
    ```
    
    ```
    navigator.mediaDevices.getUserMedia(constraints)
      .then((stream) => {
          // 这里处理打开摄像头后的操作
      })
      .catch((err) => {
          reject(err);
      });  
    ```