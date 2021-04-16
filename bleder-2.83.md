 Blender 2.83 版 
 
 在Stackoverflow 閱讀 Blender 相關問題,可幫助你快速增加所需的經驗知識。例子(https://blender.stackexchange.com/questions/46399/boolean-does-not-slice-correctly-using-difference)
 
 1.3 自定使用者界面 (Customizing the interface) 
 Blender 主視窗可開多個子視窗。
 每個子視窗都只能開一個編輯器。
 每個子視窗左上角的下拉按鈕可切換該子視窗的編輯器類型。
 鼠標在子視窗左上角時會轉成十字鼠標，此時左擊滑鼠鍵不放，下拉可clone分出一個水平子視窗編輯器。右拉可clone分出一個垂直子視窗編輯器
 鼠標在子視窗邊界處時會轉成垂直雙標或水平雙標，此時按右擊滑鼠鍵會出現分割組合視窗下拉選單, 可由下拉選單水平或垂直分出子視窗編輯器或合拼兩子視窗成為一個。
  
 2.4 物件模式基本操作 (Basic Manipulation)
 
G 移動,  S 改變大小,  R 旋轉
Alt L 重置原始位置, Alt S 重置原始大小, Alt R 重置原始角度
G [n] 移動 n 個單位, S [n] 改變大小 n 倍, R [n]  旋轉 n 度
Ctrl G 遞增移動, Ctrl S 遞增改變大小, Gtrl R 遞增旋轉
G [axis] 鎖定在某軸移動, S [axis] 鎖定在某軸改變大小, R [axis] 鎖定在某軸旋轉

Shift [Select] 選多個物件
Ctrl + J 將多個物件合在(join)在一起
Ctrl + D 複製一個物體複本
Alt + D   複製一個連結複本 (作用任一連結體，也會改變其它相連的連結體)

2.5-The outliners and the collections
Shift Select, A, Alt+A 用來選擇多個物體
選擇多個物體後，按 M 會出現選單，選 new Collection 就可將這些物體分成一組命名，該組名會出現在outliner.

2.6 物體之間的關系 Ojects Relationship
可建模一個簡單的方桌子，並將方桌子往上移，並以桌腳底放置 z = 0 的平面上。最後可將此模形所有組件以(0,0,0)為中心點的球體Empty空元件為父元件;此空元件可用來移動該物件

2.7 快捷選單及快速選單 (The context menu and quick shortcut)多門開關器的實作: 加入多個不同轉向的門，
快捷選單就是右鍵選單，在不同的編輯器，不同的模式，乃至不hip
可建模一個簡單的方桌子，並將方桌子往上移，並以桌腳底加入每個門中。可用同的物件上都有特定用途的快捷選單。
可以在選單選項上右擊任一選項，然後選Add/Remove to Quick Favorite, 就可以將此選項加入快速最愛的選單或移除.
可以在選單選項上右擊任一選項，然後選 Assigan鍵/Remove/Change Shortcut Key, 即可設定或移除該選項的快捷鍵.

2.8 物體條件限制(Oject Constraints)
在屬性編輯器中，可以針對選定的物體設定各種不同的物體條件限制器。
物體條件限制器主要有四種，Motion Tracking, Transform (轉移限制), Tracking (攝影機追蹤限制), Relationship (關系限制) .

五指控制器的製作: 加入三個圓柱體，加入一個空元件，將角度複制器 (Copy Rotation)加入第一個圓柱體，以空元件。各其它圓柱體各加入一個親子關系限制器(Child of)，讓其它圓柱體各以前一個圓柱體為父元件.
此時轉動空元件時，三個柱體會一起轉動。可在角度複制器 (Copy Rotation)上設定Set Inverse，並將Mix設成Offset. 這樣子元件圓柱體會offset回之前正確的位值。

多門開關器的實作: 加入多個不同轉向的門，加入一個空元件，將角度複制器 (Copy Rotation)加入每個門中。

2.9 布林工具 Bool Tool
布林工具是一個 Addon 工具,可由Edit|Perferences來啟動。Bool Tool AddOn 啟動後，在3D Viewport編輯器右邊界的左箭頭可拉出標籤頁，標籤頁中的Edit頁，就可展開 Bool Tool.

布林工具可令一個物體的部份被另一物體的部份形狀做布林操作，Difference: 去除另一物體的相交及其所有部份.  Union: 結合，只去除相交部份。 Intersect: 只留下相交部份。Slice: 砍去與另一物體相交部份，只留下不相交部份。 Union, Intersect及 slice 對是針對相交部份或不相交部份進行去除或保留的動作. 
如果Bool Tool無法得到預期結果，可先將其Join所有元件，然後使用Bool Modifier做同等Boolean 運算。

Union vs Join (Ctrl_J): 相結合(Union)與相連合(Join)的差別是，相結合(Union) 一個物體可與另一個物體相結合。這結合會改變3D幾何結構(Wireframe structure),兩物體相交的部份會被認為是多餘，而被去掉。 與相連合( Join, Ctrl+J) 的差別是，相連合僅僅是將兩物體相連在一起，不會改變3D幾何結構(Wireframe structure). 




