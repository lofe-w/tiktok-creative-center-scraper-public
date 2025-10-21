# TikTok Creative Center Scraper

Your ultimate tool for unlocking high-value, real-time data from the TikTok Creative Center. Designed for marketers, data analysts, and brands, this is the only Actor you need to master the full spectrum of TikTok Creative Center intelligence.

[Start Now (On Apify)](https://apify.com/doliz/tiktok-creative-center-scraper)

## ✨ Key Features

* **⚡️ Fast & Efficient**: Bypasses slow UI interactions by calling the backend API directly, saving you significant time and platform costs.
* **🎯 All-in-one Scraping**: A single Actor to rule them all! Scrape multiple pages from the Creative Center, including:
    * [Top Ads Dashboard)](https://ads.tiktok.com/business/creativecenter/inspiration/topads/pc/en)
    * [Top Ads Spotlight)](https://ads.tiktok.com/business/creativecenter/tiktok-topads-spotlight/pc/en)
    * [Ad Analytics](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Keyframe](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Percentile](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Ad Recommend](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)
    * [Keyword Insights](https://ads.tiktok.com/business/creativecenter/keyword-insights/pc/en)
    * [Keyword Insights (Related videos)](https://ads.tiktok.com/business/creativecenter/keyword-insights/pc/en)
    * [Keyword Insights (Keyword examples)](https://ads.tiktok.com/business/creativecenter/tiktok-keyword/shoe/pc/en)
    * [Keyword Insights (Related Keywords & Hashtags)](https://ads.tiktok.com/business/creativecenter/tiktok-keyword/shoe/pc/en)
    * [Trending Hashtags](https://ads.tiktok.com/business/creativecenter/inspiration/popular/hashtag/pc/en)
    * [Hashtag Analytics](https://ads.tiktok.com/business/creativecenter/hashtag/hoco/pc/en)
    * [Trending Songs Popular](https://ads.tiktok.com/business/creativecenter/inspiration/popular/music/pc/en)
    * [Trending Songs Breakout](https://ads.tiktok.com/business/creativecenter/inspiration/popular/music/pc/en)
    * [Song Analytics](https://ads.tiktok.com/business/creativecenter/song/fantasmas-7326640926458743557/pc/en)
    * [Trending Creators](https://ads.tiktok.com/business/creativecenter/inspiration/popular/creator/pc/en)
    * [Trending Videos](https://ads.tiktok.com/business/creativecenter/inspiration/popular/pc/en)

* **🔎 Powerful Filtering**: Utilize a rich set of input parameters to precisely target the data you need, mirroring the functionality of the Creative Center website.
* **🔧 Actively Maintained**: This is a commercial Actor. I am committed to maintaining it to adapt to TikTok's changes and ensure its continued reliability.

## ⚙️ Input Configuration

### ⚙️ Main

* **Target** `target`: (Required) Select the data source. Your choice determines which settings below are used.

  One of the `Top Ads Dashboard`, `Top Ads Spotlight`, `Ad Analytics`, `Ad Keyframe`, `Ad Percentile`, `Ad Recommend`, `Keyword Insights`, `Keyword Insights (Related videos)`, `Keyword Insights (Keyword examples)`, `Keyword Insights (Related Keywords & Hashtags)`, `Trending Hashtags`, `Hashtag Analytics`, `Trending Songs (Popular)`, `Trending Songs (Breakout)`, `Song Analytics`, `Trending Creators`, `Trending Videos`.

* **Cookies** `cookies`: (Required) Your authentication cookie after logging into the [TikTok Creative Center](https://ads.tiktok.com/business/creativecenter/pc/en) platform. Way to obtain:

  ![](https://github.com/lofe-w/tiktok-creative-center-scraper-public/raw/main/imgs/get_cookie.png)

---

### ⚙️ Top Ads Dashboard Settings

These settings are only used when the `Target` is set to `Top Ads Dashboard`.

* **Keyword** `dashboard_keyword`: (Optional) Search by brand or product keywords.
* **Region** `dashboard_region`: (Optional) Filter results by one or more geographical regions. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_region.json)
* **Industry** `dashboard_industry`: (Optional) Filter ads by one or more industries. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_industry.json)
* **Objective** `dashboard_objective`: (Optional) Filter ads by their campaign marketing objective. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_objective.json)
* **Period** `dashboard_period`: (Required) Filter ads by their publication period. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_period.json)
* **Ad language** `dashboard_ad_language`: (Optional) Filter ads by the language used in the creative. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_ad_language.json)
* **Ad format** `dashboard_ad_format`: (Optional) Filter by ad format. 'Spark ads' use organic posts; 'Non-Spark ads' are traditional.
* **Likes** `dashboard_likes`: (Optional) Filter ads by the percentile range of likes received. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_likes.json)
* **Sort by** `dashboard_sort_by`: (Required) Select the metric for sorting the ad results.
* **Limit** `dashboard_page`: (Required) Page number.
* **Limit** `dashboard_limit`: (Required) Page size.

---

### ⚙️ Top Ads Spotlight Settings

These settings are only used when the `Target` is set to `Top Ads Spotlight`.

* **Industry** `spotlight_industry`: (Optional) Filter ads by one or more industries for Spotlight. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/spotlight_industry.json)
* **Limit** `spotlight_page`: (Required) Page number.
* **Limit** `spotlight_limit`: (Required) Page size.

---

### ⚙️ Ad Analytics Settings

These settings are only used when the `Target` is set to `Ad Analytics`.

* **Material id** `ad_analytics_material_id`: (Required) Obtain from the result of `Top Ads Dashboard` or `Top Ads Spotlight`.

---

### ⚙️ Ad Recommend Settings

These settings are only used when the `Target` is set to `Ad Recommend`.

* **Material id** `ad_recommend_material_id`: (Required) Obtain from the result of `Top Ads Dashboard` or `Top Ads Spotlight`.
* **Industry** `ad_recommend_industry`: (Required) Industry for recommend ads. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_industry.json)
* **Country** `ad_recommend_country`: (Required) Country for recommend ads. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_region.json)

---

### ⚙️ Ad Percentile Settings

These settings are only used when the `Target` is set to `Ad Percentile`.

* **Material id** `ad_percentile_material_id`: (Required) Obtain from the result of `Top Ads Dashboard` or `Top Ads Spotlight`.
* **Metric** `ad_percentile_metric`: (Required) Select specific percentile metric to retrieve. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/ad_percentile_metric.json).
* **Period** `ad_percentile_period`: (Required) Define the time frame for the percentile data.

---

### ⚙️ Ad Keyframe Settings

These settings are only used when the `Target` is set to `Ad Keyframe`.

* **Material id** `ad_percentile_material_id`: (Required) Obtain from the result of `Top Ads Dashboard` or `Top Ads Spotlight`.
* **Metric** `ad_percentile_metric`: (Required) Select specific percentile metric to retrieve. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/ad_percentile_metric.json).


---

### ⚙️ Keyword Insights Settings

These settings are only used when the `Target` is set to `Keyword Insights`.

* **Search** `keyword_search`: (Optional) Search by keyword.
* **Region** `keyword_region`: (Optional) Filter results by one or more geographical regions. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_region.json)
* **Industry** `keyword_industry`: (Optional) Filter keywords by one or more industries. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_industry.json)
* **Objective** `keyword_objective`: (Optional) Filter keywords by their campaign marketing objective. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_objective.json)
* **Keyword type** `keyword_type`: (Optional) Filter keywords by types. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_type.json)
* **Period** `keyword_period`: (Required) Filter keywords by their publication period. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_period.json)
* **Order by** `keyword_order_by`: (Required) Select the metric for sorting the keyword results. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_order_by.json)
* **Order type** `keyword_order_type`: (Required) Select the sorting type for the keyword results.
* **Limit** `keyword_page`: (Required) Page number.
* **Limit** `keyword_limit`: (Required) Page size.

