# TikTok Creative Center Scraper

[English README](https://github.com/lofe-w/tiktok-creative-center-scraper-public/blob/main/README.md)

All In One! 这是面向 TikTok Creative Center 当前官方可用页面的全能型采集器。你可以稳定获取 Top Ads 列表、广告详情分析、关键帧表现、分位基准、相关推荐广告、热门 Hashtag 和 Hashtag 分析等结构化数据，用于营销洞察、竞品研究和创意分析。

[Start Now (On Apify)](https://apify.com/doliz/tiktok-creative-center-scraper)

## ✨ 核心功能

* **⚡️ 快速高效**：直接调用后端接口，避开缓慢的页面自动化操作，节省时间和平台成本。
* **🎯 All-in-one 官方功能覆盖**：一个 Actor 覆盖 TikTok Creative Center 当前官方 Top Ads 和 Hashtag trends 工作流，包括：
    * [Top Ads Dashboard](https://ads.tiktok.com/business/creativecenter/inspiration/topads/pc/en)
    * [Top Ads Spotlight](https://ads.tiktok.com/business/creativecenter/tiktok-topads-spotlight/pc/en)
    * [Ad Analytics](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Keyframe](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Percentile](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Recommend](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Trending Hashtags](https://ads.tiktok.com/creative/creativeCenter/trends/hashtag)
    * [Hashtag Analytics](https://ads.tiktok.com/creative/creativeCenter/trends/hashtag)
* **🔎 强大的筛选能力**：提供丰富的输入参数，尽量对齐 Creative Center 网站本身的筛选能力。
* **📦 结构化 JSON 输出**：返回适合看板、数据清洗、竞品监控和广告研究流程使用的机器可读数据。
* **🧭 与官方当前范围对齐**：TikTok 已经重构并收缩部分 Creative Center 页面，本 Actor 跟随当前官方可用范围进行调整。

## 📝 Creative Center 更新与迁移说明

TikTok 已经重构并调整了 Creative Center 的部分页面。本 Actor 跟随官方当前可用范围，现在支持 Top Ads 工作流和当前的 [Creative Center Hashtag trends 页面](https://ads.tiktok.com/creative/creativeCenter/trends/hashtag)。

请先查看 target 层面的变化：

| Status | Target | 当前用户影响 |
|---|---|---|
| Supported | `top_ads_dashboard`、`top_ads_spotlight`、`ad_analytics`、`ad_keyframe`、`ad_percentile`、`ad_recommend` | 这些 Top Ads target 仍然可选，并保持原有使用流程。 |
| Restored / Changed | `trending_hashtags`、`hashtag_analytics` | 这两个 target 重新可选，但现在对齐当前官方 Hashtag trends 页面，不再使用 0.1.0 的旧 Hashtag 页面。 |
| Removed | `keyword_insights`、`keyword_insights_videos`、`keyword_insights_examples`、`keyword_insights_related`、`creative_insights`、`top_products`、`trending_songs_popular`、`trending_songs_breakout`、`song_analytics`、`trending_creators`、`trending_videos` | 这些旧 Creative Center target 不再可选；旧 saved/API input 继续传入时，会在发起上游请求和计费前直接拒绝。 |

如果你从 Actor `0.1.0` 升级 Hashtag 功能，再查看下面这些 target 相关的输入和输出变化。本次调整只保留当前官网页面上真实可见、可操作的筛选项，因此部分旧输入被移除，而不是作为隐藏参数保留。

| Status | Target | 0.1.0 输入或行为 | 当前行为 |
|---|---|---|---|
| Removed | `trending_hashtags` | `hashtags_search` 按 hashtag 文本搜索。 | 已移除，因为当前官网页面没有这个搜索筛选。 |
| Removed | `trending_hashtags` | `hashtags_new_to_top_100` 只看新进入 top 100 的 hashtag。 | 已移除，因为当前官网页面没有这个筛选。 |
| Changed | `trending_hashtags` | `hashtags_period` 支持 `7`、`30`、`120`。 | 现在支持 `7`、`30`、`90`，展示为 `Last 7 days`、`Last 30 days`、`Last 90 days`。 |
| Changed | `trending_hashtags` | `hashtags_limit` 最大可设为 `60`。 | 现在最大为 `20`，与当前官网请求分页大小一致。 |
| Changed | `trending_hashtags` | 旧列表输出使用 `code` / `msg` / `data.list` 结构。 | 列表输出跟随当前官方接口结构，例如 `BaseResp`、`items`、`pagination`、`hashtagID`、`popularityCurve`。 |
| Renamed | `hashtag_analytics` | `hashtag_analytics_hashtag_name` 使用 `hoco` 这类 hashtag 名称。 | 改为 `hashtag_analytics_hashtag_id`，可从 `Trending Hashtags` 结果或官网分析页 URL 中获得。 |
| Changed | `hashtag_analytics` | `hashtag_analytics_country` 可以留空表示 `All regions`。 | 现在使用具体国家或地区，默认 `United States`。 |
| Changed | `hashtag_analytics` | `hashtag_analytics_period` 支持 `7`、`30`、`120`、`365`、`1095`。 | 现在支持 `7`、`30`、`90`，与当前官网页面一致。 |
| Changed | `hashtag_analytics` | 旧详情输出使用 `code` / `msg` / `data.info` 结构。 | 详情输出跟随当前官方接口结构，例如 `BaseResp`、`hashtagID`、`popularityCurve`、用户画像和视频明细字段。 |
| Unchanged | `trending_hashtags`、`hashtag_analytics` | `Trending Hashtags` 和 `Hashtag Analytics` 的计费方式分别为 `0.002$ / item` 和 `0.002$ / time`。 | 计费方式保持不变。 |

## 💡 最佳实践

本 Actor 通过访问 TikTok 后端接口运行。TikTok 对接口存在未公开的限流规则。为了稳定运行并减少被限流的概率，建议参考以下做法：

### 💡 使用多个账号 Cookie

可以提供一组账号 Cookie，并在不同请求之间轮换使用。这样可以分摊请求压力，降低单个账号因为请求量过高而被限制的风险。

### 💡 控制并发请求数量

当你需要定时或批量调用多个接口时，如果同时发起大量请求，可能会触发限流。

建议在客户端实现 [Rate Limiting](https://en.wikipedia.org/wiki/Rate_limiting)，控制并发请求数量。例如使用 [Token Bucket Algorithm](https://en.wikipedia.org/wiki/Token_bucket)：按固定速率发放 token，请求前先获取 token，没有 token 时等待后重试。

更稳健的方式是使用 [Message Queuing](https://en.wikipedia.org/wiki/Message_queue)。定时脚本只负责把任务推入队列，由专门的消费者进程取出任务并请求接口。你可以通过限制消费者数量或增加限流逻辑来控制请求速度，失败任务也可以重新入队并延迟重试。

## ⚙️ 输入配置

### ⚙️ Main

* **Target** `target`：（必填）选择要采集的数据源。不同目标会使用下方不同的配置项。

  可选值：`Top Ads Dashboard`、`Top Ads Spotlight`、`Ad Analytics`、`Ad Keyframe`、`Ad Percentile`、`Ad Recommend`、`Trending Hashtags`、`Hashtag Analytics`。

* **Cookies** `cookies`：（必填）登录 [TikTok Creative Center](https://ads.tiktok.com/business/creativecenter/pc/en) 后获取的认证 Cookie。获取方式：

  ![](https://github.com/lofe-w/tiktok-creative-center-scraper-public/raw/main/imgs/get_cookie.png)

---

### ⚙️ Top Ads Dashboard 设置

当 `Target` 设置为 `Top Ads Dashboard` 时使用这些参数。

* **Keyword** `dashboard_search`：（可选）按品牌或产品关键词搜索。
* **Region** `dashboard_region`：（可选）按一个或多个地区筛选。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_region.json)
* **Industry** `dashboard_industry`：（可选）按一个或多个行业筛选广告。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_industry.json)
* **Objective** `dashboard_objective`：（可选）按广告投放目标筛选。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_objective.json)
* **Period** `dashboard_period`：（必填）按发布时间周期筛选。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_period.json)
* **Ad language** `dashboard_ad_language`：（可选）按广告创意语言筛选。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_ad_language.json)
* **Ad format** `dashboard_ad_format`：（可选）按广告形式筛选。`Spark ads` 使用自然帖子，`Non-Spark ads` 为传统广告。
* **Likes** `dashboard_likes`：（可选）按点赞数分位区间筛选。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_likes.json)
* **Sort by** `dashboard_sort_by`：（必填）选择广告结果排序指标。
* **Page** `dashboard_page`：（必填）页码。
* **Limit** `dashboard_limit`：（必填）每页数量。

---

### ⚙️ Top Ads Spotlight 设置

当 `Target` 设置为 `Top Ads Spotlight` 时使用这些参数。

* **Industry** `spotlight_industry`：（可选）按一个或多个 Spotlight 行业筛选广告。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/spotlight_industry.json)
* **Page** `spotlight_page`：（必填）页码。
* **Limit** `spotlight_limit`：（必填）每页数量。

---

### ⚙️ Ad Analytics 设置

当 `Target` 设置为 `Ad Analytics` 时使用这些参数。

* **Material id** `ad_analytics_material_id`：（必填）可从 `Top Ads Dashboard` 或 `Top Ads Spotlight` 的结果中获得。

---

### ⚙️ Ad Keyframe 设置

当 `Target` 设置为 `Ad Keyframe` 时使用这些参数。

* **Material id** `ad_keyframe_material_id`：（必填）可从 `Top Ads Dashboard` 或 `Top Ads Spotlight` 的结果中获得。
* **Metric** `ad_keyframe_metric`：（必填）选择要获取的关键帧指标。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/ad_keyframe_metric.json)

---

### ⚙️ Ad Percentile 设置

当 `Target` 设置为 `Ad Percentile` 时使用这些参数。

* **Material id** `ad_percentile_material_id`：（必填）可从 `Top Ads Dashboard` 或 `Top Ads Spotlight` 的结果中获得。
* **Metric** `ad_percentile_metric`：（必填）选择要获取的分位指标。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/ad_percentile_metric.json)
* **Period** `ad_percentile_period`：（必填）定义分位数据的时间范围。

---

### ⚙️ Ad Recommend 设置

当 `Target` 设置为 `Ad Recommend` 时使用这些参数。

* **Material id** `ad_recommend_material_id`：（必填）可从 `Top Ads Dashboard` 或 `Top Ads Spotlight` 的结果中获得。
* **Industry** `ad_recommend_industry`：（必填）推荐广告所属行业。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_industry.json)
* **Country** `ad_recommend_country`：（必填）推荐广告所属国家或地区。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_region.json)

