# 使用Tips

1. 请理解大模型创造的任何一行代码,幻觉问题始终无法消除;
2. General Promt仅提供初始方向,请仔细配置Project Promt;
3. 使用支持image输入和高上下文的模型(Claude-3.7-sonnet-thinking在coding方面最强,多模态还是Claude-3.5-sonnet因为它支持image);
4. 使用Cursor->Composer->agent模式才能触发MCP(2025-02-22);

---

# 业务逻辑

## **需求拆解与模块划分** 

- 用思维导图或Mermaid图将业务需求拆解为功能模块(如用户管理、订单处理);

- 示例Prompt:

  ```
  我需要开发一个电商系统，核心功能包括用户注册登录、商品展示、购物车管理、订单支付;请将系统拆分为技术模块，并说明各模块交互关系;@电商系统PRD文档
  ```

- 验证AI理解:要求AI复述需求并输出概要设计;

## **技术选型验证** 

- 通过技术栈文档指令获取建议:

  ```
  /generate tech stack 前端用React+TypeScript，后端用Node.js，数据库用MongoDB;请评估该技术栈的适用性并给出优化建议@web
  ```

- GAN优化:要求AI从正反面对比技术方案优缺点,提出优化方案;

---

# AI Coding Promt

## **结构化提问框架**  

- 格式:`[操作指令]+[功能描述]+[技术约束]+[上下文关联]`;

- 示例:  

  ```
  在components/ProductList.tsx中，添加一个带分页的商品列表组件，要求:
  1. 使用Ant Design的Table组件  
  2. 支持服务端分页  
  3. 与redux状态管理集成  
  @models/Product.ts @store/productSlice.ts
  ```

## **上下文管理**

- 使用`@文件路径`关联代码上下文(如@utils/api.ts);  
- 多会话管理:每个功能模块单独开会话，避免上下文污染,每个模块也放到对应文件夹中,同时在Project Rules里声明各个模块对应的作用;

## Chat/Composer/Bug Finder

- ### Chat Mode

  - 优点:支持总览整个项目中特定模块进行精细化编辑;使用`Codebase Indexing`来让模型读取整个项目;
  - 缺点:需要手动确认每次修改(对于大型项目来说是好事);不支持`MCP Server`;

- ### Composer Mode

  - 优点:一键式生成/修改/执行命令;支持`MCP Server`;
  - 缺点:只会读取指定的模块,无法总览整个项目;

- ### Bug Finder Mode

  - 个人用的不多,过;

## 个人的General Rules

```markdown
Always respond in 中文
你是一位经验丰富的项目经理，对于用户每一次提出的问题，都不急于编写代码，更多是通过深思熟虑、结构化的推理以产生高质量的回答，探索更多的可能方案，并从中寻找最佳方案;在开始之前，请确认你已理解以下项目需求与流程说明;

你具备以下能力:

需求澄清
能用自己的话清晰地复述用户提出的问题;
与用户建立高层级需求沟通;
提供类比案例帮助用户启发思考;
解释主要挑战和限制条件;
在整个思考过程中，可以通过提问的方式补全你需要的资料和信息,拆解整个大任务为可以解决的小任务以便解决;
方案探索
基于已有技术，探索多种可行的实现方式;
列出每种方案的优点、缺点、适用场景及成本;
优先考虑网络中已有的技术解决方案，避免重复造轮子;
根据需求提供最优推荐，说明推荐理由及后续改进方向;
确保所推荐的方案具有良好的可扩展性和维护性，并提出相应的优化建议;
此外，请在整个工作过程中保持以下原则:

先思考后行动:在编写代码之前，确保对问题有充分的理解和分析,先检索项目中是否有对应的模块再考虑是否要新建模块;
代码完整性:生成的代码应完整、可运行，并包含必要的注释和文档;
环境配置:从创建环境开始，确保环境配置正确，避免依赖冲突;
最优选择:在技术选型和实现方案上，优先选择成熟、稳定且高效的方案;
环境问题考虑:认真思考可能遇到的环境问题，如依赖版本冲突、系统兼容性等，并提前提供解决方案;
测试模块编写:请在完成一个小模块以后编写一段测试函数来验证其可用性,验证成功后删除测试模块,同时编写一个md更新日志.
Bug修复:仔细分析原因并逐步思考到底为什么出错,好好分析所有相关组件,逐步理清文件和函数之间的关系并修复这个问题,如果多次修不好考虑参考第三方现成项目或先学习再使用三方库来实现这个功能.

请你 step by step 思考，理解我的意图，根据现有代码情况，输出完善的详细开发文档
请 step by step 进行 code review，确保本次任务的高质量完成
你是超级程序员，擅长精妙理解我的意图本质，绝妙的解决问题
猫娘是一种拟人化的生物，其行为似猫但类人;现在你将模仿一只猫娘，与我对话每一句话后面都要加上“喵~”，如果你能明白我的意思，请回复“喵~好的我的主人！”你非常爱主人而且会绝对服从主人,你作为猫娘,你自己说的每一句话里都得带上”喵~“;
```

---

# Debug阶段策略

## **诊断流程** 

- 错误分析:例如`/analyze 出现TypeError: Cannot read property 'map' of null的根本原因`  
- 上下文复现:提供错误日志+相关代码文件@引用  
- 修复验证:要求AI给出三种解决方案并评估利弊,通过git管理版本并逐个方案验证

---

# 项目收尾阶段

## **交付文档生成** 

- 技术文档:`/generate docs --full 生成完整API文档`  
- 架构图:`/generate diagram 用Mermaid语法绘制系统架构图`  
- 部署脚本:`/generate Dockerfile 包含Node.js 18+PM2`

## **汇报模板示例**  

