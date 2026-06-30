# Algo Lecture Coach

BaaaaaaaarkingDog 실전 알고리즘 강의 링크, GitHub 문제집, 코딩테스트 문제, 사용자 코드를 Java 기반 학습 자료로 바꿔주는 Codex 스킬입니다.

## 하는 일

- 알고리즘 강의 링크를 코딩테스트용 학습 계획으로 재구성합니다.
- 문제에서 어떤 알고리즘 유형을 떠올려야 하는지 신호를 정리합니다.
- Java 구현 패턴, 자주 하는 실수, 필수 문제를 우선순위로 제공합니다.
- BaaaaaaaarkingDog 커리큘럼 기준 10일 압축 학습 계획을 지원합니다.
- 사용자의 Java/구현/알고리즘 인식 수준을 진단하고 시작 단원을 추천합니다.
- 사용자 Java 코드를 정답성, 시간복잡도, 반례, 최소 수정 방향 중심으로 리뷰합니다.
- 암기용 Java 문법과 구현 템플릿을 따로 정리합니다.

## 구성

```text
SKILL.md
agents/openai.yaml
references/roadmap-10-days.md
references/level-assessment.md
references/output-contract.md
references/problem-review-rubric.md
references/java-syntax-patterns.md
```

## 사용 방법

이 폴더를 Codex skills 디렉터리에 설치하거나 복사한 뒤 다음처럼 호출합니다.

```text
Use $algo-lecture-coach to turn this algorithm lecture link into a concise Java coding-test study plan.
```

예시:

```text
Use $algo-lecture-coach https://blog.encrypted.gg/941 이 BFS 강의를 Java 기준으로 빠르게 학습하게 정리해줘.
```

## 기본 정책

- 기본 응답 언어: 한국어
- 기본 구현 언어: Java
- C++ 코드는 명시적으로 요청하지 않으면 제공하지 않음
- 원문 요약보다 문제 풀이에 바로 쓰는 학습 루틴을 우선함
