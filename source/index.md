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


## SDK

Kaskus SDK For PHP

This repository contains the open source PHP SDK that allows you to access Kaskus API from your PHP app.

This version of the Kaskus SDK for PHP requires
 
* PHP 5.4 or greater.
* Composer

Installation
------------

1. Require this library in your composer.json
2. [Composer](https://getcomposer.org/) is a prerequisite for using Kaskus Sdk for PHP. Install composer globally, then run `composer install` to install required files.
3. Get Consumer Key and Consumer Secret for your application.
4. Require `vendor/autoload.php` in your application.
5. Follow sample script for further usage

```json
{
  "require": {
    "kaskus/kaskus-php-sdk": "v0.2.0"
  }
}
```

Usage
-----

Minimal example:

```php
<?php

// skip these two lines if you use composer 
define('KASKUS_SDK_SRC_DIR', '/path/to/kaskus-sdk-for-php/src/Kaskus/');
require __DIR__ . '/path/to/kaskus-sdk-for-php/autoload.php';

// skip this line if you do not use composer
require 'vendor/autoload.php';

$consumerKey = 'YOUR_API_KEY';
$consumerSecret = 'YOUR_API_SECRET';

$client = new \Kaskus\KaskusClient($consumerKey, $consumerSecret);

try {
    $response = $client->get('v1/hot_threads');
    $forumList = $response->json();
    print_r($forumList);
} catch (\Kaskus\Exceptions\KaskusRequestException $exception) {
    // Kaskus Api returned an error
    
} catch (\Exception $exception) {
    // some other error occured
    
}

```

Login With Kaskus
-----------------

Use this [Oauth sample](https://github.com/kaskus/kaskus-php-sdk/blob/master/sample/oauth_sample.php)


Advance Usage
-------------

We use guzzle as HTTP Client, for further usage, read [Guzzle](http://guzzle.readthedocs.org/en/latest/)


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
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/03\/12\/avatar10793_14.gif",
        "usertitle": "Lorem ipsum dolor sit amet, nonummy ligula volutpat hac integer nonummy. Suspendisse ultricies, congue etiam tellus, erat libero, nulla eleifend, mauris pellentesque. Suspendisse integer praesent vel, integer gravida mauris, fringilla vehicula lacini",
        "number_of_post": 1046,
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
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/06\/15\/male.jpg",
        "usertitle": "Administrator",
        "number_of_post": 18,
        "enable_reputation": 0,
        "reputation": 0,
        "reputation_title": "disabled reputation",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2004\/09\/16\/avatar51917_7.gif",
            "usertitle": "Co-Admin Kaskus",
            "number_of_post": 15488,
            "enable_reputation": 1,
            "reputation": 356,
            "reputation_title": "is just really nice",
            "is_donatur": false,
            "reputation_box": 4
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
        "title": "test",
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
        "time_start": 1452655580,
        "time_end": 1452655580,
        "date_event": false
    },
    "event_calendar": [
        {
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "prefix_id": "",
            "meta_images": [],
            "event_id": "409",
            "thread_title": "Nonton Bareng Komunitas",
            "thread_link": "\/thread\/\/-",
            "date": 1409245200,
            "location": "Surabaya",
            "name": "awdaw",
            "phone": "dawdwafdsfdf",
            "sticky": "1",
            "thread_id": ""
        },
        {
            "dateline": 1262051358,
            "first_post_id": "000000000000000147966594",
            "forum_id": 21,
            "last_post": 1392991264,
            "last_post_id": "53075c20c3cb170c528b474f",
            "last_post_userid": 6464646,
            "last_poster": "elektroman",
            "open": 1,
            "poll_id": 0,
            "post_userid": 1164960,
            "post_username": "Kelincihilang",
            "prefix_id": "",
            "reply_count": 8616,
            "short_url": "http:\/\/kask.us\/gW2Zq",
            "sticky": "1",
            "title": "Sulap Matematika Untuk Agan yg mw Pamer",
            "views": 89914,
            "visible": 1,
            "vote_num": 107,
            "vote_total": 525,
            "thread_id": "000000000000000003022450",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "meta_images": [],
            "event_id": "514",
            "thread_title": "Sulap Matematika Untuk Agan yg mw Pamer",
            "thread_link": "\/thread\/000000000000000003022450\/sulap-matematika-untuk-agan-yg-mw-pamer",
            "date": 1398358800,
            "location": "Semarang",
            "name": "Sulap Super",
            "phone": "08123456789"
        },
        {
            "dateline": 1385862791,
            "first_post_id": "529a968759cb17ad18000053",
            "forum_id": 21,
            "last_post": 1386043019,
            "last_post_id": "529d568b1e0bc315560001cb",
            "last_post_userid": 1526848,
            "last_poster": "aviavsec",
            "meta_images": [
                "http:\/\/www.mobgenic.com\/wp-content\/uploads\/2012\/11\/lego-street-art-2-600x290.jpeg",
                "http:\/\/u.jimdo.com\/www15\/o\/s0b8d28d178da6ad6\/img\/i8bf832142e7d0523\/1315417487\/std\/image.jpg",
                "http:\/\/u.jimdo.com\/www15\/o\/s0b8d28d178da6ad6\/img\/iab66eac7edddb19b\/1315417424\/std\/image.jpg",
                "http:\/\/u.jimdo.com\/www15\/o\/s0b8d28d178da6ad6\/img\/i688d1963c219322d\/1315416888\/std\/image.jpg",
                "http:\/\/u.jimdo.com\/www15\/o\/s0b8d28d178da6ad6\/img\/icf01043212eaf214\/1329761908\/std\/image.jpg"
            ],
            "open": 1,
            "poll_id": 0,
            "post_userid": 4853883,
            "post_username": "ouranio",
            "prefix_id": "",
            "reply_count": 61,
            "short_url": "http:\/\/kask.us\/hoVvd",
            "sticky": "1",
            "title": "Lego Street Art yang Unik (Pictures Inside)",
            "views": 4008,
            "visible": 1,
            "vote_num": 3,
            "vote_total": 14,
            "thread_id": "529a968759cb17ad18000052",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "event_id": "408",
            "thread_title": "Thread Event Calendar",
            "thread_link": "\/thread\/529a968759cb17ad18000052\/event-calendar",
            "date": 1396198800,
            "location": "Jakarta",
            "name": "Event Calendar",
            "phone": "081298115950"
        },
        {
            "dateline": 1383190840,
            "first_post_id": "5271d1388ead0e5600692501",
            "forum_id": 21,
            "last_post": 1395727651,
            "last_post_id": "53311d23c721e63c45000019",
            "last_post_userid": 51917,
            "last_poster": "zenk",
            "open": 1,
            "poll_id": 0,
            "post_userid": 916848,
            "post_username": "beta tester",
            "prefix_id": "",
            "reply_count": 1,
            "short_url": "http:\/\/kask.us\/yP",
            "sticky": "1",
            "title": "Orang yang insyaAllah Masuk SURGA",
            "views": 127,
            "visible": 1,
            "vote_num": 1,
            "vote_total": 5,
            "thread_id": "5271d1388ead0e5600692500",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "meta_images": [],
            "event_id": "412",
            "thread_title": "Gathering Pembalap",
            "thread_link": "\/thread\/5271d1388ead0e5600692500\/orang-yang-insyaallah-masuk-surga",
            "date": 1396026000,
            "location": "jakarta",
            "name": "Kibi",
            "phone": "0856778"
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
            "sticky": "1",
            "title": "The Lounge Darurat Bot! Yang Nge-bot Laporin di Sini!",
            "views": 228461,
            "visible": 1,
            "vote_num": 540,
            "vote_total": 1818,
            "thread_id": "51697ac51ad719882b000009",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "meta_images": [],
            "event_id": "413",
            "thread_title": "The Lounge Darurat Pesta",
            "thread_link": "\/thread\/51697ac51ad719882b000009\/the-lounge-darurat-bot-yang-nge-bot-laporin-di-sini",
            "date": 1396026000,
            "location": "Bandung",
            "name": "awdwda",
            "phone": "wadad"
        },
        {
            "dateline": 1385872523,
            "first_post_id": "529abc8b108b46ce3000005d",
            "forum_id": 21,
            "last_post": 1394622235,
            "last_post_id": "53203f1bcd1c17b72400002b",
            "last_post_userid": 291720,
            "last_poster": "bemp",
            "open": 1,
            "poll_id": 0,
            "post_userid": 3887198,
            "post_username": "bilitonese",
            "prefix_id": "",
            "reply_count": 256,
            "short_url": "http:\/\/kask.us\/hoWct",
            "sticky": "1",
            "title": " Foto  Ini dapat Menjebak Mata Anda",
            "views": 10117,
            "visible": 1,
            "vote_num": 0,
            "vote_total": 0,
            "thread_id": "529abc8b108b46ce3000005c",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "meta_images": [],
            "event_id": "72",
            "thread_title": " Foto Ini dapat Menjebak Mata Anda",
            "thread_link": "\/thread\/529abc8b108b46ce3000005c\/foto--ini-dapat-menjebak-mata-anda",
            "date": 1392310800,
            "location": "Bandung",
            "name": "udin",
            "phone": "0812991"
        }
    ]
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
        "name": "THE LOUNGE",
        "description": "Tempat berbagi gosip, gambar dan video seru\/lucu\/unik.",
        "thread_count": "127930",
        "post_count": "108611120",
        "visible": "1",
        "last_thread_id": "56725fc18ead0ec2000041d1",
        "last_thread_title": "test",
        "last_thread_starter": "recca",
        "last_post_id": "56725fc18ead0ec2000041d0",
        "last_post": "1450336193",
        "last_poster": "recca",
        "service": "forum",
        "forum_icon": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    "subforum": [
        {
            "forum_id": "59",
            "name": "Gosip Nyok!",
            "description": "Gosip nyok, bareng Kaskusers.",
            "last_post_id": "54606f928ead0e46000041ab",
            "last_post": "1415606162",
            "last_poster": "superman.5",
            "last_thread_id": "54606f148ead0e45000041ac",
            "last_thread_title": "eh katanya rangga dah balik dari amrik lhoo",
            "service": "forum",
            "forum_icon": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
        },
        {
            "forum_id": "186",
            "name": "Lounge Pictures &amp; Video",
            "description": "Punya gambar bagus\/lucu\/unik yg mau di share? posting disini.",
            "last_post_id": "548a9217cdcf863a050041aa",
            "last_post": "1418367511",
            "last_poster": "admin",
            "last_thread_id": "53109f24bfcb17a1028b4576",
            "last_thread_title": "Mengintip Proses Pembuatan Piala Oscar",
            "service": "forum",
            "forum_icon": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
        }
    ],
    "top_thread": [
        {
            "dateline": 1413866430,
            "first_post_id": "5445e3bec721e68010000002",
            "forum_id": 21,
            "last_post": 1421210388,
            "last_post_id": "54b5f30fc721e66d09000040",
            "last_post_userid": 39291,
            "last_poster": "hansip",
            "meta_images": {
                "primary": ""
            },
            "open": 0,
            "poll_id": 67243,
            "post_userid": 5427,
            "post_username": "devil",
            "prefix_id": "",
            "reply_count": 79,
            "short_url": "http:\/\/kask.us\/cs7",
            "sticky": 0,
            "title": "tipe - tipe teman waktu presentasi di sekolah",
            "views": 943,
            "visible": 1,
            "vote_num": 6,
            "vote_total": 29,
            "ht_title": "tipe - tipe teman waktu presentasi di sekolah",
            "thread_id": "5445e3bec721e68010000001",
            "hot_thread": 2,
            "thread_type": 10,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/06\/19\/avatar5427_1.gif",
            "usertitle": "Administrator",
            "number_of_post": 188,
            "enable_reputation": 1,
            "reputation": 5,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "reputation_box": 1
        }
    ],
    "top_feature": [
        {
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
            "title": "Kepedulian Sosial Untuk Miranda",
            "views": 4597,
            "visible": 4,
            "vote_num": 8,
            "vote_total": 36,
            "section": "Hot Travels",
            "thread_id": "53157d55f8ca171c668b460c",
            "hot_thread": 1,
            "thread_type": 10,
            "initial_prefix_id": "",
            "meta_images": [],
            "image": "http:\/\/cdn.kaskusplayground.local\/img\/hotfeatured\/20141021015330.gif",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/11\/10\/avatar1196407_18.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 2158,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
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
            "title": "Kepedulian Sosial Untuk Miranda",
            "views": 4597,
            "visible": 4,
            "vote_num": 8,
            "vote_total": 36,
            "section": "Hot News",
            "thread_id": "53157d55f8ca171c668b460c",
            "hot_thread": 1,
            "thread_type": 10,
            "initial_prefix_id": "",
            "meta_images": [],
            "image": "http:\/\/cdn.kaskusplayground.local\/img\/hotfeatured\/20141021015417.gif",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/11\/10\/avatar1196407_18.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 2158,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
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
            "title": "Kepedulian Sosial Untuk Miranda",
            "views": 4597,
            "visible": 4,
            "vote_num": 8,
            "vote_total": 36,
            "section": "Hot Game",
            "thread_id": "53157d55f8ca171c668b460c",
            "hot_thread": 1,
            "thread_type": 10,
            "initial_prefix_id": "",
            "meta_images": [],
            "image": "http:\/\/cdn.kaskusplayground.local\/img\/hotfeatured\/20141021015428.gif",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/11\/10\/avatar1196407_18.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 2158,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "feature_id": "741",
            "forum_id": "21",
            "title": "ursuli",
            "type": "2",
            "url": "http:\/\/www.kaskus.co.id",
            "image": "http:\/\/cdn.kaskusplayground.local\/img\/hotfeatured\/top_feature_20141118041305.gif",
            "display_order": "4",
            "section": "ursuli",
            "link": "http:\/\/www.kaskus.co.id"
        }
    ],
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
            "views": 4654,
            "visible": 1,
            "vote_num": 2,
            "vote_total": 8,
            "thread_id": "529aaf183c118e5f4d0000a5",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "meta_images": [],
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/02\/11\/avatar689150_1.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 3772,
            "enable_reputation": 1,
            "reputation": 14,
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
            "views": 18,
            "visible": 1,
            "vote_num": 1,
            "vote_total": 4,
            "thread_id": "53eb4d13c721e6fe0d00001e",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/04\/23\/male.jpg",
            "usertitle": "newbie",
            "number_of_post": 30,
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
            "views": 228461,
            "visible": 1,
            "vote_num": 540,
            "vote_total": 1818,
            "thread_id": "51697ac51ad719882b000009",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "meta_images": [],
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2006\/11\/01\/avatar217057_3.gif",
            "usertitle": "Moderator Kaskus Away",
            "number_of_post": 20178,
            "enable_reputation": 0,
            "reputation": 0,
            "reputation_title": "disabled reputation",
            "is_donatur": false,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Test blacklist enchancement rules",
            "dateline": 1452572378,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 7,
            "post_username": "beta tester",
            "post_userid": 916848,
            "first_post_id": "56947edac6ec6084318b4568",
            "last_poster": "beta tester",
            "last_post_userid": 916848,
            "last_post": 1452572378,
            "last_post_id": "56947edac6ec6084318b4568",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "short_url": "http:\/\/kask.us\/hxQSy",
            "thread_id": "56947edac6ec6084318b4567",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/06\/08\/avatar916848_12.gif",
            "usertitle": "Administrator",
            "number_of_post": 2,
            "enable_reputation": 1,
            "reputation": 1000,
            "reputation_title": " has much to be proud of",
            "is_donatur": false,
            "reputation_box": 8
        },
        {
            "forum_id": 21,
            "title": "test",
            "dateline": 1452140325,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "beta tester",
            "post_userid": 916848,
            "first_post_id": "568de725c6ec6033288b4568",
            "last_poster": "beta tester",
            "last_post_userid": 916848,
            "last_post": 1452140325,
            "last_post_id": "568de725c6ec6033288b4568",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "",
            "short_url": "http:\/\/kask.us\/hxQQq",
            "thread_id": "568de725c6ec6033288b4567",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/06\/08\/avatar916848_12.gif",
            "usertitle": "Administrator",
            "number_of_post": 2,
            "enable_reputation": 1,
            "reputation": 1000,
            "reputation_title": " has much to be proud of",
            "is_donatur": false,
            "reputation_box": 8
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 7",
            "dateline": 1450417223,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 2,
            "views": 13,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "56739c4725ed60ee068b4571",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1451975716,
            "last_post_id": "568b6424498a1ba9048b4569",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "takut, indonesia, negatif, china, pasar, murah, gulung_tikar, acfta, perdagangan, industri",
            "short_url": "http:\/\/kask.us\/hxQMk",
            "thread_id": "56739c4725ed60ee068b4570",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Repost Test Hashtag 2",
            "dateline": 1450843035,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 19,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "567a1b9b25ed602d058b4570",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450843035,
            "last_post_id": "567a1b9b25ed602d058b4570",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "indonesia, acfta, sistem, perekonomian, industri, padat_karya",
            "short_url": "http:\/\/kask.us\/hxQMY",
            "thread_id": "567a1b9b25ed602d058b456f",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Repost Test Hashtag 4",
            "dateline": 1450782279,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 3,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "56792e4725ed6068058b4569",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450782279,
            "last_post_id": "56792e4725ed6068058b4569",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "short_url": "http:\/\/kask.us\/hxQMU",
            "tagsearch": "media, indonesia, batik, tekstil, apa, yah, galau, nich",
            "thread_id": "56792e4725ed6068058b4568",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Repost Test Hashtag 7",
            "dateline": 1450682352,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 5,
            "post_username": "admin",
            "post_userid": 3,
            "first_post_id": "5677a7f125ed60d6278b4568",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450682353,
            "last_post_id": "5677a7f125ed60d6278b4568",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "tagsearch": "takut, indonesia, negatif, china, pasar, murah, gulung_tikar, acfta, perdagangan, industri",
            "short_url": "http:\/\/kask.us\/hxQMu",
            "thread_id": "5677a7f125ed60d6278b4567",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "test",
            "dateline": 1450336193,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 1,
            "views": 6,
            "post_username": "recca",
            "post_userid": 11,
            "first_post_id": "56725fc18ead0ec2000041d0",
            "last_poster": "admin",
            "last_post_userid": 3,
            "last_post": 1450679902,
            "last_post_id": "56779e5e25ed6045118b4567",
            "sticky": 0,
            "prefix_id": "",
            "vote_num": 0,
            "vote_total": 0,
            "meta_images": [],
            "short_url": "http:\/\/kask.us\/hxQMs",
            "thread_id": "56725fc18ead0ec2000041d1",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
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
            "views": 4,
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
            "tagsearch": "kerja, produktif, pemerintah, buruh, perempuan, pelacur, rampok, human, trafficking, operasi",
            "short_url": "http:\/\/kask.us\/hxQMi",
            "thread_id": "56739c3825ed60ee068b456e",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 5",
            "dateline": 1450417187,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 5,
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
            "tagsearch": "indonesia, tarif, listrik, industri, produksi, importir, china, murah",
            "short_url": "http:\/\/kask.us\/hxQMg",
            "thread_id": "56739c2325ed60ee068b456c",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 4",
            "dateline": 1450417163,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 4,
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
            "tagsearch": "media, indonesia, batik, tekstil",
            "short_url": "http:\/\/kask.us\/hxQMe",
            "thread_id": "56739c0b25ed60ee068b456a",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 3",
            "dateline": 1450417097,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 4,
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
            "tagsearch": "skenario, pemerintah, industri, pengusaha, acfta, indonesia, china, media",
            "short_url": "http:\/\/kask.us\/hxQMc",
            "thread_id": "56739bc925ed60ed068b4569",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 2",
            "dateline": 1450417079,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 3,
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
            "tagsearch": "indonesia, acfta, sistem, perekonomian, industri, padat_karya",
            "short_url": "http:\/\/kask.us\/hxQMa",
            "thread_id": "56739bb725ed60ed068b4567",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "forum_id": 21,
            "title": "Test Hashtag 1",
            "dateline": 1450412106,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 3,
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
            "tagsearch": "naga, china, provokatif, ekonomi, grand, design, acfta, asean, indonesia",
            "short_url": "http:\/\/kask.us\/hxQL8",
            "thread_id": "5673884a25ed60ee068b4568",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
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
            "views": 2,
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
            "short_url": "http:\/\/kask.us\/hxQPk",
            "thread_id": "56725fba8ead0eeb2b0041cc",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "test",
            "dateline": 1450335989,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 2,
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
            "short_url": "http:\/\/kask.us\/hxQMK",
            "thread_id": "56725ef58ead0ec2000041ce",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "forum_id": 21,
            "title": "Ada Lagi Nih Promo Potongan Hotel Rp 100ribu, Gan!",
            "dateline": 1450322737,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 3,
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
            "short_url": "http:\/\/kask.us\/hxQOc",
            "thread_id": "56722b318ead0eeb2b0041c9",
            "thread_type": 10,
            "hot_thread": 0,
            "initial_prefix_id": "",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
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
        "name": "JOKES & CARTOON",
        "description": "Kumpulan humor dari Kaskuser, siap ngakak Gan!",
        "parent_id": "241",
        "parent_list": "9,241,-1",
        "child_list": "9,331,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "10",
        "name": "BERITA DAN POLITIK ",
        "description": "Forum untuk berdiskusi dan berbagi berita dari dalam maupun luar negeri. Beragam topik dihadirkan, mulai dari ideologi, politik, ekonomi, sosial dan budaya.",
        "parent_id": "241",
        "parent_list": "10,241,-1",
        "child_list": "10,250,621,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-10.png"
    },
    {
        "forum_id": "11",
        "name": "MOVIES",
        "description": "Forum penggemar film, simak info terbaru seputar dunia perfilman, serial TV, sinetron hingga miniseri favorit.",
        "parent_id": "241",
        "parent_list": "11,241,-1",
        "child_list": "11,382,171,-1",
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
        "name": "DISTURBING PICTURE",
        "description": "Watchout!",
        "parent_id": "241",
        "parent_list": "15,241,-1",
        "child_list": "15,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "18",
        "name": "CAN YOU SOLVE THIS GAME?",
        "description": "Punya tebak-tebakan, teka-teki atau permainan seru? Yuk, gabung disini!",
        "parent_id": "241",
        "parent_list": "18,241,-1",
        "child_list": "18,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "19",
        "name": "COMPUTER STUFF 2",
        "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang komputer dan internet.",
        "parent_id": "241",
        "parent_list": "19,241,-1",
        "child_list": "19,65,243,557,183,397,13,443,442,176,383,568,569,14,391,419,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "21",
        "name": "THE LOUNGE",
        "description": "Tempat berbagi gosip, gambar dan video seru\/lucu\/unik.",
        "parent_id": "241",
        "parent_list": "21,241,-1",
        "child_list": "21,59,186,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    {
        "forum_id": "22",
        "name": "Buat Latihan Posting",
        "description": "Mau latihan membuat thread di Kaskus? Silakan mampir disini!",
        "parent_id": "103",
        "parent_list": "22,103,241,-1",
        "child_list": "22,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
    },
    {
        "forum_id": "23",
        "name": "SUPRANATURAL",
        "description": "Penggemar Supranatural, Budaya dan Spiritual gabung disini",
        "parent_id": "241",
        "parent_list": "23,241,-1",
        "child_list": "23,389,173,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "27",
        "name": "Arsip Forum",
        "description": "Kumpulan pengumuman + sticky notes lama (sejak tahun 2000).",
        "parent_id": "103",
        "parent_list": "27,103,241,-1",
        "child_list": "27,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
    },
    {
        "forum_id": "28",
        "name": "OTOMOTIF",
        "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang dunia otomotif. Simak info\/tren otomotif terbaru hingga tips dan trik seputar perawatan kendaraan anda.",
        "parent_id": "241",
        "parent_list": "28,241,-1",
        "child_list": "28,112,570,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "29",
        "name": "COOKING & RESTO GUIDE",
        "description": "Penggemar masak-memasak dan berburu kuliner seru gabung disini!",
        "parent_id": "241",
        "parent_list": "29,241,-1",
        "child_list": "29,62,248,60,63,61,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "30",
        "name": "BISNIS",
        "description": "Forum untuk berdiskusi tentang karir, dunia kerja dan wirausaha. Dapatkan juga informasi seputar lowongan kerja, peluang kerjasama dan investasi.",
        "parent_id": "241",
        "parent_list": "30,241,-1",
        "child_list": "30,546,277,466,279,467,469,468,278,472,572,571,471,280,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "31",
        "name": "Kritik, Saran & Pertanyaan seputar Kaskus",
        "description": "Tempat menampung kritik, saran dan request feature Kaskus ke moderator forum atau admin. Posting selain tiga kategori diatas akan dihapus.",
        "parent_id": "103",
        "parent_list": "31,103,241,-1",
        "child_list": "31,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
    },
    {
        "forum_id": "32",
        "name": "HEWAN PELIHARAAN",
        "description": "Forum diskusi untuk penggemar dan pemilik hewan .",
        "parent_id": "241",
        "parent_list": "32,241,-1",
        "child_list": "32,124,127,123,125,126,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "34",
        "name": "ALL ABOUT DESIGN",
        "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang desain (desain grafis, desain website, desain interior dsb) termasuk tutorial, tips dan trik",
        "parent_id": "241",
        "parent_list": "34,241,-1",
        "child_list": "34,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "35",
        "name": "SPORTS",
        "description": "Penggemar olahraga gabung disini!",
        "parent_id": "241",
        "parent_list": "35,241,-1",
        "child_list": "35,187,440,276,332,144,545,538,539,104,565,537,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "36",
        "name": "HANDPHONE & PDA",
        "description": "Tempat diskusi dan berbagi seputar handphone dan PDA. Mulai dari tren terbaru, tips dan trik, komparasi produk, games dan aplikasi hingga konsultasi sebelum membeli.",
        "parent_id": "241",
        "parent_list": "36,241,-1",
        "child_list": "36,577,623,307,415,413,417,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "37",
        "name": "Ragnarok Online",
        "description": "MMORPG Community.",
        "parent_id": "100",
        "parent_list": "37,100,44,241,-1",
        "child_list": "37,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-100.png"
    },
    {
        "forum_id": "38",
        "name": "Web-based Games",
        "description": "Semua tentang web-based games.",
        "parent_id": "44",
        "parent_list": "38,44,241,-1",
        "child_list": "38,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
    },
    {
        "forum_id": "44",
        "name": "GAMES",
        "description": "Penggemar game, gabung disini!",
        "parent_id": "241",
        "parent_list": "44,241,-1",
        "child_list": "44,119,100,37,528,38,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "54",
        "name": "PHOTOGRAPHY",
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
        "description": "Gosip nyok, bareng Kaskusers.",
        "parent_id": "21",
        "parent_list": "59,21,241,-1",
        "child_list": "59,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    {
        "forum_id": "65",
        "name": "Linux dan OS Selain Microsoft & Mac",
        "description": "Tempat diskusi seputar sistem operasi Unix, Linux, dan sistem operasi lainnya (diluar produksi Microsoft & Mac).",
        "parent_id": "19",
        "parent_list": "65,19,241,-1",
        "child_list": "65,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "72",
        "name": "REGIONAL",
        "description": "Temukan Kaskuser di wilayahmu. Tinggal atau pernah tinggal di wilayah tertentu? Yuk, ngumpul bareng dan bagi info atau pengalamanmu.",
        "parent_id": "-1",
        "parent_list": "72,-1",
        "child_list": "72,592,617,83,76,421,425,96,423,109,115,108,540,90,77,477,74,384,79,106,80,475,157,82,85,129,476,73,463,427,458,89,164,405,107,412,407,78,585,457,181,564,111,160,402,84,459,167,587,567,555,403,452,411,133,583,92,461,162,146,385,91,462,584,561,170,179,166,460,161,97,543,586,548,398,145,93,156,81,117,158,194,478,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-72.png"
    },
    {
        "forum_id": "73",
        "name": "INDONESIA",
        "description": "",
        "parent_id": "72",
        "parent_list": "73,72,-1",
        "child_list": "73,463,427,458,89,164,405,107,412,407,78,585,457,181,564,111,160,402,84,459,167,587,567,555,403,452,411,133,583,92,461,162,146,385,91,462,584,561,170,179,166,460,161,97,543,586,548,398,145,93,156,81,117,-1",
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
        "description": "Khusus bagi siapa saja yang berniat mempromosikan lagu, album atau band untuk direview Kaskuser.  Review murni hasil tulisan sendiri, bukan copas dari situs lain.",
        "parent_id": "33",
        "parent_list": "87,33,241,-1",
        "child_list": "87,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "88",
        "name": "Help, Tips & Tutorial",
        "description": "Forum berbagi ilmu seputar download techniques, audio processing, mixing, musical instruments, dll.",
        "parent_id": "33",
        "parent_list": "88,33,241,-1",
        "child_list": "88,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "98",
        "name": "OUTDOOR ADVENTURE & NATURE CLUBS",
        "description": "Pecinta alam, para petualang, pecinta kegiatan outdoor gabung disini!",
        "parent_id": "241",
        "parent_list": "98,241,-1",
        "child_list": "98,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "100",
        "name": "Online Games",
        "description": "Semua tentang online games.",
        "parent_id": "44",
        "parent_list": "100,44,241,-1",
        "child_list": "100,37,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
    },
    {
        "forum_id": "103",
        "name": "WELCOME TO KASKUS",
        "description": "Mau tahu lebih banyak tentang Kaskus? Mampir disini!",
        "parent_id": "241",
        "parent_list": "103,241,-1",
        "child_list": "103,27,22,177,31,238,-1",
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
        "forum_id": "112",
        "name": "Kendaraan Roda 2",
        "description": "Pembahasan tentang kendaraan ber-roda dua (motor) dari semua brand.",
        "parent_id": "28",
        "parent_list": "112,28,241,-1",
        "child_list": "112,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-28.png"
    },
    {
        "forum_id": "119",
        "name": "Console & Handheld Games",
        "description": "Xbox, Xbox 360, PS2, PS3, GameCube, GBA\/DS, Gizmondo, Ngage, PSP.",
        "parent_id": "44",
        "parent_list": "119,44,241,-1",
        "child_list": "119,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
    },
    {
        "forum_id": "123",
        "name": "Mamalia",
        "description": "Khusus membahas mamalia (Anjing, Kucing, Hamster, Macan, Beruang, Tupai).",
        "parent_id": "32",
        "parent_list": "123,32,241,-1",
        "child_list": "123,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "124",
        "name": "Burung",
        "description": "Khusus membahas unggas dan burung.",
        "parent_id": "32",
        "parent_list": "124,32,241,-1",
        "child_list": "124,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "125",
        "name": "Reptil",
        "description": "Khusus membahas reptil.",
        "parent_id": "32",
        "parent_list": "125,32,241,-1",
        "child_list": "125,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "126",
        "name": "Saltwater Fish",
        "description": "Khusus membahas ikan laut.",
        "parent_id": "32",
        "parent_list": "126,32,241,-1",
        "child_list": "126,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-32.png"
    },
    {
        "forum_id": "127",
        "name": "Freshwater Fish",
        "description": "Khusus membahas ikan air tawar.",
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
        "forum_id": "137",
        "name": "Music Corner",
        "description": "Punya rekaman lagu oke? Solo atau dari band pribadimu? Yuk berbagi link (MP3, lirik, video klip) untuk direview Kaskuser.",
        "parent_id": "33",
        "parent_list": "137,33,241,-1",
        "child_list": "137,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "140",
        "name": "Militer",
        "description": "Tempat diskusi dan mempelajari teknologi alat-alat militer, strategi & sejarah kemiliteran baik dalam maupun luar negeri.",
        "parent_id": "575",
        "parent_list": "140,575,241,-1",
        "child_list": "140,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-575.png"
    },
    {
        "forum_id": "144",
        "name": "Martial Arts",
        "description": "Tempat diskusi para praktisi beladiri. Berbagi  informasi tentang ilmu beladiri, tangan kosong mapun bersenjata, berasal dari dalam dan luar negeri, modern dan tradisional.",
        "parent_id": "35",
        "parent_list": "144,35,241,-1",
        "child_list": "144,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
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
        "forum_id": "157",
        "name": "EROPA",
        "description": "",
        "parent_id": "72",
        "parent_list": "157,72,-1",
        "child_list": "157,82,85,129,476,-1",
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
        "description": "Hal-hal spiritual seperti meditasi, teknik relaksasi, dan pencerahan (tidak termasuk ilmu-ilmu seperti pelet, pengasihan, santet, penampakan makhluk halus).",
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
        "description": "Subforum khusus untuk para donatur. Postingan hanya bisa dilihat oleh donatur.",
        "parent_id": "103",
        "parent_list": "177,103,241,-1",
        "child_list": "177,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-103.png"
    },
    {
        "forum_id": "186",
        "name": "Lounge Pictures & Video",
        "description": "Punya gambar bagus\/lucu\/unik yg mau di share? posting disini.",
        "parent_id": "21",
        "parent_list": "186,21,241,-1",
        "child_list": "186,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    {
        "forum_id": "187",
        "name": "Brasil 2014",
        "description": "Tempat diskusi Piala Dunia Brasil 2014",
        "parent_id": "35",
        "parent_list": "187,35,241,-1",
        "child_list": "187,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "188",
        "name": "SURAT PEMBACA",
        "description": "Tempat Kaskuser berbagi keluh kesah seputar pelayanan publik atau produk tertentu. Sarana ini dibuat untuk memberi masukan untuk pelayanan yang lebih baik (bukan sekedar makian\/curhat dan ajakan untuk menjatuhkan kredibilitas).",
        "parent_id": "241",
        "parent_list": "188,241,-1",
        "child_list": "188,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "191",
        "name": "DEBATE CLUB",
        "description": "Beda pendapat? Silakan gabung di forum debat !",
        "parent_id": "241",
        "parent_list": "191,241,-1",
        "child_list": "191,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "193",
        "name": "WEDDING & FAMILY",
        "description": "Forum untuk berdiskusi dan berbagi informasi seputar pernikahan (daftar persiapan, artikel terkait) dan keluarga (hubungan pria-wanita, artikel keluarga, anak, cara mendidik anak).",
        "parent_id": "241",
        "parent_list": "193,241,-1",
        "child_list": "193,429,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "195",
        "name": "Elektronik",
        "description": "Jual beli beragam jenis barang elektronik",
        "parent_id": "25",
        "parent_list": "195,25,-1",
        "child_list": "195,313,255,254,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
    },
    {
        "forum_id": "196",
        "name": "Fashion & Mode",
        "description": "Jual beli barang fashion untuk pria dan wanita",
        "parent_id": "25",
        "parent_list": "196,25,-1",
        "child_list": "196,216,451,450,302,449,599,600,215,257,310,311,-1",
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
        "child_list": "202,269,268,602,-1",
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
        "name": "Handphone & PDA",
        "description": "Jual beli Handphone dan PDA",
        "parent_id": "25",
        "parent_list": "210,25,-1",
        "child_list": "210,527,574,381,573,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-25.png"
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
        "child_list": "227,264,594,-1",
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
        "forum_id": "236",
        "name": "Fitness & Muscle Building",
        "description": "Diskusi dan berbagi informasi tentang cara meningkatkan massa, kekuatan, performa dan kekencangan otot dari tingkat pemula, lanjutan sampai tingkat atlet untuk body fitness.",
        "parent_id": "558",
        "parent_list": "236,558,241,-1",
        "child_list": "236,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
    },
    {
        "forum_id": "239",
        "name": "KASKUS CORNER",
        "description": "Portal info Kaskus. Simak info terbaru seputar kegiatan-kegiatan yang diselenggarakan Kaskus dan melibatkan Kaskuser, seperti gathering, seminar, bakti sosial dan promo. Intip juga siapa saja sih selebriti yang ngaskus.",
        "parent_id": "241",
        "parent_list": "239,241,-1",
        "child_list": "239,240,549,473,435,263,479,480,485,481,484,486,482,483,542,488,490,489,487,619,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "240",
        "name": "KASKUS PEDULI",
        "description": "Pingin tau berbagai kegiatan bakti sosial yang diselenggarakan oleh Kaskus bersama dengan Kaskuser? Masuk kesini aja gan! Jangan sampai ketinggalan....",
        "parent_id": "239",
        "parent_list": "240,239,241,-1",
        "child_list": "240,549,473,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
    },
    {
        "forum_id": "241",
        "name": "FORUM",
        "description": "Tempat kaskuser berdiskusi dan berbagi informasi, ide, gosip, tips atau pengalaman tentang beragam topik. Mulai berita terkini, tren, gaya hidup, minat, hobi, curhatan sampai komunitas-komunitas menarik.",
        "parent_id": "-1",
        "parent_list": "241,-1",
        "child_list": "241,239,240,549,473,435,263,479,480,485,481,484,486,482,483,542,488,490,489,487,619,34,26,244,10,250,621,30,546,277,466,279,467,469,468,278,472,572,571,471,280,622,18,19,65,243,557,183,397,13,443,442,176,383,568,569,14,391,419,29,62,248,60,63,61,191,15,67,66,247,246,113,464,465,474,558,274,236,560,559,281,282,44,119,100,37,528,38,39,114,105,36,577,623,307,415,413,417,94,16,49,50,51,32,124,127,123,125,126,392,591,581,395,393,580,394,387,388,9,331,24,306,249,275,575,576,140,491,70,252,253,251,11,382,171,33,88,58,137,386,87,541,28,112,570,98,54,309,35,187,440,276,332,144,545,538,539,104,565,537,23,389,173,188,192,578,234,579,21,59,186,235,437,439,193,429,103,27,22,177,31,238,544,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image--1.png"
    },
    {
        "forum_id": "243",
        "name": "Hardware Computer",
        "description": "Tempat diskusi seputar computer hardware: updates, problems, drivers, peripheral, performance, upgrade, overclocking, showcase dan konsultasi sebelum membeli.",
        "parent_id": "19",
        "parent_list": "243,19,241,-1",
        "child_list": "243,557,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
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
        "description": "Diskusi dan berbagi informasi tentang kandungan nutrisi dalam makanan, cara sehat menurunkan berat badan termasuk mencari solusi untuk mencegah kolesterol, diabetes, dan berbagai penyakit lainnya.",
        "parent_id": "558",
        "parent_list": "274,558,241,-1",
        "child_list": "274,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
    },
    {
        "forum_id": "276",
        "name": "Grappling",
        "description": "Tempat diskusi para pecinta balap, termasuk balap bermesin atau tidak. Berbagi  informasi tentang dunia balap dari dalam dan luar negeri.",
        "parent_id": "35",
        "parent_list": "276,35,241,-1",
        "child_list": "276,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-35.png"
    },
    {
        "forum_id": "279",
        "name": "Forex\/Option\/Saham & Derivatifnya",
        "description": "Tempat berbagi dan belajar teknikal, fundamental dan psikologi trade forex, option, saham dan derivatif-nya. Pemula dan pakar silakan gabung!",
        "parent_id": "30",
        "parent_list": "279,30,241,-1",
        "child_list": "279,467,469,468,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
    },
    {
        "forum_id": "281",
        "name": "GADGET & GIZMO",
        "description": "Tempat diskusi seputar gadget. Simak tren dan perkembangan terbaru seputar gadget hingga ulasan tentang gadget tertentu.",
        "parent_id": "241",
        "parent_list": "281,241,-1",
        "child_list": "281,282,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "282",
        "name": "Audio & Video",
        "description": "Khusus membahas audio video.",
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
        "forum_id": "307",
        "name": "BlackBerry Corner",
        "description": "Diskusi khusus Blackberry.",
        "parent_id": "36",
        "parent_list": "307,36,241,-1",
        "child_list": "307,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
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
        "forum_id": "331",
        "name": "Pictures",
        "description": "Kumpulan gambar lucu.",
        "parent_id": "9",
        "parent_list": "331,9,241,-1",
        "child_list": "331,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-9.png"
    },
    {
        "forum_id": "332",
        "name": "Racing \/ Balap",
        "description": "Komunitas balap mania. Tempat berdiskusi dan saling bertukar informasi dunia balap dari dalam atau luar negeri. Termasuk balap bermesin maupun yang tidak menggunakan mesin.",
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
        "name": "Kaskus Theater",
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
        "description": "Tempat diskusi dan berbagi informasi tentang produk Macintosh, hardware & software.",
        "parent_id": "19",
        "parent_list": "383,19,241,-1",
        "child_list": "383,568,569,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-19.png"
    },
    {
        "forum_id": "386",
        "name": "Music Event",
        "description": "Forum berbagi info seputar event musik termasuk pengalaman Kaskuser setelah menonton event tersebut (baik gigs report band Indie maupun musisi mainstream).",
        "parent_id": "33",
        "parent_list": "386,33,241,-1",
        "child_list": "386,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-33.png"
    },
    {
        "forum_id": "387",
        "name": "ILMU MARKETING",
        "description": "Tempat diskusi seputar dunia marketing, keilmuan maupun penerapan.",
        "parent_id": "241",
        "parent_list": "387,241,-1",
        "child_list": "387,388,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "391",
        "name": "REQUEST @ CCPB",
        "description": "Request Windows based Applications here",
        "parent_id": "14",
        "parent_list": "391,14,19,241,-1",
        "child_list": "391,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-14.png"
    },
    {
        "forum_id": "392",
        "name": "HOBBY & COMMUNITY",
        "description": "Forum diskusi beragam komunitas dan pecinta hobi.",
        "parent_id": "241",
        "parent_list": "392,241,-1",
        "child_list": "392,591,581,395,393,580,394,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "393",
        "name": "Pisau",
        "description": "Tempat diskusi dan berbagi tentang pisau secara umum : pisau lipat, fix blades, pedang, dan peralatan lain yang berhubungan dengan pisau.",
        "parent_id": "392",
        "parent_list": "393,392,241,-1",
        "child_list": "393,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "394",
        "name": "Sepeda",
        "description": "Penikmat dan pemerhati Sepeda di Indonesia gabung disini!",
        "parent_id": "392",
        "parent_list": "394,392,241,-1",
        "child_list": "394,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "395",
        "name": "Mancing",
        "description": "Tempat diskusi dan berbagi tips, trik, tackle serta pengalaman seputar hobi memancing.",
        "parent_id": "392",
        "parent_list": "395,392,241,-1",
        "child_list": "395,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "397",
        "name": "ISP",
        "description": "Diskusi Penyedia Layanan Internet di Indonesia.",
        "parent_id": "183",
        "parent_list": "397,183,19,241,-1",
        "child_list": "397,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-183.png"
    },
    {
        "forum_id": "413",
        "name": "Mobile Phone",
        "description": "Java, Symbian, GSM, CDMA, Dual GSM\/CDMA, Apple",
        "parent_id": "36",
        "parent_list": "413,36,241,-1",
        "child_list": "413,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
    },
    {
        "forum_id": "415",
        "name": "PDA & PDA Phone",
        "description": "WM, Palm, Android",
        "parent_id": "36",
        "parent_list": "415,36,241,-1",
        "child_list": "415,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-36.png"
    },
    {
        "forum_id": "417",
        "name": "Operator CDMA dan GSM",
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
        "description": "Sharing ebooks & tutorial Computer Stuff Only",
        "parent_id": "14",
        "parent_list": "419,14,19,241,-1",
        "child_list": "419,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-14.png"
    },
    {
        "forum_id": "429",
        "name": "Kids & Parenting",
        "description": "Diskusi tentang anak dan cara mendidik anak.",
        "parent_id": "193",
        "parent_list": "429,193,241,-1",
        "child_list": "429,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-193.png"
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
        "description": "Templates & Scripts.",
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
        "forum_id": "449",
        "name": "Kaos, Polo Shirt",
        "description": "Kaos dan polo shirt",
        "parent_id": "196",
        "parent_list": "449,196,25,-1",
        "child_list": "449,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-196.png"
    },
    {
        "forum_id": "471",
        "name": "The Online Business new",
        "description": "Diskusi segala bentuk bisnis online dan perkembangannya. Dilarang promosi disini.",
        "parent_id": "30",
        "parent_list": "471,30,241,-1",
        "child_list": "471,280,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-30.png"
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
        "forum_id": "479",
        "name": "CINTA INDONESIAKU",
        "description": "Tunjukin seberapa besar Cinta Loe untuk Indonesia.",
        "parent_id": "239",
        "parent_list": "479,239,241,-1",
        "child_list": "479,480,485,481,484,486,482,483,542,488,490,489,487,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-239.png"
    },
    {
        "forum_id": "480",
        "name": "Arsitektur",
        "description": "",
        "parent_id": "479",
        "parent_list": "480,479,239,241,-1",
        "child_list": "480,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-479.png"
    },
    {
        "forum_id": "491",
        "name": "Mobile Broadband",
        "description": "Ingin diskusi mengenai wireless high-speed internet access via modem portable, telepon atau perangkat lainnya? Gabung disini!",
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
        "description": "Semua tentang PC games.",
        "parent_id": "44",
        "parent_list": "528,44,241,-1",
        "child_list": "528,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-44.png"
    },
    {
        "forum_id": "537",
        "name": "Sport Games",
        "description": "Berbagi game olahraga seru !",
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
        "description": "",
        "parent_id": "538",
        "parent_list": "539,538,35,241,-1",
        "child_list": "539,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-538.png"
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
        "forum_id": "557",
        "name": "Hardware Review Lab",
        "description": "",
        "parent_id": "243",
        "parent_list": "557,243,19,241,-1",
        "child_list": "557,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-243.png"
    },
    {
        "forum_id": "558",
        "name": "FIT & HEALTHY LIFESTYLE",
        "description": "Tempat diskusi seputar gaya hidup sehat. Simak beragam pengetahuan tentang diet dan nutrisi, fitness dan muscle building, metode olahraga untuk keseimbangan jiwa, raga dan pikiran hingga cara menghentikan ketergantungan terhadap rokok dan obat.",
        "parent_id": "241",
        "parent_list": "558,241,-1",
        "child_list": "558,274,236,560,559,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
    },
    {
        "forum_id": "559",
        "name": "Quit Smoking, Avoid Drugs",
        "description": "Diskusi dan berbagi informasi tentang cara mengubah pemikiran, langkah dan dukungan untuk berhenti merokok serta menjaga kesehatan tanpa obat-obatan terlarang",
        "parent_id": "558",
        "parent_list": "559,558,241,-1",
        "child_list": "559,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
    },
    {
        "forum_id": "560",
        "name": "Mind, Body & Soul",
        "description": "Diskusi dan berbagi informasi tentang metode olahraga untuk keseimbangan jiwa, raga dan pikiran, seperti yoga dan pilates.",
        "parent_id": "558",
        "parent_list": "560,558,241,-1",
        "child_list": "560,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-558.png"
    },
    {
        "forum_id": "565",
        "name": "Brasil 2014",
        "description": "Forum diskusi Piala Dunia 2014 Brasil",
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
        "forum_id": "591",
        "name": "Jam",
        "description": "",
        "parent_id": "392",
        "parent_list": "591,392,241,-1",
        "child_list": "591,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-392.png"
    },
    {
        "forum_id": "594",
        "name": "Komik",
        "description": "Komik",
        "parent_id": "227",
        "parent_list": "594,227,25,-1",
        "child_list": "594,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-227.png"
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
        "forum_id": "622",
        "name": "BUKU",
        "description": "Forum untuk berdiskusi tentang karir, dunia kerja dan wirausaha. Dapatkan juga informasi seputar lowongan kerja, peluang kerjasama dan investasi.",
        "parent_id": "241",
        "parent_list": "622,241,-1",
        "child_list": "622,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-241.png"
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
        "description": "Gosip nyok, bareng Kaskusers.",
        "parent_id": "21",
        "parent_list": "59,21,241,-1",
        "child_list": "59,-1",
        "visible": "1",
        "icon_url": "http:\/\/cdn.kaskusplayground.local\/ficon\/image-21.png"
    },
    {
        "forum_id": "186",
        "name": "Lounge Pictures & Video",
        "description": "Punya gambar bagus\/lucu\/unik yg mau di share? posting disini.",
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
                    "forum_id": "29",
                    "name": "COOKING & RESTO GUIDE",
                    "description": "Penggemar masak-memasak dan berburu kuliner seru gabung disini!",
                    "display_order": "70",
                    "visible": "1"
                },
                {
                    "forum_id": "558",
                    "name": "FIT & HEALTHY LIFESTYLE",
                    "description": "Tempat diskusi seputar gaya hidup sehat. Simak beragam pengetahuan tentang diet dan nutrisi, fitness dan muscle building, metode olahraga untuk keseimbangan jiwa, raga dan pikiran hingga cara menghentikan ketergantungan terhadap rokok dan obat.",
                    "display_order": "130",
                    "visible": "1"
                },
                {
                    "forum_id": "94",
                    "name": "HEALTH & MEDICAL",
                    "description": "Forum diskusi seputar dunia pengobatan, baik pengobatan modern maupun alternatif\/tradisional. Silakan bergabung untuk konsultasi atau berbagi pengalaman seputar pengobatan.",
                    "display_order": "180",
                    "visible": "1"
                },
                {
                    "forum_id": "24",
                    "name": "LIFESTYLE",
                    "description": "Diskusi seputar serba-serbi gaya hidup, dari hal inspiratif, fashion hingga info tentang event terkini.",
                    "display_order": "240",
                    "visible": "1"
                },
                {
                    "forum_id": "235",
                    "name": "TRAVELLERS",
                    "description": "Penggemar jalan-jalan gabung disini! Yuk, berdiskusi dan berbagi segala sesuatu tentang wisata termasuk ulasan tempat wisata, tips dan trik berwisata ke dalam dan luar negeri.",
                    "display_order": "400",
                    "visible": "1"
                }
            ],
            "tag_id": "19",
            "tag_name": "Lifestyle",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141013090850.png"
        },
        {
            "forums": [
                {
                    "forum_id": "18",
                    "name": "CAN YOU SOLVE THIS GAME?",
                    "description": "Punya tebak-tebakan, teka-teki atau permainan seru? Yuk, gabung disini!",
                    "display_order": "50",
                    "visible": "1"
                },
                {
                    "forum_id": "44",
                    "name": "GAMES",
                    "description": "Penggemar game, gabung disini!",
                    "display_order": "150",
                    "visible": "1"
                },
                {
                    "forum_id": "9",
                    "name": "JOKES & CARTOON",
                    "description": "Kumpulan humor dari Kaskuser, siap ngakak Gan!",
                    "display_order": "230",
                    "visible": "1"
                },
                {
                    "forum_id": "11",
                    "name": "MOVIES",
                    "description": "Forum penggemar film, simak info terbaru seputar dunia perfilman, serial TV, sinetron hingga miniseri favorit.",
                    "display_order": "270",
                    "visible": "1"
                },
                {
                    "forum_id": "33",
                    "name": "MUSIC",
                    "description": "Forum penggemar musik, simak info terbaru seputar perkembangan musik dan serunya KaskusRadio.com",
                    "display_order": "280",
                    "visible": "1"
                },
                {
                    "forum_id": "309",
                    "name": "SEPUTAR PEMILU 2009",
                    "description": "Forum khusus berdiskusi seputar PEMILU.",
                    "display_order": "330",
                    "visible": "1"
                }
            ],
            "tag_id": "20",
            "tag_name": "Entertainment",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141013090934.png"
        },
        {
            "forums": [
                {
                    "forum_id": "15",
                    "name": "DISTURBING PICTURE",
                    "description": "Watchout!",
                    "display_order": "90",
                    "visible": "1"
                },
                {
                    "forum_id": "474",
                    "name": "EVENT FROM KASKUSER",
                    "description": "Forum khusus Kaskuser yang ingin berbagi informasi mengenai event, baik yang disponsori\/ berhubungan langsung oleh Kaskus maupun independen (untuk acara gathering & FR regional harap dibuat di regionalnya masing-masing).",
                    "display_order": "120",
                    "visible": "1"
                },
                {
                    "forum_id": "239",
                    "name": "KASKUS CORNER",
                    "description": "Portal info Kaskus. Simak info terbaru seputar kegiatan-kegiatan yang diselenggarakan Kaskus dan melibatkan Kaskuser, seperti gathering, seminar, bakti sosial dan promo. Intip juga siapa saja sih selebriti yang ngaskus.",
                    "display_order": "2",
                    "visible": "1"
                },
                {
                    "forum_id": "23",
                    "name": "SUPRANATURAL",
                    "description": "Penggemar Supranatural, Budaya dan Spiritual gabung disini",
                    "display_order": "350",
                    "visible": "1"
                },
                {
                    "forum_id": "188",
                    "name": "SURAT PEMBACA",
                    "description": "Tempat Kaskuser berbagi keluh kesah seputar pelayanan publik atau produk tertentu. Sarana ini dibuat untuk memberi masukan untuk pelayanan yang lebih baik (bukan sekedar makian\/curhat dan ajakan untuk menjatuhkan kredibilitas).",
                    "display_order": "360",
                    "visible": "1"
                },
                {
                    "forum_id": "21",
                    "name": "THE LOUNGE",
                    "description": "Tempat berbagi gosip, gambar dan video seru\/lucu\/unik.",
                    "display_order": "390",
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
                    "forum_id": "39",
                    "name": "GIRLS & BOYS's CORNER",
                    "description": "Ngobrol asik seputar hubungan pria-wanita.",
                    "display_order": "160",
                    "visible": "1"
                },
                {
                    "forum_id": "16",
                    "name": "HEART TO HEART",
                    "description": "Suka nulis? Ngeblog atau bikin puisi? Yuk, gabung disini!",
                    "display_order": "190",
                    "visible": "1"
                },
                {
                    "forum_id": "193",
                    "name": "WEDDING & FAMILY",
                    "description": "Forum untuk berdiskusi dan berbagi informasi seputar pernikahan (daftar persiapan, artikel terkait) dan keluarga (hubungan pria-wanita, artikel keluarga, anak, cara mendidik anak).",
                    "display_order": "410",
                    "visible": "1"
                },
                {
                    "forum_id": "544",
                    "name": "YOUNG ON TOP KASKUS COMMUNITY (YOTKC)",
                    "description": "Berbagi inspirasi bersama Billy Boen.",
                    "display_order": "430",
                    "visible": "1"
                }
            ],
            "tag_id": "28",
            "tag_name": "Life Corner",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112034.png"
        },
        {
            "forums": [
                {
                    "forum_id": "592",
                    "name": "AMERIKA",
                    "description": "",
                    "display_order": "1",
                    "visible": "1"
                },
                {
                    "forum_id": "617",
                    "name": "AMERIKA",
                    "description": "",
                    "display_order": "1",
                    "visible": "1"
                },
                {
                    "forum_id": "109",
                    "name": "ASIA",
                    "description": "",
                    "display_order": "1",
                    "visible": "1"
                },
                {
                    "forum_id": "74",
                    "name": "AUSTRALIA",
                    "description": "",
                    "display_order": "2",
                    "visible": "1"
                },
                {
                    "forum_id": "157",
                    "name": "EROPA",
                    "description": "",
                    "display_order": "3",
                    "visible": "1"
                },
                {
                    "forum_id": "73",
                    "name": "INDONESIA",
                    "description": "",
                    "display_order": "4",
                    "visible": "1"
                },
                {
                    "forum_id": "158",
                    "name": "OTHER REGIONAL",
                    "description": "",
                    "display_order": "6",
                    "visible": "1"
                }
            ],
            "tag_id": "23",
            "tag_name": "Regional",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112114.png"
        },
        {
            "forums": [
                {
                    "forum_id": "554",
                    "name": "BANNER TEST",
                    "description": "",
                    "display_order": "9999",
                    "visible": "1"
                },
                {
                    "forum_id": "30",
                    "name": "BISNIS",
                    "description": "Forum untuk berdiskusi tentang karir, dunia kerja dan wirausaha. Dapatkan juga informasi seputar lowongan kerja, peluang kerjasama dan investasi.",
                    "display_order": "40",
                    "visible": "1"
                }
            ],
            "tag_id": "21",
            "tag_name": "News & Info",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112132.png"
        },
        {
            "forums": [
                {
                    "forum_id": "98",
                    "name": "OUTDOOR ADVENTURE & NATURE CLUBS",
                    "description": "Pecinta alam, para petualang, pecinta kegiatan outdoor gabung disini!",
                    "display_order": "310",
                    "visible": "1"
                },
                {
                    "forum_id": "35",
                    "name": "SPORTS",
                    "description": "Penggemar olahraga gabung disini!",
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
                    "forum_id": "26",
                    "name": "AMH",
                    "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang Anime dan Manga Haven",
                    "display_order": "20",
                    "visible": "1"
                },
                {
                    "forum_id": "32",
                    "name": "HEWAN PELIHARAAN",
                    "description": "Forum diskusi untuk penggemar dan pemilik hewan .",
                    "display_order": "200",
                    "visible": "1"
                },
                {
                    "forum_id": "392",
                    "name": "HOBBY & COMMUNITY",
                    "description": "Forum diskusi beragam komunitas dan pecinta hobi.",
                    "display_order": "210",
                    "visible": "1"
                },
                {
                    "forum_id": "28",
                    "name": "OTOMOTIF",
                    "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang dunia otomotif. Simak info\/tren otomotif terbaru hingga tips dan trik seputar perawatan kendaraan anda.",
                    "display_order": "300",
                    "visible": "1"
                },
                {
                    "forum_id": "54",
                    "name": "PHOTOGRAPHY",
                    "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang fotografi (amatir dan pro) termasuk tutorial, tips dan trik.",
                    "display_order": "320",
                    "visible": "1"
                },
                {
                    "forum_id": "192",
                    "name": "TANAMAN",
                    "description": "Penggemar tanaman\/tumbuhan gabung disini!",
                    "display_order": "370",
                    "visible": "1"
                }
            ],
            "tag_id": "22",
            "tag_name": "Interest",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141027034637.png"
        },
        {
            "forums": [
                {
                    "forum_id": "34",
                    "name": "ALL ABOUT DESIGN",
                    "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang desain (desain grafis, desain website, desain interior dsb) termasuk tutorial, tips dan trik",
                    "display_order": "10",
                    "visible": "1"
                },
                {
                    "forum_id": "10",
                    "name": "BERITA DAN POLITIK ",
                    "description": "Forum untuk berdiskusi dan berbagi berita dari dalam maupun luar negeri. Beragam topik dihadirkan, mulai dari ideologi, politik, ekonomi, sosial dan budaya.",
                    "display_order": "30",
                    "visible": "1"
                },
                {
                    "forum_id": "622",
                    "name": "BUKU",
                    "description": "Forum untuk berdiskusi tentang karir, dunia kerja dan wirausaha. Dapatkan juga informasi seputar lowongan kerja, peluang kerjasama dan investasi.",
                    "display_order": "40",
                    "visible": "1"
                },
                {
                    "forum_id": "19",
                    "name": "COMPUTER STUFF 2",
                    "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang komputer dan internet.",
                    "display_order": "60",
                    "visible": "1"
                },
                {
                    "forum_id": "191",
                    "name": "DEBATE CLUB",
                    "description": "Beda pendapat? Silakan gabung di forum debat !",
                    "display_order": "80",
                    "visible": "1"
                },
                {
                    "forum_id": "67",
                    "name": "EDUCATION",
                    "description": "Tempat diskusi dan berbagi informasi serta pengetahuan tentang buku, sejarah, ilmu misteri dunia hingga aktivitas beragam almamater.",
                    "display_order": "100",
                    "visible": "1"
                },
                {
                    "forum_id": "387",
                    "name": "ILMU MARKETING",
                    "description": "Tempat diskusi seputar dunia marketing, keilmuan maupun penerapan.",
                    "display_order": "220",
                    "visible": "1"
                },
                {
                    "forum_id": "72",
                    "name": "REGIONAL",
                    "description": "Temukan Kaskuser di wilayahmu. Tinggal atau pernah tinggal di wilayah tertentu? Yuk, ngumpul bareng dan bagi info atau pengalamanmu.",
                    "display_order": "50",
                    "visible": "1"
                },
                {
                    "forum_id": "578",
                    "name": "TEKNIK",
                    "description": "Forum untuk berdiskusi dan berbagi segala sesuatu tentang ilmu\/ info teknik arsitektur dan teknik sipil .",
                    "display_order": "380",
                    "visible": "1"
                },
                {
                    "forum_id": "103",
                    "name": "WELCOME TO KASKUS",
                    "description": "Mau tahu lebih banyak tentang Kaskus? Mampir disini!",
                    "display_order": "420",
                    "visible": "1"
                }
            ],
            "tag_id": "12",
            "tag_name": "Knowledge",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112014.png"
        }
    ],
    "fjb": [
        {
            "forums": [
                {
                    "forum_id": "317",
                    "name": "Komputer",
                    "description": "Jual beli komputer (hardware, software)",
                    "display_order": "19",
                    "visible": "1"
                }
            ],
            "tag_id": "37",
            "tag_name": "Computers",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111759.png"
        },
        {
            "forums": [
                {
                    "forum_id": "151",
                    "name": "Gratisan",
                    "description": "Aneka promo gratis",
                    "display_order": "11",
                    "visible": "1"
                },
                {
                    "forum_id": "210",
                    "name": "Handphone & PDA",
                    "description": "Jual beli Handphone dan PDA",
                    "display_order": "12",
                    "visible": "1"
                }
            ],
            "tag_id": "35",
            "tag_name": "Handphones",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111954.png"
        },
        {
            "forums": [
                {
                    "forum_id": "220",
                    "name": "Alat-Alat Olahraga",
                    "description": "Jual beli pakaian, sepatu dan perlengkapan olahraga",
                    "display_order": "2",
                    "visible": "1"
                },
                {
                    "forum_id": "283",
                    "name": "Antik",
                    "description": "Jual beli benda menarik, kuno dan unik",
                    "display_order": "3",
                    "visible": "1"
                },
                {
                    "forum_id": "227",
                    "name": "Buku",
                    "description": "Jual beli beragam jenis buku",
                    "display_order": "5",
                    "visible": "1"
                },
                {
                    "forum_id": "588",
                    "name": "Online Gaming",
                    "description": "",
                    "display_order": "22",
                    "visible": "1"
                }
            ],
            "tag_id": "45",
            "tag_name": "Hobbies",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111932.png"
        },
        {
            "forums": [
                {
                    "forum_id": "316",
                    "name": "Tiket",
                    "description": "Jual beli tiket",
                    "display_order": "31",
                    "visible": "1"
                },
                {
                    "forum_id": "304",
                    "name": "Tur & Paket Perjalanan",
                    "description": "Penawaran aneka tur dan paket wisata",
                    "display_order": "32",
                    "visible": "1"
                }
            ],
            "tag_id": "40",
            "tag_name": "Travel & Leisure",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111840.png"
        },
        {
            "forums": [
                {
                    "forum_id": "205",
                    "name": "Otomotif",
                    "description": "Jual beli mobil\/motor, aksesoris dan suku cadang",
                    "display_order": "23",
                    "visible": "1"
                }
            ],
            "tag_id": "38",
            "tag_name": "Automotive",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031112010.png"
        },
        {
            "forums": [
                {
                    "forum_id": "293",
                    "name": "Kamera & Aksesoris",
                    "description": "Jual beli kamera dan aksesoris",
                    "display_order": "16",
                    "visible": "1"
                }
            ],
            "tag_id": "36",
            "tag_name": "Cameras",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031112027.png"
        },
        {
            "forums": [
                {
                    "forum_id": "200",
                    "name": "CD & DVD",
                    "description": "Jual beli CD\/DVD",
                    "display_order": "6",
                    "visible": "1"
                },
                {
                    "forum_id": "195",
                    "name": "Elektronik",
                    "description": "Jual beli beragam jenis barang elektronik",
                    "display_order": "7",
                    "visible": "1"
                },
                {
                    "forum_id": "297",
                    "name": "Video Games",
                    "description": "Jual beli games dan konsol",
                    "display_order": "33",
                    "visible": "1"
                }
            ],
            "tag_id": "33",
            "tag_name": "Electronics",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031112041.png"
        },
        {
            "forums": [
                {
                    "forum_id": "196",
                    "name": "Fashion & Mode",
                    "description": "Jual beli barang fashion untuk pria dan wanita",
                    "display_order": "8",
                    "visible": "1"
                }
            ],
            "tag_id": "46",
            "tag_name": "Fashion",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111720.png"
        },
        {
            "forums": [
                {
                    "forum_id": "296",
                    "name": "Furniture",
                    "description": "Jual beli mebel (kursi, meja, lemari dsb)",
                    "display_order": "10",
                    "visible": "1"
                },
                {
                    "forum_id": "298",
                    "name": "Perkakas",
                    "description": "Jual beli aneka perkakas",
                    "display_order": "25",
                    "visible": "1"
                },
                {
                    "forum_id": "305",
                    "name": "Perlengkapan Anak & Bayi",
                    "description": "Jual beli pakaian, perlengkapan bayi dan anak-anak",
                    "display_order": "26",
                    "visible": "1"
                },
                {
                    "forum_id": "300",
                    "name": "Perlengkapan Kantor",
                    "description": "Jual beli perlengkapan kantor",
                    "display_order": "27",
                    "visible": "1"
                },
                {
                    "forum_id": "303",
                    "name": "Perlengkapan Rumah Tangga",
                    "description": "Jual beli perlengkapan rumah tangga (sub kategori terkait, cek elektronik rumah tangga)",
                    "display_order": "28",
                    "visible": "1"
                },
                {
                    "forum_id": "199",
                    "name": "Properti",
                    "description": "Jual beli properti",
                    "display_order": "29",
                    "visible": "1"
                }
            ],
            "tag_id": "39",
            "tag_name": "Home & Office",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111900.png"
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
        {
            "tag_id": "45",
            "tag_name": "Hobbies",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111932.png",
            "forums": [
                {
                    "forum_id": "220",
                    "name": "Alat-Alat Olahraga",
                    "description": "Jual beli pakaian, sepatu dan perlengkapan olahraga",
                    "display_order": 2,
                    "visible": "1",
                    "child_list": "220,589,-1"
                },
                {
                    "forum_id": "283",
                    "name": "Antik",
                    "description": "Jual beli benda menarik, kuno dan unik",
                    "display_order": 3,
                    "visible": "1",
                    "child_list": "283,-1"
                },
                {
                    "forum_id": "227",
                    "name": "Buku",
                    "description": "Jual beli beragam jenis buku",
                    "display_order": 5,
                    "visible": "1",
                    "child_list": "227,264,594,-1"
                },
                {
                    "forum_id": "588",
                    "name": "Online Gaming",
                    "description": "",
                    "display_order": 22,
                    "visible": "1",
                    "child_list": "588,-1"
                }
            ]
        },
        {
            "tag_id": "39",
            "tag_name": "Home & Office",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111900.png",
            "forums": [
                {
                    "forum_id": "296",
                    "name": "Furniture",
                    "description": "Jual beli mebel (kursi, meja, lemari dsb)",
                    "display_order": 10,
                    "visible": "1",
                    "child_list": "296,-1"
                },
                {
                    "forum_id": "298",
                    "name": "Perkakas",
                    "description": "Jual beli aneka perkakas",
                    "display_order": 25,
                    "visible": "1",
                    "child_list": "298,-1"
                },
                {
                    "forum_id": "305",
                    "name": "Perlengkapan Anak & Bayi",
                    "description": "Jual beli pakaian, perlengkapan bayi dan anak-anak",
                    "display_order": 26,
                    "visible": "1",
                    "child_list": "305,447,446,-1"
                },
                {
                    "forum_id": "300",
                    "name": "Perlengkapan Kantor",
                    "description": "Jual beli perlengkapan kantor",
                    "display_order": 27,
                    "visible": "1",
                    "child_list": "300,312,-1"
                },
                {
                    "forum_id": "303",
                    "name": "Perlengkapan Rumah Tangga",
                    "description": "Jual beli perlengkapan rumah tangga (sub kategori terkait, cek elektronik rumah tangga)",
                    "display_order": 28,
                    "visible": "1",
                    "child_list": "303,314,-1"
                },
                {
                    "forum_id": "199",
                    "name": "Properti",
                    "description": "Jual beli properti",
                    "display_order": 29,
                    "visible": "1",
                    "child_list": "199,223,225,222,-1"
                }
            ]
        },
        {
            "tag_id": "37",
            "tag_name": "Computers",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111759.png",
            "forums": [
                {
                    "forum_id": "317",
                    "name": "Komputer",
                    "description": "Jual beli komputer (hardware, software)",
                    "display_order": 19,
                    "visible": "1",
                    "child_list": "317,330,328,318,323,327,321,324,325,319,326,320,322,-1"
                }
            ]
        },
        {
            "tag_id": "35",
            "tag_name": "Handphones",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111954.png",
            "forums": [
                {
                    "forum_id": "151",
                    "name": "Gratisan",
                    "description": "Aneka promo gratis",
                    "display_order": 11,
                    "visible": "1",
                    "child_list": "151,-1"
                },
                {
                    "forum_id": "210",
                    "name": "Handphone & PDA",
                    "description": "Jual beli Handphone dan PDA",
                    "display_order": 12,
                    "visible": "1",
                    "child_list": "210,527,574,381,573,-1"
                }
            ]
        },
        {
            "tag_id": "46",
            "tag_name": "Fashion",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111720.png",
            "forums": [
                {
                    "forum_id": "196",
                    "name": "Fashion & Mode",
                    "description": "Jual beli barang fashion untuk pria dan wanita",
                    "display_order": 8,
                    "visible": "1",
                    "child_list": "196,216,451,450,302,449,599,600,215,257,310,311,-1"
                }
            ]
        },
        {
            "tag_id": "40",
            "tag_name": "Travel & Leisure",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031111840.png",
            "forums": [
                {
                    "forum_id": "316",
                    "name": "Tiket",
                    "description": "Jual beli tiket",
                    "display_order": 31,
                    "visible": "1",
                    "child_list": "316,610,611,-1"
                },
                {
                    "forum_id": "304",
                    "name": "Tur & Paket Perjalanan",
                    "description": "Penawaran aneka tur dan paket wisata",
                    "display_order": 32,
                    "visible": "1",
                    "child_list": "304,-1"
                }
            ]
        },
        {
            "tag_id": "38",
            "tag_name": "Automotive",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031112010.png",
            "forums": [
                {
                    "forum_id": "205",
                    "name": "Otomotif",
                    "description": "Jual beli mobil\/motor, aksesoris dan suku cadang",
                    "display_order": 23,
                    "visible": "1",
                    "child_list": "205,333,334,206,207,208,256,209,593,-1"
                }
            ]
        },
        {
            "tag_id": "36",
            "tag_name": "Cameras",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031112027.png",
            "forums": [
                {
                    "forum_id": "293",
                    "name": "Kamera & Aksesoris",
                    "description": "Jual beli kamera dan aksesoris",
                    "display_order": 16,
                    "visible": "1",
                    "child_list": "293,604,605,294,-1"
                }
            ]
        },
        {
            "tag_id": "33",
            "tag_name": "Electronics",
            "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141031112041.png",
            "forums": [
                {
                    "forum_id": "200",
                    "name": "CD & DVD",
                    "description": "Jual beli CD\/DVD",
                    "display_order": 6,
                    "visible": "1",
                    "child_list": "200,595,266,265,329,-1"
                },
                {
                    "forum_id": "195",
                    "name": "Elektronik",
                    "description": "Jual beli beragam jenis barang elektronik",
                    "display_order": 7,
                    "visible": "1",
                    "child_list": "195,313,255,254,-1"
                },
                {
                    "forum_id": "297",
                    "name": "Video Games",
                    "description": "Jual beli games dan konsol",
                    "display_order": 33,
                    "visible": "1",
                    "child_list": "297,612,613,-1"
                }
            ]
        }
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
    null,
    {
        "forum": [
            "94",
            "24",
            "29",
            "235",
            "558"
        ],
        "tag_id": "19",
        "tag_name": "Lifestyle",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141013090850.png"
    },
    {
        "forum": [
            "33",
            "44",
            "309",
            "9",
            "11",
            "18"
        ],
        "tag_id": "20",
        "tag_name": "Entertainment",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141013090934.png"
    },
    {
        "forum": [
            "15",
            "474",
            "188",
            "23",
            "21",
            "239"
        ],
        "tag_id": "44",
        "tag_name": "Kasak Kusuk",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141013091140.png"
    },
    {
        "forum": [
            "39",
            "16",
            "193",
            "544"
        ],
        "tag_id": "28",
        "tag_name": "Life Corner",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112034.png"
    },
    {
        "forum": [
            "109",
            "74",
            "617",
            "157",
            "73",
            "158",
            "592"
        ],
        "tag_id": "23",
        "tag_name": "Regional",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112114.png"
    },
    {
        "forum": [
            "30",
            "554"
        ],
        "tag_id": "21",
        "tag_name": "News & Info",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112132.png"
    },
    {
        "forum": [
            "98",
            "35"
        ],
        "tag_id": "25",
        "tag_name": "Sports & Adventure",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021111922.png"
    },
    {
        "forum": [
            "26",
            "32",
            "392",
            "28",
            "54",
            "192"
        ],
        "tag_id": "22",
        "tag_name": "Interest",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141027034637.png"
    },
    {
        "forum": [
            "34",
            "387",
            "67",
            "191",
            "72",
            "578",
            "10",
            "622",
            "19",
            "103"
        ],
        "tag_id": "12",
        "tag_name": "Knowledge",
        "tag_icon": "http:\/\/cdn.kaskusplayground.local\/img\/tagicon\/icon_20141021112014.png"
    }
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




> Example response

```json
[
    {
        "navigation_id": "3",
        "name": "FAQ",
        "navigation_icon": "icon_20141021021121.gif",
        "navigation_url": "http:\/\/support.kaskus.co.id\/kaskus-basic\/faq.html",
        "description": "Provide Solution",
        "flag_clickable": "1",
        "order": "4"
    }
]
```

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
    "total_post": 15834,
    "current_page": 1,
    "total_page": 1584,
    "per_page": 10,
    "posts": [
        {
            "post_userid": "11",
            "dateline": 1452655117,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5695c20d8ead0e54000042be",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452655053,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5695c1cd8ead0ea89100429f",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452591369,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5694c9098ead0e54000042bb",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452591363,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5694c9038ead0e56000042c8",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT 26",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452591327,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5694c8df8ead0ea89100429c",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT 25",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452591264,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5694c8a08ead0e54000042b8",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT 2",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452591239,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5694c8878ead0ea891004299",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT 2",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452591224,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5694c8788ead0e54000042b5",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452589605,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5694c2258ead0e56000042c3",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
        },
        {
            "post_userid": "11",
            "dateline": 1452589573,
            "visible": 1,
            "pagetext": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0,
            "post_id": "5694c2058ead0e54000042b0",
            "post": [
                {
                    "type": "text",
                    "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
                    "linktype": "",
                    "url": "",
                    "link": false
                }
            ],
            "images": [],
            "text": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "decoded": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "pagetext_noquote": "monggo ayo dicoba apel kaskus yang enak ini gan",
            "title": "TEST JUAL PUSING NIH DONAT",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna"
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
            "dateline": 1452655117,
            "thread_starter": "5695c20d8ead0e54000042be",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452655117,
            "last_post_id": "5695c20d8ead0e54000042be",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5695c20d8ead0e54000042bf",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452655053,
            "thread_starter": "5695c1cd8ead0ea89100429f",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452655053,
            "last_post_id": "5695c1cd8ead0ea89100429f",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5695c1cd8ead0ea8910042a0",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452591369,
            "thread_starter": "5694c9098ead0e54000042bb",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591369,
            "last_post_id": "5694c9098ead0e54000042bb",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c9098ead0e54000042bc",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452591363,
            "thread_starter": "5694c9038ead0e56000042c8",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591363,
            "last_post_id": "5694c9038ead0e56000042c8",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c9038ead0e56000042c9",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 26",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452591327,
            "thread_starter": "5694c8df8ead0ea89100429c",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591327,
            "last_post_id": "5694c8df8ead0ea89100429c",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8df8ead0ea89100429d",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 25",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452591264,
            "thread_starter": "5694c8a08ead0e54000042b8",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591264,
            "last_post_id": "5694c8a08ead0e54000042b8",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8a08ead0e54000042b9",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452591239,
            "thread_starter": "5694c8878ead0ea891004299",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591239,
            "last_post_id": "5694c8878ead0ea891004299",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8878ead0ea89100429a",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452591224,
            "thread_starter": "5694c8788ead0e54000042b5",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591224,
            "last_post_id": "5694c8788ead0e54000042b5",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8788ead0e54000042b6",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452589605,
            "thread_starter": "5694c2258ead0e56000042c3",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452589605,
            "last_post_id": "5694c2258ead0e56000042c3",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c2258ead0e56000042c4",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "dateline": 1452589573,
            "thread_starter": "5694c2058ead0e54000042b0",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452589573,
            "last_post_id": "5694c2058ead0e54000042b0",
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c2058ead0e54000042b1",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "discount": 0,
            "extra_attributes": [],
            "hot_thread": 0,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        }
    ],
    "thread_num": 5039,
    "current_page": 1,
    "total_page": 504,
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
            "views": 7,
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1447386429,
            "thread_starter": "56455d3d7a1f5c28008b4653",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 11,
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1447386377,
            "thread_starter": "56455d097a1f5c29008b465b",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 20,
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1447386360,
            "thread_starter": "56455cf87a1f5c29008b4655",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 3,
            "reply_count": 1,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447386361,
            "last_post_id": "56455cf97a1f5c28008b4641",
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1447385838,
            "thread_starter": "56455aee7a1f5c28008b45fd",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 3,
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "views": 7,
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1447386429,
            "thread_starter": "56455d3d7a1f5c28008b4653",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 11,
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1447386377,
            "thread_starter": "56455d097a1f5c29008b465b",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 20,
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1447386360,
            "thread_starter": "56455cf87a1f5c29008b4655",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 3,
            "reply_count": 1,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1447386361,
            "last_post_id": "56455cf97a1f5c28008b4641",
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1447385838,
            "thread_starter": "56455aee7a1f5c28008b45fd",
            "forum_id": 210,
            "forum_title": "Handphone & Tablet <font size=\"1\" color=\"blue\"><sup><b>updated<\/b><\/sup><\/font>",
            "visible": 1,
            "views": 3,
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "dateline": 1452655117,
            "thread_starter": "5695c20d8ead0e54000042be",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452655117,
            "last_post_id": "5695c20d8ead0e54000042be",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5695c20d8ead0e54000042bf",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452655053,
            "thread_starter": "5695c1cd8ead0ea89100429f",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452655053,
            "last_post_id": "5695c1cd8ead0ea89100429f",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5695c1cd8ead0ea8910042a0",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591369,
            "thread_starter": "5694c9098ead0e54000042bb",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591369,
            "last_post_id": "5694c9098ead0e54000042bb",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c9098ead0e54000042bc",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591363,
            "thread_starter": "5694c9038ead0e56000042c8",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591363,
            "last_post_id": "5694c9038ead0e56000042c8",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c9038ead0e56000042c9",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 26",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591327,
            "thread_starter": "5694c8df8ead0ea89100429c",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591327,
            "last_post_id": "5694c8df8ead0ea89100429c",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8df8ead0ea89100429d",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 25",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591264,
            "thread_starter": "5694c8a08ead0e54000042b8",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591264,
            "last_post_id": "5694c8a08ead0e54000042b8",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8a08ead0e54000042b9",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591239,
            "thread_starter": "5694c8878ead0ea891004299",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591239,
            "last_post_id": "5694c8878ead0ea891004299",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8878ead0ea89100429a",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591224,
            "thread_starter": "5694c8788ead0e54000042b5",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591224,
            "last_post_id": "5694c8788ead0e54000042b5",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8788ead0e54000042b6",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452589605,
            "thread_starter": "5694c2258ead0e56000042c3",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452589605,
            "last_post_id": "5694c2258ead0e56000042c3",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c2258ead0e56000042c4",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452589573,
            "thread_starter": "5694c2058ead0e54000042b0",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452589573,
            "last_post_id": "5694c2058ead0e54000042b0",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c2058ead0e54000042b1",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        }
    ],
    "thread_num": 760,
    "current_page": 1,
    "total_page": 76,
    "per_page": 10,
    "cursor": "MTQ1MjU4OTU3Mw"
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1416386913,
            "thread_starter": "546c5961c721e6e051000020",
            "forum_id": 594,
            "forum_title": "Komik",
            "visible": 1,
            "views": 40,
            "reply_count": 10,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1416813412,
            "last_post_id": "5472db64c721e68971000006",
            "resources": {
                "images": [
                    "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2014\/11\/19\/monyet_11_20141119034911.png"
                ],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/images\/fjb\/2014\/11\/19\/monyet_11_20141119034911.png",
                "images_thumbnail": [
                    "http:\/\/cdn.kaskusplayground.local\/r150x150\/images\/fjb\/2014\/11\/19\/monyet_11_20141119034911.png"
                ]
            },
            "prefix_id": "SOLD",
            "thread_id": "546c5961c721e6e05100001f",
            "post_userid": 11,
            "title": "monyet",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 123123,
            "discount": 0,
            "discounted_price": 123123,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        }
    ],
    "thread_num": 4,
    "current_page": 1,
    "total_page": 1,
    "per_page": 10,
    "cursor": "MTQxNjgxMzQxMg"
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
            "dateline": 1452655117,
            "thread_starter": "5695c20d8ead0e54000042be",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452655117,
            "last_post_id": "5695c20d8ead0e54000042be",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5695c20d8ead0e54000042bf",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452655053,
            "thread_starter": "5695c1cd8ead0ea89100429f",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452655053,
            "last_post_id": "5695c1cd8ead0ea89100429f",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5695c1cd8ead0ea8910042a0",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591369,
            "thread_starter": "5694c9098ead0e54000042bb",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591369,
            "last_post_id": "5694c9098ead0e54000042bb",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c9098ead0e54000042bc",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 27",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591363,
            "thread_starter": "5694c9038ead0e56000042c8",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591363,
            "last_post_id": "5694c9038ead0e56000042c8",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c9038ead0e56000042c9",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 26",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591327,
            "thread_starter": "5694c8df8ead0ea89100429c",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591327,
            "last_post_id": "5694c8df8ead0ea89100429c",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8df8ead0ea89100429d",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 25",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591264,
            "thread_starter": "5694c8a08ead0e54000042b8",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591264,
            "last_post_id": "5694c8a08ead0e54000042b8",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8a08ead0e54000042b9",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591239,
            "thread_starter": "5694c8878ead0ea891004299",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591239,
            "last_post_id": "5694c8878ead0ea891004299",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8878ead0ea89100429a",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT 2",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452591224,
            "thread_starter": "5694c8788ead0e54000042b5",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452591224,
            "last_post_id": "5694c8788ead0e54000042b5",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": null,
            "thread_id": "5694c8788ead0e54000042b6",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452589605,
            "thread_starter": "5694c2258ead0e56000042c3",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452589605,
            "last_post_id": "5694c2258ead0e56000042c3",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c2258ead0e56000042c4",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "dateline": 1452589573,
            "thread_starter": "5694c2058ead0e54000042b0",
            "forum_id": 197,
            "forum_title": "Flora &amp; Fauna",
            "visible": 1,
            "views": 1,
            "reply_count": 0,
            "last_poster": "recca",
            "last_post_userid": 11,
            "last_post": 1452589573,
            "last_post_id": "5694c2058ead0e54000042b0",
            "resources": {
                "images": [],
                "images_thumbnail": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png"
            },
            "prefix_id": "WTS",
            "payment_method": {
                "COD": "1",
                "ESCROW": "2"
            },
            "thread_id": "5694c2058ead0e54000042b1",
            "post_userid": 11,
            "title": "TEST JUAL PUSING NIH DONAT",
            "thread_type": 21,
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "item_price": 20000,
            "discount": 0,
            "discounted_price": 20000,
            "sundul_count": 0,
            "sundul_count_remainder": 5,
            "sundul_enabled": 1,
            "post_username": "recca",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        }
    ],
    "thread_num": 764,
    "current_page": 1,
    "total_page": 77,
    "per_page": 10,
    "cursor": "MTQ1MjU4OTU3Mw"
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
        "total_message": 4,
        "total_message_sticky": 112,
        "total_message_unread": 1,
        "total_message_sticky_unread": 112,
        "folder_name": "Inbox",
        "folder_id": 0
    },
    {
        "total_message": 4,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "Outbox",
        "folder_id": -1
    },
    {
        "total_message": 112,
        "total_message_sticky": 112,
        "total_message_unread": 112,
        "total_message_sticky_unread": 112,
        "folder_name": "Notices",
        "folder_id": -9
    },
    {
        "total_message": 0,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "test bikin folder",
        "folder_id": 1
    },
    {
        "total_message": 0,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "API_TEST",
        "folder_id": 2
    },
    {
        "total_message": 0,
        "total_message_sticky": 0,
        "total_message_unread": 0,
        "total_message_sticky_unread": 0,
        "folder_name": "API TEST",
        "folder_id": 3
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
    "total_reputation": "0",
    "list_reputation": [
        {
            "post_id": "544dcfa38ead0ecd4f0041b5",
            "user_id": "11",
            "reputation": 5,
            "reason": "oke gaan",
            "dateline": 1414386071,
            "reputationid": "445",
            "from": {
                "userid": 2432163,
                "username": "superman.5",
                "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/01\/02\/male.jpg",
                "usertitle": "Administrator",
                "number_of_post": 26,
                "enable_reputation": 1,
                "reputation": 0,
                "reputation_title": "tidak memiliki reputasi",
                "is_donatur": false,
                "reputation_box": 0
            },
            "post_title": "tipe - tipe teman waktu presentasi di sekolah",
            "thread_title": "tipe - tipe teman waktu presentasi di sekolah",
            "thread_id": "544dcfa38ead0ecd4f0041b4"
        },
        {
            "post_id": "542234458ead0e3f7b0041c9",
            "user_id": "11",
            "reputation": -5,
            "reason": "",
            "dateline": 1411532239,
            "reputationid": "429",
            "from": {
                "userid": 5427,
                "username": "devil",
                "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/06\/19\/avatar5427_1.gif",
                "usertitle": "Administrator",
                "number_of_post": 188,
                "enable_reputation": 1,
                "reputation": 5,
                "reputation_title": "tidak memiliki reputasi",
                "is_donatur": false,
                "reputation_box": 1
            },
            "post_title": "test forum thread hahahahahaha",
            "thread_title": "soso haha - Part 1",
            "thread_id": "5406f65ebec724330e00420c"
        },
        {
            "post_id": "53c75255eec3b451040041b2",
            "user_id": "11",
            "reputation": -5,
            "reason": "",
            "dateline": 1410850231,
            "reputationid": "427",
            "from": {
                "userid": 916848,
                "username": "beta tester",
                "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/06\/08\/avatar916848_12.gif",
                "usertitle": "Administrator",
                "number_of_post": 2,
                "enable_reputation": 1,
                "reputation": 1000,
                "reputation_title": " has much to be proud of",
                "is_donatur": false,
                "reputation_box": 8
            },
            "post_title": "Bzzzzzzzzzzz",
            "thread_title": "Bzzzzzzzzzzz",
            "thread_id": "53c75255eec3b451040041b1"
        },
        {
            "post_id": "52cbdf31ccd8061b4f000018",
            "user_id": "11",
            "reputation": 0,
            "reason": "<iframe src=\"http:\/\/www.google.com\"><\/iframe><strong>Nih cendolnya gan<\/strong>",
            "dateline": 1391506902,
            "reputationid": "411",
            "from": {
                "userid": 10793,
                "username": "bolobolo",
                "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/03\/12\/avatar10793_14.gif",
                "usertitle": "Lorem ipsum dolor sit amet, nonummy ligula volutpat hac integer nonummy. Suspendisse ultricies, congue etiam tellus, erat libero, nulla eleifend, mauris pellentesque. Suspendisse integer praesent vel, integer gravida mauris, fringilla vehicula lacini",
                "number_of_post": 1046,
                "enable_reputation": 1,
                "reputation": 0,
                "reputation_title": "tidak memiliki reputasi",
                "is_donatur": false,
                "reputation_box": 0
            },
            "post_title": "",
            "thread_title": "Jasad Puluhan Tahun di Situbondo Masih Utuh dan Wangi",
            "thread_id": "5271ce0d8ead0e5600ebc18c"
        },
        {
            "post_id": "523142469dfaf1af0200001b",
            "user_id": "11",
            "reputation": 5,
            "reason": "+5 gan",
            "dateline": 1378970090,
            "reputationid": "399",
            "from": {
                "userid": 5,
                "username": "template",
                "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar5_81.gif",
                "usertitle": "Administrator",
                "number_of_post": 120,
                "enable_reputation": 0,
                "reputation": 0,
                "reputation_title": "disabled reputation",
                "is_donatur": false,
                "reputation_box": 0
            },
            "post_title": "Latpos - Latihan posting gan (versi 2)",
            "thread_title": "Latpos - Latihan posting gan (versi 2)",
            "thread_id": "523142469dfaf1af0200001a"
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



# Search



## Search User

Search User.

### HTTP Request

`GET /search/user`

Parameter | Description
--------- | -----------
q|Username to search
output|output format (JSON or XML)




> Example response

```json
{
    "numFound": 0,
    "start": 0,
    "querytime": 0.005,
    "current_page": 1,
    "total_page": 0,
    "per_page": 10,
    "item": []
}
```

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
            "thread_id": "531e842019cb17702e8b45d1",
            "title": "[Pirate Army] Optimisasi Android by HQ.Kaskus [PG-R]",
            "score": 17,
            "thread_type": 10,
            "forum_id": 21,
            "forum_name": "THE LOUNGE",
            "post_id": "531e842019cb17702e8b45d2",
            "post_title": "[Pirate Army] Optimisasi Android by HQ.Kaskus [PG-R]",
            "post_userid": 4036780,
            "post_username": "HQ.Kaskus",
            "dateline": 1394508832,
            "last_post": 1394518059,
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
            "forum_name": "THE LOUNGE",
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
            "forum_name": "Kritik, Saran & Pertanyaan seputar Kaskus",
            "post_id": "531e4718c0cb17d2528b456c",
            "post_title": "SOAL APLIKASI KASKUS ANDROID",
            "post_userid": 3057143,
            "post_username": "rifki123",
            "dateline": 1394493208,
            "last_post": 1394493208,
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
            "thread_id": "531e1a8ff8ca1745288b462a",
            "title": "lagi cari programmer android di bandung",
            "score": 13,
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
            "thread_id": "531de515118b4672718b45a1",
            "title": "asphalt 8 android",
            "score": 17,
            "thread_type": 10,
            "forum_id": 21,
            "forum_name": "THE LOUNGE",
            "post_id": "531de515118b4672718b45a2",
            "post_title": "asphalt 8 android",
            "post_userid": 5464135,
            "post_username": "kb1198",
            "dateline": 1394468117,
            "last_post": 1394468955,
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
            "thread_id": "531dc25317cb1786458b4594",
            "title": "Lima Aplikasi Buat Genjot Kecepatan Internet di Android",
            "score": 10,
            "thread_type": 10,
            "forum_id": 21,
            "forum_name": "THE LOUNGE",
            "post_id": "531dc25317cb1786458b4595",
            "post_title": "Lima Aplikasi Buat Genjot Kecepatan Internet di Android",
            "post_userid": 3187246,
            "post_username": "aryahacky",
            "dateline": 1394459219,
            "last_post": 1394517134,
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
    "querytime": 0.0581,
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
            "score": 14,
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
            "thread_type": 10,
            "forum_id": 625,
            "forum_name": "",
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
            "discounted_price": 0,
            "item_location": 11,
            "item_condition": 1,
            "resources": null,
            "thread_views": 116,
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
            "thread_id": "5209fcb340cb17bb75000003",
            "title": "Kumpulan DVD Game Console\/Handled With Emulator, Play di PC\/laptop\/Android",
            "score": 10,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2010\/06\/06\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 432,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 2,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 1
        },
        {
            "thread_id": "531ea3a4a1cb1702148b481c",
            "title": "[RUSAK TAPI MASIH BISA KEPAKE] SAMSUNG ANDROID \/ iPHONE 3GS 32GB \/ LAPTOP - BANDUNG",
            "score": 11,
            "thread_type": 20,
            "forum_id": 210,
            "forum_name": "Handphone & PDA",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/08\/01\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 424,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 11,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/01\/21\/avatar2501421_1.gif",
            "usertitle": "aktivis kaskus",
            "number_of_post": 116,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "reputation_box": 0
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
            "thread_id": "52c1274838cb17c0708b498f",
            "title": "SERVICE & Install Komputer\/Smartphone (Mac,windows,Linux,Android,iOs,BB) Free Game",
            "score": 9,
            "thread_type": 10,
            "forum_id": 631,
            "forum_name": "",
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
            "discounted_price": 0,
            "item_location": 14,
            "item_condition": 1,
            "resources": null,
            "thread_views": 748,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "",
            "number_of_post": 0,
            "is_donatur": false,
            "is_vsl": false,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "",
            "reputation_box": 0
        }
    ],
    "start": 0,
    "numFound": 9515,
    "querytime": 0.1519,
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
            "views": 5,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 210,
            "title": "Arif foto model cantik",
            "dateline": 1447386377,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 7,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 210,
            "title": "Samsung Galaxy S4 16 GB 4d2626fb17997233d146d1f42c016297",
            "dateline": 1447386429,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 11,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 210,
            "title": "test bikin lapapkkk",
            "dateline": 1447235027,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 3,
            "views": 20,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        },
        {
            "forum_id": 449,
            "title": "beli kaktur berdurii",
            "dateline": 1446616672,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 5,
            "post_username": "pembeli",
            "post_userid": 222745,
            "first_post_id": "56399e608ead0ef33fc2a95c",
            "last_poster": "pembeli",
            "last_post_userid": 222745,
            "last_post": 1446616672,
            "last_post_id": "56399e608ead0ef33fc2a95c",
            "sticky": 0,
            "prefix_id": "SOLD",
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
            "usertitle": "newbie",
            "number_of_post": 17,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/02\/01\/avatar1183_12.gif",
            "usertitle": "Lorem ipsum dolor sit amet, nonummy ligula volutpat hac integer nonummy. Suspendisse ultricies, congue etiam tellus, erat libero, nulla eleifend, mauris pellentesque. Suspendisse integer praesent vel, integer gravida mauris, fringilla vehicula lacini",
            "number_of_post": 1603,
            "enable_reputation": 1,
            "reputation": 19,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/02\/01\/avatar1183_12.gif",
            "usertitle": "Lorem ipsum dolor sit amet, nonummy ligula volutpat hac integer nonummy. Suspendisse ultricies, congue etiam tellus, erat libero, nulla eleifend, mauris pellentesque. Suspendisse integer praesent vel, integer gravida mauris, fringilla vehicula lacini",
            "number_of_post": 1603,
            "enable_reputation": 1,
            "reputation": 19,
            "reputation_title": "sedang di jalan yg benar",
            "is_donatur": false,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/04\/30\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 109,
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
            "usertitle": "newbie",
            "number_of_post": 0,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": true,
            "reputation_box": 0
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
    "lastlogin": 1450768143,
    "lastlogout": 1444102776,
    "usergroupid": "16",
    "firstname": "recca",
    "lastname": "",
    "gender": 1,
    "email": "11@yahoo.com",
    "address": "www.z4884r.com",
    "country": "ID",
    "province": "Jawa Barat",
    "ktpnumber": "",
    "phone": "+6285691953336",
    "joindate": 1008849000,
    "dateofbirth": 502045200,
    "profilevisits": 808,
    "biography": "asasas",
    "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
    "usertitle": "Kaskus Donator",
    "number_of_post": 4726,
    "total_badge": 0,
    "enable_reputation": 1,
    "reputation": 0,
    "reputation_title": "tidak memiliki reputasi",
    "is_donatur": true,
    "reputation_box": 0,
    "total_wtb": 792,
    "total_wts": 764,
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
    "lastlogin": 1450768143,
    "lastlogout": 1444102776,
    "usergroupid": "16",
    "firstname": "recca",
    "lastname": "",
    "gender": 1,
    "email": "11@yahoo.com",
    "address": "www.z4884r.com",
    "country": "ID",
    "province": "Jawa Barat",
    "ktpnumber": "",
    "phone": "+6285691953336",
    "joindate": 1008849000,
    "dateofbirth": 502045200,
    "profilevisits": 808,
    "biography": "asasas",
    "is_friend": 0,
    "is_following": 0,
    "is_ignored": 0,
    "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
    "usertitle": "Kaskus Donator",
    "number_of_post": 4726,
    "total_badge": 0,
    "enable_reputation": 1,
    "reputation": 0,
    "reputation_title": "tidak memiliki reputasi",
    "is_donatur": true,
    "reputation_box": 0,
    "total_wtb": 792,
    "total_wts": 764,
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
        "userid": "2235791",
        "username": "simonevoid",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2010\/11\/05\/male.jpg",
        "usertitle": "Administrator",
        "number_of_post": 96,
        "enable_reputation": 1,
        "reputation": 0,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "3",
        "username": "admin",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
        "usertitle": "Administrator",
        "number_of_post": 57068,
        "enable_reputation": 1,
        "reputation": 2122,
        "reputation_title": "has a brilliant future",
        "is_donatur": false,
        "reputation_box": 11
    },
    {
        "userid": "916848",
        "username": "beta tester",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/06\/08\/avatar916848_12.gif",
        "usertitle": "Administrator",
        "number_of_post": 2,
        "enable_reputation": 1,
        "reputation": 1000,
        "reputation_title": " has much to be proud of",
        "is_donatur": false,
        "reputation_box": 8
    },
    {
        "userid": "2432163",
        "username": "superman.5",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/01\/02\/male.jpg",
        "usertitle": "Administrator",
        "number_of_post": 26,
        "enable_reputation": 1,
        "reputation": 0,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "291720",
        "username": "bemp",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/06\/22\/avatar291720_1.gif",
        "usertitle": "Administrator",
        "number_of_post": 3332,
        "enable_reputation": 0,
        "reputation": 0,
        "reputation_title": "disabled reputation",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "5427",
        "username": "devil",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2002\/06\/19\/avatar5427_1.gif",
        "usertitle": "Administrator",
        "number_of_post": 188,
        "enable_reputation": 1,
        "reputation": 5,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 1
    },
    {
        "userid": "929146",
        "username": "betatester",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/06\/15\/male.jpg",
        "usertitle": "Administrator",
        "number_of_post": 18,
        "enable_reputation": 0,
        "reputation": 0,
        "reputation_title": "disabled reputation",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "5",
        "username": "template",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/avatar5_81.gif",
        "usertitle": "Administrator",
        "number_of_post": 120,
        "enable_reputation": 0,
        "reputation": 0,
        "reputation_title": "disabled reputation",
        "is_donatur": false,
        "reputation_box": 0
    },
    {
        "userid": "19624",
        "username": "cipluk",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/08\/21\/avatar19624_1.gif",
        "usertitle": "Moderator Kaskus",
        "number_of_post": 37,
        "enable_reputation": 1,
        "reputation": 5,
        "reputation_title": "tidak memiliki reputasi",
        "is_donatur": false,
        "reputation_box": 1
    },
    {
        "userid": "3666756",
        "username": "bianbiansoso",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2014\/02\/27\/male.jpg",
        "usertitle": "Administrator",
        "number_of_post": 54,
        "enable_reputation": 0,
        "reputation": 0,
        "reputation_title": "disabled reputation",
        "is_donatur": false,
        "reputation_box": 0
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
            "value": 1
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
        "child_list": "195,313,255,254,-1",
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
        "child_list": "196,216,451,450,302,449,599,600,215,257,310,311,-1",
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
        "child_list": "202,269,268,602,-1",
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
        "name": "Handphone & PDA",
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
        "child_list": "227,264,594,-1",
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
        "forum_id": "614",
        "name": "Serba Serbi",
        "description": "Jual beli aneka produk diluar kategori \/sub kategori",
        "display_order": "30",
        "parent_id": "25",
        "parent_list": "614,25,-1",
        "child_list": "614,-1",
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
        "thread_count": "113005",
        "post_count": "2906793",
        "visible": "1",
        "last_thread_id": "55824757f7cd2e6f0003d0d4",
        "last_thread_title": "Jual gitar tanpa senar",
        "last_thread_starter": "pintoco2",
        "last_post_id": "55825a66f7cd2e6f0003d0d8",
        "last_post": "1434606182",
        "last_poster": "pintoco2",
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
            "views": 217543,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2008\/09\/08\/avatar542704_1.gif",
            "usertitle": "kaskus geek",
            "number_of_post": 14126,
            "enable_reputation": 1,
            "reputation": 480,
            "reputation_title": "is a glorious beacon of light",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 5
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
            "views": 96166,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/04\/17\/avatar802441_1.gif",
            "usertitle": "kaskus addict",
            "number_of_post": 1553,
            "enable_reputation": 1,
            "reputation": 10,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2009\/04\/13\/avatar791389_1.gif",
            "usertitle": "kaskus maniac",
            "number_of_post": 4075,
            "enable_reputation": 1,
            "reputation": 6,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2008\/09\/04\/avatar540550_10.gif",
            "usertitle": "kaskus maniac",
            "number_of_post": 8702,
            "enable_reputation": 1,
            "reputation": 78,
            "reputation_title": "akan menjadi terkenal",
            "is_donatur": false,
            "is_vsl": false,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "tes jualan",
            "dateline": 1451981265,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 1,
            "views": 3,
            "post_username": "penjual",
            "post_userid": 273525,
            "first_post_id": "568b79d1c721e63b608b4569",
            "last_poster": "pembeli",
            "last_post_userid": 222745,
            "last_post": 1451981265,
            "last_post_id": "5693769a8ead0e5906cec3b1",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "testing",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 123123,
            "item_location": 11,
            "discount": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQPg",
            "sundul_enabled": 1,
            "thread_id": "568b79d1c721e63b608b4568",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 123123,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 109,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": true,
            "reputation_box": 1
        },
        {
            "forum_id": 221,
            "title": "Tes Jualan",
            "dateline": 1451981001,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 1,
            "post_username": "penjual",
            "post_userid": 273525,
            "first_post_id": "568b78c9c721e6c2598b456a",
            "last_poster": "penjual",
            "last_post_userid": 273525,
            "last_post": 1451981001,
            "last_post_id": "568b78c9c721e6c2598b456a",
            "sticky": 0,
            "prefix_id": "WTS",
            "tagsearch": "testing",
            "meta_images": [],
            "item_condition": 1,
            "item_price": 123,
            "item_location": 11,
            "discount": 0,
            "resources": {
                "images": [],
                "thumbnail": "http:\/\/cdn.kaskusplayground.local\/e3.1\/images\/default-fjb-mobile-400.png",
                "images_thumbnail": []
            },
            "short_url": "http:\/\/kask.us\/hxQPe",
            "sundul_enabled": 1,
            "thread_id": "568b78c9c721e6c2598b4569",
            "initial_prefix_id": "WTS",
            "extra_attributes": [],
            "thread_type": 21,
            "discounted_price": 123,
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 109,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": true,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2004\/02\/05\/male.jpg",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2004\/02\/05\/male.jpg",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2004\/02\/05\/male.jpg",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2010\/07\/19\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 106,
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
            "dateline": 1444293420,
            "poll_id": 0,
            "open": 1,
            "visible": 1,
            "reply_count": 0,
            "views": 12,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 109,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
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
            "views": 10,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 109,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/02\/06\/male.jpg",
            "usertitle": "newbie",
            "number_of_post": 0,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": true,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2003\/02\/06\/male.jpg",
            "usertitle": "newbie",
            "number_of_post": 0,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": true,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 109,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 109,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
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
            "usertitle": "newbie",
            "number_of_post": 17,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 109,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/04\/30\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 109,
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
            "views": 55,
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2007\/05\/12\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": 109,
            "enable_reputation": 1,
            "reputation": 1,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "is_vsl": true,
            "reputation_box": 1
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

Read fjb thread based on id. Thread rating can be calculated from vote_total and vote_num.               Rating = vote_total / vote_num.

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

Read fjb thread based on id. Thread rating can be calculated from vote_total and vote_num.               Rating = vote_total / vote_num.

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
        "views": 34914,
        "visible": 1,
        "vote_num": 18,
        "vote_total": 67,
        "is_protected": false,
        "thread_id": "53145d43a1cb17ab258b4576",
        "hot_thread": 1,
        "thread_type": 10,
        "initial_prefix_id": "",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
        "usertitle": "",
        "number_of_post": "",
        "total_badge": 0,
        "enable_reputation": 1,
        "reputation": "",
        "reputation_title": "",
        "is_donatur": false,
        "is_vsl": false,
        "reputation_box": 0
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



# Hot_thread



## Get Hot Thread Archives

Get List of Hot Thread's Archive

### HTTP Request

`GET /v1/hot_thread_archives`

Parameter | Description
--------- | -----------
q|Querying hot threads that contains some keywords in title and its first post message
date|Format: YYYY-MM-DD. Querying hot threads that have start date equals with specified date
output|output format (JSON or XML)




> Example response

```json
{
    "data": []
}
```

## Get Hot Threads

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
            "thread_id": "5445bab0ccd80665150041a9",
            "title": "ini HT 1",
            "forum_name": "THE LOUNGE",
            "forum_id": 21,
            "username": "admin",
            "user_id": 3,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1416009600,
            "hot_thread_start_date": "20141115",
            "hot_thread_end_date": "20141115",
            "hot_thread_flag": 1,
            "vote_num": 1,
            "vote_total": 4,
            "rating": 4,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/images\/2014\/03\/03\/2805907_20140303104211.jpg"
        },
        {
            "thread_id": "5445bab0ccd80665150041a9",
            "title": "ini HT 1",
            "forum_name": "THE LOUNGE",
            "forum_id": 21,
            "username": "admin",
            "user_id": 3,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1416009600,
            "hot_thread_start_date": "20141115",
            "hot_thread_end_date": "20141115",
            "hot_thread_flag": 1,
            "vote_num": 1,
            "vote_total": 4,
            "rating": 4,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/images\/2014\/03\/03\/2805907_20140303104211.jpg"
        },
        {
            "thread_id": "5445bab0ccd80665150041a9",
            "title": "ini HT 1",
            "forum_name": "THE LOUNGE",
            "forum_id": 21,
            "username": "admin",
            "user_id": 3,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1416009600,
            "hot_thread_start_date": "20141115",
            "hot_thread_end_date": "20141115",
            "hot_thread_flag": 1,
            "vote_num": 1,
            "vote_total": 4,
            "rating": 4,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/images\/2014\/03\/03\/2805907_20140303104211.jpg"
        },
        {
            "thread_id": "5445bab0ccd80665150041a9",
            "title": "ini HT 1",
            "forum_name": "THE LOUNGE",
            "forum_id": 21,
            "username": "admin",
            "user_id": 3,
            "thread_type": 10,
            "hot_thread_start_timestamp": 1416009600,
            "hot_thread_start_date": "20141115",
            "hot_thread_end_date": "20141115",
            "hot_thread_flag": 1,
            "vote_num": 1,
            "vote_total": 4,
            "rating": 4,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/images\/2014\/03\/03\/2805907_20140303104211.jpg"
        },
        {
            "thread_id": "000000000000000015114662",
            "title": "ini HT 2",
            "forum_name": "THE LOUNGE",
            "forum_id": 21,
            "username": "Furqontino",
            "user_id": 3235999,
            "thread_type": 10,
            "hot_thread_start_timestamp": 0,
            "hot_thread_start_date": "19700101",
            "hot_thread_end_date": "19700101",
            "hot_thread_flag": 1,
            "vote_num": 70,
            "vote_total": 336,
            "rating": 4.8,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "000000000000000015114662",
            "title": "ini HT 2",
            "forum_name": "THE LOUNGE",
            "forum_id": 21,
            "username": "Furqontino",
            "user_id": 3235999,
            "thread_type": 10,
            "hot_thread_start_timestamp": 0,
            "hot_thread_start_date": "19700101",
            "hot_thread_end_date": "19700101",
            "hot_thread_flag": 1,
            "vote_num": 70,
            "vote_total": 336,
            "rating": 4.8,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "000000000000000015114662",
            "title": "ini HT 2",
            "forum_name": "THE LOUNGE",
            "forum_id": 21,
            "username": "Furqontino",
            "user_id": 3235999,
            "thread_type": 10,
            "hot_thread_start_timestamp": 0,
            "hot_thread_start_date": "19700101",
            "hot_thread_end_date": "19700101",
            "hot_thread_flag": 1,
            "vote_num": 70,
            "vote_total": 336,
            "rating": 4.8,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "5451b766c721e6b409000005",
            "title": "ini HT 3",
            "forum_name": "Handphone & PDA",
            "forum_id": 210,
            "username": "simonevoid",
            "user_id": 2235791,
            "thread_type": 22,
            "hot_thread_start_timestamp": 1416067200,
            "hot_thread_start_date": "20141115",
            "hot_thread_end_date": "20141115",
            "hot_thread_flag": 1,
            "vote_num": 0,
            "vote_total": 0,
            "rating": 0,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "000000000000000015114662",
            "title": "ht 12",
            "forum_name": "THE LOUNGE",
            "forum_id": 21,
            "username": "Furqontino",
            "user_id": 3235999,
            "thread_type": 10,
            "hot_thread_start_timestamp": 0,
            "hot_thread_start_date": "19700101",
            "hot_thread_end_date": "19700101",
            "hot_thread_flag": 1,
            "vote_num": 70,
            "vote_total": 336,
            "rating": 4.8,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        },
        {
            "thread_id": "50aa107cccd806f804000006",
            "title": "ht 13",
            "forum_name": "Antik",
            "forum_id": 283,
            "username": "template",
            "user_id": 5,
            "thread_type": 20,
            "hot_thread_start_timestamp": 1413338400,
            "hot_thread_start_date": "20141015",
            "hot_thread_end_date": "20141115",
            "hot_thread_flag": 1,
            "vote_num": 0,
            "vote_total": 0,
            "rating": 0,
            "image": "http:\/\/cdn.kaskusplayground.local\/c150x100\/e3.1\/img\/default-forum-encore-n.png"
        }
    ]
}
```

# Lapak



## GET lapak

Read lapak thread based on id. Thread rating can be calculated from vote_total and vote_num.               Rating = vote_total / vote_num.

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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/02\/24\/male.jpg",
            "usertitle": "aktivis kaskus",
            "number_of_post": "36",
            "total_badge": 0,
            "enable_reputation": 1,
            "reputation": "6",
            "reputation_title": "tidak memiliki reputasi",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2011\/04\/30\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": "109",
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": "4726",
            "total_badge": 0,
            "enable_reputation": 1,
            "reputation": "0",
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": "4726",
            "total_badge": 0,
            "enable_reputation": 1,
            "reputation": "0",
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
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
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": "4726",
            "total_badge": 0,
            "enable_reputation": 1,
            "reputation": "0",
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "is_vsl": false,
            "reputation_box": 0
        }
    ],
    "cursor": "MjEwLDQsQW9KNHl0RENyODhDT0RVMVpHRmxNMlk1TnpSa09UTmhNbUl3TURoaU5Ea3dNQT09LDIxMC0yMDg"
}
```

