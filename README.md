# InfiniGPT
## 天资

## 通用指令：
- #reset : 重置会话,清空与ChatGPT的记录,开始新的聊天!
- #id : 获取企业微信用户id
- #set_openai_api_key api_key: 设置你的OpenAI私有api_key
- #reset_openai_api_key : 重置为默认的api_key

## 目前可用功能与操作指令:
### 1. ChatGPT交互(发语音回语音/发文本回文本)

### 2. 实时新闻榜单获取(已支持:百度,知乎,微博,抖音,cnBeta)
  - 看微博 (推送微博热搜)
  - 看知乎 (推送知乎热搜)
  - 看百度 (推送百度热搜)
  - 看抖音 (推送抖音热搜)
  - 微博要闻榜
  - 微博文娱榜
  - 抖音热门视频
  - 抖音热歌榜
  - 科技新闻 (推送cnBeta的新闻)

### 3. 图片生成/优化、文图交互 (多个提示词','间隔,推荐英文,支持中文)
 - 画提示词 / 画:提示词 / 画open:提示词 (默认,都是使用openjourney模型出图)
 - 画sd:提示词 (使用Stable-Diffusion模型出图)
 - 画二次元:提示词 (使用二次元风格模型anything-v3出图)
 - 画未来:提示词 (使用未来风格模型出图)
 - 画ia:提示词 (使用ai-forever/kandinsky-2模型出图)
 - 画gc:提示词 (使用modelshoot风格GC模型出图)
   - 例: 画可爱妹子 / 画sd:小狗,草地,奔跑 / 画二次元:beach,bikini
 - %修复   (使用腾讯gfpgan模型修复美化人像/旧照片)
 - %去背景 (使用cjwbw/rembg模型去除图片背景)
 - %去模糊 (使用google-research/maxim模型修复模糊照片)
 - %识图   (使用salesforce/blip模型识别图片内容)
 - %ocr    (使用百度OCR模型识别图片文字)

### 4. IT运维类支持
 - surl:http://xxx (生成短域名)
 - check:url:https://xxx (查询url状态/返回头,域名有效期,SSL证书详情)
 - check:tcp:IP Port (查询字段IP端口TCP状态)
 - check:udp:IP Port (查询字段IP端口UDP状态)
 - check:dns:域名 DNS (查询域名的DNS详情,DNS为空默认使用114.114.114.114)
 - check:ping:域名/IP (查询指定地址的ping信息)
 - 基于定制需求获取指定时间/参数的Grafana看板截图(已定制K8S/主机/请求/业务看板)

### 5. 基于prompt(描述词)的角色扮演类 (让GPT扮演各种角色来解决问题)
 - $角色类型 类型名 (查看各角色描述,支持: 所有,常用,思维,写作,文章,文本,编程,生活百科,有趣,语言,辩论,社交,哲学)
 - $角色 角色名 (GPT扮演指定的预设角色来回答你的问题)
 - $设定扮演 描述词 (使用自定义的描述词来让GPT扮演你需要的角色)
 - $停止扮演 (清除设定的角色)

### 6. 企微功能支持
 - 查询xxx时间可用会议室 (查询描述时间空闲会议室信息)
   - 例: 帮我查下后天的会议室情况
 - 预定xxx时间几点-几点xxx会议室 (预定描述时间段的某个会议室)
   - 例: 帮我定周5下午3点到4点普拉多会议室

### 7. 类AutoGPT工具能力扩展(消耗token较多,完善中)
 - $tool 任务描述 (根据任务描述,匹配工具来联网/搜索/运算,尽可能完成任务)
 - $tool reset (重置工具)
 - 已支持工具:python,terminal,天气,网页内容获取.

### 8. 订阅能力(对于以上所有功能:支持周期订阅与一次性任务,自动推送)
 - 查询订阅 (查询所有订阅情况)
 - 查询订阅:1 (根据订阅编号,查询订阅明细)
 - 删除订阅:1
 - 暂停订阅:1
 - 恢复订阅:1
 - 执行订阅:1 (根据订阅编号,立刻执行一次)
 - 订阅:每天下午2点,画二次元:可爱妹子 (根据描述创建订阅)
   - 例: 订阅:每天7点30看知乎 (每天7:30将推送知乎热榜top10)
   - 例: 订阅:每周1-5,11点40,提醒我去热饭 (到了指定时间,GPT会幽默的发消息提醒你)
   - 例: 订阅:每天早上9点,ops:查看昨天的电商K8S各资源top (定时推送Grafana截图)
   - 例: 订阅:每5分钟随机给我讲一个笑话 (让GPT给你讲笑话)
   - 例: 订阅:7月3号上午10点提醒我赎回基金 (一次性提醒任务)

### 9. 基于背景故事的文字冒险
 - $开始冒险 故事背景描述 (开始一个基于背景故事的文字冒险,之后你的所有消息会协助完善这个故事)
   - 例: $开始冒险 你在树林里冒险,指不定会从哪里蹦出来一些奇怪的东西,你握紧手上的手枪,往树林深处走去.
 - $停止冒险 (结束游戏)
