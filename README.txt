========================================
 生活系统大修（Life System Overhaul）补丁
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

【功能概要】
・养鸡：鸡舍扩建（家具911）、孵化器（912，可孵龙蛋/鸭蛋）、
       自动抚摸机（913）、饲料箱、分档抚摸互动、鸭子与鸭蛋
・种地：育苗设施（家具908）、温室大棚（909）、隙间耕地（910）、
       新种子作物、开荒指令、花屋苗解锁（育苗→解锁花屋出售）
・酿酒：橡木酒桶（家具914，酒桶0=原版酒虫，酒桶1~5独立酿酒）、
       咸鸭蛋腌制（需养鸡+酿酒同时开启）
・钓鱼：钓鱼小游戏（浮漂下沉提竿、拉锯战）

【存档兼容】
本补丁新增变量均为新增 SAVEDATA（框架版本迁移自动处理），
旧存档可继续使用；安装后首次启动如遇异常请重新开始新档测试。

【文件清单】（44 个文件，路径与游戏一致）
ERB/DIM.ERH、アイテム解説、YASAI、VERSION_UP
ERB/ステータス表示関連/PRINT_TALENTNAME
ERB/ステータス計算関連/TRACHECK_ABLUP
ERB/SHOP関連/BONUS2
ERB/コマンド関連/COMF/外出系/COMF621 釣り、COMF625 家具屋
ERB/コマンド関連/COMF/日常系/COMF413 料理、COMF418 家庭菜園、
    COMF436 読書、COMF445 採集、COMF446 調合、COMF450 酒虫、
    COMF471 育苗、COMF472 开荒、COMF490 アイテム、COMF499 鶏小屋、
    CritterData、DISHDATA、EGGFARM、EGG_DATA、SAKE_BREWING_GUIDE、
    酒関連、酒関連F
ERB/魔改内容/qol/qol_PHARMACY(.ERH)、qol_db.ERH、qol_item
ERB/DLC/DLCEVENT、DLCCHIOSEMENU、OPTIONPRINT
ERB/DLC/生活系统大修/（生活系统大修.ERH、0_生活系统_变量.ERH、
    生活系统_养鸡/种地/酿酒/钓鱼.ERB）
ERB/fromEN/HTML_TALENTS/HTML_MOUSEOVER
CSV/Item.csv、CSV/_Rename.csv
plugins/tw_csv_chs.xml、plugins/tw_taste_chs.xml

========================================
 生活系统大修补丁 v1.0
========================================
