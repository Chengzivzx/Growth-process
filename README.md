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
<summary>展开/收起</summary>

- `<1>问题时间：`2023年4月24日 操作系统：`Windows Server 2012 R2 (腾讯服务器)`
- `<2>问题过程：`服务器异常卡顿，打开任务管理器发现Windows Powershell被异常调用(`Windows Powershell占用过高`)
- `<3>问题排查：`关闭云崽进程后异常解除，重新启动云崽再次异常且Windows Powershell进程无法完全关闭(会再次启动)
- `<4>解决方法1：`更新 [椰奶插件 (yenai-plugin)](https://gitee.com/link?target=https%3A%2F%2Fwww.yenai.ren) 并将`config/default_config`文件夹中`whole.yaml`的`statusPowerShellStartstatusPowerShellStart`项改为`true`
- `<5>解决方法2：`卸载Windows Powershell(不推荐切过程繁琐)
</details>

<br><br>
# 四.群聊类
### ①群聊伪风控
<details>
<summary>展开/收起</summary>

- `<1>问题时间：`2023年6月13日 操作系统：`Windows Server 2012 R2` (腾讯服务器)
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

# 补充:所有解决方法适用于同种类别的问题
# 友情链接
* Yunzai-Bot插件库：☞[Github](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2FyhArcadia%2FYunzai-Bot-plugins-index)|☞[Gitee](https://gitee.com/yhArcadia/Yunzai-Bot-plugins-index)
* Yunzai-Bot（V3）：☞[Github](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2FLe-niao%2FYunzai-Bot)|☞[Gitee](https://gitee.com/Le-niao/Yunzai-Bot)