---

### ⚙️ Keyword Insights (Related videos) Settings

These settings are only used when the `Target` is set to `Keyword Insights (Related videos)`.

* **Keyword** `kvideos_keyword`: (Required) Get related videos by keyword.
* **Region** `kvideos_region`: (Optional) Filter results by one or more geographical regions. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_region.json)
* **Industry** `kvideos_industry`: (Optional) Filter keywords by one or more industries. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_industry.json)
* **Objective** `kvideos_objective`: (Optional) Filter keywords by their campaign marketing objective. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_objective.json)
* **Period** `kvideos_period`: (Required) Filter keywords by their publication period. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_period.json)
* **Limit** `kvideos_limit`: (Required) Page size.

---

### ⚙️ Keyword Insights (Keyword examples) Settings

These settings are only used when the `Target` is set to `Keyword Insights (Keyword examples)`.

* **Keyword** `kexamples_keyword`: (Required) Get examples by keyword.
* **Region** `kexamples_region`: (Optional) Filter results by one or more geographical regions. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_region.json)
* **Industry** `kexamples_industry`: (Optional) Filter keyword examples by one or more industries. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_industry.json)
* **Objective** `kexamples_objective`: (Optional) Filter keyword examples by their campaign marketing objective. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_objective.json)
* **Period** `kexamples_period`: (Required) Filter keyword examples by their publication period. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_period.json)
* **Order by** `kexamples_order_by`: (Required) Select the metric for sorting the keyword examples results.
* **Order type** `kexamples_order_type`: (Required) Select the sorting type for the keyword examples.
* **Limit** `kexamples_page`: (Required) Page number.
* **Limit** `kexamples_limit`: (Required) Page size.

