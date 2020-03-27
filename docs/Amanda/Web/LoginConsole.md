# 登录云扩控制台
此节将延续上节课程，在等待手机登录特征元素出现后，执行流程决策的True分支

### 准备工作
1.  打开上节课程的流程文件
2. 已经注册云扩控制台账号，可通过手机号登录

## 定义变量并存入手机号和密码
3. 点击设计面板下的 **变量**标签，并新建以下变量，同时在下图标红处填入你的云扩控制台用户名和密码 （将用户名和密码放于英文状态下的双引号内）

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/v2.png)

## 输入手机号和密码，登录
4. 搜索**序列**组件并拖拽至设计面板，重命名为**3.1 Login_ConsolePanel**，将其和**流程决策**的True分支连接，双击打开
5. 搜索**输入文本**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到**手机号码**处，看到其高亮显示时点击。**文本**属性值写入**phoneNum**
6. 搜索**输入文本**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到**密码**处，看到其高亮显示时点击。**文本**属性值写入**pwd**
7. 搜索**点击**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到**登录**处，看到其高亮显示时点击

## 等待元素出现
此步骤用于检测上步的点击登录后是否成功加载出控制台界面，并输出出现的**控件元素**和**结果**

8. 手动登录到控制台后
9. 搜索**等待元素出现**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到右上角**帮助文档**处，看到其高亮显示时点击

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/help.png)

10. **控件元素**属性值写入**elementOutput**；**结果**属性值写入**waitElementAppearResult2**

## 流程决策：连接与条件分支设置

12. 退出当前**序列**，返回到带有开始节点的**流程图**界面
13. 搜索**流程决策**组件并拖拽至设计面板 
14. 将**3.1 Login_ConsolePanel**序列组件与**流程决策**连接
15. 点击**流程决策**，输入**条件**属性值为**waitElementAppearResult2**
16. 将**流程决策**的右侧**False**分支和**结束流程_写入日志**连接

## True分支，控制台登录成功后的操作
17. 搜索**序列**组件并拖拽至设计面板，重命名为**3.2 .OperationInsideConsole**，将其和**流程决策**的True分支连接，双击打开
18. 搜索**悬停**组件并拖拽至设计面板。**控件元素**写入属性值**elementOutput**

## 获取文本并输入
19. 搜索**获取文本**组件并拖拽至设计面板。点击**指定元素**，将鼠标放到右上角**帮助文档**处，看到下图高亮显示时点击。**文本**写入属性值**text**

![img](https://docimages.blob.core.chinacloudapi.cn/images/Amanda/Tutorial/web/h2.png)

20. 搜索**写入日志**组件并拖拽至设计面板。**日志内容**写入属性值 **"这里有"+text+"，可以点击查看帮助哟。"**

## 运行
17. 点击工具栏的**运行**按钮，结束后查看运行日志即可