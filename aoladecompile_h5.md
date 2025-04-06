./js/TestEntrance.js:

```js
// 离线调试开关
TestEntrance.isOn = true;
```

## pmdatalist:

### pmdatamap:

| index | implications                                                 | example                                                      |      |
| ----- | ------------------------------------------------------------ | ------------------------------------------------------------ | ---- |
| 0     | 种族Id                                                       | pmdatalist                                                   |      |
| 1     | 名称                                                         | Name                                                         |      |
| 2     | 身高                                                         | Stature                                                      |      |
| 3     | 体重                                                         | Avoirdupois                                                  |      |
| 4     | HP                                                           | BaseHP（生命种族值）                                         |      |
| 5     | Attack                                                       | BaseAttack(攻击种族值)                                       |      |
| 6     | SAttack                                                      | BaseDefence(防御种族值)                                      |      |
| 7     | SAttack                                                      | BaseSAttack（特攻种族值）                                    |      |
| 8     | SDefence                                                     | BaseSDefence(特防种族值)                                     |      |
| 9     | Speed                                                        | BaseSpeed（速度种族值）                                      |      |
| 10    | 努力hp                                                       | HpIncrement（生命学习力）                                    |      |
| 11    | 努力攻击                                                     | AttackIncrement（攻击学习力）                                |      |
| 12    | 努力防御                                                     | DefenceIncrement（防御学习力）                               |      |
| 13    | 努力特攻                                                     | SAttackIncrement（特攻学习力）                               |      |
| 14    | 努力特防                                                     | SDefenceIncrement（特防学习力）                              |      |
| 15    | 努力速度                                                     | SpeedIncrement（速度学习力）                                 |      |
| 16    | 属性1                                                        | Attribute                                                    |      |
| 17    | 属性2                                                        | Attribute2                                                   |      |
| 18    | 特性(注释：状态免疫)(圣域)                                   | Immunities（免疫）                                           |      |
| 19    | 特性类型                                                     | TXLX                                                         |      |
| 20    | 基础经验                                                     | BaseExp                                                      |      |
| 21    | 100级经验                                                    | ExpType                                                      |      |
| 22    | 雌雄出现概率，暂不使用                                       | SexXY                                                        |      |
| 23    | 个体值几率(注释：天赋类型)                                   | GeniusType（获取精灵类型）                                   |      |
| 24    | 捕获度1                                                      | CatchRate1                                                   |      |
| 25    | 捕获度2                                                      | CatchRate2                                                   |      |
| 26    | 进化（等级：低->高）(0-142#18-143#36-144)(等级-RaceId#)      | EvolutionInfo                                                |      |
| 27    | 超进化目标种族                                               | SuperEvolutonInfo                                            |      |
| 28    | 包含种族技能(种族具备的特别的技能，暂不使用)                 | IncludeRaceSkills                                            |      |
| 29    | 自身技能                                                     | Skills                                                       |      |
| 30    | 机器技能                                                     | LearnSkills（学习技能）                                      |      |
| 31    | AI技能                                                       | AISkills                                                     |      |
| 32    | 加强版异常效果技能可用(N正常Y加强)                           | SkillType（技能类型）                                        |      |
| 33    | 放生代号                                                     | SetFreeType                                                  |      |
| 34    | 推荐技能                                                     | DefaultSkills                                                |      |
| 35    | 推荐学习力                                                   | RecommendatoryLearningAbility                                |      |
| 36    | 推荐性格                                                     | RecommendatoryCharacter                                      |      |
| 37    | 亚比系数，用于计算战斗力                                     | BattleEff（战斗力）                                          |      |
| 38    | 形态系数 用于显示                                            | ViewLevel                                                    |      |
| 39    | 圣域技能ID                                                   | HolySpaceInfo                                                |      |
| 40    | 奥义技能ID                                                   | AoYiSkillId                                                  |      |
| 41    | 超星系系数                                                   | AoYiFactor（AoYi奥义）                                       |      |
| 42    | 领悟奥义技能需要的能量                                       | AoYiRequireEnergy                                            |      |
| 43    | 神迹亚比                                                     | isMiraclePet                                                 |      |
| 44    | 是否完全体亚比                                               | isCompletePM                                                 |      |
| 45    | 是否传奇亚比                                                 | isLegendPM                                                   |      |
| 46    | 获得亚比的魂配置                                             | getPMSoulConfig                                              |      |
| 47    | 亚比的最大技能点数                                           | maxSkillPoint                                                |      |
|       | 初始魂数                                                     | initialSoulNum                                               |      |
|       | 最大魂数                                                     | maxSoulNum                                                   |      |
| 48    | 是否异次元亚比                                               | DegeneratorPM（Degenerator异次元）DegentatorPMType：PO超元，ZHAOHUAN通灵，XIAN绝界，JUE圣体，GUILI双生，SHEN英雄，YULING王者，CHAOWEI超维，SHOU灵魂狩猎，MINGYUN命运主宰 |      |
| 49    | 获得异次元亚比的魂配置                                       | PMDegeneratorSoulConfig                                      |      |
| 50    | 异次元亚比的最大技能点数                                     | maxDegeneratorSkillPoint                                     |      |
| 51    | 推荐铭文                                                     | recommandInscriptions                                        |      |
| 52    | 皮肤                                                         | petSkinArr                                                   |      |
| 53    | 通灵亚比能通灵的式神数组                                     | summonPetArr                                                 |      |
| 54    | 是否被通灵亚比召唤的式神                                     | isShikigamiPet                                               |      |
| 55    | 圣体亚比对应的 觉变身后raceId                                | ChangeRaceId                                                 |      |
| 56    | 双生亚比对应的归离变身后raceId数组                           | guiliRaceIdArr                                               |      |
| 57    |                                                              |                                                              |      |
| 58    | 王者亚比对应的被驭灵的亚比                                   | beYuObjetArr                                                 |      |
| 59    | 英雄亚比对应的 神变身后raceId                                | ShenRaceId                                                   |      |
| 60    | 是否星辉亚比                                                 | isXinghuiPM(XinghuiType:)                                    |      |
| 61    | 获得星辉亚比的灵配置                                         | XinghuiSoulConfig                                            |      |
| 62    | 星辉亚比的最大技能点数                                       | maxXinghuiSkillPoint                                         |      |
| 63    | 推荐星灵                                                     | recommandAstralSpirit                                        |      |
| 64    | 光启永恒契约，星辉王者亚比对应的被共鸣的亚比                 | beGongmingObjetArr                                           |      |
| 65    | 启元技能                                                     | qiyuanSkillId                                                |      |
| 66    | 星辉双重神格亚比对应的其它神格亚比和技能                     | doubleGodObject                                              |      |
| 67    | 星辉亚比的性别                                               | XinghuiPetGende{male 1   female 2}                           |      |
| 68    | 星辉亚比的星级                                               | etXinghuiPetStarLevel（XINGHUI，XINGHUI_S，XINGHUI_SS，XINGHUI_SSS） |      |
| 69    | 星辉赋血权能的对应亚比                                       | FuBloodPowerRaces                                            |      |
| 70    | 星辉某些亚比的额外被动，只有神启，灵魂，万物聚元是如此，其它的不能用 | XinghuiExtraPassiveSkillId                                   |      |
|       | 星辉某些亚比的额外配置                                       | getXinghuiExtraConfig                                        |      |
|       | 某些亚比的额外配置                                           | PmExtraConfig                                                |      |
|       | 星辉亚比初始魂数                                             | initialXinghuiSoulNum                                        |      |
|       | 星辉亚比最大魂数                                             | maxXinghuiSoulNum                                            |      |
|       |                                                              | XinghuiPetType.XINXING = 1; /**  *星辉•王者亚比（改名龙鳞归位和羁绊了）  */ XinghuiPetType.WANGZHE = 2; /**  *星辉•启元亚比  */ XinghuiPetType.QIYUAN = 3; /**  *星辉•双重神格亚比  */ XinghuiPetType.DOUBLEGOD = 4; /**  *星辉•灵兽契约亚比  */ XinghuiPetType.LINGSHOUCONTRACT = 5; /**  *星辉•赋血权能亚比  */ XinghuiPetType.FUBLOODPOWER = 6; /**  *星辉•神启亚比  */ XinghuiPetType.SHENQI = 7; /**  *星辉•灵魂亚比  */ XinghuiPetType.LINGHUN = 8; /**  *星辉•原力膨胀亚比 (改名万物聚元了)  */ XinghuiPetType.FORCEEXPAND = 9; /**  *星辉•万物聚元，替换掉原来的FORCEEXPAND，有新的，请使用这个  */ XinghuiPetType.WAN_WU_JU_YUAN = 9; /**  *星辉•强袭盾护亚比  */ XinghuiPetType.QIANGXI = 10; /** |      |
|       |                                                              | 星辉•超维亚比 */ XinghuiPetType.CHAOWEI = 11; /** 星辉•王者亚比 */ XinghuiPetType.WANGZHE_REAL = 12; /** 星辉•羁绊启元亚比 */ XinghuiPetType.JIBANQIYUAN = 13; /** 星辉•六位一体亚比 */ XinghuiPetType.LIUWEIYITI = 14; /** 深渊回响 */ XinghuiPetType.SHENYUANHUIXIANG = 15; /** 通灵王SP */ XinghuiPetType.XINGHUI_SP = 16; /** 觉醒 */ XinghuiPetType.JUEXING = 17; /** 赋血全能 & sp 双系统亚比. */ XinghuiPetType.FUXUE_AND_SP = 18; /**  * @param 万物聚元 & SP 双系统亚比. @return */ XinghuiPetType.WAN_WU_JU_YUAN_AND_SP = 19; /** 星辉传说，作为双系统合成系统 */ XinghuiPetType.CHUAN_SHUO = 20; /** 星辉幻象-后来改名：正逆二重身 */ XinghuiPetType.HUAN_XIANG = 21; /** 年费独有命星 */ XinghuiPetType.MING_XING = 22; /** 星辉幻象 & 命星 ,年费2021 */ XinghuiPetType.HUAN_XIANG_MING_XING = 23; /** 星辉传说 & 启元 */ XinghuiPetType.CHUAN_SHUO_QI_YUAN = 24; /** SP & 双神格 */ XinghuiPetType.DOUBLEGOD_AND_SP = 25; /** 传说 & 灵魂 */ XinghuiPetType.CHUAN_SHUO_LING_HUN = 26; /** 混沌星辉 */ XinghuiPetType.HUNDUN_XINGHUI = 27; /** 神启启元 */ XinghuiPetType.SHENQI_QIYUAN = 28; /** 正逆+羁绊 */ XinghuiPetType.ZHENGNI_JIBAN = 29; /** sp+超维 */ XinghuiPetType.SP_AND_CHAOWEI = 30; /** 绝对神力系统 */ XinghuiPetType.SHEN_LI = 31; /** 战意系统 */ XinghuiPetType.ZHAN_YI = 32; /** 双神格+绝对神力 */ XinghuiPetType.DOUBLEGOD_AND_SHEN_LI = 33; /** 无冕之王破晓棋局系统 */ XinghuiPetType.CHECKER_BOARD = 34; /** 新盾护 */ XinghuiPetType.SHIELD_PROTECTION = 35; /** 新盾护&传说 */ XinghuiPetType.SHIELD_AND_CHUANSHUO = 36; /** 传说+超维 */ XinghuiPetType.CHAOWEI_AND_CHUANSHUO = 37; /**  *起源神灵亚比系统  */ XinghuiPetType.QI_YUAN_SHEN_LING = 38; /** 起源神灵亚比守护者 */ XinghuiPetType.QI_YUAN_SHEN_LING_GUARD = 39; /**  *通灵亚比系统  */ XinghuiPetType.TONG_LING = 40; /**  *通灵被召唤亚比  */ XinghuiPetType.TONG_LING_SUMMON = 41; /**  *2022年费系统  */ XinghuiPetType.ANNUAL_FEE_22 = 42; /**  *sp+回响  */ XinghuiPetType.SP_SHENYUANHUIXIANG = 43; /**  *sp+归位  */ XinghuiPetType.SP_WANGZHE = 44; /**  *战技  */ XinghuiPetType.ZHAN_JI = 45; /** 神超维亚比 */ XinghuiPetType.SHEN_CHAOWEI = 46; /** 神灵魂亚比 */ XinghuiPetType.SHEN_LINGHUN = 47; /** 法环系统 */ XinghuiPetType.FA_HUAN = 48; /** 神王者系统 */ XinghuiPetType.SHEN_WANGZHE_REAL = 49; /** 轮回誓约系统 */ XinghuiPetType.LUNHUI_SHIYUE = 50;miracleBreakLevel |      |
| 71    | 神迹亚比                                                     |                                                              |      |
| 72    | 光启亚比出的时间                                             |                                                              |      |
| 73    | 推荐神兵                                                     | recommandGodCard                                             |      |
| 74    | 该星辉亚比是否是神兵养成                                     | 1代表是，不填代表星灵培养                                    |      |
| 75    | 先检查是否存在数据                                           | GQPM                                                         |      |
|       | 光启亚比系统                                                 | GQType  1无系统 2：永恒契约 2023年费 3永恒之契4永恒之约5灵凯爆裂6命座 7连锁 8光烬 9 光启超维 10启元   11 神兵系统 12光启战意13爆发复制（比如使者）14天奕系统 15圣魂系统16群星之羽系统17权能系统18：2024年费系统 19异人系统20无尽命途系统21神序系统22缔结师23星之谕24觉醒25英魂&英杰盟约26英魂27英杰盟约28星月同行29星月同行&光烬30五芒星迹31永恒战意，改成永恒源晶32异维升格33神契34神契&英魂35：2025年费系统36衍化之钥37终端共鸣38至高荣耀39秘宝愚者40梦幻缔约41双神格42光烬&双神格 |      |
| 76    | 亚比光能配置                                                 | PMGQSoulConfig（比如6#2#2，光能上限6，上场2光能，每回合获得2光能） |      |
| 77    | 亚比的最大技能点数                                           | maxGQSkillPoint(z)(光启应该默认是10)                         |      |
| 78    | 光启亚比大招                                                 | 默认是消耗5光能(存疑)                                        |      |
| 79    | 光启亚比暴击伤害                                             | 150%                                                         |      |
| 80    | 光启亚比暴击抵抗                                             | 50%                                                          |      |
| 81    | 光启亚比爆伤抵抗                                             | 0%                                                           |      |
| 82    | 推荐魂卡                                                     | recommandH（获取推荐的魂卡ID列表，格式：`[id1, id2, id3, id4, id5]`） |      |
| 83    | 推荐                                                         | areaIdConfigArr（区域魂卡ID配置)                             |      |
| 84    | 推荐                                                         | fetterIdConfigArr（羁绊魂卡ID配置）                          |      |
| 85    | 推荐                                                         | areaRecommendSkillIndexArr（区域推荐技能配置）               |      |
|       |                                                              |                                                              |      |
|       |                                                              |                                                              |      |