---

### ⚙️ Keyword Insights (Related Keywords & Hashtags) Settings

These settings are only used when the `Target` is set to `Keyword Insights (Related Keywords & Hashtags)`.

* **Keyword** `krelated_keyword`: (Required) Get related keywords or hashtags by keyword.
* **Type** `krelated_type`: (Required) Get related content by type.
* **Region** `krelated_region`: (Optional) Filter results by one or more geographical regions. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_region.json)
* **Industry** `krelated_industry`: (Optional) Filter keywords by one or more industries. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_industry.json)
* **Period** `krelated_period`: (Required) Filter keywords by their publication period. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_period.json)
* **limit** `krelated_page`: (Required) Page number.
* **limit** `krelated_limit`: (Required) Page size.

---

### ⚙️ Trending Hashtags Settings

These settings are only used when the `Target` is set to `Trending Hashtags`.

* **Country** `hashtags_country`: (Required) Select the country to view its hashtags. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/hashtags_country.json)
* **Industry** `hashtags_industry`: (Optional) Filter hashtags by industry. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/hashtags_industry.json)
* **Period** `hashtags_period`: (Required) Define the time frame for the trending hashtags data. Options: "7", "30", "120"
* **New to top 100** `hashtags_new_to_top_100`: (Optional) Show only hashtags that have recently entered the top 100 chart.
* **Search** `hashtags_search`: (Optional) Search by hashtag.
* **Limit** `hashtags_page`: (Required) Page number.
* **Limit** `hashtags_limit`: (Required) Page size.

---

### ⚙️ Hashtag Analytics Settings

These settings are only used when the `Target` is set to `Hashtag Analytics`.

* **Hashtag name** `hashtag_analytics_hashtag_name`: (Required) Hashtag name. Obtain from the result of `Trending Hashtags`.
* **Country** `hashtag_analytics_country`: (Required) Select the country to view its analytics data. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/hashtags_country.json)
* **Period** `hashtag_analytics_period`: (Required) Define the time frame for the analytics data. Options: "7", "30", "120", "365", "1095"

---

### ⚙️ Trending Songs (Popular) Settings

These settings are only used when the `Target` is set to `Trending Songs (Popular)`.

