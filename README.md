# Mobile-Programming-Final-Exam-Assignment-202116019

기말고사 과제 앱 만들었습니다. 저는 버튼이라는 코드를 이용하여 각 0~9의 숫자의 버튼을 만들어서 계산기가 가능하는 앱을 만들어봤습니다.



```

//  ViewController.swift
//  202116019 유정훈 기말고사과제
//
//  Created by 203a06 on 2022/06/16.
//

import UIKit

class ViewController: UIViewController {

    @IBOutlet var display: UILabel!
    
       var isPlus = false;
       var isMinus = false;
       var isCross = false;
       var isDiv = false;
       
       var sum = Int();
       var num = Int();
       var userTyping = false;
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
    }
```
버튼을 이용하여 숫자를 디스플레이에 보여주는 코드
```
    @IBAction func touchDigit(_ sender: UIButton) {
        let dight = sender.currentTitle!
            print("thouched \(dight) dight");
        if userTyping {
            let textCurrentDisplay = display.text!
            display.text = textCurrentDisplay + dight
        }else{
            display.text = dight
        }
            userTyping = true;
}
```
C 라는 버튼으로 clear 할 수 있는 코드
```
    // C 버튼 기능
    @IBAction func clear(_ sender: Any) {
        display.text = ""
        sum = 0
        num = 0
    }
```
+라는 버튼으로 sum이라는 함수를 이용한 코드
```
    
    // + 버튼 기능
    @IBAction func plus(_ sender: Any) {
        if(isPlus==false){
                    num = Int(display.text!)!
                    print("num",num)
                    sum = num + sum
                    print("sum",sum)
                    userTyping = false
                    isPlus = true
                }
    }
  ```
  -라는 버튼으로 miuns라는 함수를 이용한 코드
  ```
    // - 버튼 기능
    @IBAction func minus(_ sender: Any) {
        if(isMinus==false){
                    num = Int(display.text!)!
                    print("num",num)
                    sum = num + sum
                    print("sum",sum)
                    userTyping = false
                    isMinus = true
                }
    }
 ```
    
 x라는 버튼으로 cross라는 함수를 이용한 코드
    
 ```
   // x 버튼 기능
    @IBAction func cross(_ sender: Any) {
        if(isCross==false){
                   num = Int(display.text!)!
                   print("num",num)
                   sum = num + sum
                   print("sum",sum)
                   userTyping = false
                   isCross = true
               }
    }
 ```
  / 라는 버튼으로 div라는 함수를 이용한 코드
   
 ``` 
    // / 버튼 기능
    @IBAction func div(_ sender: Any) {
        if(isDiv==false){
                    num = Int(display.text!)!
                    print("num",num)
                    sum =  num + sum
                    print("sum",sum)
                    userTyping = false
                    isDiv = true
                }
    }
 ```
 = 이라는 버튼으로 result라는 함수를 이용한 코드
 ```
	
	
    // = 버튼 기능
    @IBAction func result(_ sender: Any) {
        if isPlus{
                    sum  = sum + Int(display.text!)!
                    print("result Plus", sum)
                    isPlus = false
                    display.text = String(sum)
                }
                
                if isMinus {
                    sum  = sum - Int(display.text!)!
                    print("result Minus", sum)
                    isMinus = false
                    display.text = String(sum)
                }
               
                if isCross {
                    sum  = sum * Int(display.text!)!
                    print("result Cross", sum)
                    isCross = false
                    display.text = String(sum)
                }
                
                if isDiv {
                    sum  = sum / Int(display.text!)!
                    print("result Div", sum)
                    isDiv = false
                    display.text = String(sum)
                }
    }
    
    
    
    
}
