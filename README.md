# 書籍 : <設計模式與遊戲開發的完美結合> 博碩文化

<h1> Part 1.設計模式 && 遊戲設計</h1>

<h2>  Ch1.遊戲實作中的設計模式 </h2>

<h3>  Ch1-2.設計模式是什麼? </h3>

解決一再出現的問題，"模式"=解決方案=SOP

<h3>  Ch1-3.常見的設計原則 </h3>

----
‧ 單一職責原則 (SRP: Single Responsibility Principle)：<br>
當設計一個類別時，該類別應該只負責一個職責或功能。<br>
例如，一個 User 類別應該只負責處理使用者的資料，而不應該同時負責處理資料庫連接或發送郵件等功能。<br>

----
‧ 開放封閉原則 (OCP: Open-Closed Principle)：<br>
軟體實體（類別、模組、函式等）應該對擴充開放，對修改關閉，透過介面或抽象化來實現。<br>
假設有一個 Shape 抽象類別，它有一個 draw() 方法。<br>
現在我們要新增一個新的形狀 Triangle，我們可以繼承 Shape 並實作 draw() 方法以繪製三角形，而不需要修改原本的 Shape 類別。<br>

----
‧ 里氏替代原則 (LSP: Liskov Substitution Principle)：<br>
子類別必須能夠替換父類別，而不會破壞原有程式的正確性。<br>
如果有一個父類別 Animal，它有一個 makeSound() 方法。<br>
子類別如 Dog 或 Cat 應該可以替代父類別 Animal，而不影響原本的程式邏輯。<br>
例如，Dog 和 Cat 都可以實作自己的 makeSound() 方法，但仍然可以被視為 Animal 的替代品。<br>

----
‧ 依賴性反向原則 (DIP: Dependency Inversion Principle)：<br>
1.高層模組不應該依賴於低層模組，兩者都應該依賴於抽象介面或共同的抽象層級。<br>
2.抽象介面不應該依賴於實作細節，實作細節應該依賴於抽象介面。<br>
假設有一個高層模組 NotificationManager 負責處理通知的發送，它依賴於抽象的 NotificationService 介面，而不是具體的實作。<br>
具體的通知服務如 EmailNotificationService 或 SMSNotificationService 會實作 NotificationService 介面，然後被注入到 NotificationManager 中。<br>

----
‧ 介面分割原則 (ISP: Interface Segregation Principle)：<br>
客戶端不應該被迫使用不需要的介面方法。介面應該細分為特定職責或使用場景的小型介面。<br>
假設有一個 FileManager 類別，它實作了 readFile() 和 writeFile() 兩個方法。<br>
如果某個客戶端只需要使用 readFile() 方法，則不應該被迫實作或使用不需要的 writeFile() 方法。<br>
可以將 FileManager 的功能分割成兩個介面，分別是 Readable 和 Writable，讓客戶端只實作需要的介面。<br>

----
‧ 最少知識原則 (LKP: Least Knowledge Principle)：<br>
(迪米特法則)<br>
一個類別應該具備最少的知識，只和直接相關的類別互動，減少類別之間的耦合度。<br>
如果一個類別需要與其他多個類別進行互動，最好的做法是僅與直接相關的類別進行互動，減少類別之間的依賴關係。<br>
例如，一個 Order 類別不應該直接與 PaymentGateway 進行互動，而應該委派給一個 PaymentProcessor 類別處理支付相關的操作，從而降低了 Order 類別對於支付系統的知識和依賴。<br>


----
‧ 少使用繼承，多使用組合是一種常見的設計原則，稱為"優先使用組合（Favor Composition Over Inheritance）"<br>
1.避免類別之間的緊密耦合，提高靈活性和可維護性。<br>
2.提高代碼的可讀性，降低複雜性。<br>
3.更好的彈性和擴展性。<br>
4.促進代碼重用。<br>
範例：<br>
假設我們正在開發一個遊戲，有不同種類的角色，如戰士（Warrior）和法師（Mage）。<br>
這些角色都有一些共同的屬性和行為，例如名字（Name）和攻擊（Attack）。<br>
傳統的設計方法可能是創建一個父類別 Character，然後讓戰士和法師透過繼承來獲得共同的屬性和方法。然而，使用繼承可能會產生複雜性和耦合度的問題。<br>
使用組合來實現這個需求:<br>
首先，創建一個 Character 類別，它包含共同的屬性和行為，例如名字和攻擊。然後，分別創建 Warrior 和 Mage 類別，它們分別擁有獨特的屬性和方法。<br>
在每個類別中，將 Character 物件作為成員變數組合進來。這樣一來，每個角色類別可以使用 Character 物件來訪問共同的屬性和行為，同時根據自己的特性來實現額外的行為。<br>