* **Country** `popular_country`: (Required) Select the country to view its popular songs. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/popular_country.json)
* **Period** `popular_period`: (Required) Define the time frame for the trending songs data.
* **New to top 100** `popular_new_to_top_100`: (Optional) Show only songs that have recently entered the top 100 chart.
* **Approved for business use** `popular_approved_for_business_use`: (Optional) Show only songs pre-approved for commercial use.
* **Search** `popular_search`: (Optional) Search by song or artist.
* **Limit** `popular_page`: (Required) Page number.
* **Limit** `popular_limit`: (Required) Page size.

---

### ⚙️ Trending Songs (Breakout) Settings

These settings are only used when the `Target` is set to `Trending Songs (Breakout)`.

* **Country** `breakout_country`: (Required) Select the country to view its breakout songs. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/breakout_country.json)
* **Search** `breakout_search`: (Optional) Search by song or artist.
* **Limit** `breakout_page`: (Required) Page number.
* **Limit** `breakout_limit`: (Required) Page size.

---

### ⚙️ Song Analytics Settings

These settings are only used when the `Target` is set to `Song Analytics`.

* **Clip id** `song_analytics_clip_id`: (Required) Clip id. Obtain from the result of `Trending Songs (Popular)` or `Trending Songs (Breakout)`.
* **Country** `song_analytics_country`: (Required) Select the country to view its analytics data. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/breakout_country.json)
* **Period** `song_analytics_period`: (Required) Define the time frame for the analytics data. Options: "7", "30", "120"

---

### ⚙️ Trending Creators Settings

These settings are only used when the `Target` is set to `Trending Creators`.

* **Creators country** `creators_country`: (Required) Select the geographical country of the creators. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/creators_country.json)
* **Audience country** `creators_audience_country`: (Optional) Filter creators by their audience's primary country. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/creators_audience_country.json)
* **Followers** `creators_followers`: (Optional) Filter creators by their number of followers.
* **Sort by** `creators_sort_by`: (Required) Select the metric for sorting the creators. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/creators_sort_by.json)
* **Search** `creators_search`: (Optional) Search by creator.
* **Limit** `creators_page`: (Required) Page number.
* **Limit** `creators_limit`: (Required) Page size.

---

### ⚙️ Trending Videos Settings

These settings are only used when the `Target` is set to `Trending Videos`.

* **Country** `videos_country`: (Required) Select the geographical country for trending videos. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/videos_country.json)
* **Period** `videos_period`: (Required) Define the time frame for the trending videos data. [Options](https://github.com/lofe-w/tiktok-creative-center-scraper-public/blob/main/options/videos_period.json)
* **Sort by** `videos_order_by`: (Required) Select the metric for sorting the trending videos. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/videos_order_by.json)
* **Limit** `videos_page`: (Required) Page number.
* **Limit** `videos_limit`: (Required) Page size.

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

### 📊 Keyword Insights

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021141854DA8EA35393F03D4F0888",
    "data": {
        "keyword_list": [
            {
                "comment": 34739,
                "cost": 853000,
                "cpa": 0.05,
                "ctr": 4.7,
                "cvr": 100,
                "impression": 414000000,
                "keyword": "for free",
                "like": 1984613,
                "play_six_rate": 20.94,
                "post": 104000,
                "post_change": 129.21,
                "share": 61573,
                "video_list": [
                    "7562494760590658833",
                    "7517880292862872839",
                    "7561508660518882578",
                    "7557041207109618956",
                    "7525143203834596663"
                ]
            },
            ... /* omit */
        ],
        "pagination": {
            "page": 1,
            "size": 50,
            "total": 500,
            "has_more": true
        }
    }
}
```

---

### 📊 Keyword Insights (Related videos)

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021142043DBC5326153792F526C43",
    "data": {
        "video_list": [
            "7556199779693514002",
            "7530445111419850039",
            ... /* omit */
        ]
    }
}
```

---

