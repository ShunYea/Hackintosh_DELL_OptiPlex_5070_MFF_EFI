# Hackintosh_DELL_OptiPlex_5070_MFF
Dell OptiPlex 5070 Hackintosh OpenCore EFI
- CPU用的是i9-9900T，网卡是很苹果的博通xxx，最早当时用的是12点几版本忘记了，后面小版本一直升级，目前是最新的12.7.6，貌似官方也升级了。
- 修改自某位大佬的版本，也是忘记出处了，因为当时下载了很多，不知道是哪个版本能用的，就一直沿用下来。
- 功能基本是正常的，目前没有发现异常，没有其他外设，没法测试隔空啥的。稳定性也很好，用了大概一年半，没有大的问题。
- 准备要想升级到更高的版本了，虽然舍不得12版本的流程，据说高版本卡得一批。但是微信等啥的4.0版本必须得MacOS 13版本以上了，所以没办法只能跟着升级，所以这里仅仅作为最经典最稳定的12.7.6版本的EFI的存档，万一哪天需要回滚到这个老版本，就可以直接用了。

## 配置 ##
- CPU：i9-9900T
- 网卡：黑苹果博通
- MacOS：12.7.6
- OpenCore 1.0.0

## BIOS设置 ##
这个很重要：
- General - Advanced Boot Options 取消勾选 Enable Legacy Option ROMs
- System Configuration - SATA Operation 选择 AHCI
- Video - Primary Display 选择 Intel HD Graphics
- Secure Boot - Secure Boot Enable 取消勾选 Secure Boot Enable
- Intel Software Guard Extensions - Intel SGX Enable 选择 Disabled
- Virtualization Support - Virtualization 勾选 Enable Intel Virtualization Technology
- Virtualization Support - VT for Direct I/O 取消勾选 Enable VT for Direct I/O
- Power Management - Block Sleep 勾选（非常重要，重置了BIOS后这个没设置，一直造成只要一睡眠就重启……）

使用grub工具进命令行设置：
- 关闭CFG Lock：setup_var 0x5BE 0x0
- 设置64M预分配显存：setup_var 0x8DC 0x2
