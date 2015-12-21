---
title: Kaskus API Reference

language_tabs:
  - php

toc_footers:
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>
  - <a href='http://kasdok.mooo.com'>Improved version of Kasdok</a>

includes:
  - status

search: true
---

# Introduction

Welcome to the Kaskus API! You can use our API to access Kaskus API endpoints

## Getting Started

This is general guide on how to use Kaskus API. 
Kaskus api base URI is located in https://www.kaskus.co.id/api/oauth (without trailing slash) and will be refered as BASE_URI in example and detailed guide. 
Module available will be listed in sidebar located on left side of the page (sorted alphabetically).

The API is RESTful. Data is exposed in the form of URIs that represent resources and can be fetched with HTTP clients (like web browsers).
 
 
Most of the API use OAuth based authentication, so it does honor "Authorization" header (and it is required to include in most request).

`Authorization: Oauth 1 signature`
 
Data returned in the response message is provided in two formats, the default format is XML and another is JSON . 
To make a request which return certain data types you can use a query string or request header.


query string

`/uri?output=json`

request header 

`Return-Type: text/json`



# Chat



## POST chat/authentication

Endpoint to login user (only for chat application)

### HTTP Request

`POST /v1/chat/authentication`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## GET chat/user

Get certain user chat service availability

### HTTP Request

`GET /v1/chat/user/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id
output|output format (JSON or XML)



# Followed



## GET followed

Get List of followed user

### HTTP Request

`GET /followed`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## POST followed

Follow user

### HTTP Request

`POST /followed/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id
output|output format (JSON or XML)



## DELETE followed

Delete followed user

### HTTP Request

`DELETE /followed/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id
output|output format (JSON or XML)



# Follower



## GET follower

Get List of follower user

### HTTP Request

`GET /follower`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
[
    {
        "follower_id": 10793,
        "follower_name": "bolobolo",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/03\/12\/avatar10793_1.gif",
        "usertitle": "Auto Banned",
        "number_of_post": 0,
        "enable_reputation": 1,
        "reputation": 0,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "follower_id": 123478,
        "follower_name": "k4p4u",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2005\/11\/27\/male.jpg",
        "usertitle": "newbie",
        "number_of_post": 5,
        "enable_reputation": 1,
        "reputation": 0,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "follower_id": 929146,
        "follower_name": "betatester",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/06\/15\/avatar929146_6.gif",
        "usertitle": "newbie",
        "number_of_post": 39,
        "enable_reputation": 1,
        "reputation": 0,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 0
    }
]
```

# Forum



## GET forum/top_kaskuser

Return Top Users, Top Moderators, and Top Regional Leaders

### HTTP Request

`GET /forum/top_kaskuser`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "top_users": [
        {
            "userid": "51917",
            "username": "zenk",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2004\/09\/16\/avatar51917_5.gif",
            "usertitle": "Co-Admin Kaskus",
            "number_of_post": 16312,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "userid": "5684521",
            "username": "ebureg",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2013\/07\/19\/avatar5684521_28.gif",
            "usertitle": "newbie",
            "number_of_post": 2,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "reputation_box": 1
        },
        {
            "userid": "275848",
            "username": "babono",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/17\/avatar275848_7.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 2184,
            "enable_reputation": 1,
            "reputation": 28,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
            "reputation_box": 1
        },
        {
            "userid": "275848",
            "username": "babono",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/17\/avatar275848_7.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 2184,
            "enable_reputation": 1,
            "reputation": 28,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
            "reputation_box": 1
        },
        {
            "userid": "275848",
            "username": "babono",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/17\/avatar275848_7.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 2184,
            "enable_reputation": 1,
            "reputation": 28,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
            "reputation_box": 1
        },
        {
            "userid": "2562",
            "username": "andi",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/04\/12\/avatar2562_1.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 2001,
            "enable_reputation": 1,
            "reputation": 3,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "reputation_box": 1
        }
    ],
    "top_moderators": [],
    "top_regional_leaders": []
}
```

## GET forum/events

Return Kaskus Live data and Events Calendar

### HTTP Request

`GET /forum/events`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "kaskus_live": {
        "dateline": 1393917269,
        "first_post_id": "53157d55f8ca171c668b460d",
        "forum_id": 21,
        "last_post": 1402448910,
        "last_post_id": "5397ac0effb410e006000000",
        "last_post_userid": 3,
        "last_poster": "admin",
        "open": 0,
        "poll_id": 0,
        "post_userid": 1196407,
        "post_username": "benatura",
        "prefix_id": "",
        "reply_count": 4,
        "short_url": "http:\/\/kask.us\/hxTl2",
        "sticky": 0,
        "title": "test aja",
        "views": 4597,
        "visible": 4,
        "vote_num": 8,
        "vote_total": 36,
        "thread_id": "53157d55f8ca171c668b460c",
        "hot_thread": 1,
        "thread_type": 10,
        "initial_prefix_id": "",
        "meta_images": [],
        "live_id": "1",
        "image": "image.jpg",
        "link": "\/thread\/53157d55f8ca171c668b460c\/kepedulian-sosial-untuk-miranda\/",
        "description": "hahahahhaa",
        "date": "01 Jan 1970",
        "day": "Kamis",
        "time_start": 1450676221,
        "time_end": 1450676221,
        "date_event": false
    },
    "event_calendar": []
}
```

## GET forum/threads

Get Thread List (forum) of Selected Forum

### HTTP Request

`GET /v1/forum/{id}/threads`

Parameter | Description
--------- | -----------
id|forum id
output|output format (JSON or XML)
page|number of post page
limit|limit number of post per page
sort|Sorting method (lastpost,thread,postusername,views,replycount,rating,price).
order|Ordering method (asc, desc)




> Example response

```json
{
    "forum": {
        "forum_id": "21",
        "name": "The Lounge",
        "description": "Forum bagi Kaskuser untuk berbagi gosip, gambar, foto, dan video yang seru, lucu, serta unik.",
        "thread_count": "549206",
        "post_count": "209098676",
        "visible": "1",
        "last_thread_id": "56739c4725ed60ee068b4570",
        "last_thread_title": "Test Hashtag 7",
        "last_thread_starter": "admin",
        "last_post_id": "56739c4725ed60ee068b4571",
        "last_post": "1450417223",
        "last_poster": "admin",
        "service": "forum",
        "forum_icon": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    "subforum": [
        {
            "forum_id": "59",
            "name": "Gosip Nyok!",
            "description": "Tempat bergosip bareng Kaskuser.",
            "last_post_id": "5530d324cdcf861cc7004330",
            "last_post": "1429263140",
            "last_poster": "Refenus",
            "last_thread_id": "54ea968fc721e6006e000001",
            "last_thread_title": "asdadfda",
            "service": "forum",
            "forum_icon": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
        },
        {
            "forum_id": "186",
            "name": "Lounge Pictures &amp; Video",
            "description": "Tempat berbagi kumpulan gambar menarik, seru, lucu, dan unik.",
            "last_post_id": "54c86801b80a29b6000041b9",
            "last_post": "1422419974",
            "last_poster": "hansip",
            "last_thread_id": "53109f24bfcb17a1028b4576",
            "last_thread_title": "Mengintip Proses Pembuatan Piala Oscar",
            "service": "forum",
            "forum_icon": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
        }
    ],
    "top_thread": [],
    "top_feature": [],
    "thread": [
        {
            "dateline": 1385869080,
            "first_post_id": "529aaf183c118e5f4d0000a6",
            "forum_id": 21,
            "last_post": 1411634609,
            "last_post_id": "5423d5ac4964a5ea15585e4d",
            "last_post_userid": 39291,
            "last_poster": "hansip",
            "open": 0,
            "poll_id": 0,
            "post_userid": 689150,
            "post_username": "aladin sticker",
            "prefix_id": "",
            "reply_count": 59,
            "short_url": "http:\/\/kask.us\/hoVWF",
            "sticky": 1,
            "title": "MOBIL MENKES  EDAN!!!!",
            "views": 4632,
            "visible": 1,
            "vote_num": 1,
            "vote_total": 5,
            "thread_id": "529aaf183c118e5f4d0000a5",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "meta_images": [],
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/02\/11\/avatar689150_1.gif",
            "usertitle": "kaskus maniac",
            "number_of_post": 4422,
            "enable_reputation": 1,
            "reputation": 27,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
            "reputation_box": 1
        },
        {
            "dateline": 1407929619,
            "first_post_id": "53eb4d13c721e6fe0d00001f",
            "forum_id": 21,
            "last_post": 1407929619,
            "last_post_id": "53eb4d13c721e6fe0d00001f",
            "last_post_userid": 3283,
            "last_poster": "hell",
            "meta_images": [],
            "open": 1,
            "poll_id": 0,
            "post_userid": 3283,
            "post_username": "hell",
            "prefix_id": "",
            "reply_count": -2,
            "short_url": "http:\/\/kask.us\/clX",
            "sticky": 1,
            "title": "hell test",
            "views": 15,
            "visible": 1,
            "vote_num": 1,
            "vote_total": 4,
            "thread_id": "53eb4d13c721e6fe0d00001e",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/04\/23\/male.jpg",
            "usertitle": "newbie",
            "number_of_post": 21,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "dateline": 1365867205,
            "first_post_id": "51697ac51ad719882b00000a",
            "forum_id": 21,
            "last_post": 1403176582,
            "last_post_id": "53a2c6818ead0e1e01afcae9",
            "last_post_userid": 39291,
            "last_poster": "hansip",
            "open": 0,
            "poll_id": 0,
            "post_userid": 217057,
            "post_username": "gegep",
            "prefix_id": "",
            "reply_count": 4323,
            "short_url": "http:\/\/kask.us\/g9pgP",
            "sticky": 1,
            "title": "The Lounge Darurat Bot! Yang Nge-bot Laporin di Sini!",
            "views": 228458,
            "visible": 1,
            "vote_num": 540,
            "vote_total": 1818,
            "thread_id": "51697ac51ad719882b000009",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "meta_images": [],
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2006\/11\/01\/avatar217057_4.gif",
            "usertitle": "Moderator Kaskus",
            "number_of_post": 21902,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 7",
            "dateline": 1450417223,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "56739c4725ed60ee068b4571",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450417223,
            "last_post_id": "56739c4725ed60ee068b4571",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "takut, Indonesia, negatif, China, pasar, murah, gulung_tikar, ACFTA, perdagangan",
            "short_url": "http:\/\/kask.us\/hxQMk",
            "thread_id": "56739c4725ed60ee068b4570",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar3_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 25045,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 6",
            "dateline": 1450417208,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "56739c3825ed60ee068b456f",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450417208,
            "last_post_id": "56739c3825ed60ee068b456f",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "kerja, produktif, pemerintah, buruh, perempuan, PELACUR, RAMPOK, HUMAN, TRAFFICKING, Operasi",
            "short_url": "http:\/\/kask.us\/hxQMi",
            "thread_id": "56739c3825ed60ee068b456e",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar3_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 25045,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 5",
            "dateline": 1450417187,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "56739c2325ed60ee068b456d",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450417187,
            "last_post_id": "56739c2325ed60ee068b456d",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "Indonesia, tarif, listrik, industri, produksi, importir, China, murah",
            "short_url": "http:\/\/kask.us\/hxQMg",
            "thread_id": "56739c2325ed60ee068b456c",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar3_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 25045,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 4",
            "dateline": 1450417163,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "56739c0b25ed60ee068b456b",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450417163,
            "last_post_id": "56739c0b25ed60ee068b456b",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "MEDIA, Indonesia, batik, tekstil",
            "short_url": "http:\/\/kask.us\/hxQMe",
            "thread_id": "56739c0b25ed60ee068b456a",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar3_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 25045,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 3",
            "dateline": 1450417097,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "56739bc925ed60ed068b456a",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450417097,
            "last_post_id": "56739bc925ed60ed068b456a",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "skenario, pemerintah, industri, pengusaha, ACFTA, Indonesia, China, media",
            "short_url": "http:\/\/kask.us\/hxQMc",
            "thread_id": "56739bc925ed60ed068b4569",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar3_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 25045,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 2",
            "dateline": 1450417079,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "56739bb725ed60ed068b4568",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450417079,
            "last_post_id": "56739bb725ed60ed068b4568",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "indonesia, ACFTA, sistem, perekonomian, industri, padat_karya",
            "short_url": "http:\/\/kask.us\/hxQMa",
            "thread_id": "56739bb725ed60ed068b4567",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar3_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 25045,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 1",
            "dateline": 1450412106,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "5673884a25ed60ee068b4569",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450412106,
            "last_post_id": "5673884a25ed60ee068b4569",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "Naga, China, provokatif, ekonomi, Grand, Design, ACFTA, ASEAN, Indonesia",
            "short_url": "http:\/\/kask.us\/hxQL8",
            "thread_id": "5673884a25ed60ee068b4568",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar3_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 25045,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "test",
            "dateline": 1450336193,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56725fc18ead0ec2000041d0",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450336193,
            "last_post_id": "56725fc18ead0ec2000041d0",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "thread_id": "56725fc18ead0ec2000041d1",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "test",
            "dateline": 1450336186,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56725fba8ead0eeb2b0041cb",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450336186,
            "last_post_id": "56725fba8ead0eeb2b0041cb",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "thread_id": "56725fba8ead0eeb2b0041cc",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "test",
            "dateline": 1450335997,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56725efd8ead0e892c0041d1",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450335997,
            "last_post_id": "56725efd8ead0e892c0041d1",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "thread_id": "56725efd8ead0e892c0041d2",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "test",
            "dateline": 1450335989,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56725ef58ead0ec2000041cd",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450335989,
            "last_post_id": "56725ef58ead0ec2000041cd",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "thread_id": "56725ef58ead0ec2000041ce",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "dateline": 1450322737,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56722b318ead0eeb2b0041c8",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450322737,
            "last_post_id": "56722b318ead0eeb2b0041c8",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "thread_id": "56722b318ead0eeb2b0041c9",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "dateline": 1450322724,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56722b248ead0e892c0041ce",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450322724,
            "last_post_id": "56722b248ead0e892c0041ce",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "thread_id": "56722b248ead0e892c0041cf",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "dateline": 1450322715,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56722b1b8ead0ec2000041ca",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450322715,
            "last_post_id": "56722b1b8ead0ec2000041ca",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "thread_id": "56722b1b8ead0ec2000041cb",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "test create thread",
            "dateline": 1450318722,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 2,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56721b828ead0eeb2b0041c6",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450318722,
            "last_post_id": "56721b828ead0eeb2b0041c6",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "short_url": "http:\/\/kask.us\/hxQLA",
            "thread_id": "56721b828ead0eeb2b0041c5",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "test create thread",
            "dateline": 1450318698,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 2,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56721b6a8ead0e892c0041cc",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450318698,
            "last_post_id": "56721b6a8ead0e892c0041cc",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "short_url": "http:\/\/kask.us\/hxQLy",
            "thread_id": "56721b6a8ead0e892c0041cb",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "test create thread",
            "dateline": 1450318675,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 2,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56721b538ead0ec2000041c8",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450318675,
            "last_post_id": "56721b538ead0ec2000041c8",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "short_url": "http:\/\/kask.us\/hxQLw",
            "thread_id": "56721b538ead0ec2000041c7",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        }
    ],
    "thread_num": 20000,
    "current_page": 1,
    "total_page": 1000,
    "per_page": 20
}
```

# Forumlist



## GET forumlist

Get all forum list.

### HTTP Request

`GET /forumlist`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
[
    {
        "forum_id": "9",
        "name": "Jokes & Cartoon",
        "description": "Forum yang berisi kumpulan humor dari Kaskuser, siap ngakak Gan!",
        "parent_id": "241",
        "parent_list": "9,241,-1",
        "child_list": "9,331,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "10",
        "name": "Berita dan Politik",
        "description": "Forum diskusi dan berbagi berita dari dalam maupun luar negeri. Mulai dari ideologi, politik, ekonomi, sosial dan budaya.",
        "parent_id": "241",
        "parent_list": "10,241,-1",
        "child_list": "10,250,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-10.png"
    },
    {
        "forum_id": "11",
        "name": "Movies",
        "description": "Forum penggemar film, simak info terbaru seputar dunia perfilman, serial TV, sinetron hingga miniseri favorit.",
        "parent_id": "241",
        "parent_list": "11,241,-1",
        "child_list": "11,621,619,382,171,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "13",
        "name": "Website, Webmaster, Webdeveloper",
        "description": "Tempat diskusi teknis dan review seputar website, security, blogs, CMS, webhosting, filehoster, forum, board, mail, SEO, templates, snippets\/scripts, social bookmarking, social network.",
        "parent_id": "19",
        "parent_list": "13,19,241,-1",
        "child_list": "13,443,442,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "14",
        "name": "CCPB - Shareware & Freeware",
        "description": "Tempat berbagi trik dan aplikasi.",
        "parent_id": "19",
        "parent_list": "14,19,241,-1",
        "child_list": "14,391,419,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "15",
        "name": "Disturbing Picture",
        "description": "Forum kumpulan gambar-gambar 'Disturbing Picture'.",
        "parent_id": "241",
        "parent_list": "15,241,-1",
        "child_list": "15,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "16",
        "name": "Heart to Heart",
        "description": "Forum buat yang suka nulis, nge-blog, atau bikin puisi.",
        "parent_id": "241",
        "parent_list": "16,241,-1",
        "child_list": "16,49,50,51,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "18",
        "name": "Can You Solve This Game?",
        "description": "Forum berbagi tebak-tebakan, teka-teki, dan permainan sejenis.",
        "parent_id": "241",
        "parent_list": "18,241,-1",
        "child_list": "18,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "19",
        "name": "Computer Stuff",
        "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang komputer dan internet.",
        "parent_id": "241",
        "parent_list": "19,241,-1",
        "child_list": "19,14,391,419,243,557,183,397,65,383,569,568,176,13,443,442,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "21",
        "name": "The Lounge",
        "description": "Forum bagi Kaskuser untuk berbagi gosip, gambar, foto, dan video yang seru, lucu, serta unik.",
        "parent_id": "241",
        "parent_list": "21,241,-1",
        "child_list": "21,59,186,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    {
        "forum_id": "22",
        "name": "Buat Latihan Posting",
        "description": "Tempat untuk latihan membuat thread dan menggunakan fitur-fitur posting di KASKUS.",
        "parent_id": "103",
        "parent_list": "22,103,241,-1",
        "child_list": "22,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
    },
    {
        "forum_id": "23",
        "name": "Supranatural",
        "description": "Forum bagi penggemar supranatural baik yang berangkat dari budaya maupun yang terkait dengan dunia spiritual.",
        "parent_id": "241",
        "parent_list": "23,241,-1",
        "child_list": "23,389,173,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "24",
        "name": "Lifestyle",
        "description": "Forum tentang serba serbi gaya hidup, mulai dari hal inspiratif, fashion & event terkait lifestyle.",
        "parent_id": "241",
        "parent_list": "24,241,-1",
        "child_list": "24,306,249,275,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "26",
        "name": "Anime & Manga Haven",
        "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang Anime, Manga dan Comics.",
        "parent_id": "241",
        "parent_list": "26,241,-1",
        "child_list": "26,116,431,552,433,390,122,244,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "28",
        "name": "Otomotif",
        "description": "Forum diskusi dan berbagi segala sesuatu tentang dunia otomotif, info dan tren otomotif terbaru hingga tips & trik seputar perawatan kendaraan.",
        "parent_id": "241",
        "parent_list": "28,241,-1",
        "child_list": "28,112,570,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "29",
        "name": "Cooking & Resto Guide",
        "description": "Forum bagi penggemar masak-memasak dan pemburu kuliner seru.",
        "parent_id": "241",
        "parent_list": "29,241,-1",
        "child_list": "29,62,248,60,63,61,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "30",
        "name": "BISNIS",
        "description": "Forum diskusi tentang karir, dunia kerja dan wirausaha, informasi seputar lowongan kerja, peluang kerjasama, dan investasi.",
        "parent_id": "241",
        "parent_list": "30,241,-1",
        "child_list": "30,546,277,466,279,467,470,469,468,278,472,572,571,471,280,595,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "31",
        "name": "Kritik, Saran, Pertanyaan Seputar KASKUS",
        "description": "Tempat menampung kritik, saran dan request fitur KASKUS ke Moderator forum atau Admin. Posting selain tiga kategori diatas akan dihapus.",
        "parent_id": "103",
        "parent_list": "31,103,241,-1",
        "child_list": "31,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
    },
    {
        "forum_id": "32",
        "name": "Hewan Peliharaan",
        "description": "Forum diskusi dan berbagi informasi untuk penggemar dan pemilik berbagai jenis hewan.",
        "parent_id": "241",
        "parent_list": "32,241,-1",
        "child_list": "32,124,127,123,125,126,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "33",
        "name": "Music",
        "description": "Forum bagi pencinta segala jenis musik, untuk berbagi info perkembangan musik, ulasan musik, dan ngobrolin serunya KaskusRadio.com",
        "parent_id": "241",
        "parent_list": "33,241,-1",
        "child_list": "33,88,58,137,386,87,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "34",
        "name": "All About Design",
        "description": "Forum untuk berdiskusi segala sesuatu tentang desain (desain grafis, desain website, desain interior, motion design, dsb) termasuk tutorial, tips dan trik.",
        "parent_id": "241",
        "parent_list": "34,241,-1",
        "child_list": "34,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "35",
        "name": "Sports",
        "description": "Forum bagi penggemar berbagai jenis olah raga.",
        "parent_id": "241",
        "parent_list": "35,241,-1",
        "child_list": "35,187,440,276,332,144,545,538,539,104,565,537,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "36",
        "name": "Handphone & Tablet updated",
        "description": "Forum diskusi dan berbagi seputar handphone dan PDA. Mulai dari tren terbaru, tips dan trik, komparasi produk, games dan aplikasi hingga konsultasi sebelum membeli.",
        "parent_id": "241",
        "parent_list": "36,241,-1",
        "child_list": "36,577,307,415,413,417,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "37",
        "name": "Ragnarok Online",
        "description": "Tempat bagi Massively Multiplayer Online Role-Playing Game (MMORPG) Community yang memainkan Ragnarok",
        "parent_id": "100",
        "parent_list": "37,100,44,241,-1",
        "child_list": "37,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-100.png"
    },
    {
        "forum_id": "38",
        "name": "Web-based Games",
        "description": "Tempat diskusi seputar games yang dimainkan dari web browser.",
        "parent_id": "44",
        "parent_list": "38,44,241,-1",
        "child_list": "38,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
    },
    {
        "forum_id": "39",
        "name": "Girls & Boys's Corner",
        "description": "Forum tempat nanya dan meminta pendapat soal cowok ke Agan dan soal cewek ke Aganwati.",
        "parent_id": "241",
        "parent_list": "39,241,-1",
        "child_list": "39,114,105,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "40",
        "name": "Lounge Moderator Kaskus",
        "description": "Tempat untuk diskusi dan ngobrol antara sesama Moderator (Hijau) Kaskus",
        "parent_id": "4",
        "parent_list": "40,4,-1",
        "child_list": "40,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-4.png"
    },
    {
        "forum_id": "44",
        "name": "Games",
        "description": "Forumnya penggemar berbagai jenis game.",
        "parent_id": "241",
        "parent_list": "44,241,-1",
        "child_list": "44,119,100,37,528,38,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "49",
        "name": "B-Log Collections",
        "description": "Tempat Agan dan Aganwati ngeblog di KASKUS.",
        "parent_id": "16",
        "parent_list": "49,16,241,-1",
        "child_list": "49,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-16.png"
    },
    {
        "forum_id": "50",
        "name": "Poetry",
        "description": "Tempat berbaginya para pencinta puisi.",
        "parent_id": "16",
        "parent_list": "50,16,241,-1",
        "child_list": "50,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-16.png"
    },
    {
        "forum_id": "51",
        "name": "Stories from the Heart",
        "description": "Tempat memajang cerita karya Kaskuser.",
        "parent_id": "16",
        "parent_list": "51,16,241,-1",
        "child_list": "51,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-16.png"
    },
    {
        "forum_id": "54",
        "name": "Photography",
        "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang fotografi (amatir dan pro) termasuk tutorial, tips dan trik.",
        "parent_id": "241",
        "parent_list": "54,241,-1",
        "child_list": "54,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "58",
        "name": "KaskusRadio.com",
        "description": "Ngobrolin KaskusRadio, dari DJ hingga playlist. Mau band kamu di puter di KaskusRadio? Join IndieZone - http:\/\/kaskusradio.com\/indiezone",
        "parent_id": "33",
        "parent_list": "58,33,241,-1",
        "child_list": "58,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "59",
        "name": "Gosip Nyok!",
        "description": "Tempat bergosip bareng Kaskuser.",
        "parent_id": "21",
        "parent_list": "59,21,241,-1",
        "child_list": "59,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    {
        "forum_id": "60",
        "name": "Selera Nusantara (Indonesian Food)",
        "description": "Tempat membahas kuliner khas Indonesia.",
        "parent_id": "29",
        "parent_list": "60,29,241,-1",
        "child_list": "60,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
    },
    {
        "forum_id": "61",
        "name": "The Rest of the World (International Food)",
        "description": "Tempat membahas hidangan dari berbagai penjuru dunia lainnya, termasuk kuliner western dan european.",
        "parent_id": "29",
        "parent_list": "61,29,241,-1",
        "child_list": "61,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
    },
    {
        "forum_id": "62",
        "name": "Oriental Exotic (Asian food)",
        "description": "Tempat membahas kuliner khas Asia.",
        "parent_id": "29",
        "parent_list": "62,29,241,-1",
        "child_list": "62,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
    },
    {
        "forum_id": "63",
        "name": "The KASKUS Bar",
        "description": "Tempat membahas beragam jenis minuman.",
        "parent_id": "29",
        "parent_list": "63,29,241,-1",
        "child_list": "63,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
    },
    {
        "forum_id": "65",
        "name": "Linux dan OS Selain Microsoft & Mac",
        "description": "Tempat diskusi seputar sistem operasi Unix, Linux, dan sistem operasi lainnya (selain produk Microsoft & Mac).",
        "parent_id": "19",
        "parent_list": "65,19,241,-1",
        "child_list": "65,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "66",
        "name": "Buku",
        "description": "Forum bagi pecinta buku untuk berdiskusi dan berbagi ulasan bacaan favorit, sharing koleksi buku, dan ngobrolin trend perbukuan bareng komunitas.",
        "parent_id": "241",
        "parent_list": "66,241,-1",
        "child_list": "66,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "67",
        "name": "Education",
        "description": "Forum diskusi dan berbagi pengetahuan tentang buku, sejarah, ilmu misteri dunia. Serta kumpulan aktivitas dari beragam almamater.",
        "parent_id": "241",
        "parent_list": "67,241,-1",
        "child_list": "67,247,246,597,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "70",
        "name": "Model Kit & R\/C",
        "description": "Forum bagi para penggemar model kit & radio control.",
        "parent_id": "241",
        "parent_list": "70,241,-1",
        "child_list": "70,252,253,251,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "72",
        "name": "REGIONAL",
        "description": "Kenalan dan tahu lebih jauh dengan Kaskuser dari berbagai Regional, baik dalam & luar negeri. Saling berbagi pengalaman mengenai tempat-tempat yang pernah Agan kunjungi! ",
        "parent_id": "-1",
        "parent_list": "72,-1",
        "child_list": "72,617,83,76,421,425,96,423,109,115,108,540,90,77,477,74,384,79,106,80,475,157,82,85,129,476,73,463,427,458,89,164,405,107,412,407,654,78,626,585,599,457,181,653,627,564,598,111,160,402,84,459,167,587,567,555,403,651,452,411,652,133,583,628,92,461,162,146,385,91,462,584,561,170,179,166,460,161,97,543,586,548,398,145,93,156,81,117,158,194,478,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "73",
        "name": "Indonesia",
        "description": "",
        "parent_id": "72",
        "parent_list": "73,72,-1",
        "child_list": "73,463,427,458,89,164,405,107,412,407,654,78,626,585,599,457,181,653,627,564,598,111,160,402,84,459,167,587,567,555,403,651,452,411,652,133,583,628,92,461,162,146,385,91,462,584,561,170,179,166,460,161,97,543,586,548,398,145,93,156,81,117,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "74",
        "name": "Australia",
        "description": "",
        "parent_id": "72",
        "parent_list": "74,72,-1",
        "child_list": "74,384,79,106,80,475,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "76",
        "name": "USA",
        "description": "",
        "parent_id": "617",
        "parent_list": "76,617,72,-1",
        "child_list": "76,421,425,96,423,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "77",
        "name": "Singapore",
        "description": "",
        "parent_id": "109",
        "parent_list": "77,109,72,-1",
        "child_list": "77,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "78",
        "name": "DKI Jakarta",
        "description": "",
        "parent_id": "458",
        "parent_list": "78,458,73,72,-1",
        "child_list": "78,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "79",
        "name": "Melbourne",
        "description": "",
        "parent_id": "74",
        "parent_list": "79,74,72,-1",
        "child_list": "79,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "80",
        "name": "Sydney",
        "description": "",
        "parent_id": "74",
        "parent_list": "80,74,72,-1",
        "child_list": "80,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "81",
        "name": "Palembang",
        "description": "",
        "parent_id": "460",
        "parent_list": "81,460,73,72,-1",
        "child_list": "81,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "82",
        "name": "Germany",
        "description": "",
        "parent_id": "157",
        "parent_list": "82,157,72,-1",
        "child_list": "82,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "83",
        "name": "Canada",
        "description": "",
        "parent_id": "617",
        "parent_list": "83,617,72,-1",
        "child_list": "83,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "84",
        "name": "Yogyakarta",
        "description": "",
        "parent_id": "457",
        "parent_list": "84,457,73,72,-1",
        "child_list": "84,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "85",
        "name": "Netherlands",
        "description": "",
        "parent_id": "157",
        "parent_list": "85,157,72,-1",
        "child_list": "85,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "87",
        "name": "Music Review",
        "description": "Tempat khusus bagi yang ingin mempromosikan lagu, album atau band untuk direview Kaskuser. Review murni hasil tulisan sendiri, bukan copas dari situs lain.",
        "parent_id": "33",
        "parent_list": "87,33,241,-1",
        "child_list": "87,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "88",
        "name": "Help, Tips & Tutorial",
        "description": "Tempat berbagi ilmu seputar teknik, audio processing, mixing, musical instruments, dll.",
        "parent_id": "33",
        "parent_list": "88,33,241,-1",
        "child_list": "88,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "89",
        "name": "Bandung",
        "description": "",
        "parent_id": "458",
        "parent_list": "89,458,73,72,-1",
        "child_list": "89,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "90",
        "name": "Malaysia",
        "description": "",
        "parent_id": "109",
        "parent_list": "90,109,72,-1",
        "child_list": "90,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "91",
        "name": "Kalimantan Timur",
        "description": "",
        "parent_id": "461",
        "parent_list": "91,461,73,72,-1",
        "child_list": "91,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "92",
        "name": "Surabaya",
        "description": "",
        "parent_id": "459",
        "parent_list": "92,459,73,72,-1",
        "child_list": "92,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "93",
        "name": "Medan",
        "description": "",
        "parent_id": "460",
        "parent_list": "93,460,73,72,-1",
        "child_list": "93,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "94",
        "name": "Health & Medical",
        "description": "Forum diskusi seputar dunia pengobatan, baik pengobatan modern maupun alternatif\/tradisional. Silakan bergabung untuk konsultasi atau berbagi pengalaman seputar pengobatan.",
        "parent_id": "241",
        "parent_list": "94,241,-1",
        "child_list": "94,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "96",
        "name": "East USA",
        "description": "Eastern states (formerly New York)",
        "parent_id": "76",
        "parent_list": "96,76,617,72,-1",
        "child_list": "96,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "97",
        "name": "Bangka - Belitung",
        "description": "",
        "parent_id": "460",
        "parent_list": "97,460,73,72,-1",
        "child_list": "97,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "98",
        "name": "Outdoor Adventure & Nature Clubs",
        "description": "Forum bagi pecinta alam dan kegiataan outdoor serta para petualang.",
        "parent_id": "241",
        "parent_list": "98,241,-1",
        "child_list": "98,596,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "100",
        "name": "Online Games",
        "description": "Tempat diskusi seputar games yang membutuhkan jaringan komputer dan internet.",
        "parent_id": "44",
        "parent_list": "100,44,241,-1",
        "child_list": "100,37,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
    },
    {
        "forum_id": "103",
        "name": "Welcome to KASKUS",
        "description": "Forum untuk tahu dan mengulik lebih banyak tentang KASKUS.",
        "parent_id": "241",
        "parent_list": "103,241,-1",
        "child_list": "103,22,177,31,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "104",
        "name": "Soccer & Futsal Room",
        "description": "Ruang untuk para pecinta sepakbola dan futsal dan fans klub dari dalam dan luar negeri berkumpul, berdiskusi dan berbagi informasi.",
        "parent_id": "35",
        "parent_list": "104,35,241,-1",
        "child_list": "104,565,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "105",
        "name": "Ask da Girls",
        "description": "Apa kata Aganwati?",
        "parent_id": "39",
        "parent_list": "105,39,241,-1",
        "child_list": "105,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-39.png"
    },
    {
        "forum_id": "106",
        "name": "Perth",
        "description": "",
        "parent_id": "74",
        "parent_list": "106,74,72,-1",
        "child_list": "106,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "107",
        "name": "Bogor",
        "description": "",
        "parent_id": "458",
        "parent_list": "107,458,73,72,-1",
        "child_list": "107,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "108",
        "name": "Japan",
        "description": "",
        "parent_id": "109",
        "parent_list": "108,109,72,-1",
        "child_list": "108,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "109",
        "name": "Asia",
        "description": "",
        "parent_id": "72",
        "parent_list": "109,72,-1",
        "child_list": "109,115,108,540,90,77,477,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "111",
        "name": "Semarang",
        "description": "",
        "parent_id": "457",
        "parent_list": "111,457,73,72,-1",
        "child_list": "111,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "112",
        "name": "Kendaraan Roda 2",
        "description": "Tempat membahas kendaraan beroda dua (motor) dari segala brand (merek)",
        "parent_id": "28",
        "parent_list": "112,28,241,-1",
        "child_list": "112,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-28.png"
    },
    {
        "forum_id": "113",
        "name": "English",
        "description": "Forum untuk membahas dan mempelajari Bahasa Inggris.",
        "parent_id": "241",
        "parent_list": "113,241,-1",
        "child_list": "113,464,465,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "114",
        "name": "Ask da Boys",
        "description": "Apa kata Agan?",
        "parent_id": "39",
        "parent_list": "114,39,241,-1",
        "child_list": "114,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-39.png"
    },
    {
        "forum_id": "115",
        "name": "China",
        "description": "",
        "parent_id": "109",
        "parent_list": "115,109,72,-1",
        "child_list": "115,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "116",
        "name": "AMHelpdesk",
        "description": "Portal info, bantuan dan tutorial seputar Anime dan Manga.",
        "parent_id": "26",
        "parent_list": "116,26,241,-1",
        "child_list": "116,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
    },
    {
        "forum_id": "117",
        "name": "Riau Raya",
        "description": "",
        "parent_id": "460",
        "parent_list": "117,460,73,72,-1",
        "child_list": "117,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "119",
        "name": "Console & Handheld Games",
        "description": "Tempat diskusi seputar games yang dimainkan di console dan handheld. Termasuk Xbox, Xbox 360, PS2, PS3, GameCube, GBA\/DS, Gizmondo, N-Gage & PSP.",
        "parent_id": "44",
        "parent_list": "119,44,241,-1",
        "child_list": "119,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
    },
    {
        "forum_id": "122",
        "name": "Western Comic",
        "description": "Tempat untuk diskusi komik Western\/US",
        "parent_id": "26",
        "parent_list": "122,26,241,-1",
        "child_list": "122,244,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
    },
    {
        "forum_id": "123",
        "name": "Mamalia",
        "description": "Tempat untuk membahas binatang mamalia seperti anjing, kucing, hamster, macan, beruang, tupai, dsb.",
        "parent_id": "32",
        "parent_list": "123,32,241,-1",
        "child_list": "123,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "124",
        "name": "Burung",
        "description": "Tempat untuk membahas berbagai jenis unggas dan burung.",
        "parent_id": "32",
        "parent_list": "124,32,241,-1",
        "child_list": "124,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "125",
        "name": "Reptil",
        "description": "Tempat untuk membahas berbagai jenis reptil.",
        "parent_id": "32",
        "parent_list": "125,32,241,-1",
        "child_list": "125,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "126",
        "name": "Saltwater Fish",
        "description": "Tempat untuk membahas berbagai ikan laut.",
        "parent_id": "32",
        "parent_list": "126,32,241,-1",
        "child_list": "126,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "127",
        "name": "Freshwater Fish",
        "description": "Tempat untuk membahas ikan air tawar.",
        "parent_id": "32",
        "parent_list": "127,32,241,-1",
        "child_list": "127,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "129",
        "name": "United Kingdom",
        "description": "",
        "parent_id": "157",
        "parent_list": "129,157,72,-1",
        "child_list": "129,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "133",
        "name": "Malang",
        "description": "",
        "parent_id": "459",
        "parent_list": "133,459,73,72,-1",
        "child_list": "133,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "137",
        "name": "Music Corner",
        "description": "Tempat berbagi dan membahas MP3, lirik, video klip  karya musik solo dan band pribadi.",
        "parent_id": "33",
        "parent_list": "137,33,241,-1",
        "child_list": "137,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "140",
        "name": "Militer",
        "description": "Tempat diskusi tentang teknologi alat-alat militer, strategi, serta sejarah kemiliteran, di dalam maupun luar negeri.",
        "parent_id": "575",
        "parent_list": "140,575,241,-1",
        "child_list": "140,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-575.png"
    },
    {
        "forum_id": "144",
        "name": "Martial Arts",
        "description": "Tempat diskusi para praktisi beladiri tentang ilmu beladiri, tangan kosong mapun bersenjata, dari dalam dan luar negeri, baik modern dan tradisional.",
        "parent_id": "35",
        "parent_list": "144,35,241,-1",
        "child_list": "144,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "145",
        "name": "Lampung",
        "description": "",
        "parent_id": "460",
        "parent_list": "145,460,73,72,-1",
        "child_list": "145,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "146",
        "name": "Kalimantan Selatan",
        "description": "",
        "parent_id": "461",
        "parent_list": "146,461,73,72,-1",
        "child_list": "146,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "151",
        "name": "Gratisan",
        "description": "Aneka promo gratis",
        "parent_id": "25",
        "parent_list": "151,25,-1",
        "child_list": "151,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "156",
        "name": "Minangkabau",
        "description": "",
        "parent_id": "460",
        "parent_list": "156,460,73,72,-1",
        "child_list": "156,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "157",
        "name": "Europe",
        "description": "",
        "parent_id": "72",
        "parent_list": "157,72,-1",
        "child_list": "157,82,85,129,476,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "158",
        "name": "Regional Lainnya",
        "description": "",
        "parent_id": "72",
        "parent_list": "158,72,-1",
        "child_list": "158,194,478,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "160",
        "name": "Solo",
        "description": "",
        "parent_id": "457",
        "parent_list": "160,457,73,72,-1",
        "child_list": "160,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "161",
        "name": "Aceh",
        "description": "",
        "parent_id": "460",
        "parent_list": "161,460,73,72,-1",
        "child_list": "161,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "162",
        "name": "Kalimantan Barat",
        "description": "",
        "parent_id": "461",
        "parent_list": "162,461,73,72,-1",
        "child_list": "162,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "164",
        "name": "Banten",
        "description": "",
        "parent_id": "458",
        "parent_list": "164,458,73,72,-1",
        "child_list": "164,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "166",
        "name": "Palu",
        "description": "",
        "parent_id": "462",
        "parent_list": "166,462,73,72,-1",
        "child_list": "166,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "167",
        "name": "Bali",
        "description": "",
        "parent_id": "459",
        "parent_list": "167,459,73,72,-1",
        "child_list": "167,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "170",
        "name": "Makassar",
        "description": "",
        "parent_id": "462",
        "parent_list": "170,462,73,72,-1",
        "child_list": "170,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "171",
        "name": "TV",
        "description": "Forum untuk membahas segala jenis acara TV dari sinetron, mini series, dan lain lain.",
        "parent_id": "11",
        "parent_list": "171,11,241,-1",
        "child_list": "171,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-11.png"
    },
    {
        "forum_id": "173",
        "name": "Spiritual",
        "description": "Tempat membahas hal spiritual seperti meditasi, teknik relaksasi, dan pencerahan (tidak termasuk ilmu pelet, pengasihan, santet, dan penampakan makhluk halus).",
        "parent_id": "23",
        "parent_list": "173,23,241,-1",
        "child_list": "173,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-23.png"
    },
    {
        "forum_id": "176",
        "name": "Programmer Forum",
        "description": "Tempat diskusi dan belajar bahasa programming, dari pemula hingga pakar.",
        "parent_id": "19",
        "parent_list": "176,19,241,-1",
        "child_list": "176,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "177",
        "name": "Donatur Lounge",
        "description": "Tempat khusus untuk para KASKUS Donatur. Postingan hanya dapat dilihat oleh donatur.",
        "parent_id": "103",
        "parent_list": "177,103,241,-1",
        "child_list": "177,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
    },
    {
        "forum_id": "179",
        "name": "Manado",
        "description": "",
        "parent_id": "462",
        "parent_list": "179,462,73,72,-1",
        "child_list": "179,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "181",
        "name": "Banyumas",
        "description": "",
        "parent_id": "457",
        "parent_list": "181,457,73,72,-1",
        "child_list": "181,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "183",
        "name": "Internet Service & Networking",
        "description": "Tempat membahas internet service provider dan networking (hardware & tutorial).",
        "parent_id": "19",
        "parent_list": "183,19,241,-1",
        "child_list": "183,397,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "186",
        "name": "Lounge Pictures & Video",
        "description": "Tempat berbagi kumpulan gambar menarik, seru, lucu, dan unik.",
        "parent_id": "21",
        "parent_list": "186,21,241,-1",
        "child_list": "186,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    {
        "forum_id": "187",
        "name": "Airsoft Indonesia",
        "description": "Tempat diskusi para pecinta airsoft.",
        "parent_id": "35",
        "parent_list": "187,35,241,-1",
        "child_list": "187,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "188",
        "name": "Surat Pembaca",
        "description": "Tempat berbagi keluh kesah seputar pelayanan publik atau produk tertentu secara bertanggung jawab, dengan memberi masukan untuk pelayanan yang lebih baik (bukan untuk menjatuhkan kredibilitas).",
        "parent_id": "241",
        "parent_list": "188,241,-1",
        "child_list": "188,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "191",
        "name": "Debate Club",
        "description": "Forum berbagi dan menyatakan perbedaan pendapat dan pandangan",
        "parent_id": "241",
        "parent_list": "191,241,-1",
        "child_list": "191,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "192",
        "name": "Tanaman",
        "description": "Forum diskusi dan berbagi informasi untuk penggemar tanaman atau tumbuhan.",
        "parent_id": "241",
        "parent_list": "192,241,-1",
        "child_list": "192,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "193",
        "name": "Wedding & Family",
        "description": "Forum diskusi dan berbagi informasi seputar pernikahan, keluarga & anak.",
        "parent_id": "241",
        "parent_list": "193,241,-1",
        "child_list": "193,429,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "194",
        "name": "Timur Tengah",
        "description": "",
        "parent_id": "158",
        "parent_list": "194,158,72,-1",
        "child_list": "194,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "195",
        "name": "Elektronik",
        "description": "Jual beli beragam jenis barang elektronik",
        "parent_id": "25",
        "parent_list": "195,25,-1",
        "child_list": "195,313,255,254,212,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "196",
        "name": "Fashion & Mode",
        "description": "Jual beli barang fashion untuk pria dan wanita",
        "parent_id": "25",
        "parent_list": "196,25,-1",
        "child_list": "196,216,451,450,302,449,624,600,215,257,310,311,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "197",
        "name": "Flora & Fauna",
        "description": "Jual beli tanaman hias dan hewan peliharaan (kecuali yang dilindungi)",
        "parent_id": "25",
        "parent_list": "197,25,-1",
        "child_list": "197,218,219,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "198",
        "name": "Koleksi, Hobi & Mainan",
        "description": "Jual beli barang koleksi, hobi dan mainan",
        "parent_id": "25",
        "parent_list": "198,25,-1",
        "child_list": "198,261,231,262,444,606,233,291,590,292,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "199",
        "name": "Properti",
        "description": "Jual beli properti",
        "parent_id": "25",
        "parent_list": "199,25,-1",
        "child_list": "199,223,225,222,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "200",
        "name": "CD & DVD",
        "description": "Jual beli CD\/DVD",
        "parent_id": "25",
        "parent_list": "200,25,-1",
        "child_list": "200,266,265,329,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "201",
        "name": "Makanan & Minuman",
        "description": "Jual beli aneka makanan dan minuman (HARUS halal)",
        "parent_id": "25",
        "parent_list": "201,25,-1",
        "child_list": "201,228,607,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "202",
        "name": "Jasa",
        "description": "Penawaran aneka jasa",
        "parent_id": "25",
        "parent_list": "202,25,-1",
        "child_list": "202,269,268,553,631,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "204",
        "name": "FJB Feedback & Testimonials",
        "description": "Sebelum posting, silakan cek petunjuk, tips, tutorial dari Kaskuser",
        "parent_id": "25",
        "parent_list": "204,25,-1",
        "child_list": "204,270,566,271,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "205",
        "name": "Otomotif",
        "description": "Jual beli mobil\/motor, aksesoris dan suku cadang",
        "parent_id": "25",
        "parent_list": "205,25,-1",
        "child_list": "205,333,334,206,207,208,256,209,593,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "206",
        "name": "Audio, Video",
        "description": "Khusus Audio, Video untuk mobil (tape, tv head unit, dll)",
        "parent_id": "205",
        "parent_list": "206,205,25,-1",
        "child_list": "206,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
    },
    {
        "forum_id": "207",
        "name": "Interior, Exterior",
        "description": "Khusus interior, exterior",
        "parent_id": "205",
        "parent_list": "207,205,25,-1",
        "child_list": "207,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
    },
    {
        "forum_id": "208",
        "name": "Mobil",
        "description": "Aneka merk mobil",
        "parent_id": "205",
        "parent_list": "208,205,25,-1",
        "child_list": "208,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
    },
    {
        "forum_id": "209",
        "name": "Motor",
        "description": "Aneka merk motor",
        "parent_id": "205",
        "parent_list": "209,205,25,-1",
        "child_list": "209,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
    },
    {
        "forum_id": "210",
        "name": "Handphone & Tablet updated",
        "description": "Jual beli Handphone dan PDA",
        "parent_id": "25",
        "parent_list": "210,25,-1",
        "child_list": "210,527,574,381,573,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "212",
        "name": "Tablet dan Aksesoris",
        "description": "Tempat untuk berjualan Tablet (iPad, Tab, Kindle, Playbook dll)",
        "parent_id": "195",
        "parent_list": "212,195,25,-1",
        "child_list": "212,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-195.png"
    },
    {
        "forum_id": "215",
        "name": "Produk Distro",
        "description": "Barang fashion khusus produk\/merk sendiri",
        "parent_id": "196",
        "parent_list": "215,196,25,-1",
        "child_list": "215,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "216",
        "name": "Aksesoris",
        "description": "Ikat pinggang, dasi dan topi",
        "parent_id": "196",
        "parent_list": "216,196,25,-1",
        "child_list": "216,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "218",
        "name": "Flora (Tumbuhan)",
        "description": "Tanaman hias (dilarang berjualan tanaman\/ tumbuhan dilindungi)",
        "parent_id": "197",
        "parent_list": "218,197,25,-1",
        "child_list": "218,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-197.png"
    },
    {
        "forum_id": "219",
        "name": "Fauna (Hewan)",
        "description": "Hewan peliharaan (dilarang berjualan hewan dilindungi)",
        "parent_id": "197",
        "parent_list": "219,197,25,-1",
        "child_list": "219,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-197.png"
    },
    {
        "forum_id": "220",
        "name": "Alat-Alat Olahraga",
        "description": "Jual beli pakaian, sepatu dan perlengkapan olahraga",
        "parent_id": "25",
        "parent_list": "220,25,-1",
        "child_list": "220,589,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "221",
        "name": "Alat-Alat Musik",
        "description": "Jual beli alat musik dan perlengkapan studio",
        "parent_id": "25",
        "parent_list": "221,25,-1",
        "child_list": "221,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "222",
        "name": "Tanah",
        "description": "Khusus tanah beragam lokasi",
        "parent_id": "199",
        "parent_list": "222,199,25,-1",
        "child_list": "222,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-199.png"
    },
    {
        "forum_id": "223",
        "name": "Rumah",
        "description": "Khusus rumah beragam lokasi",
        "parent_id": "199",
        "parent_list": "223,199,25,-1",
        "child_list": "223,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-199.png"
    },
    {
        "forum_id": "225",
        "name": "Sewa Menyewa",
        "description": "Khusus sewa menyewa properti",
        "parent_id": "199",
        "parent_list": "225,199,25,-1",
        "child_list": "225,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-199.png"
    },
    {
        "forum_id": "227",
        "name": "Buku",
        "description": "Jual beli beragam jenis buku",
        "parent_id": "25",
        "parent_list": "227,25,-1",
        "child_list": "227,264,625,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "228",
        "name": "Makanan",
        "description": "Khusus aneka makanan (HARUS halal)",
        "parent_id": "201",
        "parent_list": "228,201,25,-1",
        "child_list": "228,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-201.png"
    },
    {
        "forum_id": "229",
        "name": "Obat-obatan",
        "description": "Jual beli segala jenis obat-obatan (HARUS aman dikonsumsi konsumen)",
        "parent_id": "25",
        "parent_list": "229,25,-1",
        "child_list": "229,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "231",
        "name": "Airsoft",
        "description": "Khusus airsoft",
        "parent_id": "198",
        "parent_list": "231,198,25,-1",
        "child_list": "231,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "233",
        "name": "Model Kit",
        "description": "Khusus model kit (lihat aturan main sebelum transaksi)",
        "parent_id": "198",
        "parent_list": "233,198,25,-1",
        "child_list": "233,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "234",
        "name": "Arsitektur",
        "description": "Tempat diskusi seputar arsitektur, baik keilmuan maupun terapan, termasuk cara membangun dan mendesain rumah.",
        "parent_id": "578",
        "parent_list": "234,578,241,-1",
        "child_list": "234,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-578.png"
    },
    {
        "forum_id": "235",
        "name": "Travellers",
        "description": "Forum diskusi para penggemar jalan-jalan. Tempat berbagi ulasan tempat wisata dan tips berwisata.",
        "parent_id": "241",
        "parent_list": "235,241,-1",
        "child_list": "235,437,439,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "236",
        "name": "Fitness & Muscle Building",
        "description": "Tempat diskusi dan berbagi cara meningkatkan massa, kekuatan, performa dan kekencangan otot dari tingkat pemula, lanjutan, dan tingkat atlet untuk body fitness.",
        "parent_id": "558",
        "parent_list": "236,558,241,-1",
        "child_list": "236,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
    },
    {
        "forum_id": "240",
        "name": "KASKUS Peduli",
        "description": "Forum berisi informasi mengenai berbagai kegiatan bakti sosial yang diselenggarakan oleh KASKUS bersama dengan Kaskuser.",
        "parent_id": "239",
        "parent_list": "240,239,-1",
        "child_list": "240,549,473,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
    },
    {
        "forum_id": "241",
        "name": "HOME FORUM",
        "description": "Apapun hobi dan kegemaran Agan, bisa ditemukan disini! Ayo gabung di komunitas terbesar di Indonesia, mulai sharing dan berdiskusi  dengan Kaskuser lainnya!",
        "parent_id": "-1",
        "parent_list": "241,-1",
        "child_list": "241,633,634,636,637,638,639,640,641,642,643,644,645,646,647,648,649,650,635,34,26,116,431,552,433,390,122,244,10,250,30,546,277,466,279,467,470,469,468,278,472,572,571,471,280,595,66,18,19,14,391,419,243,557,183,397,65,383,569,568,176,13,443,442,29,62,248,60,63,61,191,15,67,247,246,597,113,464,465,474,558,274,236,559,281,282,44,119,100,37,528,38,39,114,105,630,36,577,307,415,413,417,94,16,49,50,51,32,124,127,123,125,126,392,591,581,395,393,580,394,387,388,9,331,24,306,249,275,594,575,576,140,491,70,252,253,251,11,621,619,382,171,33,88,58,137,386,87,541,28,112,570,98,596,620,54,35,187,440,276,332,144,545,538,539,104,565,537,23,389,173,188,192,578,234,579,21,59,186,235,437,439,193,429,103,22,177,31,544,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image--1.png"
    },
    {
        "forum_id": "243",
        "name": "Hardware Computer",
        "description": "Tempat diskusi computer hardware: updates, problems, drivers, peripheral, performance, upgrade, overclocking, showcase, dan konsultasi.",
        "parent_id": "19",
        "parent_list": "243,19,241,-1",
        "child_list": "243,557,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "244",
        "name": "Latest Release",
        "description": "Tempat berbagi dan kumpulan informasi rilis terbaru.",
        "parent_id": "122",
        "parent_list": "244,122,26,241,-1",
        "child_list": "244,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-122.png"
    },
    {
        "forum_id": "246",
        "name": "Sejarah & Xenology",
        "description": "Tempat membahas sejarah\/biografi tokoh dalam dan luar negeri. Juga diskusi tentang xenology (ilmu yang membahas misteri-misteri dunia).",
        "parent_id": "67",
        "parent_list": "246,67,241,-1",
        "child_list": "246,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-67.png"
    },
    {
        "forum_id": "247",
        "name": "Civitas Academica",
        "description": "Tempat kumpul alumni dan siswa dari beragam almamater. Saling berbagi info lowongan kerja, acara reuni, dan kondisi terbaru sekolah atau universitas.",
        "parent_id": "67",
        "parent_list": "247,67,241,-1",
        "child_list": "247,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-67.png"
    },
    {
        "forum_id": "248",
        "name": "Restaurant Review",
        "description": "Tempat berbagi pengalaman makan dan ulasan seputar resto (menu, tempat, promo).",
        "parent_id": "29",
        "parent_list": "248,29,241,-1",
        "child_list": "248,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
    },
    {
        "forum_id": "249",
        "name": "Inspirasi",
        "description": "Berbagi tips dan masukan inspirasional, serta motivasi dari dan untuk Kaskuser.",
        "parent_id": "24",
        "parent_list": "249,24,241,-1",
        "child_list": "249,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-24.png"
    },
    {
        "forum_id": "250",
        "name": "Berita Luar Negeri",
        "description": "Tempat diskusi mengenai berita dari luar negeri.",
        "parent_id": "10",
        "parent_list": "250,10,241,-1",
        "child_list": "250,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-10.png"
    },
    {
        "forum_id": "251",
        "name": "Plamo",
        "description": "Tempat berbagi info tentang plastic model kit, dari mobil, military sampai Gundam.",
        "parent_id": "70",
        "parent_list": "251,70,241,-1",
        "child_list": "251,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-70.png"
    },
    {
        "forum_id": "252",
        "name": "Figures",
        "description": "Tempat berbagi segala sesuatu tentang figures baik resin, die-cast, gashapon maupun poseable action figures.",
        "parent_id": "70",
        "parent_list": "252,70,241,-1",
        "child_list": "252,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-70.png"
    },
    {
        "forum_id": "253",
        "name": "Gallery & Tutorial",
        "description": "Tempat berbagi tutorial dan gallery baik yang sudah selesai maupun work in progress (WIP).",
        "parent_id": "70",
        "parent_list": "253,70,241,-1",
        "child_list": "253,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-70.png"
    },
    {
        "forum_id": "254",
        "name": "TV, LCD & Projector",
        "description": "TV, LCD & Projector",
        "parent_id": "195",
        "parent_list": "254,195,25,-1",
        "child_list": "254,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-195.png"
    },
    {
        "forum_id": "255",
        "name": "Home Theatre, Sound System",
        "description": "Home Theater & Sound",
        "parent_id": "195",
        "parent_list": "255,195,25,-1",
        "child_list": "255,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-195.png"
    },
    {
        "forum_id": "256",
        "name": "Mobil & Motor Antik",
        "description": "Aneka mobil\/motor antik",
        "parent_id": "205",
        "parent_list": "256,205,25,-1",
        "child_list": "256,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
    },
    {
        "forum_id": "257",
        "name": "Sepatu, Sandal",
        "description": "Sepatu dan sandal beragam merk",
        "parent_id": "196",
        "parent_list": "257,196,25,-1",
        "child_list": "257,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "261",
        "name": "Action Figures",
        "description": "Khusus action figures",
        "parent_id": "198",
        "parent_list": "261,198,25,-1",
        "child_list": "261,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "262",
        "name": "Cards",
        "description": "Koleksi kartu",
        "parent_id": "198",
        "parent_list": "262,198,25,-1",
        "child_list": "262,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "263",
        "name": "KASKUS Celeb",
        "description": "Forum untuk membahas kumpulan celebrities yang Ngaskus.",
        "parent_id": "239",
        "parent_list": "263,239,-1",
        "child_list": "263,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
    },
    {
        "forum_id": "264",
        "name": "Buku Pelajaran",
        "description": "Buku pelajaran SD, SMP, SMA dan Kuliah",
        "parent_id": "227",
        "parent_list": "264,227,25,-1",
        "child_list": "264,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-227.png"
    },
    {
        "forum_id": "265",
        "name": "Film",
        "description": "CD\/DVD (film, blueray dan hd-dvd)",
        "parent_id": "200",
        "parent_list": "265,200,25,-1",
        "child_list": "265,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-200.png"
    },
    {
        "forum_id": "266",
        "name": "Audio",
        "description": "CD\/DVD (musik)",
        "parent_id": "200",
        "parent_list": "266,200,25,-1",
        "child_list": "266,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-200.png"
    },
    {
        "forum_id": "268",
        "name": "Jasa Rumah Tangga",
        "description": "Jasa kebutuhan rumah tangga",
        "parent_id": "202",
        "parent_list": "268,202,25,-1",
        "child_list": "268,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-202.png"
    },
    {
        "forum_id": "269",
        "name": "Fotografi",
        "description": "Jasa fotografi",
        "parent_id": "202",
        "parent_list": "269,202,25,-1",
        "child_list": "269,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-202.png"
    },
    {
        "forum_id": "270",
        "name": "Blacklist",
        "description": "Daftar hitam Kaskuser nakal",
        "parent_id": "204",
        "parent_list": "270,204,25,-1",
        "child_list": "270,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-204.png"
    },
    {
        "forum_id": "271",
        "name": "Official Testimonials",
        "description": "Kirimkan pengalaman \/ testimonial anda berjualan atau berinteraksi di forum Kaskus yang mengubah hidup anda. Testimonial yang terpilih akan kami cantumkan di category ini. Kirim ke testimonial@kaskusnetworks.com",
        "parent_id": "204",
        "parent_list": "271,204,25,-1",
        "child_list": "271,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-204.png"
    },
    {
        "forum_id": "272",
        "name": "FJB Tips & Tutorial",
        "description": "Kumpulan tips dan tutorial seputar Forum Jual Beli Kaskus",
        "parent_id": "25",
        "parent_list": "272,25,-1",
        "child_list": "272,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "273",
        "name": "Product Review",
        "description": "Ulasan seputar produk",
        "parent_id": "25",
        "parent_list": "273,25,-1",
        "child_list": "273,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "274",
        "name": "Fat-loss, Diet & Nutrition",
        "description": "Tempat diskusi tentang kandungan nutrisi dalam makanan, cara sehat turun berat badan, dan solusi mencegah kolesterol, diabetes, dan penyakit lainnya.",
        "parent_id": "558",
        "parent_list": "274,558,241,-1",
        "child_list": "274,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
    },
    {
        "forum_id": "275",
        "name": "Nightlife & Events",
        "description": "Tempat berbagi informasi mengenai event dan promosi yang terkait dengan lifestyle.",
        "parent_id": "24",
        "parent_list": "275,24,241,-1",
        "child_list": "275,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-24.png"
    },
    {
        "forum_id": "276",
        "name": "Grappling",
        "description": "Tempat berkumpulnya para pecinta olahraga grappling. ",
        "parent_id": "35",
        "parent_list": "276,35,241,-1",
        "child_list": "276,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "277",
        "name": "Entrepreneur Corner",
        "description": "Tempat diskusi seputar dunia wirausaha. Dilarang promosi disini.",
        "parent_id": "30",
        "parent_list": "277,30,241,-1",
        "child_list": "277,466,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "278",
        "name": "Lowongan Kerja",
        "description": "Tempat kumpulan informasi mengenai lowongan pekerjaan.",
        "parent_id": "30",
        "parent_list": "278,30,241,-1",
        "child_list": "278,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "279",
        "name": "Forex, Option, Saham, & Derivatifnya",
        "description": "Tempat berbagi dan belajar teknikal, fundamental dan psikologi trade forex, option, saham dan derivatifnya.",
        "parent_id": "30",
        "parent_list": "279,30,241,-1",
        "child_list": "279,467,470,469,468,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "280",
        "name": "HYIP \/ Money Game \/ PTC \/ Autosurf",
        "description": "",
        "parent_id": "471",
        "parent_list": "280,471,30,241,-1",
        "child_list": "280,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-471.png"
    },
    {
        "forum_id": "281",
        "name": "Gadget & Gizmo",
        "description": "Forum diskusi dan berbagi informasi seputar gadget, tren dan perkembangan gadget terbaru, hingga ulasan tentang gadget tertentu.",
        "parent_id": "241",
        "parent_list": "281,241,-1",
        "child_list": "281,282,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "282",
        "name": "Audio & Video",
        "description": "Tempat khusus membahas peralatan audio dan video",
        "parent_id": "281",
        "parent_list": "282,281,241,-1",
        "child_list": "282,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-281.png"
    },
    {
        "forum_id": "283",
        "name": "Antik",
        "description": "Jual beli benda menarik, kuno dan unik",
        "parent_id": "25",
        "parent_list": "283,25,-1",
        "child_list": "283,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "284",
        "name": "Karya Seni & Desain",
        "description": "Jual beli barang seni dan penawaran jasa desain",
        "parent_id": "25",
        "parent_list": "284,25,-1",
        "child_list": "284,603,285,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "285",
        "name": "Lukisan",
        "description": "Beragam lukisan",
        "parent_id": "284",
        "parent_list": "285,284,25,-1",
        "child_list": "285,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-284.png"
    },
    {
        "forum_id": "286",
        "name": "Industri & Supplier",
        "description": "Jual beli barang & bahan baku industri",
        "parent_id": "25",
        "parent_list": "286,25,-1",
        "child_list": "286,287,448,288,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "287",
        "name": "Alat Berat",
        "description": "Mesin pabrik\/ industri.",
        "parent_id": "286",
        "parent_list": "287,286,25,-1",
        "child_list": "287,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-286.png"
    },
    {
        "forum_id": "288",
        "name": "Peralatan Food & Beverage",
        "description": "Alat masak\/industri katering",
        "parent_id": "286",
        "parent_list": "288,286,25,-1",
        "child_list": "288,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-286.png"
    },
    {
        "forum_id": "291",
        "name": "Perangko",
        "description": "Khusus perangko",
        "parent_id": "198",
        "parent_list": "291,198,25,-1",
        "child_list": "291,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "292",
        "name": "Uang Lama",
        "description": "Khusus uang lama (koin, uang kertas)",
        "parent_id": "198",
        "parent_list": "292,198,25,-1",
        "child_list": "292,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "293",
        "name": "Kamera & Aksesoris",
        "description": "Jual beli kamera dan aksesoris",
        "parent_id": "25",
        "parent_list": "293,25,-1",
        "child_list": "293,604,605,294,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "294",
        "name": "Kamera Video",
        "description": "Kamera video beragam merk",
        "parent_id": "293",
        "parent_list": "294,293,25,-1",
        "child_list": "294,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-293.png"
    },
    {
        "forum_id": "295",
        "name": "Perawatan Tubuh & Wajah",
        "description": "Jual beli aneka produk kesehatan dan kecantikan",
        "parent_id": "25",
        "parent_list": "295,25,-1",
        "child_list": "295,608,609,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "296",
        "name": "Furniture",
        "description": "Jual beli mebel (kursi, meja, lemari dsb)",
        "parent_id": "25",
        "parent_list": "296,25,-1",
        "child_list": "296,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "297",
        "name": "Video Games",
        "description": "Jual beli games dan konsol",
        "parent_id": "25",
        "parent_list": "297,25,-1",
        "child_list": "297,612,613,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "298",
        "name": "Perkakas",
        "description": "Jual beli aneka perkakas",
        "parent_id": "25",
        "parent_list": "298,25,-1",
        "child_list": "298,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "299",
        "name": "Kerajinan Tangan",
        "description": "Jual beli aneka kerajinan tangan",
        "parent_id": "25",
        "parent_list": "299,25,-1",
        "child_list": "299,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "300",
        "name": "Perlengkapan Kantor",
        "description": "Jual beli perlengkapan kantor",
        "parent_id": "25",
        "parent_list": "300,25,-1",
        "child_list": "300,312,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "302",
        "name": "Jam Tangan",
        "description": "Jam tangan",
        "parent_id": "196",
        "parent_list": "302,196,25,-1",
        "child_list": "302,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "303",
        "name": "Perlengkapan Rumah Tangga",
        "description": "Jual beli perlengkapan rumah tangga (sub kategori terkait, cek elektronik rumah tangga)",
        "parent_id": "25",
        "parent_list": "303,25,-1",
        "child_list": "303,314,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "304",
        "name": "Tur & Paket Perjalanan",
        "description": "Penawaran aneka tur dan paket wisata",
        "parent_id": "25",
        "parent_list": "304,25,-1",
        "child_list": "304,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "305",
        "name": "Perlengkapan Anak & Bayi",
        "description": "Jual beli pakaian, perlengkapan bayi dan anak-anak",
        "parent_id": "25",
        "parent_list": "305,25,-1",
        "child_list": "305,447,446,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "306",
        "name": "Fashion",
        "description": "Tempat diskusi dan membahas tren fashion, serta update informasi fashion terkini.",
        "parent_id": "24",
        "parent_list": "306,24,241,-1",
        "child_list": "306,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-24.png"
    },
    {
        "forum_id": "307",
        "name": "BlackBerry Corner",
        "description": "Diskusi khusus mengenai Blackberry",
        "parent_id": "36",
        "parent_list": "307,36,241,-1",
        "child_list": "307,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
    },
    {
        "forum_id": "310",
        "name": "Tas, Dompet",
        "description": "Tas, dompet dan clutch beragam merk",
        "parent_id": "196",
        "parent_list": "310,196,25,-1",
        "child_list": "310,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "311",
        "name": "Tradisional",
        "description": "Pakaian dan kain tradisional (batik, songket, kebaya dsb)",
        "parent_id": "196",
        "parent_list": "311,196,25,-1",
        "child_list": "311,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "312",
        "name": "Stationery",
        "description": "Alat tulis, kertas dsb",
        "parent_id": "300",
        "parent_list": "312,300,25,-1",
        "child_list": "312,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-300.png"
    },
    {
        "forum_id": "313",
        "name": "Elektronik Rumah Tangga",
        "description": "Kebutuhan rumah tangga (Kulkas, Mesin Cuci, Pompa dsb)",
        "parent_id": "195",
        "parent_list": "313,195,25,-1",
        "child_list": "313,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-195.png"
    },
    {
        "forum_id": "314",
        "name": "Pecah Belah & Alat Makan",
        "description": "Khusus pecah belah, alat makan",
        "parent_id": "303",
        "parent_list": "314,303,25,-1",
        "child_list": "314,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-303.png"
    },
    {
        "forum_id": "316",
        "name": "Tiket",
        "description": "Jual beli tiket",
        "parent_id": "25",
        "parent_list": "316,25,-1",
        "child_list": "316,610,611,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "317",
        "name": "Komputer",
        "description": "Jual beli komputer (hardware, software)",
        "parent_id": "25",
        "parent_list": "317,25,-1",
        "child_list": "317,330,328,318,323,327,321,324,325,319,326,320,322,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "318",
        "name": "Desktop",
        "description": "Khusus desktop",
        "parent_id": "317",
        "parent_list": "318,317,25,-1",
        "child_list": "318,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "319",
        "name": "Notebook, Laptop",
        "description": "Khusus Notebook, Laptop",
        "parent_id": "317",
        "parent_list": "319,317,25,-1",
        "child_list": "319,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "320",
        "name": "Processors  & Motherboards",
        "description": "Khusus Processors, Motherboards",
        "parent_id": "317",
        "parent_list": "320,317,25,-1",
        "child_list": "320,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "321",
        "name": "Memory",
        "description": "Khusus Memory",
        "parent_id": "317",
        "parent_list": "321,317,25,-1",
        "child_list": "321,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "322",
        "name": "Sound, Graphics & Video Cards",
        "description": "Khusus sound, graphics & videocards",
        "parent_id": "317",
        "parent_list": "322,317,25,-1",
        "child_list": "322,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "323",
        "name": "Drives & Storage",
        "description": "Khusus Drives & Storage",
        "parent_id": "317",
        "parent_list": "323,317,25,-1",
        "child_list": "323,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "324",
        "name": "Monitor, Display",
        "description": "Khusus monitor, display",
        "parent_id": "317",
        "parent_list": "324,317,25,-1",
        "child_list": "324,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "325",
        "name": "Networking, Communications",
        "description": "Khusus networking, communications",
        "parent_id": "317",
        "parent_list": "325,317,25,-1",
        "child_list": "325,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "326",
        "name": "Printers, Scanners & Inks",
        "description": "Khusus printers, scanners & inks",
        "parent_id": "317",
        "parent_list": "326,317,25,-1",
        "child_list": "326,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "327",
        "name": "Keyboard, Mouse, Input",
        "description": "Khusus keyboard, mouse, input",
        "parent_id": "317",
        "parent_list": "327,317,25,-1",
        "child_list": "327,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "328",
        "name": "Casing, Power Supply, Cooling",
        "description": "Khusus casing, power supplies, cooling",
        "parent_id": "317",
        "parent_list": "328,317,25,-1",
        "child_list": "328,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "329",
        "name": "Software Original & Open Source",
        "description": "CD\/DVD (software original dan Open Source)",
        "parent_id": "200",
        "parent_list": "329,200,25,-1",
        "child_list": "329,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-200.png"
    },
    {
        "forum_id": "330",
        "name": "Aksesoris Komputer & Laptop",
        "description": "Khusus aksesoris komputer & laptop meliputi NoteBook, NetBook, LifeBook.",
        "parent_id": "317",
        "parent_list": "330,317,25,-1",
        "child_list": "330,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
    },
    {
        "forum_id": "331",
        "name": "Pictures",
        "description": "Tempat kumpulan gambar-gambar lucu.",
        "parent_id": "9",
        "parent_list": "331,9,241,-1",
        "child_list": "331,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-9.png"
    },
    {
        "forum_id": "332",
        "name": "Racing \/ Balap",
        "description": "Tempat diskusi serta berbagi informasi tentang dunia balap di dalam dan luar negeri.",
        "parent_id": "35",
        "parent_list": "332,35,241,-1",
        "child_list": "332,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "333",
        "name": "Aksesoris Motor",
        "description": "Khusus aksesoris motor",
        "parent_id": "205",
        "parent_list": "333,205,25,-1",
        "child_list": "333,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
    },
    {
        "forum_id": "334",
        "name": "Aksesoris Mobil",
        "description": "Khusus aksesoris mobil",
        "parent_id": "205",
        "parent_list": "334,205,25,-1",
        "child_list": "334,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
    },
    {
        "forum_id": "381",
        "name": "Kartu Perdana",
        "description": "Khusus jual beli kartu-kartu perdana",
        "parent_id": "210",
        "parent_list": "381,210,25,-1",
        "child_list": "381,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-210.png"
    },
    {
        "forum_id": "382",
        "name": "KASKUS Theater",
        "description": "Forum untuk membahas film karya sendiri\/ independen.",
        "parent_id": "11",
        "parent_list": "382,11,241,-1",
        "child_list": "382,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-11.png"
    },
    {
        "forum_id": "383",
        "name": "Macintosh",
        "description": "Tempat diskusi dan berbagi informasi tentang produk Macintosh, baik hardware maupun software.",
        "parent_id": "19",
        "parent_list": "383,19,241,-1",
        "child_list": "383,569,568,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "384",
        "name": "Brisbane",
        "description": "Buat kaskuer yg tinggal or pernah tinggal di Brisbane, ngumpul yuk disini!",
        "parent_id": "74",
        "parent_list": "384,74,72,-1",
        "child_list": "384,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "385",
        "name": "Kalimantan Tengah",
        "description": "",
        "parent_id": "461",
        "parent_list": "385,461,73,72,-1",
        "child_list": "385,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "386",
        "name": "Music Event",
        "description": "Tempat berbagi info seputar event musik dan pengalaman Kaskuser (baik gigs report band Indie maupun musisi mainstream).",
        "parent_id": "33",
        "parent_list": "386,33,241,-1",
        "child_list": "386,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "387",
        "name": "Ilmu Marketing",
        "description": "Forum diskusi seputar dunia marketing, baik keilmuan maupun terapan",
        "parent_id": "241",
        "parent_list": "387,241,-1",
        "child_list": "387,388,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "388",
        "name": "Ilmu Marketing & Research",
        "description": "Tempat diskusi dan membahas dasar-dasar ilmu marketing, serta berbagi hasil penelitian terkait marketing.",
        "parent_id": "387",
        "parent_list": "388,387,241,-1",
        "child_list": "388,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-387.png"
    },
    {
        "forum_id": "389",
        "name": "Budaya",
        "description": "Tempat berbagi hal-hal yang terkait dengan budaya dan adat istiadat Nusantara",
        "parent_id": "23",
        "parent_list": "389,23,241,-1",
        "child_list": "389,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-23.png"
    },
    {
        "forum_id": "390",
        "name": "TokuSenKa",
        "description": "Tempat untuk diskusi Tokusatsu, Super Sentai dan Kaijuu",
        "parent_id": "26",
        "parent_list": "390,26,241,-1",
        "child_list": "390,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
    },
    {
        "forum_id": "391",
        "name": "REQUEST @ CCPB",
        "description": "Tempat berbagi kumpulan Windows-based applications.",
        "parent_id": "14",
        "parent_list": "391,14,19,241,-1",
        "child_list": "391,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-14.png"
    },
    {
        "forum_id": "392",
        "name": "Hobby & Community",
        "description": "Forum diskusi dan berbagi informasi seputar hobi dan komunitas.",
        "parent_id": "241",
        "parent_list": "392,241,-1",
        "child_list": "392,591,581,395,393,580,394,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "393",
        "name": "Pisau",
        "description": "Tempat diskusi dan berbagi informasi tentang pisau yang mencakup pisau lipat, fix blades, pedang, dan peralatan lain yang berhubungan dengan pisau.",
        "parent_id": "392",
        "parent_list": "393,392,241,-1",
        "child_list": "393,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "394",
        "name": "Sepeda",
        "description": "Tempatnya pengguna, penikmat, dan pemerhati semua jenis sepeda.",
        "parent_id": "392",
        "parent_list": "394,392,241,-1",
        "child_list": "394,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "395",
        "name": "Mancing",
        "description": "Tempat diskusi dan berbagi tips & trik, tackle, serta pengalaman seputar hobi memancing.",
        "parent_id": "392",
        "parent_list": "395,392,241,-1",
        "child_list": "395,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "396",
        "name": "Reg Leader Lounge",
        "description": "Lounge dimana Reg leader bisa sharing pengalaman n saling tukar pikiran dan pandangan",
        "parent_id": "4",
        "parent_list": "396,4,-1",
        "child_list": "396,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-4.png"
    },
    {
        "forum_id": "397",
        "name": "ISP",
        "description": "Tempat diskusi Penyedia Layanan Internet di Indonesia.",
        "parent_id": "183",
        "parent_list": "397,183,19,241,-1",
        "child_list": "397,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-183.png"
    },
    {
        "forum_id": "398",
        "name": "Kepulauan Riau",
        "description": "",
        "parent_id": "460",
        "parent_list": "398,460,73,72,-1",
        "child_list": "398,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "402",
        "name": "Tegal",
        "description": "",
        "parent_id": "457",
        "parent_list": "402,457,73,72,-1",
        "child_list": "402,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "403",
        "name": "Karesidenan Besuki",
        "description": "Banyuwangi, Bondowoso, dan Situbondo",
        "parent_id": "459",
        "parent_list": "403,459,73,72,-1",
        "child_list": "403,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "405",
        "name": "Bekasi",
        "description": "",
        "parent_id": "458",
        "parent_list": "405,458,73,72,-1",
        "child_list": "405,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "407",
        "name": "Depok",
        "description": "",
        "parent_id": "458",
        "parent_list": "407,458,73,72,-1",
        "child_list": "407,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "411",
        "name": "Karesidenan Madiun",
        "description": "",
        "parent_id": "459",
        "parent_list": "411,459,73,72,-1",
        "child_list": "411,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "412",
        "name": "Cirebon",
        "description": "",
        "parent_id": "458",
        "parent_list": "412,458,73,72,-1",
        "child_list": "412,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "413",
        "name": "Mobile Phone",
        "description": "Diskusi mengenai ponsel berbasis Java, Symbian, GSM, CDMA, Dual GSM\/CDMA, dan iOS (produk Apple)",
        "parent_id": "36",
        "parent_list": "413,36,241,-1",
        "child_list": "413,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
    },
    {
        "forum_id": "415",
        "name": "PDA & PDA Phone",
        "description": "Diskusi mengenai Personal Digital Assistant (electronic handheld information device). Termasuk WM, Palm, dan Android",
        "parent_id": "36",
        "parent_list": "415,36,241,-1",
        "child_list": "415,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
    },
    {
        "forum_id": "417",
        "name": "Operator CDMA & GSM",
        "description": "Diskusi khusus layanan operator CDMA dan GSM.",
        "parent_id": "36",
        "parent_list": "417,36,241,-1",
        "child_list": "417,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
    },
    {
        "forum_id": "419",
        "name": "Taman Bacaan CCPB",
        "description": "Tempat khusus e-books dan tutorial Computer Stuff.",
        "parent_id": "14",
        "parent_list": "419,14,19,241,-1",
        "child_list": "419,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-14.png"
    },
    {
        "forum_id": "421",
        "name": "Visit USA",
        "description": "Apply Visa, Informasi Sekolah\/Kerja, Imigrasi, Travel, dll.",
        "parent_id": "76",
        "parent_list": "421,76,617,72,-1",
        "child_list": "421,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "423",
        "name": "West USA",
        "description": "Western states (formerly Seattle, San Francisco, Los Angeles)",
        "parent_id": "76",
        "parent_list": "423,76,617,72,-1",
        "child_list": "423,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "425",
        "name": "Central USA",
        "description": "Central + Midwest (formerly Texas, Illinois)",
        "parent_id": "76",
        "parent_list": "425,76,617,72,-1",
        "child_list": "425,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "427",
        "name": "Papua",
        "description": "",
        "parent_id": "463",
        "parent_list": "427,463,73,72,-1",
        "child_list": "427,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "429",
        "name": "Kids & Parenting",
        "description": "Tempat berbagi pengetahuan dan berdiskusi tentang anak, mencakup metode pendidikan bagi anak.",
        "parent_id": "193",
        "parent_list": "429,193,241,-1",
        "child_list": "429,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-193.png"
    },
    {
        "forum_id": "431",
        "name": "Anime",
        "description": "Tempat untuk diskusi serial Anime, baik yang sedang tayang maupun yang sudah tamat",
        "parent_id": "26",
        "parent_list": "431,26,241,-1",
        "child_list": "431,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
    },
    {
        "forum_id": "433",
        "name": "Manga, Manhua, & Manhwa",
        "description": "Tempat untuk diskusi komik yang berasal dari Jepang, Hongkong, Korea dan Indonesia",
        "parent_id": "26",
        "parent_list": "433,26,241,-1",
        "child_list": "433,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
    },
    {
        "forum_id": "435",
        "name": "KASKUS Promo updated",
        "description": "Forum yang berisi berbagai update, info & promosi terbaru dari KASKUS.",
        "parent_id": "239",
        "parent_list": "435,239,-1",
        "child_list": "435,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
    },
    {
        "forum_id": "437",
        "name": "Domestik",
        "description": "Tempat diskusi seputar objek wisata dalam negeri.",
        "parent_id": "235",
        "parent_list": "437,235,241,-1",
        "child_list": "437,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-235.png"
    },
    {
        "forum_id": "439",
        "name": "Mancanegara",
        "description": "Tempat diskusi seputar objek wisata luar negeri.",
        "parent_id": "235",
        "parent_list": "439,235,241,-1",
        "child_list": "439,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-235.png"
    },
    {
        "forum_id": "440",
        "name": "Basketball",
        "description": "Tempat diskusi para pecinta basket.",
        "parent_id": "35",
        "parent_list": "440,35,241,-1",
        "child_list": "440,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "442",
        "name": "Templates & Scripts Stuff",
        "description": "Tempat kumpulan templates dan scripts.",
        "parent_id": "13",
        "parent_list": "442,13,19,241,-1",
        "child_list": "442,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-13.png"
    },
    {
        "forum_id": "443",
        "name": "Hosting Stuff",
        "description": "Hosting (shared hosting, VPS, dedicated), domain (register), software hosting (cPanel, WHM, lxAdmin, etc), technical & security issues, webserver.",
        "parent_id": "13",
        "parent_list": "443,13,19,241,-1",
        "child_list": "443,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-13.png"
    },
    {
        "forum_id": "444",
        "name": "Die-cast, Mini4WD & R\/C",
        "description": "Khusus die-cast, Mini4WD, radio control vehicles",
        "parent_id": "198",
        "parent_list": "444,198,25,-1",
        "child_list": "444,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "446",
        "name": "Bayi",
        "description": "Pakaian dan perlengkapan bayi",
        "parent_id": "305",
        "parent_list": "446,305,25,-1",
        "child_list": "446,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-305.png"
    },
    {
        "forum_id": "447",
        "name": "Anak-Anak",
        "description": "Pakaian dan perlengkapan anak",
        "parent_id": "305",
        "parent_list": "447,305,25,-1",
        "child_list": "447,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-305.png"
    },
    {
        "forum_id": "448",
        "name": "Industri Garmen",
        "description": "Bahan baku (kain, benang dsb) dan sablon",
        "parent_id": "286",
        "parent_list": "448,286,25,-1",
        "child_list": "448,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-286.png"
    },
    {
        "forum_id": "449",
        "name": "Kemeja, Kaos & Polo Shirt ( baju )",
        "description": "Kemeja, Kaos dan polo shirt ( baju )",
        "parent_id": "196",
        "parent_list": "449,196,25,-1",
        "child_list": "449,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "450",
        "name": "Jaket, Hoodie, Sweater",
        "description": "Khusus jaket, hoodie dan sweater",
        "parent_id": "196",
        "parent_list": "450,196,25,-1",
        "child_list": "450,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "451",
        "name": "Celana,  Jeans & Rok",
        "description": "Celana bahan, kargo, jeans & rok",
        "parent_id": "196",
        "parent_list": "451,196,25,-1",
        "child_list": "451,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "452",
        "name": "Karesidenan Kediri",
        "description": "",
        "parent_id": "459",
        "parent_list": "452,459,73,72,-1",
        "child_list": "452,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "457",
        "name": "Jawa Tengah & Yogyakarta",
        "description": "",
        "parent_id": "73",
        "parent_list": "457,73,72,-1",
        "child_list": "457,181,653,627,564,598,111,160,402,84,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "458",
        "name": "Jawa Barat, Jakarta & Banten",
        "description": "",
        "parent_id": "73",
        "parent_list": "458,73,72,-1",
        "child_list": "458,89,164,405,107,412,407,654,78,626,585,599,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "459",
        "name": "Jawa Timur & Bali",
        "description": "",
        "parent_id": "73",
        "parent_list": "459,73,72,-1",
        "child_list": "459,167,587,567,555,403,651,452,411,652,133,583,628,92,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "460",
        "name": "Sumatera",
        "description": "",
        "parent_id": "73",
        "parent_list": "460,73,72,-1",
        "child_list": "460,161,97,543,586,548,398,145,93,156,81,117,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "461",
        "name": "Kalimantan",
        "description": "",
        "parent_id": "73",
        "parent_list": "461,73,72,-1",
        "child_list": "461,162,146,385,91,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "462",
        "name": "Sulawesi",
        "description": "",
        "parent_id": "73",
        "parent_list": "462,73,72,-1",
        "child_list": "462,584,561,170,179,166,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "463",
        "name": "Indonesia Timur",
        "description": "",
        "parent_id": "73",
        "parent_list": "463,73,72,-1",
        "child_list": "463,427,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "464",
        "name": "English Education & Literature",
        "description": "A place where you can find all the English help you need from TOEFL, IELTS and everything else regarding the English language and its usage.",
        "parent_id": "113",
        "parent_list": "464,113,241,-1",
        "child_list": "464,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-113.png"
    },
    {
        "forum_id": "465",
        "name": "Fun with English",
        "description": "A place to learn English through various game threads.",
        "parent_id": "113",
        "parent_list": "465,113,241,-1",
        "child_list": "465,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-113.png"
    },
    {
        "forum_id": "466",
        "name": "Penawaran Kerjasama & Investasi",
        "description": "Tempat berbagi penawaran kerjasama dan investasi usaha.",
        "parent_id": "277",
        "parent_list": "466,277,30,241,-1",
        "child_list": "466,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-277.png"
    },
    {
        "forum_id": "467",
        "name": "Forex",
        "description": "",
        "parent_id": "279",
        "parent_list": "467,279,30,241,-1",
        "child_list": "467,470,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-279.png"
    },
    {
        "forum_id": "468",
        "name": "Options",
        "description": "",
        "parent_id": "279",
        "parent_list": "468,279,30,241,-1",
        "child_list": "468,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-279.png"
    },
    {
        "forum_id": "469",
        "name": "Saham",
        "description": "",
        "parent_id": "279",
        "parent_list": "469,279,30,241,-1",
        "child_list": "469,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-279.png"
    },
    {
        "forum_id": "470",
        "name": "Forex Broker",
        "description": "",
        "parent_id": "467",
        "parent_list": "470,467,279,30,241,-1",
        "child_list": "470,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-467.png"
    },
    {
        "forum_id": "471",
        "name": "The Online Business",
        "description": "Diskusi segala bentuk bisnis online dan perkembangannya. Dilarang promosi disini.",
        "parent_id": "30",
        "parent_list": "471,30,241,-1",
        "child_list": "471,280,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "472",
        "name": "MLM, Member Get Member, & Sejenisnya",
        "description": "Tempat diskusi dan promosi bisnis direct selling dan sejenisnya.",
        "parent_id": "30",
        "parent_list": "472,30,241,-1",
        "child_list": "472,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "473",
        "name": "Gathering, Event Report & Bakti Sosial",
        "description": "Tempat kumpulan arsip dari semua event dan bakti sosial komunitas KASKUS.",
        "parent_id": "240",
        "parent_list": "473,240,239,-1",
        "child_list": "473,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-240.png"
    },
    {
        "forum_id": "474",
        "name": "Event from Kaskuser",
        "description": "Forum untuk berbagi informasi mengenai event yang berhubungan dengan KASKUS. Untuk gathering & FR regional harap dibuat di regional masing-masing.",
        "parent_id": "241",
        "parent_list": "474,241,-1",
        "child_list": "474,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "475",
        "name": "Others",
        "description": "",
        "parent_id": "74",
        "parent_list": "475,74,72,-1",
        "child_list": "475,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "476",
        "name": "Others",
        "description": "",
        "parent_id": "157",
        "parent_list": "476,157,72,-1",
        "child_list": "476,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "477",
        "name": "Others",
        "description": "",
        "parent_id": "109",
        "parent_list": "477,109,72,-1",
        "child_list": "477,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "478",
        "name": "Others",
        "description": "",
        "parent_id": "158",
        "parent_list": "478,158,72,-1",
        "child_list": "478,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "479",
        "name": "Cinta Indonesiaku",
        "description": "Forum yang didedikasikan untuk menunjukkan kecintaan Kaskuser terhadap Indonesia.",
        "parent_id": "239",
        "parent_list": "479,239,-1",
        "child_list": "479,480,485,481,484,486,482,483,542,488,490,489,487,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
    },
    {
        "forum_id": "480",
        "name": "Arsitektur",
        "description": "",
        "parent_id": "479",
        "parent_list": "480,479,239,-1",
        "child_list": "480,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "481",
        "name": "Kuliner",
        "description": "",
        "parent_id": "479",
        "parent_list": "481,479,239,-1",
        "child_list": "481,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "482",
        "name": "Pakaian",
        "description": "",
        "parent_id": "479",
        "parent_list": "482,479,239,-1",
        "child_list": "482,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "483",
        "name": "Lagu, Tarian & Alat Musik",
        "description": "",
        "parent_id": "479",
        "parent_list": "483,479,239,-1",
        "child_list": "483,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "484",
        "name": "Kerajinan & Ukiran",
        "description": "",
        "parent_id": "479",
        "parent_list": "484,479,239,-1",
        "child_list": "484,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "485",
        "name": "Kekayaan Alam, Flora & Fauna",
        "description": "",
        "parent_id": "479",
        "parent_list": "485,479,239,-1",
        "child_list": "485,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "486",
        "name": "Kesusastraan, Bahasa & Dongeng",
        "description": "",
        "parent_id": "479",
        "parent_list": "486,479,239,-1",
        "child_list": "486,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "487",
        "name": "Tata Cara Adat, Upacara & Ritual",
        "description": "",
        "parent_id": "479",
        "parent_list": "487,479,239,-1",
        "child_list": "487,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "488",
        "name": "Permainan Rakyat",
        "description": "",
        "parent_id": "479",
        "parent_list": "488,479,239,-1",
        "child_list": "488,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "489",
        "name": "Seni Peran",
        "description": "",
        "parent_id": "479",
        "parent_list": "489,479,239,-1",
        "child_list": "489,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "490",
        "name": "Properti Sejarah Nasional",
        "description": "",
        "parent_id": "479",
        "parent_list": "490,479,239,-1",
        "child_list": "490,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "491",
        "name": "Mobile Broadband",
        "description": "Forum diskusi mengenai wireless dan high-speed internet access menggunakan modem portable, jaringan telepon, maupun perangkat lainnya.",
        "parent_id": "241",
        "parent_list": "491,241,-1",
        "child_list": "491,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "527",
        "name": "Aksesoris, suku cadang HP",
        "description": "Aksesori dan suku cadang HP\/smartphone\/PDAphone\/Blackberry",
        "parent_id": "210",
        "parent_list": "527,210,25,-1",
        "child_list": "527,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-210.png"
    },
    {
        "forum_id": "528",
        "name": "PC Games",
        "description": "Tempat diskusi seputar games yang dimainkan di Personal Computer (PC)",
        "parent_id": "44",
        "parent_list": "528,44,241,-1",
        "child_list": "528,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
    },
    {
        "forum_id": "537",
        "name": "Sport Games",
        "description": "Tempat berbagi game olahraga seru.",
        "parent_id": "35",
        "parent_list": "537,35,241,-1",
        "child_list": "537,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "538",
        "name": "Racket",
        "description": "Tempat diskusi para pecinta olahraga yang menggunakan raket (tenis, squash, ping pong\/tenis meja (tenis meja), dan badminton\/bulutangkis.",
        "parent_id": "35",
        "parent_list": "538,35,241,-1",
        "child_list": "538,539,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "539",
        "name": "Badminton",
        "description": "Tempat diskusi khusus pencinta olahraga badminton atau bulutangkis.",
        "parent_id": "538",
        "parent_list": "539,538,35,241,-1",
        "child_list": "539,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-538.png"
    },
    {
        "forum_id": "540",
        "name": "Korea Selatan",
        "description": "",
        "parent_id": "109",
        "parent_list": "540,109,72,-1",
        "child_list": "540,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "541",
        "name": "Nokia",
        "description": "Forum bagi pengguna gadget Nokia. Tempat diskusi dan berbagi informasi terkini mengenai hal-hal yang terkait dengan Nokia.",
        "parent_id": "241",
        "parent_list": "541,241,-1",
        "child_list": "541,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "542",
        "name": "Pahlawan & Tokoh Nasional",
        "description": "",
        "parent_id": "479",
        "parent_list": "542,479,239,-1",
        "child_list": "542,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "543",
        "name": "Batam",
        "description": "",
        "parent_id": "460",
        "parent_list": "543,460,73,72,-1",
        "child_list": "543,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "544",
        "name": "Young on Top KASKUS Community (YOTKC)",
        "description": "Forum untuk berbagi inspirasi bersama Billy Boen.",
        "parent_id": "241",
        "parent_list": "544,241,-1",
        "child_list": "544,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "545",
        "name": "Pro Wrestling",
        "description": "Tempat diskusi para pecinta pro wrestling.",
        "parent_id": "35",
        "parent_list": "545,35,241,-1",
        "child_list": "545,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "546",
        "name": "Dunia Kerja & Profesi",
        "description": "Tempat diskusi beragam profesi dan pembahasan seputar karir, gaji, pajak, keuangan dan serba-serbi dunia kerja.",
        "parent_id": "30",
        "parent_list": "546,30,241,-1",
        "child_list": "546,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "548",
        "name": "Jambi",
        "description": "",
        "parent_id": "460",
        "parent_list": "548,460,73,72,-1",
        "child_list": "548,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "552",
        "name": "Fanstuff",
        "description": "Tempatnya para penggemar fiksi. Lihat juga cerita fiksi karya mereka!",
        "parent_id": "26",
        "parent_list": "552,26,241,-1",
        "child_list": "552,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
    },
    {
        "forum_id": "553",
        "name": "Web Hosting & Services",
        "description": "Web development, Jasa Hosting, Registrasi Domain, Voucher \/ Akses Premium ke rapid*share dsb, Web Promotion Service, SEO, Link building, Imaging, dsb., Web Consultation \/ Web coaching",
        "parent_id": "202",
        "parent_list": "553,202,25,-1",
        "child_list": "553,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-202.png"
    },
    {
        "forum_id": "554",
        "name": "BANNER TEST",
        "description": "Forum ini adalah forum diskusi untuk testing banner preview",
        "parent_id": "-1",
        "parent_list": "554,-1",
        "child_list": "554,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image--1.png"
    },
    {
        "forum_id": "555",
        "name": "Jember",
        "description": "",
        "parent_id": "459",
        "parent_list": "555,459,73,72,-1",
        "child_list": "555,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "557",
        "name": "Hardware Review Lab",
        "description": "Tempat kumpulan ulasan mengenai hardware.",
        "parent_id": "243",
        "parent_list": "557,243,19,241,-1",
        "child_list": "557,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-243.png"
    },
    {
        "forum_id": "558",
        "name": "Fit & Healty Lifestyle",
        "description": "Forum gaya hidup sehat. Pengetahuan tentang diet & nutrisi, fitness & muscle building, metode olahraga untuk keseimbangan, hingga cara menghentikan adiksi.",
        "parent_id": "241",
        "parent_list": "558,241,-1",
        "child_list": "558,274,236,559,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "559",
        "name": "Quit Smoking & Avoid Drugs",
        "description": "Tempat diskusi dan berbagi  cara mengubah pemikiran, langkah dan dukungan untuk berhenti merokok serta menjaga kesehatan tanpa obat-obatan.",
        "parent_id": "558",
        "parent_list": "559,558,241,-1",
        "child_list": "559,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
    },
    {
        "forum_id": "561",
        "name": "Kendari",
        "description": "",
        "parent_id": "462",
        "parent_list": "561,462,73,72,-1",
        "child_list": "561,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "564",
        "name": "Karesidenan Pati",
        "description": "",
        "parent_id": "457",
        "parent_list": "564,457,73,72,-1",
        "child_list": "564,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "565",
        "name": "FutSal",
        "description": "Tempat berbagi para pencinta futsal tentang berita, informasi, dan pengalaman seputar dunia futsal.",
        "parent_id": "104",
        "parent_list": "565,104,35,241,-1",
        "child_list": "565,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-104.png"
    },
    {
        "forum_id": "566",
        "name": "Surat Terbuka",
        "description": "Pusat pengaduan Kaskuser terkait transaksi di Forum Jual Beli Kaskus: kerugian, penipuan",
        "parent_id": "204",
        "parent_list": "566,204,25,-1",
        "child_list": "566,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-204.png"
    },
    {
        "forum_id": "567",
        "name": "Gresik",
        "description": "",
        "parent_id": "459",
        "parent_list": "567,459,73,72,-1",
        "child_list": "567,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "568",
        "name": "Mac OSX Info & Discussion",
        "description": "Tempat diskusi dan berbagi informasi dan pengalaman seputar Mac, Mac buyers guide, tutorials & e-books, serta teknologi terbaru .",
        "parent_id": "383",
        "parent_list": "568,383,19,241,-1",
        "child_list": "568,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-383.png"
    },
    {
        "forum_id": "569",
        "name": "Mac Applications & Games",
        "description": "Tempat review, share, troubleshooting apps, games, modifikasi OSX, beragam tips dan trik aplikasi.",
        "parent_id": "383",
        "parent_list": "569,383,19,241,-1",
        "child_list": "569,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-383.png"
    },
    {
        "forum_id": "570",
        "name": "Kendaraan Roda 4",
        "description": "Tempat membahas kendaraan beroda empat (mobil) dari segala brand (merek)",
        "parent_id": "28",
        "parent_list": "570,28,241,-1",
        "child_list": "570,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-28.png"
    },
    {
        "forum_id": "571",
        "name": "The Exclusive Business Club (ExBC)",
        "description": "Tempat berkumpulnya para pelaku bisnis atau pengusaha untuk berbagi pengalaman tentang pengembangan bisnis di bidang masing-masing.",
        "parent_id": "30",
        "parent_list": "571,30,241,-1",
        "child_list": "571,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "572",
        "name": "Penawaran Kerjasama, BO, Distribusi, Reseller, & Agen",
        "description": "Tempat untuk menawarkan bisnis baik dalam bentuk franchise, peluang bisnis, distribusi, reseller, kemitraan, dan agen usaha.",
        "parent_id": "30",
        "parent_list": "572,30,241,-1",
        "child_list": "572,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "573",
        "name": "Pulsa",
        "description": "Khusus Jual beli\/transfer pulsa, voucher HP",
        "parent_id": "210",
        "parent_list": "573,210,25,-1",
        "child_list": "573,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-210.png"
    },
    {
        "forum_id": "574",
        "name": "Jasa & Perbaikan HP",
        "description": "Jasa perbaikan, isi aplikasi dan program lainnya untuk HP\/smartphone\/PDAphone\/Blackberry",
        "parent_id": "210",
        "parent_list": "574,210,25,-1",
        "child_list": "574,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-210.png"
    },
    {
        "forum_id": "575",
        "name": "Militer dan Kepolisian",
        "description": "Forum diskusi dan berbagi berita maupun informasi seputar dunia militer dan kepolisian.",
        "parent_id": "241",
        "parent_list": "575,241,-1",
        "child_list": "575,576,140,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "576",
        "name": "Kepolisian",
        "description": "Tempat diskusi seputar dunia kepolisian.",
        "parent_id": "575",
        "parent_list": "576,575,241,-1",
        "child_list": "576,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-575.png"
    },
    {
        "forum_id": "577",
        "name": "Android",
        "description": "Diskusi khusus mengenai Android",
        "parent_id": "36",
        "parent_list": "577,36,241,-1",
        "child_list": "577,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
    },
    {
        "forum_id": "578",
        "name": "Teknik",
        "description": "Forum untuk berdiskusi dan berbagi pengetahuan atau informasi seputar teknik arsitektur dan teknik sipil .",
        "parent_id": "241",
        "parent_list": "578,241,-1",
        "child_list": "578,234,579,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "579",
        "name": "Sipil",
        "description": "Tempat diskusi seputar teknik sipil, baik keilmuan maupun terapan.",
        "parent_id": "578",
        "parent_list": "579,578,241,-1",
        "child_list": "579,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-578.png"
    },
    {
        "forum_id": "580",
        "name": "Radio Komunikasi",
        "description": "Tempat diskusi dan ngumpulnya para penggemar radio komunikasi (HAM Radio).",
        "parent_id": "392",
        "parent_list": "580,392,241,-1",
        "child_list": "580,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "581",
        "name": "Lampu Senter \/ Flashlight",
        "description": "Tempat ngumpulnya Flashholic dan pengguna senter, laser, LED, beserta aksesorisnya.",
        "parent_id": "392",
        "parent_list": "581,392,241,-1",
        "child_list": "581,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "583",
        "name": "Mojokerto",
        "description": "",
        "parent_id": "459",
        "parent_list": "583,459,73,72,-1",
        "child_list": "583,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "584",
        "name": "Gorontalo",
        "description": "",
        "parent_id": "462",
        "parent_list": "584,462,73,72,-1",
        "child_list": "584,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "585",
        "name": "Sukabumi",
        "description": "",
        "parent_id": "458",
        "parent_list": "585,458,73,72,-1",
        "child_list": "585,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "586",
        "name": "Bengkulu",
        "description": "",
        "parent_id": "460",
        "parent_list": "586,460,73,72,-1",
        "child_list": "586,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "587",
        "name": "Bromo",
        "description": "",
        "parent_id": "459",
        "parent_list": "587,459,73,72,-1",
        "child_list": "587,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "588",
        "name": "Online Gaming",
        "description": "",
        "parent_id": "25",
        "parent_list": "588,25,-1",
        "child_list": "588,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "589",
        "name": "Pakaian, Sepatu",
        "description": "Pakaian\/jersey\/seragam klub dan sepatu olahraga",
        "parent_id": "220",
        "parent_list": "589,220,25,-1",
        "child_list": "589,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-220.png"
    },
    {
        "forum_id": "590",
        "name": "Sepeda",
        "description": "Khusus sepeda, perangkat dan perlengkapannya",
        "parent_id": "198",
        "parent_list": "590,198,25,-1",
        "child_list": "590,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "591",
        "name": "Jam",
        "description": "Tempat diskusi tentang jam sebagai tools, koleksi, dan hobi",
        "parent_id": "392",
        "parent_list": "591,392,241,-1",
        "child_list": "591,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "593",
        "name": "Kredit & Leasing Kendaraan Bermotor",
        "description": "",
        "parent_id": "205",
        "parent_list": "593,205,25,-1",
        "child_list": "593,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
    },
    {
        "forum_id": "594",
        "name": "Melek Hukum",
        "description": "Forum diskusi mengenai hukum yang berlaku di Indonesia, mulai dari penerapan hukum sederhana hingga pembahasan mendalam.",
        "parent_id": "241",
        "parent_list": "594,241,-1",
        "child_list": "594,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "595",
        "name": "UKM",
        "description": "Tempat diskusi dan berbagi seputar Usaha Kecil Menengah (UKM), mulai dari tips, trik, dan pengalaman menjalankan usaha.",
        "parent_id": "30",
        "parent_list": "595,30,241,-1",
        "child_list": "595,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "596",
        "name": "Catatan Perjalanan OANC",
        "description": "Tempat diskusi, berbagi dan ajakan perjalanan mencakup bahasan tentang lokasi, rute, biaya, logistik, dll",
        "parent_id": "98",
        "parent_list": "596,98,241,-1",
        "child_list": "596,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-98.png"
    },
    {
        "forum_id": "597",
        "name": "Sains & Teknologi",
        "description": "Tempat diskusi mendalam dan berbagi pengetahuan sains dan teknologi.",
        "parent_id": "67",
        "parent_list": "597,67,241,-1",
        "child_list": "597,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-67.png"
    },
    {
        "forum_id": "598",
        "name": "Klaten ",
        "description": "",
        "parent_id": "457",
        "parent_list": "598,457,73,72,-1",
        "child_list": "598,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "599",
        "name": "Tasikmalaya ",
        "description": "",
        "parent_id": "458",
        "parent_list": "599,458,73,72,-1",
        "child_list": "599,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "600",
        "name": "Perhiasan",
        "description": "Gelang, anting, kalung dan cincin",
        "parent_id": "196",
        "parent_list": "600,196,25,-1",
        "child_list": "600,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "603",
        "name": "Desain",
        "description": "Produk dan jasa desain",
        "parent_id": "284",
        "parent_list": "603,284,25,-1",
        "child_list": "603,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-284.png"
    },
    {
        "forum_id": "604",
        "name": "Aksesoris Kamera",
        "description": "Aksesoris kamera",
        "parent_id": "293",
        "parent_list": "604,293,25,-1",
        "child_list": "604,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-293.png"
    },
    {
        "forum_id": "605",
        "name": "Kamera",
        "description": "Kamera beragam merk",
        "parent_id": "293",
        "parent_list": "605,293,25,-1",
        "child_list": "605,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-293.png"
    },
    {
        "forum_id": "606",
        "name": "Kaset",
        "description": "Khusus kaset",
        "parent_id": "198",
        "parent_list": "606,198,25,-1",
        "child_list": "606,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
    },
    {
        "forum_id": "607",
        "name": "Minuman",
        "description": "Khusus aneka minuman (HARUS halal)",
        "parent_id": "201",
        "parent_list": "607,201,25,-1",
        "child_list": "607,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-201.png"
    },
    {
        "forum_id": "608",
        "name": "Perawatan Tubuh",
        "description": "Produk untuk perawatan tubuh",
        "parent_id": "295",
        "parent_list": "608,295,25,-1",
        "child_list": "608,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-295.png"
    },
    {
        "forum_id": "609",
        "name": "Perawatan Wajah",
        "description": "Produk untuk perawatan wajah",
        "parent_id": "295",
        "parent_list": "609,295,25,-1",
        "child_list": "609,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-295.png"
    },
    {
        "forum_id": "610",
        "name": "Pertunjukan",
        "description": "Khusus tiket pertunjukkan musik\/ konser\/ film",
        "parent_id": "316",
        "parent_list": "610,316,25,-1",
        "child_list": "610,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-316.png"
    },
    {
        "forum_id": "611",
        "name": "Transportasi",
        "description": "Khusus tiket transportasi (darat, laut, udara)",
        "parent_id": "316",
        "parent_list": "611,316,25,-1",
        "child_list": "611,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-316.png"
    },
    {
        "forum_id": "612",
        "name": "Aksesoris",
        "description": "Khusus aksesori",
        "parent_id": "297",
        "parent_list": "612,297,25,-1",
        "child_list": "612,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-297.png"
    },
    {
        "forum_id": "613",
        "name": "Konsol",
        "description": "PS, Nintendo, Xbox, PSP, Sega dsb",
        "parent_id": "297",
        "parent_list": "613,297,25,-1",
        "child_list": "613,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-297.png"
    },
    {
        "forum_id": "614",
        "name": "Serba Serbi",
        "description": "Jual beli aneka produk diluar kategori \/sub kategori",
        "parent_id": "25",
        "parent_list": "614,25,-1",
        "child_list": "614,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "615",
        "name": "Bisnis",
        "description": "Penawaran bisnis",
        "parent_id": "25",
        "parent_list": "615,25,-1",
        "child_list": "615,616,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "616",
        "name": "Peluang Bisnis",
        "description": "Reseller, franchise dan supplier",
        "parent_id": "615",
        "parent_list": "616,615,25,-1",
        "child_list": "616,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-615.png"
    },
    {
        "forum_id": "617",
        "name": "America",
        "description": "",
        "parent_id": "72",
        "parent_list": "617,72,-1",
        "child_list": "617,83,76,421,425,96,423,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "619",
        "name": "Indie Filmmaker",
        "description": "Tempat untuk pembuat film independent saling berdiskusi & berbagi kesukaan. Baik produksi atau topik yang berhubungan dengan film independent.",
        "parent_id": "11",
        "parent_list": "619,11,241,-1",
        "child_list": "619,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-11.png"
    },
    {
        "forum_id": "620",
        "name": "Perencanaan Keuangan",
        "description": "Forum untuk diskusi & konsultasi seputar perencanaan keuangan, mulai dari pengelolaan keuangan hingga cara berinvestasi yang tepat.",
        "parent_id": "241",
        "parent_list": "620,241,-1",
        "child_list": "620,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "621",
        "name": "Film Indonesia",
        "description": "Forum untuk berdiskusi seputar film-film Indonesia dari era lampau hingga sekarang. Hal yang terkait dengan industri perfilman Indonesia juga dibahas disini.",
        "parent_id": "11",
        "parent_list": "621,11,241,-1",
        "child_list": "621,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-11.png"
    },
    {
        "forum_id": "624",
        "name": "Pakaian dalam",
        "description": "Lingerie & Pakaian dalam",
        "parent_id": "196",
        "parent_list": "624,196,25,-1",
        "child_list": "624,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "625",
        "name": "Komik",
        "description": "Komik",
        "parent_id": "227",
        "parent_list": "625,227,25,-1",
        "child_list": "625,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-227.png"
    },
    {
        "forum_id": "626",
        "name": "Karawang",
        "description": "",
        "parent_id": "458",
        "parent_list": "626,458,73,72,-1",
        "child_list": "626,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "627",
        "name": "Karesidenan Kedu",
        "description": "",
        "parent_id": "457",
        "parent_list": "627,457,73,72,-1",
        "child_list": "627,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "628",
        "name": "Sidoarjo",
        "description": "",
        "parent_id": "459",
        "parent_list": "628,459,73,72,-1",
        "child_list": "628,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "629",
        "name": "KASKUS Playground",
        "description": "Tempat informasi, kisah-kisah & cerita unik tentang Kaskus & Kaskus Officer",
        "parent_id": "239",
        "parent_list": "629,239,-1",
        "child_list": "629,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
    },
    {
        "forum_id": "630",
        "name": "Green Lifestyle",
        "description": "",
        "parent_id": "241",
        "parent_list": "630,241,-1",
        "child_list": "630,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "631",
        "name": "Instalasi Komputer new",
        "description": "Tempat menawarkan jasa untuk instalasi komputer, notebook, laptop, games",
        "parent_id": "202",
        "parent_list": "631,202,25,-1",
        "child_list": "631,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-202.png"
    },
    {
        "forum_id": "633",
        "name": "PEMILU 2014",
        "description": "Ruang diskusi & semua informasi yang berhubungan dengan Pemilu 2014, mulai dari partai politik, calon legislatif hingga calon presiden. Yuk, bangun Indonesia! Kenali Janji Manisnya, Suarakan Pendapatmu!\n",
        "parent_id": "241",
        "parent_list": "633,241,-1",
        "child_list": "633,634,636,637,638,639,640,641,642,643,644,645,646,647,648,649,650,635,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "634",
        "name": "PILIH PARPOL",
        "description": "Tempat khusus untuk membahas partai-partai PEMILU 2014 dan para calon legislatifnya",
        "parent_id": "633",
        "parent_list": "634,633,241,-1",
        "child_list": "634,636,637,638,639,640,641,642,643,644,645,646,647,648,649,650,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-633.png"
    },
    {
        "forum_id": "635",
        "name": "PILIH CAPRES",
        "description": "Ruang utama untuk mendiskusikan calon-calon presiden PEMILU 2014\n",
        "parent_id": "633",
        "parent_list": "635,633,241,-1",
        "child_list": "635,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-633.png"
    },
    {
        "forum_id": "636",
        "name": "1 - Partai NasDem",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Nasional Demokrat (NasDem) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "636,634,633,241,-1",
        "child_list": "636,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "637",
        "name": "2 - Partai Kebangkitan Bangsa (PKB)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Kebangkitan Bangsa (PKB) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "637,634,633,241,-1",
        "child_list": "637,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "638",
        "name": "3 - Partai Keadilan Sejahtera (PKS)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Keadilan Sejahtera (PKS) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "638,634,633,241,-1",
        "child_list": "638,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "639",
        "name": "4 - Partai Demokrasi Indonesia Perjuangan (PDIP)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Demokrasi Indonesia Perjuangan (PDIP) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "639,634,633,241,-1",
        "child_list": "639,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "640",
        "name": "5 - Partai Golongan Karya (GOLKAR)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Golongan Karya (GOLKAR) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "640,634,633,241,-1",
        "child_list": "640,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "641",
        "name": "6 - Partai Gerakan Indonesia Raya (GERINDRA)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Gerakan Indonesia Raya (GERINDRA) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "641,634,633,241,-1",
        "child_list": "641,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "642",
        "name": "7 - Partai Demokrat",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Demokrat dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "642,634,633,241,-1",
        "child_list": "642,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "643",
        "name": "8 - Partai Amanat Nasional (PAN)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Amanat  Nasional (PAN) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "643,634,633,241,-1",
        "child_list": "643,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "644",
        "name": "9 - Partai Persatuan Pembangunan (PPP)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai  Persatuan Pembangunan (PPP) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "644,634,633,241,-1",
        "child_list": "644,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "645",
        "name": "10 - Partai Hati Nurani Rakyat (HANURA)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Hati Nurani Rakyat (HANURA) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "645,634,633,241,-1",
        "child_list": "645,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "646",
        "name": "11 - Partai Damai Aceh (PDA)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Damai Aceh (PDA) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "646,634,633,241,-1",
        "child_list": "646,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "647",
        "name": "12 - Partai Nasional Aceh (PNA)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Nasional Aceh (PNA) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "647,634,633,241,-1",
        "child_list": "647,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "648",
        "name": "13 - Partai Aceh (PA)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Aceh (PA) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "648,634,633,241,-1",
        "child_list": "648,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "649",
        "name": "14 - Partai Bulan Bintang (PBB)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Bulan Bintang (PBB) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "649,634,633,241,-1",
        "child_list": "649,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "650",
        "name": "15 - Partai Keadilan Dan Persatuan Indonesia (PKPI)",
        "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Keadilan dan Persatuan Indonesia (PKPI) dan para calon legislatifnya",
        "parent_id": "634",
        "parent_list": "650,634,633,241,-1",
        "child_list": "650,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
    },
    {
        "forum_id": "651",
        "name": "Karesidenan Bojonegoro new",
        "description": "Bojonegoro, Tuban, dan Lamongan",
        "parent_id": "459",
        "parent_list": "651,459,73,72,-1",
        "child_list": "651,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "652",
        "name": "Madura new",
        "description": "",
        "parent_id": "459",
        "parent_list": "652,459,73,72,-1",
        "child_list": "652,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "653",
        "name": "Cilacap",
        "description": "",
        "parent_id": "457",
        "parent_list": "653,457,73,72,-1",
        "child_list": "653,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "654",
        "name": "Garut new",
        "description": "",
        "parent_id": "458",
        "parent_list": "654,458,73,72,-1",
        "child_list": "654,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    }
]
```

## GET forumlist

Get all subforum list of certain forum.

### HTTP Request

`GET /forumlist/{forum_id}`

Parameter | Description
--------- | -----------
forum_id|forum id
output|output format (JSON or XML)




> Example response

```json
[
    {
        "forum_id": "59",
        "name": "Gosip Nyok!",
        "description": "Tempat bergosip bareng Kaskuser.",
        "parent_id": "21",
        "parent_list": "59,21,241,-1",
        "child_list": "59,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    {
        "forum_id": "186",
        "name": "Lounge Pictures & Video",
        "description": "Tempat berbagi kumpulan gambar menarik, seru, lucu, dan unik.",
        "parent_id": "21",
        "parent_list": "186,21,241,-1",
        "child_list": "186,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    }
]
```

# Forumtag



## GET forumtag/all

Return All Tags

### HTTP Request

`GET /forumtag/all`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "forum": [
        {
            "forums": [
                {
                    "forum_id": "26",
                    "name": "Anime & Manga Haven",
                    "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang Anime, Manga dan Comics.",
                    "display_order": "20",
                    "visible": "1"
                }
            ],
            "tag_id": "58",
            "tag_name": "Technology",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021111902.png"
        },
        {
            "forums": [
                {
                    "forum_id": "634",
                    "name": "PILIH PARPOL",
                    "description": "Tempat khusus untuk membahas partai-partai PEMILU 2014 dan para calon legislatifnya",
                    "display_order": "100",
                    "visible": "1"
                },
                {
                    "forum_id": "35",
                    "name": "Sports",
                    "description": "Forum bagi penggemar berbagai jenis olah raga.",
                    "display_order": "340",
                    "visible": "1"
                }
            ],
            "tag_id": "25",
            "tag_name": "Sports & Adventure",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021111922.png"
        },
        {
            "forums": [
                {
                    "forum_id": "554",
                    "name": "BANNER TEST",
                    "description": "Forum ini adalah forum diskusi untuk testing banner preview",
                    "display_order": "9999",
                    "visible": "1"
                },
                {
                    "forum_id": "72",
                    "name": "REGIONAL",
                    "description": "Kenalan dan tahu lebih jauh dengan Kaskuser dari berbagai Regional, baik dalam & luar negeri. Saling berbagi pengalaman mengenai tempat-tempat yang pernah Agan kunjungi! ",
                    "display_order": "50",
                    "visible": "1"
                }
            ],
            "tag_id": "44",
            "tag_name": "Kasak Kusuk",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141013091140.png"
        },
        {
            "forums": [
                {
                    "forum_id": "635",
                    "name": "PILIH CAPRES",
                    "description": "Ruang utama untuk mendiskusikan calon-calon presiden PEMILU 2014\n",
                    "display_order": "110",
                    "visible": "1"
                }
            ],
            "tag_id": "28",
            "tag_name": "Life Corner",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112034.png"
        }
    ]
}
```

## GET forumtag/fjb

Return All FJB Tags

### HTTP Request

`GET /forumtag/fjb`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "data": [
        null,
        null,
        null,
        null,
        null,
        null,
        null,
        null,
        null
    ]
}
```

## GET forumtag/list_forum_tag

Return All Forum Tags

### HTTP Request

`GET /forumtag/list_forum_tag`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
[
    {
        "forum": [
            "72",
            "554"
        ],
        "tag_id": "44",
        "tag_name": "Kasak Kusuk",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141013091140.png"
    },
    {
        "forum": [
            "35",
            "634"
        ],
        "tag_id": "25",
        "tag_name": "Sports & Adventure",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021111922.png"
    },
    null,
    null,
    null,
    {
        "forum": [
            "26"
        ],
        "tag_id": "58",
        "tag_name": "Technology",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021111902.png"
    },
    {
        "forum": [
            "635"
        ],
        "tag_id": "28",
        "tag_name": "Life Corner",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112034.png"
    },
    null,
    null,
    null
]
```

## GET forumtag/list_forum_subscription

Return All Forum subscription Tags

### HTTP Request

`GET /forumtag/list_forum_subscription`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## GET forumtag/list_navigation_info

Return List navigation info

### HTTP Request

`GET /forumtag/list_navigation_info`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



# Friend



## GET friend

Get List of Currently logged in user's friend.

### HTTP Request

`GET /friend`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "total_friend": "0",
    "current_page": 1,
    "total_page": 0,
    "per_page": 10,
    "friends": []
}
```

## POST friend

Request friend

### HTTP Request

`POST /friend/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id that you want to be friend
output|output format (JSON or XML)



## DELETE friend

Unfriend user

### HTTP Request

`DELETE /friend/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id that you want to remove
output|output format (JSON or XML)



# Lapakinfo



## GET lapakinfo

Get forumlist, forumtag, location list, and lapak setting.

### HTTP Request

`GET /lapakinfo`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)
location_version|location list version




> Example response

```json
{
    "forumlist": [
        {
            "forum_id": "9",
            "name": "Jokes & Cartoon",
            "description": "Forum yang berisi kumpulan humor dari Kaskuser, siap ngakak Gan!",
            "parent_id": "241",
            "parent_list": "9,241,-1",
            "child_list": "9,331,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "10",
            "name": "Berita dan Politik",
            "description": "Forum diskusi dan berbagi berita dari dalam maupun luar negeri. Mulai dari ideologi, politik, ekonomi, sosial dan budaya.",
            "parent_id": "241",
            "parent_list": "10,241,-1",
            "child_list": "10,250,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-10.png"
        },
        {
            "forum_id": "11",
            "name": "Movies",
            "description": "Forum penggemar film, simak info terbaru seputar dunia perfilman, serial TV, sinetron hingga miniseri favorit.",
            "parent_id": "241",
            "parent_list": "11,241,-1",
            "child_list": "11,621,619,382,171,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "13",
            "name": "Website, Webmaster, Webdeveloper",
            "description": "Tempat diskusi teknis dan review seputar website, security, blogs, CMS, webhosting, filehoster, forum, board, mail, SEO, templates, snippets\/scripts, social bookmarking, social network.",
            "parent_id": "19",
            "parent_list": "13,19,241,-1",
            "child_list": "13,443,442,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
        },
        {
            "forum_id": "14",
            "name": "CCPB - Shareware & Freeware",
            "description": "Tempat berbagi trik dan aplikasi.",
            "parent_id": "19",
            "parent_list": "14,19,241,-1",
            "child_list": "14,391,419,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
        },
        {
            "forum_id": "15",
            "name": "Disturbing Picture",
            "description": "Forum kumpulan gambar-gambar 'Disturbing Picture'.",
            "parent_id": "241",
            "parent_list": "15,241,-1",
            "child_list": "15,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "16",
            "name": "Heart to Heart",
            "description": "Forum buat yang suka nulis, nge-blog, atau bikin puisi.",
            "parent_id": "241",
            "parent_list": "16,241,-1",
            "child_list": "16,49,50,51,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "18",
            "name": "Can You Solve This Game?",
            "description": "Forum berbagi tebak-tebakan, teka-teki, dan permainan sejenis.",
            "parent_id": "241",
            "parent_list": "18,241,-1",
            "child_list": "18,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "19",
            "name": "Computer Stuff",
            "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang komputer dan internet.",
            "parent_id": "241",
            "parent_list": "19,241,-1",
            "child_list": "19,14,391,419,243,557,183,397,65,383,569,568,176,13,443,442,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "21",
            "name": "The Lounge",
            "description": "Forum bagi Kaskuser untuk berbagi gosip, gambar, foto, dan video yang seru, lucu, serta unik.",
            "parent_id": "241",
            "parent_list": "21,241,-1",
            "child_list": "21,59,186,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
        },
        {
            "forum_id": "22",
            "name": "Buat Latihan Posting",
            "description": "Tempat untuk latihan membuat thread dan menggunakan fitur-fitur posting di KASKUS.",
            "parent_id": "103",
            "parent_list": "22,103,241,-1",
            "child_list": "22,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
        },
        {
            "forum_id": "23",
            "name": "Supranatural",
            "description": "Forum bagi penggemar supranatural baik yang berangkat dari budaya maupun yang terkait dengan dunia spiritual.",
            "parent_id": "241",
            "parent_list": "23,241,-1",
            "child_list": "23,389,173,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "24",
            "name": "Lifestyle",
            "description": "Forum tentang serba serbi gaya hidup, mulai dari hal inspiratif, fashion & event terkait lifestyle.",
            "parent_id": "241",
            "parent_list": "24,241,-1",
            "child_list": "24,306,249,275,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "26",
            "name": "Anime & Manga Haven",
            "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang Anime, Manga dan Comics.",
            "parent_id": "241",
            "parent_list": "26,241,-1",
            "child_list": "26,116,431,552,433,390,122,244,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "28",
            "name": "Otomotif",
            "description": "Forum diskusi dan berbagi segala sesuatu tentang dunia otomotif, info dan tren otomotif terbaru hingga tips & trik seputar perawatan kendaraan.",
            "parent_id": "241",
            "parent_list": "28,241,-1",
            "child_list": "28,112,570,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "29",
            "name": "Cooking & Resto Guide",
            "description": "Forum bagi penggemar masak-memasak dan pemburu kuliner seru.",
            "parent_id": "241",
            "parent_list": "29,241,-1",
            "child_list": "29,62,248,60,63,61,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "30",
            "name": "BISNIS",
            "description": "Forum diskusi tentang karir, dunia kerja dan wirausaha, informasi seputar lowongan kerja, peluang kerjasama, dan investasi.",
            "parent_id": "241",
            "parent_list": "30,241,-1",
            "child_list": "30,546,277,466,279,467,470,469,468,278,472,572,571,471,280,595,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "31",
            "name": "Kritik, Saran, Pertanyaan Seputar KASKUS",
            "description": "Tempat menampung kritik, saran dan request fitur KASKUS ke Moderator forum atau Admin. Posting selain tiga kategori diatas akan dihapus.",
            "parent_id": "103",
            "parent_list": "31,103,241,-1",
            "child_list": "31,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
        },
        {
            "forum_id": "32",
            "name": "Hewan Peliharaan",
            "description": "Forum diskusi dan berbagi informasi untuk penggemar dan pemilik berbagai jenis hewan.",
            "parent_id": "241",
            "parent_list": "32,241,-1",
            "child_list": "32,124,127,123,125,126,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "33",
            "name": "Music",
            "description": "Forum bagi pencinta segala jenis musik, untuk berbagi info perkembangan musik, ulasan musik, dan ngobrolin serunya KaskusRadio.com",
            "parent_id": "241",
            "parent_list": "33,241,-1",
            "child_list": "33,88,58,137,386,87,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "34",
            "name": "All About Design",
            "description": "Forum untuk berdiskusi segala sesuatu tentang desain (desain grafis, desain website, desain interior, motion design, dsb) termasuk tutorial, tips dan trik.",
            "parent_id": "241",
            "parent_list": "34,241,-1",
            "child_list": "34,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "35",
            "name": "Sports",
            "description": "Forum bagi penggemar berbagai jenis olah raga.",
            "parent_id": "241",
            "parent_list": "35,241,-1",
            "child_list": "35,187,440,276,332,144,545,538,539,104,565,537,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "36",
            "name": "Handphone & Tablet updated",
            "description": "Forum diskusi dan berbagi seputar handphone dan PDA. Mulai dari tren terbaru, tips dan trik, komparasi produk, games dan aplikasi hingga konsultasi sebelum membeli.",
            "parent_id": "241",
            "parent_list": "36,241,-1",
            "child_list": "36,577,307,415,413,417,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "37",
            "name": "Ragnarok Online",
            "description": "Tempat bagi Massively Multiplayer Online Role-Playing Game (MMORPG) Community yang memainkan Ragnarok",
            "parent_id": "100",
            "parent_list": "37,100,44,241,-1",
            "child_list": "37,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-100.png"
        },
        {
            "forum_id": "38",
            "name": "Web-based Games",
            "description": "Tempat diskusi seputar games yang dimainkan dari web browser.",
            "parent_id": "44",
            "parent_list": "38,44,241,-1",
            "child_list": "38,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
        },
        {
            "forum_id": "39",
            "name": "Girls & Boys's Corner",
            "description": "Forum tempat nanya dan meminta pendapat soal cowok ke Agan dan soal cewek ke Aganwati.",
            "parent_id": "241",
            "parent_list": "39,241,-1",
            "child_list": "39,114,105,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "40",
            "name": "Lounge Moderator Kaskus",
            "description": "Tempat untuk diskusi dan ngobrol antara sesama Moderator (Hijau) Kaskus",
            "parent_id": "4",
            "parent_list": "40,4,-1",
            "child_list": "40,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-4.png"
        },
        {
            "forum_id": "44",
            "name": "Games",
            "description": "Forumnya penggemar berbagai jenis game.",
            "parent_id": "241",
            "parent_list": "44,241,-1",
            "child_list": "44,119,100,37,528,38,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "49",
            "name": "B-Log Collections",
            "description": "Tempat Agan dan Aganwati ngeblog di KASKUS.",
            "parent_id": "16",
            "parent_list": "49,16,241,-1",
            "child_list": "49,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-16.png"
        },
        {
            "forum_id": "50",
            "name": "Poetry",
            "description": "Tempat berbaginya para pencinta puisi.",
            "parent_id": "16",
            "parent_list": "50,16,241,-1",
            "child_list": "50,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-16.png"
        },
        {
            "forum_id": "51",
            "name": "Stories from the Heart",
            "description": "Tempat memajang cerita karya Kaskuser.",
            "parent_id": "16",
            "parent_list": "51,16,241,-1",
            "child_list": "51,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-16.png"
        },
        {
            "forum_id": "54",
            "name": "Photography",
            "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang fotografi (amatir dan pro) termasuk tutorial, tips dan trik.",
            "parent_id": "241",
            "parent_list": "54,241,-1",
            "child_list": "54,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "58",
            "name": "KaskusRadio.com",
            "description": "Ngobrolin KaskusRadio, dari DJ hingga playlist. Mau band kamu di puter di KaskusRadio? Join IndieZone - http:\/\/kaskusradio.com\/indiezone",
            "parent_id": "33",
            "parent_list": "58,33,241,-1",
            "child_list": "58,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
        },
        {
            "forum_id": "59",
            "name": "Gosip Nyok!",
            "description": "Tempat bergosip bareng Kaskuser.",
            "parent_id": "21",
            "parent_list": "59,21,241,-1",
            "child_list": "59,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
        },
        {
            "forum_id": "60",
            "name": "Selera Nusantara (Indonesian Food)",
            "description": "Tempat membahas kuliner khas Indonesia.",
            "parent_id": "29",
            "parent_list": "60,29,241,-1",
            "child_list": "60,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
        },
        {
            "forum_id": "61",
            "name": "The Rest of the World (International Food)",
            "description": "Tempat membahas hidangan dari berbagai penjuru dunia lainnya, termasuk kuliner western dan european.",
            "parent_id": "29",
            "parent_list": "61,29,241,-1",
            "child_list": "61,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
        },
        {
            "forum_id": "62",
            "name": "Oriental Exotic (Asian food)",
            "description": "Tempat membahas kuliner khas Asia.",
            "parent_id": "29",
            "parent_list": "62,29,241,-1",
            "child_list": "62,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
        },
        {
            "forum_id": "63",
            "name": "The KASKUS Bar",
            "description": "Tempat membahas beragam jenis minuman.",
            "parent_id": "29",
            "parent_list": "63,29,241,-1",
            "child_list": "63,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
        },
        {
            "forum_id": "65",
            "name": "Linux dan OS Selain Microsoft & Mac",
            "description": "Tempat diskusi seputar sistem operasi Unix, Linux, dan sistem operasi lainnya (selain produk Microsoft & Mac).",
            "parent_id": "19",
            "parent_list": "65,19,241,-1",
            "child_list": "65,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
        },
        {
            "forum_id": "66",
            "name": "Buku",
            "description": "Forum bagi pecinta buku untuk berdiskusi dan berbagi ulasan bacaan favorit, sharing koleksi buku, dan ngobrolin trend perbukuan bareng komunitas.",
            "parent_id": "241",
            "parent_list": "66,241,-1",
            "child_list": "66,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "67",
            "name": "Education",
            "description": "Forum diskusi dan berbagi pengetahuan tentang buku, sejarah, ilmu misteri dunia. Serta kumpulan aktivitas dari beragam almamater.",
            "parent_id": "241",
            "parent_list": "67,241,-1",
            "child_list": "67,247,246,597,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "70",
            "name": "Model Kit & R\/C",
            "description": "Forum bagi para penggemar model kit & radio control.",
            "parent_id": "241",
            "parent_list": "70,241,-1",
            "child_list": "70,252,253,251,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "72",
            "name": "REGIONAL",
            "description": "Kenalan dan tahu lebih jauh dengan Kaskuser dari berbagai Regional, baik dalam & luar negeri. Saling berbagi pengalaman mengenai tempat-tempat yang pernah Agan kunjungi! ",
            "parent_id": "-1",
            "parent_list": "72,-1",
            "child_list": "72,617,83,76,421,425,96,423,109,115,108,540,90,77,477,74,384,79,106,80,475,157,82,85,129,476,73,463,427,458,89,164,405,107,412,407,654,78,626,585,599,457,181,653,627,564,598,111,160,402,84,459,167,587,567,555,403,651,452,411,652,133,583,628,92,461,162,146,385,91,462,584,561,170,179,166,460,161,97,543,586,548,398,145,93,156,81,117,158,194,478,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "73",
            "name": "Indonesia",
            "description": "",
            "parent_id": "72",
            "parent_list": "73,72,-1",
            "child_list": "73,463,427,458,89,164,405,107,412,407,654,78,626,585,599,457,181,653,627,564,598,111,160,402,84,459,167,587,567,555,403,651,452,411,652,133,583,628,92,461,162,146,385,91,462,584,561,170,179,166,460,161,97,543,586,548,398,145,93,156,81,117,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "74",
            "name": "Australia",
            "description": "",
            "parent_id": "72",
            "parent_list": "74,72,-1",
            "child_list": "74,384,79,106,80,475,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "76",
            "name": "USA",
            "description": "",
            "parent_id": "617",
            "parent_list": "76,617,72,-1",
            "child_list": "76,421,425,96,423,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "77",
            "name": "Singapore",
            "description": "",
            "parent_id": "109",
            "parent_list": "77,109,72,-1",
            "child_list": "77,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "78",
            "name": "DKI Jakarta",
            "description": "",
            "parent_id": "458",
            "parent_list": "78,458,73,72,-1",
            "child_list": "78,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "79",
            "name": "Melbourne",
            "description": "",
            "parent_id": "74",
            "parent_list": "79,74,72,-1",
            "child_list": "79,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "80",
            "name": "Sydney",
            "description": "",
            "parent_id": "74",
            "parent_list": "80,74,72,-1",
            "child_list": "80,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "81",
            "name": "Palembang",
            "description": "",
            "parent_id": "460",
            "parent_list": "81,460,73,72,-1",
            "child_list": "81,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "82",
            "name": "Germany",
            "description": "",
            "parent_id": "157",
            "parent_list": "82,157,72,-1",
            "child_list": "82,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "83",
            "name": "Canada",
            "description": "",
            "parent_id": "617",
            "parent_list": "83,617,72,-1",
            "child_list": "83,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "84",
            "name": "Yogyakarta",
            "description": "",
            "parent_id": "457",
            "parent_list": "84,457,73,72,-1",
            "child_list": "84,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "85",
            "name": "Netherlands",
            "description": "",
            "parent_id": "157",
            "parent_list": "85,157,72,-1",
            "child_list": "85,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "87",
            "name": "Music Review",
            "description": "Tempat khusus bagi yang ingin mempromosikan lagu, album atau band untuk direview Kaskuser. Review murni hasil tulisan sendiri, bukan copas dari situs lain.",
            "parent_id": "33",
            "parent_list": "87,33,241,-1",
            "child_list": "87,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
        },
        {
            "forum_id": "88",
            "name": "Help, Tips & Tutorial",
            "description": "Tempat berbagi ilmu seputar teknik, audio processing, mixing, musical instruments, dll.",
            "parent_id": "33",
            "parent_list": "88,33,241,-1",
            "child_list": "88,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
        },
        {
            "forum_id": "89",
            "name": "Bandung",
            "description": "",
            "parent_id": "458",
            "parent_list": "89,458,73,72,-1",
            "child_list": "89,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "90",
            "name": "Malaysia",
            "description": "",
            "parent_id": "109",
            "parent_list": "90,109,72,-1",
            "child_list": "90,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "91",
            "name": "Kalimantan Timur",
            "description": "",
            "parent_id": "461",
            "parent_list": "91,461,73,72,-1",
            "child_list": "91,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "92",
            "name": "Surabaya",
            "description": "",
            "parent_id": "459",
            "parent_list": "92,459,73,72,-1",
            "child_list": "92,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "93",
            "name": "Medan",
            "description": "",
            "parent_id": "460",
            "parent_list": "93,460,73,72,-1",
            "child_list": "93,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "94",
            "name": "Health & Medical",
            "description": "Forum diskusi seputar dunia pengobatan, baik pengobatan modern maupun alternatif\/tradisional. Silakan bergabung untuk konsultasi atau berbagi pengalaman seputar pengobatan.",
            "parent_id": "241",
            "parent_list": "94,241,-1",
            "child_list": "94,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "96",
            "name": "East USA",
            "description": "Eastern states (formerly New York)",
            "parent_id": "76",
            "parent_list": "96,76,617,72,-1",
            "child_list": "96,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "97",
            "name": "Bangka - Belitung",
            "description": "",
            "parent_id": "460",
            "parent_list": "97,460,73,72,-1",
            "child_list": "97,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "98",
            "name": "Outdoor Adventure & Nature Clubs",
            "description": "Forum bagi pecinta alam dan kegiataan outdoor serta para petualang.",
            "parent_id": "241",
            "parent_list": "98,241,-1",
            "child_list": "98,596,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "100",
            "name": "Online Games",
            "description": "Tempat diskusi seputar games yang membutuhkan jaringan komputer dan internet.",
            "parent_id": "44",
            "parent_list": "100,44,241,-1",
            "child_list": "100,37,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
        },
        {
            "forum_id": "103",
            "name": "Welcome to KASKUS",
            "description": "Forum untuk tahu dan mengulik lebih banyak tentang KASKUS.",
            "parent_id": "241",
            "parent_list": "103,241,-1",
            "child_list": "103,22,177,31,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "104",
            "name": "Soccer & Futsal Room",
            "description": "Ruang untuk para pecinta sepakbola dan futsal dan fans klub dari dalam dan luar negeri berkumpul, berdiskusi dan berbagi informasi.",
            "parent_id": "35",
            "parent_list": "104,35,241,-1",
            "child_list": "104,565,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "105",
            "name": "Ask da Girls",
            "description": "Apa kata Aganwati?",
            "parent_id": "39",
            "parent_list": "105,39,241,-1",
            "child_list": "105,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-39.png"
        },
        {
            "forum_id": "106",
            "name": "Perth",
            "description": "",
            "parent_id": "74",
            "parent_list": "106,74,72,-1",
            "child_list": "106,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "107",
            "name": "Bogor",
            "description": "",
            "parent_id": "458",
            "parent_list": "107,458,73,72,-1",
            "child_list": "107,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "108",
            "name": "Japan",
            "description": "",
            "parent_id": "109",
            "parent_list": "108,109,72,-1",
            "child_list": "108,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "109",
            "name": "Asia",
            "description": "",
            "parent_id": "72",
            "parent_list": "109,72,-1",
            "child_list": "109,115,108,540,90,77,477,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "111",
            "name": "Semarang",
            "description": "",
            "parent_id": "457",
            "parent_list": "111,457,73,72,-1",
            "child_list": "111,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "112",
            "name": "Kendaraan Roda 2",
            "description": "Tempat membahas kendaraan beroda dua (motor) dari segala brand (merek)",
            "parent_id": "28",
            "parent_list": "112,28,241,-1",
            "child_list": "112,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-28.png"
        },
        {
            "forum_id": "113",
            "name": "English",
            "description": "Forum untuk membahas dan mempelajari Bahasa Inggris.",
            "parent_id": "241",
            "parent_list": "113,241,-1",
            "child_list": "113,464,465,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "114",
            "name": "Ask da Boys",
            "description": "Apa kata Agan?",
            "parent_id": "39",
            "parent_list": "114,39,241,-1",
            "child_list": "114,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-39.png"
        },
        {
            "forum_id": "115",
            "name": "China",
            "description": "",
            "parent_id": "109",
            "parent_list": "115,109,72,-1",
            "child_list": "115,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "116",
            "name": "AMHelpdesk",
            "description": "Portal info, bantuan dan tutorial seputar Anime dan Manga.",
            "parent_id": "26",
            "parent_list": "116,26,241,-1",
            "child_list": "116,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
        },
        {
            "forum_id": "117",
            "name": "Riau Raya",
            "description": "",
            "parent_id": "460",
            "parent_list": "117,460,73,72,-1",
            "child_list": "117,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "119",
            "name": "Console & Handheld Games",
            "description": "Tempat diskusi seputar games yang dimainkan di console dan handheld. Termasuk Xbox, Xbox 360, PS2, PS3, GameCube, GBA\/DS, Gizmondo, N-Gage & PSP.",
            "parent_id": "44",
            "parent_list": "119,44,241,-1",
            "child_list": "119,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
        },
        {
            "forum_id": "122",
            "name": "Western Comic",
            "description": "Tempat untuk diskusi komik Western\/US",
            "parent_id": "26",
            "parent_list": "122,26,241,-1",
            "child_list": "122,244,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
        },
        {
            "forum_id": "123",
            "name": "Mamalia",
            "description": "Tempat untuk membahas binatang mamalia seperti anjing, kucing, hamster, macan, beruang, tupai, dsb.",
            "parent_id": "32",
            "parent_list": "123,32,241,-1",
            "child_list": "123,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
        },
        {
            "forum_id": "124",
            "name": "Burung",
            "description": "Tempat untuk membahas berbagai jenis unggas dan burung.",
            "parent_id": "32",
            "parent_list": "124,32,241,-1",
            "child_list": "124,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
        },
        {
            "forum_id": "125",
            "name": "Reptil",
            "description": "Tempat untuk membahas berbagai jenis reptil.",
            "parent_id": "32",
            "parent_list": "125,32,241,-1",
            "child_list": "125,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
        },
        {
            "forum_id": "126",
            "name": "Saltwater Fish",
            "description": "Tempat untuk membahas berbagai ikan laut.",
            "parent_id": "32",
            "parent_list": "126,32,241,-1",
            "child_list": "126,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
        },
        {
            "forum_id": "127",
            "name": "Freshwater Fish",
            "description": "Tempat untuk membahas ikan air tawar.",
            "parent_id": "32",
            "parent_list": "127,32,241,-1",
            "child_list": "127,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
        },
        {
            "forum_id": "129",
            "name": "United Kingdom",
            "description": "",
            "parent_id": "157",
            "parent_list": "129,157,72,-1",
            "child_list": "129,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "133",
            "name": "Malang",
            "description": "",
            "parent_id": "459",
            "parent_list": "133,459,73,72,-1",
            "child_list": "133,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "137",
            "name": "Music Corner",
            "description": "Tempat berbagi dan membahas MP3, lirik, video klip  karya musik solo dan band pribadi.",
            "parent_id": "33",
            "parent_list": "137,33,241,-1",
            "child_list": "137,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
        },
        {
            "forum_id": "140",
            "name": "Militer",
            "description": "Tempat diskusi tentang teknologi alat-alat militer, strategi, serta sejarah kemiliteran, di dalam maupun luar negeri.",
            "parent_id": "575",
            "parent_list": "140,575,241,-1",
            "child_list": "140,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-575.png"
        },
        {
            "forum_id": "144",
            "name": "Martial Arts",
            "description": "Tempat diskusi para praktisi beladiri tentang ilmu beladiri, tangan kosong mapun bersenjata, dari dalam dan luar negeri, baik modern dan tradisional.",
            "parent_id": "35",
            "parent_list": "144,35,241,-1",
            "child_list": "144,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "145",
            "name": "Lampung",
            "description": "",
            "parent_id": "460",
            "parent_list": "145,460,73,72,-1",
            "child_list": "145,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "146",
            "name": "Kalimantan Selatan",
            "description": "",
            "parent_id": "461",
            "parent_list": "146,461,73,72,-1",
            "child_list": "146,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "151",
            "name": "Gratisan",
            "description": "Aneka promo gratis",
            "parent_id": "25",
            "parent_list": "151,25,-1",
            "child_list": "151,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "156",
            "name": "Minangkabau",
            "description": "",
            "parent_id": "460",
            "parent_list": "156,460,73,72,-1",
            "child_list": "156,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "157",
            "name": "Europe",
            "description": "",
            "parent_id": "72",
            "parent_list": "157,72,-1",
            "child_list": "157,82,85,129,476,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "158",
            "name": "Regional Lainnya",
            "description": "",
            "parent_id": "72",
            "parent_list": "158,72,-1",
            "child_list": "158,194,478,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "160",
            "name": "Solo",
            "description": "",
            "parent_id": "457",
            "parent_list": "160,457,73,72,-1",
            "child_list": "160,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "161",
            "name": "Aceh",
            "description": "",
            "parent_id": "460",
            "parent_list": "161,460,73,72,-1",
            "child_list": "161,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "162",
            "name": "Kalimantan Barat",
            "description": "",
            "parent_id": "461",
            "parent_list": "162,461,73,72,-1",
            "child_list": "162,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "164",
            "name": "Banten",
            "description": "",
            "parent_id": "458",
            "parent_list": "164,458,73,72,-1",
            "child_list": "164,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "166",
            "name": "Palu",
            "description": "",
            "parent_id": "462",
            "parent_list": "166,462,73,72,-1",
            "child_list": "166,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "167",
            "name": "Bali",
            "description": "",
            "parent_id": "459",
            "parent_list": "167,459,73,72,-1",
            "child_list": "167,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "170",
            "name": "Makassar",
            "description": "",
            "parent_id": "462",
            "parent_list": "170,462,73,72,-1",
            "child_list": "170,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "171",
            "name": "TV",
            "description": "Forum untuk membahas segala jenis acara TV dari sinetron, mini series, dan lain lain.",
            "parent_id": "11",
            "parent_list": "171,11,241,-1",
            "child_list": "171,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-11.png"
        },
        {
            "forum_id": "173",
            "name": "Spiritual",
            "description": "Tempat membahas hal spiritual seperti meditasi, teknik relaksasi, dan pencerahan (tidak termasuk ilmu pelet, pengasihan, santet, dan penampakan makhluk halus).",
            "parent_id": "23",
            "parent_list": "173,23,241,-1",
            "child_list": "173,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-23.png"
        },
        {
            "forum_id": "176",
            "name": "Programmer Forum",
            "description": "Tempat diskusi dan belajar bahasa programming, dari pemula hingga pakar.",
            "parent_id": "19",
            "parent_list": "176,19,241,-1",
            "child_list": "176,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
        },
        {
            "forum_id": "177",
            "name": "Donatur Lounge",
            "description": "Tempat khusus untuk para KASKUS Donatur. Postingan hanya dapat dilihat oleh donatur.",
            "parent_id": "103",
            "parent_list": "177,103,241,-1",
            "child_list": "177,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
        },
        {
            "forum_id": "179",
            "name": "Manado",
            "description": "",
            "parent_id": "462",
            "parent_list": "179,462,73,72,-1",
            "child_list": "179,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "181",
            "name": "Banyumas",
            "description": "",
            "parent_id": "457",
            "parent_list": "181,457,73,72,-1",
            "child_list": "181,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "183",
            "name": "Internet Service & Networking",
            "description": "Tempat membahas internet service provider dan networking (hardware & tutorial).",
            "parent_id": "19",
            "parent_list": "183,19,241,-1",
            "child_list": "183,397,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
        },
        {
            "forum_id": "186",
            "name": "Lounge Pictures & Video",
            "description": "Tempat berbagi kumpulan gambar menarik, seru, lucu, dan unik.",
            "parent_id": "21",
            "parent_list": "186,21,241,-1",
            "child_list": "186,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
        },
        {
            "forum_id": "187",
            "name": "Airsoft Indonesia",
            "description": "Tempat diskusi para pecinta airsoft.",
            "parent_id": "35",
            "parent_list": "187,35,241,-1",
            "child_list": "187,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "188",
            "name": "Surat Pembaca",
            "description": "Tempat berbagi keluh kesah seputar pelayanan publik atau produk tertentu secara bertanggung jawab, dengan memberi masukan untuk pelayanan yang lebih baik (bukan untuk menjatuhkan kredibilitas).",
            "parent_id": "241",
            "parent_list": "188,241,-1",
            "child_list": "188,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "191",
            "name": "Debate Club",
            "description": "Forum berbagi dan menyatakan perbedaan pendapat dan pandangan",
            "parent_id": "241",
            "parent_list": "191,241,-1",
            "child_list": "191,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "192",
            "name": "Tanaman",
            "description": "Forum diskusi dan berbagi informasi untuk penggemar tanaman atau tumbuhan.",
            "parent_id": "241",
            "parent_list": "192,241,-1",
            "child_list": "192,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "193",
            "name": "Wedding & Family",
            "description": "Forum diskusi dan berbagi informasi seputar pernikahan, keluarga & anak.",
            "parent_id": "241",
            "parent_list": "193,241,-1",
            "child_list": "193,429,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "194",
            "name": "Timur Tengah",
            "description": "",
            "parent_id": "158",
            "parent_list": "194,158,72,-1",
            "child_list": "194,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "195",
            "name": "Elektronik",
            "description": "Jual beli beragam jenis barang elektronik",
            "parent_id": "25",
            "parent_list": "195,25,-1",
            "child_list": "195,313,255,254,212,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "196",
            "name": "Fashion & Mode",
            "description": "Jual beli barang fashion untuk pria dan wanita",
            "parent_id": "25",
            "parent_list": "196,25,-1",
            "child_list": "196,216,451,450,302,449,624,600,215,257,310,311,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "197",
            "name": "Flora & Fauna",
            "description": "Jual beli tanaman hias dan hewan peliharaan (kecuali yang dilindungi)",
            "parent_id": "25",
            "parent_list": "197,25,-1",
            "child_list": "197,218,219,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "198",
            "name": "Koleksi, Hobi & Mainan",
            "description": "Jual beli barang koleksi, hobi dan mainan",
            "parent_id": "25",
            "parent_list": "198,25,-1",
            "child_list": "198,261,231,262,444,606,233,291,590,292,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "199",
            "name": "Properti",
            "description": "Jual beli properti",
            "parent_id": "25",
            "parent_list": "199,25,-1",
            "child_list": "199,223,225,222,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "200",
            "name": "CD & DVD",
            "description": "Jual beli CD\/DVD",
            "parent_id": "25",
            "parent_list": "200,25,-1",
            "child_list": "200,266,265,329,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "201",
            "name": "Makanan & Minuman",
            "description": "Jual beli aneka makanan dan minuman (HARUS halal)",
            "parent_id": "25",
            "parent_list": "201,25,-1",
            "child_list": "201,228,607,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "202",
            "name": "Jasa",
            "description": "Penawaran aneka jasa",
            "parent_id": "25",
            "parent_list": "202,25,-1",
            "child_list": "202,269,268,553,631,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "204",
            "name": "FJB Feedback & Testimonials",
            "description": "Sebelum posting, silakan cek petunjuk, tips, tutorial dari Kaskuser",
            "parent_id": "25",
            "parent_list": "204,25,-1",
            "child_list": "204,270,566,271,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "205",
            "name": "Otomotif",
            "description": "Jual beli mobil\/motor, aksesoris dan suku cadang",
            "parent_id": "25",
            "parent_list": "205,25,-1",
            "child_list": "205,333,334,206,207,208,256,209,593,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "206",
            "name": "Audio, Video",
            "description": "Khusus Audio, Video untuk mobil (tape, tv head unit, dll)",
            "parent_id": "205",
            "parent_list": "206,205,25,-1",
            "child_list": "206,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
        },
        {
            "forum_id": "207",
            "name": "Interior, Exterior",
            "description": "Khusus interior, exterior",
            "parent_id": "205",
            "parent_list": "207,205,25,-1",
            "child_list": "207,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
        },
        {
            "forum_id": "208",
            "name": "Mobil",
            "description": "Aneka merk mobil",
            "parent_id": "205",
            "parent_list": "208,205,25,-1",
            "child_list": "208,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
        },
        {
            "forum_id": "209",
            "name": "Motor",
            "description": "Aneka merk motor",
            "parent_id": "205",
            "parent_list": "209,205,25,-1",
            "child_list": "209,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
        },
        {
            "forum_id": "210",
            "name": "Handphone & Tablet updated",
            "description": "Jual beli Handphone dan PDA",
            "parent_id": "25",
            "parent_list": "210,25,-1",
            "child_list": "210,527,574,381,573,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "212",
            "name": "Tablet dan Aksesoris",
            "description": "Tempat untuk berjualan Tablet (iPad, Tab, Kindle, Playbook dll)",
            "parent_id": "195",
            "parent_list": "212,195,25,-1",
            "child_list": "212,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-195.png"
        },
        {
            "forum_id": "215",
            "name": "Produk Distro",
            "description": "Barang fashion khusus produk\/merk sendiri",
            "parent_id": "196",
            "parent_list": "215,196,25,-1",
            "child_list": "215,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "216",
            "name": "Aksesoris",
            "description": "Ikat pinggang, dasi dan topi",
            "parent_id": "196",
            "parent_list": "216,196,25,-1",
            "child_list": "216,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "218",
            "name": "Flora (Tumbuhan)",
            "description": "Tanaman hias (dilarang berjualan tanaman\/ tumbuhan dilindungi)",
            "parent_id": "197",
            "parent_list": "218,197,25,-1",
            "child_list": "218,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-197.png"
        },
        {
            "forum_id": "219",
            "name": "Fauna (Hewan)",
            "description": "Hewan peliharaan (dilarang berjualan hewan dilindungi)",
            "parent_id": "197",
            "parent_list": "219,197,25,-1",
            "child_list": "219,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-197.png"
        },
        {
            "forum_id": "220",
            "name": "Alat-Alat Olahraga",
            "description": "Jual beli pakaian, sepatu dan perlengkapan olahraga",
            "parent_id": "25",
            "parent_list": "220,25,-1",
            "child_list": "220,589,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "221",
            "name": "Alat-Alat Musik",
            "description": "Jual beli alat musik dan perlengkapan studio",
            "parent_id": "25",
            "parent_list": "221,25,-1",
            "child_list": "221,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "222",
            "name": "Tanah",
            "description": "Khusus tanah beragam lokasi",
            "parent_id": "199",
            "parent_list": "222,199,25,-1",
            "child_list": "222,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-199.png"
        },
        {
            "forum_id": "223",
            "name": "Rumah",
            "description": "Khusus rumah beragam lokasi",
            "parent_id": "199",
            "parent_list": "223,199,25,-1",
            "child_list": "223,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-199.png"
        },
        {
            "forum_id": "225",
            "name": "Sewa Menyewa",
            "description": "Khusus sewa menyewa properti",
            "parent_id": "199",
            "parent_list": "225,199,25,-1",
            "child_list": "225,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-199.png"
        },
        {
            "forum_id": "227",
            "name": "Buku",
            "description": "Jual beli beragam jenis buku",
            "parent_id": "25",
            "parent_list": "227,25,-1",
            "child_list": "227,264,625,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "228",
            "name": "Makanan",
            "description": "Khusus aneka makanan (HARUS halal)",
            "parent_id": "201",
            "parent_list": "228,201,25,-1",
            "child_list": "228,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-201.png"
        },
        {
            "forum_id": "229",
            "name": "Obat-obatan",
            "description": "Jual beli segala jenis obat-obatan (HARUS aman dikonsumsi konsumen)",
            "parent_id": "25",
            "parent_list": "229,25,-1",
            "child_list": "229,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "231",
            "name": "Airsoft",
            "description": "Khusus airsoft",
            "parent_id": "198",
            "parent_list": "231,198,25,-1",
            "child_list": "231,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "233",
            "name": "Model Kit",
            "description": "Khusus model kit (lihat aturan main sebelum transaksi)",
            "parent_id": "198",
            "parent_list": "233,198,25,-1",
            "child_list": "233,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "234",
            "name": "Arsitektur",
            "description": "Tempat diskusi seputar arsitektur, baik keilmuan maupun terapan, termasuk cara membangun dan mendesain rumah.",
            "parent_id": "578",
            "parent_list": "234,578,241,-1",
            "child_list": "234,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-578.png"
        },
        {
            "forum_id": "235",
            "name": "Travellers",
            "description": "Forum diskusi para penggemar jalan-jalan. Tempat berbagi ulasan tempat wisata dan tips berwisata.",
            "parent_id": "241",
            "parent_list": "235,241,-1",
            "child_list": "235,437,439,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "236",
            "name": "Fitness & Muscle Building",
            "description": "Tempat diskusi dan berbagi cara meningkatkan massa, kekuatan, performa dan kekencangan otot dari tingkat pemula, lanjutan, dan tingkat atlet untuk body fitness.",
            "parent_id": "558",
            "parent_list": "236,558,241,-1",
            "child_list": "236,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
        },
        {
            "forum_id": "240",
            "name": "KASKUS Peduli",
            "description": "Forum berisi informasi mengenai berbagai kegiatan bakti sosial yang diselenggarakan oleh KASKUS bersama dengan Kaskuser.",
            "parent_id": "239",
            "parent_list": "240,239,-1",
            "child_list": "240,549,473,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
        },
        {
            "forum_id": "243",
            "name": "Hardware Computer",
            "description": "Tempat diskusi computer hardware: updates, problems, drivers, peripheral, performance, upgrade, overclocking, showcase, dan konsultasi.",
            "parent_id": "19",
            "parent_list": "243,19,241,-1",
            "child_list": "243,557,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
        },
        {
            "forum_id": "244",
            "name": "Latest Release",
            "description": "Tempat berbagi dan kumpulan informasi rilis terbaru.",
            "parent_id": "122",
            "parent_list": "244,122,26,241,-1",
            "child_list": "244,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-122.png"
        },
        {
            "forum_id": "246",
            "name": "Sejarah & Xenology",
            "description": "Tempat membahas sejarah\/biografi tokoh dalam dan luar negeri. Juga diskusi tentang xenology (ilmu yang membahas misteri-misteri dunia).",
            "parent_id": "67",
            "parent_list": "246,67,241,-1",
            "child_list": "246,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-67.png"
        },
        {
            "forum_id": "247",
            "name": "Civitas Academica",
            "description": "Tempat kumpul alumni dan siswa dari beragam almamater. Saling berbagi info lowongan kerja, acara reuni, dan kondisi terbaru sekolah atau universitas.",
            "parent_id": "67",
            "parent_list": "247,67,241,-1",
            "child_list": "247,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-67.png"
        },
        {
            "forum_id": "248",
            "name": "Restaurant Review",
            "description": "Tempat berbagi pengalaman makan dan ulasan seputar resto (menu, tempat, promo).",
            "parent_id": "29",
            "parent_list": "248,29,241,-1",
            "child_list": "248,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-29.png"
        },
        {
            "forum_id": "249",
            "name": "Inspirasi",
            "description": "Berbagi tips dan masukan inspirasional, serta motivasi dari dan untuk Kaskuser.",
            "parent_id": "24",
            "parent_list": "249,24,241,-1",
            "child_list": "249,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-24.png"
        },
        {
            "forum_id": "250",
            "name": "Berita Luar Negeri",
            "description": "Tempat diskusi mengenai berita dari luar negeri.",
            "parent_id": "10",
            "parent_list": "250,10,241,-1",
            "child_list": "250,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-10.png"
        },
        {
            "forum_id": "251",
            "name": "Plamo",
            "description": "Tempat berbagi info tentang plastic model kit, dari mobil, military sampai Gundam.",
            "parent_id": "70",
            "parent_list": "251,70,241,-1",
            "child_list": "251,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-70.png"
        },
        {
            "forum_id": "252",
            "name": "Figures",
            "description": "Tempat berbagi segala sesuatu tentang figures baik resin, die-cast, gashapon maupun poseable action figures.",
            "parent_id": "70",
            "parent_list": "252,70,241,-1",
            "child_list": "252,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-70.png"
        },
        {
            "forum_id": "253",
            "name": "Gallery & Tutorial",
            "description": "Tempat berbagi tutorial dan gallery baik yang sudah selesai maupun work in progress (WIP).",
            "parent_id": "70",
            "parent_list": "253,70,241,-1",
            "child_list": "253,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-70.png"
        },
        {
            "forum_id": "254",
            "name": "TV, LCD & Projector",
            "description": "TV, LCD & Projector",
            "parent_id": "195",
            "parent_list": "254,195,25,-1",
            "child_list": "254,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-195.png"
        },
        {
            "forum_id": "255",
            "name": "Home Theatre, Sound System",
            "description": "Home Theater & Sound",
            "parent_id": "195",
            "parent_list": "255,195,25,-1",
            "child_list": "255,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-195.png"
        },
        {
            "forum_id": "256",
            "name": "Mobil & Motor Antik",
            "description": "Aneka mobil\/motor antik",
            "parent_id": "205",
            "parent_list": "256,205,25,-1",
            "child_list": "256,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
        },
        {
            "forum_id": "257",
            "name": "Sepatu, Sandal",
            "description": "Sepatu dan sandal beragam merk",
            "parent_id": "196",
            "parent_list": "257,196,25,-1",
            "child_list": "257,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "261",
            "name": "Action Figures",
            "description": "Khusus action figures",
            "parent_id": "198",
            "parent_list": "261,198,25,-1",
            "child_list": "261,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "262",
            "name": "Cards",
            "description": "Koleksi kartu",
            "parent_id": "198",
            "parent_list": "262,198,25,-1",
            "child_list": "262,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "263",
            "name": "KASKUS Celeb",
            "description": "Forum untuk membahas kumpulan celebrities yang Ngaskus.",
            "parent_id": "239",
            "parent_list": "263,239,-1",
            "child_list": "263,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
        },
        {
            "forum_id": "264",
            "name": "Buku Pelajaran",
            "description": "Buku pelajaran SD, SMP, SMA dan Kuliah",
            "parent_id": "227",
            "parent_list": "264,227,25,-1",
            "child_list": "264,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-227.png"
        },
        {
            "forum_id": "265",
            "name": "Film",
            "description": "CD\/DVD (film, blueray dan hd-dvd)",
            "parent_id": "200",
            "parent_list": "265,200,25,-1",
            "child_list": "265,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-200.png"
        },
        {
            "forum_id": "266",
            "name": "Audio",
            "description": "CD\/DVD (musik)",
            "parent_id": "200",
            "parent_list": "266,200,25,-1",
            "child_list": "266,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-200.png"
        },
        {
            "forum_id": "268",
            "name": "Jasa Rumah Tangga",
            "description": "Jasa kebutuhan rumah tangga",
            "parent_id": "202",
            "parent_list": "268,202,25,-1",
            "child_list": "268,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-202.png"
        },
        {
            "forum_id": "269",
            "name": "Fotografi",
            "description": "Jasa fotografi",
            "parent_id": "202",
            "parent_list": "269,202,25,-1",
            "child_list": "269,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-202.png"
        },
        {
            "forum_id": "270",
            "name": "Blacklist",
            "description": "Daftar hitam Kaskuser nakal",
            "parent_id": "204",
            "parent_list": "270,204,25,-1",
            "child_list": "270,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-204.png"
        },
        {
            "forum_id": "271",
            "name": "Official Testimonials",
            "description": "Kirimkan pengalaman \/ testimonial anda berjualan atau berinteraksi di forum Kaskus yang mengubah hidup anda. Testimonial yang terpilih akan kami cantumkan di category ini. Kirim ke testimonial@kaskusnetworks.com",
            "parent_id": "204",
            "parent_list": "271,204,25,-1",
            "child_list": "271,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-204.png"
        },
        {
            "forum_id": "272",
            "name": "FJB Tips & Tutorial",
            "description": "Kumpulan tips dan tutorial seputar Forum Jual Beli Kaskus",
            "parent_id": "25",
            "parent_list": "272,25,-1",
            "child_list": "272,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "273",
            "name": "Product Review",
            "description": "Ulasan seputar produk",
            "parent_id": "25",
            "parent_list": "273,25,-1",
            "child_list": "273,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "274",
            "name": "Fat-loss, Diet & Nutrition",
            "description": "Tempat diskusi tentang kandungan nutrisi dalam makanan, cara sehat turun berat badan, dan solusi mencegah kolesterol, diabetes, dan penyakit lainnya.",
            "parent_id": "558",
            "parent_list": "274,558,241,-1",
            "child_list": "274,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
        },
        {
            "forum_id": "275",
            "name": "Nightlife & Events",
            "description": "Tempat berbagi informasi mengenai event dan promosi yang terkait dengan lifestyle.",
            "parent_id": "24",
            "parent_list": "275,24,241,-1",
            "child_list": "275,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-24.png"
        },
        {
            "forum_id": "276",
            "name": "Grappling",
            "description": "Tempat berkumpulnya para pecinta olahraga grappling. ",
            "parent_id": "35",
            "parent_list": "276,35,241,-1",
            "child_list": "276,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "277",
            "name": "Entrepreneur Corner",
            "description": "Tempat diskusi seputar dunia wirausaha. Dilarang promosi disini.",
            "parent_id": "30",
            "parent_list": "277,30,241,-1",
            "child_list": "277,466,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "278",
            "name": "Lowongan Kerja",
            "description": "Tempat kumpulan informasi mengenai lowongan pekerjaan.",
            "parent_id": "30",
            "parent_list": "278,30,241,-1",
            "child_list": "278,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "279",
            "name": "Forex, Option, Saham, & Derivatifnya",
            "description": "Tempat berbagi dan belajar teknikal, fundamental dan psikologi trade forex, option, saham dan derivatifnya.",
            "parent_id": "30",
            "parent_list": "279,30,241,-1",
            "child_list": "279,467,470,469,468,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "280",
            "name": "HYIP \/ Money Game \/ PTC \/ Autosurf",
            "description": "",
            "parent_id": "471",
            "parent_list": "280,471,30,241,-1",
            "child_list": "280,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-471.png"
        },
        {
            "forum_id": "281",
            "name": "Gadget & Gizmo",
            "description": "Forum diskusi dan berbagi informasi seputar gadget, tren dan perkembangan gadget terbaru, hingga ulasan tentang gadget tertentu.",
            "parent_id": "241",
            "parent_list": "281,241,-1",
            "child_list": "281,282,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "282",
            "name": "Audio & Video",
            "description": "Tempat khusus membahas peralatan audio dan video",
            "parent_id": "281",
            "parent_list": "282,281,241,-1",
            "child_list": "282,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-281.png"
        },
        {
            "forum_id": "283",
            "name": "Antik",
            "description": "Jual beli benda menarik, kuno dan unik",
            "parent_id": "25",
            "parent_list": "283,25,-1",
            "child_list": "283,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "284",
            "name": "Karya Seni & Desain",
            "description": "Jual beli barang seni dan penawaran jasa desain",
            "parent_id": "25",
            "parent_list": "284,25,-1",
            "child_list": "284,603,285,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "285",
            "name": "Lukisan",
            "description": "Beragam lukisan",
            "parent_id": "284",
            "parent_list": "285,284,25,-1",
            "child_list": "285,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-284.png"
        },
        {
            "forum_id": "286",
            "name": "Industri & Supplier",
            "description": "Jual beli barang & bahan baku industri",
            "parent_id": "25",
            "parent_list": "286,25,-1",
            "child_list": "286,287,448,288,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "287",
            "name": "Alat Berat",
            "description": "Mesin pabrik\/ industri.",
            "parent_id": "286",
            "parent_list": "287,286,25,-1",
            "child_list": "287,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-286.png"
        },
        {
            "forum_id": "288",
            "name": "Peralatan Food & Beverage",
            "description": "Alat masak\/industri katering",
            "parent_id": "286",
            "parent_list": "288,286,25,-1",
            "child_list": "288,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-286.png"
        },
        {
            "forum_id": "291",
            "name": "Perangko",
            "description": "Khusus perangko",
            "parent_id": "198",
            "parent_list": "291,198,25,-1",
            "child_list": "291,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "292",
            "name": "Uang Lama",
            "description": "Khusus uang lama (koin, uang kertas)",
            "parent_id": "198",
            "parent_list": "292,198,25,-1",
            "child_list": "292,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "293",
            "name": "Kamera & Aksesoris",
            "description": "Jual beli kamera dan aksesoris",
            "parent_id": "25",
            "parent_list": "293,25,-1",
            "child_list": "293,604,605,294,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "294",
            "name": "Kamera Video",
            "description": "Kamera video beragam merk",
            "parent_id": "293",
            "parent_list": "294,293,25,-1",
            "child_list": "294,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-293.png"
        },
        {
            "forum_id": "295",
            "name": "Perawatan Tubuh & Wajah",
            "description": "Jual beli aneka produk kesehatan dan kecantikan",
            "parent_id": "25",
            "parent_list": "295,25,-1",
            "child_list": "295,608,609,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "296",
            "name": "Furniture",
            "description": "Jual beli mebel (kursi, meja, lemari dsb)",
            "parent_id": "25",
            "parent_list": "296,25,-1",
            "child_list": "296,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "297",
            "name": "Video Games",
            "description": "Jual beli games dan konsol",
            "parent_id": "25",
            "parent_list": "297,25,-1",
            "child_list": "297,612,613,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "298",
            "name": "Perkakas",
            "description": "Jual beli aneka perkakas",
            "parent_id": "25",
            "parent_list": "298,25,-1",
            "child_list": "298,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "299",
            "name": "Kerajinan Tangan",
            "description": "Jual beli aneka kerajinan tangan",
            "parent_id": "25",
            "parent_list": "299,25,-1",
            "child_list": "299,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "300",
            "name": "Perlengkapan Kantor",
            "description": "Jual beli perlengkapan kantor",
            "parent_id": "25",
            "parent_list": "300,25,-1",
            "child_list": "300,312,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "302",
            "name": "Jam Tangan",
            "description": "Jam tangan",
            "parent_id": "196",
            "parent_list": "302,196,25,-1",
            "child_list": "302,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "303",
            "name": "Perlengkapan Rumah Tangga",
            "description": "Jual beli perlengkapan rumah tangga (sub kategori terkait, cek elektronik rumah tangga)",
            "parent_id": "25",
            "parent_list": "303,25,-1",
            "child_list": "303,314,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "304",
            "name": "Tur & Paket Perjalanan",
            "description": "Penawaran aneka tur dan paket wisata",
            "parent_id": "25",
            "parent_list": "304,25,-1",
            "child_list": "304,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "305",
            "name": "Perlengkapan Anak & Bayi",
            "description": "Jual beli pakaian, perlengkapan bayi dan anak-anak",
            "parent_id": "25",
            "parent_list": "305,25,-1",
            "child_list": "305,447,446,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "306",
            "name": "Fashion",
            "description": "Tempat diskusi dan membahas tren fashion, serta update informasi fashion terkini.",
            "parent_id": "24",
            "parent_list": "306,24,241,-1",
            "child_list": "306,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-24.png"
        },
        {
            "forum_id": "307",
            "name": "BlackBerry Corner",
            "description": "Diskusi khusus mengenai Blackberry",
            "parent_id": "36",
            "parent_list": "307,36,241,-1",
            "child_list": "307,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
        },
        {
            "forum_id": "310",
            "name": "Tas, Dompet",
            "description": "Tas, dompet dan clutch beragam merk",
            "parent_id": "196",
            "parent_list": "310,196,25,-1",
            "child_list": "310,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "311",
            "name": "Tradisional",
            "description": "Pakaian dan kain tradisional (batik, songket, kebaya dsb)",
            "parent_id": "196",
            "parent_list": "311,196,25,-1",
            "child_list": "311,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "312",
            "name": "Stationery",
            "description": "Alat tulis, kertas dsb",
            "parent_id": "300",
            "parent_list": "312,300,25,-1",
            "child_list": "312,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-300.png"
        },
        {
            "forum_id": "313",
            "name": "Elektronik Rumah Tangga",
            "description": "Kebutuhan rumah tangga (Kulkas, Mesin Cuci, Pompa dsb)",
            "parent_id": "195",
            "parent_list": "313,195,25,-1",
            "child_list": "313,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-195.png"
        },
        {
            "forum_id": "314",
            "name": "Pecah Belah & Alat Makan",
            "description": "Khusus pecah belah, alat makan",
            "parent_id": "303",
            "parent_list": "314,303,25,-1",
            "child_list": "314,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-303.png"
        },
        {
            "forum_id": "316",
            "name": "Tiket",
            "description": "Jual beli tiket",
            "parent_id": "25",
            "parent_list": "316,25,-1",
            "child_list": "316,610,611,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "317",
            "name": "Komputer",
            "description": "Jual beli komputer (hardware, software)",
            "parent_id": "25",
            "parent_list": "317,25,-1",
            "child_list": "317,330,328,318,323,327,321,324,325,319,326,320,322,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "318",
            "name": "Desktop",
            "description": "Khusus desktop",
            "parent_id": "317",
            "parent_list": "318,317,25,-1",
            "child_list": "318,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "319",
            "name": "Notebook, Laptop",
            "description": "Khusus Notebook, Laptop",
            "parent_id": "317",
            "parent_list": "319,317,25,-1",
            "child_list": "319,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "320",
            "name": "Processors  & Motherboards",
            "description": "Khusus Processors, Motherboards",
            "parent_id": "317",
            "parent_list": "320,317,25,-1",
            "child_list": "320,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "321",
            "name": "Memory",
            "description": "Khusus Memory",
            "parent_id": "317",
            "parent_list": "321,317,25,-1",
            "child_list": "321,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "322",
            "name": "Sound, Graphics & Video Cards",
            "description": "Khusus sound, graphics & videocards",
            "parent_id": "317",
            "parent_list": "322,317,25,-1",
            "child_list": "322,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "323",
            "name": "Drives & Storage",
            "description": "Khusus Drives & Storage",
            "parent_id": "317",
            "parent_list": "323,317,25,-1",
            "child_list": "323,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "324",
            "name": "Monitor, Display",
            "description": "Khusus monitor, display",
            "parent_id": "317",
            "parent_list": "324,317,25,-1",
            "child_list": "324,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "325",
            "name": "Networking, Communications",
            "description": "Khusus networking, communications",
            "parent_id": "317",
            "parent_list": "325,317,25,-1",
            "child_list": "325,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "326",
            "name": "Printers, Scanners & Inks",
            "description": "Khusus printers, scanners & inks",
            "parent_id": "317",
            "parent_list": "326,317,25,-1",
            "child_list": "326,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "327",
            "name": "Keyboard, Mouse, Input",
            "description": "Khusus keyboard, mouse, input",
            "parent_id": "317",
            "parent_list": "327,317,25,-1",
            "child_list": "327,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "328",
            "name": "Casing, Power Supply, Cooling",
            "description": "Khusus casing, power supplies, cooling",
            "parent_id": "317",
            "parent_list": "328,317,25,-1",
            "child_list": "328,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "329",
            "name": "Software Original & Open Source",
            "description": "CD\/DVD (software original dan Open Source)",
            "parent_id": "200",
            "parent_list": "329,200,25,-1",
            "child_list": "329,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-200.png"
        },
        {
            "forum_id": "330",
            "name": "Aksesoris Komputer & Laptop",
            "description": "Khusus aksesoris komputer & laptop meliputi NoteBook, NetBook, LifeBook.",
            "parent_id": "317",
            "parent_list": "330,317,25,-1",
            "child_list": "330,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-317.png"
        },
        {
            "forum_id": "331",
            "name": "Pictures",
            "description": "Tempat kumpulan gambar-gambar lucu.",
            "parent_id": "9",
            "parent_list": "331,9,241,-1",
            "child_list": "331,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-9.png"
        },
        {
            "forum_id": "332",
            "name": "Racing \/ Balap",
            "description": "Tempat diskusi serta berbagi informasi tentang dunia balap di dalam dan luar negeri.",
            "parent_id": "35",
            "parent_list": "332,35,241,-1",
            "child_list": "332,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "333",
            "name": "Aksesoris Motor",
            "description": "Khusus aksesoris motor",
            "parent_id": "205",
            "parent_list": "333,205,25,-1",
            "child_list": "333,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
        },
        {
            "forum_id": "334",
            "name": "Aksesoris Mobil",
            "description": "Khusus aksesoris mobil",
            "parent_id": "205",
            "parent_list": "334,205,25,-1",
            "child_list": "334,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
        },
        {
            "forum_id": "381",
            "name": "Kartu Perdana",
            "description": "Khusus jual beli kartu-kartu perdana",
            "parent_id": "210",
            "parent_list": "381,210,25,-1",
            "child_list": "381,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-210.png"
        },
        {
            "forum_id": "382",
            "name": "KASKUS Theater",
            "description": "Forum untuk membahas film karya sendiri\/ independen.",
            "parent_id": "11",
            "parent_list": "382,11,241,-1",
            "child_list": "382,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-11.png"
        },
        {
            "forum_id": "383",
            "name": "Macintosh",
            "description": "Tempat diskusi dan berbagi informasi tentang produk Macintosh, baik hardware maupun software.",
            "parent_id": "19",
            "parent_list": "383,19,241,-1",
            "child_list": "383,569,568,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
        },
        {
            "forum_id": "384",
            "name": "Brisbane",
            "description": "Buat kaskuer yg tinggal or pernah tinggal di Brisbane, ngumpul yuk disini!",
            "parent_id": "74",
            "parent_list": "384,74,72,-1",
            "child_list": "384,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "385",
            "name": "Kalimantan Tengah",
            "description": "",
            "parent_id": "461",
            "parent_list": "385,461,73,72,-1",
            "child_list": "385,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "386",
            "name": "Music Event",
            "description": "Tempat berbagi info seputar event musik dan pengalaman Kaskuser (baik gigs report band Indie maupun musisi mainstream).",
            "parent_id": "33",
            "parent_list": "386,33,241,-1",
            "child_list": "386,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
        },
        {
            "forum_id": "387",
            "name": "Ilmu Marketing",
            "description": "Forum diskusi seputar dunia marketing, baik keilmuan maupun terapan",
            "parent_id": "241",
            "parent_list": "387,241,-1",
            "child_list": "387,388,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "388",
            "name": "Ilmu Marketing & Research",
            "description": "Tempat diskusi dan membahas dasar-dasar ilmu marketing, serta berbagi hasil penelitian terkait marketing.",
            "parent_id": "387",
            "parent_list": "388,387,241,-1",
            "child_list": "388,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-387.png"
        },
        {
            "forum_id": "389",
            "name": "Budaya",
            "description": "Tempat berbagi hal-hal yang terkait dengan budaya dan adat istiadat Nusantara",
            "parent_id": "23",
            "parent_list": "389,23,241,-1",
            "child_list": "389,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-23.png"
        },
        {
            "forum_id": "390",
            "name": "TokuSenKa",
            "description": "Tempat untuk diskusi Tokusatsu, Super Sentai dan Kaijuu",
            "parent_id": "26",
            "parent_list": "390,26,241,-1",
            "child_list": "390,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
        },
        {
            "forum_id": "391",
            "name": "REQUEST @ CCPB",
            "description": "Tempat berbagi kumpulan Windows-based applications.",
            "parent_id": "14",
            "parent_list": "391,14,19,241,-1",
            "child_list": "391,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-14.png"
        },
        {
            "forum_id": "392",
            "name": "Hobby & Community",
            "description": "Forum diskusi dan berbagi informasi seputar hobi dan komunitas.",
            "parent_id": "241",
            "parent_list": "392,241,-1",
            "child_list": "392,591,581,395,393,580,394,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "393",
            "name": "Pisau",
            "description": "Tempat diskusi dan berbagi informasi tentang pisau yang mencakup pisau lipat, fix blades, pedang, dan peralatan lain yang berhubungan dengan pisau.",
            "parent_id": "392",
            "parent_list": "393,392,241,-1",
            "child_list": "393,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
        },
        {
            "forum_id": "394",
            "name": "Sepeda",
            "description": "Tempatnya pengguna, penikmat, dan pemerhati semua jenis sepeda.",
            "parent_id": "392",
            "parent_list": "394,392,241,-1",
            "child_list": "394,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
        },
        {
            "forum_id": "395",
            "name": "Mancing",
            "description": "Tempat diskusi dan berbagi tips & trik, tackle, serta pengalaman seputar hobi memancing.",
            "parent_id": "392",
            "parent_list": "395,392,241,-1",
            "child_list": "395,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
        },
        {
            "forum_id": "396",
            "name": "Reg Leader Lounge",
            "description": "Lounge dimana Reg leader bisa sharing pengalaman n saling tukar pikiran dan pandangan",
            "parent_id": "4",
            "parent_list": "396,4,-1",
            "child_list": "396,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-4.png"
        },
        {
            "forum_id": "397",
            "name": "ISP",
            "description": "Tempat diskusi Penyedia Layanan Internet di Indonesia.",
            "parent_id": "183",
            "parent_list": "397,183,19,241,-1",
            "child_list": "397,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-183.png"
        },
        {
            "forum_id": "398",
            "name": "Kepulauan Riau",
            "description": "",
            "parent_id": "460",
            "parent_list": "398,460,73,72,-1",
            "child_list": "398,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "402",
            "name": "Tegal",
            "description": "",
            "parent_id": "457",
            "parent_list": "402,457,73,72,-1",
            "child_list": "402,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "403",
            "name": "Karesidenan Besuki",
            "description": "Banyuwangi, Bondowoso, dan Situbondo",
            "parent_id": "459",
            "parent_list": "403,459,73,72,-1",
            "child_list": "403,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "405",
            "name": "Bekasi",
            "description": "",
            "parent_id": "458",
            "parent_list": "405,458,73,72,-1",
            "child_list": "405,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "407",
            "name": "Depok",
            "description": "",
            "parent_id": "458",
            "parent_list": "407,458,73,72,-1",
            "child_list": "407,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "411",
            "name": "Karesidenan Madiun",
            "description": "",
            "parent_id": "459",
            "parent_list": "411,459,73,72,-1",
            "child_list": "411,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "412",
            "name": "Cirebon",
            "description": "",
            "parent_id": "458",
            "parent_list": "412,458,73,72,-1",
            "child_list": "412,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "413",
            "name": "Mobile Phone",
            "description": "Diskusi mengenai ponsel berbasis Java, Symbian, GSM, CDMA, Dual GSM\/CDMA, dan iOS (produk Apple)",
            "parent_id": "36",
            "parent_list": "413,36,241,-1",
            "child_list": "413,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
        },
        {
            "forum_id": "415",
            "name": "PDA & PDA Phone",
            "description": "Diskusi mengenai Personal Digital Assistant (electronic handheld information device). Termasuk WM, Palm, dan Android",
            "parent_id": "36",
            "parent_list": "415,36,241,-1",
            "child_list": "415,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
        },
        {
            "forum_id": "417",
            "name": "Operator CDMA & GSM",
            "description": "Diskusi khusus layanan operator CDMA dan GSM.",
            "parent_id": "36",
            "parent_list": "417,36,241,-1",
            "child_list": "417,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
        },
        {
            "forum_id": "419",
            "name": "Taman Bacaan CCPB",
            "description": "Tempat khusus e-books dan tutorial Computer Stuff.",
            "parent_id": "14",
            "parent_list": "419,14,19,241,-1",
            "child_list": "419,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-14.png"
        },
        {
            "forum_id": "421",
            "name": "Visit USA",
            "description": "Apply Visa, Informasi Sekolah\/Kerja, Imigrasi, Travel, dll.",
            "parent_id": "76",
            "parent_list": "421,76,617,72,-1",
            "child_list": "421,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "423",
            "name": "West USA",
            "description": "Western states (formerly Seattle, San Francisco, Los Angeles)",
            "parent_id": "76",
            "parent_list": "423,76,617,72,-1",
            "child_list": "423,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "425",
            "name": "Central USA",
            "description": "Central + Midwest (formerly Texas, Illinois)",
            "parent_id": "76",
            "parent_list": "425,76,617,72,-1",
            "child_list": "425,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "427",
            "name": "Papua",
            "description": "",
            "parent_id": "463",
            "parent_list": "427,463,73,72,-1",
            "child_list": "427,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "429",
            "name": "Kids & Parenting",
            "description": "Tempat berbagi pengetahuan dan berdiskusi tentang anak, mencakup metode pendidikan bagi anak.",
            "parent_id": "193",
            "parent_list": "429,193,241,-1",
            "child_list": "429,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-193.png"
        },
        {
            "forum_id": "431",
            "name": "Anime",
            "description": "Tempat untuk diskusi serial Anime, baik yang sedang tayang maupun yang sudah tamat",
            "parent_id": "26",
            "parent_list": "431,26,241,-1",
            "child_list": "431,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
        },
        {
            "forum_id": "433",
            "name": "Manga, Manhua, & Manhwa",
            "description": "Tempat untuk diskusi komik yang berasal dari Jepang, Hongkong, Korea dan Indonesia",
            "parent_id": "26",
            "parent_list": "433,26,241,-1",
            "child_list": "433,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
        },
        {
            "forum_id": "435",
            "name": "KASKUS Promo updated",
            "description": "Forum yang berisi berbagai update, info & promosi terbaru dari KASKUS.",
            "parent_id": "239",
            "parent_list": "435,239,-1",
            "child_list": "435,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
        },
        {
            "forum_id": "437",
            "name": "Domestik",
            "description": "Tempat diskusi seputar objek wisata dalam negeri.",
            "parent_id": "235",
            "parent_list": "437,235,241,-1",
            "child_list": "437,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-235.png"
        },
        {
            "forum_id": "439",
            "name": "Mancanegara",
            "description": "Tempat diskusi seputar objek wisata luar negeri.",
            "parent_id": "235",
            "parent_list": "439,235,241,-1",
            "child_list": "439,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-235.png"
        },
        {
            "forum_id": "440",
            "name": "Basketball",
            "description": "Tempat diskusi para pecinta basket.",
            "parent_id": "35",
            "parent_list": "440,35,241,-1",
            "child_list": "440,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "442",
            "name": "Templates & Scripts Stuff",
            "description": "Tempat kumpulan templates dan scripts.",
            "parent_id": "13",
            "parent_list": "442,13,19,241,-1",
            "child_list": "442,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-13.png"
        },
        {
            "forum_id": "443",
            "name": "Hosting Stuff",
            "description": "Hosting (shared hosting, VPS, dedicated), domain (register), software hosting (cPanel, WHM, lxAdmin, etc), technical & security issues, webserver.",
            "parent_id": "13",
            "parent_list": "443,13,19,241,-1",
            "child_list": "443,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-13.png"
        },
        {
            "forum_id": "444",
            "name": "Die-cast, Mini4WD & R\/C",
            "description": "Khusus die-cast, Mini4WD, radio control vehicles",
            "parent_id": "198",
            "parent_list": "444,198,25,-1",
            "child_list": "444,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "446",
            "name": "Bayi",
            "description": "Pakaian dan perlengkapan bayi",
            "parent_id": "305",
            "parent_list": "446,305,25,-1",
            "child_list": "446,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-305.png"
        },
        {
            "forum_id": "447",
            "name": "Anak-Anak",
            "description": "Pakaian dan perlengkapan anak",
            "parent_id": "305",
            "parent_list": "447,305,25,-1",
            "child_list": "447,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-305.png"
        },
        {
            "forum_id": "448",
            "name": "Industri Garmen",
            "description": "Bahan baku (kain, benang dsb) dan sablon",
            "parent_id": "286",
            "parent_list": "448,286,25,-1",
            "child_list": "448,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-286.png"
        },
        {
            "forum_id": "449",
            "name": "Kemeja, Kaos & Polo Shirt ( baju )",
            "description": "Kemeja, Kaos dan polo shirt ( baju )",
            "parent_id": "196",
            "parent_list": "449,196,25,-1",
            "child_list": "449,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "450",
            "name": "Jaket, Hoodie, Sweater",
            "description": "Khusus jaket, hoodie dan sweater",
            "parent_id": "196",
            "parent_list": "450,196,25,-1",
            "child_list": "450,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "451",
            "name": "Celana,  Jeans & Rok",
            "description": "Celana bahan, kargo, jeans & rok",
            "parent_id": "196",
            "parent_list": "451,196,25,-1",
            "child_list": "451,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "452",
            "name": "Karesidenan Kediri",
            "description": "",
            "parent_id": "459",
            "parent_list": "452,459,73,72,-1",
            "child_list": "452,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "457",
            "name": "Jawa Tengah & Yogyakarta",
            "description": "",
            "parent_id": "73",
            "parent_list": "457,73,72,-1",
            "child_list": "457,181,653,627,564,598,111,160,402,84,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "458",
            "name": "Jawa Barat, Jakarta & Banten",
            "description": "",
            "parent_id": "73",
            "parent_list": "458,73,72,-1",
            "child_list": "458,89,164,405,107,412,407,654,78,626,585,599,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "459",
            "name": "Jawa Timur & Bali",
            "description": "",
            "parent_id": "73",
            "parent_list": "459,73,72,-1",
            "child_list": "459,167,587,567,555,403,651,452,411,652,133,583,628,92,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "460",
            "name": "Sumatera",
            "description": "",
            "parent_id": "73",
            "parent_list": "460,73,72,-1",
            "child_list": "460,161,97,543,586,548,398,145,93,156,81,117,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "461",
            "name": "Kalimantan",
            "description": "",
            "parent_id": "73",
            "parent_list": "461,73,72,-1",
            "child_list": "461,162,146,385,91,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "462",
            "name": "Sulawesi",
            "description": "",
            "parent_id": "73",
            "parent_list": "462,73,72,-1",
            "child_list": "462,584,561,170,179,166,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "463",
            "name": "Indonesia Timur",
            "description": "",
            "parent_id": "73",
            "parent_list": "463,73,72,-1",
            "child_list": "463,427,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "464",
            "name": "English Education & Literature",
            "description": "A place where you can find all the English help you need from TOEFL, IELTS and everything else regarding the English language and its usage.",
            "parent_id": "113",
            "parent_list": "464,113,241,-1",
            "child_list": "464,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-113.png"
        },
        {
            "forum_id": "465",
            "name": "Fun with English",
            "description": "A place to learn English through various game threads.",
            "parent_id": "113",
            "parent_list": "465,113,241,-1",
            "child_list": "465,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-113.png"
        },
        {
            "forum_id": "466",
            "name": "Penawaran Kerjasama & Investasi",
            "description": "Tempat berbagi penawaran kerjasama dan investasi usaha.",
            "parent_id": "277",
            "parent_list": "466,277,30,241,-1",
            "child_list": "466,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-277.png"
        },
        {
            "forum_id": "467",
            "name": "Forex",
            "description": "",
            "parent_id": "279",
            "parent_list": "467,279,30,241,-1",
            "child_list": "467,470,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-279.png"
        },
        {
            "forum_id": "468",
            "name": "Options",
            "description": "",
            "parent_id": "279",
            "parent_list": "468,279,30,241,-1",
            "child_list": "468,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-279.png"
        },
        {
            "forum_id": "469",
            "name": "Saham",
            "description": "",
            "parent_id": "279",
            "parent_list": "469,279,30,241,-1",
            "child_list": "469,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-279.png"
        },
        {
            "forum_id": "470",
            "name": "Forex Broker",
            "description": "",
            "parent_id": "467",
            "parent_list": "470,467,279,30,241,-1",
            "child_list": "470,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-467.png"
        },
        {
            "forum_id": "471",
            "name": "The Online Business",
            "description": "Diskusi segala bentuk bisnis online dan perkembangannya. Dilarang promosi disini.",
            "parent_id": "30",
            "parent_list": "471,30,241,-1",
            "child_list": "471,280,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "472",
            "name": "MLM, Member Get Member, & Sejenisnya",
            "description": "Tempat diskusi dan promosi bisnis direct selling dan sejenisnya.",
            "parent_id": "30",
            "parent_list": "472,30,241,-1",
            "child_list": "472,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "473",
            "name": "Gathering, Event Report & Bakti Sosial",
            "description": "Tempat kumpulan arsip dari semua event dan bakti sosial komunitas KASKUS.",
            "parent_id": "240",
            "parent_list": "473,240,239,-1",
            "child_list": "473,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-240.png"
        },
        {
            "forum_id": "474",
            "name": "Event from Kaskuser",
            "description": "Forum untuk berbagi informasi mengenai event yang berhubungan dengan KASKUS. Untuk gathering & FR regional harap dibuat di regional masing-masing.",
            "parent_id": "241",
            "parent_list": "474,241,-1",
            "child_list": "474,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "475",
            "name": "Others",
            "description": "",
            "parent_id": "74",
            "parent_list": "475,74,72,-1",
            "child_list": "475,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "476",
            "name": "Others",
            "description": "",
            "parent_id": "157",
            "parent_list": "476,157,72,-1",
            "child_list": "476,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "477",
            "name": "Others",
            "description": "",
            "parent_id": "109",
            "parent_list": "477,109,72,-1",
            "child_list": "477,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "478",
            "name": "Others",
            "description": "",
            "parent_id": "158",
            "parent_list": "478,158,72,-1",
            "child_list": "478,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "479",
            "name": "Cinta Indonesiaku",
            "description": "Forum yang didedikasikan untuk menunjukkan kecintaan Kaskuser terhadap Indonesia.",
            "parent_id": "239",
            "parent_list": "479,239,-1",
            "child_list": "479,480,485,481,484,486,482,483,542,488,490,489,487,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
        },
        {
            "forum_id": "480",
            "name": "Arsitektur",
            "description": "",
            "parent_id": "479",
            "parent_list": "480,479,239,-1",
            "child_list": "480,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "481",
            "name": "Kuliner",
            "description": "",
            "parent_id": "479",
            "parent_list": "481,479,239,-1",
            "child_list": "481,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "482",
            "name": "Pakaian",
            "description": "",
            "parent_id": "479",
            "parent_list": "482,479,239,-1",
            "child_list": "482,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "483",
            "name": "Lagu, Tarian & Alat Musik",
            "description": "",
            "parent_id": "479",
            "parent_list": "483,479,239,-1",
            "child_list": "483,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "484",
            "name": "Kerajinan & Ukiran",
            "description": "",
            "parent_id": "479",
            "parent_list": "484,479,239,-1",
            "child_list": "484,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "485",
            "name": "Kekayaan Alam, Flora & Fauna",
            "description": "",
            "parent_id": "479",
            "parent_list": "485,479,239,-1",
            "child_list": "485,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "486",
            "name": "Kesusastraan, Bahasa & Dongeng",
            "description": "",
            "parent_id": "479",
            "parent_list": "486,479,239,-1",
            "child_list": "486,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "487",
            "name": "Tata Cara Adat, Upacara & Ritual",
            "description": "",
            "parent_id": "479",
            "parent_list": "487,479,239,-1",
            "child_list": "487,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "488",
            "name": "Permainan Rakyat",
            "description": "",
            "parent_id": "479",
            "parent_list": "488,479,239,-1",
            "child_list": "488,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "489",
            "name": "Seni Peran",
            "description": "",
            "parent_id": "479",
            "parent_list": "489,479,239,-1",
            "child_list": "489,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "490",
            "name": "Properti Sejarah Nasional",
            "description": "",
            "parent_id": "479",
            "parent_list": "490,479,239,-1",
            "child_list": "490,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "491",
            "name": "Mobile Broadband",
            "description": "Forum diskusi mengenai wireless dan high-speed internet access menggunakan modem portable, jaringan telepon, maupun perangkat lainnya.",
            "parent_id": "241",
            "parent_list": "491,241,-1",
            "child_list": "491,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "527",
            "name": "Aksesoris, suku cadang HP",
            "description": "Aksesori dan suku cadang HP\/smartphone\/PDAphone\/Blackberry",
            "parent_id": "210",
            "parent_list": "527,210,25,-1",
            "child_list": "527,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-210.png"
        },
        {
            "forum_id": "528",
            "name": "PC Games",
            "description": "Tempat diskusi seputar games yang dimainkan di Personal Computer (PC)",
            "parent_id": "44",
            "parent_list": "528,44,241,-1",
            "child_list": "528,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
        },
        {
            "forum_id": "537",
            "name": "Sport Games",
            "description": "Tempat berbagi game olahraga seru.",
            "parent_id": "35",
            "parent_list": "537,35,241,-1",
            "child_list": "537,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "538",
            "name": "Racket",
            "description": "Tempat diskusi para pecinta olahraga yang menggunakan raket (tenis, squash, ping pong\/tenis meja (tenis meja), dan badminton\/bulutangkis.",
            "parent_id": "35",
            "parent_list": "538,35,241,-1",
            "child_list": "538,539,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "539",
            "name": "Badminton",
            "description": "Tempat diskusi khusus pencinta olahraga badminton atau bulutangkis.",
            "parent_id": "538",
            "parent_list": "539,538,35,241,-1",
            "child_list": "539,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-538.png"
        },
        {
            "forum_id": "540",
            "name": "Korea Selatan",
            "description": "",
            "parent_id": "109",
            "parent_list": "540,109,72,-1",
            "child_list": "540,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "541",
            "name": "Nokia",
            "description": "Forum bagi pengguna gadget Nokia. Tempat diskusi dan berbagi informasi terkini mengenai hal-hal yang terkait dengan Nokia.",
            "parent_id": "241",
            "parent_list": "541,241,-1",
            "child_list": "541,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "542",
            "name": "Pahlawan & Tokoh Nasional",
            "description": "",
            "parent_id": "479",
            "parent_list": "542,479,239,-1",
            "child_list": "542,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
        },
        {
            "forum_id": "543",
            "name": "Batam",
            "description": "",
            "parent_id": "460",
            "parent_list": "543,460,73,72,-1",
            "child_list": "543,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "544",
            "name": "Young on Top KASKUS Community (YOTKC)",
            "description": "Forum untuk berbagi inspirasi bersama Billy Boen.",
            "parent_id": "241",
            "parent_list": "544,241,-1",
            "child_list": "544,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "545",
            "name": "Pro Wrestling",
            "description": "Tempat diskusi para pecinta pro wrestling.",
            "parent_id": "35",
            "parent_list": "545,35,241,-1",
            "child_list": "545,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
        },
        {
            "forum_id": "546",
            "name": "Dunia Kerja & Profesi",
            "description": "Tempat diskusi beragam profesi dan pembahasan seputar karir, gaji, pajak, keuangan dan serba-serbi dunia kerja.",
            "parent_id": "30",
            "parent_list": "546,30,241,-1",
            "child_list": "546,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "548",
            "name": "Jambi",
            "description": "",
            "parent_id": "460",
            "parent_list": "548,460,73,72,-1",
            "child_list": "548,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "552",
            "name": "Fanstuff",
            "description": "Tempatnya para penggemar fiksi. Lihat juga cerita fiksi karya mereka!",
            "parent_id": "26",
            "parent_list": "552,26,241,-1",
            "child_list": "552,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-26.png"
        },
        {
            "forum_id": "553",
            "name": "Web Hosting & Services",
            "description": "Web development, Jasa Hosting, Registrasi Domain, Voucher \/ Akses Premium ke rapid*share dsb, Web Promotion Service, SEO, Link building, Imaging, dsb., Web Consultation \/ Web coaching",
            "parent_id": "202",
            "parent_list": "553,202,25,-1",
            "child_list": "553,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-202.png"
        },
        {
            "forum_id": "554",
            "name": "BANNER TEST",
            "description": "Forum ini adalah forum diskusi untuk testing banner preview",
            "parent_id": "-1",
            "parent_list": "554,-1",
            "child_list": "554,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image--1.png"
        },
        {
            "forum_id": "555",
            "name": "Jember",
            "description": "",
            "parent_id": "459",
            "parent_list": "555,459,73,72,-1",
            "child_list": "555,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "557",
            "name": "Hardware Review Lab",
            "description": "Tempat kumpulan ulasan mengenai hardware.",
            "parent_id": "243",
            "parent_list": "557,243,19,241,-1",
            "child_list": "557,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-243.png"
        },
        {
            "forum_id": "558",
            "name": "Fit & Healty Lifestyle",
            "description": "Forum gaya hidup sehat. Pengetahuan tentang diet & nutrisi, fitness & muscle building, metode olahraga untuk keseimbangan, hingga cara menghentikan adiksi.",
            "parent_id": "241",
            "parent_list": "558,241,-1",
            "child_list": "558,274,236,559,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "559",
            "name": "Quit Smoking & Avoid Drugs",
            "description": "Tempat diskusi dan berbagi  cara mengubah pemikiran, langkah dan dukungan untuk berhenti merokok serta menjaga kesehatan tanpa obat-obatan.",
            "parent_id": "558",
            "parent_list": "559,558,241,-1",
            "child_list": "559,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
        },
        {
            "forum_id": "561",
            "name": "Kendari",
            "description": "",
            "parent_id": "462",
            "parent_list": "561,462,73,72,-1",
            "child_list": "561,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "564",
            "name": "Karesidenan Pati",
            "description": "",
            "parent_id": "457",
            "parent_list": "564,457,73,72,-1",
            "child_list": "564,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "565",
            "name": "FutSal",
            "description": "Tempat berbagi para pencinta futsal tentang berita, informasi, dan pengalaman seputar dunia futsal.",
            "parent_id": "104",
            "parent_list": "565,104,35,241,-1",
            "child_list": "565,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-104.png"
        },
        {
            "forum_id": "566",
            "name": "Surat Terbuka",
            "description": "Pusat pengaduan Kaskuser terkait transaksi di Forum Jual Beli Kaskus: kerugian, penipuan",
            "parent_id": "204",
            "parent_list": "566,204,25,-1",
            "child_list": "566,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-204.png"
        },
        {
            "forum_id": "567",
            "name": "Gresik",
            "description": "",
            "parent_id": "459",
            "parent_list": "567,459,73,72,-1",
            "child_list": "567,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "568",
            "name": "Mac OSX Info & Discussion",
            "description": "Tempat diskusi dan berbagi informasi dan pengalaman seputar Mac, Mac buyers guide, tutorials & e-books, serta teknologi terbaru .",
            "parent_id": "383",
            "parent_list": "568,383,19,241,-1",
            "child_list": "568,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-383.png"
        },
        {
            "forum_id": "569",
            "name": "Mac Applications & Games",
            "description": "Tempat review, share, troubleshooting apps, games, modifikasi OSX, beragam tips dan trik aplikasi.",
            "parent_id": "383",
            "parent_list": "569,383,19,241,-1",
            "child_list": "569,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-383.png"
        },
        {
            "forum_id": "570",
            "name": "Kendaraan Roda 4",
            "description": "Tempat membahas kendaraan beroda empat (mobil) dari segala brand (merek)",
            "parent_id": "28",
            "parent_list": "570,28,241,-1",
            "child_list": "570,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-28.png"
        },
        {
            "forum_id": "571",
            "name": "The Exclusive Business Club (ExBC)",
            "description": "Tempat berkumpulnya para pelaku bisnis atau pengusaha untuk berbagi pengalaman tentang pengembangan bisnis di bidang masing-masing.",
            "parent_id": "30",
            "parent_list": "571,30,241,-1",
            "child_list": "571,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "572",
            "name": "Penawaran Kerjasama, BO, Distribusi, Reseller, & Agen",
            "description": "Tempat untuk menawarkan bisnis baik dalam bentuk franchise, peluang bisnis, distribusi, reseller, kemitraan, dan agen usaha.",
            "parent_id": "30",
            "parent_list": "572,30,241,-1",
            "child_list": "572,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "573",
            "name": "Pulsa",
            "description": "Khusus Jual beli\/transfer pulsa, voucher HP",
            "parent_id": "210",
            "parent_list": "573,210,25,-1",
            "child_list": "573,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-210.png"
        },
        {
            "forum_id": "574",
            "name": "Jasa & Perbaikan HP",
            "description": "Jasa perbaikan, isi aplikasi dan program lainnya untuk HP\/smartphone\/PDAphone\/Blackberry",
            "parent_id": "210",
            "parent_list": "574,210,25,-1",
            "child_list": "574,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-210.png"
        },
        {
            "forum_id": "575",
            "name": "Militer dan Kepolisian",
            "description": "Forum diskusi dan berbagi berita maupun informasi seputar dunia militer dan kepolisian.",
            "parent_id": "241",
            "parent_list": "575,241,-1",
            "child_list": "575,576,140,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "576",
            "name": "Kepolisian",
            "description": "Tempat diskusi seputar dunia kepolisian.",
            "parent_id": "575",
            "parent_list": "576,575,241,-1",
            "child_list": "576,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-575.png"
        },
        {
            "forum_id": "577",
            "name": "Android",
            "description": "Diskusi khusus mengenai Android",
            "parent_id": "36",
            "parent_list": "577,36,241,-1",
            "child_list": "577,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
        },
        {
            "forum_id": "578",
            "name": "Teknik",
            "description": "Forum untuk berdiskusi dan berbagi pengetahuan atau informasi seputar teknik arsitektur dan teknik sipil .",
            "parent_id": "241",
            "parent_list": "578,241,-1",
            "child_list": "578,234,579,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "579",
            "name": "Sipil",
            "description": "Tempat diskusi seputar teknik sipil, baik keilmuan maupun terapan.",
            "parent_id": "578",
            "parent_list": "579,578,241,-1",
            "child_list": "579,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-578.png"
        },
        {
            "forum_id": "580",
            "name": "Radio Komunikasi",
            "description": "Tempat diskusi dan ngumpulnya para penggemar radio komunikasi (HAM Radio).",
            "parent_id": "392",
            "parent_list": "580,392,241,-1",
            "child_list": "580,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
        },
        {
            "forum_id": "581",
            "name": "Lampu Senter \/ Flashlight",
            "description": "Tempat ngumpulnya Flashholic dan pengguna senter, laser, LED, beserta aksesorisnya.",
            "parent_id": "392",
            "parent_list": "581,392,241,-1",
            "child_list": "581,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
        },
        {
            "forum_id": "583",
            "name": "Mojokerto",
            "description": "",
            "parent_id": "459",
            "parent_list": "583,459,73,72,-1",
            "child_list": "583,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "584",
            "name": "Gorontalo",
            "description": "",
            "parent_id": "462",
            "parent_list": "584,462,73,72,-1",
            "child_list": "584,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "585",
            "name": "Sukabumi",
            "description": "",
            "parent_id": "458",
            "parent_list": "585,458,73,72,-1",
            "child_list": "585,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "586",
            "name": "Bengkulu",
            "description": "",
            "parent_id": "460",
            "parent_list": "586,460,73,72,-1",
            "child_list": "586,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "587",
            "name": "Bromo",
            "description": "",
            "parent_id": "459",
            "parent_list": "587,459,73,72,-1",
            "child_list": "587,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "588",
            "name": "Online Gaming",
            "description": "",
            "parent_id": "25",
            "parent_list": "588,25,-1",
            "child_list": "588,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "589",
            "name": "Pakaian, Sepatu",
            "description": "Pakaian\/jersey\/seragam klub dan sepatu olahraga",
            "parent_id": "220",
            "parent_list": "589,220,25,-1",
            "child_list": "589,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-220.png"
        },
        {
            "forum_id": "590",
            "name": "Sepeda",
            "description": "Khusus sepeda, perangkat dan perlengkapannya",
            "parent_id": "198",
            "parent_list": "590,198,25,-1",
            "child_list": "590,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "591",
            "name": "Jam",
            "description": "Tempat diskusi tentang jam sebagai tools, koleksi, dan hobi",
            "parent_id": "392",
            "parent_list": "591,392,241,-1",
            "child_list": "591,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
        },
        {
            "forum_id": "593",
            "name": "Kredit & Leasing Kendaraan Bermotor",
            "description": "",
            "parent_id": "205",
            "parent_list": "593,205,25,-1",
            "child_list": "593,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-205.png"
        },
        {
            "forum_id": "594",
            "name": "Melek Hukum",
            "description": "Forum diskusi mengenai hukum yang berlaku di Indonesia, mulai dari penerapan hukum sederhana hingga pembahasan mendalam.",
            "parent_id": "241",
            "parent_list": "594,241,-1",
            "child_list": "594,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "595",
            "name": "UKM",
            "description": "Tempat diskusi dan berbagi seputar Usaha Kecil Menengah (UKM), mulai dari tips, trik, dan pengalaman menjalankan usaha.",
            "parent_id": "30",
            "parent_list": "595,30,241,-1",
            "child_list": "595,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
        },
        {
            "forum_id": "596",
            "name": "Catatan Perjalanan OANC",
            "description": "Tempat diskusi, berbagi dan ajakan perjalanan mencakup bahasan tentang lokasi, rute, biaya, logistik, dll",
            "parent_id": "98",
            "parent_list": "596,98,241,-1",
            "child_list": "596,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-98.png"
        },
        {
            "forum_id": "597",
            "name": "Sains & Teknologi",
            "description": "Tempat diskusi mendalam dan berbagi pengetahuan sains dan teknologi.",
            "parent_id": "67",
            "parent_list": "597,67,241,-1",
            "child_list": "597,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-67.png"
        },
        {
            "forum_id": "598",
            "name": "Klaten ",
            "description": "",
            "parent_id": "457",
            "parent_list": "598,457,73,72,-1",
            "child_list": "598,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "599",
            "name": "Tasikmalaya ",
            "description": "",
            "parent_id": "458",
            "parent_list": "599,458,73,72,-1",
            "child_list": "599,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "600",
            "name": "Perhiasan",
            "description": "Gelang, anting, kalung dan cincin",
            "parent_id": "196",
            "parent_list": "600,196,25,-1",
            "child_list": "600,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "603",
            "name": "Desain",
            "description": "Produk dan jasa desain",
            "parent_id": "284",
            "parent_list": "603,284,25,-1",
            "child_list": "603,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-284.png"
        },
        {
            "forum_id": "604",
            "name": "Aksesoris Kamera",
            "description": "Aksesoris kamera",
            "parent_id": "293",
            "parent_list": "604,293,25,-1",
            "child_list": "604,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-293.png"
        },
        {
            "forum_id": "605",
            "name": "Kamera",
            "description": "Kamera beragam merk",
            "parent_id": "293",
            "parent_list": "605,293,25,-1",
            "child_list": "605,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-293.png"
        },
        {
            "forum_id": "606",
            "name": "Kaset",
            "description": "Khusus kaset",
            "parent_id": "198",
            "parent_list": "606,198,25,-1",
            "child_list": "606,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-198.png"
        },
        {
            "forum_id": "607",
            "name": "Minuman",
            "description": "Khusus aneka minuman (HARUS halal)",
            "parent_id": "201",
            "parent_list": "607,201,25,-1",
            "child_list": "607,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-201.png"
        },
        {
            "forum_id": "608",
            "name": "Perawatan Tubuh",
            "description": "Produk untuk perawatan tubuh",
            "parent_id": "295",
            "parent_list": "608,295,25,-1",
            "child_list": "608,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-295.png"
        },
        {
            "forum_id": "609",
            "name": "Perawatan Wajah",
            "description": "Produk untuk perawatan wajah",
            "parent_id": "295",
            "parent_list": "609,295,25,-1",
            "child_list": "609,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-295.png"
        },
        {
            "forum_id": "610",
            "name": "Pertunjukan",
            "description": "Khusus tiket pertunjukkan musik\/ konser\/ film",
            "parent_id": "316",
            "parent_list": "610,316,25,-1",
            "child_list": "610,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-316.png"
        },
        {
            "forum_id": "611",
            "name": "Transportasi",
            "description": "Khusus tiket transportasi (darat, laut, udara)",
            "parent_id": "316",
            "parent_list": "611,316,25,-1",
            "child_list": "611,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-316.png"
        },
        {
            "forum_id": "612",
            "name": "Aksesoris",
            "description": "Khusus aksesori",
            "parent_id": "297",
            "parent_list": "612,297,25,-1",
            "child_list": "612,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-297.png"
        },
        {
            "forum_id": "613",
            "name": "Konsol",
            "description": "PS, Nintendo, Xbox, PSP, Sega dsb",
            "parent_id": "297",
            "parent_list": "613,297,25,-1",
            "child_list": "613,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-297.png"
        },
        {
            "forum_id": "614",
            "name": "Serba Serbi",
            "description": "Jual beli aneka produk diluar kategori \/sub kategori",
            "parent_id": "25",
            "parent_list": "614,25,-1",
            "child_list": "614,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "615",
            "name": "Bisnis",
            "description": "Penawaran bisnis",
            "parent_id": "25",
            "parent_list": "615,25,-1",
            "child_list": "615,616,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
        },
        {
            "forum_id": "616",
            "name": "Peluang Bisnis",
            "description": "Reseller, franchise dan supplier",
            "parent_id": "615",
            "parent_list": "616,615,25,-1",
            "child_list": "616,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-615.png"
        },
        {
            "forum_id": "617",
            "name": "America",
            "description": "",
            "parent_id": "72",
            "parent_list": "617,72,-1",
            "child_list": "617,83,76,421,425,96,423,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "619",
            "name": "Indie Filmmaker",
            "description": "Tempat untuk pembuat film independent saling berdiskusi & berbagi kesukaan. Baik produksi atau topik yang berhubungan dengan film independent.",
            "parent_id": "11",
            "parent_list": "619,11,241,-1",
            "child_list": "619,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-11.png"
        },
        {
            "forum_id": "620",
            "name": "Perencanaan Keuangan",
            "description": "Forum untuk diskusi & konsultasi seputar perencanaan keuangan, mulai dari pengelolaan keuangan hingga cara berinvestasi yang tepat.",
            "parent_id": "241",
            "parent_list": "620,241,-1",
            "child_list": "620,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "621",
            "name": "Film Indonesia",
            "description": "Forum untuk berdiskusi seputar film-film Indonesia dari era lampau hingga sekarang. Hal yang terkait dengan industri perfilman Indonesia juga dibahas disini.",
            "parent_id": "11",
            "parent_list": "621,11,241,-1",
            "child_list": "621,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-11.png"
        },
        {
            "forum_id": "624",
            "name": "Pakaian dalam",
            "description": "Lingerie & Pakaian dalam",
            "parent_id": "196",
            "parent_list": "624,196,25,-1",
            "child_list": "624,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
        },
        {
            "forum_id": "625",
            "name": "Komik",
            "description": "Komik",
            "parent_id": "227",
            "parent_list": "625,227,25,-1",
            "child_list": "625,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-227.png"
        },
        {
            "forum_id": "626",
            "name": "Karawang",
            "description": "",
            "parent_id": "458",
            "parent_list": "626,458,73,72,-1",
            "child_list": "626,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "627",
            "name": "Karesidenan Kedu",
            "description": "",
            "parent_id": "457",
            "parent_list": "627,457,73,72,-1",
            "child_list": "627,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "628",
            "name": "Sidoarjo",
            "description": "",
            "parent_id": "459",
            "parent_list": "628,459,73,72,-1",
            "child_list": "628,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "629",
            "name": "KASKUS Playground",
            "description": "Tempat informasi, kisah-kisah & cerita unik tentang Kaskus & Kaskus Officer",
            "parent_id": "239",
            "parent_list": "629,239,-1",
            "child_list": "629,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
        },
        {
            "forum_id": "630",
            "name": "Green Lifestyle",
            "description": "",
            "parent_id": "241",
            "parent_list": "630,241,-1",
            "child_list": "630,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "631",
            "name": "Instalasi Komputer new",
            "description": "Tempat menawarkan jasa untuk instalasi komputer, notebook, laptop, games",
            "parent_id": "202",
            "parent_list": "631,202,25,-1",
            "child_list": "631,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-202.png"
        },
        {
            "forum_id": "633",
            "name": "PEMILU 2014",
            "description": "Ruang diskusi & semua informasi yang berhubungan dengan Pemilu 2014, mulai dari partai politik, calon legislatif hingga calon presiden. Yuk, bangun Indonesia! Kenali Janji Manisnya, Suarakan Pendapatmu!\n",
            "parent_id": "241",
            "parent_list": "633,241,-1",
            "child_list": "633,634,636,637,638,639,640,641,642,643,644,645,646,647,648,649,650,635,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
        },
        {
            "forum_id": "634",
            "name": "PILIH PARPOL",
            "description": "Tempat khusus untuk membahas partai-partai PEMILU 2014 dan para calon legislatifnya",
            "parent_id": "633",
            "parent_list": "634,633,241,-1",
            "child_list": "634,636,637,638,639,640,641,642,643,644,645,646,647,648,649,650,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-633.png"
        },
        {
            "forum_id": "635",
            "name": "PILIH CAPRES",
            "description": "Ruang utama untuk mendiskusikan calon-calon presiden PEMILU 2014\n",
            "parent_id": "633",
            "parent_list": "635,633,241,-1",
            "child_list": "635,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-633.png"
        },
        {
            "forum_id": "636",
            "name": "1 - Partai NasDem",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Nasional Demokrat (NasDem) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "636,634,633,241,-1",
            "child_list": "636,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "637",
            "name": "2 - Partai Kebangkitan Bangsa (PKB)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Kebangkitan Bangsa (PKB) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "637,634,633,241,-1",
            "child_list": "637,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "638",
            "name": "3 - Partai Keadilan Sejahtera (PKS)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Keadilan Sejahtera (PKS) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "638,634,633,241,-1",
            "child_list": "638,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "639",
            "name": "4 - Partai Demokrasi Indonesia Perjuangan (PDIP)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Demokrasi Indonesia Perjuangan (PDIP) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "639,634,633,241,-1",
            "child_list": "639,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "640",
            "name": "5 - Partai Golongan Karya (GOLKAR)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Golongan Karya (GOLKAR) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "640,634,633,241,-1",
            "child_list": "640,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "641",
            "name": "6 - Partai Gerakan Indonesia Raya (GERINDRA)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Gerakan Indonesia Raya (GERINDRA) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "641,634,633,241,-1",
            "child_list": "641,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "642",
            "name": "7 - Partai Demokrat",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Demokrat dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "642,634,633,241,-1",
            "child_list": "642,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "643",
            "name": "8 - Partai Amanat Nasional (PAN)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Amanat  Nasional (PAN) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "643,634,633,241,-1",
            "child_list": "643,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "644",
            "name": "9 - Partai Persatuan Pembangunan (PPP)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai  Persatuan Pembangunan (PPP) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "644,634,633,241,-1",
            "child_list": "644,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "645",
            "name": "10 - Partai Hati Nurani Rakyat (HANURA)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Hati Nurani Rakyat (HANURA) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "645,634,633,241,-1",
            "child_list": "645,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "646",
            "name": "11 - Partai Damai Aceh (PDA)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Damai Aceh (PDA) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "646,634,633,241,-1",
            "child_list": "646,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "647",
            "name": "12 - Partai Nasional Aceh (PNA)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Nasional Aceh (PNA) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "647,634,633,241,-1",
            "child_list": "647,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "648",
            "name": "13 - Partai Aceh (PA)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Aceh (PA) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "648,634,633,241,-1",
            "child_list": "648,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "649",
            "name": "14 - Partai Bulan Bintang (PBB)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Bulan Bintang (PBB) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "649,634,633,241,-1",
            "child_list": "649,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "650",
            "name": "15 - Partai Keadilan Dan Persatuan Indonesia (PKPI)",
            "description": "Ruang khusus untuk mendiskusikan segala sesuatu tentang Partai Keadilan dan Persatuan Indonesia (PKPI) dan para calon legislatifnya",
            "parent_id": "634",
            "parent_list": "650,634,633,241,-1",
            "child_list": "650,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-634.png"
        },
        {
            "forum_id": "651",
            "name": "Karesidenan Bojonegoro new",
            "description": "Bojonegoro, Tuban, dan Lamongan",
            "parent_id": "459",
            "parent_list": "651,459,73,72,-1",
            "child_list": "651,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "652",
            "name": "Madura new",
            "description": "",
            "parent_id": "459",
            "parent_list": "652,459,73,72,-1",
            "child_list": "652,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "653",
            "name": "Cilacap",
            "description": "",
            "parent_id": "457",
            "parent_list": "653,457,73,72,-1",
            "child_list": "653,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        },
        {
            "forum_id": "654",
            "name": "Garut new",
            "description": "",
            "parent_id": "458",
            "parent_list": "654,458,73,72,-1",
            "child_list": "654,-1",
            "visible": "1",
            "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
        }
    ],
    "forumtag": {
        "data": [
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null,
            null
        ]
    },
    "location_list": [
        {
            "1": "Nanggroe Aceh Darussalam"
        },
        {
            "2": "Sumatera Utara"
        },
        {
            "3": "Sumatera Barat"
        },
        {
            "4": "Riau"
        },
        {
            "5": "Jambi"
        },
        {
            "6": "Sumatera Selatan"
        },
        {
            "7": "Bengkulu"
        },
        {
            "8": "Lampung"
        },
        {
            "9": "Kepulauan Bangka Belitung"
        },
        {
            "10": "Kepulauan Riau"
        },
        {
            "11": "DKI Jakarta"
        },
        {
            "12": "Jawa Barat"
        },
        {
            "13": "Jawa Tengah"
        },
        {
            "14": "Daerah Istimewa Yogyakarta"
        },
        {
            "15": "Jawa Timur"
        },
        {
            "16": "Banten"
        },
        {
            "17": "Bali"
        },
        {
            "18": "Nusa Tenggara Barat"
        },
        {
            "19": "Nusa Tenggara Timur"
        },
        {
            "20": "Kalimantan Barat"
        },
        {
            "21": "Kalimantan Tengah"
        },
        {
            "22": "Kalimantan Selatan"
        },
        {
            "23": "Kalimantan Timur"
        },
        {
            "24": "Sulawasi Utara"
        },
        {
            "25": "Sulawesi Tengah"
        },
        {
            "26": "Sulawesi Selatan"
        },
        {
            "27": "Sulawesi Tenggara"
        },
        {
            "28": "Gorontalo"
        },
        {
            "29": "Sulawesi Barat"
        },
        {
            "30": "Maluku"
        },
        {
            "31": "Maluku Utara"
        },
        {
            "32": "Papua"
        },
        {
            "33": "N\/A"
        },
        {
            "34": "Kalimantan Utara"
        },
        {
            "35": "Papua Barat"
        }
    ],
    "smiley": [
        {
            "text": ":ultah",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/ultah.gif"
        },
        {
            "text": ":travel",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/traveller.gif"
        },
        {
            "text": ":toast",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/toastcendol.gif"
        },
        {
            "text": ":takut",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/takut.gif"
        },
        {
            "text": ":sup:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fd_5.gif"
        },
        {
            "text": ":sup2",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/sundul.gif"
        },
        {
            "text": ":sorry",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/sorry.gif"
        },
        {
            "text": ":shakehand2",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/shakehand2.gif"
        },
        {
            "text": ":selamat",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/selamat.gif"
        },
        {
            "text": ":salaman",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/lebaran03.gif"
        },
        {
            "text": ":salahkamar",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/salah_kamar.gif"
        },
        {
            "text": ":request",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/request.gif"
        },
        {
            "text": ":repost:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fd_7.gif"
        },
        {
            "text": ":repost2",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_sm_repost2.gif"
        },
        {
            "text": ":repost",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_sm_repost1.gif"
        },
        {
            "text": ":recsel",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/recseller.gif"
        },
        {
            "text": ":rate5",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/rate5.gif"
        },
        {
            "text": ":peluk",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/peluk.gif"
        },
        {
            "text": ":nosara",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/nosara.gif"
        },
        {
            "text": ":nohope",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/nohope.gif"
        },
        {
            "text": ":ngakak",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/ngakak.gif"
        },
        {
            "text": ":ngacir2",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/ngacir2.gif"
        },
        {
            "text": ":ngacir",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/ngacir3.gif"
        },
        {
            "text": ":najis",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/najis.gif"
        },
        {
            "text": ":mewek",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/mewek.gif"
        },
        {
            "text": ":matabelo",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/matabelo1.gif"
        },
        {
            "text": ":marah",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/marah.gif"
        },
        {
            "text": ":malu",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/malu.gif"
        },
        {
            "text": ":maafaganwati",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/lebaran04.gif"
        },
        {
            "text": ":maafagan",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/lebaran01.gif"
        },
        {
            "text": ":kts:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fd_6.gif"
        },
        {
            "text": ":kr",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/kaskus_radio.gif"
        },
        {
            "text": ":kiss",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/cewek.gif"
        },
        {
            "text": ":kimpoi",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/kimpoi.gif"
        },
        {
            "text": ":ketupat",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/lebaran05.gif"
        },
        {
            "text": ":kbgt:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fd_4.gif"
        },
        {
            "text": ":kacau:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fd_8.gif"
        },
        {
            "text": ":jrb:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fd_1.gif"
        },
        {
            "text": ":ilovekaskus",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_sm_ilovekaskus.gif"
        },
        {
            "text": ":iloveindonesia",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/I-Luv-Indonesia.gif"
        },
        {
            "text": ":hoax",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/hoax.gif"
        },
        {
            "text": ":hn",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/hotnews.gif"
        },
        {
            "text": ":hammer",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/hammer.gif"
        },
        {
            "text": ":games",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/games.gif"
        },
        {
            "text": ":dp",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/dp.gif"
        },
        {
            "text": ":cystg",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/cystg.gif"
        },
        {
            "text": ":cool",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/cool2.gif"
        },
        {
            "text": ":cendolbig",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_big_cendol.gif"
        },
        {
            "text": ":cekpm",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/cekpm.gif"
        },
        {
            "text": ":cd:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fd_2.gif"
        },
        {
            "text": ":cd",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/capede.gif"
        },
        {
            "text": ":bola",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/bola.gif"
        },
        {
            "text": ":bingung",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/bingung.gif"
        },
        {
            "text": ":bigo:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fd_3.gif"
        },
        {
            "text": ":betty",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_sm_maho.gif"
        },
        {
            "text": ":berduka",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/berduka.gif"
        },
        {
            "text": ":bedug",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/lebaran02.gif"
        },
        {
            "text": ":batabig",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_big_batamerah.gif"
        },
        {
            "text": ":babygirl",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/babygirl.gif"
        },
        {
            "text": ":babyboy1",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/babyboy1.gif"
        },
        {
            "text": ":babyboy",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/babyboy.gif"
        },
        {
            "text": ":angel",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/angel1.gif"
        },
        {
            "text": ":2thumbup",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/jempol2.gif"
        },
        {
            "text": ":1thumbup",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/jempol1.gif"
        },
        {
            "text": ":Yb",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_sm_peace.gif"
        },
        {
            "text": ":takuts",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/takuts.gif"
        },
        {
            "text": ":sundulgans",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/sundulgans.gif"
        },
        {
            "text": ":shutups",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/shutup-kecil.gif"
        },
        {
            "text": ":reposts",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/reposts.gif"
        },
        {
            "text": ":ngakaks",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/ngakaks.gif"
        },
        {
            "text": ":najiss",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/najiss.gif"
        },
        {
            "text": ":malus",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/malus.gif"
        },
        {
            "text": ":mads",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/mads.gif"
        },
        {
            "text": ":kisss",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/kisss.gif"
        },
        {
            "text": ":ilovekaskuss",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/iluvkaskuss.gif"
        },
        {
            "text": ":iloveindonesias",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/iloveindonesias.gif"
        },
        {
            "text": ":hammers",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/hammers.gif"
        },
        {
            "text": ":cendols",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/cendols.gif"
        },
        {
            "text": ":cendolb",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_sm_cendol.gif"
        },
        {
            "text": ":cekpms",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/cekpms.gif"
        },
        {
            "text": ":capedes",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/capedes.gif"
        },
        {
            "text": ":bookmarks",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/bookmark-kecil.gif"
        },
        {
            "text": ":bingungs",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/bingungs.gif"
        },
        {
            "text": ":bettys",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/mahos.gif"
        },
        {
            "text": ":berdukas",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/berdukas.gif"
        },
        {
            "text": ":berbusas",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/berbusa-kecil.gif"
        },
        {
            "text": ":batas",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/batas.gif"
        },
        {
            "text": ":bata",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_sm_batamerah.gif"
        },
        {
            "text": ":armys",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/army-kecil.gif"
        },
        {
            "text": ":addfriends",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/add-friend-kecil.gif"
        },
        {
            "text": ":)b",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/s_sm_smile.gif"
        },
        {
            "text": ";)",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/13.gif"
        },
        {
            "text": ":wowcantik",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/001.gif"
        },
        {
            "text": ":tv",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/44.gif"
        },
        {
            "text": ":thumbup",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/47.gif"
        },
        {
            "text": ":thumbdown",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/48.gif"
        },
        {
            "text": ":think:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/006.gif"
        },
        {
            "text": ":tai",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/shit-3.gif"
        },
        {
            "text": ":tabrakan:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/tabrakan.gif"
        },
        {
            "text": ":table:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/39.gif"
        },
        {
            "text": ":sun:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/008.gif"
        },
        {
            "text": ":siul",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/020.gif"
        },
        {
            "text": ":shutup:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/5.gif"
        },
        {
            "text": ":shakehand",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/49.gif"
        },
        {
            "text": ":rose:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/34.gif"
        },
        {
            "text": ":rolleyes",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/01.gif"
        },
        {
            "text": ":ricebowl:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/32.gif"
        },
        {
            "text": ":rainbow:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/e02.gif"
        },
        {
            "text": ":rain:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/60.gif"
        },
        {
            "text": ":present:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/40.gif"
        },
        {
            "text": ":Phone:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/41.gif"
        },
        {
            "text": ":Peace:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/005.gif"
        },
        {
            "text": ":Paws:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/paw.gif"
        },
        {
            "text": ":p",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/6.gif"
        },
        {
            "text": ":Onigiri",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/rice.gif"
        },
        {
            "text": ":o",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/07.gif"
        },
        {
            "text": ":norose:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/35.gif"
        },
        {
            "text": ":nohope:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/q11.gif"
        },
        {
            "text": ":ngacir:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/ngacir.gif"
        },
        {
            "text": ":moon:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/007.gif"
        },
        {
            "text": ":metal",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/q17.gif"
        },
        {
            "text": ":medicine:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/33.gif"
        },
        {
            "text": ":matabelo:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/004.gif"
        },
        {
            "text": ":malu:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/1.gif"
        },
        {
            "text": ":mad",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/12.gif"
        },
        {
            "text": ":linux2:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/26.gif"
        },
        {
            "text": ":linux1:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/25.gif"
        },
        {
            "text": ":kucing:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/28.gif"
        },
        {
            "text": ":kissmouth",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/36.gif"
        },
        {
            "text": ":kissing:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/014.gif"
        },
        {
            "text": ":kimpoi:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/smiley_couple.gif"
        },
        {
            "text": ":kagets:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/3.gif"
        },
        {
            "text": ":hi:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/hi.gif"
        },
        {
            "text": ":heart:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/37.gif"
        },
        {
            "text": ":hammer:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/8.gif"
        },
        {
            "text": ":gila:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/crazy.gif"
        },
        {
            "text": ":genit",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/q03.gif"
        },
        {
            "text": ":fuck:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fuck-4.gif"
        },
        {
            "text": ":fuck3:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fuck-8.gif"
        },
        {
            "text": ":fuck2:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/fuck-6.gif"
        },
        {
            "text": ":frog:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/frog.gif"
        },
        {
            "text": ":fm:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/smileyfm329wj.gif"
        },
        {
            "text": ":flower:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/e03.gif"
        },
        {
            "text": ":exclamati",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/52.gif"
        },
        {
            "text": ":email",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/43.gif"
        },
        {
            "text": ":eek",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/4.gif"
        },
        {
            "text": ":doctor",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/18.gif"
        },
        {
            "text": ":D",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/14.gif"
        },
        {
            "text": ":cool:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/05.gif"
        },
        {
            "text": ":confused",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/7.gif"
        },
        {
            "text": ":coffee:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/31.gif"
        },
        {
            "text": ":clock",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/42.gif"
        },
        {
            "text": ":ck",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/kaskuslove.gif"
        },
        {
            "text": ":buldog",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/woof.gif"
        },
        {
            "text": ":breakheart",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/38.gif"
        },
        {
            "text": ":bingung:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/bolakbalik.gif"
        },
        {
            "text": ":bikini",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/vana-bum-vanaweb-dot-com.gif"
        },
        {
            "text": ":berbusa",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/q20.gif"
        },
        {
            "text": ":beer:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/smiley_beer.gif"
        },
        {
            "text": ":baby:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/30.gif"
        },
        {
            "text": ":babi:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/27.gif"
        },
        {
            "text": ":army",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/24.gif"
        },
        {
            "text": ":anjing:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/29.gif"
        },
        {
            "text": ":angel:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/017.gif"
        },
        {
            "text": ":amazed:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/amazed.gif"
        },
        {
            "text": ":afro:",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/kribo.gif"
        },
        {
            "text": ":)",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/15.gif"
        },
        {
            "text": ":(",
            "url": "http:\/\/cdn.kaskusplayground.local\/images\/mobile\/smiley\/06.gif"
        }
    ]
}
```

# Mutualfriend



## GET mutualfriend

Get List of Mutual friends between currently logged in and user

### HTTP Request

`GET /mutualfriend/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)



# Mypost



## GET mypost

Get List of User Post

### HTTP Request

`GET /mypost/{user_id}/{thread_id}`

Parameter | Description
--------- | -----------
user_id|User Id
thread_id|Thread Id that you want to see whose post that posted by certain user
output|output format (JSON or XML)




> Example response

```json
{
    "total_post": 0,
    "current_page": 1,
    "total_page": 0,
    "per_page": 10,
    "posts": []
}
```

## GET mypost

Get List of User Post

### HTTP Request

`GET /mypost/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)




> Example response

```json
{
    "total_post": 15799,
    "current_page": 1,
    "total_page": 1580,
    "per_page": 10,
    "posts": [
        {
            "post_userid": "11",
            "dateline": 1450336193,
            "visible": 1,
            "pagetext": "a\nbc\nc\nd\ne",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56725fc18ead0ec2000041d0",
            "post": [
                {
                    "type": "text",
                    "text": "a\nbc\nc\nd\ne",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "a\nbc\nc\nd\ne",
            "decoded": "a<br \/> bc<br \/> c<br \/> d<br \/> e",
            "pagetext_noquote": "a\nbc\nc\nd\ne",
            "title": "test",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450336186,
            "visible": 1,
            "pagetext": "a\nb\nc\nd",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56725fba8ead0eeb2b0041cb",
            "post": [
                {
                    "type": "text",
                    "text": "a\nb\nc\nd",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "a\nb\nc\nd",
            "decoded": "a<br \/> b<br \/> c<br \/> d",
            "pagetext_noquote": "a\nb\nc\nd",
            "title": "test",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450335997,
            "visible": 1,
            "pagetext": "a\nb\nc\nd",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56725efd8ead0e892c0041d1",
            "post": [
                {
                    "type": "text",
                    "text": "a\nb\nc\nd",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "a\nb\nc\nd",
            "decoded": "a<br \/> b<br \/> c<br \/> d",
            "pagetext_noquote": "a\nb\nc\nd",
            "title": "test",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450335989,
            "visible": 1,
            "pagetext": "a\nb\nc\nd\ne",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56725ef58ead0ec2000041cd",
            "post": [
                {
                    "type": "text",
                    "text": "a\nb\nc\nd\ne",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "a\nb\nc\nd\ne",
            "decoded": "a<br \/> b<br \/> c<br \/> d<br \/> e",
            "pagetext_noquote": "a\nb\nc\nd\ne",
            "title": "test",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450322737,
            "visible": 1,
            "pagetext": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap ",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56722b318ead0eeb2b0041c8",
            "post": [
                {
                    "type": "text",
                    "text": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "decoded": "Top 30 Hotel Deals Sudah Mulai<br \/> <br \/> Halo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive<br \/> Di sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!<br \/> Semuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "pagetext_noquote": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450322724,
            "visible": 1,
            "pagetext": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap ",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56722b248ead0e892c0041ce",
            "post": [
                {
                    "type": "text",
                    "text": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "decoded": "Top 30 Hotel Deals Sudah Mulai<br \/> <br \/> Halo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive<br \/> Di sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!<br \/> Semuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "pagetext_noquote": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450322715,
            "visible": 1,
            "pagetext": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap ",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56722b1b8ead0ec2000041ca",
            "post": [
                {
                    "type": "text",
                    "text": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "decoded": "Top 30 Hotel Deals Sudah Mulai<br \/> <br \/> Halo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive<br \/> Di sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!<br \/> Semuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "pagetext_noquote": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450318722,
            "visible": 1,
            "pagetext": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap ",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56721b828ead0eeb2b0041c6",
            "post": [
                {
                    "type": "text",
                    "text": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "decoded": "Top 30 Hotel Deals Sudah Mulai<br \/> <br \/> Halo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive<br \/> Di sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!<br \/> Semuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "pagetext_noquote": "Top 30 Hotel Deals Sudah Mulai\n\nHalo Gan diskon hotel Tiket.com balik lagi nih dengan tema promo Top Hotels Exclusive\nDi sini ada 360 Hotel list rekomendasi hotel yang baru tiap 2 minggu Gan!\nSemuanya tersebar di 6 kota besar Indonesia dan 3 negara Asia untuk Agan nikmatin liburan tahun ini! Mantap",
            "title": "test create thread",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450318698,
            "visible": 1,
            "pagetext": "hai semua\n\naaa",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56721b6a8ead0e892c0041cc",
            "post": [
                {
                    "type": "text",
                    "text": "hai semua\n\naaa",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "hai semua\n\naaa",
            "decoded": "hai semua<br \/> <br \/> aaa",
            "pagetext_noquote": "hai semua\n\naaa",
            "title": "test create thread",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        },
        {
            "post_userid": "11",
            "dateline": 1450318675,
            "visible": 1,
            "pagetext": "hai semua",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11,
            "post_id": "56721b538ead0ec2000041c8",
            "post": [
                {
                    "type": "text",
                    "text": "hai semua",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "hai semua",
            "decoded": "hai semua",
            "pagetext_noquote": "hai semua",
            "title": "test create thread",
            "forum_id": 21,
            "forum_title": "THE LOUNGE"
        }
    ]
}
```

# Myquotedpost



## GET myquotedpost

Get Quoted Post List from logged in user

### HTTP Request

`GET /myquotedpost`

Parameter | Description
--------- | -----------




> Example response

```json
[
    {
        "thread_id": "000000000000000000878886",
        "post_username": "kudaliar",
        "post_userid": "5915",
        "title": "Taekwondo (&#53468;&#44428;&#46020;) WTF Thread",
        "dateline": 1446168586,
        "pagetext": "test multiquote aja ini",
        "visible": 1,
        "viewed": 1,
        "post_id": "5632c80ac721e659388b457d",
        "forum_id": "144",
        "forum_name": "Martial Arts"
    },
    {
        "thread_id": "000000000000000000878886",
        "post_username": "kudaliar",
        "post_userid": "5915",
        "title": "Taekwondo (&#53468;&#44428;&#46020;) WTF Thread",
        "dateline": 1446025500,
        "pagetext": "AHHAHAHA",
        "visible": 1,
        "viewed": 1,
        "post_id": "5630991cc721e6b1158b4574",
        "forum_id": "144",
        "forum_name": "Martial Arts"
    },
    {
        "thread_id": "000000000000000000878886",
        "post_username": "kudaliar",
        "post_userid": "5915",
        "title": "Taekwondo (&#53468;&#44428;&#46020;) WTF Thread",
        "dateline": 1446019509,
        "pagetext": "mampuy:ilovekaskuss",
        "visible": 1,
        "viewed": 1,
        "post_id": "563081b5c721e6d5098b458b",
        "forum_id": "144",
        "forum_name": "Martial Arts"
    },
    {
        "thread_id": "000000000000000000878886",
        "post_username": "kudaliar",
        "post_userid": "5915",
        "title": "Taekwondo (&#53468;&#44428;&#46020;) WTF Thread",
        "dateline": 1446010851,
        "pagetext": "aduh",
        "visible": 1,
        "viewed": 1,
        "post_id": "56305fe3c721e63a3a8b4582",
        "forum_id": "144",
        "forum_name": "Martial Arts"
    },
    {
        "thread_id": "000000000000000000878886",
        "post_username": "kudaliar",
        "post_userid": "5915",
        "title": "Taekwondo (&#53468;&#44428;&#46020;) WTF Thread",
        "dateline": 1446010772,
        "pagetext": "astajim final!",
        "visible": 1,
        "viewed": 1,
        "post_id": "56305f94c721e6d5518b4585",
        "forum_id": "144",
        "forum_name": "Martial Arts"
    },
    {
        "thread_id": "000000000000000000878886",
        "post_username": "kudaliar",
        "post_userid": "5915",
        "title": "Taekwondo (&#53468;&#44428;&#46020;) WTF Thread",
        "dateline": 1446010657,
        "pagetext": "astajim lagiii",
        "visible": 1,
        "viewed": 1,
        "post_id": "56305f21c721e6d5098b4589",
        "forum_id": "144",
        "forum_name": "Martial Arts"
    }
]
```

# Mythread



## GET mythread

Get List of User Thread

### HTTP Request

`GET /mythread/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "dateline": 1450350742,
            "thread_starter": "56729896c721e6e8638b4568",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450350742,
            "last_post_id": "56729896c721e6e8638b4568",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1"
            },
            "thread_id": "56729896c721e6e8638b4567",
            "post_userid": 11,
            "title": "TEST SUBSCRIBE",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450336193,
            "thread_starter": "56725fc18ead0ec2000041d0",
            "forum_id": 21,
            "forum_title": "THE LOUNGE",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450336193,
            "last_post_id": "56725fc18ead0ec2000041d0",
            "thread_id": "56725fc18ead0ec2000041d1",
            "post_userid": 11,
            "title": "test",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450336186,
            "thread_starter": "56725fba8ead0eeb2b0041cb",
            "forum_id": 21,
            "forum_title": "THE LOUNGE",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450336186,
            "last_post_id": "56725fba8ead0eeb2b0041cb",
            "thread_id": "56725fba8ead0eeb2b0041cc",
            "post_userid": 11,
            "title": "test",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450335997,
            "thread_starter": "56725efd8ead0e892c0041d1",
            "forum_id": 21,
            "forum_title": "THE LOUNGE",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450335997,
            "last_post_id": "56725efd8ead0e892c0041d1",
            "thread_id": "56725efd8ead0e892c0041d2",
            "post_userid": 11,
            "title": "test",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450335989,
            "thread_starter": "56725ef58ead0ec2000041cd",
            "forum_id": 21,
            "forum_title": "THE LOUNGE",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450335989,
            "last_post_id": "56725ef58ead0ec2000041cd",
            "thread_id": "56725ef58ead0ec2000041ce",
            "post_userid": 11,
            "title": "test",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450322737,
            "thread_starter": "56722b318ead0eeb2b0041c8",
            "forum_id": 21,
            "forum_title": "THE LOUNGE",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450322737,
            "last_post_id": "56722b318ead0eeb2b0041c8",
            "thread_id": "56722b318ead0eeb2b0041c9",
            "post_userid": 11,
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450322724,
            "thread_starter": "56722b248ead0e892c0041ce",
            "forum_id": 21,
            "forum_title": "THE LOUNGE",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450322724,
            "last_post_id": "56722b248ead0e892c0041ce",
            "thread_id": "56722b248ead0e892c0041cf",
            "post_userid": 11,
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450322715,
            "thread_starter": "56722b1b8ead0ec2000041ca",
            "forum_id": 21,
            "forum_title": "THE LOUNGE",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450322715,
            "last_post_id": "56722b1b8ead0ec2000041ca",
            "thread_id": "56722b1b8ead0ec2000041cb",
            "post_userid": 11,
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450318722,
            "thread_starter": "56721b828ead0eeb2b0041c6",
            "forum_id": 21,
            "forum_title": "The Lounge",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450318722,
            "last_post_id": "56721b828ead0eeb2b0041c6",
            "thread_id": "56721b828ead0eeb2b0041c5",
            "post_userid": 11,
            "title": "test create thread",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450318698,
            "thread_starter": "56721b6a8ead0e892c0041cc",
            "forum_id": 21,
            "forum_title": "The Lounge",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450318698,
            "last_post_id": "56721b6a8ead0e892c0041cc",
            "thread_id": "56721b6a8ead0e892c0041cb",
            "post_userid": 11,
            "title": "test create thread",
            "thread_type": 10,
            "initial_prefix_id": "",
            "prefix_id": "",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/img\/default-forum-encore-n.png"
            },
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        }
    ],
    "thread_num": 5011,
    "current_page": 1,
    "total_page": 502,
    "per_page": 10
}
```

# Mywtb



## GET Mywtb/active

Get List of User WTB thread (active)

### HTTP Request

`GET /mywtb/active/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "dateline": 1447386377,
            "thread_starter": "56455d017a1f5cbf2a8b463e",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 5,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1449209635,
            "last_post_id": "56455d017a1f5cbf2a8b463e",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455d017a1f5cbf2a8b463f",
            "post_userid": 11,
            "title": "Arif foto model cantik",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 90961,
            "discount": 0,
            "discounted_price": 90961,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447386429,
            "thread_starter": "56455d3d7a1f5c28008b4653",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 9,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1449209470,
            "last_post_id": "56455d3d7a1f5c28008b4653",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455d3d7a1f5c28008b4654",
            "post_userid": 11,
            "title": "Samsung Galaxy S4 16 GB 4d2626fb17997233d146d1f42c016297",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 19419883,
            "discount": 10,
            "discounted_price": 17477895,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447386377,
            "thread_starter": "56455d097a1f5c29008b465b",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 19,
            "reply_count": 14,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447386419,
            "last_post_id": "56455d337a1f5cbf2a8b464e",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455d097a1f5c29008b465c",
            "post_userid": 11,
            "title": "Zulamdat foto model cantik",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 359678,
            "discount": 0,
            "discounted_price": 359678,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447386362,
            "thread_starter": "56455cfa7a1f5cbf2a8b463a",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 5,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447386362,
            "last_post_id": "56455cfa7a1f5cbf2a8b463a",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455cfa7a1f5cbf2a8b463b",
            "post_userid": 11,
            "title": "Stevan dan Stevan main-main di bioskop",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 568208,
            "discount": 0,
            "discounted_price": 568208,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447386360,
            "thread_starter": "56455cf87a1f5c29008b4655",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447386360,
            "last_post_id": "56455cf87a1f5c29008b4655",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455cf87a1f5c29008b4656",
            "post_userid": 11,
            "title": "Denza sedang lari di GOR",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 756148,
            "discount": 0,
            "discounted_price": 756148,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447385838,
            "thread_starter": "56455aee7a1f5c28008b45fd",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447385838,
            "last_post_id": "56455aee7a1f5c28008b45fd",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455aee7a1f5c28008b45fe",
            "post_userid": 11,
            "title": "Tono pergi ke pasar",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 308355,
            "discount": 0,
            "discounted_price": 308355,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447051552,
            "thread_starter": "564041207a1f5c29008b4665",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 4,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447051552,
            "last_post_id": "564041207a1f5c29008b4665",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "564041207a1f5c29008b4666",
            "post_userid": 11,
            "title": "Iphone 3 8 GB 201f7dab6f2e7fb7fdc89742d4f1b107",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 14154977,
            "discount": 10,
            "discounted_price": 12739479,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447051493,
            "thread_starter": "564040e57a1f5c28008b4640",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447051493,
            "last_post_id": "564040e57a1f5c28008b4640",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "thread_id": "564040e57a1f5c28008b4641",
            "post_userid": 11,
            "title": "Vilia main-main di bioskop",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 747952,
            "discount": 0,
            "discounted_price": 747952,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447051033,
            "thread_starter": "56403f197a1f5c29008b460c",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447051033,
            "last_post_id": "56403f197a1f5c29008b460c",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "thread_id": "56403f197a1f5c29008b460d",
            "post_userid": 11,
            "title": "Vilia dan Vilia main-main di bioskop",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 674641,
            "discount": 0,
            "discounted_price": 674641,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1445948605,
            "thread_starter": "562f6cbd7a1f5c28008b4651",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1445948605,
            "last_post_id": "562f6cbd7a1f5c28008b4651",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "thread_id": "562f6cbd7a1f5c28008b4652",
            "post_userid": 11,
            "title": "Steven dan Steven lagi belajar",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 264333,
            "discount": 0,
            "discounted_price": 264333,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        }
    ],
    "thread_num": 789,
    "current_page": 1,
    "total_page": 79,
    "per_page": 10,
    "cursor": "MTQ0NTk0ODYwNQ"
}
```

## GET Mywtb/got_it

Get List of User WTB thread (Got It)

### HTTP Request

`GET /mywtb/got_it/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "dateline": 1426753762,
            "thread_starter": "550a88e2de324eca000041b3",
            "forum_id": 313,
            "forum_title": "Elektronik Rumah Tangga",
            "visible": 1,
            "views": 25,
            "reply_count": 3,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1426816218,
            "last_post_id": "550b7cda5e811207a30041bd",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "prefix_id": "SOLD",
            "thread_id": "550a88e2de324eca000041b2",
            "post_userid": 11,
            "title": "Coba Beli motor",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 123123,
            "discount": 50,
            "discounted_price": 61562,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1425354942,
            "thread_starter": "54f530be1ef4cc7d080041a8",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 3,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1425354942,
            "last_post_id": "54f530be1ef4cc7d080041a8",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "prefix_id": "SOLD",
            "thread_id": "54f530be1ef4cc7d080041a7",
            "post_userid": 11,
            "title": "hape bekas pakai nuris",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 1000000,
            "discount": 0,
            "discounted_price": 1000000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1416820932,
            "thread_starter": "5472f8c4c721e6fa69000005",
            "forum_id": 220,
            "forum_title": "Alat-Alat Olahraga",
            "visible": 1,
            "views": 4,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1416820932,
            "last_post_id": "5472f8c4c721e6fa69000005",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "prefix_id": "SOLD",
            "thread_id": "5472f8c4c721e6fa69000004",
            "post_userid": 11,
            "title": "beli donk",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 2134,
            "discount": false,
            "discounted_price": 2134,
            "sundul_enabled": 0,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        }
    ],
    "thread_num": 3,
    "current_page": 1,
    "total_page": 1,
    "per_page": 10,
    "cursor": "MTQxNjgyMDkzMg"
}
```

## GET Mywtb

Get List of User WTB thread (Active + Got It)

### HTTP Request

`GET /mywtb/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "dateline": 1447386377,
            "thread_starter": "56455d017a1f5cbf2a8b463e",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 5,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1449209635,
            "last_post_id": "56455d017a1f5cbf2a8b463e",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455d017a1f5cbf2a8b463f",
            "post_userid": 11,
            "title": "Arif foto model cantik",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 90961,
            "discount": 0,
            "discounted_price": 90961,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447386429,
            "thread_starter": "56455d3d7a1f5c28008b4653",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 9,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1449209470,
            "last_post_id": "56455d3d7a1f5c28008b4653",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455d3d7a1f5c28008b4654",
            "post_userid": 11,
            "title": "Samsung Galaxy S4 16 GB 4d2626fb17997233d146d1f42c016297",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 19419883,
            "discount": 10,
            "discounted_price": 17477895,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447386377,
            "thread_starter": "56455d097a1f5c29008b465b",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 19,
            "reply_count": 14,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447386419,
            "last_post_id": "56455d337a1f5cbf2a8b464e",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455d097a1f5c29008b465c",
            "post_userid": 11,
            "title": "Zulamdat foto model cantik",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 359678,
            "discount": 0,
            "discounted_price": 359678,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447386362,
            "thread_starter": "56455cfa7a1f5cbf2a8b463a",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 5,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447386362,
            "last_post_id": "56455cfa7a1f5cbf2a8b463a",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455cfa7a1f5cbf2a8b463b",
            "post_userid": 11,
            "title": "Stevan dan Stevan main-main di bioskop",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 568208,
            "discount": 0,
            "discounted_price": 568208,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447386360,
            "thread_starter": "56455cf87a1f5c29008b4655",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447386360,
            "last_post_id": "56455cf87a1f5c29008b4655",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455cf87a1f5c29008b4656",
            "post_userid": 11,
            "title": "Denza sedang lari di GOR",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 756148,
            "discount": 0,
            "discounted_price": 756148,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447385838,
            "thread_starter": "56455aee7a1f5c28008b45fd",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447385838,
            "last_post_id": "56455aee7a1f5c28008b45fd",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "56455aee7a1f5c28008b45fe",
            "post_userid": 11,
            "title": "Tono pergi ke pasar",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 308355,
            "discount": 0,
            "discounted_price": 308355,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447051552,
            "thread_starter": "564041207a1f5c29008b4665",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 4,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447051552,
            "last_post_id": "564041207a1f5c29008b4665",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "payment_method": null,
            "thread_id": "564041207a1f5c29008b4666",
            "post_userid": 11,
            "title": "Iphone 3 8 GB 201f7dab6f2e7fb7fdc89742d4f1b107",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 14154977,
            "discount": 10,
            "discounted_price": 12739479,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447051493,
            "thread_starter": "564040e57a1f5c28008b4640",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447051493,
            "last_post_id": "564040e57a1f5c28008b4640",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "thread_id": "564040e57a1f5c28008b4641",
            "post_userid": 11,
            "title": "Vilia main-main di bioskop",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 747952,
            "discount": 0,
            "discounted_price": 747952,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1447051033,
            "thread_starter": "56403f197a1f5c29008b460c",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447051033,
            "last_post_id": "56403f197a1f5c29008b460c",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "thread_id": "56403f197a1f5c29008b460d",
            "post_userid": 11,
            "title": "Vilia dan Vilia main-main di bioskop",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 674641,
            "discount": 0,
            "discounted_price": 674641,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1445948605,
            "thread_starter": "562f6cbd7a1f5c28008b4651",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1445948605,
            "last_post_id": "562f6cbd7a1f5c28008b4651",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTB",
            "thread_id": "562f6cbd7a1f5c28008b4652",
            "post_userid": 11,
            "title": "Steven dan Steven lagi belajar",
            "thread_type": 21,
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "item_price": 264333,
            "discount": 0,
            "discounted_price": 264333,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        }
    ],
    "thread_num": 792,
    "current_page": 1,
    "total_page": 80,
    "per_page": 10,
    "cursor": "MTQ0NTk0ODYwNQ"
}
```

# Mywts



## GET Mywts/active

Get List of User WTS thread (active)

### HTTP Request

`GET /mywts/active/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "dateline": 1450350742,
            "thread_starter": "56729896c721e6e8638b4568",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450350742,
            "last_post_id": "56729896c721e6e8638b4568",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1"
            },
            "thread_id": "56729896c721e6e8638b4567",
            "post_userid": 11,
            "title": "TEST SUBSCRIBE",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 300000,
            "discount": 0,
            "discounted_price": 300000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450252803,
            "thread_starter": "56711a038ead0e56000041d3",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450252803,
            "last_post_id": "56711a038ead0e56000041d3",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "56711a038ead0e56000041d4",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 999",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450248736,
            "thread_starter": "56710a208ead0e54000041d4",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450248736,
            "last_post_id": "56710a208ead0e54000041d4",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": "2",
            "thread_id": "56710a208ead0e54000041d5",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 999",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450248681,
            "thread_starter": "567109e98ead0e54000041d1",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450248681,
            "last_post_id": "567109e98ead0e54000041d1",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "567109e98ead0e54000041d2",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450248299,
            "thread_starter": "5671086b8ead0e56000041d0",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450248299,
            "last_post_id": "5671086b8ead0e56000041d0",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": "1,2",
            "thread_id": "5671086b8ead0e56000041d1",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450247965,
            "thread_starter": "5671071d8ead0e56000041c5",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450247965,
            "last_post_id": "5671071d8ead0e56000041c5",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5671071d8ead0e56000041c6",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450246799,
            "thread_starter": "5671028f8ead0e56000041c2",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450246799,
            "last_post_id": "5671028f8ead0e56000041c2",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5671028f8ead0e56000041c3",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450166333,
            "thread_starter": "566fc83d8ead0e54000041c6",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 15,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450166333,
            "last_post_id": "566fc83d8ead0e54000041c6",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": "2",
            "thread_id": "566fc83d8ead0e54000041c7",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450091335,
            "thread_starter": "566ea3478ead0e56000041b4",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 12,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450091335,
            "last_post_id": "566ea3478ead0e56000041b4",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": "2",
            "thread_id": "566ea3478ead0e56000041b5",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450090515,
            "thread_starter": "566ea0138ead0e54000041b6",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 0,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450090515,
            "last_post_id": "566ea0138ead0e54000041b6",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "566ea0138ead0e54000041b7",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        }
    ],
    "thread_num": 734,
    "current_page": 1,
    "total_page": 74,
    "per_page": 10,
    "cursor": "MTQ1MDA5MDUxNQ"
}
```

## GET Mywts/sold_out

Get List of User WTS thread (Sold Out)

### HTTP Request

`GET /mywts/sold_out/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "dateline": 1426077677,
            "thread_starter": "550037edc721e6f25f8b457e",
            "forum_id": 210,
            "forum_title": "Handphone &amp; PDA",
            "visible": 1,
            "views": 3,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1426077677,
            "last_post_id": "550037edc721e6f25f8b457e",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "prefix_id": "SOLD",
            "thread_id": "550037edc721e6f25f8b457d",
            "post_userid": 11,
            "title": "Cara unik membantu Veteran Perang dengan foto \"HOT SHOTS\"",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 10000,
            "discount": 12,
            "discounted_price": 8800,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1421997580,
            "thread_starter": "54c1f60c8ead0eda000041bb",
            "forum_id": 221,
            "forum_title": "Alat-Alat Musik",
            "visible": 1,
            "views": 3,
            "reply_count": 1,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1421997610,
            "last_post_id": "54c1f62a8ead0ed9000041c1",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "SOLD",
            "thread_id": "54c1f60c8ead0eda000041bc",
            "post_userid": 11,
            "title": "aaa111",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 100500,
            "discount": 0,
            "discounted_price": 100500,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1421633006,
            "thread_starter": "54bc65ee8ead0ed60000489e",
            "forum_id": 221,
            "forum_title": "Alat-Alat Musik",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1421633006,
            "last_post_id": "54bc65ee8ead0ed60000489e",
            "resources": {
                "images": [],
                "thumbnail": "\/e3.1\/images\/default-fjb-400.png",
                "images_thumbnail": []
            },
            "prefix_id": "SOLD",
            "thread_id": "54bc65ee8ead0ed60000489f",
            "post_userid": 11,
            "title": "tnonotnot tonontonton",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 3333,
            "discount": 22,
            "discounted_price": 2600,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        }
    ],
    "thread_num": 3,
    "current_page": 1,
    "total_page": 1,
    "per_page": 10,
    "cursor": "MTQyMTYzMzAwNg"
}
```

## GET Mywts

Get List of User WTS thread (Active + Sold out)

### HTTP Request

`GET /mywts/{user_id}`

Parameter | Description
--------- | -----------
user_id|User Id
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "dateline": 1450350742,
            "thread_starter": "56729896c721e6e8638b4568",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450350742,
            "last_post_id": "56729896c721e6e8638b4568",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1"
            },
            "thread_id": "56729896c721e6e8638b4567",
            "post_userid": 11,
            "title": "TEST SUBSCRIBE",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 300000,
            "discount": 0,
            "discounted_price": 300000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450252803,
            "thread_starter": "56711a038ead0e56000041d3",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450252803,
            "last_post_id": "56711a038ead0e56000041d3",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "56711a038ead0e56000041d4",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 999",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450248736,
            "thread_starter": "56710a208ead0e54000041d4",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450248736,
            "last_post_id": "56710a208ead0e54000041d4",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": "2",
            "thread_id": "56710a208ead0e54000041d5",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 999",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450248681,
            "thread_starter": "567109e98ead0e54000041d1",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450248681,
            "last_post_id": "567109e98ead0e54000041d1",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "567109e98ead0e54000041d2",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450248299,
            "thread_starter": "5671086b8ead0e56000041d0",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450248299,
            "last_post_id": "5671086b8ead0e56000041d0",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": "1,2",
            "thread_id": "5671086b8ead0e56000041d1",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450247965,
            "thread_starter": "5671071d8ead0e56000041c5",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450247965,
            "last_post_id": "5671071d8ead0e56000041c5",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5671071d8ead0e56000041c6",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450246799,
            "thread_starter": "5671028f8ead0e56000041c2",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 2,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450246799,
            "last_post_id": "5671028f8ead0e56000041c2",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5671028f8ead0e56000041c3",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450166333,
            "thread_starter": "566fc83d8ead0e54000041c6",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 15,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450166333,
            "last_post_id": "566fc83d8ead0e54000041c6",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": "2",
            "thread_id": "566fc83d8ead0e54000041c7",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450091335,
            "thread_starter": "566ea3478ead0e56000041b4",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 12,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450091335,
            "last_post_id": "566ea3478ead0e56000041b4",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": "2",
            "thread_id": "566ea3478ead0e56000041b5",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "dateline": 1450090515,
            "thread_starter": "566ea0138ead0e54000041b6",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 0,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450090515,
            "last_post_id": "566ea0138ead0e54000041b6",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "566ea0138ead0e54000041b7",
            "post_userid": 11,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        }
    ],
    "thread_num": 737,
    "current_page": 1,
    "total_page": 74,
    "per_page": 10,
    "cursor": "MTQ1MDA5MDUxNQ"
}
```

# Pmfolder



## GET pmfolder

Get list of Private Message Folder

### HTTP Request

`GET /pmfolder`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
[
    {
        "total_message": 16,
        "total_message_sticky": 20,
        "total_message_unread": 11,
        "total_message_sticky_unread": 14,
        "folder_name": "Inbox",
        "folder_id": 0
    },
    {
        "total_message": 5,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "Outbox",
        "folder_id": -1
    },
    {
        "total_message": 20,
        "total_message_sticky": 20,
        "total_message_unread": 14,
        "total_message_sticky_unread": 14,
        "folder_name": "Notices",
        "folder_id": -9
    },
    {
        "total_message": 0,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "API TEST",
        "folder_id": 1
    },
    {
        "total_message": 0,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "test folder",
        "folder_id": 3
    },
    {
        "total_message": 1,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "asdsad",
        "folder_id": 5
    },
    {
        "total_message": 0,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "lala",
        "folder_id": 6
    },
    {
        "total_message": 0,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "API_TEST",
        "folder_id": 7
    }
]
```

## POST pmfolder

Create new private message folder

### HTTP Request

`POST /pmfolder`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## DELETE pmfolder

Create new private message folder

### HTTP Request

`DELETE /pmfolder/{folder_id}`

Parameter | Description
--------- | -----------
folder_id|Delete private message folder
output|output format (JSON or XML)



# Post



## GET post

Get current post detail.

### HTTP Request

`GET /post/{post_id}`

Parameter | Description
--------- | -----------
oauth_callback|Callback url after user do authorization



## POST post

Edit current post detail

### HTTP Request

`POST /post/{post_id}`

Parameter | Description
--------- | -----------
post_id|Post that we want to edit
output|output format (JSON or XML)



## GET post

Similar with /v1/forum_post or /v1/fjb_post or /v1/lapak_post.           It returns post detail regardless of its type. It is a little bit slower than specific post endpoints.

### HTTP Request

`GET /v1/post/{id}`

Parameter | Description
--------- | -----------
id|Post Id that we want to get the detail
output|output format (JSON or XML)
field|post field that need to be filtered



# Posts



## GET posts

Get post list that contains certain post

### HTTP Request

`GET /posts/{post_id}`

Parameter | Description
--------- | -----------
post_id|Post id
output|output format (JSON or XML)



# Reputation



## GET reputation

Get current user's reputation.

### HTTP Request

`GET /reputation`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "total_reputation": "1774",
    "list_reputation": [
        {
            "post_id": "562202147a1f5c28008b466e",
            "user_id": "11",
            "reputation": 15,
            "reason": "mamam nih",
            "dateline": 1445234141,
            "reputationid": "31618228",
            "post_title": "Henkie dan Henkie sedang lari di GOR",
            "thread_title": "Henkie dan Henkie sedang lari di GOR",
            "thread_id": "562202147a1f5c28008b466f"
        },
        {
            "post_id": "56208b2b8ead0eb9000041a7",
            "user_id": "11",
            "reputation": -14,
            "reason": "smilies mbahmu",
            "dateline": 1444991201,
            "reputationid": "31618226",
            "post_title": "testst smiliesss",
            "thread_title": "testst smiliesss",
            "thread_id": "56208b2b8ead0eb9000041a8"
        },
        {
            "post_id": "55dae3cb74d93a2b008b48eb",
            "user_id": "11",
            "reputation": 5,
            "reason": "ljlkjlkj",
            "dateline": 1442380617,
            "reputationid": "31618220",
            "post_title": "Babono pergi ke pasar",
            "thread_title": "Babono pergi ke pasar",
            "thread_id": "55dae3cb74d93a2b008b48ec"
        },
        {
            "post_id": "52e7a875bdcb172d118b4588",
            "user_id": "11",
            "reputation": 1,
            "reason": "",
            "dateline": 1390925118,
            "reputationid": "31106356",
            "post_title": ""
        },
        {
            "post_id": "52070561bccb172447000001",
            "user_id": "11",
            "reputation": 1,
            "reason": "From davinroswell neh gan,ditunggu KiRbaLnya yaa..Thx b4..",
            "dateline": 1376437301,
            "reputationid": "28551231",
            "post_title": ""
        },
        {
            "post_id": "50d5ba03ea74b49770000033",
            "user_id": "11",
            "reputation": 1,
            "reason": "jangan lupa gan...makasih",
            "dateline": 1356418996,
            "reputationid": "24303449",
            "post_title": ""
        },
        {
            "post_id": "000000000000000702586862",
            "user_id": "11",
            "reputation": 1,
            "reason": "sandiiochii :D",
            "dateline": 1340285971,
            "reputationid": "20766018",
            "post_title": ""
        },
        {
            "post_id": "000000000000000647751388",
            "user_id": "11",
            "reputation": 0,
            "reason": "",
            "dateline": 1329370014,
            "reputationid": "19461307",
            "post_title": ""
        },
        {
            "post_id": "000000000000000635920998",
            "user_id": "11",
            "reputation": 1,
            "reason": "as yazsmien",
            "dateline": 1327251915,
            "reputationid": "16979682",
            "post_title": ""
        },
        {
            "post_id": "000000000000000635920998",
            "user_id": "11",
            "reputation": 1,
            "reason": "andri_umt",
            "dateline": 1327251721,
            "reputationid": "16979556",
            "post_title": ""
        }
    ]
}
```

## GET reputation

Get reputation for selected post.

### HTTP Request

`GET /reputation/{post_id}`

Parameter | Description
--------- | -----------
post_id|Post id
output|output format (JSON or XML)



## POST reputation

Give reputation for selected post

### HTTP Request

`POST /reputation/{post_id}`

Parameter | Description
--------- | -----------
post_id|Post id
output|output format (JSON or XML)



# Stream



## GET stream

Get List of currently logged in's friend and followed users' posts.

### HTTP Request

`GET /stream`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



# Subscribe



## GET subscribe/lapak

Get user subscription list for lapak.

### HTTP Request

`GET /subscribe/lapak`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "forum_id": 197,
            "title": "TEST JUAL ANDROID DARI POSTMAN 999",
            "dateline": 1450252803,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 3,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56711a038ead0e56000041d3",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450252803,
            "last_post_id": "56711a038ead0e56000041d3",
            "sticky": 0,
            "prefix_id": "WTS",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "item_condition": 1,
            "item_price": 20000,
            "item_location": 10,
            "tagsearch": "apple",
            "resources": {
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images": [],
                "images_thumbnail": []
            },
            "discount": 0,
            "short_url": "http:\/\/kask.us\/dHa",
            "sundul_enabled": 1,
            "thread_id": "56711a038ead0e56000041d4",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 20000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "forum_id": 197,
            "title": "TEST JUAL ANDROID DARI POSTMAN 2",
            "dateline": 1450246799,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 2,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "5671028f8ead0e56000041c2",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1450246799,
            "last_post_id": "5671028f8ead0e56000041c2",
            "sticky": 0,
            "prefix_id": "WTS",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "item_condition": 1,
            "item_price": 20000,
            "item_location": 10,
            "tagsearch": "apple",
            "resources": {
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images": [],
                "images_thumbnail": []
            },
            "discount": 0,
            "short_url": "http:\/\/kask.us\/hxQLW",
            "sundul_enabled": 1,
            "thread_id": "5671028f8ead0e56000041c3",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 20000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "forum_id": 210,
            "title": "Arif foto model cantik",
            "dateline": 1447386377,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 5,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56455d017a1f5cbf2a8b463e",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1449209635,
            "last_post_id": "56455d017a1f5cbf2a8b463e",
            "sticky": 0,
            "prefix_id": "WTB",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "item_condition": 1,
            "item_price": 90961,
            "item_location": 1,
            "tagsearch": "rumah tangga,elektronik,fashion,iphone,makanan",
            "resources": {
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images": [],
                "images_thumbnail": []
            },
            "discount": 0,
            "short_url": "http:\/\/kask.us\/dGY",
            "sundul_enabled": 1,
            "thread_id": "56455d017a1f5cbf2a8b463f",
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 90961,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "forum_id": 210,
            "title": "Samsung Galaxy S4 16 GB 4d2626fb17997233d146d1f42c016297",
            "dateline": 1447386429,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 10,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56455d3d7a1f5c28008b4653",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1449209470,
            "last_post_id": "56455d3d7a1f5c28008b4653",
            "sticky": 0,
            "prefix_id": "WTB",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "item_condition": 2,
            "item_price": 19419883,
            "item_location": 28,
            "tagsearch": "samsung",
            "resources": {
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images": [],
                "images_thumbnail": []
            },
            "discount": 10,
            "short_url": "http:\/\/kask.us\/dG0",
            "sundul_enabled": 1,
            "thread_id": "56455d3d7a1f5c28008b4654",
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 17477895,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "forum_id": 210,
            "title": "test bikin lapapkkk",
            "dateline": 1447235027,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 3,
            "views": 19,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56430dd38ead0e5c2b0041bd",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447674622,
            "last_post_id": "5649c4568ead0ec9000041f6",
            "sticky": 0,
            "prefix_id": "WTS",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "item_condition": 1,
            "item_price": 10023023,
            "item_location": 1,
            "tagsearch": "nsdfslkdfjkslfjdkslfj",
            "resources": {
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images": [],
                "images_thumbnail": []
            },
            "discount": 0,
            "short_url": "http:\/\/kask.us\/hxQFg",
            "sundul_enabled": 1,
            "thread_id": "56430dd38ead0e5c2b0041be",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 10023023,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "forum_id": 449,
            "title": "beli kaktur berdurii",
            "dateline": 1446616672,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 3,
            "post_username": "pembeli",
            "post_userid": 222745,
            "first_post_id": "56399e608ead0ef33fc2a95c",
            "last_poster": "pembeli",
            "last_post_userid": 222745,
            "last_post": 1446616672,
            "last_post_id": "56399e608ead0ef33fc2a95c",
            "sticky": 0,
            "prefix_id": "WTB",
            "tagsearch": "elektronik",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 185000,
            "item_location": 4,
            "discount": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQDW",
            "sundul_enabled": 1,
            "thread_id": "56399e608ead0ef33fc2a95b",
            "initial_prefix_id": "WTB",
            "extra_attributes": [
                {
                    "attribute": "Tes",
                    "value": "Tes"
                }
            ],
            "thread_type": 21,
            "discounted_price": 185000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2006\/11\/21\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 6,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1416470860,
            "discount": 10,
            "first_post_id": "546da14cc721e6ce59000015",
            "forum_id": 197,
            "item_condition": 1,
            "item_location": 2,
            "item_price": 21212121,
            "last_post": 1444642872,
            "last_post_id": "5620a145f7cd2e0e5f0041ad",
            "last_post_userid": 11,
            "last_poster": "recca",
            "meta_images": [],
            "open": 1,
            "poll_id": 0,
            "post_userid": 1183,
            "post_username": "newbie",
            "prefix_id": "SOLD",
            "reply_count": 11,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/cAh",
            "sticky": 0,
            "tagsearch": "tes",
            "title": "a",
            "views": 84,
            "visible": 1,
            "sundul_enabled": 1,
            "thread_id": "546da14cc721e6ce59000014",
            "extra_attributes": [],
            "initial_prefix_id": "WTS",
            "thread_type": 21,
            "discounted_price": 19090909,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/02\/01\/avatar1183_45.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 1801,
            "enable_reputation": 1,
            "reputation": 21,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "dateline": 1416468590,
            "discount": 0,
            "first_post_id": "546d986ec721e68563000002",
            "forum_id": 197,
            "item_condition": 1,
            "item_location": 4,
            "item_price": 211111,
            "last_post": 1444376115,
            "last_post_id": "546d986ec721e68563000002",
            "last_post_userid": 1183,
            "last_poster": "newbie",
            "meta_images": [],
            "open": 1,
            "poll_id": 0,
            "post_userid": 1183,
            "post_username": "newbie",
            "prefix_id": "SOLD",
            "reply_count": 0,
            "resources": {
                "images": [
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2014\/11\/20\/1183_20141120022936.jpg",
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2014\/11\/20\/1183_20141120022941.jpg"
                ],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2014\/11\/20\/1183_20141120022936.jpg",
                "images_thumbnail": [
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2014\/11\/20\/1183_20141120022936.jpg",
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2014\/11\/20\/1183_20141120022941.jpg"
                ]
            },
            "short_url": "http:\/\/kask.us\/cAf",
            "sticky": 0,
            "tagsearch": "tes",
            "title": "Tes jualan hushky gan",
            "views": 19,
            "visible": 1,
            "sundul_enabled": 1,
            "thread_id": "546d986ec721e68563000001",
            "extra_attributes": [
                {
                    "attribute": "Warna",
                    "value": "Merah"
                }
            ],
            "initial_prefix_id": "WTS",
            "thread_type": 21,
            "discounted_price": 211111,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/02\/01\/avatar1183_45.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 1801,
            "enable_reputation": 1,
            "reputation": 21,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "forum_id": 449,
            "title": "Jual kaos bolong",
            "dateline": 1434601128,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 19,
            "post_username": "pintoco2",
            "post_userid": 2896639,
            "first_post_id": "558246a8f7cd2e6f0003d0d3",
            "last_poster": "pintoco2",
            "last_post_userid": 2896639,
            "last_post": 1442215126,
            "last_post_id": "558246a8f7cd2e6f0003d0d3",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "pakaian",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 15000,
            "item_location": 5,
            "discount": 10,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/dpa",
            "sundul_enabled": 1,
            "thread_id": "558246a8f7cd2e6f0003d0d2",
            "initial_prefix_id": "WTS",
            "extra_attributes": [
                {
                    "attribute": "Tes",
                    "value": "Tes"
                }
            ],
            "thread_type": 21,
            "discounted_price": 13500,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/04\/30\/avatar2896639_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 63,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 269,
            "title": "Foto Binatang Murah",
            "dateline": 1433918992,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 2,
            "post_username": "one",
            "post_userid": 1740,
            "first_post_id": "5577de10c721e6de288b456a",
            "last_poster": "one",
            "last_post_userid": 1740,
            "last_post": 1433918992,
            "last_post_id": "5577de10c721e6de288b456a",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "5d,",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 1500000,
            "item_location": 11,
            "discount": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQvn",
            "sundul_enabled": 1,
            "thread_id": "5577de10c721e6de288b4569",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 1485000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/02\/14\/male.jpg",
            "usertitle": "kaskus addict",
            "number_of_post": 1958,
            "enable_reputation": 1,
            "reputation": 1501,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": true,
            "reputation_box": 11
        }
    ],
    "thread_num": 13,
    "current_page": 1,
    "total_page": 2,
    "per_page": 10
}
```

# User



## GET user

Get certain user profile

### HTTP Request

`GET /user/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id
output|output format (JSON or XML)




> Example response

```json
{
    "userid": 11,
    "username": "recca",
    "lastlogin": 1450669417,
    "lastlogout": 1450669657,
    "usergroupid": "2",
    "firstname": "l",
    "lastname": "habul yamin",
    "gender": 1,
    "email": "11@yahoo.com",
    "address": "JL. SAKTI 1 NO : 7A",
    "country": "ID",
    "province": "Papua Barat",
    "ktpnumber": "3174103105840004",
    "phone": "+628113535333",
    "joindate": 1008849000,
    "dateofbirth": 1420131600,
    "profilevisits": 2983,
    "biography": "My life My rules",
    "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
    "usertitle": "kaskus addict",
    "number_of_post": 3295,
    "total_badge": 0,
    "enable_reputation": 1,
    "reputation": 1774,
    "reputation_title": "has a brilliant future",
    "is_donatur": false,
    "reputation_box": 11,
    "total_wtb": 792,
    "total_wts": 737,
    "friend": 0,
    "following": 0,
    "follower": 3,
    "country_name": "Indonesia",
    "vm_enable": 1
}
```

## POST user

Update currently logged in user profile

### HTTP Request

`POST /user`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## GET user

Get current user profile

### HTTP Request

`GET /user`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)
include|include extra field




> Example response

```json
{
    "userid": 11,
    "username": "recca",
    "lastlogin": 1450669417,
    "lastlogout": 1450669657,
    "usergroupid": "2",
    "firstname": "l",
    "lastname": "habul yamin",
    "gender": 1,
    "email": "11@yahoo.com",
    "address": "JL. SAKTI 1 NO : 7A",
    "country": "ID",
    "province": "Papua Barat",
    "ktpnumber": "3174103105840004",
    "phone": "+628113535333",
    "joindate": 1008849000,
    "dateofbirth": 1420131600,
    "profilevisits": 2983,
    "biography": "My life My rules",
    "is_friend": 0,
    "is_following": 0,
    "is_ignored": 0,
    "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
    "usertitle": "kaskus addict",
    "number_of_post": 3295,
    "total_badge": 0,
    "enable_reputation": 1,
    "reputation": 1774,
    "reputation_title": "has a brilliant future",
    "is_donatur": false,
    "reputation_box": 11,
    "total_wtb": 792,
    "total_wts": 737,
    "friend": 0,
    "following": 0,
    "follower": 3,
    "country_name": "Indonesia",
    "vm_enable": 1,
    "badges": []
}
```

## GET user/visitor

Get certain user's visitor list

### HTTP Request

`GET /user/visitor/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id
output|output format (JSON or XML)




> Example response

```json
[
    {
        "userid": "2610",
        "username": "turtle",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/04\/10\/avatar2610_1.gif",
        "usertitle": "newbie",
        "number_of_post": 0,
        "enable_reputation": 1,
        "reputation": 0,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "3",
        "username": "admin",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar3_1.gif",
        "usertitle": "Administrator",
        "number_of_post": 25045,
        "enable_reputation": 0,
        "reputation": 0,
        "reputation_title": "disabled reputation",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "15086",
        "username": "asd",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/04\/24\/avatar15086_7.gif",
        "usertitle": "kaskus holic",
        "number_of_post": 892,
        "enable_reputation": 1,
        "reputation": 2020,
        "reputation_title": "has a reputation beyond repute",
        "is_donatur": false,
        "reputation_box": 11
    },
    {
        "userid": "5915",
        "username": "kudaliar",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/07\/04\/avatar5915_2.gif",
        "usertitle": "newbie",
        "number_of_post": 21,
        "enable_reputation": 1,
        "reputation": 100,
        "reputation_title": "akan menjadi terkenal",
        "is_donatur": false,
        "reputation_box": 2
    },
    {
        "userid": "470613",
        "username": "dekampes",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2008\/06\/04\/male.jpg",
        "usertitle": "Administrator",
        "number_of_post": 126,
        "enable_reputation": 0,
        "reputation": 0,
        "reputation_title": "disabled reputation",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "2283291",
        "username": "buriza12",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2010\/11\/19\/avatar2283291_2.gif",
        "usertitle": "Administrator",
        "number_of_post": 22,
        "enable_reputation": 0,
        "reputation": 0,
        "reputation_title": "disabled reputation",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "1415",
        "username": "budi",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/02\/05\/avatar1415_4.gif",
        "usertitle": "kaskuser",
        "number_of_post": 113,
        "enable_reputation": 1,
        "reputation": 12,
        "reputation_title": "sedang di jalan yg benar",
        "is_donatur": false,
        "reputation_box": 1
    },
    {
        "userid": "2562",
        "username": "andi",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/04\/12\/avatar2562_1.gif",
        "usertitle": "kaskus addict",
        "number_of_post": 2001,
        "enable_reputation": 1,
        "reputation": 3,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 1
    },
    {
        "userid": "1",
        "username": "vadmin",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/12\/29\/avatar1_1.gif",
        "usertitle": "Guest",
        "number_of_post": 20,
        "enable_reputation": 1,
        "reputation": 11,
        "reputation_title": "sedang di jalan yg benar",
        "is_donatur": false,
        "reputation_box": 1
    },
    {
        "userid": "806013",
        "username": "qb_marukochan",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/04\/18\/avatar806013_7.gif",
        "usertitle": "Kaskus Donator",
        "number_of_post": 7665,
        "enable_reputation": 1,
        "reputation": 1990,
        "reputation_title": "has a brilliant future",
        "is_donatur": true,
        "reputation_box": 11
    }
]
```

## GET user/badges

Get certain user's badges list

### HTTP Request

`GET /user/badges/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id
output|output format (JSON or XML)




> Example response

```json
{
    "username": "recca",
    "userid": "11",
    "badges": []
}
```

## GET user/privacy_setting

Get currently logged in user's privacy setting. Response will be key-value map.               With value (1) means shareable to public, otherwise is (0).

### HTTP Request

`GET /user/privacy_setting`

Parameter | Description
--------- | -----------
setting|Filter by certain setting
output|output format (JSON or XML)




> Example response

```json
{
    "settings": [
        {
            "name": "phone",
            "value": 0
        }
    ]
}
```

## POST user/privacy_setting

Update privacy settings.

### HTTP Request

`POST /user/privacy_setting`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



# Versions



## GET versions

Get application version.

### HTTP Request

`GET /v1/versions`

Parameter | Description
--------- | -----------
platform|Your application platform (android or ios)
application|Application id
version|Your current application version (x.y.z)



# Categories



## GET categories

Get all categories for FJB.

### HTTP Request

`GET /v1/categories`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
[
    {
        "forum_id": "151",
        "name": "Gratisan",
        "description": "Aneka promo gratis",
        "display_order": "11",
        "parent_id": "25",
        "parent_list": "151,25,-1",
        "child_list": "151,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "195",
        "name": "Elektronik",
        "description": "Jual beli beragam jenis barang elektronik",
        "display_order": "7",
        "parent_id": "25",
        "parent_list": "195,25,-1",
        "child_list": "195,313,255,254,212,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "196",
        "name": "Fashion & Mode",
        "description": "Jual beli barang fashion untuk pria dan wanita",
        "display_order": "8",
        "parent_id": "25",
        "parent_list": "196,25,-1",
        "child_list": "196,216,451,450,302,449,624,600,215,257,310,311,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "197",
        "name": "Flora & Fauna",
        "description": "Jual beli tanaman hias dan hewan peliharaan (kecuali yang dilindungi)",
        "display_order": "9",
        "parent_id": "25",
        "parent_list": "197,25,-1",
        "child_list": "197,218,219,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "198",
        "name": "Koleksi, Hobi & Mainan",
        "description": "Jual beli barang koleksi, hobi dan mainan",
        "display_order": "18",
        "parent_id": "25",
        "parent_list": "198,25,-1",
        "child_list": "198,261,231,262,444,606,233,291,590,292,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "199",
        "name": "Properti",
        "description": "Jual beli properti",
        "display_order": "29",
        "parent_id": "25",
        "parent_list": "199,25,-1",
        "child_list": "199,223,225,222,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "200",
        "name": "CD & DVD",
        "description": "Jual beli CD\/DVD",
        "display_order": "6",
        "parent_id": "25",
        "parent_list": "200,25,-1",
        "child_list": "200,266,265,329,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "201",
        "name": "Makanan & Minuman",
        "description": "Jual beli aneka makanan dan minuman (HARUS halal)",
        "display_order": "20",
        "parent_id": "25",
        "parent_list": "201,25,-1",
        "child_list": "201,228,607,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "202",
        "name": "Jasa",
        "description": "Penawaran aneka jasa",
        "display_order": "14",
        "parent_id": "25",
        "parent_list": "202,25,-1",
        "child_list": "202,269,268,553,631,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "205",
        "name": "Otomotif",
        "description": "Jual beli mobil\/motor, aksesoris dan suku cadang",
        "display_order": "23",
        "parent_id": "25",
        "parent_list": "205,25,-1",
        "child_list": "205,333,334,206,207,208,256,209,593,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "210",
        "name": "Handphone & Tablet updated",
        "description": "Jual beli Handphone dan PDA",
        "display_order": "12",
        "parent_id": "25",
        "parent_list": "210,25,-1",
        "child_list": "210,527,574,381,573,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "220",
        "name": "Alat-Alat Olahraga",
        "description": "Jual beli pakaian, sepatu dan perlengkapan olahraga",
        "display_order": "2",
        "parent_id": "25",
        "parent_list": "220,25,-1",
        "child_list": "220,589,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "221",
        "name": "Alat-Alat Musik",
        "description": "Jual beli alat musik dan perlengkapan studio",
        "display_order": "1",
        "parent_id": "25",
        "parent_list": "221,25,-1",
        "child_list": "221,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "227",
        "name": "Buku",
        "description": "Jual beli beragam jenis buku",
        "display_order": "5",
        "parent_id": "25",
        "parent_list": "227,25,-1",
        "child_list": "227,264,625,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "229",
        "name": "Obat-obatan",
        "description": "Jual beli segala jenis obat-obatan (HARUS aman dikonsumsi konsumen)",
        "display_order": "21",
        "parent_id": "25",
        "parent_list": "229,25,-1",
        "child_list": "229,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "273",
        "name": "Product Review",
        "description": "Ulasan seputar produk",
        "display_order": "34",
        "parent_id": "25",
        "parent_list": "273,25,-1",
        "child_list": "273,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "283",
        "name": "Antik",
        "description": "Jual beli benda menarik, kuno dan unik",
        "display_order": "3",
        "parent_id": "25",
        "parent_list": "283,25,-1",
        "child_list": "283,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "284",
        "name": "Karya Seni & Desain",
        "description": "Jual beli barang seni dan penawaran jasa desain",
        "display_order": "15",
        "parent_id": "25",
        "parent_list": "284,25,-1",
        "child_list": "284,603,285,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "286",
        "name": "Industri & Supplier",
        "description": "Jual beli barang & bahan baku industri",
        "display_order": "13",
        "parent_id": "25",
        "parent_list": "286,25,-1",
        "child_list": "286,287,448,288,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "293",
        "name": "Kamera & Aksesoris",
        "description": "Jual beli kamera dan aksesoris",
        "display_order": "16",
        "parent_id": "25",
        "parent_list": "293,25,-1",
        "child_list": "293,604,605,294,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "295",
        "name": "Perawatan Tubuh & Wajah",
        "description": "Jual beli aneka produk kesehatan dan kecantikan",
        "display_order": "24",
        "parent_id": "25",
        "parent_list": "295,25,-1",
        "child_list": "295,608,609,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "296",
        "name": "Furniture",
        "description": "Jual beli mebel (kursi, meja, lemari dsb)",
        "display_order": "10",
        "parent_id": "25",
        "parent_list": "296,25,-1",
        "child_list": "296,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "297",
        "name": "Video Games",
        "description": "Jual beli games dan konsol",
        "display_order": "33",
        "parent_id": "25",
        "parent_list": "297,25,-1",
        "child_list": "297,612,613,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "298",
        "name": "Perkakas",
        "description": "Jual beli aneka perkakas",
        "display_order": "25",
        "parent_id": "25",
        "parent_list": "298,25,-1",
        "child_list": "298,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "299",
        "name": "Kerajinan Tangan",
        "description": "Jual beli aneka kerajinan tangan",
        "display_order": "17",
        "parent_id": "25",
        "parent_list": "299,25,-1",
        "child_list": "299,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "300",
        "name": "Perlengkapan Kantor",
        "description": "Jual beli perlengkapan kantor",
        "display_order": "27",
        "parent_id": "25",
        "parent_list": "300,25,-1",
        "child_list": "300,312,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "303",
        "name": "Perlengkapan Rumah Tangga",
        "description": "Jual beli perlengkapan rumah tangga (sub kategori terkait, cek elektronik rumah tangga)",
        "display_order": "28",
        "parent_id": "25",
        "parent_list": "303,25,-1",
        "child_list": "303,314,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "304",
        "name": "Tur & Paket Perjalanan",
        "description": "Penawaran aneka tur dan paket wisata",
        "display_order": "32",
        "parent_id": "25",
        "parent_list": "304,25,-1",
        "child_list": "304,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "305",
        "name": "Perlengkapan Anak & Bayi",
        "description": "Jual beli pakaian, perlengkapan bayi dan anak-anak",
        "display_order": "26",
        "parent_id": "25",
        "parent_list": "305,25,-1",
        "child_list": "305,447,446,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "316",
        "name": "Tiket",
        "description": "Jual beli tiket",
        "display_order": "31",
        "parent_id": "25",
        "parent_list": "316,25,-1",
        "child_list": "316,610,611,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "317",
        "name": "Komputer",
        "description": "Jual beli komputer (hardware, software)",
        "display_order": "19",
        "parent_id": "25",
        "parent_list": "317,25,-1",
        "child_list": "317,330,328,318,323,327,321,324,325,319,326,320,322,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "588",
        "name": "Online Gaming",
        "description": "",
        "display_order": "22",
        "parent_id": "25",
        "parent_list": "588,25,-1",
        "child_list": "588,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "614",
        "name": "Serba Serbi",
        "description": "Jual beli aneka produk diluar kategori \/sub kategori",
        "display_order": "30",
        "parent_id": "25",
        "parent_list": "614,25,-1",
        "child_list": "614,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "615",
        "name": "Bisnis",
        "description": "Penawaran bisnis",
        "display_order": "4",
        "parent_id": "25",
        "parent_list": "615,25,-1",
        "child_list": "615,616,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    }
]
```

# Fjb



## GET fjb/threads

Get Thread List (FJB) of Selected Forum

### HTTP Request

`GET /v1/fjb/{id}/threads`

Parameter | Description
--------- | -----------
id|forum id
output|output format (JSON or XML)
page|number of post page
limit|limit number of post per page
sort|Sorting method (lastpost,thread,postusername,views,replycount,rating,price).
order|Ordering method (asc, desc)




> Example response

```json
{
    "forum": {
        "forum_id": "221",
        "name": "Alat-Alat Musik",
        "description": "Jual beli alat musik dan perlengkapan studio",
        "thread_count": "114813",
        "post_count": "5339440",
        "visible": "1",
        "last_thread_id": "556c09bcc721e62f628b4567",
        "last_thread_title": "gyoza suara",
        "last_thread_starter": "penjual",
        "last_post_id": "567128b18ead0e5831cec3ad",
        "last_post": "1450256561",
        "last_poster": "pembeli",
        "service": "classified",
        "forum_icon": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    "subforum": [],
    "top_thread": [],
    "top_feature": [],
    "thread": [
        {
            "dateline": 1234004691,
            "first_post_id": "000000000000000066899479",
            "forum_id": 221,
            "item_condition": 1,
            "item_price": 1,
            "last_post": 1422848448,
            "last_post_id": "54cef1c08ead0e893c0041c8",
            "last_post_userid": 11,
            "last_poster": "recca",
            "open": 1,
            "poll_id": 0,
            "post_userid": 542704,
            "post_username": "sevenstring",
            "prefix_id": "",
            "reply_count": 1872,
            "short_url": "http:\/\/kask.us\/gVRIN",
            "sticky": 1,
            "tagsearch": "",
            "title": "Daftar Penjual Terpercaya",
            "views": 217542,
            "visible": 1,
            "vote_num": 98,
            "vote_total": 321,
            "sundul_enabled": 1,
            "thread_id": "000000000000000001416590",
            "thread_type": 20,
            "item_location": 0,
            "discount": 0,
            "discounted_price": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "extra_attributes": [],
            "initial_prefix_id": "",
            "meta_images": [],
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2008\/09\/08\/avatar542704_3.gif",
            "usertitle": "kaskus geek",
            "number_of_post": 14544,
            "enable_reputation": 1,
            "reputation": 526,
            "reputation_title": "is a glorious beacon of light",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 6
        },
        {
            "dateline": 1259733312,
            "first_post_id": "000000000000000138740363",
            "forum_id": 221,
            "last_post": 1394513959,
            "last_post_id": "531e98271bcb1706788b466a",
            "last_post_userid": 4206715,
            "last_poster": "homiesound",
            "open": 1,
            "poll_id": 0,
            "post_userid": 802441,
            "post_username": "patrick_t",
            "prefix_id": "",
            "reply_count": 693,
            "short_url": "http:\/\/kask.us\/gVTQa",
            "sticky": 1,
            "title": "List Daftar  Studio2 Rekaman\/Mixing\/Mastering di Kaskus",
            "views": 96165,
            "visible": 1,
            "vote_num": 25,
            "vote_total": 108,
            "sundul_enabled": 1,
            "thread_id": "000000000000000002858574",
            "thread_type": 20,
            "item_price": 0,
            "item_location": 0,
            "item_condition": 0,
            "discount": 0,
            "tagsearch": "",
            "discounted_price": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "extra_attributes": [],
            "initial_prefix_id": "",
            "meta_images": [],
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/04\/17\/male.jpg",
            "usertitle": "kaskus addict",
            "number_of_post": 1533,
            "enable_reputation": 1,
            "reputation": 13,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "dateline": 1258619496,
            "first_post_id": "000000000000000134546742",
            "forum_id": 221,
            "last_post": 1393740134,
            "last_post_id": "5312c966becb17fc3d8b456d",
            "last_post_userid": 6445515,
            "last_poster": "angelsgh",
            "open": 1,
            "poll_id": 0,
            "post_userid": 791389,
            "post_username": "oollie16",
            "prefix_id": "",
            "reply_count": 526,
            "short_url": "http:\/\/kask.us\/gVYSx",
            "sticky": 1,
            "title": "Jenis Modus Penipuan Di FJB Musical Instrument",
            "views": 82633,
            "visible": 1,
            "vote_num": 28,
            "vote_total": 101,
            "sundul_enabled": 1,
            "thread_id": "000000000000000002783708",
            "thread_type": 20,
            "item_price": 0,
            "item_location": 0,
            "item_condition": 0,
            "discount": 0,
            "tagsearch": "",
            "discounted_price": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "extra_attributes": [],
            "initial_prefix_id": "",
            "meta_images": [],
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/04\/13\/avatar791389_3.gif",
            "usertitle": "kaskus maniac",
            "number_of_post": 4078,
            "enable_reputation": 1,
            "reputation": 7,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "dateline": 1232805233,
            "first_post_id": "000000000000000064848939",
            "forum_id": 221,
            "item_condition": 1,
            "item_price": 12345,
            "last_post": 1393642284,
            "last_post_id": "53114b2c5bcb17897600002d",
            "last_post_userid": 5204272,
            "last_poster": "rumahgitar",
            "open": 1,
            "poll_id": 0,
            "post_userid": 540550,
            "post_username": "sikacamata",
            "prefix_id": "",
            "reply_count": 908,
            "short_url": "http:\/\/kask.us\/gWkk1",
            "sticky": 1,
            "tagsearch": "",
            "title": "-The Blacklist People In FJB Musik-",
            "views": 127696,
            "visible": 1,
            "vote_num": 31,
            "vote_total": 146,
            "sundul_enabled": 1,
            "thread_id": "000000000000000001381729",
            "thread_type": 20,
            "item_location": 0,
            "discount": 0,
            "discounted_price": 12345,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "extra_attributes": [],
            "initial_prefix_id": "",
            "meta_images": [],
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2008\/09\/04\/avatar540550_1.gif",
            "usertitle": "Auto Banned",
            "number_of_post": 8971,
            "enable_reputation": 1,
            "reputation": 81,
            "reputation_title": "akan menjadi terkenal",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "kaskus99@yahoo.comkaskus99@yahoo.com",
            "dateline": 1449048099,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 2,
            "post_username": "bobi",
            "post_userid": 27575,
            "first_post_id": "565eb823c721e61a708b4568",
            "last_poster": "bobi",
            "last_post_userid": 27575,
            "last_post": 1449048099,
            "last_post_id": "565eb823c721e61a708b4568",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "test",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 234213,
            "item_location": 5,
            "discount": 23,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQI8",
            "sundul_enabled": 1,
            "thread_id": "565eb823c721e61a708b4567",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 180344,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2004\/02\/05\/avatar27575_3.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3873,
            "enable_reputation": 1,
            "reputation": 1229,
            "reputation_title": " has much to be proud of",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 9
        },
        {
            "forum_id": 221,
            "title": "gad sg sfh dsfgt rhfd hte hdf gd gdsg serdg ",
            "dateline": 1449047407,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "bobi",
            "post_userid": 27575,
            "first_post_id": "565eb56fc721e665308b4573",
            "last_poster": "bobi",
            "last_post_userid": 27575,
            "last_post": 1449047407,
            "last_post_id": "565eb56fc721e665308b4573",
            "sticky": 0,
            "prefix_id": "WTB",
            "tagsearch": "test",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 100000,
            "item_location": 3,
            "discount": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQI4",
            "sundul_enabled": 1,
            "thread_id": "565eb56fc721e665308b4572",
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 100000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2004\/02\/05\/avatar27575_3.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3873,
            "enable_reputation": 1,
            "reputation": 1229,
            "reputation_title": " has much to be proud of",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 9
        },
        {
            "forum_id": 221,
            "title": "test ya gan hehehe",
            "dateline": 1449047275,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 1,
            "views": 3,
            "post_username": "bobi",
            "post_userid": 27575,
            "first_post_id": "565eb4ebc721e60c308b4574",
            "last_poster": "bobi",
            "last_post_userid": 27575,
            "last_post": 1449047275,
            "last_post_id": "565eb51ec721e67e078b4575",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "test",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 100000,
            "item_location": 8,
            "discount": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQI2",
            "sundul_enabled": 1,
            "thread_id": "565eb4ebc721e60c308b4573",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 100000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2004\/02\/05\/avatar27575_3.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3873,
            "enable_reputation": 1,
            "reputation": 1229,
            "reputation_title": " has much to be proud of",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 9
        },
        {
            "forum_id": 221,
            "title": "test registered seller ",
            "dateline": 1445506684,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 14,
            "post_username": "entahsiapa",
            "post_userid": 1890013,
            "first_post_id": "5628ae7cc721e6b3228b456b",
            "last_poster": "entahsiapa",
            "last_post_userid": 1890013,
            "last_post": 1445506684,
            "last_post_id": "5628ae7cc721e6b3228b456b",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "gg",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 123123,
            "item_location": 3,
            "discount": 12,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQC4",
            "sundul_enabled": 1,
            "thread_id": "5628ae7cc721e6b3228b456a",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 108348,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2010\/07\/19\/avatar1890013_1.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 130,
            "enable_reputation": 1,
            "reputation": 4,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "bypass duplicator 1",
            "dateline": 1444293420,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 11,
            "post_username": "penjual",
            "post_userid": 273525,
            "first_post_id": "56162b2cc721e6c71d8b4575",
            "last_poster": "penjual",
            "last_post_userid": 273525,
            "last_post": 1445000886,
            "last_post_id": "56162b2cc721e6c71d8b4575",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "bypass duplicator 1",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 230000000,
            "item_location": 5,
            "discount": 20,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQA8",
            "sundul_enabled": 1,
            "thread_id": "56162b2cc721e6c71d8b4574",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 184000000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/avatar273525_1.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 78,
            "enable_reputation": 1,
            "reputation": 4,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": true,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "bypass duplicator 1",
            "dateline": 1444293380,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 9,
            "post_username": "penjual",
            "post_userid": 273525,
            "first_post_id": "56162b04c721e692408b4569",
            "last_poster": "penjual",
            "last_post_userid": 273525,
            "last_post": 1444636259,
            "last_post_id": "56162b04c721e692408b4569",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "bypass duplicator 1",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 230000000,
            "item_location": 5,
            "discount": 20,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQA6",
            "sundul_enabled": 1,
            "thread_id": "56162b04c721e692408b4568",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 184000000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/avatar273525_1.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 78,
            "enable_reputation": 1,
            "reputation": 4,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": true,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "groqwjf emfiowq fmewoi fmweo fikew",
            "dateline": 1444293625,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 5,
            "post_username": "kuda",
            "post_userid": 11626,
            "first_post_id": "56162bf9c721e6de658b4571",
            "last_poster": "kuda",
            "last_post_userid": 11626,
            "last_post": 1444293625,
            "last_post_id": "56162bf9c721e6de658b4571",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "bypass duplicator 1",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 1231298,
            "item_location": 5,
            "discount": 20,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQBc",
            "sundul_enabled": 1,
            "thread_id": "56162bf9c721e6de658b4570",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 985038,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/02\/06\/avatar11626_1.gif",
            "usertitle": "newbie",
            "number_of_post": 0,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 221,
            "title": "bypass duplicator 1",
            "dateline": 1444293472,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "kuda",
            "post_userid": 11626,
            "first_post_id": "56162b60c721e6ce128b4599",
            "last_poster": "kuda",
            "last_post_userid": 11626,
            "last_post": 1444293472,
            "last_post_id": "56162b60c721e6ce128b4599",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "bypass duplicator 1",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 230000000,
            "item_location": 5,
            "discount": 20,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQBa",
            "sundul_enabled": 1,
            "thread_id": "56162b60c721e6ce128b4598",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 184000000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/02\/06\/avatar11626_1.gif",
            "usertitle": "newbie",
            "number_of_post": 0,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 221,
            "title": "bypass duplicator 1",
            "dateline": 1444293335,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "penjual",
            "post_userid": 273525,
            "first_post_id": "56162ad7c721e6de658b456f",
            "last_poster": "penjual",
            "last_post_userid": 273525,
            "last_post": 1444293335,
            "last_post_id": "56162ad7c721e6de658b456f",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "bypass duplicator 1",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 230000000,
            "item_location": 4,
            "discount": 20,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQA4",
            "sundul_enabled": 1,
            "thread_id": "56162ad7c721e6de658b456e",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 184000000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/avatar273525_1.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 78,
            "enable_reputation": 1,
            "reputation": 4,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": true,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "bypass duplicator 1",
            "dateline": 1444292753,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 0,
            "post_username": "penjual",
            "post_userid": 273525,
            "first_post_id": "561628914d8a4f3e200041b0",
            "last_poster": "penjual",
            "last_post_userid": 273525,
            "last_post": 1444292753,
            "last_post_id": "561628914d8a4f3e200041b0",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "bypass duplicator 1",
            "meta_images": [],
            "item_condition": 4,
            "item_price": 230000000,
            "item_location": 2,
            "discount": 20,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQA2",
            "sundul_enabled": 1,
            "thread_id": "561628914d8a4f3e200041af",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 184000000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/avatar273525_1.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 78,
            "enable_reputation": 1,
            "reputation": 4,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": true,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "Tes Jual Barang",
            "dateline": 1444285996,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 2,
            "post_username": "pembeli",
            "post_userid": 222745,
            "first_post_id": "56160e2ce2ec60b9058b4568",
            "last_poster": "pembeli",
            "last_post_userid": 222745,
            "last_post": 1444285996,
            "last_post_id": "56160e2ce2ec60b9058b4568",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "alat musik tes",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 123000,
            "item_location": 11,
            "discount": 23,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQAI",
            "sundul_enabled": 1,
            "thread_id": "56160e2ce2ec60b9058b4567",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 94710,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2006\/11\/21\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 6,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 221,
            "title": "Jualan gitar maha sati (TEST FEEDBACK)",
            "dateline": 1439258418,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 14,
            "post_username": "penjual",
            "post_userid": 273525,
            "first_post_id": "55c95732c721e6fc478b4568",
            "last_poster": "penjual",
            "last_post_userid": 273525,
            "last_post": 1442238896,
            "last_post_id": "55c95732c721e6fc478b4568",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "tes, feedback, gitar, musik",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 150000,
            "item_location": 12,
            "discount": 0,
            "resources": {
                "images": [
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2015\/08\/13\/_Menu_Zenbu2014_rev03_Page_09_1439448192.jpg",
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2015\/08\/13\/_Menu_Zenbu2014_rev03_Page_09_1439448243.jpg"
                ],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2015\/08\/13\/_Menu_Zenbu2014_rev03_Page_09_1439448192.jpg",
                "images_thumbnail": [
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2015\/08\/13\/_Menu_Zenbu2014_rev03_Page_09_1439448192.jpg",
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2015\/08\/13\/_Menu_Zenbu2014_rev03_Page_09_1439448243.jpg"
                ]
            },
            "short_url": "http:\/\/kask.us\/hxQyt",
            "sundul_enabled": 1,
            "thread_id": "55c95732c721e6fc478b4567",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 150000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/avatar273525_1.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 78,
            "enable_reputation": 1,
            "reputation": 4,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": true,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "Jual gitar tanpa senar",
            "dateline": 1434601303,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 3,
            "views": 14,
            "post_username": "pintoco2",
            "post_userid": 2896639,
            "first_post_id": "55824757f7cd2e6f0003d0d5",
            "last_poster": "pintoco2",
            "last_post_userid": 2896639,
            "last_post": 1442227409,
            "last_post_id": "55825a66f7cd2e6f0003d0d8",
            "sticky": 0,
            "prefix_id": "SOLD",
            "tagsearch": "gadget",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 90000,
            "item_location": 1,
            "discount": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/dpb",
            "sundul_enabled": 1,
            "thread_id": "55824757f7cd2e6f0003d0d4",
            "initial_prefix_id": "WTB",
            "extra_attributes": [
                {
                    "attribute": "Abu",
                    "value": "Warna"
                }
            ],
            "thread_type": 21,
            "discounted_price": 90000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/04\/30\/avatar2896639_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 63,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 221,
            "title": "gyoza bersuara",
            "dateline": 1441969647,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 1,
            "views": 54,
            "post_username": "penjual",
            "post_userid": 273525,
            "first_post_id": "55f2b5efc721e6ca328b4568",
            "last_poster": "bobi",
            "last_post_userid": 27575,
            "last_post": 1441969647,
            "last_post_id": "5658365ac721e6080b8b4584",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "gg",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 1000000,
            "item_location": 11,
            "discount": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQAs",
            "sundul_enabled": 1,
            "thread_id": "55f2b5efc721e6ca328b4567",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 990000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/avatar273525_1.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 78,
            "enable_reputation": 1,
            "reputation": 4,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": true,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "Coba masukin aja",
            "dateline": 1437624484,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 4,
            "post_username": "Lientz",
            "post_userid": 2629271,
            "first_post_id": "55b068a4c721e6555c8b4568",
            "last_poster": "Lientz",
            "last_post_userid": 2629271,
            "last_post": 1437624484,
            "last_post_id": "55b068a4c721e6555c8b4568",
            "sticky": 0,
            "prefix_id": "WTB",
            "tagsearch": "Gondrong",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 500000,
            "item_location": 11,
            "discount": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQyd",
            "sundul_enabled": 1,
            "thread_id": "55b068a4c721e6555c8b4567",
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 500000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/02\/24\/avatar2629271_1.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 2134,
            "enable_reputation": 1,
            "reputation": 11,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "Gitar bapak Ane yang pernah dibanting",
            "dateline": 1434094301,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "one",
            "post_userid": 1740,
            "first_post_id": "557a8addc721e6d3488b456a",
            "last_poster": "one",
            "last_post_userid": 1740,
            "last_post": 1434094301,
            "last_post_id": "557a8addc721e6d3488b456a",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "gitar",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 100000,
            "item_location": 1,
            "discount": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQvD",
            "sundul_enabled": 1,
            "thread_id": "557a8addc721e6d3488b4569",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 100000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/02\/14\/male.jpg",
            "usertitle": "kaskus addict",
            "number_of_post": 1958,
            "enable_reputation": 1,
            "reputation": 1501,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": true,
            "reputation_box": 11
        }
    ],
    "thread_num": 20000,
    "current_page": 1,
    "total_page": 1000,
    "per_page": 20
}
```

## GET fjb/lapaks

Get Thread List (Lapak) of Selected Forum

### HTTP Request

`GET /v1/fjb/{id}/lapaks`

Parameter | Description
--------- | -----------
id|forum id
output|output format (JSON or XML)
page|number of post page
limit|limit number of post per page
sort|Sorting method (lastpost,thread).
order|Ordering method (asc, desc)
cursor|thread id to get thread after it. Use cursor = 0 to start from beginning



# Fjb_image



## POST fjb_image

Upload image for Lapak or FJB

### HTTP Request

`POST /v1/fjb_image`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



# Fjb_post



## GET fjb_post

Get fjb post details

### HTTP Request

`GET /v1/fjb_post/{id}`

Parameter | Description
--------- | -----------
id|Post Id that we want to get the detail
output|output format (JSON or XML)
field|post field that need to be filtered



## POST fjb_post

Create new FJB post

### HTTP Request

`POST /v1/fjb_post`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## POST fjb_post

Edit FJB post

### HTTP Request

`POST /v1/fjb_post/{id}/edit`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



# Fjb_thread



## GET fjb_thread

Read fjb thread based on id. Thread rating can be calculated from vote_total and vote_num.           Rating = vote_total / vote_num.

### HTTP Request

`GET /v1/fjb_thread/{id}`

Parameter | Description
--------- | -----------
id|thread id
output|output format (JSON or XML)
page|number of post page
limit|limit number of post per page
field|post field that need to be filtered
include|add similar thread
post|get thread by post id



## GET fjb_thread

Read fjb thread based on id. Thread rating can be calculated from vote_total and vote_num.           Rating = vote_total / vote_num.

### HTTP Request

`GET /v1/fjb_thread/{id}`

Parameter | Description
--------- | -----------
id|thread id
output|output format (JSON or XML)
page|number of post page
limit|limit number of post per page
field|post field that need to be filtered
include|add similar thread
post|get thread by post id



## POST fjb_thread

Sundul fjb thread

### HTTP Request

`POST /v1/fjb_thread/{id}/sundul`

Parameter | Description
--------- | -----------
id|thread id



# Forum_post



## GET forum_post

Get forum post details

### HTTP Request

`GET /v1/forum_post/{id}`

Parameter | Description
--------- | -----------
id|Post Id that we want to get the detail
output|output format (JSON or XML)
field|post field that need to be filtered



## POST forum_post

Create new forum post

### HTTP Request

`POST /v1/forum_post`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## POST forum_post

Edit forum post

### HTTP Request

`POST /v1/forum_post/{id}/edit`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



# Forum_thread



## GET forum_thread

Read forum thread based on id

### HTTP Request

`GET /v1/forum_thread/{id}`

Parameter | Description
--------- | -----------
id|thread id
output|output format (JSON or XML)
page|number of post page
limit|limit number of post per page
field|post field that need to be filtered




> Example response

```json
{
    "thread": {
        "dateline": 1393843523,
        "first_post_id": "53145d43a1cb17ab258b4577",
        "forum_id": 21,
        "last_post": 1429610414,
        "last_post_id": "55361fae8ead0e93000041a7",
        "last_post_userid": 916848,
        "last_poster": "beta tester",
        "open": 0,
        "poll_id": 0,
        "post_userid": 4440622,
        "post_username": "KASKUS.Update",
        "prefix_id": "",
        "reply_count": 613,
        "short_url": "http:\/\/kask.us\/hxNDr",
        "sticky": 0,
        "title": "[Live Ngaskus] Ngomongin Cinta Bareng Para Pemeran Film Aku Cinta Kamu",
        "views": 34912,
        "visible": 1,
        "vote_num": 18,
        "vote_total": 67,
        "is_protected": false,
        "thread_id": "53145d43a1cb17ab258b4576",
        "hot_thread": 1,
        "thread_type": 10,
        "initial_prefix_id": "",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2012\/06\/12\/avatar4440622_4.gif",
        "usertitle": "Kaskus Official",
        "number_of_post": "307",
        "total_badge": 0,
        "enable_reputation": 1,
        "reputation": "53",
        "reputation_title": "akan menjadi terkenal",
        "is_donatur": false,
        "is_vsl": false,
        "reputation_box": 1
    },
    "total_post": 614,
    "current_page": 1,
    "total_page": 31,
    "per_page": 20,
    "posts": [
        {
            "pagetext": "[CENTER][FONT=\"Georgia\"][size=\"5\"][size=\"7\"][color=blue]Heellloooww Gan & Siiiss![\/color][\/size]\n:shakehand2 \n\n[QUOTE][CENTER][size=\"5\"][FONT=\"Georgia\"][size=\"7\"][color=red][B]UPDATE[\/B][\/color][\/size]\n:hn :hn :hn\n\nDan inilah para penanya terbaik Live Ngaskus bareng Piyu, Rio Dewanto dan Eriska Rein. \n\n[B]1. wqew\n\n2. R8486.Jr\n\n3. Dofar26\n\n4. cicimol\n\n5. defend\n\n6. dellahurahura\n\n7. GIML\n\n8. kemanajabole\n\n9. maulanfazry\n\n10. free1412[\/B]\n\n[color=orange][size=\"6\"]Selamat kepada pemenang![\/size][\/color]\n:selamat :selamat :selamat\n\nSeluruh pemenang berhak mendapatkan masing-masing 2 tiket film Aku Cinta Kamu yang bisa ditonton di seluruh bioskop 21. \n[B][color=red]Tiket bisa diambil di kantor KASKUS mulai hari Rabu, 12 Maret 2014 sampai Jumat, 14 Maret 2014 pukul 10.00 -18.00[\/color][\/B]\n[\/FONT][\/size][\/CENTER]\n\n[\/QUOTE]\n\n\n\n[QUOTE][CENTER][size=\"5\"][B]UPDATE[\/B]\n:hn :hn :hn\n\nLive Ngaskus lagi berlangsung nih Gan! Ayo tanya-tanya tentang film [B][color=red]Aku Cinta Kamu [\/color][\/B]ke Piyu, Rio Dewanto, dan Eriska Rein! Pertanyaan terbaik bakal dapet hadiah loh!\n:2thumbup\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305025508.jpg[\/img]\n[I]Asli, IGO ini bening banget Gan! [\/I]\n:matabelo\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305025514.jpg[\/img]\n[I]Piyu senyum-senyum nih liat komentar para Kaskuser[\/I]\n:ngakak\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305025521.jpg[\/img]\n[I]Kalau Rio serius nih jawab-in pertanyaan Agan-Agan[\/I]\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305025500.jpg[\/img]\n[I]Say Cheeseee[\/I][\/size][\/CENTER]\n[\/QUOTE]\n\n\n\nHooorrrreee!! Ketemu lagi di acaranya [color=blue]KAS[\/color][color=orange]KUS[\/color] yang paling interaktif, apalagi kalau bukan[color=red][size=\"7\"]Live Ngaskus[\/size][\/color]\n:selamat :selamat\n\n\nYayyyy!! Bulan Maret ini kita bakal kedatangan para pemeran film \n[size=\"7\"][color=magenta]Aku Cinta Kamu[\/color][\/size]\n:heart: :heart: :heart: :heart:\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/03\/4440622_20140303053824.jpg[\/img]\n\n[YOUTUBE]qtdmRlPPGfE[\/YOUTUBE]\n\n\nKetika cinta menyengat, berjuta rasa menjangkiti hati dan pikiran kita. Berbagai peristiwa besar dalam kehidupan, dipicu oleh satu kalimat singkat : [B]Aku Cinta Kamu[\/B]. Nah, berangkat dari 4 lagu cinta ciptaan seorang Piyu, dibuatlah 4 kisah dengan 4 genre menjadi sebuah film untuk mengenal cinta. Pokonya, it\u2019s all about love :heart: :heart: :heart:\n\n[SPOILER=Sinopsis Cerita 1 - Firasatku]Tentang Sita (Acha Septriasa) dan Randu (Rio Dewanto) yang mempersiapkan sebuah pesta pernikahan. Sita sebagai wedding organizer sangat perfectionist, dan menginginkan pernikahan paling sempurna. Sedangkan Randu, fotografer berjiwa seniman seakan cuek dengan persiapan Sita. Randu punya beribu alasan untuk menangguhkan foto prewed mereka. Hingga Sita mulai dipengaruhi firasatnya sendiri, kalau Randu berselingkuh dengan wanita lain bernama Rani (Fanny Fabriana). Hingga akhirnya Sita memergoki mereka. Sita dilema, apakah membatalkan pernikahannya atau mencoba ikhlas dan berfikir positif, mungkin Randu ingin menyelesaikan sejarah percintaannya dengan Rani sebelum memulai hidup bersamanya. \nHari pernikahan tiba, Sita dengan gaun cantik pernikahannya tidak bisa membendung air matanya. Dia lari dan Randu mengejarnya, hingga kecelakaan merenggut nyawa salah satu dari mereka, dan membuka mata bahwa firasat tidak selalu benar. \n[\/SPOILER]\n\n[SPOILER=Sinopsis Cerita 2 - Cinta Itu Adalah]Kim (Kim Kurniawan) seorang pemain bola yang sedang naik daun, bertetangga dengan Raisha (Eriska Rein) yang begitu terobsesi untuk selalu dekat dan melayani Kim, walaupun Kim menganggap Raisha hanya sahabat. \nSampai akhirnya Kim diterima di timnas. Raisha yang mempersiapkan pesta kejutan untuk Kim, menelan kekecewaan karena Kim merayakan dengan teman-temannya. Raisha menangis melihat begitu banyak wanita cantik berebutan foto dengan Kim, kesuksesan telah membawa Kim pergi jauh darinya.\nKim pun mulai latihan, tidak ada lagi Raisha yang selalu siap di pinggir lapangan untuk memberinya minum, tidak ada sepatu bola yang telah dibersihkan menunggunya. \nHingga sepulang latihan dengan bersepeda Kim ditabrak lari sebuah mobil, dan semua gelap. Kim tidak bisa melihat. Ketika semua mulai meninggalkannya, hanya Raisha yang telaten mendampinginya. \nYudith (Martina Tesela) perawat cantik di rumah sakit menyarankan Kim operasi kornea mata. Raisha marah dan menganggap Yudith hanya ingin memperkaya rumah sakit. Sejak itu Kim tidak kembali berobat, Yudith curiga dan mendatangi Kim. Raisha memergoki Yudith dan mencegahnya untuk membawa Kim. \n[\/SPOILER]\n\n\n[SPOILER=Sinopsis Cerita 3 - Sakit Hati]Gerry (Giorgino Abraham), SMA kelas 3 memiliki kekasih Lisa (Pevita Pearce). Mereka selalu bersama penuh keceriaan, Gerry selalu menyanyikan lagu ciptaannya untuk Lisa di sebuah bukit tempat favorit mereka. \nAkhir tahun ajaran membuat mereka berpisah karena beda perguruan tinggi. Lisa semakin larut dalam pergaulan metropolis, Lisa membohongi Gerry yang ngapel ke rumah kost Lisa hanya boleh sampai jam 9 malam. Padahal sepulang Gerry, Lisa berganti kostum dan melesat ke lantai disco dengan teman-temannya yang party-holic. Hingga akhirnya Gerry mengetahui ini, dengan motor yang diperoleh Gerry dengan bekerja di sebuah bengkel, ia mengikuti mobil teman-teman Lisa. Gerry tidak bisa menahan dirinya melihat Lisa dicium seorang lelaki. Tapi justru Lisa malah memilih lelaki itu, dan mengusir Gerry.\nSakit hati mengantar Gerry menjadi pencipta lagu yang sukses, di bukit kenangan mereka kembali bertemu. Lisa meminta maaf. Apakah Gerry masih punya ruang di hatinya untuk memaafkan Lisa?\n[\/SPOILER]\n\n[SPOILER=Sinopsis Cerita 4 - Jernih ]Tora (Dimas Anggara) dan Gofar (Gofar Hilman) adalah pedagang barang-barang KW di lapak yang selalu berurusan dengan razia yang dilakukan oleh Omar (Tri Wardoyo), si hamba hukum lebay. Saat mereka kabur dengan tas LV KW, mereka bertabrakan dengan Elena (Manohara Odelia) seorang wanita cantik dan elegan. Tas LV KW tertukar tas ori, sekaligus tabrakan itu menghempaskan hati Tora yang jatuh cinta ke Elena pada pandangan pertama. \nMereka terkejut mengetahui tas LV mereka tertukar dengan dokumen-dokumen yang tebal. Gofar ngamuk, baginya tas itu modal kerjanya, dan cewek itu adalah maling. Hingga HP mereka berbunyi, Elena menelepon Gofar karena ada kartu nama Gofar di kotak botol parfum KW yang mereka jual. Akhirnya dibuat janji pertukaran tas. Tora panik, sibuk dandan dan ingin tampil seganteng mungkin. Tanpa mereka ketahui, Elena adalah tunangan Haji Jo\u2019e (Joe P Project) pimpinan ormas kaya yang mirip mafia.\nAkankah Tora mendapatkan cinta Elena, yang memang sedang berusaha lepas dari Haji Jo\u2019e. Akankah Gofar kembali ke bisnisnya yang selalu kejar-kejaran dengan Omar, atau malah Omar berhasil menjernihkan kasus yang lebih besar? [\/SPOILER]\n\n:kiss\n\n[B][size=\"6\"]Siapa aja yang bakal dateng?? [\/size][\/B]\n\n[SPOILER=Nih, artis-artinya Gan][img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/03\/4440622_20140303053555.jpg[\/img]\n[I]Piyu[\/I]\n\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/03\/4440622_20140303053602.jpg[\/img]\n[I]Eriska Rein[\/I]\n\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305010113.jpg[\/img]\n[I]Rio Dewanto[\/I]\n[\/SPOILER]\n\n\nWah, mereka datang ber-enam Broo. Bakal seru dan heboh abis nih pastinya\n:matabelo\n\n\nKapan kapan kapan?? Mark your calendar yaa...\n\n[QUOTE][size=\"7\"][CENTER][B]Rabu, 5 Maret 2014\nPukul 14.00 - 16.00[\/B][\/CENTER][\/size][\/QUOTE]\n\nSo, udah siap mau live ngaskus bareng artis-artis kece ini?? Jangan lupa buat tulis pertanyaan-pertanyaan terbaik lo [URL=\"http:\/\/kask.us\/hxNDR\"][B]di sini[\/B][\/URL]\n\n\n[QUOTE][CENTER][size=\"5\"]10 orang yang beruntung akan mendapatkan masing-masing[B] 2 buah tiket [\/B]nonton film Aku Cinta Kamu yang bisa digunakan mulai hari Kamis, 6 Maret 2014 di seluruh bioskop 21.[\/B]\n\nNote: Tiket bisa diambil di kantor KASKUS hari Jumat, 7 Maret 2014[\/size][\/CENTER][\/QUOTE]\n\n\nFor more updates, bookmark thread ini ya Gann!\n\n\n\nCiaooo\n:ngacir :ngacir :ngacir \n[\/size][\/FONT][\/CENTER]",
            "text": "Heellloooww Gan & Siiiss!\n:shakehand2 \n\nUPDATE\n:hn :hn :hn\n\nDan inilah para penanya terbaik Live Ngaskus bareng Piyu, Rio Dewanto dan Eriska Rein. \n\n1. wqew\n\n2. R8486.Jr\n\n3. Dofar26\n\n4. cicimol\n\n5. defend\n\n6. dellahurahura\n\n7. GIML\n\n8. kemanajabole\n\n9. maulanfazry\n\n10. free1412\n\nSelamat kepada pemenang!\n:selamat :selamat :selamat\n\nSeluruh pemenang berhak mendapatkan masing-masing 2 tiket film Aku Cinta Kamu yang bisa ditonton di seluruh bioskop 21. \nTiket bisa diambil di kantor KASKUS mulai hari Rabu, 12 Maret 2014 sampai Jumat, 14 Maret 2014 pukul 10.00 -18.00\n\n\n\n\n\n\nUPDATE\n:hn :hn :hn\n\nLive Ngaskus lagi berlangsung nih Gan! Ayo tanya-tanya tentang film Aku Cinta Kamu ke Piyu, Rio Dewanto, dan Eriska Rein! Pertanyaan terbaik bakal dapet hadiah loh!\n:2thumbup\n\n\nAsli, IGO ini bening banget Gan! \n:matabelo\n\n\nPiyu senyum-senyum nih liat komentar para Kaskuser\n:ngakak\n\n\nKalau Rio serius nih jawab-in pertanyaan Agan-Agan\n\n\nSay Cheeseee\n\n\n\n\nHooorrrreee!! Ketemu lagi di acaranya KASKUS yang paling interaktif, apalagi kalau bukanLive Ngaskus\n:selamat :selamat\n\n\nYayyyy!! Bulan Maret ini kita bakal kedatangan para pemeran film \nAku Cinta Kamu\n:heart: :heart: :heart: :heart:\n\n\n\nqtdmRlPPGfE\n\n\nKetika cinta menyengat, berjuta rasa menjangkiti hati dan pikiran kita. Berbagai peristiwa besar dalam kehidupan, dipicu oleh satu kalimat singkat : Aku Cinta Kamu. Nah, berangkat dari 4 lagu cinta ciptaan seorang Piyu, dibuatlah 4 kisah dengan 4 genre menjadi sebuah film untuk mengenal cinta. Pokonya, it\u2019s all about love :heart: :heart: :heart:\n\nTentang Sita (Acha Septriasa) dan Randu (Rio Dewanto) yang mempersiapkan sebuah pesta pernikahan. Sita sebagai wedding organizer sangat perfectionist, dan menginginkan pernikahan paling sempurna. Sedangkan Randu, fotografer berjiwa seniman seakan cuek dengan persiapan Sita. Randu punya beribu alasan untuk menangguhkan foto prewed mereka. Hingga Sita mulai dipengaruhi firasatnya sendiri, kalau Randu berselingkuh dengan wanita lain bernama Rani (Fanny Fabriana). Hingga akhirnya Sita memergoki mereka. Sita dilema, apakah membatalkan pernikahannya atau mencoba ikhlas dan berfikir positif, mungkin Randu ingin menyelesaikan sejarah percintaannya dengan Rani sebelum memulai hidup bersamanya. \nHari pernikahan tiba, Sita dengan gaun cantik pernikahannya tidak bisa membendung air matanya. Dia lari dan Randu mengejarnya, hingga kecelakaan merenggut nyawa salah satu dari mereka, dan membuka mata bahwa firasat tidak selalu benar. \n\n\nKim (Kim Kurniawan) seorang pemain bola yang sedang naik daun, bertetangga dengan Raisha (Eriska Rein) yang begitu terobsesi untuk selalu dekat dan melayani Kim, walaupun Kim menganggap Raisha hanya sahabat. \nSampai akhirnya Kim diterima di timnas. Raisha yang mempersiapkan pesta kejutan untuk Kim, menelan kekecewaan karena Kim merayakan dengan teman-temannya. Raisha menangis melihat begitu banyak wanita cantik berebutan foto dengan Kim, kesuksesan telah membawa Kim pergi jauh darinya.\nKim pun mulai latihan, tidak ada lagi Raisha yang selalu siap di pinggir lapangan untuk memberinya minum, tidak ada sepatu bola yang telah dibersihkan menunggunya. \nHingga sepulang latihan dengan bersepeda Kim ditabrak lari sebuah mobil, dan semua gelap. Kim tidak bisa melihat. Ketika semua mulai meninggalkannya, hanya Raisha yang telaten mendampinginya. \nYudith (Martina Tesela) perawat cantik di rumah sakit menyarankan Kim operasi kornea mata. Raisha marah dan menganggap Yudith hanya ingin memperkaya rumah sakit. Sejak itu Kim tidak kembali berobat, Yudith curiga dan mendatangi Kim. Raisha memergoki Yudith dan mencegahnya untuk membawa Kim. \n\n\n\nGerry (Giorgino Abraham), SMA kelas 3 memiliki kekasih Lisa (Pevita Pearce). Mereka selalu bersama penuh keceriaan, Gerry selalu menyanyikan lagu ciptaannya untuk Lisa di sebuah bukit tempat favorit mereka. \nAkhir tahun ajaran membuat mereka berpisah karena beda perguruan tinggi. Lisa semakin larut dalam pergaulan metropolis, Lisa membohongi Gerry yang ngapel ke rumah kost Lisa hanya boleh sampai jam 9 malam. Padahal sepulang Gerry, Lisa berganti kostum dan melesat ke lantai disco dengan teman-temannya yang party-holic. Hingga akhirnya Gerry mengetahui ini, dengan motor yang diperoleh Gerry dengan bekerja di sebuah bengkel, ia mengikuti mobil teman-teman Lisa. Gerry tidak bisa menahan dirinya melihat Lisa dicium seorang lelaki. Tapi justru Lisa malah memilih lelaki itu, dan mengusir Gerry.\nSakit hati mengantar Gerry menjadi pencipta lagu yang sukses, di bukit kenangan mereka kembali bertemu. Lisa meminta maaf. Apakah Gerry masih punya ruang di hatinya untuk memaafkan Lisa?\n\n\nTora (Dimas Anggara) dan Gofar (Gofar Hilman) adalah pedagang barang-barang KW di lapak yang selalu berurusan dengan razia yang dilakukan oleh Omar (Tri Wardoyo), si hamba hukum lebay. Saat mereka kabur dengan tas LV KW, mereka bertabrakan dengan Elena (Manohara Odelia) seorang wanita cantik dan elegan. Tas LV KW tertukar tas ori, sekaligus tabrakan itu menghempaskan hati Tora yang jatuh cinta ke Elena pada pandangan pertama. \nMereka terkejut mengetahui tas LV mereka tertukar dengan dokumen-dokumen yang tebal. Gofar ngamuk, baginya tas itu modal kerjanya, dan cewek itu adalah maling. Hingga HP mereka berbunyi, Elena menelepon Gofar karena ada kartu nama Gofar di kotak botol parfum KW yang mereka jual. Akhirnya dibuat janji pertukaran tas. Tora panik, sibuk dandan dan ingin tampil seganteng mungkin. Tanpa mereka ketahui, Elena adalah tunangan Haji Jo\u2019e (Joe P Project) pimpinan ormas kaya yang mirip mafia.\nAkankah Tora mendapatkan cinta Elena, yang memang sedang berusaha lepas dari Haji Jo\u2019e. Akankah Gofar kembali ke bisnisnya yang selalu kejar-kejaran dengan Omar, atau malah Omar berhasil menjernihkan kasus yang lebih besar? \n\n:kiss\n\nSiapa aja yang bakal dateng?? \n\n\nPiyu\n\n\n\nEriska Rein\n\n\n\nRio Dewanto\n\n\n\nWah, mereka datang ber-enam Broo. Bakal seru dan heboh abis nih pastinya\n:matabelo\n\n\nKapan kapan kapan?? Mark your calendar yaa...\n\nRabu, 5 Maret 2014\nPukul 14.00 - 16.00\n\nSo, udah siap mau live ngaskus bareng artis-artis kece ini?? Jangan lupa buat tulis pertanyaan-pertanyaan terbaik lo di sini\n\n\n10 orang yang beruntung akan mendapatkan masing-masing 2 buah tiket nonton film Aku Cinta Kamu yang bisa digunakan mulai hari Kamis, 6 Maret 2014 di seluruh bioskop 21.\n\nNote: Tiket bisa diambil di kantor KASKUS hari Jumat, 7 Maret 2014\n\n\nFor more updates, bookmark thread ini ya Gann!\n\n\n\nCiaooo\n:ngacir :ngacir :ngacir"
        },
        {
            "pagetext": "[CENTER][FONT=\"Century Gothic\"]alhamdulilah menang \n\n[\/FONT][\/CENTER]",
            "text": "alhamdulilah menang"
        },
        {
            "pagetext": "Thread ini telah melebihi batas maksimal reply yang telah di tentukan. \n\t\t\t\n\t\t\t\t\t\t\t\t\t\t\tThread lanjutan dapat diakses di: [URL=\"http:\/\/aji.kaskus.dev\/thread\/54b389bc1ef4cc34060041a8\"]http:\/\/aji.kaskus.dev\/thread\/54b389bc1ef4cc34060041a8[\/URL]",
            "text": "Thread ini telah melebihi batas maksimal reply yang telah di tentukan. \n\t\t\t\n\t\t\t\t\t\t\t\t\t\t\tThread lanjutan dapat diakses di: http:\/\/aji.kaskus.dev\/thread\/54b389bc1ef4cc34060041a8"
        },
        {
            "pagetext": ";lkjlkjljlkjlkjl",
            "text": ";lkjlkjljlkjlkjl"
        },
        {
            "pagetext": "haloooo",
            "text": "haloooo"
        }
    ]
}
```

## POST forum_thread

Create forum thread based on id

### HTTP Request

`POST /v1/forum_thread`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



# Hot_thread_archive



## GET hot_thread_archive

Get List of Hot Thread's Archive

### HTTP Request

`GET /v1/hot_thread_archive`

Parameter | Description
--------- | -----------
q|Querying hot threads that contains some keywords in title and its first post message
date|Format: YYYY-MM-DD. Querying hot threads that have start date equals with specified date
output|output format (JSON or XML)



# Hot_threads



## GET hot_threads

Get List of Current Hot Thread

### HTTP Request

`GET /v1/hot_threads`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "data": [
        {
            "thread_id": "531e91b1bfcb17fc478b4746",
            "title": "Bosen sama gelas ente? Ancurin dikit yok ",
            "forum_name": "The Lounge",
            "forum_id": 21,
            "username": "Visivius4",
            "user_id": 2489108,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1448902800,
            "hot_thread_start_date": "20151201",
            "hot_thread_end_date": "20151210",
            "hot_thread_flag": 1,
            "vote_num": 1,
            "vote_total": 5,
            "rating": 5,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "531e81733dcb17036a8b4615",
            "title": "Di bentak kopaska, Tentara Laut malaysia kabur dari ambalat",
            "forum_name": "The Lounge",
            "forum_id": 21,
            "username": "pangerankecoa",
            "user_id": 6535994,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1449594000,
            "hot_thread_start_date": "20151209",
            "hot_thread_end_date": "20151212",
            "hot_thread_flag": 1,
            "vote_num": 1,
            "vote_total": 4,
            "rating": 4,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "567106d08ead0eeb2b0041bd",
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "forum_name": "The Lounge",
            "forum_id": 21,
            "username": "recca",
            "user_id": 11,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1450285200,
            "hot_thread_start_date": "20151217",
            "hot_thread_end_date": "20151217",
            "hot_thread_flag": 1,
            "vote_num": 0,
            "vote_total": 0,
            "rating": 0,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "531e9e04bfcb179c088b45ed",
            "title": "Heboh Foto Simpatisan PDIP Minum Air Cucian Kaki Megawati Soekarnoputri",
            "forum_name": "The Lounge",
            "forum_id": 21,
            "username": "dewinova",
            "user_id": 6537320,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1450285200,
            "hot_thread_start_date": "20151217",
            "hot_thread_end_date": "20151217",
            "hot_thread_flag": 1,
            "vote_num": 1,
            "vote_total": 1,
            "rating": 1,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "531e97a7a2cb17334f8b465a",
            "title": "Gunung Slamet Level II (Waspada)",
            "forum_name": "The Lounge",
            "forum_id": 21,
            "username": "highsa",
            "user_id": 892739,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1450285200,
            "hot_thread_start_date": "20151217",
            "hot_thread_end_date": "20151217",
            "hot_thread_flag": 1,
            "vote_num": 3,
            "vote_total": 15,
            "rating": 5,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "531e832af7ca17b85f8b45ad",
            "title": "Secret Operation: Naga Cina Melilit Garuda",
            "forum_name": "The Lounge",
            "forum_id": 21,
            "username": "hadifataya",
            "user_id": 3197276,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1450198800,
            "hot_thread_start_date": "20151216",
            "hot_thread_end_date": "19700101",
            "hot_thread_flag": 1,
            "vote_num": 0,
            "vote_total": 0,
            "rating": 0,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "51c2d7af05346a2909000004",
            "title": "MotoGP Community: Ajang Informasi dan Diskusi Penggemar MotoGP",
            "forum_name": "Racing \/ Balap",
            "forum_id": 332,
            "username": "5peedz",
            "user_id": 3169969,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1450198800,
            "hot_thread_start_date": "20151216",
            "hot_thread_end_date": "19700101",
            "hot_thread_flag": 1,
            "vote_num": 22,
            "vote_total": 101,
            "rating": 4.59,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "52eb2abffcca175d350000de",
            "title": "SOLO JUNGLE WARGAME 24 HOURS 30-31 MARET 2014 \"SEKIPAN FOREST\"",
            "forum_name": "Airsoft Indonesia",
            "forum_id": 187,
            "username": "aisantoso",
            "user_id": 2710707,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1450198800,
            "hot_thread_start_date": "20151216",
            "hot_thread_end_date": "19700101",
            "hot_thread_flag": 1,
            "vote_num": 2,
            "vote_total": 10,
            "rating": 5,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "52ea5b4aa4cb1775218b4619",
            "title": "beresikokah? yambung besi kolom beton bertulang di tumpuan dengan dilas",
            "forum_name": "Sipil",
            "forum_id": 579,
            "username": "mredah",
            "user_id": 2608759,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1450198800,
            "hot_thread_start_date": "20151216",
            "hot_thread_end_date": "19700101",
            "hot_thread_flag": 1,
            "vote_num": 0,
            "vote_total": 0,
            "rating": 0,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        }
    ],
    "meta": {
        "cache_key": "request_get_hot_threads_request_handler",
        "cached": true,
        "cached_from": 1450676227
    }
}
```

# Lapak



## GET lapak

Read lapak thread based on id. Thread rating can be calculated from vote_total and vote_num.           Rating = vote_total / vote_num.

### HTTP Request

`GET /v1/lapak/{id}`

Parameter | Description
--------- | -----------
id|thread id
output|output format (JSON or XML)
page|number of post page
limit|limit number of post per page
field|post field that need to be filtered
include|add similar thread
post|get thread by post id



## POST lapak

Create lapak thread

### HTTP Request

`POST /v1/lapak`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## POST lapak

Sundul lapak thread

### HTTP Request

`POST /v1/lapak/{id}/sundul`

Parameter | Description
--------- | -----------
id|thread id



# Lapak_post



## GET lapak_post

Get lapak post details

### HTTP Request

`GET /v1/lapak_post/{id}`

Parameter | Description
--------- | -----------
id|Post Id that we want to get the detail
output|output format (JSON or XML)
field|post field that need to be filtered



## POST lapak_post

Create new lapak post

### HTTP Request

`POST /v1/lapak_post`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



## POST lapak_post

Edit lapak post

### HTTP Request

`POST /v1/lapak_post/{id}/edit`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)



# Lapak_setting



## GET lapak_setting

Get Lapak Setting

### HTTP Request

`GET /v1/lapak/settings`

Parameter | Description
--------- | -----------
output|output format (JSON or XML)




> Example response

```json
{
    "upload_pictures": {
        "max": 10,
        "min": 0,
        "required": false
    },
    "extra_attributes": {
        "max": 5,
        "min": 0,
        "required": false
    },
    "item_price": {
        "max": 450000000,
        "min": 100,
        "required": true
    },
    "title": {
        "max": 85,
        "min": 1,
        "required": true
    },
    "message": {
        "max": 20000,
        "min": 5,
        "required": true
    },
    "search_tags": {
        "max": 1000,
        "min": 1,
        "required": true
    },
    "comment_title": {
        "max": 85,
        "min": 0,
        "required": false
    },
    "comment_message": {
        "max": 20000,
        "min": 5,
        "required": true
    },
    "sundul": {
        "excluded_forum_id": [
            220
        ]
    }
}
```

# Latest_products



## GET latest_products

get list of latest WTS product from requested only FJB forums.       For each forum we will get five latest items

### HTTP Request

`GET /latest_products`

Parameter | Description
--------- | -----------
forum_ids|List of forum id separated by comma
cursor|First request you just to have use cursor:0
limit|limit for returned lapak in a request
output|output format (JSON or XML)




> Example response

```json
{
    "thread": [
        {
            "forum_id": 210,
            "title": "BALON ADA 5",
            "dateline": 1429254794,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 1,
            "views": 125,
            "post_username": "Lientz",
            "post_userid": 2629271,
            "first_post_id": "5530b28a8ead0e12010041a8",
            "last_poster": "Lientz",
            "last_post_userid": 2629271,
            "last_post": 1444639350,
            "last_post_id": "55998189f9845fecc70041c0",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "asdafa",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 10000,
            "item_location": 1,
            "discount": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/cYl",
            "sundul_enabled": 1,
            "thread_id": "5530b28a8ead0e12010041a7",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 9900,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/02\/24\/avatar2629271_1.gif",
            "usertitle": "kaskus addict",
            "number_of_post": "2134",
            "total_badge": 0,
            "enable_reputation": 1,
            "reputation": "11",
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "forum_id": 210,
            "title": "Iphone 7 Brand New",
            "dateline": 1432814304,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 1,
            "views": 246,
            "post_username": "pintoco2",
            "post_userid": 2896639,
            "first_post_id": "556702e0c721e6f4298b4568",
            "last_poster": "pintoco2",
            "last_post_userid": 2896639,
            "last_post": 1442205602,
            "last_post_id": "55f64fa278ae7a4fc200fc6e",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "iphone 7",
            "meta_images": [],
            "item_condition": 2,
            "item_price": 7000000,
            "item_location": 11,
            "discount": 10,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQt9",
            "sundul_enabled": 1,
            "thread_id": "556702e0c721e6f4298b4567",
            "initial_prefix_id": "WTS",
            "extra_attributes": [
                {
                    "attribute": "Warna",
                    "value": "Hijau"
                }
            ],
            "thread_type": 21,
            "discounted_price": 6300000,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/04\/30\/avatar2896639_1.gif",
            "usertitle": "Administrator",
            "number_of_post": "63",
            "total_badge": 0,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 210,
            "title": "Nokia Lumia 820 32 GB 34867f4885a3544bb3ef2ea50d515f8c",
            "dateline": 1440408611,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 6,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "55dae42374d93a9e028b48e4",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1440408611,
            "last_post_id": "55dae42374d93a9e028b48e4",
            "sticky": 0,
            "prefix_id": "WTB",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "item_condition": 4,
            "item_price": 43066252,
            "item_location": 25,
            "tagsearch": "aksesoris",
            "resources": {
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images": [],
                "images_thumbnail": []
            },
            "discount": 10,
            "short_url": "http:\/\/kask.us\/dBa",
            "sundul_enabled": 1,
            "thread_id": "55dae42374d93a9e028b48e5",
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 38759627,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": "3295",
            "total_badge": 0,
            "enable_reputation": 1,
            "reputation": "1774",
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "forum_id": 210,
            "title": "Anggoro sedang makan2 bulanan",
            "dateline": 1440408572,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 14,
            "views": 23,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "55dae3fc74d93ae6248b48a0",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1440408606,
            "last_post_id": "55dae41e74d93a2b008b490f",
            "sticky": 0,
            "prefix_id": "WTS",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "item_condition": 2,
            "item_price": 357613,
            "item_location": 8,
            "tagsearch": "makanan,fashion,hp,elektronik",
            "resources": {
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images": [],
                "images_thumbnail": []
            },
            "discount": 0,
            "short_url": "http:\/\/kask.us\/dA9",
            "sundul_enabled": 1,
            "thread_id": "55dae3fc74d93ae6248b48a1",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 357613,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": "3295",
            "total_badge": 0,
            "enable_reputation": 1,
            "reputation": "1774",
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        },
        {
            "forum_id": 210,
            "title": "Bowo dan Bowo sedang makan2 bulanan",
            "dateline": 1440408569,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 3,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "55dae3f974d93a2b008b48ff",
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1440408569,
            "last_post_id": "55dae3f974d93a2b008b48ff",
            "sticky": 0,
            "prefix_id": "WTB",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "item_condition": 1,
            "item_price": 298899,
            "item_location": 11,
            "tagsearch": "iphone,rumah tangga,samsung,makanan,hp",
            "resources": {
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images": [],
                "images_thumbnail": []
            },
            "discount": 0,
            "short_url": "http:\/\/kask.us\/dA8",
            "sundul_enabled": 1,
            "thread_id": "55dae3f974d93a2b008b4900",
            "initial_prefix_id": "WTB",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 298899,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": "3295",
            "total_badge": 0,
            "enable_reputation": 1,
            "reputation": "1774",
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 11
        }
    ],
    "cursor": "MjEwLDQsQW9KNHl0RENyODhDT0RVMVpHRmxNMlk1TnpSa09UTmhNbUl3TURoaU5Ea3dNQT09LDIxMC0yMDg"
}
```

# Search



## GET search/forum

Search Forum.

### HTTP Request

`GET /search/forum`

Parameter | Description
--------- | -----------
q|Query string to search
output|output format (JSON or XML)
include|valid value: facet




> Example response

```json
{
    "item": [
        {
            "thread_id": "531e8aa93fcb1799068b45ec",
            "title": "Review: Acer Liquid Z5, Android dengan Tombol \"Selfie\"",
            "score": 10,
            "thread_type": 10,
            "forum_id": 250,
            "forum_name": "Berita Luar Negeri",
            "post_id": "531e8aa93fcb1799068b45ed",
            "post_title": "Review: Acer Liquid Z5, Android dengan Tombol \"Selfie\"",
            "post_userid": 6503627,
            "post_username": "manusiagadget",
            "dateline": 1394510505,
            "last_post": 1394511175,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2014\/02\/28\/avatar6503627_1.gif",
            "usertitle": "newbie",
            "number_of_post": 3,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 0
        },
        {
            "thread_id": "531e842019cb17702e8b45d1",
            "title": "[Pirate Army] Optimisasi Android by HQ.Kaskus [PG-R]",
            "score": 17,
            "thread_type": 10,
            "forum_id": 21,
            "forum_name": "The Lounge",
            "post_id": "531e842019cb17702e8b45d2",
            "post_title": "[Pirate Army] Optimisasi Android by HQ.Kaskus [PG-R]",
            "post_userid": 4036780,
            "post_username": "HQ.Kaskus",
            "dateline": 1394508832,
            "last_post": 1394518059,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2012\/02\/16\/avatar4036780_6.gif",
            "usertitle": "kaskus holic",
            "number_of_post": 930,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 5,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 1
        },
        {
            "thread_id": "531e64c05ccb17ec3000009a",
            "title": "Hp android yang kaya iPod itu apa ya ?",
            "score": 10,
            "thread_type": 10,
            "forum_id": 577,
            "forum_name": "Android",
            "post_id": "531e64c05ccb17ec3000009b",
            "post_title": "Hp android yang kaya iPod itu apa ya ?",
            "post_userid": 6517758,
            "post_username": "aldy9900",
            "dateline": 1394500800,
            "last_post": 1394500800,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "",
            "number_of_post": 0,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "",
            "reputation_box": 0
        },
        {
            "thread_id": "531e51e659cb17107b8b45a4",
            "title": "Download Complete Guide How to Root Android (Ebook)",
            "score": 10,
            "thread_type": 10,
            "forum_id": 21,
            "forum_name": "The Lounge",
            "post_id": "531e51e659cb17107b8b45a5",
            "post_title": "Download Complete Guide How to Root Android (Ebook)",
            "post_userid": 6539351,
            "post_username": "lilae123",
            "dateline": 1394495974,
            "last_post": 1394518534,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "",
            "number_of_post": 0,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "",
            "reputation_box": 0
        },
        {
            "thread_id": "531e4718c0cb17d2528b456b",
            "title": "SOAL APLIKASI KASKUS ANDROID",
            "score": 17,
            "thread_type": 10,
            "forum_id": 31,
            "forum_name": "Kritik, Saran, Pertanyaan Seputar KASKUS",
            "post_id": "531e4718c0cb17d2528b456c",
            "post_title": "SOAL APLIKASI KASKUS ANDROID",
            "post_userid": 3057143,
            "post_username": "rifki123",
            "dateline": 1394493208,
            "last_post": 1394493208,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/06\/11\/avatar3057143_3.gif",
            "usertitle": "kaskuser",
            "number_of_post": 183,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 0
        },
        {
            "thread_id": "531e300dc2cb17221b8b45ee",
            "title": "bbm android",
            "score": 21,
            "thread_type": 10,
            "forum_id": 577,
            "forum_name": "Android",
            "post_id": "531e300dc2cb17221b8b45ef",
            "post_title": "bbm android",
            "post_userid": 6229232,
            "post_username": "elkapiten",
            "dateline": 1394487309,
            "last_post": 1394487309,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2013\/12\/18\/avatar6229232_1.gif",
            "usertitle": "newbie",
            "number_of_post": 8,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 0
        },
        {
            "thread_id": "531e1a8ff8ca1745288b462a",
            "title": "lagi cari programmer android di bandung",
            "score": 12,
            "thread_type": 10,
            "forum_id": 176,
            "forum_name": "Programmer Forum",
            "post_id": "531e1a8ff8ca1745288b462b",
            "post_title": "lagi cari programmer android di bandung",
            "post_userid": 4356248,
            "post_username": "jacki7",
            "dateline": 1394481807,
            "last_post": 1394497315,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2012\/05\/16\/avatar4356248_1.gif",
            "usertitle": "newbie",
            "number_of_post": 8,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 0
        },
        {
            "thread_id": "531de515118b4672718b45a1",
            "title": "asphalt 8 android",
            "score": 17,
            "thread_type": 10,
            "forum_id": 21,
            "forum_name": "The Lounge",
            "post_id": "531de515118b4672718b45a2",
            "post_title": "asphalt 8 android",
            "post_userid": 5464135,
            "post_username": "kb1198",
            "dateline": 1394468117,
            "last_post": 1394468955,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2013\/05\/12\/male.jpg",
            "usertitle": "newbie",
            "number_of_post": 0,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 0
        },
        {
            "thread_id": "531dc25317cb1786458b4594",
            "title": "Lima Aplikasi Buat Genjot Kecepatan Internet di Android",
            "score": 10,
            "thread_type": 10,
            "forum_id": 21,
            "forum_name": "The Lounge",
            "post_id": "531dc25317cb1786458b4595",
            "post_title": "Lima Aplikasi Buat Genjot Kecepatan Internet di Android",
            "post_userid": 3187246,
            "post_username": "aryahacky",
            "dateline": 1394459219,
            "last_post": 1394517134,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/07\/13\/avatar3187246_1.gif",
            "usertitle": "kaskuser",
            "number_of_post": 230,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 6,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 1
        },
        {
            "thread_id": "531db6e95bcb17ef040000e3",
            "title": "android",
            "score": 34,
            "thread_type": 10,
            "forum_id": 577,
            "forum_name": "Android",
            "post_id": "531db6e95bcb17ef040000e4",
            "post_title": "android",
            "post_userid": 6537876,
            "post_username": "aand20",
            "dateline": 1394456297,
            "last_post": 1394456297,
            "hot_thread": 0,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "",
            "number_of_post": 0,
            "is_donatur": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "",
            "reputation_box": 0
        }
    ],
    "start": 0,
    "numFound": 1583,
    "querytime": 0.0139,
    "facet": {
        "forum_id": [
            {
                "value": "21",
                "count": 1038
            },
            {
                "value": "281",
                "count": 70
            },
            {
                "value": "577",
                "count": 67
            },
            {
                "value": "176",
                "count": 58
            },
            {
                "value": "119",
                "count": 32
            },
            {
                "value": "10",
                "count": 30
            },
            {
                "value": "9",
                "count": 28
            },
            {
                "value": "278",
                "count": 27
            },
            {
                "value": "19",
                "count": 26
            },
            {
                "value": "186",
                "count": 24
            },
            {
                "value": "14",
                "count": 18
            },
            {
                "value": "183",
                "count": 17
            },
            {
                "value": "250",
                "count": 16
            },
            {
                "value": "100",
                "count": 14
            },
            {
                "value": "238",
                "count": 9
            },
            {
                "value": "13",
                "count": 9
            },
            {
                "value": "31",
                "count": 8
            },
            {
                "value": "59",
                "count": 6
            },
            {
                "value": "34",
                "count": 6
            },
            {
                "value": "541",
                "count": 4
            },
            {
                "value": "54",
                "count": 4
            },
            {
                "value": "191",
                "count": 4
            },
            {
                "value": "471",
                "count": 3
            },
            {
                "value": "419",
                "count": 3
            },
            {
                "value": "243",
                "count": 3
            },
            {
                "value": "331",
                "count": 3
            },
            {
                "value": "65",
                "count": 3
            },
            {
                "value": "282",
                "count": 2
            },
            {
                "value": "469",
                "count": 2
            },
            {
                "value": "528",
                "count": 2
            },
            {
                "value": "280",
                "count": 2
            },
            {
                "value": "602",
                "count": 2
            },
            {
                "value": "413",
                "count": 2
            },
            {
                "value": "88",
                "count": 2
            },
            {
                "value": "26",
                "count": 2
            },
            {
                "value": "30",
                "count": 2
            },
            {
                "value": "37",
                "count": 2
            },
            {
                "value": "33",
                "count": 2
            },
            {
                "value": "443",
                "count": 1
            },
            {
                "value": "467",
                "count": 1
            },
            {
                "value": "437",
                "count": 1
            },
            {
                "value": "421",
                "count": 1
            },
            {
                "value": "472",
                "count": 1
            },
            {
                "value": "429",
                "count": 1
            },
            {
                "value": "435",
                "count": 1
            },
            {
                "value": "561",
                "count": 1
            },
            {
                "value": "595",
                "count": 1
            },
            {
                "value": "620",
                "count": 1
            },
            {
                "value": "586",
                "count": 1
            },
            {
                "value": "572",
                "count": 1
            },
            {
                "value": "557",
                "count": 1
            },
            {
                "value": "417",
                "count": 1
            },
            {
                "value": "546",
                "count": 1
            },
            {
                "value": "188",
                "count": 1
            },
            {
                "value": "113",
                "count": 1
            },
            {
                "value": "114",
                "count": 1
            },
            {
                "value": "98",
                "count": 1
            },
            {
                "value": "91",
                "count": 1
            },
            {
                "value": "38",
                "count": 1
            },
            {
                "value": "84",
                "count": 1
            },
            {
                "value": "116",
                "count": 1
            },
            {
                "value": "140",
                "count": 1
            },
            {
                "value": "277",
                "count": 1
            },
            {
                "value": "279",
                "count": 1
            },
            {
                "value": "181",
                "count": 1
            },
            {
                "value": "179",
                "count": 1
            },
            {
                "value": "167",
                "count": 1
            },
            {
                "value": "170",
                "count": 1
            },
            {
                "value": "391",
                "count": 1
            }
        ]
    },
    "current_page": 1,
    "total_pages": 159,
    "per_page": 10
}
```

## GET search/classified

Search fjb thread.

### HTTP Request

`GET /search/classified`

Parameter | Description
--------- | -----------
q|Query with optional filters. Valid filters are 'condition:new,second,refurbish',               'location:province_id1,province_id2', 'fid:forum_id,forum_id2','type:sold,buy,sell','donatur:true',               'price:10' - exact match,'price:10-100' - between,'price:10' - use less than mark,'price:10' -               use greater than mark, 'price:~100' - price between 90 to 110 (about 10%)
output|output format (JSON or XML)
include|valid value: facet




> Example response

```json
{
    "item": [
        {
            "thread_id": "531b27590d8b4661228b45f0",
            "title": "Android Htc desire adr6275 COD BANDUNG",
            "score": 13,
            "thread_type": 20,
            "forum_id": 527,
            "forum_name": "Aksesoris, suku cadang HP",
            "post_id": "531b27590d8b4661228b45f1",
            "post_title": "Android Htc desire adr6275 COD BANDUNG",
            "post_userid": 6516175,
            "post_username": "galihmontana",
            "dateline": 1394288473,
            "last_post": 1394520199,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 950000,
            "discount": 0,
            "discounted_price": 950000,
            "item_location": 12,
            "item_condition": 2,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 214,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "",
            "number_of_post": 0,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "",
            "reputation_box": 0
        },
        {
            "thread_id": "530c712341cb17ff088b46ad",
            "title": "DIGITAL DVD WESTERN COMICS MARVEL, dan DC PC\/ANDROID\/IPAD",
            "score": 9,
            "thread_type": 20,
            "forum_id": 625,
            "forum_name": "Komik",
            "post_id": "530c712341cb17ff088b46ae",
            "post_title": "DIGITAL DVD WESTERN COMICS MARVEL, dan DC PC\/ANDROID\/IPAD",
            "post_userid": 5335704,
            "post_username": "yoidahh07",
            "dateline": 1393324323,
            "last_post": 1394520191,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 77777,
            "discount": 0,
            "discounted_price": 77777,
            "item_location": 11,
            "item_condition": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 116,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2013\/04\/03\/male.jpg",
            "usertitle": "newbie",
            "number_of_post": 13,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 0
        },
        {
            "thread_id": "5209fcb340cb17bb75000003",
            "title": "Kumpulan DVD Game Console\/Handled With Emulator, Play di PC\/laptop\/Android",
            "score": 9,
            "thread_type": 20,
            "forum_id": 200,
            "forum_name": "CD & DVD",
            "post_id": "5209fcb340cb17bb75000004",
            "post_title": "Kumpulan DVD Game Console\/Handled With Emulator, Play di PC\/laptop\/Android",
            "post_userid": 1746382,
            "post_username": "raizodanz",
            "dateline": 1376386227,
            "last_post": 1394520186,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 8000,
            "discount": 0,
            "discounted_price": 8000,
            "item_location": 11,
            "item_condition": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 2735,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2010\/06\/06\/avatar1746382_6.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 1956,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 556,
            "reputation_title": "is a name known to all",
            "reputation_box": 6
        },
        {
            "thread_id": "531ea3a4a1cb1702148b481c",
            "title": "[RUSAK TAPI MASIH BISA KEPAKE] SAMSUNG ANDROID \/ iPHONE 3GS 32GB \/ LAPTOP - BANDUNG",
            "score": 11,
            "thread_type": 20,
            "forum_id": 210,
            "forum_name": "Handphone & Tablet updated",
            "post_id": "531ea3a4a1cb1702148b481d",
            "post_title": "[RUSAK TAPI MASIH BISA KEPAKE] SAMSUNG ANDROID \/ iPHONE 3GS 32GB \/ LAPTOP - BANDUNG",
            "post_userid": 1012340,
            "post_username": "sugamen",
            "dateline": 1394516900,
            "last_post": 1394520173,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 1234567890,
            "discount": 0,
            "discounted_price": 1234567890,
            "item_location": 12,
            "item_condition": 2,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 54,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/08\/01\/avatar1012340_16.gif",
            "usertitle": "aktivis kaskus",
            "number_of_post": 685,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 20,
            "reputation_title": "sedang di jalan yg benar",
            "reputation_box": 1
        },
        {
            "thread_id": "52ecea5641cb1778688b4685",
            "title": "Targus Stylus for iPad iPhone Ipod Tablet Android ",
            "score": 11,
            "thread_type": 20,
            "forum_id": 527,
            "forum_name": "Aksesoris, suku cadang HP",
            "post_id": "52ecea5641cb1778688b4686",
            "post_title": "Targus Stylus for iPad iPhone Ipod Tablet Android ",
            "post_userid": 2501421,
            "post_username": "elqo",
            "dateline": 1391258198,
            "last_post": 1394520120,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 130000,
            "discount": 0,
            "discounted_price": 130000,
            "item_location": 11,
            "item_condition": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 376,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/01\/21\/avatar2501421_2.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 2235,
            "is_donatur": true,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 29,
            "reputation_title": "sedang di jalan yg benar",
            "reputation_box": 1
        },
        {
            "thread_id": "52cb4fcf5ccb179e08000027",
            "title": "***TOMCAT!! BONEKA KUCING YANG BISA BERSUARA!! PERSIS KAYA DI IPHONE ATAU ANDROID!!**",
            "score": 9,
            "thread_type": 20,
            "forum_id": 198,
            "forum_name": "Koleksi, Hobi & Mainan",
            "post_id": "52cb4fcf5ccb179e08000028",
            "post_title": "***TOMCAT!! BONEKA KUCING YANG BISA BERSUARA!! PERSIS KAYA DI IPHONE ATAU ANDROID!!**",
            "post_userid": 6235425,
            "post_username": "rika.akana88",
            "dateline": 1389055951,
            "last_post": 1394519948,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 90000,
            "discount": 0,
            "discounted_price": 90000,
            "item_location": 11,
            "item_condition": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 718,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2013\/12\/19\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 101,
            "is_donatur": true,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 2,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 1
        },
        {
            "thread_id": "525662ca38cb179958000002",
            "title": "[Kompi Gue] Gaming Controller Untuk Android, Iphone, Tablet Gan!! | Silakan masuk!!",
            "score": 12,
            "thread_type": 20,
            "forum_id": 527,
            "forum_name": "Aksesoris, suku cadang HP",
            "post_id": "525662ca38cb179958000003",
            "post_title": "[Kompi Gue] Gaming Controller Untuk Android, Iphone, Tablet Gan!! | Silakan masuk!!",
            "post_userid": 5830755,
            "post_username": "kompigue",
            "dateline": 1381393098,
            "last_post": 1394519935,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 123,
            "discount": 0,
            "discounted_price": 123,
            "item_location": 12,
            "item_condition": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 3438,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2013\/09\/04\/avatar5830755_5.gif",
            "usertitle": "Kaskus Donator",
            "number_of_post": 106,
            "is_donatur": true,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 94,
            "reputation_title": "akan menjadi terkenal",
            "reputation_box": 1
        },
        {
            "thread_id": "5301a6ab1f0bc30b778b45b4",
            "title": "UNBRICKANDROID MEDIATEK ~ UNBRICK ANDROID GENERIC-REPLIKA-SUPERCOPY-MTK-ALLWINNER DLL",
            "score": 9,
            "thread_type": 20,
            "forum_id": 574,
            "forum_name": "Jasa & Perbaikan HP",
            "post_id": "5301a6ab1f0bc30b778b45b5",
            "post_title": "UNBRICKANDROID MEDIATEK ~ UNBRICK ANDROID GENERIC-REPLIKA-SUPERCOPY-MTK-ALLWINNER DLL",
            "post_userid": 6267029,
            "post_username": "unbrickandroid",
            "dateline": 1392617131,
            "last_post": 1394519849,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 1234,
            "discount": 0,
            "discounted_price": 1234,
            "item_location": 12,
            "item_condition": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 483,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2013\/12\/29\/avatar6267029_3.gif",
            "usertitle": "kaskuser",
            "number_of_post": 171,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 2,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 1
        },
        {
            "thread_id": "52c1274838cb17c0708b498f",
            "title": "SERVICE & Install Komputer\/Smartphone (Mac,windows,Linux,Android,iOs,BB) Free Game",
            "score": 9,
            "thread_type": 20,
            "forum_id": 631,
            "forum_name": "Instalasi Komputer new",
            "post_id": "52c1274838cb17c0708b4990",
            "post_title": "SERVICE & Install Komputer\/Smartphone (Mac,windows,Linux,Android,iOs,BB) Free Game",
            "post_userid": 5021669,
            "post_username": "arvianeutron",
            "dateline": 1388390216,
            "last_post": 1394519714,
            "prefix_id": "",
            "initial_prefix_id": "",
            "item_price": 123,
            "discount": 0,
            "discounted_price": 123,
            "item_location": 14,
            "item_condition": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 748,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2012\/12\/21\/avatar5021669_16.gif",
            "usertitle": "kaskus maniac",
            "number_of_post": 4043,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 960,
            "reputation_title": "is a splendid one to behold",
            "reputation_box": 8
        },
        {
            "thread_id": "52a9762818cb1723158b45e2",
            "title": "Jasa Pembuatan Software Perkantoran, Website, SEO, ERP, Android Mobile, Manage Server",
            "score": 9,
            "thread_type": 20,
            "forum_id": 553,
            "forum_name": "Web Hosting & Services",
            "post_id": "52a9762818cb1723158b45e3",
            "post_title": "Jasa Pembuatan Software Perkantoran, Website, SEO, ERP, Android Mobile, Manage Server",
            "post_userid": 5812535,
            "post_username": "amantechnology",
            "dateline": 1386837544,
            "last_post": 1394519676,
            "prefix_id": "WTS",
            "initial_prefix_id": "",
            "item_price": 123,
            "discount": 0,
            "discounted_price": 123,
            "item_location": 11,
            "item_condition": 1,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "thread_views": 738,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2013\/08\/29\/avatar5812535_1.gif",
            "usertitle": "newbie",
            "number_of_post": 19,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 0
        }
    ],
    "start": 0,
    "numFound": 9515,
    "querytime": 0.0194,
    "facet": {
        "forum_id": [
            {
                "value": "210",
                "count": 6649
            },
            {
                "value": "527",
                "count": 803
            },
            {
                "value": "574",
                "count": 288
            },
            {
                "value": "588",
                "count": 184
            },
            {
                "value": "212",
                "count": 121
            },
            {
                "value": "200",
                "count": 115
            },
            {
                "value": "294",
                "count": 99
            },
            {
                "value": "329",
                "count": 76
            },
            {
                "value": "202",
                "count": 67
            },
            {
                "value": "297",
                "count": 63
            },
            {
                "value": "553",
                "count": 61
            },
            {
                "value": "254",
                "count": 59
            },
            {
                "value": "330",
                "count": 52
            },
            {
                "value": "302",
                "count": 52
            },
            {
                "value": "195",
                "count": 50
            },
            {
                "value": "319",
                "count": 48
            },
            {
                "value": "215",
                "count": 48
            },
            {
                "value": "449",
                "count": 46
            },
            {
                "value": "325",
                "count": 46
            },
            {
                "value": "323",
                "count": 44
            },
            {
                "value": "613",
                "count": 42
            },
            {
                "value": "255",
                "count": 42
            },
            {
                "value": "327",
                "count": 41
            },
            {
                "value": "381",
                "count": 36
            },
            {
                "value": "604",
                "count": 32
            },
            {
                "value": "612",
                "count": 28
            },
            {
                "value": "631",
                "count": 24
            },
            {
                "value": "318",
                "count": 22
            },
            {
                "value": "313",
                "count": 19
            },
            {
                "value": "206",
                "count": 17
            },
            {
                "value": "614",
                "count": 15
            },
            {
                "value": "293",
                "count": 14
            },
            {
                "value": "334",
                "count": 13
            },
            {
                "value": "151",
                "count": 12
            },
            {
                "value": "261",
                "count": 12
            },
            {
                "value": "605",
                "count": 11
            },
            {
                "value": "450",
                "count": 11
            },
            {
                "value": "616",
                "count": 10
            },
            {
                "value": "208",
                "count": 10
            },
            {
                "value": "198",
                "count": 10
            },
            {
                "value": "322",
                "count": 9
            },
            {
                "value": "264",
                "count": 7
            },
            {
                "value": "227",
                "count": 7
            },
            {
                "value": "221",
                "count": 7
            },
            {
                "value": "226",
                "count": 7
            },
            {
                "value": "444",
                "count": 6
            },
            {
                "value": "265",
                "count": 6
            },
            {
                "value": "573",
                "count": 5
            },
            {
                "value": "220",
                "count": 5
            },
            {
                "value": "310",
                "count": 5
            },
            {
                "value": "333",
                "count": 4
            },
            {
                "value": "589",
                "count": 4
            },
            {
                "value": "324",
                "count": 4
            },
            {
                "value": "268",
                "count": 4
            },
            {
                "value": "216",
                "count": 4
            },
            {
                "value": "196",
                "count": 4
            },
            {
                "value": "300",
                "count": 3
            },
            {
                "value": "320",
                "count": 3
            },
            {
                "value": "273",
                "count": 3
            },
            {
                "value": "321",
                "count": 2
            },
            {
                "value": "625",
                "count": 2
            },
            {
                "value": "299",
                "count": 2
            },
            {
                "value": "590",
                "count": 2
            },
            {
                "value": "286",
                "count": 2
            },
            {
                "value": "269",
                "count": 2
            },
            {
                "value": "204",
                "count": 2
            },
            {
                "value": "312",
                "count": 1
            },
            {
                "value": "288",
                "count": 1
            },
            {
                "value": "314",
                "count": 1
            },
            {
                "value": "326",
                "count": 1
            },
            {
                "value": "283",
                "count": 1
            },
            {
                "value": "603",
                "count": 1
            },
            {
                "value": "205",
                "count": 1
            },
            {
                "value": "199",
                "count": 1
            },
            {
                "value": "209",
                "count": 1
            },
            {
                "value": "231",
                "count": 1
            },
            {
                "value": "256",
                "count": 1
            },
            {
                "value": "257",
                "count": 1
            }
        ],
        "prefix_id": [
            {
                "value": "wts",
                "count": 8199
            },
            {
                "value": "sold",
                "count": 739
            },
            {
                "value": "wtb",
                "count": 232
            }
        ],
        "item_location": [
            {
                "value": "11",
                "count": 3550
            },
            {
                "value": "12",
                "count": 1471
            },
            {
                "value": "14",
                "count": 1350
            },
            {
                "value": "15",
                "count": 995
            },
            {
                "value": "13",
                "count": 817
            },
            {
                "value": "16",
                "count": 614
            },
            {
                "value": "6",
                "count": 47
            },
            {
                "value": "23",
                "count": 45
            },
            {
                "value": "22",
                "count": 44
            },
            {
                "value": "20",
                "count": 44
            },
            {
                "value": "21",
                "count": 41
            },
            {
                "value": "2",
                "count": 41
            },
            {
                "value": "18",
                "count": 37
            },
            {
                "value": "8",
                "count": 36
            },
            {
                "value": "4",
                "count": 34
            },
            {
                "value": "5",
                "count": 33
            },
            {
                "value": "17",
                "count": 33
            },
            {
                "value": "33",
                "count": 29
            },
            {
                "value": "26",
                "count": 24
            },
            {
                "value": "19",
                "count": 23
            },
            {
                "value": "3",
                "count": 20
            },
            {
                "value": "1",
                "count": 17
            },
            {
                "value": "10",
                "count": 14
            },
            {
                "value": "7",
                "count": 11
            },
            {
                "value": "9",
                "count": 8
            },
            {
                "value": "24",
                "count": 6
            },
            {
                "value": "25",
                "count": 4
            },
            {
                "value": "32",
                "count": 3
            },
            {
                "value": "30",
                "count": 1
            },
            {
                "value": "29",
                "count": 1
            }
        ],
        "item_condition": [
            {
                "value": "1",
                "count": 6333
            },
            {
                "value": "2",
                "count": 3115
            },
            {
                "value": "4",
                "count": 7
            }
        ]
    },
    "current_page": 1,
    "total_pages": 952,
    "per_page": 10
}
```

## GET search/lapak

Search lapak thread.

### HTTP Request

`GET /search/lapak`

Parameter | Description
--------- | -----------
q|Query with optional filters. Valid filters are 'condition:new,second,refurbish',               'location:province_id1,province_id2', 'fid:forum_id,forum_id2','type:sold,buy,sell','donatur:true',               'price:10' - exact match,'price:10-100' - between,'price:10' - use less than mark,'price:10' - use greater               than mark, 'price:~100' - price between 90 to 110 (about 10%)
output|output format (JSON or XML)
include|valid value: facet
sort|Sort field: price, date, last_post, title, username, score



## GET search/group

Search Group.

### HTTP Request

`GET /search/group`

Parameter | Description
--------- | -----------
q|Query string to search
output|output format (JSON or XML)
include|valid value: facet



# Smiley



## GET smiley

Get smiley groups

### HTTP Request

`GET /v1/smiley_categories`

Parameter | Description
--------- | -----------




> Example response

```json
{
    "data": [
        {
            "category_id": 4,
            "category_name": "Only in Kaskus Smilies"
        },
        {
            "category_id": 3,
            "category_name": "Standart Smilies"
        },
        {
            "category_id": 5,
            "category_name": "Only in Kaskus Smilies(Small)"
        }
    ]
}
```

## GET smiley

Get smiley by category Id

### HTTP Request

`GET /v1/smiley/{categoryId}`

Parameter | Description
--------- | -----------
categoryId|Smiley category id



## GET smiley

Get smiley kaskus plus

### HTTP Request

`GET /v1/smiley_kaskus_plus`

Parameter | Description
--------- | -----------




> Example response

```json
{
    "data": [
        {
            "category_id": 6,
            "category_name": "Only for Kaskus Plus",
            "smilies": [
                {
                    "text": ":stiker1",
                    "imageUrl": "http:\/\/cdn.kaskusplayground.local\/images\/smilies\/smilies_fb5hwl0dmzi5.gif"
                }
            ]
        }
    ]
}
```

# Thread



## GET thread

Similar with /v1/forum_thread or /v1/fjb_thread or /v1/lapak. It returns thread detail regardless of its type. It is a little bit slower than specific thread endpoints.

### HTTP Request

`GET /v1/thread/{id}`

Parameter | Description
--------- | -----------
id|thread id
output|output format (JSON or XML)
page|number of post page
limit|limit number of post per page
field|post field that need to be filtered




> Example response

```json
{
    "thread": {
        "dateline": 1393843523,
        "first_post_id": "53145d43a1cb17ab258b4577",
        "forum_id": 21,
        "last_post": 1429610414,
        "last_post_id": "55361fae8ead0e93000041a7",
        "last_post_userid": 916848,
        "last_poster": "beta tester",
        "open": 0,
        "poll_id": 0,
        "post_userid": 4440622,
        "post_username": "KASKUS.Update",
        "prefix_id": "",
        "reply_count": 613,
        "short_url": "http:\/\/kask.us\/hxNDr",
        "sticky": 0,
        "title": "[Live Ngaskus] Ngomongin Cinta Bareng Para Pemeran Film Aku Cinta Kamu",
        "views": 34912,
        "visible": 1,
        "vote_num": 18,
        "vote_total": 67,
        "is_protected": false,
        "sundul_enabled": 1,
        "thread_id": "53145d43a1cb17ab258b4576",
        "hot_thread": 1,
        "thread_type": 10,
        "initial_prefix_id": "",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2012\/06\/12\/avatar4440622_4.gif",
        "usertitle": "Kaskus Official",
        "number_of_post": "307",
        "total_badge": 0,
        "enable_reputation": 1,
        "reputation": "53",
        "reputation_title": "akan menjadi terkenal",
        "is_donatur": false,
        "is_vsl": false,
        "reputation_box": 1
    },
    "total_post": 614,
    "current_page": 1,
    "total_page": 31,
    "per_page": 20,
    "posts": [
        {
            "pagetext": "[CENTER][FONT=\"Georgia\"][size=\"5\"][size=\"7\"][color=blue]Heellloooww Gan & Siiiss![\/color][\/size]\n:shakehand2 \n\n[QUOTE][CENTER][size=\"5\"][FONT=\"Georgia\"][size=\"7\"][color=red][B]UPDATE[\/B][\/color][\/size]\n:hn :hn :hn\n\nDan inilah para penanya terbaik Live Ngaskus bareng Piyu, Rio Dewanto dan Eriska Rein. \n\n[B]1. wqew\n\n2. R8486.Jr\n\n3. Dofar26\n\n4. cicimol\n\n5. defend\n\n6. dellahurahura\n\n7. GIML\n\n8. kemanajabole\n\n9. maulanfazry\n\n10. free1412[\/B]\n\n[color=orange][size=\"6\"]Selamat kepada pemenang![\/size][\/color]\n:selamat :selamat :selamat\n\nSeluruh pemenang berhak mendapatkan masing-masing 2 tiket film Aku Cinta Kamu yang bisa ditonton di seluruh bioskop 21. \n[B][color=red]Tiket bisa diambil di kantor KASKUS mulai hari Rabu, 12 Maret 2014 sampai Jumat, 14 Maret 2014 pukul 10.00 -18.00[\/color][\/B]\n[\/FONT][\/size][\/CENTER]\n\n[\/QUOTE]\n\n\n\n[QUOTE][CENTER][size=\"5\"][B]UPDATE[\/B]\n:hn :hn :hn\n\nLive Ngaskus lagi berlangsung nih Gan! Ayo tanya-tanya tentang film [B][color=red]Aku Cinta Kamu [\/color][\/B]ke Piyu, Rio Dewanto, dan Eriska Rein! Pertanyaan terbaik bakal dapet hadiah loh!\n:2thumbup\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305025508.jpg[\/img]\n[I]Asli, IGO ini bening banget Gan! [\/I]\n:matabelo\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305025514.jpg[\/img]\n[I]Piyu senyum-senyum nih liat komentar para Kaskuser[\/I]\n:ngakak\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305025521.jpg[\/img]\n[I]Kalau Rio serius nih jawab-in pertanyaan Agan-Agan[\/I]\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305025500.jpg[\/img]\n[I]Say Cheeseee[\/I][\/size][\/CENTER]\n[\/QUOTE]\n\n\n\nHooorrrreee!! Ketemu lagi di acaranya [color=blue]KAS[\/color][color=orange]KUS[\/color] yang paling interaktif, apalagi kalau bukan[color=red][size=\"7\"]Live Ngaskus[\/size][\/color]\n:selamat :selamat\n\n\nYayyyy!! Bulan Maret ini kita bakal kedatangan para pemeran film \n[size=\"7\"][color=magenta]Aku Cinta Kamu[\/color][\/size]\n:heart: :heart: :heart: :heart:\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/03\/4440622_20140303053824.jpg[\/img]\n\n[YOUTUBE]qtdmRlPPGfE[\/YOUTUBE]\n\n\nKetika cinta menyengat, berjuta rasa menjangkiti hati dan pikiran kita. Berbagai peristiwa besar dalam kehidupan, dipicu oleh satu kalimat singkat : [B]Aku Cinta Kamu[\/B]. Nah, berangkat dari 4 lagu cinta ciptaan seorang Piyu, dibuatlah 4 kisah dengan 4 genre menjadi sebuah film untuk mengenal cinta. Pokonya, it\u2019s all about love :heart: :heart: :heart:\n\n[SPOILER=Sinopsis Cerita 1 - Firasatku]Tentang Sita (Acha Septriasa) dan Randu (Rio Dewanto) yang mempersiapkan sebuah pesta pernikahan. Sita sebagai wedding organizer sangat perfectionist, dan menginginkan pernikahan paling sempurna. Sedangkan Randu, fotografer berjiwa seniman seakan cuek dengan persiapan Sita. Randu punya beribu alasan untuk menangguhkan foto prewed mereka. Hingga Sita mulai dipengaruhi firasatnya sendiri, kalau Randu berselingkuh dengan wanita lain bernama Rani (Fanny Fabriana). Hingga akhirnya Sita memergoki mereka. Sita dilema, apakah membatalkan pernikahannya atau mencoba ikhlas dan berfikir positif, mungkin Randu ingin menyelesaikan sejarah percintaannya dengan Rani sebelum memulai hidup bersamanya. \nHari pernikahan tiba, Sita dengan gaun cantik pernikahannya tidak bisa membendung air matanya. Dia lari dan Randu mengejarnya, hingga kecelakaan merenggut nyawa salah satu dari mereka, dan membuka mata bahwa firasat tidak selalu benar. \n[\/SPOILER]\n\n[SPOILER=Sinopsis Cerita 2 - Cinta Itu Adalah]Kim (Kim Kurniawan) seorang pemain bola yang sedang naik daun, bertetangga dengan Raisha (Eriska Rein) yang begitu terobsesi untuk selalu dekat dan melayani Kim, walaupun Kim menganggap Raisha hanya sahabat. \nSampai akhirnya Kim diterima di timnas. Raisha yang mempersiapkan pesta kejutan untuk Kim, menelan kekecewaan karena Kim merayakan dengan teman-temannya. Raisha menangis melihat begitu banyak wanita cantik berebutan foto dengan Kim, kesuksesan telah membawa Kim pergi jauh darinya.\nKim pun mulai latihan, tidak ada lagi Raisha yang selalu siap di pinggir lapangan untuk memberinya minum, tidak ada sepatu bola yang telah dibersihkan menunggunya. \nHingga sepulang latihan dengan bersepeda Kim ditabrak lari sebuah mobil, dan semua gelap. Kim tidak bisa melihat. Ketika semua mulai meninggalkannya, hanya Raisha yang telaten mendampinginya. \nYudith (Martina Tesela) perawat cantik di rumah sakit menyarankan Kim operasi kornea mata. Raisha marah dan menganggap Yudith hanya ingin memperkaya rumah sakit. Sejak itu Kim tidak kembali berobat, Yudith curiga dan mendatangi Kim. Raisha memergoki Yudith dan mencegahnya untuk membawa Kim. \n[\/SPOILER]\n\n\n[SPOILER=Sinopsis Cerita 3 - Sakit Hati]Gerry (Giorgino Abraham), SMA kelas 3 memiliki kekasih Lisa (Pevita Pearce). Mereka selalu bersama penuh keceriaan, Gerry selalu menyanyikan lagu ciptaannya untuk Lisa di sebuah bukit tempat favorit mereka. \nAkhir tahun ajaran membuat mereka berpisah karena beda perguruan tinggi. Lisa semakin larut dalam pergaulan metropolis, Lisa membohongi Gerry yang ngapel ke rumah kost Lisa hanya boleh sampai jam 9 malam. Padahal sepulang Gerry, Lisa berganti kostum dan melesat ke lantai disco dengan teman-temannya yang party-holic. Hingga akhirnya Gerry mengetahui ini, dengan motor yang diperoleh Gerry dengan bekerja di sebuah bengkel, ia mengikuti mobil teman-teman Lisa. Gerry tidak bisa menahan dirinya melihat Lisa dicium seorang lelaki. Tapi justru Lisa malah memilih lelaki itu, dan mengusir Gerry.\nSakit hati mengantar Gerry menjadi pencipta lagu yang sukses, di bukit kenangan mereka kembali bertemu. Lisa meminta maaf. Apakah Gerry masih punya ruang di hatinya untuk memaafkan Lisa?\n[\/SPOILER]\n\n[SPOILER=Sinopsis Cerita 4 - Jernih ]Tora (Dimas Anggara) dan Gofar (Gofar Hilman) adalah pedagang barang-barang KW di lapak yang selalu berurusan dengan razia yang dilakukan oleh Omar (Tri Wardoyo), si hamba hukum lebay. Saat mereka kabur dengan tas LV KW, mereka bertabrakan dengan Elena (Manohara Odelia) seorang wanita cantik dan elegan. Tas LV KW tertukar tas ori, sekaligus tabrakan itu menghempaskan hati Tora yang jatuh cinta ke Elena pada pandangan pertama. \nMereka terkejut mengetahui tas LV mereka tertukar dengan dokumen-dokumen yang tebal. Gofar ngamuk, baginya tas itu modal kerjanya, dan cewek itu adalah maling. Hingga HP mereka berbunyi, Elena menelepon Gofar karena ada kartu nama Gofar di kotak botol parfum KW yang mereka jual. Akhirnya dibuat janji pertukaran tas. Tora panik, sibuk dandan dan ingin tampil seganteng mungkin. Tanpa mereka ketahui, Elena adalah tunangan Haji Jo\u2019e (Joe P Project) pimpinan ormas kaya yang mirip mafia.\nAkankah Tora mendapatkan cinta Elena, yang memang sedang berusaha lepas dari Haji Jo\u2019e. Akankah Gofar kembali ke bisnisnya yang selalu kejar-kejaran dengan Omar, atau malah Omar berhasil menjernihkan kasus yang lebih besar? [\/SPOILER]\n\n:kiss\n\n[B][size=\"6\"]Siapa aja yang bakal dateng?? [\/size][\/B]\n\n[SPOILER=Nih, artis-artinya Gan][img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/03\/4440622_20140303053555.jpg[\/img]\n[I]Piyu[\/I]\n\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/03\/4440622_20140303053602.jpg[\/img]\n[I]Eriska Rein[\/I]\n\n\n[img]http:\/\/cdn.kaskus.com\/images\/2014\/03\/05\/4440622_20140305010113.jpg[\/img]\n[I]Rio Dewanto[\/I]\n[\/SPOILER]\n\n\nWah, mereka datang ber-enam Broo. Bakal seru dan heboh abis nih pastinya\n:matabelo\n\n\nKapan kapan kapan?? Mark your calendar yaa...\n\n[QUOTE][size=\"7\"][CENTER][B]Rabu, 5 Maret 2014\nPukul 14.00 - 16.00[\/B][\/CENTER][\/size][\/QUOTE]\n\nSo, udah siap mau live ngaskus bareng artis-artis kece ini?? Jangan lupa buat tulis pertanyaan-pertanyaan terbaik lo [URL=\"http:\/\/kask.us\/hxNDR\"][B]di sini[\/B][\/URL]\n\n\n[QUOTE][CENTER][size=\"5\"]10 orang yang beruntung akan mendapatkan masing-masing[B] 2 buah tiket [\/B]nonton film Aku Cinta Kamu yang bisa digunakan mulai hari Kamis, 6 Maret 2014 di seluruh bioskop 21.[\/B]\n\nNote: Tiket bisa diambil di kantor KASKUS hari Jumat, 7 Maret 2014[\/size][\/CENTER][\/QUOTE]\n\n\nFor more updates, bookmark thread ini ya Gann!\n\n\n\nCiaooo\n:ngacir :ngacir :ngacir \n[\/size][\/FONT][\/CENTER]",
            "text": "Heellloooww Gan & Siiiss!\n:shakehand2 \n\nUPDATE\n:hn :hn :hn\n\nDan inilah para penanya terbaik Live Ngaskus bareng Piyu, Rio Dewanto dan Eriska Rein. \n\n1. wqew\n\n2. R8486.Jr\n\n3. Dofar26\n\n4. cicimol\n\n5. defend\n\n6. dellahurahura\n\n7. GIML\n\n8. kemanajabole\n\n9. maulanfazry\n\n10. free1412\n\nSelamat kepada pemenang!\n:selamat :selamat :selamat\n\nSeluruh pemenang berhak mendapatkan masing-masing 2 tiket film Aku Cinta Kamu yang bisa ditonton di seluruh bioskop 21. \nTiket bisa diambil di kantor KASKUS mulai hari Rabu, 12 Maret 2014 sampai Jumat, 14 Maret 2014 pukul 10.00 -18.00\n\n\n\n\n\n\nUPDATE\n:hn :hn :hn\n\nLive Ngaskus lagi berlangsung nih Gan! Ayo tanya-tanya tentang film Aku Cinta Kamu ke Piyu, Rio Dewanto, dan Eriska Rein! Pertanyaan terbaik bakal dapet hadiah loh!\n:2thumbup\n\n\nAsli, IGO ini bening banget Gan! \n:matabelo\n\n\nPiyu senyum-senyum nih liat komentar para Kaskuser\n:ngakak\n\n\nKalau Rio serius nih jawab-in pertanyaan Agan-Agan\n\n\nSay Cheeseee\n\n\n\n\nHooorrrreee!! Ketemu lagi di acaranya KASKUS yang paling interaktif, apalagi kalau bukanLive Ngaskus\n:selamat :selamat\n\n\nYayyyy!! Bulan Maret ini kita bakal kedatangan para pemeran film \nAku Cinta Kamu\n:heart: :heart: :heart: :heart:\n\n\n\nqtdmRlPPGfE\n\n\nKetika cinta menyengat, berjuta rasa menjangkiti hati dan pikiran kita. Berbagai peristiwa besar dalam kehidupan, dipicu oleh satu kalimat singkat : Aku Cinta Kamu. Nah, berangkat dari 4 lagu cinta ciptaan seorang Piyu, dibuatlah 4 kisah dengan 4 genre menjadi sebuah film untuk mengenal cinta. Pokonya, it\u2019s all about love :heart: :heart: :heart:\n\nTentang Sita (Acha Septriasa) dan Randu (Rio Dewanto) yang mempersiapkan sebuah pesta pernikahan. Sita sebagai wedding organizer sangat perfectionist, dan menginginkan pernikahan paling sempurna. Sedangkan Randu, fotografer berjiwa seniman seakan cuek dengan persiapan Sita. Randu punya beribu alasan untuk menangguhkan foto prewed mereka. Hingga Sita mulai dipengaruhi firasatnya sendiri, kalau Randu berselingkuh dengan wanita lain bernama Rani (Fanny Fabriana). Hingga akhirnya Sita memergoki mereka. Sita dilema, apakah membatalkan pernikahannya atau mencoba ikhlas dan berfikir positif, mungkin Randu ingin menyelesaikan sejarah percintaannya dengan Rani sebelum memulai hidup bersamanya. \nHari pernikahan tiba, Sita dengan gaun cantik pernikahannya tidak bisa membendung air matanya. Dia lari dan Randu mengejarnya, hingga kecelakaan merenggut nyawa salah satu dari mereka, dan membuka mata bahwa firasat tidak selalu benar. \n\n\nKim (Kim Kurniawan) seorang pemain bola yang sedang naik daun, bertetangga dengan Raisha (Eriska Rein) yang begitu terobsesi untuk selalu dekat dan melayani Kim, walaupun Kim menganggap Raisha hanya sahabat. \nSampai akhirnya Kim diterima di timnas. Raisha yang mempersiapkan pesta kejutan untuk Kim, menelan kekecewaan karena Kim merayakan dengan teman-temannya. Raisha menangis melihat begitu banyak wanita cantik berebutan foto dengan Kim, kesuksesan telah membawa Kim pergi jauh darinya.\nKim pun mulai latihan, tidak ada lagi Raisha yang selalu siap di pinggir lapangan untuk memberinya minum, tidak ada sepatu bola yang telah dibersihkan menunggunya. \nHingga sepulang latihan dengan bersepeda Kim ditabrak lari sebuah mobil, dan semua gelap. Kim tidak bisa melihat. Ketika semua mulai meninggalkannya, hanya Raisha yang telaten mendampinginya. \nYudith (Martina Tesela) perawat cantik di rumah sakit menyarankan Kim operasi kornea mata. Raisha marah dan menganggap Yudith hanya ingin memperkaya rumah sakit. Sejak itu Kim tidak kembali berobat, Yudith curiga dan mendatangi Kim. Raisha memergoki Yudith dan mencegahnya untuk membawa Kim. \n\n\n\nGerry (Giorgino Abraham), SMA kelas 3 memiliki kekasih Lisa (Pevita Pearce). Mereka selalu bersama penuh keceriaan, Gerry selalu menyanyikan lagu ciptaannya untuk Lisa di sebuah bukit tempat favorit mereka. \nAkhir tahun ajaran membuat mereka berpisah karena beda perguruan tinggi. Lisa semakin larut dalam pergaulan metropolis, Lisa membohongi Gerry yang ngapel ke rumah kost Lisa hanya boleh sampai jam 9 malam. Padahal sepulang Gerry, Lisa berganti kostum dan melesat ke lantai disco dengan teman-temannya yang party-holic. Hingga akhirnya Gerry mengetahui ini, dengan motor yang diperoleh Gerry dengan bekerja di sebuah bengkel, ia mengikuti mobil teman-teman Lisa. Gerry tidak bisa menahan dirinya melihat Lisa dicium seorang lelaki. Tapi justru Lisa malah memilih lelaki itu, dan mengusir Gerry.\nSakit hati mengantar Gerry menjadi pencipta lagu yang sukses, di bukit kenangan mereka kembali bertemu. Lisa meminta maaf. Apakah Gerry masih punya ruang di hatinya untuk memaafkan Lisa?\n\n\nTora (Dimas Anggara) dan Gofar (Gofar Hilman) adalah pedagang barang-barang KW di lapak yang selalu berurusan dengan razia yang dilakukan oleh Omar (Tri Wardoyo), si hamba hukum lebay. Saat mereka kabur dengan tas LV KW, mereka bertabrakan dengan Elena (Manohara Odelia) seorang wanita cantik dan elegan. Tas LV KW tertukar tas ori, sekaligus tabrakan itu menghempaskan hati Tora yang jatuh cinta ke Elena pada pandangan pertama. \nMereka terkejut mengetahui tas LV mereka tertukar dengan dokumen-dokumen yang tebal. Gofar ngamuk, baginya tas itu modal kerjanya, dan cewek itu adalah maling. Hingga HP mereka berbunyi, Elena menelepon Gofar karena ada kartu nama Gofar di kotak botol parfum KW yang mereka jual. Akhirnya dibuat janji pertukaran tas. Tora panik, sibuk dandan dan ingin tampil seganteng mungkin. Tanpa mereka ketahui, Elena adalah tunangan Haji Jo\u2019e (Joe P Project) pimpinan ormas kaya yang mirip mafia.\nAkankah Tora mendapatkan cinta Elena, yang memang sedang berusaha lepas dari Haji Jo\u2019e. Akankah Gofar kembali ke bisnisnya yang selalu kejar-kejaran dengan Omar, atau malah Omar berhasil menjernihkan kasus yang lebih besar? \n\n:kiss\n\nSiapa aja yang bakal dateng?? \n\n\nPiyu\n\n\n\nEriska Rein\n\n\n\nRio Dewanto\n\n\n\nWah, mereka datang ber-enam Broo. Bakal seru dan heboh abis nih pastinya\n:matabelo\n\n\nKapan kapan kapan?? Mark your calendar yaa...\n\nRabu, 5 Maret 2014\nPukul 14.00 - 16.00\n\nSo, udah siap mau live ngaskus bareng artis-artis kece ini?? Jangan lupa buat tulis pertanyaan-pertanyaan terbaik lo di sini\n\n\n10 orang yang beruntung akan mendapatkan masing-masing 2 buah tiket nonton film Aku Cinta Kamu yang bisa digunakan mulai hari Kamis, 6 Maret 2014 di seluruh bioskop 21.\n\nNote: Tiket bisa diambil di kantor KASKUS hari Jumat, 7 Maret 2014\n\n\nFor more updates, bookmark thread ini ya Gann!\n\n\n\nCiaooo\n:ngacir :ngacir :ngacir"
        },
        {
            "pagetext": "[CENTER][FONT=\"Century Gothic\"]alhamdulilah menang \n\n[\/FONT][\/CENTER]",
            "text": "alhamdulilah menang"
        },
        {
            "pagetext": "Thread ini telah melebihi batas maksimal reply yang telah di tentukan. \n\t\t\t\n\t\t\t\t\t\t\t\t\t\t\tThread lanjutan dapat diakses di: [URL=\"http:\/\/aji.kaskus.dev\/thread\/54b389bc1ef4cc34060041a8\"]http:\/\/aji.kaskus.dev\/thread\/54b389bc1ef4cc34060041a8[\/URL]",
            "text": "Thread ini telah melebihi batas maksimal reply yang telah di tentukan. \n\t\t\t\n\t\t\t\t\t\t\t\t\t\t\tThread lanjutan dapat diakses di: http:\/\/aji.kaskus.dev\/thread\/54b389bc1ef4cc34060041a8"
        },
        {
            "pagetext": ";lkjlkjljlkjlkjl",
            "text": ";lkjlkjljlkjlkjl"
        },
        {
            "pagetext": "haloooo",
            "text": "haloooo"
        }
    ]
}
```

# Vm



## POST vm

Send visitor message to certain user.

### HTTP Request

`POST /vm/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id
output|output format (JSON or XML)



## DELETE vm

Delete visitor message to certain user.

### HTTP Request

`DELETE /vm/{vm_id}`

Parameter | Description
--------- | -----------
vm_id|Visitor Message id
output|output format (JSON or XML)



## GET vm

Get certain user's visitor messages. Pagination works here.

### HTTP Request

`GET /vm/{user_id}`

Parameter | Description
--------- | -----------
user_id|User id
output|output format (JSON or XML)




> Example response

```json
{
    "total": "26",
    "page": 1,
    "per_page": 10,
    "total_page": 3,
    "vm": [
        {
            "vmid": 42223558,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450432326,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223556,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450428890,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223554,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450428813,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223552,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450425299,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223550,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450424342,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223548,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450424297,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223546,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450424249,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223544,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450424204,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223542,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450424116,
            "pagetext": "13113231321",
            "messageread": "0",
            "decoded": "13113231321",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223540,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450422760,
            "pagetext": "1adaada",
            "messageread": "0",
            "decoded": "1adaada",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar11_70.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3295,
            "enable_reputation": 1,
            "reputation": 1774,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        }
    ]
}
```

## GET vm/conversation

Get certain two users' conversation in visitor messages.

### HTTP Request

`GET /vm/{user_id_1}/{user_id_2}`

Parameter | Description
--------- | -----------
user_id_1|User id
user_id_2|User id
output|output format (JSON or XML)



# Whoposted



## GET whoposted

Get list of user who reply post in certain thread

### HTTP Request

`GET /whoposted/{thread_id}`

Parameter | Description
--------- | -----------
thread_id|thread id
output|output format (JSON or XML)




> Example response

```json
{
    "users": [
        {
            "userid": 11,
            "username": "recca",
            "total_post": 11
        },
        {
            "userid": 3,
            "username": "admin",
            "total_post": 5
        }
    ],
    "total_post": 16
}
```