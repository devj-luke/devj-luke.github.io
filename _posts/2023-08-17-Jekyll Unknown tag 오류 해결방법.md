---
layout: listings
date: 2023-08-17 02:30:00 +0900
---
* toc
{:toc}

# 개요

블로그에 포스팅 하려다가 다음과 같은 에러가 났다.

> Liquid Exception: Liquid syntax error (line 34): Unknown tag 'f' in /Users/...

왜 이런 에러가 발생한것일까?


{% raw %}
# 원인
[jykell](https://jekyllrb-ko.github.io/)은 Ruby 언어 기반으로 만들어졌는데, 여기에서 템플릿을 표현하기위한 언어로 사용하는 것이 [Liquid Tag](https://help.shopify.com/en/themes/liquid/tags) 라고 한다.

작성한 마크다운 파일에서  `{%` 와 `%}` 가 들어가는 문자열을 사용할 때 Liquid Tag로 인식되어서 발생한 오류였다.
{% endraw %}

# 해결

그냥 간단하게 {% raw %}{%{% endraw %} raw %} {% raw %}{%{% endraw %} endraw %}로 감싸주면 된다.

> ```
> GITHUB_TOKEN: {% raw %}{%{% endraw %} raw %}${% raw %}{{{% endraw %} secrets.GITHUB_TOKEN }}{% raw %}{%{% endraw %} endraw %}
> ```

# 참조

- [스타일 가이드](https://docs.github.com/ko/contributing/writing-for-github-docs/style-guide#code-blocks)
- [Github Pages의 Liquid tag 관련 빌드 오류](https://ivorycirrus.github.io/TIL/jekyll-liquid-tag-error/)
- [[짧은글] Liquid 코드 그대로 출력하기](https://chaelin1211.github.io/study/2021/02/24/liquid-code.html)