### 📊 Keyword Insights (Keyword examples)

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "202510211421080D774D917D50306ACAF3",
    "data": {
        "pagination": {
            "page": 1,
            "size": 50,
            "total": 28,
            "has_more": false
        },
        "sentence_list": [
            {
                "covers": [
                    "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/5c12d9d97967404c8ed0036bffc6c54f_1709391498~tplv-noop.image?t=9276707c&x-expires=1761049288&x-signature=RFGfoeC%2FpBtgbcRW4tTPo7Mswhs%3D"
                ],
                "ctr": 40,
                "cvr": 0,
                "sentence": "#trending #xuhuong #2024 #meme #shopping",
                "use_type": "script_use_type_title"
            },
            ... /* omit */
        ]
    }
}
```

---

### 📊 Keyword Insights (Related Keywords & Hashtags)

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "2025102114213239B201F33E22C23FCB60",
    "data": {
        "list": [
            {
                "name": "ชั้นใน",
                "score": 100
            },
            ... /* omit */
        ]
    }
}
```

---

### 📊 Trending Hashtags

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021142231C1F07AF59616583266A4",
    "data": {
        "list": [
            {
                "hashtag_id": "601255",
                "hashtag_name": "hoco",
                "country_info": {
                    "id": "US",
                    "value": "United States",
                    "label": "US"
                },
                "is_promoted": false,
                "trend": [
                    {
                        "time": 1760400000,
                        "value": 0.54
                    },
                    {
                        "time": 1760486400,
                        "value": 0.35
                    },
                    {
                        "time": 1760572800,
                        "value": 0.28
                    },
                    {
                        "time": 1760659200,
                        "value": 0.27
                    },
                    {
                        "time": 1760745600,
                        "value": 0.33
                    },
                    {
                        "time": 1760832000,
                        "value": 0.7
                    },
                    {
                        "time": 1760918400,
                        "value": 1
                    }
                ],
                "publish_cnt": 115458,
                "video_views": 254321646,
                "rank": 1,
                "rank_diff_type": 4
            },
            ... /* omit */
        ],
        "pagination": {
            "page": 1,
            "size": 60,
            "total": 100,
            "has_more": true
        }
    }
}
```

---

### 📊 Hashtag Analytics

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021142337B6F9483058BE0D3DB6D7",
    "data": {
        "info": {
            "hashtag_id": "601255",
            "hashtag_name": "hoco",
            "description": "It's Homecoming season! Show us how you're getting ready for #HoCo.",
            "video_url": "https://www.tiktok.com/tag/hoco",
            "country_info": {
                "id": "ALL",
                "value": "ALL",
                "label": "ALL"
            },
            "is_promoted": false,
            "trend": [
                {
                    "time": 1760400000,
                    "value": 0.54
                },
                ... /* omit */
                {
                    "time": 1760918400,
                    "value": 1
                }
            ],
            "publish_cnt": 120049,
            "video_views": 366084497,
            "publish_cnt_all": 1683931,
            "video_views_all": 13178730685,
            "longevity": {
                "popular_days": 0,
                "current_popularity": 0
            },
            "audience_ages": [
                {
                    "age_level": 3,
                    "score": 73
                },
                ... /* omit */
            ],
            "audience_interests": [
                {
                    "interest_info": {
                        "id": "10015",
                        "label": "diversify_10015",
                        "value": "Campus Life"
                    },
                    "score": 117
                },
                ... /* omit */
            ],
            "audience_countries": [
                {
                    "country_info": {
                        "id": "6252001",
                        "label": "US",
                        "value": "United States"
                    },
                    "score": 669
                },
                ... /* omit */
            ],
            "related_hashtags": [
                {
                    "hashtag_id": "1603145068720134",
                    "hashtag_name": "tiktokbacktoschool",
                    "video_url": "https://www.tiktok.com/tag/tiktokbacktoschool"
                },
                ... /* omit */
            ],
            "related_items": [
                {
                    "item_id": 7562659435622010000,
                    "cover_uri": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/o8DTnWfaBd5fRF5IJCyCALoyE5QD7InAjs34f9~tplv-noop.image?t=9276707c&x-expires=1761049429&x-signature=5gVQie6DMmSJ9gb%2FthcK4UaF6hc%3D"
                },
                ... /* omit */
            ]
        }
    }
}
```

