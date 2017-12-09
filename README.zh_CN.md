# macOS High Sierra 的 APFS 文件系统驱动

[English](README.md)

这里提供修改版的 macOS High Sierra 中的 APFS 驱动，在启动载入时不会输出日志信息。

苹果公司在 macOS High Sierra 中引入了 Apple 文件系统（APFS）。为了从 PC 引导启动 macOS，你需要将 AFPS 的驱动
`apfs.efi` 加入到你的引导系统中。

从 macOS High Sierra 中提取出来的 `apfs.efi` (`/usr/standalone/i386/apfs.efi`) 默认开启了日志，会在系统进入
引导界面之前输出一些信息到屏幕（不知道的还以为系统引导出问题了）。这里提供了修改版的驱动来消除这些日志输出，省去你手动改
二进制文件的麻烦。原版的驱动也保留在对应的文件夹中。

## 10.13.1

https://www.tonymacx86.com/threads/apfs-high-sierra-10-13-1-no-early-logging.236133/

> In order to quiet the APFS.efi logging, patch the following in Hex Fiend:
>
> Offset 0x2227e -> 0x55 to 0xC3

* [`apfs.efi`](10.13.1/apfs.efi) - 消除日志版
   * MD5: `bbdfcc6e4998401aa942b93992a7282e`
   * SHA1: `324e81abc51620dab303976a8f739c66283ce117`
* [`apfs.efi.original`](10.13.1/apfs.efi.original) - 原版（注意改扩展名）
   * MD5: `c4f1aed703d099c4cd84b25cc9ff7b18`
   * SHA1: `2d9a016f60eb49dd12d3f2ca3be7bf3fdd56f134`

## 10.13.2

https://www.tonymacx86.com/threads/how-to-update-current-and-past-apfs-efi-downloads.236103/page-2#post-1643926

> This works in terminal: 
>
> sudo perl -i -pe 's|\x00\x74\x07\xb8\xff\xff|\x00\x90\x90\xb8\xff\xff|sg' /path/to/your/APFS.efi

* [`apfs.efi`](10.13.2/apfs.efi) - 消除日志版
   * MD5: `f9258848ffbbb9dd7f109c8c70666b46`
   * SHA1: `3ea189240c2b74fdd6f9486167c2475afee9b702`
* [`apfs.efi.original`](10.13.2/apfs.efi.original) - 原版（注意改扩展名）
   * MD5: `da1e17572159b5db36f637c9d48ac2cb`
   * SHA1: `8b062e1b1538b8cbf906a716ed3a1a6a8e626bf3`
