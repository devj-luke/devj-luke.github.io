---
layout: listings
date: 2023-08-17 05:42:10 +0900
---
* toc
{:toc}

# 개요

분명히 post에 파일이 양식대로 올라가 있다.

>  YYYY-MM-DD-title.md
>
> 2023-08-17-Jekyll_Unknown _tag_오류_해결법.md

근데 제대로 출력이 되지 않는다.

왜그럴까?

# 해결시도

## 1. 새파일을 추가해보았다.

<img width="440" alt="image" src="https://user-images.githubusercontent.com/102304046/261130559-45879c7f-0cf0-497a-a523-addd17f7a8d6.png">

해봤는데 반영이 안된다.

## 2. build로그 확인

휵시나 해서 해당 레포지토리에 build 로그를 확인해보았다.

> 해당 레포지토리 Actions > pages-build-deployment > pages build and deployment 클릭

<img width="650" alt="image" src="https://user-images.githubusercontent.com/102304046/261130636-8003cf87-63ee-4e9c-a225-c0c600df83cb.png">


<img width="650" alt="image" src="https://user-images.githubusercontent.com/102304046/261130682-64a26597-bec5-466d-96a4-2a3af6a2db7d.png">

확인해보니까 해당 항목이 스킵이 된것을 확인했다.

<img width="646" alt="image" src="https://user-images.githubusercontent.com/102304046/261130804-c4c8679b-41ef-4061-9bdc-36266f974bc4.png">



# 해결

이유는 이랬다.

Jekyll는 별도로 date를 [Front Matter](https://jekyllrb.com/docs/front-matter/)로 명시하지 않을 경우 UTC+0000를 기준으로 한다.

나는 별도로 명시를 하지 않았기때문에 현재 새벽 5시 31분 기준 아직 UTC 시간은 16일이라서 스킵을 했던 것이였다.

<img width="621" alt="image" src="https://user-images.githubusercontent.com/102304046/261130857-10356043-e6f1-48be-bc6a-427149ae674e.png">

고로 시간을 지정해주니까 제대로 반영이 되었다.

``` ruby
---
layout: listings
date: 2023-08-17 02:30:00 +0900
---
```



