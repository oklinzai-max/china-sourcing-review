# ChinaSourcing 内容加料 · 第三方审查请求

> 生成：2026-11-22 · 站点：https://chinasourcinghq.com · 范围：`src/content/guides/` 21 篇
> **给审查者**：这是一份内容改动的自审材料。请按第 5 节的 6 个问题逐条给出判断，重点核查第 4 节的事实断言是否准确、是否过时、是否存在会误导买家的表述。

---

## 1. 背景与目标

ChinaSourcing 是一个面向国际采购商的英文静态站（Astro 5），内容覆盖广交会、义乌市场、珠三角城市采购、来华实务。

**改动前的问题**（实测，非主观判断）：

1. **两篇文章内部有整段重复**。`yiwu/shopping-tips` 的 4 个章节各出现 3 次，`yiwu/market-guide` 的一节出现 3 次；MD5 完全相同，属逐字复制。共 8 组、13,011 字符。
2. **内容停留在"区域级建议"**。例如广州篇写 "Zhanxi and surrounding garment markets"，但全文没有出现十三行、沙河、桂花岗、中大布匹等真实市场名；`Metro` 一词只出现 1 次。深圳篇提到华强北 10 次，但一栋具体楼宇都没写。广交会 5 篇的展区编号出现 **0 次**。
3. **已核验的数据源未用足**。官方 Chinagoods 的义乌六区逐层目录、广交会官方展区图，此前只用到零头。

**本次目标**：在不改站点框架（不新增页面类型、不改导航）的前提下，删重复、补具体名称/路线/楼层/馆号，并修正事实错误。

---

## 2. 改动总览

| 指标 | 结果 |
|---|---|
| 涉及文章 | 21 篇（27 篇中） |
| 删除重复 | 8 组 / 13,011 字符 |
| 字符总量 | 192,826 → 217,795（+24,969） |
| 净新增有效内容 | 约 38,000 字符 |
| 修正事实错误 | 2 处（见 4.1、4.2） |
| 评估后不动 | 6 篇（见第 6 节） |
| 验证 | build 47 页 / 上线检查通过 / QA 71/71 |

---

## 3. 逐篇改动明细

### 3.1 去重（2 篇）

| 文件 | 删除内容 | 结果 |
|---|---|---|
| `yiwu/shopping-tips.md` | `Judging export experience`、`Customisation`、`When English runs out`、`After you buy` 各重复 2 份；2 组 FAQ 各重复 2 条 | 23,351 → 13,515 |
| `yiwu/market-guide.md` | `A booth is not a factory`（含表格）重复 2 份；同名 FAQ 2 条 | 15,042 → 13,899（含新增 2,193） |

说明：`When English runs out` 与 `After you buy` 的首份与后两份措辞略有差异（`have them read` / `ask them to read`；`ships via` / `ships through`），相似度 0.55 与 0.90。处理方式：保留首份。

### 3.2 第一批（9 篇）

**`china-sourcing/guangzhou.md`（8,019 → 11,286）**
新增 7 个具名市场表（十三行/沙河/白马/站西/桂花岗/中大/一德路），含主营、区域、最近地铁、时段；新增「市场 vs 展会」决策表与「哪个市场干什么」速查；新增 1 天 / 3 天路线。
关键原文：
> | Shisanhang (New China Building) | Fast-fashion womenswear, very high stall density | Renmin South Road, Liwan | Line 6, Cultural Park, Exit A (about 500 m walk) | Early morning to early afternoon |

**`china-sourcing/shenzhen-electronics.md`（8,104 → 11,871）**
新增华强北 6 栋楼分工表（SEG / 华强电子世界 / 明通 / 远望 / 都会 / 新亚洲）、楼层功能、2 小时首刷路线、1 天 / 3 天。
关键原文：
> | **SEG Electronics Market** | The price benchmark; the original | Lower floors are consumer electronics, finished goods and phone parts; middle floors shift to components, development boards, repair parts and tools; upper floors are wholesale with minimum quantities |

**`canton-fair/guide.md`（11,862 → 17,233）**
新增三期 × A–D 区「品类 → 馆号」完整映射表（第 140 届官方布局）、馆号读法、Y 馆与室外 0 层说明、Gate 7/8 入场建议。
关键原文：
> A hall number reads as **building.floor**: `1.1` is building 1 ground floor, `14.4` is building 14 fourth floor.

