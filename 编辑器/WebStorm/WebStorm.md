# 快捷键

Shift + Alt + F10：调出运行列表

Ctrl + Shift + J：将选中的行合并成一行

Alt + 向左箭头：上一个编辑器

Alt + 向右箭头：下一个编辑器

Ctrl + B：定位至声明的位置

Ctrl + Alt + B：定位至选中类或者方法的具体实现

Ctrl + Shift + B:直接定位至光标所在变量的类型定义

Ctrl + U：直接定位至当前方法 override 或者 implements 的方法定义处

Ctrl + F12：显示当前文件的文件结构

Ctrl + Alt + F12：显示当前文件的路径，并可以方便的将相关父路径打开

Ctrl + H：显示当前类的继承层次

Ctrl + Shift + H：显示当前方法的继承层次

Ctrl + Alt + H：显示当前方法的调用层次

F2：定位至下一个错误处

Shift + F2：定位至前一个错误处

Ctrl + Alt + 向上箭头：查找前一个变量共现的地方

Ctrl + Alt + 向下箭头：查找下一个变量共现的地方

Ctrl + =：展开代码

Ctrl + -：收缩代码

Ctrl + Alt + =：递归展开代码

Ctrl + Alt + -：递归收缩代码

Ctrl + Shift + =：展开所有代码

Ctrl + Shift + -：收缩所有代码

Ctrl + Shitft + 向下箭头：将光标所在的代码块向下整体移动

Ctrl + Shift + 向上箭头：将光标所在的代码块向上整体移动

Ctrl + Alt + Shift + 向左箭头：将元素向左移动

Ctrl + Alt + Shift + 向右箭头：将元素向右移动

Alt + Shift + 向下箭头：将行向下移动

Alt + Shift + 向上箭头：将行向上移动

Ctrl + F：在当前文件中查找

Ctrl + R：替换字符串

Ctrl + Shift + F:在全局文件中查找字符串

Ctrl + Shift + R：在全局中替换字符串

Alt + F7：查找当前变量的使用，并列表显示

Ctrl + Alt + F7：查找当前变量的使用，并直接对话框提示

Ctrl + F7：在文件中查找符号的使用

Ctrl + Shift + F7：在文件中高亮显示变量的使用

Ctrl + O：重写基类方法

Ctrl + I：实现基类或接口中的方法

Alt + Insert：产生构造方法，get/set 方法等

Ctrl + Alt + T：将选中的代码使用 if、while、try/catch 等包装

Ctrl + Shitf + Delete：去除相关的包装代码

Alt + /：自动完成

Alt + Enter：自动提示完成，抛出异常

Ctrl + /：使用 // 注释

Ctrl + Shift + /：使用 /**/ 注释

Ctrl + Alt + L：格式化代码

Ctrl + Alt + O：优化 import

Ctrl + ]：快速跳转至诸如 {} 围起来的代码块的结尾处

Ctrl + [：快速跳转至诸如 {} 围起来的代码块的开头处

Ctrl + Shift + Enter：将输入的 if、for、函数等等补上 {} 或者，使代码语句完整

Shift + Enter：在当前行的下方开始新行

Ctrl + Alt + Enter：在当前行的上方插入新行

Ctrl + Shift + U：切换大小写

Shift + F6：重命名1

Ctrl + Shift + F6：更改类型

# 设置

## 1. 禁用双修改键快捷方式（双击 Ctrl、双击 Shift）

Settings -> Advanced Settings -> 找到 User Interface 标题 -> 将 Disable double modifier key shortcuts 勾上

## 2. sass 全局配置

File -> New Projects Setup -> Settings for Vew Projects... -> Tools -> File Watchers -> 添加一个 scss -> 将 Arguments 的值修改为 --style=compressed --update --no-source-map $FileName$:$FileNameWithoutExtension$.min.css 即可