----

<h3>  Ch1-4.為什麼要學設計模式 </h3>

學習先人智慧<br>
不必重新思考新的解決方案<br>
被驗證過的模式<br>


<h3>  Ch1-6.三大類: </h3>

----
‧ 生成模式 (Creational):產生物件的過程及方式<br>
簡單工廠 <br>
Ch5.Singleton 獨體,單例 <br>
Ch14.工廠方法<br>
Ch15.建造者 <br>
Ch27.原型<br>
Ch28.抽象工廠<br>

----
‧ 結構模式 (Structural):類別或物件之件組合的方式<br>
Ch4.外觀<br>
Ch9.橋接<br>
Ch16.享元<br>
Ch17.組合<br>
Ch24.裝飾<br>
Ch25.轉接,轉換器<br>
Ch26.代理<br>

----
‧ 行為模式 (Behavioral):類別或物件之間互動或是責任分配的方式<br>
Ch3、12.狀態<br>
Ch6.仲介者<br>
Ch10.策略<br>
Ch11.範本,樣板方法<br>
Ch19.命令<br>
Ch20.責任鏈<br>
Ch21.觀察者<br>
Ch22.備忘錄<br>
Ch23.訪問者<br>
Ch27.迭代器<br>
Ch27.解釋器<br>

----

<h1> Part 2.基礎系統</h1>

<h2>  Ch3.遊戲場景轉換 - State 狀態模式 </h2>


