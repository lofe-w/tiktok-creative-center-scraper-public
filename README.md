# TikTok Creative Center Scraper

[中文 README](https://github.com/lofe-w/tiktok-creative-center-scraper-public/blob/main/README.zh-CN.md)

All In One! The definitive scraper for the official TikTok Creative Center surfaces available today. Reliably extract structured Top Ads data, deep ad analytics, keyframe performance, percentile benchmarks, and related ad recommendations for marketing intelligence, competitive research, and creative analysis.

[Start Now (On Apify)](https://apify.com/doliz/tiktok-creative-center-scraper)

## ✨ Key Features

* **⚡️ Fast & Efficient**: Bypasses slow UI interactions by calling the backend API directly, saving you significant time and platform costs.
* **🎯 All-in-one Official Scraping**: One Actor covering the current official TikTok Creative Center Top Ads workflow, including:
    * [Top Ads Dashboard](https://ads.tiktok.com/business/creativecenter/inspiration/topads/pc/en)
    * [Top Ads Spotlight](https://ads.tiktok.com/business/creativecenter/tiktok-topads-spotlight/pc/en)
    * [Ad Analytics](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Keyframe](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Percentile](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Recommend](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
* **🔎 Powerful Filtering**: Utilize a rich set of input parameters to precisely target the data you need, mirroring the functionality of the Creative Center website.
* **📦 Structured JSON Output**: Get clean, machine-readable data that is ready for dashboards, enrichment pipelines, competitive monitoring, and ad research workflows.
* **🧭 Officially Aligned Scope**: TikTok has refocused the available Creative Center surfaces, and this Actor follows that current official product scope.

## 💡 Best practices

This Actor operates by directly accessing TikTok's backend API. Please be aware that TikTok imposes undisclosed rate limits on its API. To ensure stable operation and avoid your requests being throttled, we strongly recommend following these best practices:

### 💡 Utilize Multiple Accounts (Cookies):

By providing a pool of account cookies, and rotate through them for different requests. This effectively distributes the request load and significantly reduces the risk of any single account being rate-limited due to high traffic.

### 💡 Limit the number of concurrent requests

For time-synchronized data, if a large number of API interfaces are called at the same time, the request may be throttled.

In this case, you can implement [Rate Limiting](https://en.wikipedia.org/wiki/Rate_limiting) on the client side, to control the number of concurrent requests. An example is the [Token Bucket Algorithm](https://en.wikipedia.org/wiki/Token_bucket). Tokens are issued according to the rate limit rules (for example, 10 tokens are issued per second). Before making a request, try to obtain the token, if there are no token currently available, wait for a period of time, then try again.

A more robust implementation is to use [Message Queuing](https://en.wikipedia.org/wiki/Message_queue). The timing script is not directly responsible for requesting the API, but uses a [producer-consumer](https://en.wikipedia.org/wiki/Producer%E2%80%93consumer_problem) Model. Push the requested task to the message queue, and a dedicated consumer takes the task from the queue for consumption (through an API request). You can limit the number of concurrent users by limiting the number of concurrent consumers for a certain type of task or using a rate limit. Tasks that fail to execute, can be pushed back into the queue (and set a certain delay) to retry.

## ⚙️ Input Configuration

### ⚙️ Main

* **Target** `target`: (Required) Select the data source. Your choice determines which settings below are used.

  One of `Top Ads Dashboard`, `Top Ads Spotlight`, `Ad Analytics`, `Ad Keyframe`, `Ad Percentile`, `Ad Recommend`.

* **Cookies** `cookies`: (Required) Your authentication cookie after logging into the [TikTok Creative Center](https://ads.tiktok.com/business/creativecenter/pc/en) platform. Way to obtain:

  ![](https://github.com/lofe-w/tiktok-creative-center-scraper-public/raw/main/imgs/get_cookie.png)

---

### ⚙️ Top Ads Dashboard Settings

These settings are only used when the `Target` is set to `Top Ads Dashboard`.

* **Keyword** `dashboard_search`: (Optional) Search by brand or product keywords.
* **Region** `dashboard_region`: (Optional) Filter results by one or more geographical regions. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_region.json)
* **Industry** `dashboard_industry`: (Optional) Filter ads by one or more industries. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_industry.json)
* **Objective** `dashboard_objective`: (Optional) Filter ads by their campaign marketing objective. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_objective.json)
* **Period** `dashboard_period`: (Required) Filter ads by their publication period. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_period.json)
* **Ad language** `dashboard_ad_language`: (Optional) Filter ads by the language used in the creative. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_ad_language.json)
* **Ad format** `dashboard_ad_format`: (Optional) Filter by ad format. 'Spark ads' use organic posts; 'Non-Spark ads' are traditional.
* **Likes** `dashboard_likes`: (Optional) Filter ads by the percentile range of likes received. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_likes.json)
* **Sort by** `dashboard_sort_by`: (Required) Select the metric for sorting the ad results.
* **Page** `dashboard_page`: (Required) Page number.
* **Limit** `dashboard_limit`: (Required) Page size.

---

### ⚙️ Top Ads Spotlight Settings

These settings are only used when the `Target` is set to `Top Ads Spotlight`.

* **Industry** `spotlight_industry`: (Optional) Filter ads by one or more industries for Spotlight. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/spotlight_industry.json)
* **Page** `spotlight_page`: (Required) Page number.
* **Limit** `spotlight_limit`: (Required) Page size.

---

### ⚙️ Ad Analytics Settings

These settings are only used when the `Target` is set to `Ad Analytics`.

* **Material id** `ad_analytics_material_id`: (Required) Obtain from the result of `Top Ads Dashboard` or `Top Ads Spotlight`.

---

### ⚙️ Ad Keyframe Settings

These settings are only used when the `Target` is set to `Ad Keyframe`.

* **Material id** `ad_keyframe_material_id`: (Required) Obtain from the result of `Top Ads Dashboard` or `Top Ads Spotlight`.
* **Metric** `ad_keyframe_metric`: (Required) Select specific keyframe metric to retrieve. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/ad_keyframe_metric.json).

---

### ⚙️ Ad Percentile Settings

These settings are only used when the `Target` is set to `Ad Percentile`.

* **Material id** `ad_percentile_material_id`: (Required) Obtain from the result of `Top Ads Dashboard` or `Top Ads Spotlight`.
* **Metric** `ad_percentile_metric`: (Required) Select specific percentile metric to retrieve. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/ad_percentile_metric.json).
* **Period** `ad_percentile_period`: (Required) Define the time frame for the percentile data.

