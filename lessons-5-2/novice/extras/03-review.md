---
layout: lesson
root: ../..
title: 코드 리뷰 (Code Review)
---

소프트웨어 품질을 향상하는 방법은 많이 있다. 가장 효과적인 방법이 
[코드 리뷰(code review)](../../gloss.html#code-review)다.
GitHub은 프로젝트 내부에서 혹은 프로젝트 사이에 코드 리뷰를 촉진하기 위해서 [풀 요청(pull request)](../../gloss.html#pull-request)을 사용한다.

풀 요청은 한 [브랜치(branch)](../../gloss.html#branch)에서 또 다른 브랜치로 병합을 제안하는 방법이다. 브랜치가 동일한 저장소 혹은 같은 프로젝트의 다른 [포크(forks)](../../gloss.html#fork)에 있을 수 있다.
본 학습은 다른 사람들과 효과적으로 일하는 방법에 대한 [Git 브랜치](../extras/01-branching.html) 심화 과정이다.

드라큘라 프로젝트에 기여하고자 로컬 브랜치에 변경사항을 만든 늑대인간의 경우를 다시 살펴보자. GitHub에 변경사항을 만들어 브랜치에 푸쉬한다. 원래 저장소에 변경사항을 푸쉬하거나 만약 원래 저장소에 접근할 수 없다면 포크에 푸쉬한다.
그리고 나면 늑대인간은 웹브라우저의 저장소 페이지를 로드하고, 풀 요청을 할 수 있다. 만약 늑대인간이 몇분 내에 풀 요청을 한다면, 최근에 변경된 브랜치가 풀 요청을 할수 있는 버든과 함께 저장소 헤더에 눈에 돋보이게 표시된다.

<img src="img/github-recently-pushed-branches-ui.png" alt="recently pushed branches are highlighted in the UI" />

만약 늑대인간이 더 이상 눈에 돋보이지 않게 된 브랜치에 풀 요청을 하고자 한다면, 모든 브랜치의 전반적인 상황을 로드하는 저장소 헤더의 링크를 사용할 수 있다.

<img src="img/github-summary-header.png" alt="the repository header fields are links" />

브랜치 개요에서 각 브랜치별로 버튼이 있어서 풀 요청을 할 수 있다.

<img src="img/github-branch-ui.png" alt="an individual branch row" />

드라큘라가 풀 요청을 온라인에서 봤을 때, 늑대인간이 바꿀려고 하는 변경 사항을 볼 수 있다. 드라큘라는 코멘트를 코드 각 라인별로 남기거나, 늑대인간에게 피드백을 주기 위해서 광범위한 풀 요청에 코멘트를 할 수 있다. 
늑대인간이 로컬 코드에 변경을 하고 브랜치에 푸쉬할 수도 있다. 풀 요청이 자동으로 변경사항을 반영하여 갱신한다.

풀 요청에 대해서 받는 피드백이 아주 폭넓거나 혹은 최소일 수도 있다.
처음에는 스타일적인 요소에 초점이 맞춰질 수도 있다 -- 어디에 줄 바꿈을 넣는지, 변수에 대한 작명 규칙, 혹은 관용법에 맞는 코드 변환.
나중에는 구현을 다룰 수도 있다 - 코드가 함수와 모듈로 어떻게 구조화되는지.
중요하게, 검토자는 작업한 것을 좀더 작게, 논리적인 조각으로 나누어 다시 작성하도록 요청도 한다. 이런 변경 사항이 검토를 쉽게 하고, 프로젝트와 통합하기 쉽고, 버그를 덜 생성하게 한다.

코드를 리뷰하는 것은 더 복잡할 수 있다. 코드 리뷰 작업을 도와주는 도구는 많이 있다. 소프트웨어 린트(lint)는 코드가 스타일을 따르는지 확인하는 도구다. 자동 테스트는 이전 버그가 다시 재현되지 않도록 보장한다. 하지만, 어떠한 도구도 동료에 의한 주의깊은 검토를 받는 것만큼 효과적이지는 않다.
변경사항을 읽어가면서 뜻밖의 원천을 찾아서 세밀히 조사하는 것이 좋은 경험적 방법(heuristics)이다. 
리뷰는 초기에 코드를 작성하는 것보다 더 어렵고, 검토자는 한시간 검토 뒤에는 급격하게 효율성이 저하된다. 코드 라인숫자는 패치(patch)를 검토하는데 얼마나 오래 시간이 걸리는지에 대한 좋은 근사치가 된다.

대체로 훨씬 더 빠르지만, 프로세스가 과학 출판의 동료 검토와 유사하다.
규모가 큰 공개 소프트웨어 프로젝트에서, 최종적으로 승인되어 병합되기 전에 풀 요청이 수차례 갱신되는 것은 매우 흔하다.
이와 같은 작업 방식은 코드의 품질을 유지할 뿐만 아니라, 지식을 전달하는 매우 효과적인 방식도 된다.

늑대인간은 첫번째 변경사항에 대한 검토를 기다리는 동안에, 로컬 저장소에 새로운 브랜치를 생서해서 작업을 계속할 수 있다.
새로운 브랜치에서 새로운 변경사항을 만들고, GitHub에 푸쉬하고, 두번째 풀 요청을 보낸다. 이것이 Git, Mercurial 그리고 다른 최신 버젼 제어 시스템이 브랜치를 사용하는 중요한 방식이다.
드라큘라가 늑대인간의 변경사항을 검토하는데 몇일이 소요될 것이다.
검토가 완료될 때까지 정지하기 보다, 늑대인간은 다른 브랜치로 전화해서 다른 작업을 한고, 드라큘라의 검토가 최종적으로 도착했을 때, 다시 원래의 작업으로 전환한다. 드라큘라가 변경사항이 마음에 들고, 자신의 프로젝트와 병합하고자 한다면, 버튼을 클릭해서 작업을 완료할 수 있다.

<img src="img/github-merge-ui.png" alt="Merging a Pull Request" />

변경사항이 특정 브랜치에 승인되고, `master` (혹은 다른 브랜치)에 병합되자마자, 
늑대인간은 브랜치를 삭제할 수 있다. 변경사항 자체는 병합되는 곳에 보존된다.