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

# 이 포스트에서는 slack에서 webhook을 사용하는 방법을 알아보겠습니다.
## 1.워크스페이스 개설
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

## 2.Webhook

우선 [이곳](https://api.slack.com)으로 접속해 줍니다.

로그인이 안되어있다면 하시고  
아래의 이미지와 같이 Your apps를 클릭해 줍니다

<img src="/img/webhook/slackappweb.png">

클릭했다면 아래와 같은 창이 뜰건데요.

<img src="/img/webhook/appcreate.png">
빨갛게 표시된 부분을 클릭해주시면 되겠습니다.
<img src="/img/webhook/apppick.png">
그 다음에 위 사진에 표시되어있는 부분을 클릭하시면
<img src="/img/webhook/appname.png">
이런 창이 뜰 것입니다.  
여기서는 사진과 같이 해주시면 됩니다.  
여기까지 하셨다면 이제 webhook기능을 선택해주셔야합니다.  
<img src="/img/webhook/pickwebhook.png">
사진과 같이 Incoming Webhooks를 선택해주시면
<img src="/img/webhook/onoff.png">
위와 같은 창이 뜨게 될것인데요,  
여기서는 사진과 같이 off로 되어있는 버튼을 on으로 바꾼 뒤  
Add New Webhook to Workspace 라고 적혀있는 버튼을 눌러주시면 됩니다.
<img src="/img/webhook/channalpick.png">
이제 선택했던 워크스페이스의 채널 중 webhook을 적용시킬 채널을 선택해주세요
<img src="/img/webhook/webhookwin.png">
자 이제 끝났습니다.  
테스트 해 볼까요?


## 3.테스트

자 테스트를 위해 파이썬에 아래와 같은 코드를  
작성해 주겠습니다

{% highlight css %}
import json
import requests
 
webhook_url = "웹훅 주소를 입력"
content = "WebHook Test"
payload = {"text": content}
 
requests.post(
    webhook_url, data=json.dumps(payload),
    headers={'Content-Type': 'application/json'}
)
{% endhighlight %}

여기서 webhook_url에는 
<img src="/img/webhook/webhookwin.png">
이 사진에서 Webhook url을 카피해서 붙여넣어 주시면 됩니다  
이렇게 해서 실행시켜주면
<img src="/img/webhook/webhooktest.png">
이렇게 놀랍게도 직접 채팅을 치지 않아도  
webhook 앱이 알아서 채팅을 써줍니다!  

그러므로 예를 들어
{% highlight css %}
import json
import requests
webhook_url = "웹훅 주소"
content = "Error"
payload = {"text": content}
while True:
    try:
        a=4
        b=0
        c=a%b
    except:
        requests.post(
            webhook_url, data=json.dumps(payload),
            headers={'Content-Type': 'application/json'}
        )
        break
{% endhighlight %}
이러한 코드가 있다고 치면  
오류가 뜰시 slack으로 메세지가 가게 할수 있다는 것입니다!

여기까지 slack을 통해 webhook을 써보았고요.  
감사합니다.  
안녕히계세요.
