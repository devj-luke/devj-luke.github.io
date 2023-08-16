---
layout: listings
---

# 개요

블로그에 포스팅 하려다가 다음과 같은 에러가 났다.

> Liquid Exception: Liquid syntax error (line 34): Unknown tag 'f' in /Users/...

왜 이런 에러가 발생한것일까?



# 원인

[jykell](https://jekyllrb-ko.github.io/)은 Ruby 언어 기반으로 만들어졌는데, 여기에서 템플릿을 표현하기위한 언어로 사용하는 것이 [Liquid Tag](https://help.shopify.com/en/themes/liquid/tags) 라고 한다.
{% raw %}
작성한 마크다운 파일에  `{%` 와 `%}` 를 Liquid Tag로 인식되어서 발생한 오류였다.
{% endraw %}
# 해결

코드 예제에 포함되거나 렌더링되어야 하는 경우 `{`해당 `}`섹션을 래핑하여 `{% raw %}` `{% endraw %}`해당 섹션에 대한 Liquid 처리를 비활성화한다.
즉 일반 문자로 인식되게 감싸면 된다.

> ```
> GITHUB_TOKEN: {% raw %}${{ secrets.GITHUB_TOKEN }}{% endraw %}
> ```



# 참조

- [스타일 가이드](https://docs.github.com/ko/contributing/writing-for-github-docs/style-guide#code-blocks)
- [Github Pages의 Liquid tag 관련 빌드 오류](https://ivorycirrus.github.io/TIL/jekyll-liquid-tag-error/)