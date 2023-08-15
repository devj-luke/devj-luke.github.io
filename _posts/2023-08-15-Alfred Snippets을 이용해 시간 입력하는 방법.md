---
layout: listings
---

# 개요

파일을 작성할때 보통 시간을 입력하는 편이다.

왜냐면 파일의 정보가 날라간 경우 , 파일 자체에 생성 시간을 가지고 있으면 그것을 참고하면 되기 때문이다.

<img width="196" alt="image" src="https://user-images.githubusercontent.com/102304046/260749696-aec09b0c-fd3c-428a-9d1a-1b9f94de97c5.png">

매번 이걸 입력을 할려니깐 귀찮았고 방법을 찾아서 기록해둔다.



# 방법

### 1. alfred에 스니펫 추가

<img width="756" alt="image" src="https://user-images.githubusercontent.com/102304046/260748987-0dace6b3-14de-4d1f-a6ce-54b5fd32213c.png">

``` shell
{isodate:`yyyy.MM.dd. a hh:mm:ss`}
```

마크다운에서 코드 스펜으로 둘러싸서 입력해도 문자로만 입력 되게 만들었다.

보이지도 않아서 좋았다.



# 참조

- [동적 자리 표시자](https://www.alfredapp.com/help/workflows/advanced/placeholders/)
  - 앵간한건 여기 설명이 있다.
- [날짜/시간 마스크 및 형식 지정자](https://www.ibm.com/docs/ko/rbd/9.5.1?topic=parts-datetime-masks-format-specifiers)
  - 해당 문서에서 PM/AM 하는 서식을 찾았다.