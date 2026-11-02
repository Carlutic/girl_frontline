# girl_frontline

少女前线（Girls' Frontline / 少女前线2：追放）MMD 模型库，供 `model-viewer` 站点读取
（`https://carlutic.github.io/model-viewer/`，分类 id 以 8 开头）。

## 目录结构

```
girl_frontline.json      # 角色清单（站点启动时读取）
skins.json               # 皮肤清单（同一角色下切换，可为空数组）
chars/<ASCII 名>/         # PMX 模型 + 贴图（保持 PMX 内引用的相对路径，如 Textures/、spa/、normalmap/）
Covers/<ASCII 名>.png    # 512x512 缩略图（站点卡片封面）
```

## 清单格式（girl_frontline.json）

```json
[
    {
        "id": 80001,                    // 首位数字 8 = Girls' Frontline 分类
        "name": "Clukay",               // ASCII 名（URL slug / 查找用）
        "displayName": "可露凯（无瑕侍礼）",  // 界面显示名（可含中文）
        "weaponType": "",
        "element": "GirlsFrontline",
        "gender": "Female",
        "region": "",
        "rarity": 5,
        "directory": "chars/Clukay",
        "image": "Covers/Clukay.png",
        "pmx": "【少女前线2：追放】可露凯（无瑕侍礼)-全配件.pmx"
    }
]
```

## 添加新角色

1. 新建 `chars/<ASCII 名>/`，放入 `.pmx` 与全部贴图/子目录（保持原有相对路径）。
2. 在 `girl_frontline.json` 追加一条，`id` 顺延；`name` ASCII，`displayName` 中文全名。
3. 生成 512x512 缩略图放到 `Covers/<ASCII 名>.png`。
4. 推送 `main` 后等 Pages 发布，站点刷新即可（站点运行时直接读取本仓库）。

## 当前收录

- **34 个角色条目 + 32 个皮肤**
- 每个角色一个卡片；同一角色的原皮/皮肤/休息室等版本放在皮肤列表里，
  站点里用左侧工具栏的衣服按钮切换（`skins.json`）。
- 贴图为控制 GitHub Pages 体积做了下采样（普通贴图最长边 768，脸/眼/发等 1024），
  PMX 文件保持原样。
- 其中 **4 套只有 .blend 的模型**（9口6 提取版：芙洛伦·翠雀媚、刘莳·东方有佳人、
  杜莎妮·明日救星、阿斯缇亚·冬夜星途）由 Blender 4.2 + mmd_tools 转换导出为 PMX，
  骨骼/材质/morph/刚体基本保留，个别贴图源文件缺失（作者原盘路径失效）用同角色贴图或
  占位图补齐。

## 版权与配布规则（重要）

- 模型版权归属 **Sunborn / 散爆网络（少女前线2：追放）**，模型由模之屋作者配布。
- 原配布规则通常为：**不允许二次配布、不允许商用、不允许拆取部件挪用**；本仓库公开托管不构成对模型的再配布授权，公开访问/分发存在被作者或平台投诉的风险。
- 作者规则原文见各 `chars/<角色>/Readme.txt`（如有）。