**`practical-guides/airport-transfers.md`（7,117 → 12,210）**
新增 T1 停用说明、T2（地铁 3 号线）/ T3（城际约 29 分钟到琶洲）分流表、T2↔T3 接驳、机场大巴 3 条线路票价、广交会琶洲专线、出租车费用区间。
关键原文：
> **T1 stopped handling passengers in 2026, and traffic now runs through T2 and T3.**

**`china-sourcing/foshan.md`（8,194 → 10,934）**
新增乐从 7 大卖场定位表（罗浮宫 / 顺联南北 / 皇朝 / 南华东恒 / 红星 / 会展中心）、「乐从看款、龙江看厂、九江看设计」三分法、1 天 / 3 天。

**`china-sourcing/zhongshan-lighting.md`（7,687 → 10,042）**
新增古镇灯博会 8 馆 + 8 个具名分会场、按品类选卖场表、城轨古镇站接驳、1 天 / 3 天。

**`yiwu/market-guide.md`（去重后净 +2,193）**
新增六区逐层（1F 珠宝潮玩 / 2F 护肤婴童 / 3F 家居·无人机 / 4F 智能 IP）；新增 20 行「30 秒定位区/层」速查表。

**`practical-guides/payment-connectivity.md`（8,080 → 9,832）**
新增支付宝/微信绑卡菜单路径、卡被拒的 5 种症状排查表、双卡 + ¥300–500 现金策略。

**`routes/guangzhou-to-yiwu.md`（7,862 → 9,267）**
新增每日约 5 班直达的班次结构表（06:18 8h34m / 11:25 7h22m / 13:19 6h53m / 15:09 5h21m）、票价区间 ¥630–770；修正距离 1,100 → 970 km。

### 3.3 第二批（10 篇）

**`canton-fair/transportation.md`（7,349 → 8,269）**
新增「地铁站 ↔ 展区」对应表：琶洲站 → B/C 区，新港东站 → A/D 区；走错站多走 15–20 分钟。

**`canton-fair/dates-phases.md`（7,475 → 8,848）**
新增三期 × 四区分布表；说明选期后该进哪个区、从哪个站进。

**`routes/canton-fair-yiwu.md`（7,971 → 9,263）**
新增「反直觉班次」：早班 06:18 走 8h34m，下午 15:09 只走 5h21m；按到达时间选车的对照表。

**`canton-fair/buyer-registration.md`（8,262 → 8,493）**
澄清买家证「一届通用、非一期一证」：
> One badge normally covers all three phases of the session you registered for, so attending two phases does not require two registrations. It does not carry over to the next session.

**`china-sourcing/city-product-guide.md`（9,609 → 10,803）**
新增「城市 → 具名市场」表，把"去广州"落到"去十三行/白马/站西"。

**`practical-guides/transportation.md`（7,398 → 8,593）**
新增珠三角主要行程时长表：广深/广中/广佛约 30–40 分钟，广州→义乌 5h21m–8h34m。

**`yiwu/arrival-hotels.md`（7,543 → 7,776）**
修正「订早上出发的火车」建议，与真实班次一致。

**`practical-guides/china-train-booking.md`（7,454 → 8,386）**
新增外国护照注册最容易卡住的 3 步：护照审核需 1 天以上、国际号码可能收不到验证码、姓/名顺序填反会在闸机被拦。

**`practical-guides/trade-terms.md`（8,967 → 10,046）**
补 FCA、DAP、PO、定金/尾款；新增两对易混说明：FCA 适用任何运输方式而 FOB 只适用海运；DAP 不含进口清关与关税而 DDP 含。

**`practical-guides/business-communication.md`（8,153 → 9,277）**
新增 6 句可直接复制的句式（开场询价、确认价格、压 MOQ、要样品、催报价、收尾确认）。

---

## 4. 关键事实断言清单（请重点核查）

