# APFS Driver for macOS High Sierra

`apfs.efi` driver in macOS High Sierra, with the verbose logging suppressed.

Apple introduced Apple File System in macOS High Sierra. In order to boot to macOS from PC,
you need to add the file system driver `apfs.efi` to your boot loader.

The original `apfs.efi` driver extracted from macOS High Sierra has verbose logging and will
display some flash messages before you boot into the loader. This repository provides the modified 
version (and also the original version) so that you don't have to edit the binary yourself.

## 10.13.1

https://www.tonymacx86.com/threads/apfs-high-sierra-10-13-1-no-early-logging.236133/

> In order to quiet the APFS.efi logging, patch the following in Hex Fiend:
>
> Offset 0x2227e -> 0x55 to 0xC3

* [`apfs.efi`](10.13.1/apfs.efi) - logging suppressed
   * MD5: `bbdfcc6e4998401aa942b93992a7282e`
   * SHA1: `324e81abc51620dab303976a8f739c66283ce117`
* [`apfs.efi.original`](10.13.1/apfs.efi.original) - original version
   * MD5: `c4f1aed703d099c4cd84b25cc9ff7b18`
   * SHA1: `2d9a016f60eb49dd12d3f2ca3be7bf3fdd56f134`

## 10.13.2

https://www.tonymacx86.com/threads/how-to-update-current-and-past-apfs-efi-downloads.236103/page-2#post-1643926

> This works in terminal: 
>
> sudo perl -i -pe 's|\x00\x74\x07\xb8\xff\xff|\x00\x90\x90\xb8\xff\xff|sg' /path/to/your/APFS.efi

* [`apfs.efi`](10.13.2/apfs.efi) - logging suppressed
   * MD5: `f9258848ffbbb9dd7f109c8c70666b46`
   * SHA1: `3ea189240c2b74fdd6f9486167c2475afee9b702`
* [`apfs.efi.original`](10.13.2/apfs.efi.original) - original version
   * MD5: `da1e17572159b5db36f637c9d48ac2cb`
   * SHA1: `8b062e1b1538b8cbf906a716ed3a1a6a8e626bf3`
