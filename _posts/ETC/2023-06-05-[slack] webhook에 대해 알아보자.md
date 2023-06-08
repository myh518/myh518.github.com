---
layout: post
title: '[slack] webhook에 대해 알아보자!'
excerpt: slack의 기능 중 webhook에 대해 알아보자
category: ETC
tags:
  - slack
  - webhook
  - app
---

## 이 포스트에서는 slack에서 webhook을 사용하는 방법을 알아보겠습니다.

우선 [slack 공식 사이트](https://slack.com/intl/ko-kr/trials?remote_promo=f4d95f0b&d=7013y000002pzFBAAY&nc=7013y000002pznPAAQ&utm_source=google&utm_medium=paid_search&utm_campaign=ppc_google_apac_kr_kr_brand_selfserve_discount&utm_content=slack-pg-ss-all-kr-brand_7013y000002pzFBAAY&utm_term=slack_exact_._slack_._e_._c_._659249920207&gad=1&gclid=CjwKCAjw-IWkBhBTEiwA2exyO2zerhUghFn_I7SxfLswuwmGpucgR4-rzgT9IQ-0RXvUVEQ09mURRRoCB1AQAvD_BwE&gclsrc=aw.ds)에 접속해 줍니다.

로그인 후 아래의 그림처럼 새 워크 스페이스 개설을 눌러줍니다.  
<img src="/img/webhook/slackweb.png">

- - -

여기서부터 시키는대로 하고요

<img src="/img/webhook/workspacename.png">

여기서는 워크스페이스의 이름을 설정해 주시면 되고요

<img src="/img/webhook/work.png">

여기서는 채널을 추가하는것입니다.(나중에도 더 추가할 수 있어요)

<img src="/img/webhook/email.png">

이곳에서는 다이렉트 메세지를 나눌, 이 워크스페이스에 들어오게 할 사람의 이메일을 적으시면 됩니다

<img src="/img/webhook/slackready.png">

여기까지 하셨다면 이런창이 뜨실건데요.  
알아서 하시면 되시고요, 
저는 무료버전으로 했습니다.

<img src="/img/webhook/slackmain.png">
이제 워크스페이스 준비는 끝났습니다.

# 👏👏

이제 webhook을 준비 및 테스트해 봅시다.

우선 [이곳](https://api.slack.com)으로 접속해 줍니다.

로그인이 안되어있다면 하시고  
아래의 이미지와 같이 Your apps를 클릭해 줍니다

<img src="/img/webhook/slackappweb.png">

클릭했다면 아래와 같은 창이 뜰건데요.

<img src="/img/webhook/appcreate.png">
빨갛게 표시된 부분을 클릭해주시면 되겠습니다.
<img src="/img.webhook/">
