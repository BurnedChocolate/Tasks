# Ruby's Adventure范例学习

## （一）学习笔记

###  🎞目录索引：

0. 资源商店

1. 五大视图

2. 组件

3. 工具栏

4. 常用快捷键
5. 角色的移动与坐标
6. 输入与输出
7. 场景布置
8. 渲染顺序与层级设置
9. 



### 0.asset store（资源商店）

![【资源商店】](https://github.com/BurnedChocolate/Tasks/blob/5c64649f17a372143fbbc6f825a696c6b468801a/%E9%98%B6%E6%AE%B54%E7%AC%94%E8%AE%B0/pictures/%E8%B5%84%E6%BA%90%E5%95%86%E5%BA%97.png)

路径：`window - asset store`

功能：用于购买模型、插件等资源。下载完毕后选择`import`进行导入。

> 🤔：在软件内加载不出来时，可访问官网：[Unity 资源商店](https://assetstore.unity.com/)

### 1.Unity五大视图 - window/view

✔Unity共有五个视图窗口（面板）。

> 🤔：面板基本上都是可拖拽的。

![【五大视图】](https://github.com/BurnedChocolate/Tasks/blob/5c64649f17a372143fbbc6f825a696c6b468801a/%E9%98%B6%E6%AE%B54%E7%AC%94%E8%AE%B0/pictures/%E4%BA%94%E5%A4%A7%E8%A7%86%E5%9B%BE.jpg)

| 名称                        | 功能                                                         |
| --------------------------- | ------------------------------------------------------------ |
| 工程面板 - project window   | 显示可在项目中使用的**资源库**。将资源导入到项目中时，这些资源将显示在此处。包含图片、声音、脚本、模型等。 |
| 层次面板 - hierarchy window | 显示**当前场景**中的所有**物体**对象，并展示其**父子级关系**，是**场景**中每个游戏对象的分层文本表示形式。场景中的每一项都在层级视图中有一个条目，显示了游戏对象之间相互连接的结构。 |
| 场景视图 - scene view       | 用于直观地导航和编辑场景。是当前加载的场景和层次视图中所有游戏对象的实时预览窗口。 |
| 游戏视图 - game view        | 测试游戏时显示的窗口面板。通过场景摄像机模拟最终渲染的游戏的外观效果。单击Play按钮时，模拟开始。 |
| 检视面板- inspector window  | 用于查看和编辑当前所选游戏对象的所有属性。                   |

名词解释：

- **场景**：游戏由一幕幕的场景组成。场景中有不同的内容物。
- **游戏物体**：场景中的内容物。例如main camera、游戏角色、方块等。
- **父子关系**：（隶属关系），移动、缩放、删除父对象会对子对象产生相同的影响。见下图。

![【父子关系】](https://github.com/BurnedChocolate/Tasks/blob/5c64649f17a372143fbbc6f825a696c6b468801a/%E9%98%B6%E6%AE%B54%E7%AC%94%E8%AE%B0/pictures/%E7%88%B6%E5%AD%90%E5%85%B3%E7%B3%BB.png)

> 🤔：hierarchy [n.] 等级制度 ; inspector [n.] 检察员 。

### 2.组件 - component

✔**定义**：在**游戏对象**中实现某些功能的集合。游戏对象**包含**组件，组件定义了该游戏对象的行为，（万物皆对象）。组件在检视面板 - inspector window中显示。

> 🤔：例如，角色想跑，就需要腿的组件；想要思考，就需要大脑的组件。

看一个示例。

![【组件】](https://github.com/BurnedChocolate/Tasks/blob/5c64649f17a372143fbbc6f825a696c6b468801a/%E9%98%B6%E6%AE%B54%E7%AC%94%E8%AE%B0/pictures/%E7%BB%84%E4%BB%B6.png)

其中，转换/变换 - transform就是一个重要的组件，它的三个属性分别指定当前物体位置（position）、旋转角度（rotation）和缩放（scale）。transform component不可被移除。按住transform组件中的x、y、z字母进行拖动，可对相应属性进行调整。

在2d游戏中，旋转一般是指在z轴上进行旋转。

### 3.工具栏

- 【左】快捷键分别为：`Q W E R T Y`
  - 视野查看工具 - hand tool：拖拽移动当前视野。
  - 移动工具 - move tool：移动物体。
  - 旋转工具 - rotate tool：旋转物体 。
  - 缩放工具 - scale tool：缩放物体。
  - 矩形工具 - rect transform tool：查看、编辑2d物体的rect transform组件，移动、缩放、旋转游戏物体，按下shift键可等比缩放游戏对象。
  - 多功能工具：移动/缩放/旋转物体。
- 【中】播放 - Play、暂停 - Pause、逐帧运行 - Step：可以在game view中进行游戏效果的测试。

### 4.常用快捷键

`ctrl+D`：选中物体后进行克隆。

`Q W E R T Y`：对工具栏最左侧六个工具的调用。

`F`：**聚焦**物体。需要先在层次面板中进行选中。（鼠标双击层次面板中的物体名称也有相同效果）

`ctrl+N`：新建场景。

`ctrl+K+C`：多行注释。

`ctrl+K+U`：取消多行注释。

其他见[Unity 快捷键手册](https://docs.unity.cn/cn/2019.4/Manual/UnityHotkeys.html)。

### 5.角色的移动与坐标

- 2d游戏中，角色的坐标以x，y坐标轴为准。

- 子对象的坐标是**相对于**父对象而言的。（即，是一个相对坐标，子对象以父对象为坐标原点）

- RubyController脚本：
  - 创建c#组件，把组件放到ruby上。
  
  - **start()**函数：游戏开始时，unity只在start中执行一次，且在第一帧更新之前调用。（首先调用，且只调用一次）
  
  - **update()**函数：**每秒调用60次左右**（取决于电脑性能和当前状态），需要连续进行的事件可以写在update函数中。
  
  - ```c#
        // Update is called once per frame
        void Update()
        {
            Vector2 position = transform.position; //position，变量名；Vector2，变量类型，存储两个数字的变量类型，此处即transform中的x、y值；transform，当前脚本挂载的组件， .position 即指明transform的属性
            position.x = position.x + 0.1f; //f，即float类型，在数后写一个f，意思是告诉它这个数是浮点数；int类型不需要写
            transform.position = position; 
        }
    ```
  
  - `.`右边相当于左边东西的属性。
  
  - `transform.position`，ruby的位置。`Vector2 position`申请了一个变量，为它的副本。
  
  - `position.x = position.x + 0.1f;`，对position变量的值进行修改。
  
  - `transform.position = position;`把修改后的数值放回到`transform.position`，ruby的位置中去。
  
  - 代码效果：向右运动0.1个单位，每秒运动60次左右。

- 脚本的挂载：

  - 直接拖拽到inspector中
  - 或在inspector中点击add component

- 报错的查看：

  - window-general-console（快捷键`ctrl+shift+c`）
  - 或单击左下角的红色错误提示

- 调整帧率：

  - 在**Start函数**中：

    ```c#
    void Start()
    {
        Application.targetFramRate = 20;//将默认的每秒调用60次调整为每秒调用20次
    }
    ```

### 6.unity中的输入与输出

- 输入设置：

  edit-project settings-input manager

- 查看debug值：

  window-general-console

- 键盘输入监听：

  ←逐渐从0到-1，→逐渐从0到1

- ```c#
  float horizontal = Input.GetAxis("Horizontal");//调用方法，接收监听玩家类型的值（？）Input：类；GetAxis：方法；("Horizontal")：参数。
  Debug.Log(horizontal);//在debug中查看。Debug：类；Log：方法；(horizontal)：参数。
  float vertical =Input.GetAxis("Vertical");
  Vector2 position = transform.position;       position.x = position.x + 5 * horizontal * Time.deltaTime;// 注意Time.deltaTime
  position.y = position.y + 5 * vertical* Time.deltaTime;
  transform.position = position;
  ```

- 这样就可以用wasd控制ruby上下左右的移动了。

  > 🤔：horizontal [n./adj.] 水平；水平的
  >
  > ​		 感觉是否有必要学习一些c#基础语法……

### 7.场景布置

#### ✔场景 - 其一

- 将场景图片素材拖到场景中进行布置。注意复制（克隆）在unity中是`ctrl+D`。

- `W`快捷键调用移动工具，按住`ctrl`键可进行固定长度单位的移动（每次移动的单位数值固定）。

  该移动数值可在edit-grid and snap settings的move中修改（默认为0.25）

上述方式在场景较大的时候工作量大，下面记录利用**tilemap**实现场景布置的方法。

- 在hierarchy中右键，选择2d object-tilemap，将会生成**Grid和Tilemap**。

- 给tile赋值：

  - 拖拽赋值的方法：
    - 让inspector打开在需要拖入的tile界面中
    - 把tile拖拽进去
  - 打开tile界面，点击sprite右边的按钮，选择想要的图片对tile进行赋值

- 创建tile palette：

  window-2d-tile palette

概念汇总：

- **网格 - grid**：用来将游戏对象均匀的放在单元格中。选中Grid/tilemap的时候scene view中会出现白色的网格。

- **瓦片地图 - tilemape**：网格的子游戏对象，由瓦片 - tiles组成。

- **精灵 - sprite**：纹理（图片）的容器。一张图。

  大型纹理图集可转换为**精灵图集 - sprite sheet**。很多图。

- **瓦片 - tiles**：一种特殊的精灵，相比精灵有更多功能。

- **调色板 - tile palette**：保存瓦片，将它们绘制到网格上。这个窗口可以放在game视图旁边。

- **笔刷 - brush：**将画好的东西绘制到画布上面。使用tilemap时，可在多个笔刷中任意选择画出不同的形状（如线条、方块等）

> 🤔：tiles瓦片，相当于笔上的颜料，用来绘制场景；tile palette调色板，相当于调色板，用来保存颜料；tilemap瓦片地图，相当于画布；brush笔刷，啊就是笔刷而已（？

#### ✔场景 其二

- 像素单位的填充与适应

  在environment对应的瓦片图片中选择最底下的那一栏，查看图片本身的大小（eg：64x64）→的inspector - sprite mode - pixeis per unit中进行调整，将数值改为图片本身大小（64）。

  > pixeis per unit：每一行有多少**像素点**的调整单位

- 点击inspector最下面的**apply**就可以让瓦片无缝衔接了！

![【场景其二】](https://github.com/BurnedChocolate/Tasks/blob/5c64649f17a372143fbbc6f825a696c6b468801a/%E9%98%B6%E6%AE%B54%E7%AC%94%E8%AE%B0/pictures/%E5%9C%BA%E6%99%AF%E5%85%B6%E4%BA%8C.png)

- 把一张图片打包成九种资源

  > 就是把精灵做成精灵图集（？）

  图片本身的inspector - sprite mode，将single改为multiple。

  记得点**apply**。

- 切割图片

  编辑精灵的编辑窗口：图片本身的inspector - sprite mode那一栏中底下的sprite editor按钮。打开的窗口中选择slice - type - grid by cell count，即按照行列进行切割。在column & row中编辑为`3 3`。

  关闭窗口，点**apply**。

  ![【切割图片】](https://github.com/BurnedChocolate/Tasks/blob/5c64649f17a372143fbbc6f825a696c6b468801a/%E9%98%B6%E6%AE%B54%E7%AC%94%E8%AE%B0/pictures/%E5%9B%BE%E7%89%87%E5%88%87%E5%89%B2.png)

- 调色板中的工具栏（只对瓦片起作用）

  - select tool - 选择工具：选择想要使用的瓦片，拖动可进行多项选中。快捷键`X`。

  - move tool - 移动工具：选择并移动**scene**中瓦片的位置。快捷键`M`。

  - paintbrush tool - 画笔工具：选择瓦片并在场景面板中绘制。快捷键`B`。

  - fill box tool - 方形区域填充工具：选择一个或一片区域大小的瓦片，绘制区域小于选中区域时会部分绘制选中内容的纹理，等大区域时会全部显示，大于区域时会平铺。快捷键`U`。

    > 🤔：看不懂概念就去画来看看咯。

  - picker tool - 取色工具：取样选中瓦片并绘制，快捷键`I`。

  - eraser tool - 擦除工具：就，橡皮擦。快捷键`D`。

  - fill tool - 填充工具：就，油漆桶。大范围绘制选中的瓦片。快捷键`G`。

- 修改调色板中的瓦片

  选择tile palette中的edit，工具栏就可以对调色板起作用了。

#### ✔场景 其三

来绘制场景吧！

- 可以创建多个tilemap（瓦片地图）（也就是画布），可在inspector中勾选它的显示和隐藏。达到隐藏某画布的效果。
- 橡皮擦工具也可以定义大小，只要在tile palette中框选不同的大小即可。

![【场景绘制】](https://github.com/BurnedChocolate/Tasks/blob/5c64649f17a372143fbbc6f825a696c6b468801a/%E9%98%B6%E6%AE%B54%E7%AC%94%E8%AE%B0/pictures/%E5%9C%BA%E6%99%AF%E7%BB%98%E5%88%B6.png)

### 8.渲染顺序与层级设置

- 渲染

  根据渲染深度决定显示的位置（谁在最下层、谁在中间、谁在最上面）

  要让主角ruby显示在最上面！

- 调整渲染顺序——层级

  **层级**：可以在2d游戏中的sprite renderer和地形tilemap renderer组件中的order in layer属性中去设置层级大小。层级越大的越后渲染，即层级高的物体会显示在更上面。

  - 打开3d模式，调整主角z轴位置。（不推荐）
  - 按照上述修改层级大小。推荐地形层级设置为`-10`，因为地形需要最先进行渲染以防被后面添加的物品挡住。









## （二）参考资料

- [Unity 用户手册 (2019.4 LTS) - Unity 手册](https://docs.unity.cn/cn/2019.4/Manual/UnityManual.html)



















