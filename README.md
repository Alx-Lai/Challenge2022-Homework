# Challenge 2022 Homework

Adapted from [WooLNinesun / PygameMVC](https://github.com/WooLNinesun/PygameMVC) \& [ktpss95112 / Challenge2020-Homework](https://github.com/ktpss95112/Challenge2020-Homework)

* 需求
Python >= 3.6
Pygame >= 1.9.6

* 目的
熟悉 Python
稍微熟悉 Pygame
稍微熟悉 git

* Folder Hierarchy
```
homework
|--main.py
|--Const.py
|--Model.py
|--View.py
|--Controller.py
|--EventManager.py
```

* 螢幕座標: (800, 800)
```
---------------------
|(0, 0)     (800, 0)|
|                   |
|                   |
|                   |
|                   |
|                   |
|(0, 800) (800, 800)|
---------------------
```

* 遊戲規則（裡面的參數都可以自己改）：
    1. 按空白鍵開始玩遊戲
    2. 兩個玩家各自操控（上下左右&WASD）一個圓 (半徑=75)，出生在 (200, 400) 和 (200, 600)。地圖有邊界。玩家一（上下左右）先當攻，玩家零（WASD）先當受。
    3. 以下流程每 t 秒跑一次:
        a. 攻擊方的移動速度是 100 (pixel per sec)，防守方的速度是 70 (pixel per second)。
        b. 攻方碰到受方的話，就會把受方吃掉。這樣受方就輸了，遊戲結束。
        c. t 秒到了，攻受交換！


* 程式碼
你可以想像 Model, View, Controller, EventManager 是四個不同的人，各自負責不同的事情。Model 負責遊戲的程式，Controller 負責把 user input 處理成 Model 的 input，View 負責把 Model 的狀態畫出來，Event Manager 負責不同的人之間的通訊。
舉個例子，如果 Controller 收到了一個 W 的按鍵，他就會往 Event Manager 送一個 `EventPlayerMove('W')` 的 event。這個時候，Event Manager 就會通知 model，model 就會把 player 的狀態給更新。


* 現在遊戲已經有的功能：
    1. 有很陽春的背景跟玩家圖示
    2. 可以用鍵盤操作玩家
    3. 整個遊戲目前有 3 個 state，分別是 `STATE_MENU`, `STATE_PLAY`, `STATE_ENDGAME`



* 作業流程：
    1. Fork [這個作業](https://github.com/Alx-Lai/Challenge2022-Homework) 然後 clone 到你的電腦，開新的 branch 叫作 new_feature。做完作業之後把 new_feature merge 回 master。
    2. 先看懂 code （沒有很多）（這份 code 是化簡了去年的 code，所以看懂了的話會幫助你之後去看去年 code 更細節的部份）。如果你真的完全看不懂 Pygame 的話，強烈建議先花兩個小時跟著 [這個 tutorial](https://nerdparadise.com/programming/pygame/part1) 走過一遍。
    3. 改 `Model.py` 加上玩家的碰撞判斷
    4. 改 `Model.py` 加上攻受交換的功能
    5. 改 `View.py` 顯示出現在的攻受狀態和交換的倒數
    6. 改 `View.py` 顯示遊戲的倒數計時器
    7. 改 `View.py` 跟 `Controller.py` 新增遊戲的暫停功能



* Optional（自由練習）
    1. 遊戲結束後，顯示勝負或計分版
    3. 把地圖改成無邊界（左進右出）（上進下出）
    4. 讓遊戲獲勝的條件從「碰到」變成「蓋過去」（類似 agar.io）（可能要讓攻的半徑變大）
    5. 新增道具（加速果實）（變大果實）（？？果實）
    6. 修改遊戲背景、玩家圖示
    7. 可以調整玩家數量（兩人、三人、四人）
    8. 讓遊戲跑得更快？
    9. 如果今天電腦比較爛，沒辦法跑到 60 fps，要怎麼調整程式，讓遊戲的進行跟 fps 無關？（提示：$\Delta x = v \cdot \Delta t$）
    10. 讓遊戲可以 restart
    11. 發揮你的創意？


