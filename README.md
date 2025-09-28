# TikTok Creative Center Scraper

Your ultimate tool for unlocking high-value, real-time data from the TikTok Creative Center. This Actor is designed for marketers, data analysts, and brands to track viral trends, analyze top-performing ads, discover emerging creators, and find trending songs, hashtags, and keywords directly from the source.

[Start Now (On Apify)](https://apify.com/doliz/tiktok-creative-center-scraper)

## ✨ Key Features

* **⚡️ Fast & Efficient**: Bypasses slow UI interactions by calling the backend API directly, saving you significant time and platform costs.
* **🎯 Multi-Target Scraping**: A single Actor to rule them all! Scrape multiple pages from the Creative Center, including:
    * [Top Ads (Dashboard & Spotlight)](https://ads.tiktok.com/business/creativecenter/inspiration/topads/pc/en)

      Optional include **details(analytics)** or **keyframe metrics(interactive time analysis)**
    * [Keyword Insights](https://ads.tiktok.com/business/creativecenter/keyword-insights/pc/en)
    * [Keyword Insights (Related videos)](https://ads.tiktok.com/business/creativecenter/keyword-insights/pc/en)
    * [Keyword Insights (Keyword examples)](https://ads.tiktok.com/business/creativecenter/tiktok-keyword/shoe/pc/en)
    * [Keyword Insights (Related Keywords & Hashtags)](https://ads.tiktok.com/business/creativecenter/tiktok-keyword/shoe/pc/en)
    * [Trending Hashtags](https://ads.tiktok.com/business/creativecenter/inspiration/popular/hashtag/pc/en)

      Optional include **details(analytics)**
    * [Trending Songs (Popular & Breakout)](https://ads.tiktok.com/business/creativecenter/inspiration/popular/music/pc/en)

      Optional include **details(analytics)**
    * [Trending Creators](https://ads.tiktok.com/business/creativecenter/inspiration/popular/creator/pc/en)
    * [Trending Videos](https://ads.tiktok.com/business/creativecenter/inspiration/popular/pc/en)

* **🔎 Powerful Filtering**: Utilize a rich set of input parameters to precisely target the data you need, mirroring the functionality of the Creative Center website.
* **🔧 Actively Maintained**: This is a commercial Actor. I am committed to maintaining it to adapt to TikTok's changes and ensure its continued reliability.

## ⚙️ Input Configuration

### ⚙️ Main

* **Target** `target`: (Required) Select the data source. Your choice determines which settings below are used.

  One of the `Top Ads Dashboard`, `Top Ads Spotlight`, `Trending Videos`, `Trending Creators`, `Trending Songs (Popular)`, `Trending Songs (Breakout)`, `Trending Hashtags`.

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
* **Include details** `dashboard_include_details`: (Optional) If enabled, fetches additional data from each ad's detail page.
* **Include keyframe metrics** `dashboard_include_keyframe_metrics`: (Optional) Select specific keyframe metrics to retrieve. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/dashboard_include_keyframe_metrics.json)
* **Limit** `dashboard_limit`: (Required) Specify the maximum number of ads to retrieve.

---

### ⚙️ Top Ads Spotlight Settings

These settings are only used when the `Target` is set to `Top Ads Spotlight`.

* **Industry** `spotlight_industry`: (Optional) Filter ads by one or more industries for Spotlight. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/spotlight_industry.json)
* **Include details** `spotlight_include_details`: (Optional) If enabled, fetches additional data from each ad's detail page.
* **Include keyframe metrics** `spotlight_include_keyframe_metrics`: (Optional) Select specific keyframe metrics to retrieve. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/spotlight_include_keyframe_metrics.json)
* **Limit** `spotlight_limit`: (Required) Specify the maximum number of ads to retrieve.

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
* **Limit** `keyword_limit`: (Required) Specify the maximum number of keywords to retrieve.

---

### ⚙️ Keyword Insights (Related videos) Settings

These settings are only used when the `Target` is set to `Keyword Insights (Related videos)`.

* **Keyword** `kvideos_keyword`: (Required) Get related videos by keyword.
* **Region** `kvideos_region`: (Optional) Filter results by one or more geographical regions. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_region.json)
* **Industry** `kvideos_industry`: (Optional) Filter keywords by one or more industries. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_industry.json)
* **Objective** `kvideos_objective`: (Optional) Filter keywords by their campaign marketing objective. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_objective.json)
* **Period** `kvideos_period`: (Required) Filter keywords by their publication period. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/keyword_period.json)
* **Include related videos limit** `kvideos_limit`: (Required) Specify the maximum number of related videos to retrieve.

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
* **Limit** `kexamples_limit`: (Required) Specify the maximum number of keyword examples to retrieve.

---

### ⚙️ Trending Hashtags Settings

These settings are only used when the `Target` is set to `Trending Hashtags`.

* **Country** `hashtags_country`: (Required) Select the country to view its hashtags. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/hashtags_country.json)
* **Industry** `hashtags_industry`: (Optional) Filter hashtags by industry. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/hashtags_industry.json)
* **Period** `hashtags_period`: (Required) Define the time frame for the trending hashtags data.
* **New to top 100** `hashtags_new_to_top_100`: (Optional) Show only hashtags that have recently entered the top 100 chart.
* **Search** `hashtags_search`: (Optional) Search by hashtag.
* **Include details** `hashtags_include_details`: (Optional) If enabled, fetches additional data from each hashtag's detail page.
* **Details period** `hashtags_details_period`: (Required when `Include details` is enabled) Define the time frame for the trending hashtag details data.
* **Limit** `hashtags_limit`: (Optional) Specify the maximum number of hashtags to retrieve.

---

### ⚙️ Trending Songs (Popular) Settings

These settings are only used when the `Target` is set to `Trending Songs (Popular)`.

* **Country** `popular_country`: (Required) Select the country to view its popular songs. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/popular_country.json)
* **Period** `popular_period`: (Required) Define the time frame for the trending songs data.
* **New to top 100** `popular_new_to_top_100`: (Optional) Show only songs that have recently entered the top 100 chart.
* **Approved for business use** `popular_approved_for_business_use`: (Optional) Show only songs pre-approved for commercial use.
* **Search** `popular_search`: (Optional) Search by song or artist.
* **Include details** `popular_include_details`: (Optional) If enabled, fetches additional data from each song's detail page.
* **Details period** `popular_details_period`: (Required when `Include details` is enabled) Define the time frame for the trending songs details data.
* **Limit** `popular_limit`: (Required) Specify the maximum number of songs to retrieve.

