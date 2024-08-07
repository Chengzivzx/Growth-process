# Yunzai-Bot搭建过程中你可能遇到的一些问题及其解答
## 不定时更新 如果你也有问题 `讨论|提问` 可以在 ` Issues ` 中进行！！！

# 一.介绍
该项目分享我在搭建Yunzai-Bot的过程中遇到的一些问题，希望可以帮到你！

# 二.补充
* #### 格式

    >望用户遵守以下 `提问|回答` 格式：
    * <1>问题时间 操作系统
    * <2>问题过程|问题说明
    * <3>问题排查
    * <4>解决方法1
    * <5>解决方法2
    * <6>说明
    * `本项目也会尽量遵守以上规则`
* #### 括号

    * `该文档内括号的作用为介绍说明或表示该操作的另一种用法`

# 三.Windows Powershell类
### ①Windows Powershell被异常调用(多开)
<details>
<summary>Windows Server 2019 展开/收起</summary>

- `<1>问题时间：`2024年6月16日 操作系统：`Windows Server 2019 (京东云2c4c5m)`
- `<2>问题过程：`服务器异常卡顿，打开任务管理器发现Windows Powershell被异常调用(`Windows Powershell占用过高`)
- `<3>问题排查：`关闭Qsign进程后异常解除，重新启动Qsign再次异常且Windows Powershell进程无法完全关闭(会再次启动)
- `<5>解决方法1：`卸载Windows Powershell(不推荐并且过程繁琐)或者更改Windows Powershell名称
- 相关文档请查看 ☞ [Windows10进程powershell.exe占用CPU过高解决办法](https://blog.csdn.net/dayuang2009/article/details/102454607)
</details>

<details>
<summary>Windows Server 2012 R2 展开/收起</summary>

- `<1>问题时间：`2023年4月24日 操作系统：`Windows Server 2012 R2 (腾讯云2c2g5m)`
- `<2>问题过程：`服务器异常卡顿，打开任务管理器发现Windows Powershell被异常调用(`Windows Powershell占用过高`)
- `<3>问题排查：`关闭云崽进程后异常解除，重新启动云崽再次异常且Windows Powershell进程无法完全关闭(会再次启动)
- `<4>解决方法1：`更新 [椰奶插件 (yenai-plugin)](https://gitee.com/link?target=https%3A%2F%2Fwww.yenai.ren) 并将`config/default_config`文件夹中`whole.yaml`的`statusPowerShellStartstatusPowerShellStart`项改为`true`
- `<5>解决方法2：`卸载Windows Powershell(不推荐并且过程繁琐)或者更改Windows Powershell名称
- 相关文档请查看 ☞ [Windows10进程powershell.exe占用CPU过高解决办法](https://blog.csdn.net/dayuang2009/article/details/102454607)
</details>

<br><br>
# 四.消息类
### ①群聊伪风控
<details>
<summary>展开/收起</summary>

- `<1>问题时间：`2023年6月13日 操作系统：`Windows Server 2012 R2` (腾讯云2c2g5m)
- `<2>问题过程：`群聊无法发送信息 私聊却可以（与风控类似-不同点见下方`问题排查`）
    >后台截图：![输入图片说明]($8C5R6%60_O%2593P8%25%5BGKI~021.jpg)
- `<3>问题排查：
    >`![输入图片说明](N0DF9BDP%5B%7B%60LHU%60C@N3R384.jpg)
    >>`后台报错风控但是手动上号却可以发消息且别人可以接受消息`
- `<4>解决方法1：`![输入图片说明](2%5D5~GX6$%7BN%5B$%7DE%5B5MPC9Y%5D4.jpg)
    >补充:机器人需要装有`浏览器截图预览插件` 如上图弹出图片即视为成功
    >>`私聊发送链接:https://accounts.qq.com/#/`
    >>>成功后截图:![输入图片说明](%258YMC7GZ~WO0WXY7%7DF%5B0Y3Y.jpg)
</details>

<br><br>

### ②风控-错误码:45
<details>
<summary>新版本风控 展开/收起</summary>

- ##### `<1>问题时间：`2023年6月13日持续至今
>操作系统：`Windows Server 版本不限` 
- ##### `<2>问题过程：`群聊无法发送信息 私聊也无法发送消息
    >后台截图可能出现签名api错误等提示
- ##### `<3>问题排查：`手机上号后发现不是帐号本身的问题(指账号安全异常或者已被冻结)
- ##### `<4>解决方法1：` 下载安装Qsign以辅助icqq类Bot进行消息发送等功能
- ### 访问以下仓库 并且下载安装对应文件：
- ***Windows首选：***
```
https://github.com/CikeyQi/unidbg-fetch-qsign-gui/releases
```
>Windows Server 2019及以上`Qsign`推荐版本`1.1.3` `Java`推荐版本`Java8 144`
>>Windows Server 2012及以下`Qsign`推荐版本`1.0.6` `Java`推荐版本`Java8 401`
- ***Linux首选***
```
https://github.com/CikeyQi/unidbg-fetch-qsign-shell
```
- 安装完成后开始部署Qsign，端口等相关配置好后即可使用
>打开（Miao-Yunzai/Yunzai-Bot）\config\config\bot.yaml 在最底下添加 其中`8080`是配置好的端口号，根据需求更改，默认8080
```
sign_api_addr: http://127.0.0.1:8080/sign
```
>>Qsign协议版本推荐8.9.78


</details>
<details>
<summary>旧版本风控 展开/收起</summary>

- `<1>问题时间：`2023年6月13日 操作系统：`Windows Server 2012 R2` (腾讯云2c2g5m)
- `<2>问题过程：`群聊无法发送信息 私聊也无法发送消息（与风控类似）
    >后台截图可能出现签名api错误等提示
- `<3>问题排查：`手机上号后发现不是帐号本身的问题
- `<4>解决方法1：` **仅限Windows** 
>首先下载一键包：☞[签名api一键包](https://gitee.com/touchscale/Qsign)
>>1.安装jdk([一键包里自带jdk安装包](https://www.oracle.com/downloads/))并配置环境变量([配置教程](https://blog.csdn.net/Marvin_996_ICU/article/details/106240065))
>>>2.升级icqq到0.4.7（指令：pnpm install icqq@0.4.7 -w）
>>>>3.替换（Miao-Yunzai/Yunzai-Bot）\node_modules\icqq\lib\core\devices.js
>>>>>4.打开unidbg-fetch-qsign的 一键startAPI.bat
>>>>>>5.打开（Miao-Yunzai/Yunzai-Bot）\config\config\bot.yaml 在最底下添加
```
sign_api_addr: http://127.0.0.1:80/sign
```
>>>>>>>6.打开（Miao-Yunzai/Yunzai-Bot）\config\config\qq.yaml 更改为协议1或2（ 1:安卓手机、 2:aPad）
- `<5>解决方法2：`使用寒暄的脚本
```
bash <(curl -sL https://gitee.com/haanxuan/version/raw/master/version.sh)
```
</details>

<br><br>

# 五.依赖类

### ①频繁掉依赖
<details>
<summary>展开/收起</summary>

- `<1>问题时间：`2023年7月29日 操作系统：`Windows Server 2012 R2` (腾讯云2c2g5m)
- `<2>问题过程：`启动提示缺失依赖,按照指令安装依赖缺报错,见下图
    >![输入图片说明](%E5%9B%BE%E7%89%87/QQ%E5%9B%BE%E7%89%8720230730010204.jpg)
    >>![输入图片说明](%E5%9B%BE%E7%89%87/QQ%E5%9B%BE%E7%89%8720230730010226.jpg)
- `<3>解决方法：`更新puppeteer.依次执行下列命令(根目录)
```
pnpm uninstall puppeteer
```
```
pnpm install puppeteer@19.8.3 -w
```
```
node ./node_modules/puppeteer/install.js
```
>执行完命令后重新安装依赖发现报错消失
</details>

<br><br>

# 六.[py-plugin](https://gitee.com/realhuhu/py-plugin)插件类

### ①发送指令无反应
<details>
<summary>展开/收起</summary>

## 此解决方法仅限于原版Yunzai
- `<1>问题时间：`2023年7月30日 操作系统：`Windows Server 2012 R2` (腾讯云2c2g5m)
- `<2>问题过程：`按照py-plugin插件教程搭建后,发送任何指令都没有反应,py服务器也已经成功启动
- `<3>解决方法：`更新至miao-Yunzai
>这里提供☞[便捷工具下载地址](https://yshs.lanzouy.com/i756z13upb1c)
>>下载完成后打开,选择<2>-<云崽管理>,再选择<8>-<从官方云崽切换为喵喵云崽>

</details>

<br><br>

# 友情链接
* Yunzai-Bot插件库：☞[Github](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2FyhArcadia%2FYunzai-Bot-plugins-index)|☞[Gitee](https://gitee.com/yhArcadia/Yunzai-Bot-plugins-index)
* Yunzai-Bot（V3）：☞[Github](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2FLe-niao%2FYunzai-Bot)|☞[Gitee](https://gitee.com/Le-niao/Yunzai-Bot)
* Salipet云崽问题合集：☞[wolai文档](https://www.wolai.com/oA43vuW71aBnv7UsEysn4T)|☞[wolai文档](https://www.wolai.com/f1M1idtvVGfeHAjcywfwmw)
* fafa云崽问题合集：☞[wolai文档](https://www.wolai.com/d87HohAH7zgLNG3u9Z2yJz)
* 云崽前置工具下载地址:☞[一闪提供-密码:0000](https://yshs.lanzouy.com/b09zk5u1g)
* QQ频道交流群：☞[点击链接加入QQ频道【原神交流区】](https://pd.qq.com/s/bhj7dpaz)
