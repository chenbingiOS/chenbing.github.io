---
layout: post
title: iOS 平台常用传感器
tags: [iOS,传感器]
---

<!--more-->


iOS 传感器
================
*	[加速度传感器](#overview)
    *   [宗旨](#philosophy)
    *   [兼容 HTML](#html)
    *   [特殊字符自动转换](#autoescape)
*   [区块元素](#block)
    *   [段落和换行](#p)
    *   [标题](#header)
    *   [区块引用](#blockquote)
    *   [列表](#list)
    *   [代码区块](#precode)
    *   [分隔线](#hr)
*   [区段元素](#span)
    *   [链接](#link)
    *   [强调](#em)
    *   [代码](#code)
    *   [图片](#img)
*   [其它](#misc)
    *   [反斜杠](#backslash)
    *   [自动链接](#autolink)
*   [感谢](#acknowledgement)

* * *

#iOS 加速度传感器(accelerometer)

##简介
加速度传感器是根据x、y和z三个方向来检测在设备位置的改变。
通过加速度传感器可以知道当前设备相对于地面的位置。

以下实例代码需要在真实设备上运行，在模拟器上是无法工作的。

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