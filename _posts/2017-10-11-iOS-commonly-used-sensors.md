---
layout: post
title: iOS 平台常用传感器
tags: [iOS,传感器]
---

<!--more-->


iOS 传感器
================
*	[加速度传感器](#accelerometer)

* * *

<h2 id="accelerometer">加速度传感器(accelerometer)
</h2>

##简介
加速度传感器是根据x、y和z三个方向来检测在设备位置的改变。<br />
通过加速度传感器可以知道当前设备相对于地面的位置。<br />
以下实例代码需要在真实设备上运行，在模拟器上是无法工作的。<br />

##实例步骤

Swift Code
````
// 加速度传感器
import CoreMotion

class ViewController: UIViewController {

    var cmm:CMMotionManager!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        cmm = CMMotionManager();
    }
    
    override func viewWillAppear(_ animated: Bool) {
        cmm.accelerometerUpdateInterval = 1.0
        if cmm.isAccelerometerAvailable {
            cmm.startAccelerometerUpdates(to:OperationQueue(), withHandler: {(data:CMAccelerometerData!, err:Error!) in
                print(data)
            })
        } else {
            print("加速度传感器不可用")
        }
    }
    
    override func viewWillDisappear(_ animated: Bool) {
        if cmm.isAccelerometerActive {
            cmm.stopAccelerometerUpdates()
        }
    }
}
```
---