![image](https://github.com/10gt12nc/DesignPatterns/blob/main/Imge/CH3%20State/%E8%A6%8F%E5%8A%83.png)

![image](https://github.com/10gt12nc/DesignPatterns/blob/main/Imge/CH3%20State/%E7%B5%90%E6%A7%8B.png)

: 讓一個物件的行為隨著內部狀態的改變而變化，而該物件也像換了類別一樣。

‧GameLoop 遊戲主迴圈
不繼承Monobehavior，定期更新，與遊戲引擎解耦
//BattleState - StateUpdate() 遊戲邏輯(各遊戲系統)  Game Loop
PBaseDefenseGame.Instance.Update();

‧ SceneStateController 
場景狀態控制者 

‧ ISceneState
介面

‧ StartState 、MainMenuState、BattleState
對應 開始場景、主畫面場景、 戰鬥場景



<h2>  Ch4.遊戲主要類別 - Facade 外觀模式 </h2>


![image](https://github.com/10gt12nc/DesignPatterns/blob/main/Imge/CH4%20Facade/%E7%B5%90%E6%A7%8B.png)

: 替子系統定義一組統一的介面，這個高階的介面會讓子系統更容易被使用。

‧ GameEventSystem、CampSystem ...

‧ PBaseDefenseGame 類別
整合所有子系統，並提供高階介面的外觀模式類別。

‧ BattleState 戰鬥狀態類別
//Facade
PBaseDefenseGame.Instance.Initinal();


<h2>  Ch5.唯一物件 - Singleton 單例模式 </h2>


![image](https://github.com/10gt12nc/DesignPatterns/blob/main/Imge/CH5%20Singleton/%E7%B5%90%E6%A7%8B.png)

:確認類別只有一個物件，並且提供一個全域的方法來取得這個物件。

‧ PBaseDefenseGame 類別
// Singleton 單例
private static PBaseDefenseGame _instance;
...

‧ BattleState 戰鬥狀態類別
//取得唯一物件
PBaseDefenseGame.Instance. ...


<h2>  Ch6.各系統整合 - Mediator 仲介者模式 </h2>


![image](https://github.com/10gt12nc/DesignPatterns/blob/main/Imge/CH6%20Mediator/%E7%B5%90%E6%A7%8B.png)

:定義一個介面用來包裝一群物件的互動行為。仲介者藉由移除物件間的引用，來減少他們之間的耦合。並能讓你改變他們之間的互動獨立性。

‧ PBaseDefenseGame 仲介者，串接 遊戲系統 & 玩家介面

‧ IGameSyatem  (BaseClass 資料夾裡)
遊戲系統 共同父類

‧ GameEventSystem、CampSystem ...
各系統

‧ IUserInterface  (BaseClass 資料夾裡)
玩家介面 共同父類

‧ SoldierInfoUI、CampInfoUI ...
各系統


<h1> Part 3.角色的設計</h1>

<h2>  Ch8.角色系統的設計分析 -  </h2>

![image]()

‧ ICharacter
‧ ISoldier
‧ IEnemy

<h2>  Ch9.角色與武器的實作 - Bridge 橋接模式 </h2>


![image]()

:將抽象與實作分離，讓他們之間的變化獨立。(定義一個介面類別，然後將實作的部分在子類別中完成)。

‧ ICharacter
組合 IWeapon，宣告武器攻擊目標方法(WeaponAttackTarget)。
‧ ISoldier、IEnemy
實作 武器攻擊目標方法(WeaponAttackTarget)，使用目前裝備攻擊對手

‧ IWeapon
武器介面
‧ WeaponGun、WeaponRifle、WeaponRocket ...
實作

<h2>  Ch10.角色數值的計算 - Strategy 策略模式 </h2>


![image]()

:定義一群演算法，並封裝每個演算法，讓他們可以彼此交換使用。策略模式讓這些演算法在客戶端使用它們時能更加獨立。

‧ ICharacter
組合 ICharacterAttr
// 數值
protected ICharacterAttr m_Attribute = null;

‧ ICharacterAttr
角色數值界面，組合IAttrStrategy 呼叫真正計算。

‧ SoldierAttr、EnemyAttr
繼承 ICharacterAttr

‧ IAttrStrategy
角色數值計算界面，分離 ICharacterAttr，讓 ICharacterAttr 更容易更換計算策略。

‧ EnemyAttr
實作 敵方單位的數值計算策略

‧ SoldierAttr
實作 玩家單位(士兵)的數值計算策略


<h2>  Ch11.攻擊特效與擊中反應 - Template Method 樣板方法模式 </h2>


![image]()

:在一個操作方法中定義演算法的流程，當中某些步驟由子類別完成。樣板方法模式讓子類別在不更動原有演算法的流程下，還能夠重新定義當中的步驟。

‧ IWeapon
攻擊目標 Fire 方法中，執行步驟宣告為抽象方法
// 顯示武器子彈特效(子類別實作)
DoShowBulletEffect(theTarget);
// 顯示音效(子類別實作)
DoShowSoundEffect();
<br>
// 顯示武器子彈特效
protected abstract void DoShowBulletEffect(ICharacter theTarget);
// 顯示音效
protected abstract void DoShowSoundEffect();

‧ WeaponGun、WeaponRifle、WeaponRocket ...
實作 IWeapon 中需要被實作的 抽象方法


![image]()

‧ ICharacter
// 被攻擊
 public abstract void UnderAttack
 
‧ ISoldier、IEnemy
UnderAttack
DoPlayKilledSound();    // 音效
DoShowKilledEffect();   // 特效           
// 播放音效
public abstract void DoPlayKilledSound();
// 播放特效
public abstract void DoShowKilledEffect();
	
‧ ISoldier 陣營 : Captain上尉、Rookie新兵、Sergeant中士
實作 
‧ IEnemy 陣營 : Troll山妖、Ogre怪物、Elf精靈
實作 


<h2>  Ch12.角色AI - State 狀態模式 </h2>

<h1> Part 4.角色的產生</h1>

<h2>  Ch14.角色的產生 - Factory Method 工廠方法模式 </h2>
<h2>  Ch15.角色的組裝 - Builder 建造者模式 </h2>
<h2>  Ch16.數值管理功能 - Flyweight 享元模式 </h2>


<h1> Part 5.戰爭開始</h1>

<h2>  Ch17.介面設計 - Composite 組合模式 </h2>
<h2>  Ch19.兵營訓練單位 - Command 命令模式 </h2>
<h2>  Ch20.關卡設計 - Chain of Responsibility 責任鏈模式 </h2>

<h1> Part 6.輔助系統</h1>

<h2>  Ch21.成就系統 - Observer 觀察者模式 </h2>
<h2>  Ch22.存檔功能 - Memento 備忘錄模式 </h2>
<h2>  Ch23.角色資訊查詢 - Visitor 訪問者模式 </h2>

<h1> Part 7.調整與最佳化</h1>

<h2>  Ch24.字首字尾 - Decorator 裝飾模式 </h2>
<h2>  Ch25.俘兵 - Adapter 轉換器模式 </h2>
<h2>  Ch26.載入速度最佳化 - Proxy 代理模式 </h2>

<h1> Part 8.未明確使用的模式</h1>
<h2>  Ch27.Iterator 迭代器、Prototype 原型、Interpreter 解釋器 </h2>
<h2>  Ch28.Abstract Factory 抽象工廠 </h2>


<h1> UML </h1>

![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()
![image]()