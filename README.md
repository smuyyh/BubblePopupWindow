# BubblePopupWindow
Android 实现各个方向的气泡弹窗，可控制气泡尖角偏移量。

### 截图
<img src="https://github.com/smuyyh/BubblePopupWindow/blob/master/screenshot/screen.png?raw=true" width=280/>

### 依赖
```
dependencies {
    compile 'com.yuyh.bubble:library:1.0.0'
}
```

### 使用
- 默认弹窗
```java
BubblePopupWindow leftTopWindow = new BubblePopupWindow(MainActivity.this);
View bubbleView = inflater.inflate(R.layout.layout_popup_view, null);
TextView tvContent = (TextView) bubbleView.findViewById(R.id.tvContent);
tvContent.setText("HelloWorld");
leftTopWindow.setBubbleView(bubbleView); // 设置气泡内容
leftTopWindow.show(view, Gravity.BOTTOM, 0); // 显示弹窗
```
```java
/**
 * 显示弹窗
 *
 * @param parent
 * @param gravity
 * @param bubbleOffset 气泡尖角位置偏移量。默认位于中间
 */
public void show(View parent, int gravity, float bubbleOffset) {
    // ...
}
```
- 自定义弹窗
使用气泡布局
```xml
<?xml version="1.0" encoding="utf-8"?>
<com.yuyh.library.BubbleRelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/brlBackground"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:background="@android:color/transparent"
    app:cornerRadius="10"
    app:halfBaseOfLeg="18dp"
    app:padding="18dp"
    app:shadowColor="#64000000"
    app:strokeWidth="5">
    
    <!-- add view  -->

</com.yuyh.library.BubbleRelativeLayout>
```
然后通过PopupWindow显示气泡弹窗，当然，也可直接显示气泡布局。
