# Yunzai-Bot搭建过程中你可能遇到的一些问题及其解答

## 一.介绍
该项目分享我在搭建Yunzai-Bot的过程中遇到的一些问题，希望可以帮到你！

## 二.补充
>* 格式

    * 望用户遵守以下 提问|回答 格式：
    * <1>问题时间 操作系统
    * <2>问题过程|问题说明
    * <3>问题排查
    * <4>解决方法1
    * <5>解决方法2
    * <6>说明
    * 本项目也会尽量遵守以上规则
>* 括号

    * 该文档内括号的作用为介绍说明或表示该操作的另一种用法

## 三.Windows Powershell类
* #### ①.Windows Powershell被异常调用(多开)

    * <1>问题时间：2023年4月24日 操作系统：Windows Server 2012 R2 (腾讯服务器)
    * <2>问题过程：服务器异常卡顿，打开任务管理器发现Windows Powershell被异常调用(Windows Powershell占用过高)
    * <3>问题排查：关闭云崽进程后异常解除，重新启动云崽再次异常且Windows Powershell进程无法完全关闭(会再次启动)
    * <4>解决方法1：①打开任务管理器(右键任务栏 → 任务管理器)
                   ②找到Windows Powershell进程，右键并且选择 <打开文件位置> 后成功打开该进程目录文件夹
                   ③找到该进程的应用程序，右键选择<获得管理员所有权(右键 → <属性> → <安全> → <高级> → <更改> → <高级> → <立即查找> → <选择单头像的服务器名称 例:Administrator> → <确定> → <确定> → <确定> → 修改所有用户组权限为 <完全控制> → <确定>)
                   ④修改该进程应用程序的名称(不同于之前)后即可解决
    * <5>解决方法2：卸载Windows Powershell(不推荐切过程繁琐)
    * <6>说明：解决方法1 ③过程中括号里的详细步骤请去百度~