---

### 📊 Trending Songs (Popular) & Trending Songs (Breakout)

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021142712EE4858F6BD9C05547E9D",
    "data": {
        "pagination": {
            "page": 1,
            "size": 20,
            "total": 100,
            "has_more": true
        },
        "sound_list": [
            {
                "author": "Doddie Savage",
                "clip_id": "7552073523387205648",
                "country_code": "US",
                "cover": "https://p16-sg.tiktokcdn.com/aweme/720x720/tos-alisg-v-2774/o0iOK0WyiuUzBiKDaAoEAwAZRFAZAxByWEQfss.jpeg",
                "duration": 60,
                "if_cml": false,
                "is_search": false,
                "link": "https://www.tiktok.com/music/x-7552073523387205648",
                "on_list_times": null,
                "promoted": false,
                "rank": 1,
                "rank_diff": 0,
                "rank_diff_type": 2,
                "related_items": [
                    {
                        "item_id": 7562062508232576000,
                        "cover_uri": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068c799-us/o03a1OMgBIb96x7rAHiAVvR97BfDouEEizAVEe~tplv-noop.image?t=9276707c&x-expires=1761049638&x-signature=4oNk6GWhu7q3VV6KoN7z1SigOGk%3D"
                    },
                    {
                        "item_id": 7561923075134983000,
                        "cover_uri": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068c799-us/oUixQrIoeA7BDGfDi0LKrRWBSbxvIWikEkQgIB~tplv-noop.image?t=9276707c&x-expires=1761049643&x-signature=o4jb2eS6HAioDVy5J%2BkroP8ta14%3D"
                    },
                    {
                        "item_id": 7562380203083697000,
                        "cover_uri": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068c799-us/owGlzIn5QFeyEQINNeGeRQjOCfcU9AnQHhATLj~tplv-noop.image?t=9276707c&x-expires=1761049641&x-signature=3gvBMI%2ByG0UIIV4m0H%2F4R3ml78E%3D"
                    },
                    {
                        "item_id": 7562321544534298000,
                        "cover_uri": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068c799-us/osi7iWHeAA9RAET2oRIjh2iREuEyVVfwBqBmB0~tplv-noop.image?t=9276707c&x-expires=1761049658&x-signature=VlEYb1PGAtJLb1XcNkYRnl2GvRc%3D"
                    }
                ],
                "song_id": "7552084308169672705",
                "title": "Whoopty Doo",
                "trend": [
                    {
                        "time": 1760745600,
                        "value": 0
                    },
                    {
                        "time": 1760832000,
                        "value": 0.19
                    },
                    {
                        "time": 1760918400,
                        "value": 1
                    }
                ],
                "url_title": "Whoopty-Doo"
            },
            ... /* omit */
        ]
    }
}
```

---

### 📊 Song Analytics

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021142747AEEF1A91FFA2C1586C33",
    "data": {
        "disliked": null,
        "like_count": null,
        "liked": null,
        "sound": {
            "audience_ages": null,
            "audience_countries": [
                {
                    "country_info": {
                        "id": "660013",
                        "label": "FI",
                        "value": "Finland"
                    },
                    "score": 1527
                },
                ... /* omit */
            ],
            "audience_interests": [
                {
                    "interest_info": {
                        "id": "10002",
                        "label": "diversify_10002",
                        "value": "Hilarious Fails"
                    },
                    "score": 254
                },
                ... /* omit */
            ],
            "author": "HUMBE",
            "clip_id": "7326640926458743557",
            "country_code": "US",
            "cover": "https://p16-sg.tiktokcdn.com/aweme/720x720/tos-alisg-v-2774/o4AAbIXCgGA7vQffKGFsAtfDLA6IAIem11T5GU.jpeg",
            "duration": 12,
            "if_cml": false,
            "is_search": false,
            "link": "https://www.tiktok.com/music/x-7326640926458743557",
            "longevity": {
                "popular_days": 0,
                "current_popularity": 0
            },
            "music_url": null,
            "on_list_times": null,
            "promoted": false,
            "rank": null,
            "rank_diff": null,
            "related_items": [
                {
                    "item_id": 7562333750168653000,
                    "cover_uri": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068c799-us/ogQeYL3KAoejWGgwQ8zIXBzSfbII5RGqADCyIh~tplv-noop.image?t=9276707c&x-expires=1761049739&x-signature=1n7FNtcZDc8I%2F2YpjMbxyawp%2Bp8%3D"
                },
                ... /* omit */
            ],
            "song_id": "7299899156654475266",
            "title": "fantasmas",
            "trend": [
                {
                    "time": 1760400000,
                    "value": 0.56
                },
                ... /* omit */
                {
                    "time": 1760918400,
                    "value": 0.87
                }
            ],
            "url_title": "fantasmas"
        }
    }
}
```

