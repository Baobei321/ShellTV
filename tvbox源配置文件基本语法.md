
<h1 align="center">TvBox 配置文件基本语法</h1>

## 1. 配置文件的基本结构
TVBox 的配置文件通常是一个 JSON 文件，包含以下主要部分：

```json
{
  "spider": "数据源爬虫配置",
  "sites": "站点列表",
  "parses": "解析规则列表",
  "flags": "分类标识",
  "lives": "直播源配置",
  "ijk": "播放器配置",
  "ads": "广告屏蔽配置",
  "doh": "DNS-over-HTTPS 配置"
}
```


## 2. 常见配置项详解
### (1) spider（数据源爬虫配置）
用于定义数据源的爬虫规则，通常是一个 URL 或 JS 脚本，后面的md5信息可选。

```json
"spider": "https://example.com/spider.jar;md5;928787071b399acc863d001929973803"
```

### (2) sites（站点列表）
定义影视站点，每个站点包含名称、API 地址、分类等信息。

```json
"sites": [
  {
    "key": "site1",
    "name": "站点1",
    "type": 3,
    "api": "https://example.com/api/v1",
    "searchable": 1,
    "quickSearch": 1,
    "filterable": 1,
    "hide": 0
  },
  {
    "key": "site2",
    "name": "站点2",
    "type": 3,
    "api": "https://example.com/api/v2",
    "searchable": 1,
    "quickSearch": 0,
    "filterable": 0,
     "hide": 1
  }
]
```
| 属性       | 描述                     | 缺省值   |
|------------|--------------------------|--------|
| key| 站点唯一标识  | |
| name| 站点名称| |
| type | 站点类型，0：xml 1：json 3：Spider | 1|
| api  | 站点 API 地址      | |
| searchable | 是否支持搜索，1：支持，0：不支持      | 1|
| quickSearch | 是否支持快速搜索，1：支持，0：不支持      | 1|
| filterable  | 是否支持筛选，1：支持，0：不支持      | 1|
| hide | 是否首页源选择中隐藏站点，1：隐藏，0：不隐藏| 0|
| playerType | 缺省播放器，1：IJK，2：EXO| 2|


### (3) parses（解析规则列表）
定义视频解析规则，通常是一个 URL 或 JS 脚本。

```json
"parses": [
  {
    "name": "解析1",
    "url": "https://example.com/parse1.js",
    "type": 0
  },
  {
    "name": "解析2",
    "url": "https://example.com/parse2.js",
    "type": 1
  }
]
```
- type: 0= 普通嗅探， 1= json， 2=Json扩展， 3= 聚合

### (4) flags（分类标识）
定义影视分类，用于首页推荐或筛选。
```json
"flags": [
  "国产剧",
  "美剧",
  "韩剧",
  "日剧",
  "电影",
  "综艺"
]
```
### (5) lives（直播源配置）
定义直播源，支持 M3U 或 TXT 格式。
```json
"lives": [
  {
    "name": "直播1",
    "type": 0,
    "url": "https://example.com/live1.m3u",
    "playertype": 0
  },
  {
    "name": "直播2",
    "type": 1,
    "url": "https://example.com/live2.txt",
    "playertype": 1
  }
]
```
| 属性       | 描述                     | 缺省值   |
|------------|--------------------------|--------|
| name| 直播源名称  | |
| type| 直播源类型，0：M3U 格式，1：TXT 格式  | 0|
| url| 直播源地址  | |
| playertype| 播放器类型，1：IJK 播放器，2：EXO 播放器  | 1|


### (6) ijk（播放器配置）
配置播放器参数，如解码器、硬解等。

```json
"ijk": {
  "mediaCodec": 1,
  "mediaCodecAutoRotate": 1,
  "mediaCodecHandleResolutionChange": 1,
  "opensles": 0,
  "soundTouch": 1
}
```
### (7) ads（广告配置）
定义广告过滤，通常是一个 URL。

```json
"ads": [
  "mimg.0c1q0l.cn",
  "www.googletagmanager.com"
]
```
### (8) doh（DNS-over-HTTPS 配置）
配置 DNS-over-HTTPS 服务，用于解析域名。

```json
"doh": [
  {
    "name": "Cloudflare",
    "url": "https://cloudflare-dns.com/dns-query"
  }
]
```


## 4. 注意事项
JSON 格式：配置文件必须符合 JSON 语法，否则 TVBox 无法正确加载。
数据源和解析规则：确保数据源和解析规则的 URL 可用。

测试配置：修改配置文件后，建议在 TVBox 中测试是否生效。

[完整源配置文件样例.json](./源配置样例.json)
