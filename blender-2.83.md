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

Auto Boolean Vs Brush Boolean (自動布林運算 Vs 遮罩布林運算) 自動布林運算是立即對物體做布林運算修改。遮罩布林運算是遮罩物體用來對物體做布林運算，可以立即看到布林修改結果，但未apply前，並不會更改幾何物體結構 (wireframe structure)的。遮罩布林運算其實是套用了Boolean Modifier(布林修改器)所產生的效果. 遮罩布林運算比直接套用Boolean Modifier省了很多steps.

Brush Boolan and Viewport Display | Display As Solid/Bound
遮罩布林運算的物體屬性編輯器的Viewport Display欄中的 Display As 可選Solid使得Brush Boolean不產生作用. 可選Bound恢愎其作用。

3.0 基礎建模練習
製作杯子
製作檯燈
製作椅子
製作書桌

5.1-Introducing vertice, edge, face 頂點，邊，面

切換物體到編輯模式: (1) 選擇物體，然後按Tab切換 (2) 選擇物體，然後按Ctrl+Tab啟動pie menu來選 Edit Mode 切換 (3) 選擇物體，然後從3D Viewport編輯器左上角的模式下拉選單來切換.
編輯模式中切換對頂點，邊及面的選取. 1鍵是頂點編輯模式. 2鍵是3D邊編輯模式. 3鍵是面編輯模式. 其它專有名詞名稱: Quad就是四個點的polygon. Triangle是三個點的face. 超過4個點的face叫做Ngon.
Shift-Select 連選多個頂點(線、面).  Alt-Select 選一條水平線或垂直線裡的所有頂點(線、面).
選擇物體相連頂點，邊或面的方法: 選擇物體的頂點，邊或面後，按L會選擇所有相連在物體上的相對應頂點，邊或面。
將同一物體的部份分離的方法:在編輯模式中選取要分離的部份(選點、邊、面都可以)，然後按L選取所有連結的部份，不可用A，A會全選所有編輯模式的物體。 按P顯示分離選單(Seperate)，然後選(Selection)，將所選物分離至一個新的物體。
Delete 及 Dissolve 的差別: 在編輯模式中，選一個頂點，邊或面。然後按X顯示刪除選單。 接下來可選Vertices或Dissolve Vertices，差別在於Dissolve不會造出缺口，而是使用Ngon。只用刪除Vertices會造出缺口. 刪除邊或面，Dissolve邊或面也是同樣的。 Ctrl+X 可以根據當前編輯模式(點，邊，面)來Dissolve所選區.

5.2  選取工具 (Selection Tool)
Ctrl Select vs Shift Select: Shift Select 可用來多選每個選取的物體(點，邊，面), Ctrl Select是選取兩個或以上點時，中間的點都會一起被選取。
Alt Select (loop select): 選取點、邊、面相連的迴路上的所有點、邊、面都被選取。迴路上如果有三角形，則超過一條路徑的可能性，則會被視為迴路的終點，不再進行選擇。
B (box)/ Ctrl B 可啟動方塊選取或取消選取。 在Solid View用方塊選取，無法選取到物體背面的幾何結構。在Wire Frame View用方塊選取，可以選取到物體背面的幾何結構。
C (circle)/ Shift C 可啟動圓形塗選取或取消選取, Enter Key 確定選取範圍。
Ctrl I: 反轉(inverse)當前選取區.
Ctrl +: Select More 多選一層 , Ctrl -: Select Less 少選一層.
L 選取當前連在一起的物體。 H / Alt H: hide/show 當前選取區。

3.3-Extrusion and face creation

Extrude 擠型:Extrude其實是複製所選區，然後舊的所選區連接到新複製出的所選區.
E S 鍵: 可以創造新的face在其所選的face上，這方法對點無效，因為點無法變大變小.
顯示3D平面法線的方法. 選 Viewport Overlays，然後按 Display Normals.

按住左鍵不放，可顯示 Extrude 選單: Extrude Region, Extrude Along Normals, and Extrude Individual.
Extrude Region 可在多選區(faces)中，根據各區塊(face)的平均法線來拉出，拉出來是一體的狀態。
Extrude Individual 可在多選區(faces)中，根據各區塊(face)的法線來拉出，拉出來是分開的狀態。

可在多選區(faces)中，令各個face都獨立的變大變小的方法: 多選後，按Transform Pivot Point下拉選單，然後選Individual Origins(使用各個物體的獨立 Local Origin).

製作方格濾網: Shift+A 加入一個Grid. Tab 到面編輯模式. A 全選. 選 Extrude Individual ，拉高一點點。 S 變小一點點。 此時，網格看起來像超市賣的巧克塊。 X 刪除當前所選的頂面就會變成方格濾網.
玻璃酒杯: Shift+A 加入一個 Circle. 用 E Z 拉出，E S 改變大小兩個功能，邊拉邊調整出酒杯的形狀。 最後可用 F 鍵來在己選的迴路中建立face來封面。
球體把手: Shift+A 加入一個球體 (UV Sphere). 在球體上面環面選四個面，下面環面另選四個面，按X刪除來上面兩個大孔。 選形成大孔迴路上的四點，然後按E Extrude拉出，按R調整做出手把U型。 
最後，相續各選四個點按F來建立face來封合，直到全部封合為止。
車形(機器)方體: Shift+A 加入一個平面，選二個點。使用Front View,然後E拉出車側邊的形狀，最後Shift + Select選四點按F封口. 用Ctrl +Select 選兩點時，會將兩點相連的路徑上的點也幫你自動選。

快速建模小技巧:
G G: Slide Mode 在不改變當前幾何結構下，移動當前所選的邊' 迴路'面等等)


