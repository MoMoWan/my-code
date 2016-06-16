//
//  Shakeable.swift
//  TTKGC
//
//  Created by iosnull on 16/6/12.
//  Copyright © 2016年 iosnull. All rights reserved.
//

//  Shakeable.swift

import UIKit

protocol Shakeable {
 
    

}

// 你可以只为 UIView 添加 shake 方法！
extension Shakeable where Self: UIView {
    // shake 方法的默认实现
    func shake() {
        let animation = CABasicAnimation(keyPath: "position")
        animation.duration = 0.1
        animation.repeatCount = 15
        animation.autoreverses = true
        animation.fromValue = NSValue(CGPoint: CGPointMake(self.center.x - 4.0, self.center.y))
        animation.toValue = NSValue(CGPoint: CGPointMake(self.center.x + 4.0, self.center.y))
        layer.addAnimation(animation, forKey: "position")
    }
}
