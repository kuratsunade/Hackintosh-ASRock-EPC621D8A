# Hackintosh - SMBIOS Mac Pro 7,1

## 硬件配置

- 主板：Asrock EPC621D8A 
- BIOS版本：C621D8A2.15E 感谢[远景](bbs.pcbeta.com) @prmvb 提供
- CPU：Intel Xeon W3175x (LGA3647)
- 显卡：华硕 TUF 6800XT x 2
- 内存：镁光DDR4 2400 RECC 16GB x 8
- 硬盘：WD SN550 x 1 + HP EX900 x 3 (其中两张NVMe由PCIE转接) @ PCIE 2
- 网卡：上海狄迅科技BCM94360CD (PCIE x 1 + USB线改装) @  PCIE 3
- 网卡：LR-Link AQC107 @ PCIE 1

## 软件说明

- 感谢@[CrazyHulk](https://github.com/CrazyHulk/)提供以及维护基础EFI
- 操作系统版本：macOS Ventura 13.1
- OpenCore 版本：0.8.7
- SSD Trim：正常。
- SSDT-APCPU以及SSDT-fix - by CrazyHulk
- 有个ssdt需要注意，Mac OS 需要屏蔽 P4500 参见 NOBR1A.aml, 但是你们可能不需要，或者跟我插的不是同一个 PCIE 接口，需要注意。- by CrazyHulk 
- 添加SSDT-DMAR修复DMAR问题驱动AQC107 - 默认不加载

## What's NOT Working
- 四个板载网口 - Intel X722千兆

## OpenCore 的更新

-  推荐[OCAuxiliaryTools](https://github.com/ic005k/OCAuxiliaryTools/), 手动更新太麻烦

## 可能存在的问题

- 偶尔语音通话后会出现杂音。

## BIOS：关于 BIOS 的版本

如果你没有像我一样刷提供的 BIOS，请开启 AppleCpuPmCfgLock 和 AppleXcpmCfgLock， 并且移除 DSDT.aml

## 为何使用 OpenCore

OpenCore的思路是，通过完善ACPI表与UEFI固件来运行macOS：

- 一方面，通过修改ACPI表，可以让硬件的描述与操作方式符合苹果的ACPI规范，从而macOS可以正确的识别和操作硬件。
- 另一方面，通过修改UEFI固件，可以提供一些固件原本没有而macOS需要使用的方法，或者将现有方法改造为macOS可以调用的接口。

OpenCore官方([这里](https://github.com/acidanthera/OpenCorePkg))提供了非常详尽的文档，建议阅读Configuration.pdf即知道每个配置项的存在的意义和作用了，待有时间再补充详细修改的地方。

## Build Photos
机箱/Case
![Case Photo](https://github.com/kuratsunade/Hackintosh-ASRock-EPC621D8A/raw/master/Build%20Photos/PC291533.jpg)
![Case Photo](https://github.com/kuratsunade/Hackintosh-ASRock-EPC621D8A/raw/master/Build%20Photos/P1062920.jpg)
![Case Photo](https://github.com/kuratsunade/Hackintosh-ASRock-EPC621D8A/raw/master/Build%20Photos/P1062949.jpg)

MacOS版本
![MacOS Version](https://github.com/kuratsunade/Hackintosh-ASRock-EPC621D8A/raw/master/Build%20Photos/Screenshot%202023-01-09%20at%2002.12.24.jpg)

系统其他设备
![PCIE Slots](https://github.com/kuratsunade/Hackintosh-ASRock-EPC621D8A/raw/master/Build%20Photos/Screenshot%202023-01-09%20at%2002.14.37.jpg)


## 致谢

- @[CrazyHulk](https://github.com/CrazyHulk/) 提供基础EFI
- @[acidanthera](https://github.com/acidanthera) OpenCore Bootloader
- @[Cheney Veron](https://github.com/cheneyveron) 这个大佬在 BIOS 更新后给了我莫大的灵感和建议
- [Apple](https://www.apple.com)：研发的 macOS 系统
- @[**vit9696**](https://github.com/vit9696)：制作 Lilu & AppleALC
- @[**cfmwan**](http://i.pcbeta.com/space-uid-8977.html)：分享的其EFI，其中有制作的修复睡眠、USB等功能的SSDT，见[这里](http://bbs.pcbeta.com/viewthread-1832693-1-1.html)
- [远景论坛](http://bbs.pcbeta.com) & [InsanelyMac](http://www.insanelymac.com)：提供交流的场所
