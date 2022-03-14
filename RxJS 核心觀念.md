# RxJS 核心觀念
:::info

當有非同步行為時，RxJS會把過程中產生的數據儲存在流裡面，當有需要取裡面的數據時，再透過訂閱把流開啟，讓資料流出，當然也可以自己透過一些運算子去控制流出的資料型態
> ReactiveX combines the Observer pattern with the Iterator pattern and functional programming with collections to fill the need for an ideal way of managing sequences of events.
:::
是一個用來做非同步行為處理的library，核心組件為Observable，再搭配其他支援的類型(Observer, Schedulers, Subjects)，還有一些運算子(概念類似於Array的filter、some...)，也可以想像成事件處理的library
## 使用方法
1. 創建Observable
建立一個流用來儲存一段時間或一段事件中的數據
2. 訂閱Observable
透過subscribe來啟動流
3. 執行Observable
需要被訂閱後才會啟動流，才能看到流裡面的數據

### JavaScript中類似手法
* callback
* Promise 物件
* 語法糖 async/await 
### 非同步常遇到的問題
* 競態條件 (Race Condition)
* 記憶體洩漏 (Memory Leak)
* 複雜的狀態 (Complex State)
* 例外處理 (Exception Handling)

## 型別
### Observable 
被觀察的物件，未來可被調用的物件或事件，一個會隨時間增加數據的集合
### Observer 觀察者
callbacks 用來監聽Observable是否有發送值，接收觀察結果，處理流
### Subscription 訂閱
代表Observable的執行，在取消執行上很有用，Observable物件要透過訂閱才能解析其中的資料
### Operators
用來做資料處理的運算子們
### Subject
等同於EventEmitter，用來廣播傳送值給多個Observer的唯一方法
### Schedulers（還沒使用過待研究）
> are centralized dispatchers to control concurrency, allowing us to coordinate when computation happens on e.g. setTimeout or requestAnimationFrame or others.
### BehaviorSubject
只會儲存最新的值
* 取當下儲存的內容
`BehaviorSubject.value`

---

[最简Rxjs入门教程--别再被Rxjs的概念淹没了](https://juejin.cn/post/7003328753556258846)
[RxJS官網](https://rxjs.dev/)
[RxJS快速入门-掘金](https://juejin.cn/post/6844904078091223054)
[希望是最淺顯易懂的 RxJS 教學](https://blog.techbridge.cc/2017/12/08/rxjs/)
[尾呼優化(tail call optimization)](https://2ality.com/2015/06/tail-call-optimization.html)
[30 天精通 RxJS](https://blog.jerry-hong.com/series/rxjs/thirty-days-RxJS-01/)
###### tags: `Angular`