---

### ⚙️ Trending Songs (Breakout) Settings

These settings are only used when the `Target` is set to `Trending Songs (Breakout)`.

* **Country** `breakout_country`: (Required) Select the country to view its breakout songs. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/breakout_country.json)
* **Search** `breakout_search`: (Optional) Search by song or artist.
* **Include details** `breakout_include_details`: (Optional) If enabled, fetches additional data from each song's detail page.
* **Details period** `breakout_details_period`: (Required when `Include details` is enabled) Define the time frame for the trending songs details data.
* **Limit** `breakout_limit`: (Required) Specify the maximum number of songs to retrieve.

---

### ⚙️ Trending Creators Settings

These settings are only used when the `Target` is set to `Trending Creators`.

* **Creators country** `creators_country`: (Required) Select the geographical country of the creators. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/creators_country.json)
* **Audience country** `creators_audience_country`: (Optional) Filter creators by their audience's primary country. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/creators_audience_country.json)
* **Followers** `creators_followers`: (Optional) Filter creators by their number of followers.
* **Sort by** `creators_sort_by`: (Required) Select the metric for sorting the creators. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/creators_sort_by.json)
* **Search** `creators_search`: (Optional) Search by creator
* **Limit** `creators_limit`: (Required) Specify the maximum number of creators to retrieve.

---

### ⚙️ Trending Videos Settings

These settings are only used when the `Target` is set to `Trending Videos`.