---

### ⚙️ Trending Hashtags 设置

当 `Target` 设置为 `Trending Hashtags` 时使用这些参数。

* **Country** `hashtags_country`：（必填）按国家或地区筛选。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/hashtags_country.json)
* **Time period** `hashtags_period`：（必填）按官网时间范围筛选：`Last 7 days`、`Last 30 days` 或 `Last 90 days`。
* **Industry** `hashtags_industry`：（可选）按官网行业筛选。选择 `All Industries` 表示不使用行业筛选。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/hashtags_industry.json)
* **Page** `hashtags_page`：（必填）页码。
* **Limit** `hashtags_limit`：（必填）每页数量。

---

### ⚙️ Hashtag Analytics 设置

当 `Target` 设置为 `Hashtag Analytics` 时使用这些参数。

* **Hashtag ID** `hashtag_analytics_hashtag_id`：（必填）可从 `Trending Hashtags` 结果或官网 Hashtag 分析页面 URL 中获得。
* **Country** `hashtag_analytics_country`：（必填）按国家或地区筛选。[Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/hashtags_country.json)
* **Time period** `hashtag_analytics_period`：（必填）按官网时间范围筛选：`Last 7 days`、`Last 30 days` 或 `Last 90 days`。

为了稳定获得完整详情，建议使用同一国家或地区的 `Trending Hashtags` 结果中的 `hashtag_analytics_hashtag_id`。