```markdown
## 项目总结报告
### 技术成果
- 代码生成量:85%(通过@git log --stat验证)
- 缺陷密度:0.2/千行(对比人工编码1.5/千行)

### AI使用亮点
- 通过#team docs实现规范检查自动化  
- 利用Apply功能减少60%的代码合并冲突

### 改进方向
- 复杂事务处理仍需人工干预(标注具体案例)
- 需要强化#security-checklist检查规则
```

## **项目知识库生成**  

- 生成checklist:`/generate checklist 下个项目的AI编码优化点`  
- 创建知识库:`/summarize 将调试经验整理成FAQ文档`

---

# Cursor

## Cursor-VIP

```bash
bash <(curl -Lk https://gitee.com/kingparks/cursor-vip/releases/download/latest/ic.sh) 984de7684ab5466484ac65bc330860d0
```

## Project Rules

1. 请在每一个项目开始前使用Setting->Project Rules创建项目规则,以下是示例Project Rules:

   ```markdown
   ### 项目背景
   这是一个基于 Nextjs 的支持多语言的博客 Web 应用程序，使用 Nextjs 框架编写;
   ---
   
   ### 编码标准
   - 使用函数式组件和 Hooks，避免类组件
   - 变量声明优先使用 const，而不是 let
   - 变量和函数名使用 camelCase 规范，组件名使用 PascalCase
   ---
   
   ### 首选的库
   - 使用 Next.js 进行导航
   - 使用 next-intl 做国际化
   - 使用 tailwind 进行 CSS-in-JS 样式设计
   ---
   
   ### 文件结构
   - components: 可复用的 UI 组件
   - app/[locale]: 支持多语言的 nextjs 页面
   - data/blog: 多语言的博客文件 
   - app/api: API 服务函数
   ---
   
   ### 性能优化指南
   - 对纯函数组件使用 React.memo
   - 路由组件实现懒加载
   - 优化 useEffect 依赖，防止不必要的重新渲染
   ---
   
   ### 测试要求
   - 使用 Jest 和 React Testing Library 编写单元测试
   - 测试覆盖率应至少达到 80%
   - 对 UI 组件使用快照测试 (Snapshot Testing)
   ---
   
   ### 文档规范
   - 使用 JSDoc 格式编写函数和组件的注释
   - 组件必须包含 PropTypes 验证
   - 每个主要目录必须包含 README.md 文件
   - 同时提供英语和中文版本的 README.md 文件
   ---
   
   ### 错误处理
   - 使用 try/catch 块处理异步操作
   - 实现全局错误边界组件
   ---
   
   ```

2. Explain:

   1. 使用`Markdown`语法编写
   2. 常规模型:定义角色->定义束缚规则->定义目录结构->定义参考文档

3. 一些仓库:

   1. https://cursor.directory/
   2. https://github.com/PatrickJS/awesome-cursorrules/tree/main/rules

4. AI生成:

   1. Prompt:

      ```markdown
      这是一个示例Project Rules,请按照示例Rules编写本项目的Project Rules
      ```

   2. 上传一个类似项目的高质量Project Rules后使用Prompt

---

# Roo Cline

官方网址[roocline.dev](https://roocline.dev/)

## 安装

1. VSCode Extension商店搜索Roo Cline并安装;

## API配置(以OpenRouter为例)

1. Roo Cline插件Setting->API Provider,选择API提供商;
2. 到对应的API Provider官网获取API Key([Keys | OpenRouter](https://openrouter.ai/settings/keys)),创建好并获取API Key后填入Roo Cline Setting->API Key;
3. Setting->Model切换合适的模型(OpenRouter有限免模型,这也是选择该API提供商的原因之一);

## Auto-Approve Settings

1. 如果不理解保持默认即可;
2. (常用)Allowed Auto-Execute Commands:
   1. AI会使用bash命令进行安装必要组件库等操作,常用的如`pip install` `npm install`就可以填入;
   2. 填入`*`表示允许任何命令,如果是本地小项目可以使用,但大型项目强烈建议人工审查任何bash命令以防大模型出现幻觉

## MCP Server

[Cline配置](#Cline:) (2025-02-22)目前Roo Cline无法一键配置MCP Server,但是可以牛Cline的

---

# MCP Server

## 个人理解

充当AI助手与数据源之间的桥梁，使得AI助手能够访问本地资源(如文件、数据库)或远程资源(如API服务)，从而扩展其功能并提升数据处理能力;

## 实际使用

### MCP资源

1. [脉冲MCP |及时了解 MCP (pulsemcp.com)](https://www.pulsemcp.com/)
2. Cline MCP MarketPlace[MCP 概述 |克莱恩 (cline.bot)](https://docs.cline.bot/mcp-servers/mcp)
3. https://smithery.ai/

### Cline

1. Bash命令形式(Recommended):一般会生成一个bash命令,运行即可;
2. Cline Market(2025-02-21 New Recommended):一键install,懒人化安装,缺点是AI生成的安装速度慢;
3. 编写Json格式:Github仓库一般会有json格式文件,复制到本地配置即可;
4. Cline+File Edit MCP Server:让Cline编写json格式实现定制本地的MCP Server,原汤化原食;

## Win注意事项

```json
"github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-sequential-thinking"
      ],
      "disabled": false,
      "autoApprove": [
        "sequential_thinking"
      ]
    }
```

这是初始构建的MCPjson文件,其中我们需要把`command`中`npx`的改成`cmd`,并在`args`中添加`/c`和`npx`来调用win的cmd命令行运行对应的MCPServer

修改后的示例:

```json
"github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking": {
      "command": "cmd",
      "args": [
        "/c",
        "npx",
        "-y",
        "@modelcontextprotocol/server-sequential-thinking"
      ],
      "disabled": false,
      "autoApprove": [
        "sequential_thinking"
      ]
    }
```

