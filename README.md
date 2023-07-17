# 書籍 : <設計模式與遊戲開發的完美結合> 博碩文化

<h1> Part 1.設計模式 && 遊戲設計</h1>

<h2> Ch1.遊戲實作中的設計模式 </h2>

<h3> Ch1-2.設計模式是什麼? </h3>

解決一再出現的問題，"模式"=解決方案=SOP

<h3> Ch1-3.常見的設計原則 </h3>

常見:

+‧單一職責原則 (SRP: Single Responsibility Principle)：
當設計一個類別時，該類別應該只負責一個職責或功能。
例如，一個 User 類別應該只負責處理使用者的資料，而不應該同時負責處理資料庫連接或發送郵件等功能。


‧開放封閉原則 (OCP: Open-Closed Principle)：
軟體實體（類別、模組、函式等）應該對擴充開放，對修改關閉，透過介面或抽象化來實現。
假設有一個 Shape 抽象類別，它有一個 draw() 方法。現在我們要新增一個新的形狀 Triangle，我們可以繼承 Shape 並實作 draw() 方法以繪製三角形，而不需要修改原本的 Shape 類別。


‧里氏替代原則 (LSP: Liskov Substitution Principle)：
子類別必須能夠替換父類別，而不會破壞原有程式的正確性。
如果有一個父類別 Animal，它有一個 makeSound() 方法。
子類別如 Dog 或 Cat 應該可以替代父類別 Animal，而不影響原本的程式邏輯。例如，Dog 和 Cat 都可以實作自己的 makeSound() 方法，但仍然可以被視為 Animal 的替代品。

‧依賴性反向原則 (DIP: Dependency Inversion Principle)：
1.高層模組不應該依賴於低層模組，兩者都應該依賴於抽象介面或共同的抽象層級。
2.抽象介面不應該依賴於實作細節，實作細節應該依賴於抽象介面。
假設有一個高層模組 NotificationManager 負責處理通知的發送，它依賴於抽象的 NotificationService 介面，而不是具體的實作。
具體的通知服務如 EmailNotificationService 或 SMSNotificationService 會實作 NotificationService 介面，然後被注入到 NotificationManager 中。


‧介面分割原則 (ISP: Interface Segregation Principle)：
客戶端不應該被迫使用不需要的介面方法。介面應該細分為特定職責或使用場景的小型介面。
假設有一個 FileManager 類別，它實作了 readFile() 和 writeFile() 兩個方法。
如果某個客戶端只需要使用 readFile() 方法，則不應該被迫實作或使用不需要的 writeFile() 方法。
可以將 FileManager 的功能分割成兩個介面，分別是 Readable 和 Writable，讓客戶端只實作需要的介面。


‧最少知識原則 (LKP: Least Knowledge Principle)：
一個類別應該具備最少的知識，只和直接相關的類別互動，減少類別之間的耦合度。
如果一個類別需要與其他多個類別進行互動，最好的做法是僅與直接相關的類別進行互動，減少類別之間的依賴關係。
例如，一個 Order 類別不應該直接與 PaymentGateway 進行互動，而應該委派給一個 PaymentProcessor 類別處理支付相關的操作，從而降低了 Order 類別對於支付系統的知識和依賴。


‧少使用繼承，多使用組合是一種常見的設計原則，稱為"優先使用組合（Favor Composition Over Inheritance）"
1.避免類別之間的緊密耦合，提高靈活性和可維護性。
2.提高代碼的可讀性，降低複雜性。
3.更好的彈性和擴展性。
4.促進代碼重用。
範例：
假設我們正在開發一個遊戲，有不同種類的角色，如戰士（Warrior）和法師（Mage）。這些角色都有一些共同的屬性和行為，例如名字（Name）和攻擊（Attack）。
傳統的設計方法可能是創建一個父類別 Character，然後讓戰士和法師透過繼承來獲得共同的屬性和方法。然而，使用繼承可能會產生複雜性和耦合度的問題。
相反，我們可以使用組合來實現這個需求。首先，創建一個 Character 類別，它包含共同的屬性和行為，例如名字和攻擊。然後，分別創建 Warrior 和 Mage 類別，它們分別擁有獨特的屬性和方法。
在每個類別中，將 Character 物件作為成員變數組合進來。這樣一來，每個角色類別可以使用 Character 物件來訪問共同的屬性和行為，同時根據自己的特性來實現額外的行為。


<h3> Ch1-4.為什麼要學設計模式 </h3>

學習先人智慧
不必重新思考新的解決方案
被驗證過的模式


<h3> Ch1-6. </h3>

三大類:
生成模式 (Creational):產生物件的過程及方式
結構模式 (Structural):類別或物件之件組合的方式
行為模式 (Behavioral):類別或物件之間互動或是責任分配的方式

<h1> Part 2-基礎系統</h1>

<h3> Ch3.遊戲場景轉換 - State 狀態模式 </h3>

7/17

![image](https://github.com/10gt12nc/DesignPatterns/blob/main/Imge/CH3%20State/%E8%A6%8F%E5%8A%83.png)

![image](https://github.com/10gt12nc/DesignPatterns/blob/main/Imge/CH3%20State/%E7%B5%90%E6%A7%8B.png)

: 讓一個物件的行為隨著內部狀態的改變而變化，而該物件也像換了類別一樣。

‧GameLoop
遊戲主迴圈

‧SceneStateController 
場景狀態控制者 

‧ISceneState
介面

‧StartState 、MainMenuState、BattleState
對應 開始場景、主畫面場景、 戰鬥場景



<h3> Ch4.遊戲主要類別 - Facade 外觀模式 </h3>

: 替子系統定義一組統一的介面，這個高階的介面會讓子系統更容易被使用。


![image](https://github.com/10gt12nc/DesignPatterns/blob/main/Imge/CH4%20Facade/%E7%B5%90%E6%A7%8B.png)


PBaseDefenseGame 類別 = 整合所有子系統，並提供高階介面的外觀模式類別。



<h1> Part 3.角色的設計</h1>
<h1> Part 4.角色的產生</h1>
<h1> Part 5.戰爭開始</h1>
<h1> Part 6.輔助系統</h1>
<h1> Part 7.調整與最佳化</h1>
<h1> Part 8.未明確使用的模式</h1>

