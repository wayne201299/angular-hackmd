:::info
依執行順序排列
:::
# Constructor
* TypeScript特性之一，非Angular生命週期之一
* 是類別的屬性， Angular 並不能控制 constructor
* 會在 class（類別）建立時最先被執行
* 當 constructor 執行時，元件尚未被初始化，因此幾乎不會在這個階段寫程式碼
* 主要用於相依注入（dependency injection），例如服務、函式或值


:::info
在ngOnInit跟constructor裡寫邏輯的區別?
Constructor是class中預設的方法，當class被實現的話就會呼叫Dependency Injector 依賴注入則會分析constructor中的參數，當有使用時會去參照@component裝飾器中的providers來去實現注入物件
:::

# ngOnChanges
- 最先被觸發
- @input()的值有變動會觸發，父元件透過屬性繫結傳遞資料

# ngOnInit
* 元件初始化完成時呼叫
* 只會被呼叫一次

# ngDoCheck()

# ngAfterContentInit()


# ngAfterContentChecked()


# ngAfterViewInit()
- @ViewChild的值會在這裡取得，可以透過在viewchild添加{ static: true }，讓元素在ngAfterViewInit之前被渲染，避免因為ngif而導致取不到viewchild的值
    ```typescript!
    @ViewChild('calendarComponent', { static: false })
        calendarComponent!: FullCalendarComponent;
    ```


# ngAfterViewChecked()


# ngOnDestroy()
- 當component被移除時觸發
- 常用在取消訂閱，避免memory leak或重複訂閱

:::warning
* 初始化時若沒先賦值會導致undefined錯誤出現，可在constructor中先做賦值
:::


---
相關連結
[Angular lifecycle hook](https://angular.tw/guide/lifecycle-hooks)
###### tags: `Angular`