* **Country** `videos_country`: (Required) Select the geographical country for trending videos. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/videos_country.json)
* **Period** `videos_period`: (Required) Define the time frame for the trending videos data. [Options](https://github.com/lofe-w/tiktok-creative-center-scraper-public/blob/main/options/videos_period.json)
* **Sort by** `videos_order_by`: (Required) Select the metric for sorting the trending videos. [Options](https://raw.githubusercontent.com/lofe-w/tiktok-creative-center-scraper-public/refs/heads/main/options/videos_order_by.json)
* **Limit** `videos_limit`: (Required) Specify the maximum number of videos to retrieve.

---

## 📊 Output Structure

The Actor returns a dataset of items. The structure of each item depends on the `target` you selected.

**NOTE**: The following are sample structures. The actual output may contain more fields. Please refer to the output of a sample run for the exact schema.

---

### 📊 Top Ads (Dashboard & Spotlight)

`Top Ads Dashboard`'s page size is **20**; `Top Ads Spotlight`'s page size is **50**.

- List-only: When `Include details` is disabled and `Include keyframe metrics` is not selected. One `List Event`(\$0.1) is consumed for every page results retrieved.

    ```json
    [
        {
            "ad_title": "🗃️ نجاحات حقيقية للأعمال مع +Service  #TikTokserviceplusmena @ramyzeytouni @english.with.adani @feynmaneducation @mahmoud.alsale7",
            "brand_name": "",
            "cost": 2,
            "ctr": 0.85,
            "favorite": false,
            "id": "7546175611464876049",
            "industry_key": "label_24112000000",
            "is_search": true,
            "like": 25503,
            "objective_key": "campaign_objective_video_view",
            "video_info": {
                "vid": "v14025g50000d2sk1dnog65hnip00fa0",
                "duration": 100.502,
                "cover": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/okmvAitallBAa5ULAaITIVAIAivR2PAlxLYBx~tplv-noop.image?t=9276707c\u0026x-expires=1758966036\u0026x-signature=Iq9G%2FJ0XlwiuXIAZy5j8MvT6jVM%3D",
                "video_url": {
                    "720p": "https://v16m-default.tiktokcdn.com/ede0240e34d2900521d9a5e8628a92cc/68d7b114/video/tos/alisg/tos-alisg-pve-0037/o4lVAAtR5YaEU2ti0lCBvnAviaQPALxbEAILI/?a=0\u0026bti=NTU4QDM1NGA%3D\u0026ch=0\u0026cr=0\u0026dr=0\u0026lr=tiktok_business\u0026cd=0%7C0%7C0%7C0\u0026cv=1\u0026br=784\u0026bt=392\u0026cs=0\u0026ds=3\u0026ft=cApXJCz7ThWHanF_EGZmo0P\u0026mime_type=video_mp4\u0026qs=0\u0026rc=ZjVmNjdlNzg0M2U1ZjszO0BpM2kzbGs5cmduNTMzODgzNEAvYzYyYC4tXl4xLjRfYy5gYSNeLW1rMmRrLnBhLS1kLzFzcw%3D%3D\u0026vvpl=1\u0026l=20250927113856B7C57584EB903A89AE99\u0026btag=e00090000"
                },
                "width": 576,
                "height": 1024
            }
        },
        ... /* Other results */
    ]
    ```

- With-details: When `Include details` is enabled, an extra `details` object is added to each result. This consumes extra one `Details Event`(\$0.1) per page result.

    ```json
    [
        {
            ..., /* List-only Output */
            "details": {
                "ad_title": "🗃️ نجاحات حقيقية للأعمال مع +Service  #TikTokserviceplusmena @ramyzeytouni @english.with.adani @feynmaneducation @mahmoud.alsale7",
                "brand_name": "",
                "comment": 127,
                "cost": 2,
                "country_code": ["EG", "LB", "BH", "KW", "OM", "MA", "DZ", "SA", "IQ", "QA", "AE"],
                "ctr": 0.85,
                "favorite": false,
                "has_summary": false,
                "highlight_text": "",
                "id": "7546175611464876049",
                "industry_key": "label_24112000000",
                "is_search": false,
                "keyword_list": null,
                "landing_page": "",
                "like": 25503,
                "objective_key": "campaign_objective_video_view",
                "objectives": [
                    {
                        "label": "campaign_objective_video_view",
                        "value": 4
                    }
                ],
                "pattern_label": [],
                "share": 934,
                "source": "Others",
                "source_key": 36,
                "video_info": {
                    "vid": "v14025g50000d2sk1dnog65hnip00fa0",
                    "duration": 100.502,
                    "cover": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/okmvAitallBAa5ULAaITIVAIAivR2PAlxLYBx~tplv-noop.image?t=9276707c\u0026x-expires=1758967468\u0026x-signature=bovb3SgFTv21eVclIAE7iDPItIw%3D",
                    "video_url": {
                        "720p": "https://v16m-default.tiktokcdn.com/fb38370c97f304e350a1153720d1e2ce/68d7b6ac/video/tos/alisg/tos-alisg-pve-0037/o4lVAAtR5YaEU2ti0lCBvnAviaQPALxbEAILI/?a=0\u0026bti=NTU4QDM1NGA%3D\u0026ch=0\u0026cr=0\u0026dr=0\u0026lr=tiktok_business\u0026cd=0%7C0%7C0%7C0\u0026cv=1\u0026br=784\u0026bt=392\u0026cs=0\u0026ds=3\u0026ft=cApXJCz7ThWHLc__EGZmo0P\u0026mime_type=video_mp4\u0026qs=0\u0026rc=ZjVmNjdlNzg0M2U1ZjszO0BpM2kzbGs5cmduNTMzODgzNEAvYzYyYC4tXl4xLjRfYy5gYSNeLW1rMmRrLnBhLS1kLzFzcw%3D%3D\u0026vvpl=1\u0026l=20250927120248AB5325965EDE5A8CAF7F\u0026btag=e00090000"
                    },
                    "width": 576,
                    "height": 1024
                },
                "voice_over": false
            }
        },
        ... /* Other results */
    ]
    ```

- With-keyframes: When `Include keyframe metrics` is selected, has extra `keyframe_*` object is added per keyframe option, per page results. This consumes extra one `Keyframes Event`(\$0.1) per keyframe option, per page results.

    - `CTR` selected → extra `keyframe_retain_ctr` object
    - `CVR` selected → extra `keyframe_retain_cvr` object
    - `Clicks` selected → extra `keyframe_click_cnt` object
    - `Conversion` selected → extra `keyframe_convert_cnt` object
    - `Remain` selected → extra `keyframe_play_retain_cnt` object

    The structures they output are consistent
    ```json
    [
        {
            ..., /* List-only Output */
            "keyframe_retain_ctr": {
                "analysis": [
                    {
                        "second": 0,
                        "value": 0.1
                    },
                    {
                        "second": 1,
                        "value": 0.8999999999999999
                    },
                    ... /* omit */
                    {
                        "second": 99,
                        "value": 0
                    }
                ],
                "duration": 100,
                "highlight": [2, 5, 10]
            }
        },
        ... /* Other results */
    ]
    ```

---

### 📊 Keyword Insights

`Keyword Insights`'s page size is **50**.

- One `List Event`(\$0.1) is consumed per page results retrieved.

    ```json
    [
        {
            "comment": 1528,
            "cost": 193000,
            "cpa": 12.5,
            "ctr": 1.36,
            "cvr": 9.85,
            "impression": 25000000,
            "keyword": "free shipping",
            "like": 70178,
            "play_six_rate": 8.41,
            "post": 8190,
            "post_change": 78.34,
            "share": 1588,
            "video_list": [
                "7528525829135944974",
                "7548765955007024392",
                "7545920550527405367",
                "7514835735384608046",
                "7507661938252369198"
            ]
        },
        ... /* Other results */
    ]
    ```

---

### 📊 Keyword Insights (Related videos)

- One `List Event`(\$0.1) is consumed per actor.

    ```json
    [
        "7528525829135944974",
        "7548765955007024392",
        ... /* omit */
        "7545920550527405367"
    ]
    ```

---

### 📊 Keyword Insights (Keyword examples)

`Keyword Insights (Keyword examples)`'s page size is **50**.

- One `List Event`(\$0.1) is consumed per page results retrieved.

    ```json
    [
        {
            "covers": [
                "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068c799-us/oAwsgWFjOAzgLeGQ0QfL8M2ABzqMAWnHfIc9fR~tplv-noop.image?t=9276707c\u0026x-expires=1759075386\u0026x-signature=m%2Bd6wWu05uyxGFU9yS4tN6Bn9lU%3D"
            ],
            "ctr": 73.33,
            "cvr": 57.5,
            "sentence": "Lemme Play Gummies Free Shipping Must buy Women’s products Women 30+ Women 40+ Trending products #tiktokshoprestock #lemme #women #supplements #gummies @lemme",
            "use_type": "script_use_type_title"
        },
        ... /* Other results */
    ]
    ```

---

### 📊 Trending Hashtags

`Trending Hashtags`'s page size is **50**.

- List-only: When `Include details` is disabled. One `List Event`(\$0.1) is consumed per page results retrieved.

    ```json
    [
        {
            "hashtag_id": "405389",
            "hashtag_name": "golive",
            "country_info": {
                "id": "QA",
                "value": "Qatar",
                "label": "QA"
            },
            "is_promoted": false,
            "trend": [
                {
                    "time": 1758326400,
                    "value": 0.47
                },
                {
                    "time": 1758412800,
                    "value": 0.44
                },
                ... /* omit */
                {
                    "time": 1758844800,
                    "value": 1
                }
            ],
            "creators": [
                {
                    "nick_name": "❤️samjhana❤️💕",
                    "avatar_url": "https://p19-common-sign-useastred.tiktokcdn-eu.com/tos-useast2a-avt-0068-giso/9a1b04464fa32c9f15ae73e1c4fc0973~tplv-tiktokx-cropcenter:100:100.png?dr=14579\u0026refresh_token=65ffb1a7\u0026x-expires=1759125600\u0026x-signature=G3Ndla%2FNrfC4nPp%2F34so84fkfqQ%3D\u0026t=4d5b0474\u0026ps=13740610\u0026shp=a5d48078\u0026shcp=317596d8\u0026idc=my"
                }
            ],
            "publish_cnt": 2032,
            "video_views": 7939394,
            "rank": 1,
            "rank_diff": 1,
            "rank_diff_type": 1
        },
        ... /* Other results */
    ]
    ```
- With-details: When `Include details` is enabled, an extra `details` object is added to each result. This consumes extra one `Details Event`(\$0.1) per page results.

    ```json
    [
        {
            ..., /* List-only Output */
            "details": {
                "info": {
                    "hashtag_id": "405389",
                    "hashtag_name": "golive",
                    "video_url": "https://www.tiktok.com/tag/golive",
                    "country_info": {
                        "id": "ALL",
                        "value": "ALL",
                        "label": "ALL"
                    },
                    "is_promoted": false,
                    "trend": [
                        {
                            "time": 1758326400,
                            "value": 0.62
                        },
                        {
                            "time": 1758412800,
                            "value": 0.66
                        },
                        ... /* omit */
                        {
                            "time": 1758844800,
                            "value": 0.99
                        }
                    ],
                    "publish_cnt": 120437,
                    "video_views": 887726837,
                    "publish_cnt_all": 542863,
                    "video_views_all": 4738608858,
                    "longevity": {
                        "popular_days": 0,
                        "current_popularity": 0
                    },
                    "audience_ages": [
                        {
                            "age_level": 4,
                            "score": 53
                        },
                        ... /* omit */
                        {
                            "age_level": 3,
                            "score": 22
                        }
                    ],
                    "audience_interests": [
                        {
                            "interest_info": {
                                "id": "10008",
                                "label": "diversify_10008",
                                "value": "Professional Special Effects"
                            },
                            "score": 327
                        },
                        ... /* omit */
                        {
                            "interest_info": {
                                "id": "10093",
                                "label": "diversify_10093",
                                "value": "Business \u0026 Finance"
                            },
                            "score": 169
                        }
                    ],
                    "audience_countries": [
                        {
                            "country_info": {
                                "id": "272103",
                                "label": "LB",
                                "value": "Lebanon"
                            },
                            "score": 2167
                        },
                        ... /* omit */
                        {
                            "country_info": {
                                "id": "798549",
                                "label": "RO",
                                "value": "Romania"
                            },
                            "score": 153
                        }
                    ],
                    "related_hashtags": [
                        {
                            "hashtag_id": "6417",
                            "hashtag_name": "live",
                            "video_url": "https://www.tiktok.com/tag/live"
                        },
                        ... /* omit */
                        {
                            "hashtag_id": "80007445",
                            "hashtag_name": "straykids",
                            "video_url": "https://www.tiktok.com/tag/straykids"
                        }
                    ],
                    "related_items": [
                        {
                            "item_id": 7549128372564069650,
                            "cover_uri": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/owKCCniwOEBFD8AAIn6gfIiUoDI8VBEBUmAf5B~tplv-noop.image?t=9276707c\u0026x-expires=1758977488\u0026x-signature=79aEVaQD%2BCkTCDuXpE%2FhUENIbCI%3D"
                        },
                        ... /* omit */
                        {
                            "item_id": 7551813247855267080,
                            "cover_uri": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/oQDeSnDkEFA2IvBztCEURbEuBwWxfRnNoPiLgb~tplv-noop.image?t=9276707c\u0026x-expires=1758977498\u0026x-signature=nnBVrNhK%2FhoyT4HjFKxKSdAFhyg%3D"
                        }
                    ]
                }
            }
        },
        ... /* Other results */
    ]
    ```

---

### 📊 Trending Songs (Popular & Breakout)

`Trending Songs (Popular)`'s page size is **20**; `Trending Songs (Breakout)`'s page size is **20**.

- List-only: When `Include details` is disabled. One `List Event`(\$0.1) is consumed per page results retrieved.

    ```json
    [
        {
            "author": "Joe Walsh",
            "clip_id": "6590963034687031301",
            "country_code": "QA",
            "cover": "https://p16-sg.tiktokcdn.com/aweme/720x720/tos-alisg-v-2774/oIVBAzmfA6ZoFBC7I3eCZuwDgExtQZAQ6jHTIA.jpeg",
            "duration": 30,
            "if_cml": false,
            "is_search": false,
            "link": "https://www.tiktok.com/music/x-6590963034687031301",
            "on_list_times": null,
            "promoted": false,
            "rank": 1,
            "rank_diff": null,
            "rank_diff_type": 4,
            "related_items": [
                {
                    "item_id": 7553210639578172679,
                    "cover_uri": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/ocvocuUeDAp2FRsggIFT0ZcDOfwjiRmEBEBnSI~tplv-noop.image?t=9276707c\u0026x-expires=1758976040\u0026x-signature=uF32FCeVEHRrcGqWXbvvujqEyFc%3D"
                },
                ... /* omit */
                {
                    "item_id": 7548500246725250321,
                    "cover_uri": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/o8U1RDQQHDGGARAnIlWICfTDyoLgjgsIlK4ee1~tplv-noop.image?t=9276707c\u0026x-expires=1758976045\u0026x-signature=8BaccExSwrl1c2IgBZrAO4nqOpU%3D"
                }
            ],
            "song_id": "6734206429713926145",
            "title": "Rocky Mountain Way",
            "trend": [
                {
                    "time": 1758326400,
                    "value": 0.55
                },
                {
                    "time": 1758412800,
                    "value": 0.59
                },
                ... /* omit */
                {
                    "time": 1758844800,
                    "value": 1
                }
            ],
            "url_title": "Rocky-Mountain-Way"
        },
        ... /* Other results */
    ]
    ```
- With-details: When `Include details` is enabled, an extra `details` object is added to each result. This consumes extra one `List Event`(\$0.1) per page results.

    ```json
    [
        {
            ..., /* List-only Output */
            "details": {
                "disliked": null,
                "like_count": null,
                "liked": null,
                "sound": {
                    "audience_ages": [
                        {
                            "age_level": 3,
                            "score": 59
                        },
                        ... /* omit */
                        {
                            "age_level": 5,
                            "score": 6
                        }
                    ],
                    "audience_countries": [
                        {
                            "country_info": {
                                "id": "390903",
                                "label": "GR",
                                "value": "Greece"
                            },
                            "score": 1200
                        },
                        ... /* omit */
                        {
                            "country_info": {
                                "id": "2635167",
                                "label": "GB",
                                "value": "United Kingdom"
                            },
                            "score": 440
                        }
                    ],
                    "audience_interests": [
                        {
                            "interest_info": {
                                "id": "10026",
                                "label": "diversify_10026",
                                "value": "Beauty"
                            },
                            "score": 294
                        },
                        ... /* omit */
                        {
                            "interest_info": {
                                "id": "10011",
                                "label": "diversify_10011",
                                "value": "Other Talent"
                            },
                            "score": 234
                        }
                    ],
                    "author": "Joe Walsh",
                    "clip_id": "6590963034687031301",
                    "country_code": "QA",
                    "cover": "https://p16-sg.tiktokcdn.com/aweme/720x720/tos-alisg-v-2774/oIVBAzmfA6ZoFBC7I3eCZuwDgExtQZAQ6jHTIA.jpeg",
                    "duration": 30,
                    "if_cml": false,
                    "is_search": false,
                    "link": "https://www.tiktok.com/music/x-6590963034687031301",
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
                            "item_id": 7553210639578172679,
                            "cover_uri": "https://p16-sign-sg.tiktokcdn.com/tos-alisg-p-0037/ocvocuUeDAp2FRsggIFT0ZcDOfwjiRmEBEBnSI~tplv-noop.image?t=9276707c\u0026x-expires=1758976920\u0026x-signature=aGjpw6TNFsBfmcwinWwOB8G1hus%3D"
                        },
                        ... /* omit */
                        {
                            "item_id": 7528454908945894678,
                            "cover_uri": "https://p19-vod-sign-useast2a.tiktokcdn-eu.com/tos-no1a-p-0037-no/ocpKQI03eDAe4u1O2OFgLjQB7IrAUDy9QAfy0E~tplv-noop.image?t=9276707c\u0026x-expires=1758976922\u0026x-signature=MmpSZBNLs5zAAmBi8QStFeDvv1U%3D"
                        }
                    ],
                    "song_id": "6734206429713926145",
                    "title": "Rocky Mountain Way",
                    "trend": [
                        {
                            "time": 1758326400,
                            "value": 0.55
                        },
                        {
                            "time": 1758412800,
                            "value": 0.59
                        },
                        ... /* omit */
                        {
                            "time": 1758844800,
                            "value": 1
                        }
                    ],
                    "url_title": "Rocky-Mountain-Way"
                }
            }
        },
        ... /* Other results */
    ]
    ```

---

### 📊 Trending Creators

`Trending Creators`'s page size is **50**.

- One `List Event`(\$0.1) is consumed per page results retrieved.

    ```json
    [
        {
            "tcm_id": "7414477993612935173",
            "user_id": "62133858422239232",
            "nick_name": "Fernanda",
            "avatar_url": "https://p16-sign-va.tiktokcdn.com/tos-maliva-avt-0068/200b649d30f76f1238d771f4aff51ee1~tplv-tiktokx-cropcenter:100:100.png?dr=14579\u0026refresh_token=86148874\u0026x-expires=1759125600\u0026x-signature=lff4lmv3BlQCJooKb7%2BkXdszfyk%3D\u0026t=4d5b0474\u0026ps=13740610\u0026shp=a5d48078\u0026shcp=317596d8\u0026idc=sg1",
            "country_code": "US",
            "follower_cnt": 9135515,
            "liked_cnt": 668294555,
            "tt_link": "https://www.tiktok.com/@ferchugimenez",
            "tcm_link": "https://creatormarketplace.tiktok.com/ad#/author/7414477993612935173",
            "items": [
                {
                    "item_id": "7444674312784645432",
                    "cover_url": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068/oQIBhn2EeBMUWQR5wVQACFEBtlDxgUDdAfoB8J~tplv-noop.image?t=9276707c\u0026x-expires=1758975932\u0026x-signature=CZie51aNoVsZjKdbTQ9KGoafBnI%3D",
                    "tt_link": "https://www.tiktok.com/@author/video/7444674312784645432",
                    "vv": 13733332,
                    "liked_cnt": 516217,
                    "create_time": 1733348322
                },
                ... /* omit */
                {
                    "item_id": "7095849716054789381",
                    "cover_url": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068/e43ff589d5244725b89cb58dbebf0b00~tplv-noop.image?t=9276707c\u0026x-expires=1758975916\u0026x-signature=BroLgq4VFjuEMh%2BCp2rgN7XZSng%3D",
                    "tt_link": "https://www.tiktok.com/@author/video/7095849716054789381",
                    "vv": 10422320,
                    "liked_cnt": 1547779,
                    "create_time": 1652131259
                }
            ]
        },
        ... /* Other results */
    ]
    ```

---

### 📊 Trending Videos

`Trending Videos`'s page size is **20**.

- One `List Event`(\$0.1) is consumed per page results retrieved.

    ```json
    [
        {
            "country_code": "US",
            "cover": "https://p16-sign-va.tiktokcdn.com/tos-maliva-p-0068c799-us/og8yzpBAHECQneA3ffMskRQ0cIbq3SjO0XUItk~tplv-noop.image?t=9276707c\u0026x-expires=1758975640\u0026x-signature=1yuyCigEelUv9uPnDsHb9z8Aldc%3D",
            "duration": 48,
            "id": "7546244699665812750",
            "item_id": "7546244699665812750",
            "item_url": "https://www.tiktok.com/@mnm_pipi/video/7546244699665812750",
            "region": "United States",
            "title": "#Peacockpartner The NFL's best games are on Sunday Night Football! Here are four predictions about who will shine the brightest in primetime in 2025. Catch all the SNF action streaming on Peacock to see if these picks come true! #nfl #nflpicks #nfl2025 #paperfootballguy "
        },
        ... /* Other results */
    ]
    ```

---

## 💰 Cost of Use & Pricing

Pricing model: [Pay per event](https://docs.apify.com/platform/actors/publishing/monetize/pay-per-event)

| Event                                                    | Description                                                                                                                    | Price    | Unit           |
|----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|----------------|
| Actor Start                                              | Charged when the Actor starts running. Number of events charged depends on Actor memory (one event per GB, minimum one event). | \$0.0001 | \$0.0001/actor |
| List Event(per page)                                     | One list event is consumed for every page retrieved.                                                                           | \$0.1    | \$0.1/page     |
| Details Event(per page)                                  | One details event is consumed for every page retrieved, when `Include details` is enabled.                                     | \$0.1    | \$0.1/page     |
| Keyframes Event(per page, per keyframe option)           | One keyframes event is consumed per keyframe option for every page retrieved, when `Include keyframe metrics` is selected.     | \$0.1    | \$0.1/page     |

For target:

| Target                                         | Page size |
|------------------------------------------------|-----------|
| Top Ads Dashboard                              | 20        |
| Top Ads Spotlight                              | 50        |
| Keyword Insights                               | 50        |
| Keyword Insights (Related videos)              | 50        |
| Keyword Insights (Keyword examples)            |           |
| Keyword Insights (Related Keywords & Hashtags) |           |
| Trending Hashtags                              | 60        |
| Trending Songs (Popular)                       | 20        |
| Trending Songs (Breakout)                      | 20        |
| Trending Creators                              | 50        |
| Trending Videos                                | 20        |


## 📞 Support

If you encounter any issues or have feature requests, please use the **Issues** tab on the Actor's page in the Apify Console. Please provide a detailed description of the problem and the Run ID.

## Limitations and Disclaimers

* This Actor is not an official TikTok product and is not affiliated with or endorsed by TikTok, Inc.
* The structure of the TikTok Creative Center website and its internal APIs may change at any time. I will do my best to maintain this Actor, but functionality is not guaranteed and occasional downtime may occur.
* Please use this Actor responsibly and in accordance with the Apify Terms of Service.
