### View 控件的根。布局也是控件？

android当中所有可视的空间都叫做View。

- **TextView**
- **Button**
- **EditView**
- **ImageView**
- **ProgressBar**
- 布局也是view。继承。

![image-20210616135618270](image/image-20210616135618270.png)

### 通用属性：代表view？

![image-20210616135829604](image/image-20210616135829604.png)

### TextView

![image-20210616135933506](image/image-20210616135933506.png)

### EditText

![image-20210616140001943](image/image-20210616140001943.png)

### Button

四种点击事件

#### 内部类

![image-20210616151342929](image/image-20210616151342929.png)

#### 匿名内部类

![image-20210616151449347](image/image-20210616151449347.png)

#### Activity

实现接口。

传入this。

#### XML 

![image-20210616154828453](image/image-20210616154828453.png)

![image-20210616154917587](image/image-20210616154917587.png)

### ImageView

android:src = 

![image-20210617072012213](image/image-20210617072012213.png)

android:background = 

![image-20210617072107059](image/image-20210617072107059.png)

### ProgressBar

进度条

![image-20210617091559013](image/image-20210617091559013.png)

代码控制进度条

![image-20210617091715919](image/image-20210617091715919.png)

### Seekbar

#### XML

- **android:max = "100"**
- **android:progress = "35" //seekbar的默认位置。**

#### Code

普通方法

- **setProgress(35);//设置progress**
- **getProgress();//获得progress**
- **setMax(120)//设置max**

![image-20210620153216528](image/image-20210620153216528.png)

**LogCat打印：**

![image-20210620153318167](image/image-20210620153318167.png)

#### SeekBar和progressBar

- **SeekBar可以拖拽。progressBar只能显示。**

### CheckBox（多选）

#### **XML**

- **android:checked = "false/true" 设置选中状态。**
- **用LinearLayout包裹若干个checkBox控件。**

#### Code

- **setChecked(true/false) //设置选中状态**
- **boolean isChecked()//返回选中状态**

**监听**

只能对**每一个checkBox**经行监听。

- checkbox.**setOnCheckedChangeListener**（new **CompoundButton.OnCheckedChangeListener(){}**）；.

![image-20210622201246807](image/image-20210622201246807.png)

### RadioButton（单选）

**需要用RadioGroup包裹，去实现单选。**

**XML**

![image-20210620141922362](image/image-20210620141922362.png)

**Code**

**监听1：监听RadioGroup：****RadioGroup.OnCheckChangeListener**

![image-20210623000022608](image/image-20210623000022608.png)

**监听2：监听RadioButton：**

![image-20210622235920569](image/image-20210622235920569.png)

### 区别（check和radio）

1. checkBox可以点击切换状态。radioButton不行。
2. checkBox可以当多选。radioButton不行。
3. radio是圆的。checkbox是方的。
4. **单个按钮的监听是一样的**
   1. **checkbox.setOnChekedChangeListener(new CompoundButton.OnCheckedChangeListener(){});**
   2. **radiobutton.setOnChekedChangeListener(new CompoundButton.OnCheckedChangeListener(){});**

### ToggleButton

和**switch**开关差不多。有两种状态。

**上面的文字实现当前按钮的状态。显示textOn或者textOff。**

##### **XML**

- **android:textOn=""**
- **android:textOff=""**
- **android:checked="true/false"**
  - **true显示textOn，false显示textOff。**

![image-20210620145122647](image/image-20210620145122647.png)

##### Code

![image-20210620145445656](image/image-20210620145445656.png)

还有一个方法

- **setChecked(true/false)；**

### 