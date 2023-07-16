
# 書籍 : <設計模式與遊戲開發的完美結合> 博碩文化

<h1> Part 1.設計模式 && 遊戲設計</h1>

<h2> Ch1.遊戲實作中的設計模式 </h2>

<h3> Ch1-2.設計模式是什麼? </h3>

解決一再出現的問題，"模式"=解決方案=SOP

<h3> Ch1-3.常見的設計原則 </h3>

常見:

•單一職責原則 (SRP: Single Responsibility Principle)：
當設計一個類別時，該類別應該只負責一個職責或功能。
例如，一個 User 類別應該只負責處理使用者的資料，而不應該同時負責處理資料庫連接或發送郵件等功能。

•開放封閉原則 (OCP: Open-Closed Principle)：
軟體實體（類別、模組、函式等）應該對擴充開放，對修改關閉，透過介面或抽象化來實現。
假設有一個 Shape 抽象類別，它有一個 draw() 方法。現在我們要新增一個新的形狀 Triangle，我們可以繼承 Shape 並實作 draw() 方法以繪製三角形，而不需要修改原本的 Shape 類別。


•里氏替代原則 (LSP: Liskov Substitution Principle)：
子類別必須能夠替換父類別，而不會破壞原有程式的正確性。
如果有一個父類別 Animal，它有一個 makeSound() 方法。
子類別如 Dog 或 Cat 應該可以替代父類別 Animal，而不影響原本的程式邏輯。例如，Dog 和 Cat 都可以實作自己的 makeSound() 方法，但仍然可以被視為 Animal 的替代品。


•依賴性反向原則 (DIP: Dependency Inversion Principle)：
1.高層模組不應該依賴於低層模組，兩者都應該依賴於抽象介面或共同的抽象層級。
2.抽象介面不應該依賴於實作細節，實作細節應該依賴於抽象介面。
假設有一個高層模組 NotificationManager 負責處理通知的發送，它依賴於抽象的 NotificationService 介面，而不是具體的實作。
具體的通知服務如 EmailNotificationService 或 SMSNotificationService 會實作 NotificationService 介面，然後被注入到 NotificationManager 中。


•介面分割原則 (ISP: Interface Segregation Principle)：
客戶端不應該被迫使用不需要的介面方法。介面應該細分為特定職責或使用場景的小型介面。
假設有一個 FileManager 類別，它實作了 readFile() 和 writeFile() 兩個方法。
如果某個客戶端只需要使用 readFile() 方法，則不應該被迫實作或使用不需要的 writeFile() 方法。
可以將 FileManager 的功能分割成兩個介面，分別是 Readable 和 Writable，讓客戶端只實作需要的介面。


•最少知識原則 (LKP: Least Knowledge Principle)：
一個類別應該具備最少的知識，只和直接相關的類別互動，減少類別之間的耦合度。
如果一個類別需要與其他多個類別進行互動，最好的做法是僅與直接相關的類別進行互動，減少類別之間的依賴關係。
例如，一個 Order 類別不應該直接與 PaymentGateway 進行互動，而應該委派給一個 PaymentProcessor 類別處理支付相關的操作，從而降低了 Order 類別對於支付系統的知識和依賴。

•少使用繼承，多使用組合是一種常見的設計原則，稱為"優先使用組合（Favor Composition Over Inheritance）"
1.避免類別之間的緊密耦合，提高靈活性和可維護性。
2.提高代碼的可讀性，降低複雜性。
3.更好的彈性和擴展性。
4.促進代碼重用。
範例：
假設我們正在開發一個遊戲，有不同種類的角色，如戰士（Warrior）和法師（Mage）。這些角色都有一些共同的屬性和行為，例如名字（Name）和攻擊（Attack）。
傳統的設計方法可能是創建一個父類別 Character，然後讓戰士和法師透過繼承來獲得共同的屬性和方法。然而，使用繼承可能會產生複雜性和耦合度的問題。
相反，我們可以使用組合來實現這個需求。首先，創建一個 ICharacter 介面，它只包含基本的屬性和方法。然後，創建一個 Warrior 類別和一個 Mage 類別，它們分別包含獨特的屬性和方法。(ISP)
這樣我們可以更靈活地組合不同的角色特性，同時避免了繼承帶來的問題。

<h1> Part 2-基礎系統</h1>
<h1> Part 3.角色的設計</h1>
<h1> Part 4.角色的產生</h1>
<h1> Part 5.戰爭開始</h1>
<h1> Part 6.輔助系統</h1>
<h1> Part 7.調整與最佳化</h1>
<h1> Part 8.未明確使用的模式</h1>