---

## 📊 输出结构

Actor 会返回 dataset items。每个 item 的结构取决于你选择的 `target`。

**说明**：下面是简化后的结构示例。实际输出可能包含更多字段，请以实际运行结果为准。

### 📊 Top Ads Dashboard & Top Ads Spotlight

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021141421A2ED3905E2130C3F1389",
    "data": {
        "materials": [
            {
                "ad_title": "Example ad title",
                "brand_name": "Example brand",
                "cost": 1,
                "ctr": 0.93,
                "id": "7559593149158670352",
                "industry_key": "label_14104000000",
                "like": 230,
                "objective_key": "campaign_objective_reach",
                "video_info": {
                    "vid": "v10025g50000example",
                    "duration": 24.219,
                    "cover": "https://...",
                    "video_url": {
                        "720p": "https://..."
                    },
                    "width": 576,
                    "height": 1020
                }
            }
        ],
        "pagination": {
            "has_more": true,
            "page": 1,
            "size": 20,
            "total_count": 400
        }
    }
}
```

### 📊 Ad Analytics

```json
{
    "code": 0,
    "msg": "OK",
    "data": {
        "ad_title": "Example ad title",
        "brand_name": "Example brand",
        "comment": 1,
        "ctr": 0.34,
        "id": "7558904828435202056",
        "landing_page": "https://...",
        "like": 23116,
        "share": 522,
        "video_info": {
            "vid": "v10033g50000example",
            "duration": 5.931,
            "cover": "https://...",
            "video_url": {
                "720p": "https://..."
            }
        }
    }
}
```

### 📊 Ad Keyframe

```json
{
    "code": 0,
    "msg": "OK",
    "data": {
        "analysis": [
            {
                "second": 0,
                "value": 0.013720197930724248
            }
        ],
        "duration": 7,
        "highlight": [
            1
        ]
    }
}
```

### 📊 Ad Percentile

```json
{
    "code": 0,
    "msg": "OK",
    "data": {
        "ctr_percentile": 0.48
    }
}
```

### 📊 Ad Recommend

```json
{
    "code": 0,
    "msg": "OK",
    "data": {
        "materials": [
            {
                "ad_title": "Example recommended ad",
                "brand_name": "Example brand",
                "cost": 2,
                "ctr": 0.37,
                "id": "7553372735096815634",
                "like": 28543,
                "video_info": {
                    "vid": "v10033g50000example",
                    "duration": 6.434,
                    "cover": "https://...",
                    "video_url": {
                        "720p": "https://..."
                    }
                }
            }
        ]
    }
}
```

---

## 💰 使用成本与价格

计费模式：[Pay per event](https://docs.apify.com/platform/actors/publishing/monetize/pay-per-event)

事件触发逻辑取决于返回结果数量。

| Target | 价格 |
|---|---|
| [Top Ads Dashboard](https://ads.tiktok.com/business/creativecenter/inspiration/topads/pc/en) | 0.002$ / item |
| [Top Ads Spotlight](https://ads.tiktok.com/business/creativecenter/tiktok-topads-spotlight/pc/en) | 0.002$ / item |
| [Ad Analytics](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en) | 0.002$ / time |
| [Ad Keyframe](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en) | 0.002$ / time |
| [Ad Percentile](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en) | 0.002$ / time |
| [Ad Recommend](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en) | 0.002$ / time |
| [Trending Hashtags](https://ads.tiktok.com/creative/creativeCenter/trends/hashtag) | 0.002$ / item |
| [Hashtag Analytics](https://ads.tiktok.com/creative/creativeCenter/trends/hashtag) | 0.002$ / time |

已废弃 target 会在发起上游请求和计费前被拒绝。

## 📞 支持

如果你遇到问题或有功能请求，请在 Apify Console 的 Actor 页面使用 **Issues** tab，并尽量提供详细问题描述和 Run ID。

## ⚠️ 限制与免责声明

* 本 Actor 不是 TikTok 官方产品，与 TikTok, Inc. 没有关联，也不代表 TikTok 官方背书。
* TikTok Creative Center 网站和内部接口结构可能随时变化。
* 请负责任地使用本 Actor，并遵守 Apify Terms of Service。
