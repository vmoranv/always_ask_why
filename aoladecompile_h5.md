./js/TestEntrance.js:

```js
// 离线调试开关
TestEntrance.isOn = true;
```

## pmdatalist:

### pmdatamap:

| index | implications | source     |
| ----- | ------------ | ---------- |
| 0     | 种族Id       | pmdatalist |

|      |                                                              |                                                              |
| ---- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | 名称                                                         | Name                                                         |
| 2    | 身高                                                         | Stature                                                      |
| 3    | 体重                                                         | Avoirdupois                                                  |
| 4    | HP                                                           | BaseHP（生命种族值）                                         |
| 5    | Attack                                                       | BaseAttack(攻击种族值)                                       |
| 6    | SAttack                                                      | BaseDefence(防御种族值)                                      |
| 7    | SAttack                                                      | BaseSAttack（特攻种族值）                                    |
| 8    | SDefence                                                     | BaseSDefence(特防种族值)                                     |
| 9    | Speed                                                        | BaseSpeed（速度种族值）                                      |
| 10   | 努力hp                                                       | HpIncrement（生命学习力）                                    |
| 11   | 努力攻击                                                     | AttackIncrement（攻击学习力）                                |
| 12   | 努力防御                                                     | DefenceIncrement（防御学习力）                               |
| 13   | 努力特攻                                                     | SAttackIncrement（特攻学习力）                               |
| 14   | 努力特防                                                     | SDefenceIncrement（特防学习力）                              |
| 15   | 努力速度                                                     | SpeedIncrement（速度学习力）                                 |
| 16   | 属性1                                                        | Attribute                                                    |
| 17   | 属性2                                                        | Attribute2                                                   |
| 18   | 特性(注释：状态免疫)(圣域)                                   | Immunities（免疫）                                           |
| 19   | 特性类型                                                     | TXLX                                                         |
| 20   | 基础经验                                                     | BaseExp                                                      |
| 21   | 100级经验                                                    | ExpType                                                      |
| 22   | 雌雄出现概率，暂不使用                                       | SexXY                                                        |
| 23   | 个体值几率(注释：天赋类型)                                   | GeniusType（获取精灵类型）                                   |
| 24   | 捕获度1                                                      | CatchRate1                                                   |
| 25   | 捕获度2                                                      | CatchRate2                                                   |
| 26   | 进化（等级：低->高）(0-142#18-143#36-144)(等级-RaceId#)      | EvolutionInfo                                                |
| 27   | 超进化目标种族                                               | SuperEvolutonInfo                                            |
| 28   | 包含种族技能(种族具备的特别的技能，暂不使用)                 | IncludeRaceSkills                                            |
| 29   | 自身技能                                                     | Skills                                                       |
| 30   | 机器技能                                                     | LearnSkills（学习技能）                                      |
| 31   | AI技能                                                       | AISkills                                                     |
| 32   | 加强版异常效果技能可用(N正常Y加强)                           | SkillType（技能类型）                                        |
| 33   | 放生代号                                                     | SetFreeType                                                  |
| 34   | 推荐技能                                                     | DefaultSkills                                                |
| 35   | 推荐学习力                                                   | RecommendatoryLearningAbility                                |
| 36   | 推荐性格                                                     | RecommendatoryCharacter                                      |
| 37   | 亚比系数，用于计算战斗力                                     | BattleEff（战斗力）                                          |
| 38   | 形态系数 用于显示                                            | ViewLevel                                                    |
| 39   | 圣域技能ID                                                   | HolySpaceInfo                                                |
| 40   | 奥义技能ID                                                   | AoYiSkillId                                                  |
| 41   | 超星系系数                                                   | AoYiFactor（AoYi奥义）                                       |
| 42   | 领悟奥义技能需要的能量                                       | AoYiRequireEnergy                                            |
| 43   | 神迹亚比                                                     | isMiraclePet                                                 |
| 44   | 是否完全体亚比                                               | isCompletePM                                                 |
| 45   | 是否传奇亚比                                                 | isLegendPM                                                   |
| 46   | 获得亚比的魂配置                                             | getPMSoulConfig                                              |
| 47   | 亚比的最大技能点数                                           | maxSkillPoint                                                |
|      | 初始魂数                                                     | initialSoulNum                                               |
|      | 最大魂数                                                     | maxSoulNum                                                   |
| 48   | 是否异次元亚比                                               | DegeneratorPM（Degenerator异次元）DegentatorPMType：PO超元，ZHAOHUAN通灵，XIAN绝界，JUE圣体，GUILI双生，SHEN英雄，YULING王者，CHAOWEI超维，SHOU灵魂狩猎，MINGYUN命运主宰 |
| 49   | 获得异次元亚比的魂配置                                       | PMDegeneratorSoulConfig                                      |
| 50   | 异次元亚比的最大技能点数                                     | maxDegeneratorSkillPoint                                     |
| 51   | 推荐铭文                                                     | recommandInscriptions                                        |
| 52   | 皮肤                                                         | petSkinArr                                                   |
| 53   | 通灵亚比能通灵的式神数组                                     | summonPetArr                                                 |
| 54   | 是否被通灵亚比召唤的式神                                     | isShikigamiPet                                               |
| 55   | 圣体亚比对应的 觉变身后raceId                                | ChangeRaceId                                                 |
| 56   | 双生亚比对应的归离变身后raceId数组                           | guiliRaceIdArr                                               |
| 57   |                                                              |                                                              |
| 58   | 王者亚比对应的被驭灵的亚比                                   | beYuObjetArr                                                 |
| 59   | 英雄亚比对应的 神变身后raceId                                | ShenRaceId                                                   |
| 60   | 是否星辉亚比                                                 | isXinghuiPM(XinghuiType:)                                    |
| 61   | 获得星辉亚比的灵配置                                         | XinghuiSoulConfig                                            |
| 62   | 星辉亚比的最大技能点数                                       | maxXinghuiSkillPoint                                         |
| 63   | 推荐星灵                                                     | recommandAstralSpirit                                        |
| 64   | 光启永恒契约，星辉王者亚比对应的被共鸣的亚比                 | beGongmingObjetArr                                           |
| 65   | 启元技能                                                     | qiyuanSkillId                                                |
| 66   | 星辉双重神格亚比对应的其它神格亚比和技能                     | doubleGodObject                                              |
| 67   | 星辉亚比的性别                                               | XinghuiPetGende{male 1   female 2}                           |
| 68   | 星辉亚比的星级                                               | etXinghuiPetStarLevel（XINGHUI，XINGHUI_S，XINGHUI_SS，XINGHUI_SSS） |
| 69   | 星辉赋血权能的对应亚比                                       | FuBloodPowerRaces                                            |
| 70   | 星辉某些亚比的额外被动，只有神启，灵魂，万物聚元是如此，其它的不能用 | XinghuiExtraPassiveSkillId                                   |
|      | 星辉某些亚比的额外配置                                       | getXinghuiExtraConfig                                        |
|      | 某些亚比的额外配置                                           | PmExtraConfig                                                |
|      | 星辉亚比初始魂数                                             | initialXinghuiSoulNum                                        |
|      | 星辉亚比最大魂数                                             | maxXinghuiSoulNum                                            |
| 71   | 神迹亚比                                                     | miracleBreakLevel                                            |
| 72   |                                                              |                                                              |
| 73   | 推荐神兵                                                     | recommandGodCard                                             |
| 74   |                                                              |                                                              |
| 75   |                                                              | isGQPM                                                       |
| 76   |                                                              | PMGQSoulConfig                                               |
| 77   |                                                              |                                                              |
| 78   |                                                              |                                                              |
| 79   |                                                              |                                                              |
| 80   |                                                              |                                                              |
| 81   |                                                              |                                                              |
| 82   | 推荐魂卡                                                     | recommandH                                                   |
| 83   | 推荐                                                         | areaIdConfigArr                                              |
| 84   | 推荐                                                         | fetterIdConfigArr                                            |
| 85   | 推荐                                                         | areaRecommendSkillIndexArr                                   |
| 86   |                                                              |                                                              |
| 87   |                                                              |                                                              |

