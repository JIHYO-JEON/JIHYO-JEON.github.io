---
layout: post
title: "Pythonic Way: The Zen of Python"
date: 2020-07-30 20:46:00
tags: [python]
---

파이썬은 Pythonic Way, 파이썬다운 방식이라는 고유한 철학이 있다. 파이썬에서는 The Zen of Python이라는 이름으로 부르고 있다.
import this 명령어를 통해 Tim Peters가 정의한 The Zen of Python을 출력할 수 있다.

{% highlight ruby linenos %}
>>> import this

The Zen of Python, by Tim Peters
Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
{% endhighlight %}

요약하자면 단순하고 명시적이고 가독성이 좋은 아름다운 코드를 구현하라는 것인데... 실행할 수 있는 수도코드라고 불리는 파이썬에게
아주 잘 어울린다. The Zen of Python에서 말하는 코드를 구현하는 것은 어렵지만, 개발은 혼자하는 일이 아니므로 좋은 코드를 쓰는 것은 아주 중요하다.
좋은 코드는 누구나 쉽게 이해하고 수정 및 추가할 수 있는 단순, 명료한 코드를 말한다. 영어로는 Clean Code라고 한다.
코드의 로직이 서로 얽혀있는 스파게티 코드 등 복잡하고 이해하기 어려운 코드는 나쁜 코드, Bad Code라고 한다. 왜 Dirty Code가 아닌지 모르겠다.

우리의 파이썬은 클린코드 작성을 위해서 PEP, Python Enhancement Proposals 중 코딩 스타일 가이드인 PEP8을 통해 파이썬 나름의 규칙을 정해주었다.
PEP8을 잘 지켜주면 조금 더 본새나는 코드를 작성할 수 있다.


