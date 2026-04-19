# 附錄 C 本書常用 Swift 與 SwiftUI 速查

## 這份附錄怎麼用

這不是拿來從頭閱讀的章節，而是一本小型速查表。

當你在正文裡反覆看到某些語法，卻總覺得「我好像看過，但一時想不起來」，就回來查這裡。

## 1. 常見 Swift 宣告

```swift
let title = "今天"
var count = 0
```

- `let`：建立後不再改動
- `var`：後面可能還會改

```swift
struct Habit {
    let name: String
    var isCompletedToday: Bool
}
```

- `struct`：把一組有關的資料包在一起

```swift
enum LoadState {
    case idle
    case loading
    case loaded
    case failed
}
```

- `enum`：描述有限種狀態

## 2. 常見 SwiftUI 屬性標記

```swift
@State private var isCompletedToday = false
```

- 本地畫面狀態

```swift
@Binding var habit: Habit
```

- 子視圖需要修改父視圖持有的資料

## 3. 常見畫面容器

```swift
VStack { }
HStack { }
ZStack { }
```

- `VStack`：垂直排列
- `HStack`：水平排列
- `ZStack`：疊在同一層

## 4. 常見畫面元素

```swift
Text("今天")
Image(systemName: "checkmark.circle.fill")
Button("標記完成") { }
```

這三個幾乎會一路跟著你讀完整本書。

## 5. 常見 modifier

```swift
.padding()
.background(...)
.clipShape(...)
.foregroundStyle(...)
.frame(maxWidth: .infinity)
```

你可以先這樣記：

- `.padding()`：留空間
- `.background(...)`：補背景
- `.clipShape(...)`：裁形狀
- `.foregroundStyle(...)`：調整前景顏色或樣式
- `.frame(...)`：控制尺寸與對齊

## 6. 常見控制流程

```swift
if habits.isEmpty {
    Text("還沒有習慣")
} else {
    HabitList(habits: habits)
}
```

- `if / else`：根據不同條件顯示不同畫面

```swift
ForEach(habits) { habit in
    Text(habit.name)
}
```

- `ForEach`：把一組資料逐筆顯示出來

## 7. 常見行為傳遞

```swift
Button {
    isCompletedToday.toggle()
} label: {
    Text("切換")
}
```

- 大括號裡是要執行的行為

```swift
onSave: {
    saveHabit()
}
```

- closure 常常被拿來把行為往下傳

## 8. 常見非同步與載入

```swift
.task {
    await model.load()
}
```

- 畫面出現時觸發載入工作

```swift
switch loadState {
case .idle:
    EmptyView()
case .loading:
    ProgressView()
case .loaded:
    ContentView()
case .failed:
    ErrorView()
}
```

- 根據載入狀態顯示不同畫面

## 9. 讀正文時最值得先記住的判斷

- 畫面是由狀態推導出來的
- 一份真實資料最好只有一個可信來源
- 子視圖只讀時傳值，需要修改時傳 `Binding`
- 畫面狀態、長期資料、資料來源責任最好分開
- Preview、測試、手動驗證各自處理不同風險

## 本附錄小結

如果你每次卡住時，都能先回來用這份速查把語法重新接上，正文的閱讀節奏會順很多。這份附錄存在的目的不是取代正文，而是讓你不要因為忘記某個小語法，就在真正重要的觀念前停太久。
