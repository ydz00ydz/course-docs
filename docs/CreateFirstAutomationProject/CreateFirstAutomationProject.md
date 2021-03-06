现在，我们已经对编辑器有了基础的了解，那么便开始使用智能录制器录制一下记事本应用程序来熟悉一下。

在此单元中，你将学习到：
- 智能录制器的使用
- 变量的使用

现在，我们将打开一个记事本，在记事本中写入内容，并插入当前时间，最后将写入的内容打印出来，那么如何实现呢？

你可以按照以下操作进行：
## 新建项目并启动录制器
首先，我们需要在编辑器中新建一个项目，并启动录制来录制记事本操作，如何实现呢？
1. 为了便于录制，首先需要打开一个记事本应用程序，便于录制记事本操作
2. 打开编辑器进入主界面，在项目面板中，点击“新建项目”
3. 输入项目名称，例如“记事本的简单操作”。若使用默认项目名称，回车或点击“创建”即可，但是项目名称不可为空
4. 从组件面板拖入一个“打开程序”组件到编辑区域，用于打开记事本
5. 在“打开程序”组件的属性面板中，输入以下内容：
    - **程序路径**："C:\Windows\System32\notepad.exe"</br>要打开的程序的路径

    ![打开程序](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/DesktopAutomation/openApp.PNG)

    >注意：
    >WIindows系统下，记事本的默认路径为"C:\Windows\System32\notepad.exe"</br>
    >在属性面板中输入属性值时，若属性值为字符串，需要将字符串放在英文双引号中。

6. 选中“打开程序”组件，在工具菜单栏下，点击“智能录制”，打开智能录制器
7. 此时，智能录制器已启动

    ![智能录制器](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/FirstProject/recorder.PNG)

## 在记事本中写入内容并插入当前时间
现在，已经打开了智能录制器，让我们开始进行录制。
1. 点击录制器的“智能录制”，开始录制自动化流程

    > 注意：
    > 当出现黄色高亮的矩形区域时，才可以点击目标元素，因为此时代表录制器已经识别出元素，意味着点击后可以获取到相关数据。

2. 找到记事本，点击记事本的主窗口，会弹出一个输入文本的窗口
3. 输入一段自定义文本，然后点击“确定”，将会把该段文本写入到记事本中</br>例如：您好，欢迎使用云扩RPA
4. 选择“编辑”菜单，然后点击“时间/日期”选项，在该段文本后插入当前时间
5. 按下ESC，暂停桌面应用的录制，此时，之前录制的操作已经暂存到录制器的预览界面

    > 注意：
    > 当录制过程出现操作失误等情况导致流程错误，可以通过录制器的预览界面来管理录制好的流程操作。

    ![暂停录制](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/FirstProject/stopRecording.PNG)

## 获取记事本中写入的内容
现在，我们已经在记事本中写入相关内容并插入当前时间，那么如何获取我们写入的内容？
1. 点击智能录制器的“文本”->“获取文本”，该操作将会把目标元素的文本获取到，以让你可以进行后续处理

    ![获取文本](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/FirstProject/getText.PNG)

2. 找到记事本，再次点击记事本的主窗口，此时便获取到记事本主窗口的文本
3. 点击“保存&退出”，将录制的自动化流程保存在编辑区域中

    ![保存并退出](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/FirstProject/saveExit.PNG)

4. 录制好的流程会自动包含在序列中，如下所示：

    ![录制好的流程](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/FirstProject/firstProject-record.PNG)

## 打印记事本中写入的内容
现在，记事本的相关录制操作已完成，我们需要将获取到的文本打印，那么如何打印呢？
1. 在打印之前，我们需要对录制好的流程进行一个简单的处理，使得能够准确输入文本内容
2. 从组件面板拖入一个“发送快捷键”组件到“输入文本”下方
3. 在“发送快捷键”组件的Key中，选择“Enter”

    ![发送快捷键](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/FirstProject/sendHotKey.PNG)

4. 现在开始打印内容。在编辑区域，点击“变量，打开变量列表，创建一个字符串型（String）变量-text，用于存储获取到的文本内容

    ![创建变量Text](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/FirstProject/Variable-Text.PNG)

5. 在“获取文本”组件的属性面板中，输入以下内容：
    - **文本**：text</br>将获取到的文本输出，以进行后续处理
6. 从组件面板拖入一个“确认框”组件到“获取文本”下方
7. 在“确认框”组件的属性面板中，输入以下内容：
    - **标题**："内容"</br>确认框的标题
    - **描述**："记事本的内容："+text</br>将获取到的记事本的内容打印出来


最终，项目如下所示：

![最终项目](https://docimages.blob.core.chinacloudapi.cn/images/EncooLearn/FirstProject/FirstProject.PNG)

## 运行自动化项目
在运行面板中，点击“运行”，将会自动回放我们录制的过程。

## 如何在编辑器中使用示例
对于上述示例，你可以在编辑器的“流程市场”进行下载和使用。
1. 打开编辑器进入主界面，在“市场面板”中，点击“流程市场”
2. 在搜索栏中输入以下名称-记事本的简单操作，搜索到对应流程
3. 选中该流程，点击“下载”，打开“新建项目”窗口
4. 输入自定义项目名称或使用默认名称，点击“创建”，即可下载成功
5. 在项目面板中，找到对应的项目，双击打开就可使用

除此之外，你还可以从云扩市场网站查找到该示例流程，点击[此处](https://marketplace.encoo.com/#/workflow/detail?packageId=%E8%AE%B0%E4%BA%8B%E6%9C%AC%E7%9A%84%E7%AE%80%E5%8D%95%E6%93%8D%E4%BD%9C)前往查看。

