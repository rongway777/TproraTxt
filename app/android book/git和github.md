#### VCS

版本控制系统

 git：最著名的一种分布式vcs。

github：使用git的代码托管服务平台。

#### git

Repository 仓库。

Clone 克隆。

Checkout 检出。**

Commit 提交。**

Branch 分支。**

Merge 合并。**

Push 推送。

Pull 拉取。

![2021-07-13 14-22-14屏幕截图](/home/mi/图片/2021-07-13 14-22-14屏幕截图.png)

android studio:下的git

安装git以后。

VCS：选择git。

会在项目文件目录下生成一个.git隐藏文件。也就是仓库文件。

在最下方会出现一个git的操作窗口。

commit一个项目。出现commit change窗口。

下面是绿色则表示新添加的。仓库当中没有。

![image-20210713144730246](/home/mi/.config/Typora/typora-user-images/image-20210713144730246.png)

commit message : 提交信息。

Before commit ：提交前的工作。分析代码。格式化代码。等等。

- 提交的user和email **全局**的话在home下的.gitconfig文件下。也就是说任何项目没有配置user的话，使用全局。
- 也可以配置项目下的gitconfig来覆盖全局。.git下的config文件。

在git窗口的Log（很重要）下。可以看到各个版本。包含代码和message。

可以看到head指针和master分支。

开发的话不要在master分支上开发，新建一个分支完成开发任务。

右键，new一个branch。



对当前项目作了一些更改。点击commit。

绿色就是新添加的内容。

![image-20210713151555164](/home/mi/.config/Typora/typora-user-images/image-20210713151555164.png)

commit之后，在Log窗口可以看到刚刚提交的版本。

![image-20210713152132262](/home/mi/.config/Typora/typora-user-images/image-20210713152132262.png)

标签：master。head。新的分支。（dev）

还可以对已经提交的版本进行追加，而不是创建新的提交(镜像)。属于追加。

![image-20210713155504928](/home/mi/.config/Typora/typora-user-images/image-20210713155504928.png)

追加相当于是对上次提交的修订。不会创建新的提交。

需要点击Amend Commit。必须点击。否则会创建新的提交。

不仅能修改上次提交的内容。还可以对上次的message进行修改。

相当于是对上次的补充修订。

![image-20210713155823075](/home/mi/.config/Typora/typora-user-images/image-20210713155823075.png)

绿条表示对于上次的版本新的修改。点击，有个返回建。可以撤销，显示上次的版本代码。



在实现了Button的监听之后。完成了一部分功能，**合并到master上**。

1.点击master，右键。checkout-->master。（切换到master分支上面，head就会到master上）。

2.VCS --> git -->merge -->选择dev分支。合并。

这个时候三个标签在一个镜像上面。**就像刚开始的图片一样。**head master dev。

![image-20210713162445825](/home/mi/.config/Typora/typora-user-images/image-20210713162445825.png)

点击版本。右键可以添加TAG，表示当前的版本。如v1.0等等。

到此。相当于如下图。

![2021-07-13 14-22-14屏幕截图](/home/mi/图片/2021-07-13 14-22-14屏幕截图.png)

选择切换到dev分支。继续开发。

现在是什么状态不太清楚。





![image-20210714203457381](/home/mi/.config/Typora/typora-user-images/image-20210714203457381.png)

算一个快速合并。

![image-20210714203511281](/home/mi/.config/Typora/typora-user-images/image-20210714203511281.png)



fix合并到master。切换到dev。

将master（合并了fix）合并到dev

#### github

1.单人使用。

和git差不多，没有merge。需要pull request，请求拉取。同意，merge。

2.团队协作

添加team。可以进行文件的提交。

3.开源项目

先fork。然后修改。然后pull request。master。