---

### 📊 Trending Creators

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "20251021142829BAE766CD7E38FC4A990F",
    "data": {
        "creators": [
            {
                "tcm_id": "7414477993612935173",
                "user_id": "62133858422239232",
                "nick_name": "Fernanda",
                "avatar_url": "https://p16-sign-va.tiktokcdn.com/tos-maliva-avt-0068/3fa0e612da6c7528e77ef65fbb79a932~tplv-tiktokx-cropcenter:100:100.png?dr=14579&refresh_token=2b43df9f&x-expires=1761199200&x-signature=7pFx84EiRAXO%2Fs308G6%2BVrYCBWg%3D&t=4d5b0474&ps=13740610&shp=a5d48078&shcp=317596d8&idc=my",
                "country_code": "US",
                "follower_cnt": 9135515,
                "liked_cnt": 668294555,
                "tt_link": "https://www.tiktok.com/@ferchugimenez",
                "tcm_link": "https://creatormarketplace.tiktok.com/ad#/author/7414477993612935173",
                "items": [
                    {
                        "item_id": "7444674312784645432",
                        "cover_url": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068/oQIBhn2EeBMUWQR5wVQACFEBtlDxgUDdAfoB8J~tplv-noop.image?t=9276707c&x-expires=1761049779&x-signature=GPU6SW3m4B9ers8E%2B%2BJOjNW9dVg%3D",
                        "tt_link": "https://www.tiktok.com/@author/video/7444674312784645432",
                        "vv": 13733332,
                        "liked_cnt": 516217,
                        "create_time": 1733348322
                    },
                    {
                        "item_id": "7200099364549774598",
                        "cover_url": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068/290e93cfbb6249e484c263f1024b612b_1676403776~tplv-noop.image?t=9276707c&x-expires=1761049744&x-signature=indrHl%2BqhJU7%2BjYBIJJHvGXajEY%3D",
                        "tt_link": "https://www.tiktok.com/@author/video/7200099364549774598",
                        "vv": 17975712,
                        "liked_cnt": 306648,
                        "create_time": 1676403774
                    },
                    {
                        "item_id": "7095849716054789381",
                        "cover_url": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068/e43ff589d5244725b89cb58dbebf0b00~tplv-noop.image?t=9276707c&x-expires=1761049763&x-signature=BeaIPP%2B6PpzC8iY8YgRG2nhfws4%3D",
                        "tt_link": "https://www.tiktok.com/@author/video/7095849716054789381",
                        "vv": 10422320,
                        "liked_cnt": 1547779,
                        "create_time": 1652131259
                    }
                ]
            },
            ... /* omit */
        ],
        "pagination": {
            "page": 1,
            "size": 50,
            "total": 459,
            "has_more": true
        }
    }
}
```

---

### 📊 Trending Videos

```json
{
    "code": 0,
    "msg": "OK",
    "request_id": "202510211429195707715B59F5C85B409C",
    "data": {
        "pagination": {
            "has_more": true,
            "limit": 20,
            "page": 1,
            "total_count": 500
        },
        "videos": [
            {
                "country_code": "US",
                "cover": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068c799-us/o4eoqQ7gGWpCvCeVAIeJAGKggL4JyRII78Ij5i~tplv-noop.image?t=9276707c&x-expires=1761049792&x-signature=ZZKnqKe37bvk%2BUT3zZwoyK6Tk1w%3D",
                "duration": 31,
                "id": "7552950479534279967",
                "item_id": "7552950479534279967",
                "item_url": "https://www.tiktok.com/@mnm_pipi/video/7552950479534279967",
                "region": "United States",
                "title": "The Delonghi Dedica Duo Espresso Machine has been such a great little addition to our kitchen! I’ve been starting off my mornings with this protein shake and it’s been so fun using the machine. Super easy to use and love the pretty neutral color. Also comes in other beautiful colors as well, including pink and green. You can shop these beauties @Walmart #walmartpartner"
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

|Target| Cost          |
|---|---------------|
|[Top Ads Dashboard)](https://ads.tiktok.com/business/creativecenter/inspiration/topads/pc/en)| 0.002$ / item |
|[Top Ads Spotlight)](https://ads.tiktok.com/business/creativecenter/tiktok-topads-spotlight/pc/en)| 0.002$ / item |
|[Ad Analytics](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)| 0.002$ / time |
|[Ad Keyframe](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)| 0.002$ / time |
|[Ad Percentile](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)| 0.002$ / time |
|[Ad Recommend](https://ads.tiktok.com/business/creativecenter/topads/7558904828435202056/pc/en)| 0.002$ / time |
|[Keyword Insights](https://ads.tiktok.com/business/creativecenter/keyword-insights/pc/en)| 0.002$ / item |
|[Keyword Insights (Related videos)](https://ads.tiktok.com/business/creativecenter/keyword-insights/pc/en)| 0.002$ / time |
|[Keyword Insights (Keyword examples)](https://ads.tiktok.com/business/creativecenter/tiktok-keyword/shoe/pc/en)| 0.002$ / item |
|[Keyword Insights (Related Keywords & Hashtags)](https://ads.tiktok.com/business/creativecenter/tiktok-keyword/shoe/pc/en)| 0.002$ / time |
|[Trending Hashtags](https://ads.tiktok.com/business/creativecenter/inspiration/popular/hashtag/pc/en)| 0.002$ / item |
|[Hashtag Analytics](https://ads.tiktok.com/business/creativecenter/hashtag/hoco/pc/en)| 0.002$ / time |
|[Trending Songs Popular](https://ads.tiktok.com/business/creativecenter/inspiration/popular/music/pc/en)| 0.002$ / item |
|[Trending Songs Breakout](https://ads.tiktok.com/business/creativecenter/inspiration/popular/music/pc/en)| 0.002$ / item |
|[Song Analytics](https://ads.tiktok.com/business/creativecenter/song/fantasmas-7326640926458743557/pc/en)| 0.002$ / time |
|[Trending Creators](https://ads.tiktok.com/business/creativecenter/inspiration/popular/creator/pc/en)|      0.002$ / item    |
|[Trending Videos](https://ads.tiktok.com/business/creativecenter/inspiration/popular/pc/en)|          0.002$ / item |

## 📞 Support

If you encounter any issues or have feature requests, please use the **Issues** tab on the Actor's page in the Apify Console. Please provide a detailed description of the problem and the Run ID.

## Limitations and Disclaimers

* This Actor is not an official TikTok product and is not affiliated with or endorsed by TikTok, Inc.
* The structure of the TikTok Creative Center website and its internal APIs may change at any time. I will do my best to maintain this Actor, but functionality is not guaranteed and occasional downtime may occur.
* Please use this Actor responsibly and in accordance with the Apify Terms of Service.
