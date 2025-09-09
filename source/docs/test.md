# LeRobot SO-101机械臂使用文档

## 1.环境配置

### 1.1安装Anaconda

①**下载Anaconda包**

[Advance AI with Open Source | Anaconda](https://www.anaconda.com/)

​	点击链接，跳转到Anaconda官网，点击“**Free Download**”进行下载。

![74a4a22c-b38c-4422-8d60-ac111c5cdc9e](C:\Users\Admin\Desktop\强化学习机械臂\image\74a4a22c-b38c-4422-8d60-ac111c5cdc9e.png)

---

​	**不过官网是外网，这里推荐国内清华大学的镜像源，对于国内的网络友好，下载速度更快！**

---

[Index of /anaconda/archive/ | 清华大学开源软件镜像站 | Tsinghua Open Source Mirror](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)

​	点击上面链接进行下载，这里选择的是Anaconda3-5.3.1。

![fec42d44-7221-4f42-9919-da3ec613e041](C:\Users\Admin\Desktop\强化学习机械臂\image\fec42d44-7221-4f42-9919-da3ec613e041.png)

②**安装Anaconda**

​	找到你所下载的安装包，点击点击安装，按照步骤进行安装。

![3e180897-6df2-4129-a21a-45796373facc](C:\Users\Admin\Desktop\强化学习机械臂\image\3e180897-6df2-4129-a21a-45796373facc.png)

![5c34cac4-003f-415c-81e1-20c87e1cb41c](C:\Users\Admin\Desktop\强化学习机械臂\image\5c34cac4-003f-415c-81e1-20c87e1cb41c.png)

![b2b5f605-bfb1-45c4-a1cb-f1893f083dd8](C:\Users\Admin\Desktop\强化学习机械臂\image\b2b5f605-bfb1-45c4-a1cb-f1893f083dd8.png)

![7c408ce4-50d7-4de5-b549-1c58c71d85aa](C:\Users\Admin\Desktop\强化学习机械臂\image\7c408ce4-50d7-4de5-b549-1c58c71d85aa.png)

![ba026564-67e5-4401-ba6d-193437d1e8be](C:\Users\Admin\Desktop\强化学习机械臂\image\ba026564-67e5-4401-ba6d-193437d1e8be.png)

![3eb7b8eb-50e0-4ce6-b86d-c003bb55e808](C:\Users\Admin\Desktop\强化学习机械臂\image\3eb7b8eb-50e0-4ce6-b86d-c003bb55e808.png)

![674eaf5c-5df7-4128-99ce-d609627efbfe](C:\Users\Admin\Desktop\强化学习机械臂\image\674eaf5c-5df7-4128-99ce-d609627efbfe.png)

![3b462868-caf8-4294-9624-71e8f6cef12e](C:\Users\Admin\Desktop\强化学习机械臂\image\3b462868-caf8-4294-9624-71e8f6cef12e.png)

![082ed775-5eb0-4e12-bfd3-b50334c8bbce](C:\Users\Admin\Desktop\强化学习机械臂\image\082ed775-5eb0-4e12-bfd3-b50334c8bbce.png)

③换源

[anaconda | 镜像站使用帮助 | 清华大学开源软件镜像站 | Tsinghua Open Source Mirror](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/)

​	点击链接，进入Anaconda软件仓库，找到下图所框选的第三方源。

![image-20250908181402792](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908181402792.png)

```json
channels:
  - defaults
show_channel_urls: true
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```

​	“**win+R**”打开控制面板，输入“**cmd**”，打开终端。

![ab17d422-3202-40fa-a108-2e0733eb42d1](C:\Users\Admin\Desktop\强化学习机械臂\image\ab17d422-3202-40fa-a108-2e0733eb42d1.png)

​	终端输入指令，生成“**.condarc**”。

```bash
conda config --set show_channel_urls yes
```

![image-20250908183207242](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908183207242.png)

​	“**.condarc**”文件一般放在用户文件下，例如“**C:\Users\Admin**”，打开“**.condarc**”，将内容进行替换，如下所示。

![image-20250908183354635](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908183354635.png)

```bash
conda clean -i
```

![image-20250908183724677](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908183724677.png)

### 1.2配置虚拟环境

①打开终端

​	“win+R”打开控制面板，输入“cmd”，打开终端。

![ab17d422-3202-40fa-a108-2e0733eb42d1](C:\Users\Admin\Desktop\强化学习机械臂\image\ab17d422-3202-40fa-a108-2e0733eb42d1.png)

②创建虚拟环境

​	输入指令，按下回车，创建虚拟环境。

``````bash
conda create -n lerobot python=3.10
``````

​	出现下图标志，按y继续。

![67d48845-77a4-41f8-a28f-cfb15bb6685b](C:\Users\Admin\Desktop\强化学习机械臂\image\67d48845-77a4-41f8-a28f-cfb15bb6685b.png)

​	创建完成之后，输入指令，即可查到所创建的虚拟环境。

```bash
conda env list
```

![image-20250908184905052](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908184905052.png)

③进入虚拟环境

```bash
conda activate lerobot
```

![image-20250908185021535](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908185021535.png)

④下载代码库

​	下载lerobot工程包，将工程文件，解压到桌面。

![image-20250908185904649](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908185904649.png)

⑤安装依赖包

​	进入到lerobot目录，安装lerobot的依赖包并且指定添加飞特舵机相关的驱动。

```bash
cd Desktop\lerobot
pip install -e ".[feetech]"

```

![image-20250908195013617](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908195013617.png)

⑤安装ffmpeg（建议7.1.1，支持 libsvtav1编码）

```bash
conda install -c conda-forge ffmpeg=7.1.1
```

![image-20250908195256347](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908195256347.png)
## 2.机械臂控制

### 2.1查找端口号

​	输入指令，机械臂的端口号。

```bash
lerobot-find-port
```

![image-20250908200844252](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908200844252.png)

​	上图红色框框选中的即为两个机械臂的端口，再拔掉一个机械臂的接口，再进行查找端口号，就可以知道两个机械臂的端口分别是什么。

---

**本篇文档使用的主机械臂（领导者）和从机械臂（跟随者）的端口号分别为COM22和COM24。**

---

### 2.2设置机械臂ID

#### 2.2.1从机械臂（跟随者）

​	输入指令，进行ID设置。

```bash
lerobot-setup-motors --robot.type=so101_follower --robot.port=COM24
```

![image-20250908202037486](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908202037486.png)

​	该型号的机械臂为六轴机械臂，由六个磁编码舵机控制，从上往下的每个舵机的命名分别为：`gripper`、`wrist_flex`、`wrist_flex`、`elbow_flex`、`shoulder_lift`和`shoulder_pan`，对应着6-1。

---

> [!CAUTION]
>
> 在设置舵机ID时，只能有一个舵机连接主控板。

---

![image-20250908202731723](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908202731723.png)

#### 2.2.2主机械臂（领导者）

​	输入指令，进行ID设置。

```bash
lerobot-setup-motors --teleop.type=so101_leader --teleop.port=COM22
```

​	步骤同[从机械臂](2.2.1从机械臂（跟随者）)。

### 2.3校准

#### 2.3.1从机械臂（跟随者）

​	输入指令，进行校准。

```bash
lerobot-calibrate --robot.type=so101_follower --robot.port=COM24 --robot.id=my_awesome_follower_arm
```

![image-20250908204427057](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908204427057.png)

​	如果没有校准过，按下`Enter`即可进入校准，校准过需要重新校准的，需要按下`c`，再按`Enter`，才能进行校准。

![image-20250908204914675](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908204914675.png)

校准步骤：

​	1)机械臂中间位置：

