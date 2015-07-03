###带清除按钮的 EditText
---
在输入框中输入内容后会在输入框右侧自动显示清除按钮，点击可清空输入框文本。

清除按钮的样式可以自定义，设置方法如下：  
在代码中设置：  
`editText.setIconClear(R.drawable.ic_clear);`  
也可在布局文件中设置：  
`app:iconClear="@drawable/ic_clear"`  

需要注意两点:  
1. 清除按钮会占据 `drawableRight` 的位置，所以 `ClearEditText` 设置 `drawableRight` 属性无效果;  
2. 在 `ClearEditText` 中实现了默认的 `TextWatcher`，便于更新清除按钮显示状态，
如果要设置自定义的 `TextWatcher`，需要在接口方法 `afterTextChanged(Editable s)` 调用 `editText.updateIconClear();
`，此方法用于更新清除按钮状态。  

显示效果：  
<img src="/screenshots/s1.jpg" alt="输入内容前" title="输入内容前" width="270" height="486" />
<img src="/screenshots/s2.jpg" alt="输入内容后" title="输入内容后" width="270" height="486" />
