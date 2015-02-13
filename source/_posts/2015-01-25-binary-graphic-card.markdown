---
layout: post
title: "在 ubuntu 系統驅動 nvidia 顯卡"
date: 2015-01-25 17:13:32 +0800
comments: true
categories: linux
---

我的筆電有一張獨顯，最近因為看到朋友用 pc 打遊戲很爽，就想來驅動一下這張獨顯。

先查詢電腦中接上的顯卡：

    sudo lshw -C video

<!--more-->

我的電腦告訴我，我有兩張顯卡（第一張是還沒驅動的）：

{% codeblock %}

  *-display UNCLAIMED
       description: 3D controller
       product: GK208M [GeForce GT 740M]
       vendor: NVIDIA Corporation
       [...]
  *-display
       description: VGA compatible controller
       product: 3rd Gen Core processor Graphics Controller
       vendor: Intel Corporation
       [...]
{% endcodeblock %}

# 方法一

安裝驅動程式（不用 beebumble ，改用 nvidia prime）：

    sudo apt-add-repository ppa:xorg-edgers/ppa
    sudo apt-get update
    sudo apt-get install nvidia-319 nvidia-prime 

reboot 以後，進入 soft-center 的 adding driver 選項，選擇想要的顯卡驅動程式。進入 nvidia-setting 將顯卡改為想要的顯卡。

reboot 以後，就用 nvidia 顯卡開機了。

# 方法二

第一種方法的體驗實在太糟糕了，確實用讀顯開機畫面變得比較好，但是效能太差了。於是我決定放棄 nvidia-prime ，改用 bumblebee 。

先移除 nvidia-prime ，然後安裝 bumblebee：

    sudo apt-get purge nvidia-prime
    sudo apt-get install bumblebee bumblebee-nvidia primus linux-headers-generic

reboot 後用 glxspheres64 測試一下，就發現成功用顯卡跑了這支程式了。

# 參考

* [BinaryDriverHowto/Nvidia (ubuntu docs)](https://help.ubuntu.com/community/BinaryDriverHowto/Nvidia#SLI_Application_Profiles_for_ID_Tech_4_Engine_Games_on_Ubuntu_.28and_Linux_in_general.29)
* [Bumblebee Project](https://wiki.ubuntu.com/Bumblebee)
