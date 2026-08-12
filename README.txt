========================================
 生活系统大修（Life System Overhaul）补丁
 基线：eratw-sub-modding develop（e9220932 仿生森林nightly更新）
========================================

【安装方法】
将本压缩包解压后，把 ERB、CSV、plugins 三个文件夹
整个拖入/覆盖到游戏根目录（与 Emuera_skiaV10_x64.exe 同级）即可。
zip 内的目录结构与原版游戏完全一致，覆盖安装安全。

【重要：数据库重建】
若你的游戏目录中已存在 plugins/qol_data.db（旧版本生成），
请先删除该文件再启动游戏——游戏启动时会自动重建数据库，
包含本补丁新增的料理/调合配方数据。

【启用方式】
游戏内：DLC设置 → [69] 生活系统大修 → 主菜单
  [1] 养鸡系统   [2] 种地系统   [3] 酿酒系统   [4] 钓鱼系统
各子系统独立启停，关闭时完全恢复原版逻辑。

【架构说明（对齐上游合并规范）】
· 上游 COMF418/COMF499/YASAI/DLCCHIOSEMENU 均保留原样，
  仅在最外层入口添加「IF 生活系统_XXX → 转入 DLC 实现」的
  开关分支（JUMP 分支结构）；开关关闭时本体行为完全不变。
· 全部增强逻辑位于 ERB/DLC/生活系统大修/：
    0_生活系统_变量.ERH   变量声明（数组扩容：菜园240/鸡舍8）
    生活系统_菜单.ERB     设置主菜单 + 子系统菜单
    生活系统_COM418.ERB   菜园增强（分页/一键播种/育苗作物/天赋）
    生活系统_COM499.ERB   鸡舍增强（孵化器/抚摸/饲料箱/鸭子）
    生活系统_养鸡/种地/酿酒/钓鱼.ERB  各子系统每日事件与功能
· 新增物品按上游规范命名（中文名直写 Item.csv），翻译表仅注册
  显示映射（k==v），无冗余。
· 新增配方遵循上游机制：定义于 RECIPE_DATA.ERB 的 @RECIPE_DATA，
  由导出模式批量注册（不直接调用 QOL_RECIPE_DATA_SET）。
· 新增素质已注册：TALENT 耕种Lv=58、催熟/丰收/沃土/双收=63~66、
  FLAG 耕种BONUS取得状況=712、EXP 耕种経験=139。
· 实绩页：魔法成就保持上游第8页（MAGIC_DLC条件），耕种成就为
  新增第9页（无条件）。

【功能概要】
・养鸡：鸡舍扩建（家具911）、孵化器（912，可孵龙蛋/鸭蛋）、
       自动抚摸机（913）、饲料箱、分档抚摸互动、鸭子与鸭蛋
・种地：育苗设施（家具908）、温室大棚（909）、隙间耕地（910）、
       22种新种子作物（山菜种子/药草种子/菌菇孢子等）、开荒、
       花屋苗解锁（育苗→解锁花屋出售）
・酿酒：橡木酒桶（家具914，酒桶0=原版酒虫，酒桶1~5独立酿酒）、
       咸鸭蛋腌制（需养鸡+酿酒同时开启）、茶叶蛋调合
・钓鱼：钓鱼小游戏（浮漂下沉提竿、拉锯战）

【存档兼容】
本补丁新增变量均为新增 SAVEDATA（框架版本迁移自动处理），
旧存档可继续使用；安装后首次启动如遇异常请重新开始新档测试。

【文件清单】（52 个文件，路径与游戏一致）
修改 41 个：DIM.ERH / TALENT.csv / FLAG.csv / EXP.csv / Item.csv /
  _Rename.csv / EGGFARM.ERH / YASAI.ERB / VERSION_UP.ERB /
  PRINT_TALENTNAME.ERB / TRACHECK_ABLUP.ERB / BONUS2.ERB /
  ITEMDATA.ERB / COMF418 / COMF436 / COMF445 / COMF446 / COMF450 /
  COMF490 / COMF499 / COMF621 / COMF625 / CritterData / DISHDATA /
  EGG_DATA / RECIPE_DATA / SAKE_BREWING_GUIDE / 酒関連 / 酒関連F /
  qol_PHARMACY(.ERH) / qol_db.ERH / qol_item.ERB / DLCEVENT /
  DLCCHIOSEMENU / OPTIONPRINT / HTML_MOUSEOVER / tw_csv_chs.xml /
  tw_taste_chs.xml
新增 11 个：COMF471 育苗 / COMF472 开荒 /
  DLC/生活系统大修/（9 个文件）

========================================
 生活系统大修补丁 v2.0（develop 基线）
========================================
