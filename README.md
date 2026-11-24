# 《Bishoujo Mangekyou CC》Chinese Translation Patch

十五周年纪念版汉化补丁制作中
Simplified Chinese translation patch project for *Bishoujo Mangekyou CC* .

目前的文本都在各个Part文件夹里的.s里面，游玩或者阅读的时候觉得有问题可以修改一下

## Tools
## Acknowledgments & Third-Party Tools

- **[GARbro](https://github.com/morkt/GARbro)**: Unpacks game archive files (such as `.pack`) to extract script files for local patching.
- **[VNTextPatch-net8](https://github.com/rafael-vasconcellos/VNTextPatch-net8)**: Extracts script text to `.jsonl` and injects translated lines back into `.s` files via `insertlocal`.
- **[qliepack](https://github.com/Ginsakura/qliepack)** (`qliepackV1`): Repacks modified script directories into `data*.pack` archives.
- **[MinHook](https://github.com/TsudaKageyu/minhook)**: Windows API hooking library used for file redirection (`CreateFileA`/`CreateFileW`) to load patched `data*.pack` archives.

## Workflow

补丁流程：先把2个.dll文件放入游戏根目录，再用[GARbro](https://github.com/morkt/GARbro) 解包游戏文件夹GameData中的含文本的.pack文件，之后用对应Part里的汉化过的.s文件替换，之后用 **[qliepack](https://github.com/Ginsakura/qliepack)** 重新封包后在游戏根目录新建patch文件夹放入即可游玩。
1. Inject `.jsonl` translations into clean `.s` scripts using `VNTextPatch insertlocal`.
2. Repack the script folder into `data8.pack` using `qliepackV1`.
3. Place or redirect `data8.pack` to the patch target path and test in-game.