| # | 断言 | 我写的值 | 来源 | 我的置信度 |
|---|---|---|---|---|
| 4.1 | 白云机场 T1 已停止客运 | 2026 年停用，现为 T2/T3 | 机场交通指引 + 第三方攻略交叉 | 中高（**最需核查**） |
| 4.2 | 广州→义乌距离 | 约 970 km（原写 1,100） | 12306 / 去哪儿 | 高 |
| 4.3 | 琶洲站 ↔ 展区 | 琶洲站→B/C 区；新港东站→A/D 区 | 广交会交通指引类文章 | 中高 |
| 4.4 | 广交会三期 × 四区馆号 | 见 `canton-fair/guide.md` 三张表 | 官方 `365.cantonfair.org.cn`（第 140 届） | 高（但属第 140 届） |
| 4.5 | 义乌六区逐层 | 1F 珠宝潮玩 / 2F 护肤婴童 / 3F 家居·无人机 / 4F 智能 IP | Chinagoods 官方指南 | 高 |
| 4.6 | 华强北楼宇分工 | 赛格偏元件与批发、华强电子世界偏成品与开发板、明通偏手机壳 | 官方认定 35 个专业市场清单 + 3 份攻略 | 中（楼层会变） |
| 4.7 | 广州市场地铁站 | 十三行→文化公园 A 口；沙河→沙河顶 B 口；白马/站西→广州火车站；桂花岗→三元里；中大→中大；一德路→一德路 | 地图数据 + 攻略 | 中高 |
| 4.8 | 广州→义乌班次 | 每日约 5 班，5h21m–8h34m，¥630–770 | 12306 / 去哪儿 | 高 |
| 4.9 | 广交会琶洲专线 | 约 ¥35，50 分钟，09:00–16:00 | 官方交通指引 | 中（季节性） |
| 4.10 | 白云机场大巴票价 | 1 号线 ¥22 / 2 号线 ¥23 / 3 号线 ¥26 | 第三方交通攻略 | 中 |
| 4.11 | 乐从卖场分工 | 罗浮宫标杆、顺联北区中高端、南区批发、南区比北区便宜 20–40% | 百科 + 南方网 + 罗浮宫官网 | 中高（20–40% 为攻略口径，已写 "reported"） |
| 4.12 | 古镇灯博会 | 2026 秋第 35 届 10/22–25，8 馆 + 8 分会场 | 灯博会官网 + 官方公众号 | 高 |
| 4.13 | 白云机场城际到琶洲 | 约 29 分钟，¥5–23，T3 白云机场东站 B2 | 第三方交通攻略 | 中 |
| 4.14 | 义乌市场营业规律 | 一周约六天，春节休市，摊位各自不同 | 行业常识 + 官方说明 | 中高 |

**统一处理原则**：凡不能从官方页面确认的，文中一律写 "typical / about / roughly"，并写入各篇 `needsVerification`，不写死。

---

## 5. 请审查的 6 个问题

1. **事实准确性**：第 4 节 14 条断言中，哪些有明显错误或已过时？特别是 4.1（T1 停用）、4.3（地铁站与展区对应）、4.4（馆号）。
2. **推荐逻辑**：广州篇「哪个市场干什么」与佛山篇「乐从看款、龙江看厂、九江看设计」的分流，会不会把买家引到错误的地方？
3. **英文质量**：新增英文段落是否有中式英语、表达不自然或过于啰嗦？是否需要按母语采购商习惯改写？
4. **信息完整性**：作为首次来华的采购商，读完这些页面还缺什么关键信息？
5. **合规与风险**：有没有可能被视为承诺、担保或误导的表述（例如 "reported 20–40% cheaper"、认证相关表述）？
6. **结构**：在 8k–17k 字符的篇幅内，新增表格是否过多、是否影响阅读节奏？

---

## 6. 评估后不动的 6 篇

| 页面 | 理由 |
|---|---|
| `yiwu/inside-the-market.md` | 已有 08:30–17:30 小时级时间线 |
| `yiwu/market-itinerary.md` | 已有 1 天 / 2 天 / 3 天方案 |
| `china-sourcing/itinerary.md` | 37 行表格、三条路线 |
| `practical-guides/samples-shipping.md` | 快递 vs 货代、Incoterm、清关结构完整 |
| `practical-guides/trip-documents.md` | 清单类，覆盖完整 |
| `practical-guides/visa-invitation.md` | 政策类，保持"查官方"口径，多写反而危险 |

---

## 7. 技术验证

```
npm run build        → 47 pages built, no errors
npm run check:launch → all passed (1 reminder: GA4 not configured)
node scripts/qa.mjs  → 71/71 checks passed
```

内容验证：全站重复章节 0、重复 FAQ 0；10 个改动页面全部 200，内部链接全部可解析；`lastVerified` 统一为 2026-11-22。
