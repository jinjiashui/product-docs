# 执行流程

机器人可以通过桌面点击的方式执行流程，也可以通过控制台集中管理执行流程。
控制台集中管理执行流程详见：[如何下发一个流程](../Console/process/runProcess.md?_v=v2020.4)

本地执行的流程来源分为两种：
1. 本地流程文件文件：通过编辑器导出的流程包（后缀为.dgs的流程压缩包）
2. 在线流程库:获取机器人所在资源组的[流程包](..\Console\packages\aboutPackages.md?_v=v2020.4)

**在线流程库**仅供通过控制台激活的机器人使用。

同一机器人同一时间只能执行一个流程，仅在流程执行结束后，方可执行下一个流程。

## 执行流程
左键单击系统托盘，点击执行窗口的“**打开流程库**” 或 双击系统托盘打开“**流程库**”弹窗。

### 执行本地流程
1. 打开流程库
2. 点击导入流程，将编辑器导出的.dgs导入本地流程库。
3. 选择你想要执行的流程，你可以输入流程名点击搜索进行查询。
4. 点击执行，你会看到流程在执行窗口中准备，流程在快速准备后将自动执行。
![robot](https://docimages.blob.core.chinacloudapi.cn/images/Robot/robotlocalprocess.png)

当机器人处于以下情况时，流程库窗口无法打开：
- 当前机器人正在运行流程
- 机器人未获得许可

**注意** 若当前流程需要传入参数，点击执行后会弹窗提示输入参数，例如下图中的流程需要3个参数（参数sheetName和cell为String类型；count为Int类型）：
![robot](https://docimages.blob.core.chinacloudapi.cn/images/Robot/InputArgDialog.png)

### 执行在线流程
1. 打开流程库
2. 点击在线流程库，即可获取流程库所有流程包
3. 你可以通过流程包名搜索找到你想要执行的流程包。
4. 选择要执行的版本，点击执行。
![robot](https://docimages.blob.core.chinacloudapi.cn/images/Robot/robotlocalprocess2.png)


### 终止流程

当流程正在执行时，用户可以随时终止流程运行。
1. 打开流程库，找到正在运行的流程
2. 正在运行的流程，右侧按钮将显示“**终止**”
3. 点击“**终止**”
4. 确认**终止**后，机器人将强制杀死正在运行的流程，无论流程运行到哪一步。“**终止**”操作无法撤回，无法删除。请谨慎操作。
![robot](https://docimages.blob.core.chinacloudapi.cn/images/Robot/robotkillprocess.png)


### 查看运行的流程

右键单击托盘，即可查看运行窗口。

运行窗口将从上到下按照执行时间依次展示：
- 当前机器人最近三条执行完成的流程
- 当前机器人正在执行的流程
- 当前机器人等待执行的流程

若robot service遇到意外情况被重启，则列表将会清空，执行完成的记录丢失。机器人将根据新一轮的执行命令重新加载数据。

![robot](https://docimages.blob.core.chinacloudapi.cn/images/Robot/executorRobot.png)

你可以通过[机器人日志](\log.md?_v=v2020.4)查看更详细的执行日志。