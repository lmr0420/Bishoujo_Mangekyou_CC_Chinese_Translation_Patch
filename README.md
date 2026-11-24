# 《Bishoujo Mangekyou CC》Chinese Translation Patch

十五周年纪念版汉化补丁制作中
Simplified Chinese translation patch project for *Bishoujo Mangekyou CC* .

## Tools

- **[VNTextPatch-net8](https://github.com/rafael-vasconcellos/VNTextPatch-net8)**: Extracts script text to `.jsonl` and injects translated lines back into `.s` files via `insertlocal`.
- **[qliepack](https://github.com/Ginsakura/qliepack)** (`qliepackV1`): Repacks modified script directories into `data*.pack` archives.
- **[MinHook](https://github.com/TsudaKageyu/minhook)**: Windows API hooking library used for file redirection (`CreateFileA`/`CreateFileW`) to load patched `data*.pack` archives.

## Workflow

1. Inject `.jsonl` translations into clean `.s` scripts using `VNTextPatch insertlocal`.
2. Repack the script folder into `data8.pack` using `qliepackV1`.
3. Place or redirect `data8.pack` to the patch target path and test in-game.
