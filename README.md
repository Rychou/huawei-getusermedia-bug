# huawei-getusermedia-bug

华为浏览器中，存在一个采集的 Bug，其他浏览器（Chrome）表现正常。复现流程：
1. 用 navigator.mediaDevices.getUserMedia({ audio: true, video: true }) 同时开启麦克风和摄像头
2. 使用 videoTrack.stop()，将第一步采集到的摄像头停止采集
3. 重新调用 navigator.mediaDevices.getUserMedia({ audio: false, video: true }) 单独采集摄像头，此时无法正常采集，返回的 Promise 一直处于 pending 状态。

demo 地址：https://sdk-web-1252463788.cos.ap-hongkong.myqcloud.com/trtc/webrtc/test/rychou-test/huawei.html