![image-20250908205419857](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908205419857.png)

​	2)机械臂零位：

![image-20250908205710155](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908205710155.png)

​	3)机械臂旋转位：

![image-20250908205741893](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908205741893.png)

​	4)机械臂就绪等待位：

![image-20250908205824621](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250908205824621.png)

#### 2.3.2主机械臂（领导者）

​	输入指令，进行校准。

```bash
lerobot-calibrate --teleop.type=so101_leader --teleop.port=COM22 --teleop.id=my_awesome_leader_arm
```

​	步骤同[从机械臂](2.3.1从机械臂（跟随者）)。

### 2.2遥操作不带视觉

​	输入指令，进行机械臂控制。

```bash
python -m lerobot.teleoperate --robot.type=so101_follower --robot.port=COM24 --robot.id=my_awesome_follower_arm --teleop.type=so101_leader --teleop.port=COM22 --teleop.id=my_awesome_leader_arm
```

![image-20250909095701478](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250909095701478.png)

​	当出现下图提示时，按下“Eeter”继续。

![image-20250909095826671](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250909095826671.png)

​	出现下图界面，即可通过主机械臂遥控从机械臂。

![image-20250909095938989](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250909095938989.png)

​	“Ctal+c”即可终止终止程序。

### 2.3遥操作可视化

​	将两个摄像头的USB插到电脑上。

---

> [!注意]
>
> 如果你有使用拓展坞，需要注意，两个摄像头的USB不能都接在拓展坞上。

---

​	运行指令，查找摄像头ID。

```bash
lerobot-find-cameras opencv
```

![image-20250909110833531](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250909110833531.png)

​	运行结束，会将捕获的图片保存到`**outputs\captured_images**`。

![image-20250909110936026](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250909110936026.png)

![image-20250909111335585](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250909111335585.png)

​	可以通过文件名来区分摄像头的`ID`，`opencv_0`对应着`ID`：0，`opencv_1`对应着`ID`：1。

​	运行指令，进行遥操作可视化。

```bash
python -m lerobot.teleoperate --robot.type=so101_follower --robot.port=COM24 --robot.id=my_awesome_follower_arm --robot.cameras="{ fixed: {type: opencv, index_or_path: 1, width: 640, height: 480, fps: 30}, handeye: {type: opencv, index_or_path: 0, width: 640, height: 480, fps: 30}}" --teleop.type=so101_leader --teleop.port=COM22 --teleop.id=my_awesome_leader_arm --display_data=true
```

---

> [!NOTE]
>
> **robot.cameras**为固定环境摄像头，**handeye**为夹爪相机。

---

出现下面提示词，按“Enter”继续。

![image-20250909114113287](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250909114113287.png)

![image-20250909114314679](C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20250909114314679.png)

​	通过主机械臂控制从机械臂的同时会回传摄像头捕捉到的画面。若想关闭程序，在终端中“Ctal+c”即可关闭。

## 3.数据采集

```bash
python -m lerobot.record --robot.type=so101_follower --robot.port=COM24 --robot.id=my_awesome_follower_arm --robot.cameras="{ handeye: {type: opencv, index_or_path: 1, width: 640, height: 480, fps: 30}, front: {type:opencv, index_or_path: 0, width: 640, height: 480, fps: 30}}" --teleop.type=so101_leader --teleop.port=COM22 --teleop.id=my_awesome_leader_arm --display_data=true --dataset.repo_id=${HF_USER}/demo --dataset.num_episodes=20 --dataset.single_task="Grab the screwdriver"
```



​	







