# Discord-API
<h1>디스코드 비공식 API 아바타 변경</h1>

##<h2>API BASE URL</h2>
- http://xoker.xyz/api/v1/users/avatar

|Method|설명|
|------|---|
|POST|디스코드 아바타 변경|
|GET|추가 예정|

|Query Data|설명|
|------|---|
|headers|디스코드 API 리퀘스트 헤더 커스텀 여부 / 기본값: False|

|Json Data|설명|
|------|---|
|Optional: headers|headers Query Data가 True일시 전송받은 헤더로 디스코드 API 리퀘스트 / ```꼭 Authorization 키를 포함해야합니다.``` / 기본값: False|
|token|아바타를 변경할 토큰입니다. / headers Query Data가 True일시 headers에 Authorization의 value에 넣어주세요 / ```꼭 Authorization 키를 포함해야합니다.```|
|image|전송받은 이미지로 토큰 아바타를 변경합니다. / ```이미지는 base64로 인코딩된 String을 보내주세요 Byte 전송 X```|

|Return Code|설명|
|------|---|
|200|성공했을때 반환|
|303|시간제한 / 동시에 많은 인원이 요청시 발생|
|404|토큰에 문제가 있을때 반환|
|505|올바른 JSON 데이터가 전송되지 않았을때 발생|

<h1>기본 요청 헤더</h1>
<pre>
{
        "authority": "discord.com",
        "method": "PATCH",
        "scheme": "https",
        "accept": "/",
        "accept-encoding": "gzip, deflate, br",
        "accept-language": "en-US",
        "Authorization": token,
        "content-length": "0",
        "cookie": f"cfuid={RANDOM STRING * 43}; dcfduid={RANDOM STRING * 32}; locale=en-US",
        "origin": "https://discord.com/",
        "sec-fetch-dest": "empty",
        "sec-fetch-mode": "cors",
        "sec-fetch-site": "same-origin",
        "user-agent": RANDOM USER AGENT,
        "x-context-properties": "eyJsb2NhdGlvbiI6Ikludml0ZSBCdXR0b24gRW1iZWQiLCJsb2NhdGlvbl9ndWlsZF9pZCI6Ijg3OTc4MjM4MDAxMTk0NjAyNCIsImxvY2F0aW9uX2NoYW5uZWxfaWQiOiI4ODExMDg4MDc5NjE0MTk3OTYiLCJsb2NhdGlvbl9jaGFubmVsX3R5cGUiOjAsImxvY2F0aW9uX21lc3NhZ2VfaWQiOiI4ODExOTkzOTI5MTExNTkzNTcifQ==",
        "x-debug-options": "bugReporterEnabled",
        "x-super-properties": "eyJvcyI6IldpbmRvd3MiLCJicm93c2VyIjoiRGlzY29yZCBDbGllbnQiLCJyZWxlYXNlX2NoYW5uZWwiOiJjYW5hcnkiLCJjbGllbnRfdmVyc2lvbiI6IjEuMC42MDAiLCJvc192ZXJzaW9uIjoiMTAuMC4yMjAwMCIsIm9zX2FyY2giOiJ4NjQiLCJzeXN0ZW1fbG9jYWxlIjoic2siLCJjbGllbnRfYnVpbGRfbnVtYmVyIjo5NTM1MywiY2xpZW50X2V2ZW50X3NvdXJjZSI6bnVsbH0="
    }
<pre>


