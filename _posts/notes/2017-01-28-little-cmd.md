---
layout: post
title: 常用命令的整理
category: tools
tags: [linux]
---
{% include JB/setup %}

整理一下常用的命令行，不分平台，tex和vim和tex不在此列



- grep

  - grep取反 grep -v ”ect“”
- Linux 

  - Ctrl + L清屏
  - mv filename(/*) -t directory 也有重命名功能
- du -a du -h
    - du -h --max-depth=1 常用，看一个目录
  - file libvswrtp.so 查询文件信息（查链接库版本一个小经验）ldd
- win

  - wslconfig /l  wslconfig /s ubuntu-18.04
  - win shirl S win10 截图
  - compmgmt.msc 计算机 管理
  - devmgmt.msc 设备管理器
  - win + break 直接调出系统设置
  - eventvwr
  - ie 卸载程序
  - Ctrl + Shift + Esc 任务管理器
  - alt space n
  - alt f4/alt space c
  - snipingtool
  - mspaint
  - ctrl + win +d /F4 虚拟桌面
  - ctrl + win + →
  - win + L 锁屏
  - 磁盘格式转换 convert h: /fs:ntfs
  - windows查看端口占用 `netstat -aon|findstr 25340` 最后一行就是进程id
  - windows 杀死进程，在任务管理找不到的前提下 taskkill /f /pid 13656
- VS

  - Ctrl+k Ctrl+f 对齐(format)
  - Ctrl+k Ctrl+c注释
  - Ctrl+k Ctrl+U 取消注释
  - F5 F9断点 F10 F11
- EverNote 

  - F10标签 F11笔记本列表 F9同步

  - 结合enter esc与方向键使用
- cmder

  - cmder /register all
- gdb
  - thread apply all bt
- tar 
  - 对于xz文件 **tar xvJf  \**\*.tar.xz**
- mount
  - mount /dev/vdb target_dir
- scp 
  - scp local_file root@xx.xx.xx.xx:/root
- 特殊场景
  - 查找体积较大的十个文件
    - du -hsx * | sort -rh | head -10
  - 端口占用 netstat|grep 11221
    - lsof -i :11221抓到对应的进程
- putty
  - alt enter退出全屏 在window behaviour里，勾选最后一个
    - [x] full screen on alt-enter
  - 小键盘设置，在terminal features 勾选 
    - [x] disable application keypad mode
  - 记得保存设置
- telnet 
  - 退出 ctrl  ]



特殊需求

git统计提交行数

```bash
git log --author="name"  --since=2019–01-01 --until=2020-01-01  --pretty=tformat: --numstat | awk '{ add += $1; subs += $2; loc += $1 -  $2 } END { printf "added lines: %s, removed lines: %s, total lines:  %s\n", add, subs, loc }'
```
比较两个文件夹

```bash
 diff -Nrq a b
```



列出目录几层的文件

```bash
tree -L 1
```

拆分 合并文件

```shell
split -b 10M data
cat x* > data & #加个&是因为输出可能把tmux标签污染，干脆就后台运行
```

---

看到这里或许你有建议或者疑问，我的邮箱wanghenshui@qq.com 先谢指教。

### 参考

- mount <https://www.runoob.com/linux/linux-comm-mount.html>
- tar <https://blog.csdn.net/silvervi/article/details/6325698>
- <https://my.oschina.net/huxuanhui/blog/58119>
- scp <https://linuxtools-rst.readthedocs.io/zh_CN/latest/tool/scp.html>
- putty 保存设置<https://blog.csdn.net/tianlesoftware/article/details/5831605>
- tree https://www.jianshu.com/p/f117be185c6f
  - tree在markdown中格式会乱的解决办法，用`````` https://stackoverflow.com/questions/19699059/representing-directory-file-structure-in-markdown-syntax
- diff https://blog.csdn.net/longxj04/article/details/7033744





---

Any advice mailto:wanghenshui@qq.com, thanks! 

Pulling a [issue](https://github.com/wanghenshui/wanghenshui.github.io/issues/new) is fine! I can get noticed from email.

看到这里或许你有建议或者疑问或者指出我的错误，我的邮箱wanghenshui@qq.com 先谢指教。或者到博客上提[issue](https://github.com/wanghenshui/wanghenshui.github.io/issues/new) 我能收到邮件提醒。