---

### ⚙️ Ad Recommend Settings

These settings are only used when the `Target` is set to `Ad Recommend`.

* **Material id** `ad_recommend_material_id`: (Required) Obtain from the result of `Top Ads Dashboard` or `Top Ads Spotlight`.
* **Industry** `ad_recommend_industry`: (Required) Industry for recommend ads. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_industry.json)
* **Country** `ad_recommend_country`: (Required) Country for recommend ads. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_region.json)

---

## 📝 Creative Center Update

TikTok has refocused and reworked parts of Creative Center. This Actor follows the current official scope and now focuses on the Top Ads workflow listed above: Dashboard, Spotlight, ad-level analytics, keyframes, percentile benchmarks, and recommendations.

The former Creative Center targets below are no longer selectable in this Actor. Their original official links are kept here so existing users can recognize what changed. Some pages may redirect, show a new layout, or remain visible without the old stable data API; saved/API inputs using these targets are rejected before any upstream request or charge.

| Former target | Original official page | Current status |
|---|---|---|
| Keyword Insights | [Keyword Insights](https://ads.tiktok.com/business/creativecenter/keyword-insights/pc/en) | Deprecated |
| Keyword Insights related videos | [Keyword Insights](https://ads.tiktok.com/business/creativecenter/keyword-insights/pc/en) | Deprecated |
| Keyword Insights keyword examples | [Keyword detail](https://ads.tiktok.com/business/creativecenter/tiktok-keyword/shoe/pc/en) | Deprecated |
| Keyword Insights related keywords & hashtags | [Keyword detail](https://ads.tiktok.com/business/creativecenter/tiktok-keyword/shoe/pc/en) | Deprecated |
| Creative Insights | [Creative Insights](https://ads.tiktok.com/business/creativecenter/creative-pattern/pc/en) | Deprecated |
| Top Products | [Top Products](https://ads.tiktok.com/business/creativecenter/top-products/pc/en) | Deprecated |
| Trending Hashtags | [Trending Hashtags](https://ads.tiktok.com/business/creativecenter/inspiration/popular/hashtag/pc/en) | Deprecated |
| Hashtag Analytics | [Hashtag Analytics](https://ads.tiktok.com/business/creativecenter/hashtag/hoco/pc/en) | Deprecated |
| Trending Songs Popular | [Trending Songs](https://ads.tiktok.com/business/creativecenter/inspiration/popular/music/pc/en) | Deprecated |
| Trending Songs Breakout | [Trending Songs](https://ads.tiktok.com/business/creativecenter/inspiration/popular/music/pc/en) | Deprecated |
| Song Analytics | [Song Analytics](https://ads.tiktok.com/business/creativecenter/song/fantasmas-7326640926458743557/pc/en) | Deprecated |
| Trending Creators | [Trending Creators](https://ads.tiktok.com/business/creativecenter/inspiration/popular/creator/pc/en) | Deprecated |
| Trending Videos | [Trending Videos](https://ads.tiktok.com/business/creativecenter/inspiration/popular/pc/en) | Deprecated |

---

## 📊 Output Structure

The Actor returns a dataset of items. The structure of each item depends on the `target` you selected.

**NOTE**: The following are sample structures. The actual output may contain more fields. Please refer to the output of a sample run for the exact schema.

---

### 📊 Top Ads Dashboard & Top Ads Spotlight

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021141421A2ED3905E2130C3F1389",
    "data": {
        "materials": [
            {
                "ad_title": "※ネタバレ注意！今年も凄すぎる〜🎄✨#サボン #sabon #アドベントカレンダー #クリスマスコフレ #新作コスメ",
                "brand_name": "",
                "cost": 1,
                "ctr": 0.93,
                "favorite": false,
                "id": "7559593149158670352",
                "industry_key": "label_14104000000",
                "is_search": true,
                "like": 230,
                "objective_key": "campaign_objective_reach",
                "video_info": {
                    "vid": "v10025g50000d3i797vog65q5f4gnf60",
                    "duration": 24.219,
                    "cover": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/owkLvJdBKIKAKoEf6bEC8kB0QmMiiAPjAwOpdc~tplv-noop.image?t=9276707c&x-expires=1761048886&x-signature=A2dpK3MkBMV6K32G767F%2FbBdZPI%3D",
                    "video_url": {
                        "720p": "https://v16m-default.tiktokcdn.com/8949959c8a99b0e246d965c3f324134e/68f77936/video/tos/alisg/tos-alisg-pve-0037/o80Ko3tKPAvIjAiK6ALE8ryQFcBkw7f3hpgBiM/?a=0&bti=NTU4QDM1NGA%3D&ch=0&cr=0&dr=0&lr=tiktok_business&cd=0%7C0%7C1%7C0&cv=1&br=3496&bt=1748&cs=0&ds=3&ft=cApXJCz7ThWHdqtIEGZmo0P&mime_type=video_mp4&qs=0&rc=aDM7OjQ8Z2doNjZkPDg4M0BpM2lqaXQ5cjo6NjMzODgzNEBiYzI0MC00Xl4xLTAxYi0yYSMzazEyMmRzNmZhLS1kLy1zcw%3D%3D&vvpl=1&l=20251021141421A2ED3905E2130C3F1389&btag=e000b8000"
                    },
                    "width": 576,
                    "height": 1020
                }
            },
            ... /* omit */
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
---

### 📊 Ad Analytics

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "202510211416202976DB5255AD7A58AD76",
    "data": {
        "ad_title": "apple is back",
        "brand_name": "Starbucks",
        "comment": 1,
        "cost": 2,
        "country_code": [
            "US"
        ],
        "ctr": 0.34,
        "favorite": false,
        "has_summary": false,
        "highlight_text": "",
        "id": "7558904828435202056",
        "industry_key": "label_23116000000",
        "is_search": false,
        "keyword_list": null,
        "landing_page": "https://starbucks.app.link/r0xeHOZ5VVb?%243p=a_tiktok&%7Ecustomer_placement=tiktok&%7Ecampaign=fy2526q4q1fallsocial&%7Ecreative_name=featuredmenu",
        "like": 23116,
        "objective_key": "campaign_objective_reach",
        "objectives": [
            {
                "label": "campaign_objective_reach",
                "value": 5
            }
        ],
        "pattern_label": [],
        "share": 522,
        "source": "TikTok Ads Manager",
        "source_key": 1,
        "video_info": {
            "vid": "v10033g50000d3jaamfog65irh5pn29g",
            "duration": 5.931,
            "cover": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0051c001-sg/oA05SURcGgfsMNLqAuLFgLbzJCeeRbDQI5ASGz~tplv-noop.image?t=9276707c&x-expires=1761048985&x-signature=tk5EkZNf20ItC9IpWp4fcYe1z90%3D",
            "video_url": {
                "720p": "https://v16m-default.tiktokcdn.com/261e8ad48159561ab8ee4768e17f8d7d/68f77999/video/tos/alisg/tos-alisg-ve-0051c001-sg/okqEwcBJWE06i3bKvofAm3sFKyiY51BuAiATjI/?a=0&bti=NTU4QDM1NGA%3D&ch=0&cr=0&dr=0&lr=tiktok_business&cd=0%7C0%7C1%7C0&cv=1&br=1710&bt=855&cs=0&ds=3&ft=cApXJCz7ThWHrItIEGZmo0P&mime_type=video_mp4&qs=0&rc=aTg5MzdpPDRlPDY3NGk1PEBpajVza2w5cnBkNjMzODYzNEBfNl5hMTJgNS8xMi9jYDVhYSM2azJvMmRjXmdhLS1kMC1zcw%3D%3D&vvpl=1&l=202510211416202976DB5255AD7A58AD76&btag=e000b0000"
            },
            "width": 576,
            "height": 1024
        },
        "voice_over": false
    }
}
```

---

### 📊 Ad Keyframe

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021141815AF6461D583D2AF415D03",
    "data": {
        "analysis": [
            {
                "second": 0,
                "value": 0.013720197930724248
            },
            ... /* omit */
            {
                "second": 6,
                "value": 0.309604138551507
            }
        ],
        "duration": 7,
        "highlight": [
            1
        ]
    }
}
```

---

### 📊 Ad Percentile

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021173406B92FD6277A6134645863",
    "data": {
        "ctr_percentile": 0.48
    }
}
```

---

### 📊 Ad Recommend

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021175158CD9AD6F7297CA639BE2A",
    "data": {
        "materials": [
            {
                "ad_title": "an iced pumpkin cream chai the size of my body would probably cure me",
                "brand_name": "Starbucks",
                "cost": 2,
                "ctr": 0.37,
                "favorite": false,
                "id": "7553372735096815634",
                "industry_key": "label_23116000000",
                "is_search": false,
                "like": 28543,
                "objective_key": "campaign_objective_reach",
                "video_info": {
                    "vid": "v10033g50000d39g46nog65nq59ms5lg",
                    "duration": 6.434,
                    "cover": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0051c001-sg/oYANCrNTF0AJBIvuh4vAaAsUziYbViBEdUMG3~tplv-noop.image?t=9276707c&x-expires=1761061924&x-signature=FxWwVJmDyZhiNI0Rmgv%2FE8h8nlY%3D",
                    "video_url": {
                        "720p": "https://v16m-default.tiktokcdn.com/f1487176ecbcb22151720c68f8dc586d/68f7ac24/video/tos/alisg/tos-alisg-ve-0051c001-sg/oUAvN3NaACbUGBr0BhIoXA5DuEFUiVjMYWzMi/?a=0&bti=NTU4QDM1NGA%3D&ch=0&cr=0&dr=0&lr=tiktok_business&cd=0%7C0%7C1%7C0&cv=1&br=1976&bt=988&cs=0&ds=3&ft=cApXJCz7ThWHdwFIEGZmo0P&mime_type=video_mp4&qs=0&rc=NWc2NGVkNjk7OzY0OTk2aEBpajhwOHE5cjlqNjMzODYzNEAzNjRfNjAyXzUxMzRgXzY2YSNpcDZuMmRrMTZhLS1kMC1zcw%3D%3D&vvpl=1&l=20251021175158CD9AD6F7297CA639BE2A&btag=e000b0000"
                    },
                    "width": 576,
                    "height": 1024
                }
            },
          ... /* omit */
        ]
    }
}
```

---

## 💰 Cost of Use & Pricing

Pricing model: [Pay per event](https://docs.apify.com/platform/actors/publishing/monetize/pay-per-event)

The trigger logic of the event is the number of items that return the result.

| Target                                                                                             | Cost          |
|----------------------------------------------------------------------------------------------------|---------------|
| [Top Ads Dashboard](https://ads.tiktok.com/business/creativecenter/inspiration/topads/pc/en)        | 0.002$ / item |
| [Top Ads Spotlight](https://ads.tiktok.com/business/creativecenter/tiktok-topads-spotlight/pc/en)  | 0.002$ / item |
| [Ad Analytics](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)    | 0.002$ / time |
| [Ad Keyframe](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)     | 0.002$ / time |
| [Ad Percentile](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)   | 0.002$ / time |
| [Ad Recommend](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)    | 0.002$ / time |

Deprecated targets are rejected before any upstream request or charge.

## 📞 Support

If you encounter any issues or have feature requests, please use the **Issues** tab on the Actor's page in the Apify Console. Please provide a detailed description of the problem and the Run ID.

## ⚠️ Limitations and Disclaimers

* This Actor is not an official TikTok product and is not affiliated with or endorsed by TikTok, Inc.
* The structure of the TikTok Creative Center website and its internal APIs may change at any time.
* Please use this Actor responsibly and in accordance with the Apify Terms of Service.
