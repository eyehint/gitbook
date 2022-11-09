# 등록 / 삭제 결과 확인

## GET /progress/register/{register\_id}

서브 기기 등록/삭제 요청이 완료되었는지 확인하기 위한 API입니다. 등록/삭제 요청에 대한 응답 메세지에 포함된 [registerId](post-devices.md#response)를 사용하여 요청합니다.



**Request**

> **URL** : http://{device\_ip}:5003**/progress/register/{register\_id}**
>
> **METHOD** : <mark style="color:purple;">**GET**</mark>
>
> **Header**&#x20;
>
> * None
>
> **Parameter**
>
> * None

#### Response

> Type: Object
>
> * resultCode (String) <mark style="color:red;">\*</mark>: API 수행 결과 코드 값
> * result (Object) <mark style="color:red;">\*</mark> : 등록 결과 정보
>   * state (String) <mark style="color:red;">\*</mark> : 등록 진행 상황을 나타냄. 성공이면 "SUCCESS"가 돌아옴
>   * result (String) <mark style="color:red;">\*</mark> : 등록 결과로 기기가 리턴한 정보

#### Response Example

```

{
    "resultCode": "0000",
    "result": {
        "state": "SUCCESS",
        "result": "None"
    }
}
```
