#### Menu 菜单

- **三种Menu的menu.xml文件是一样的。不同的menu显示不一样。**
- menu的xml最多二级菜单。

##### OptionMenu 选项菜单

- **一个Activity当中只有一个OptionMenu。也就是toolbar右上角那三个点。**

**XML**

- 最多二级子菜单。

![image-20210626111100559](/home/mi/yankang/study/android/image/image-20210626111100559.png)

**加载Menu**

![image-20210626111624867](/home/mi/yankang/study/android/image/image-20210626111624867.png)

**监听Item**

![image-20210626112631633](/home/mi/yankang/study/android/image/image-20210626112631633.png)

**效果**

![image-20210626125315368](/home/mi/yankang/study/android/image/image-20210626125315368.png)

------------------------------------------------------------------------------------------------------------------------

![image-20210626125303579](/home/mi/yankang/study/android/image/image-20210626125303579.png)

------------------------------------------------------------------------------------------------------------------------



![image-20210626125324705](/home/mi/yankang/study/android/image/image-20210626125324705.png)

##### ContextMenu 上下文菜单

- ContextMenu的数量不受限制。
- 对于绑定了contextMenu的控件，必须长按才能生效。
- 比optionMenu多了注册。是正常的，因为要绑定到一个控件上。而optionMenu是直接和Activity挂钩的。
- 也是最多二级菜单。
- 在一个Activity当中。可以将contextMenu绑定到不同的组件上。一对多。
- 或者fragment上？

**第一种ContextMenu**

**效果**

![image-20210626125430699](/home/mi/yankang/study/android/image/image-20210626125430699.png)

**XML**

![image-20210626124419759](/home/mi/yankang/study/android/image/image-20210626124419759.png)

**代码**

![image-20210626124725875](/home/mi/yankang/study/android/image/image-20210626124725875.png)

**第二种ContextMenu**

效果

![image-20210627203722840](/home/mi/yankang/study/android/image/image-20210627203722840.png)

**XML**

和第一种一样。menu的xml是一样的

**代码**

![image-20210627203836534](/home/mi/yankang/study/android/image/image-20210627203836534.png)

![image-20210627203901009](/home/mi/yankang/study/android/image/image-20210627203901009.png)

##### PopupMenu 弹出菜单

xml一样。

代码new一个Menu。

![image-20210715163949684](/home/mi/.config/Typora/typora-user-images/image-20210715163949684.png)

![image-20210715164008151](/home/mi/.config/Typora/typora-user-images/image-20210715164008151.png)

