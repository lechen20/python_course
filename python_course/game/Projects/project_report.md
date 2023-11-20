# 《Python程序设计基础》程序设计作品说明书

题目： 外星人入侵游戏👽

学院： 21计科01

姓名： 陈乐

学号： B20190202222

指导教师： 周景

起止日期：2023.11.10-2023.12.10

## 摘要

_介绍本次设计完成的项目的概述，本文的主要内容，总结你主要完成的工作以及关键词。_

关键词：外星人入侵, pygame, alien, bullet, button, game_functions,    
        scoreboard, settings, ship, game_stats    

## 第1章 需求分析

1. 实现教材12章的功能：创建游戏窗口、添加飞船图像、驾驶飞船、飞船可以射击子弹。    
2. 实现教材13章的功能：创建一群外星人、外星人可以移动、可以射杀外星人、结束游戏。    
3. 实现教材14章的功能：添加Play按钮、可以提高等级、计分功能。     
4. 实现教材部分练习的功能：练习12-6将飞船放在屏幕左侧进行射击、练习13-2在游戏背景中随机位置绘制星星、练习14-5 将游戏中得到的最高分保存到文件中。    

## 第2章 分析与设计

### 项目设计   

#### 设计思想 

1. 在完成某一个需求前，首先确定职责 —— 要做的事情（方法）   

2. 根据职责确定不同的对象，在对象内部封装不同的方法（多个）   

3. 最后完成的代码，就是顺序地让不同的对象调用不同的方法   

    《外星人入侵》项目，是一个 飞船通过发射子弹消灭外星人来获取得分、升级的游戏。需要的对象有：飞船、子弹、外星人等等。   

#### 游戏流程   

1. 初始化游戏：pygame.init()   
2. 新建模块settings，包含Settings类，用于存储与游戏相关的所有设置    
3. 新建模块game_function，包含很多方法，用于存储与游戏相关的所有操作    
4. 新建游戏窗口对象   
5. 创建一艘飞船   
6. 创建一个子弹编组   
7. 创建一个外星人编组   
8. 创建一个游戏开始的按钮   
9. 创建一个用于存储游戏统计信息的实例   
10. 创建记分   
11. 创建外星人群   
12. 游戏的主循环   
    检测事件   
    针对不同事件，让不同的对象 调用 同的方法   



### 项目使用各类方法

#### 窗口相关操作   

1. 创建窗口   
    pygame.display.set_mode((窗口宽，窗口高))   
2. 设置窗口标题   
    pygame.display.set_caption("窗口标题")   
3. 设置窗口图标   
    pygame.display.set_icon(image)   
4. 指定坐标，将图片绘制到窗口   
    self.screen.blit(self.image,self.rect)   
    blit() ： 绘图方法   
5. 不断更新屏幕，命令pygame让最近绘制的屏幕可见   
    pygame.display.flip()   


#### 图像相关操作

1. pygame.image : 图像相关操作   
2. pygame.rect : 管理矩形区域   
3. 加载资源图片，返回图片对象（返回的就是surface）    
    image = pygame.image.load("图片路径")   
4. 获得图片矩形对象   
    get_rect()：获取相应surface的属性rect   
将游戏元素居中，可设相应rect对象的属性center,centerx或centery     
将游戏元素与屏幕边缘对齐，可使用属性top,bottom,left或right   
调整游戏元素的水平或垂直位置，可使用属性x和y，它们分别是相应矩形左上角的x和y坐标   
  rect = image.get_rect(centerx=x,centery=y)   
5. 默认情况下左上角坐标是(0,0)   
6. 绘制图形：pygame.draw()   
            blit()   
7. 在原位置基础上，移动指定的偏移量（x,y增加）   
    rect.move_ip(num1,num2)    
8. 判断两个矩形是否相交，相交返回True，否则返回False   
pygame.Rect.colliderect(rect1,rect2)    
同理，判断两个圆形是否相交，把rect改为circle    
判断两个组是否相交，改为groupcollide()    
检验任何图像是否发生碰撞，改为collideany()   

#### 事件相关操作   

1. QUIT 关闭窗口    
2. KEYDOWN 键盘按键   
3. KEYUP 松开键盘    
4. 获得所有事件的列表   
   for event in pygame.event.get()   
5. 鼠标点击关闭窗口事件   
    if event.type == pygame.QUIT   
        sys.exit()   
6. 键盘按下事件   
    if event.type == pygame.KEYDOWN   
7. 判断用户按下的键是否是a键   
    if event.key == pygame.K_q   
8. 无论单击屏幕什么地方，Pygame将检测到一个MOUSEBUTTONDOWN事件   
    pygame.mouse.get_pos()，返回一个元组，其中包含单击时的x和y坐标 


### 项目模块

#### sprite（精灵）模块：pygame.sprite

1. 作用：一种可以在屏幕上移动的图形对象，并且可以与其他图形对象交互。使用它，只需继承它，然后按需写出自己的类。    
2. sprite模块包含类Sprite    
3. 创建一个精灵组：pygame.sprite.Group()    

#### sys 模块 

1. 作用：sys.exit()退出当前程序    
2. 函数基本使用方法为：import sys后，直接调用就可以终止程序    


### 项目功能

#### 创建游戏窗口


#### 添加飞船图像


#### 驾驶飞船


#### 飞船射击子弹


#### 创建一群外星人


#### 外星人可以移动


#### 射杀外星人


#### 结束 游戏


#### 添加Play按钮


#### 提高等级


#### 计分功能



## 第3章 软件测试

_本章的内容主要包括以类和函数作为单元进行单元测试，编写的对系统的主要功能的测试用例，以及测试用例执行的测试报告。_

## 结论

_本章的内容主要是对项目的总结，项目主要实现了哪些功能，达到了哪些目标，哪些不足之处，可以如何改进。_

## 参考文献