# Smiley



## Get Smiley Categories

Get smiley groups

### HTTP Request

`GET /v1/smiley_categories`

Parameter | Description
--------- | -----------




> Example response

```json
{
    "data": []
}
```

## Get Smiley by category

Get smiley by category Id

### HTTP Request

`GET /v1/smiley/{categoryId}`

Parameter | Description
--------- | -----------
categoryId|Smiley category id



## Get Smiley Categories only for Kaskus Plus

Get smiley kaskus plus

### HTTP Request

`GET /v1/smiley_kaskus_plus`

Parameter | Description
--------- | -----------



# Thread



## GET thread

Similar with /v1/forum_thread or /v1/fjb_thread or /v1/lapak.       It returns thread detail regardless of its type. It is a little bit slower than specific thread endpoints.

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
        "views": 34914,
        "visible": 1,
        "vote_num": 18,
        "vote_total": 67,
        "is_protected": false,
        "sundul_enabled": 1,
        "thread_id": "53145d43a1cb17ab258b4576",
        "hot_thread": 1,
        "thread_type": 10,
        "initial_prefix_id": "",
        "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
        "usertitle": "",
        "number_of_post": "",
        "total_badge": 0,
        "enable_reputation": 1,
        "reputation": "",
        "reputation_title": "",
        "is_donatur": false,
        "is_vsl": false,
        "reputation_box": 0
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
    "total": "9",
    "page": 1,
    "per_page": 10,
    "total_page": 1,
    "vm": [
        {
            "vmid": 42223853,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1450410341,
            "pagetext": "haiaihaihaihihaiai",
            "messageread": "0",
            "decoded": "haiaihaihaihihaiai",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "vmid": 42223456,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1431501623,
            "pagetext": "qqqqqq",
            "messageread": "0",
            "decoded": "qqqqqq",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "vmid": 42223455,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1431501618,
            "pagetext": "helo helo helo helo",
            "messageread": "0",
            "decoded": "helo helo helo helo",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "vmid": 42223454,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1431501522,
            "pagetext": "helo helo helo helo",
            "messageread": "0",
            "decoded": "helo helo helo helo",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "vmid": 42223376,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1427103259,
            "pagetext": "mslfksdlkfjdlf",
            "messageread": "1",
            "decoded": "mslfksdlkfjdlf",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "vmid": 42223279,
            "postuserid": 3,
            "postusername": "admin",
            "dateline": 1423477023,
            "pagetext": "sampah",
            "messageread": "1",
            "decoded": "sampah",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/male.jpg",
            "usertitle": "Administrator",
            "number_of_post": 57068,
            "enable_reputation": 1,
            "reputation": 2122,
            "reputation_title": "has a brilliant future",
            "is_donatur": false,
            "reputation_box": 11
        },
        {
            "vmid": 42223263,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1422000152,
            "pagetext": "hiiii",
            "messageread": "1",
            "decoded": "hiiii",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "vmid": 42222964,
            "postuserid": 11,
            "postusername": "recca",
            "dateline": 1414487847,
            "pagetext": "blaahh\n",
            "messageread": "1",
            "decoded": "blaahh<br \/>\n",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "Kaskus Donator",
            "number_of_post": 4726,
            "enable_reputation": 1,
            "reputation": 0,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": true,
            "reputation_box": 0
        },
        {
            "vmid": 42222903,
            "postuserid": 20,
            "postusername": "jorjoran",
            "dateline": 1408436235,
            "pagetext": "halo halo bandung ibukota perhiyangan.. lalala yeyeye.. huuuuuuuuuuu",
            "messageread": "1",
            "decoded": "halo halo bandung ibukota perhiyangan.. lalala yeyeye.. huuuuuuuuuuu",
            "profilepicture": "http:\/\/cdn.kaskusplayground.local\/user\/avatar\/2001\/12\/20\/male.jpg",
            "usertitle": "newbie",
            "number_of_post": 78,
            "enable_reputation": 1,
            "reputation": 6,
            "reputation_title": "tidak memiliki reputasi",
            "is_donatur": false,
            "reputation_box": 1
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