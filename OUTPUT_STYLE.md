# 코드 컨벤션 문서 작성 가이드

본 문서는 회사 코드 컨벤션 문서를 작성할 때 따라야 할 포맷과 스타일 규칙을 정의합니다.

---

## 문서 구조

### 1. 문서 헤더
컨벤션 문서는 다음 구조로 시작합니다:

```markdown
# 코드 컨벤션

> **작성일**: YYYY-MM-DD
> **최종 수정일**: YYYY-MM-DD

## 목차
- [개요](#개요)
- [Java / Spring Boot 컨벤션](#java--spring-boot-컨벤션)
- [Python / Django 컨벤션](#python--django-컨벤션)
- [공통 컨벤션](#공통-컨벤션)
...
```

### 2. 개요 섹션
```markdown
## 개요

본 문서는 Java/Spring Boot와 Python/Django 프로젝트에서 따라야 할 코딩 표준을 정의합니다.

### 목적
- 코드 일관성 유지
- 가독성 향상
- 유지보수성 증대
- 협업 효율성 개선

### 적용 범위
- **Java/Spring Boot**: API 서버 및 비즈니스 로직
- **Python/Django**: Celery 기반 배치 작업

### 기술 스택
- **Backend API**: Java 11+, Spring Boot 2.x+
- **Batch Processing**: Python 3.8+, Django 3.x+, Celery
```

### 3. 언어별 섹션 구조
문서는 언어별로 섹션을 구분하되, 하나의 파일에 통합하여 작성합니다:

```markdown
## Java / Spring Boot 컨벤션

### 네이밍 컨벤션
...

### 코드 구조
...

---

## Python / Django 컨벤션

### 네이밍 컨벤션
...

### Celery 태스크 작성
...

---

## 공통 컨벤션

### API 응답 형식
...

### 에러 핸들링
...
```

---

## 작성 규칙

### 규칙 항목 포맷

각 컨벤션 규칙은 다음 구조를 따릅니다:

```markdown
### [카테고리명]

#### [규칙명]

**설명**: [규칙에 대한 명확한 설명]

**Best**:
```[언어]
// 가장 좋은 코드 예시 (선택사항)
```

**Good**:
```[언어]
// 좋은 코드 예시 (필수)
```

**Not Bad**:
```[언어]
// 허용 가능하지만 권장하지 않는 예시 (선택사항)
```

**Bad**:
```[언어]
// 안티패턴 코드 예시 (필수)
```

**이유**: [왜 이 규칙을 따라야 하는지 설명]

**예외**: [규칙의 예외 사항이 있다면 명시]

---

## 코드 예시 작성 규칙

### 1. 예시 코드 품질
- 맥락을 이해할 수 있는 최소-충분 코드를 제공합니다
- 공통 컨벤션은 Java 로 예시 코드를 제공합니다

### 2. 예시 레벨 구분
- **Best**: 가장 이상적인 코드 (선택사항)
- **Good**: 이상적인 수준의 코드 (필수)
- **Not Bad**: 허용 가능하지만 Best/Good보다 권장하지 않는 코드 (선택사항, 필요시에만 작성)
- **Bad**: 피해야 할 안티패턴 코드 (필수)
- 최소한 **Good**와 **Bad**는 반드시 쌍으로 제공하여 차이를 명확히 합니다

### 3. 코드 블록 주석
- 안티 패턴 코드는 주석으로 이유를 작성해야 한다

**Good**:
```java
public boolean isValid() { }
public void naming() {
   Member member = getMember();
}
```

**Bad**:
```java
public void isValid() { }        // 접두사와 반환값이 맞지 않음
public void naming() {
   Member user = getMember();    // 변수명과 함수명이 일치하지 않음
}
```

---

## 섹션 구성 가이드

컨벤션 문서는 언어별 섹션과 공통 섹션으로 구성됩니다.

### 공통 컨벤션 섹션

1. **API 규칙** (Java와 Python 간 통신)
   - 요청/응답 형식
   - 에러 코드 규칙
   - 인증/인가

2. **데이터베이스**
   - 테이블/컬럼 네이밍
   - 인덱스 규칙

3. **로깅**
   - 로그 레벨 사용 기준
   - 로그 메시지 형식

4. **보안**
   - 인증 정보 관리
   - SQL Injection 방지
   - XSS 방지

### Java / Spring Boot 섹션

1. **네이밍 컨벤션**
   - 클래스명
   - 메서드명
   - 변수명
   - 상수명

2. **주석 및 문서화**
   - JavaDoc 작성 규칙
   - 인라인 주석 작성

3. **Spring Boot 특화 규칙**
   - Controller 작성
   - Service 레이어 설계
   - Repository 패턴
   - DTO/Entity 구분
   - Exception 처리

4. **모범 사례**
   - 의존성 주입
   - 트랜잭션 관리
   - 로깅
   - 보안 고려사항

### Python / Django 섹션

1. **네이밍 컨벤션**
   - 클래스명
   - 함수명
   - 변수명
   - 상수명
   - 모듈명

2. **코드 구조**
   - 모듈 구조
   - 클래스 정의 순서
   - 함수 정의 순서

3. **주석 및 문서화**
   - Docstring 작성 규칙
   - 인라인 주석 작성

4. **Django/Celery 특화 규칙**
   - Celery Task 작성
   - Task 네이밍 규칙
   - Task 인자 전달
   - 에러 핸들링 및 재시도
   - 로깅 규칙

5. **모범 사례**
   - 비동기 처리
   - 타임아웃 설정
   - 메모리 관리
   - 보안 고려사항

---

## 언어별 톤 & 매너

### 어조
- **명확하고 간결하게**: 불필요한 수식어를 피합니다
- **권위적이지 않게**: "~해야 합니다" 대신 "~하는 것이 좋습니다" 사용
- **이유 중심으로**: 규칙의 배경과 이유를 설명합니다

### 표현 가이드
- 긍정적 표현 우선: "X를 하지 마세요" → "Y를 사용하세요"
- 구체적 예시 제공: 추상적 설명보다 코드 예시 우선
- 일관된 용어 사용: 동일한 개념은 동일한 용어로 표현

---

## 문서 레이아웃

### 가독성 개선 요소

1. **적절한 공백 사용**
   - 섹션 간 구분을 위해 빈 줄 사용
   - 코드 블록 전후로 빈 줄 추가

2. **시각적 구분 요소**
   - 구분선 `---` 사용하여 대섹션 구분
   - 인용구 `>` 사용하여 중요 정보 강조
   - 표 사용하여 비교 정보 제공

3. **목록 스타일**
   - 순서가 있는 목록: `1.`, `2.`, `3.`
   - 순서가 없는 목록: `-` 또는 `*`
   - 중첩 목록은 2칸 들여쓰기

### 강조 표시

```markdown
**굵게**: 중요 키워드, 규칙명
*기울임*: 변수명, 파일명
`코드`: 인라인 코드, 명령어
> 인용구: 중요 노트, 경고 사항
```

---

## 참조 및 부록

### 외부 리소스 링크
```markdown
## 참고 자료

- [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
- [Spring Boot Best Practices](https://spring.io/guides)
- [PEP 8 – Style Guide for Python Code](https://peps.python.org/pep-0008/)
- [Django Coding Style](https://docs.djangoproject.com/en/dev/internals/contributing/writing-code/coding-style/)
- [Celery Best Practices](https://docs.celeryproject.org/en/stable/userguide/tasks.html)
```

### 용어 정의
```markdown
## 용어 사전

**camelCase**: 첫 단어는 소문자, 이후 단어의 첫 글자는 대문자로 작성하는 방식 (예: `userName`)

**PascalCase**: 모든 단어의 첫 글자를 대문자로 작성하는 방식 (예: `UserProfile`, Java 클래스명)

**snake_case**: 단어를 소문자로 작성하고 언더스코어로 연결하는 방식 (예: `user_name`, Python 변수명/함수명)

**UPPER_SNAKE_CASE**: 단어를 대문자로 작성하고 언더스코어로 연결하는 방식 (예: `MAX_COUNT`, 상수명)
```

---

## 체크리스트

컨벤션 문서 작성 완료 전 다음 사항을 확인합니다:

- [ ] 목차가 모든 주요 섹션을 포함하고 링크가 작동하는가?
- [ ] 공통 컨벤션, Java/Spring Boot, Python/Django 섹션 중 적절한 섹션에 포함되어 있는가?
- [ ] 모든 규칙에 최소한 Good과 Bad 예시가 쌍으로 제공되는가?
- [ ] 코드 예시가 간결하고 명확한가?
- [ ] 규칙의 이유가 충분히 설명되어 있는가?
- [ ] 일관된 톤과 용어를 사용하고 있는가?
- [ ] 이모지를 사용하지 않았는가?
- [ ] 자동 포맷팅으로 처리되는 규칙(import 순서 등)을 포함하지 않았는가?
- [ ] 맞춤법 및 문법 검토가 완료되었는가?

---

## 예시 템플릿

### Java 규칙 항목 예시

```markdown
### 변수 선언

#### final 키워드를 적극 활용한다

**설명**: 재할당이 없는 변수는 `final` 키워드를 사용하여 불변성을 명확히 하고, 의도치 않은 재할당을 방지합니다.

**Good**:
```java
public void example() {
    final String sample = getSample();
}
```

**Bad**:
```java
public void example() {
    String sample = getSample();    // 재할당 가능
}
```

**이유**:
- `final` 키워드는 변수의 불변성을 컴파일 타임에 보장합니다
- 코드 리뷰 시 변수의 의도를 명확히 파악할 수 있습니다
- 멀티스레드 환경에서 안전성을 높입니다

**예외**: 루프 카운터 등 명백히 재할당이 필요한 경우는 `final`을 사용하지 않습니다.
```


### Python 규칙 항목 예시

```markdown
### Celery Task 작성

#### Task는 멱등성을 보장해야 한다

**설명**: Celery Task는 같은 인자로 여러 번 실행되어도 동일한 결과를 보장해야 하며, 중복 실행에 대비한 처리가 필요합니다.

**Good**:
```python
from celery import shared_task
from django.db import transaction

@shared_task
def process_payment(order_id):
    """결제 처리 Task - 멱등성 보장"""
    with transaction.atomic():
        # select_for_update로 동시성 제어
        order = Order.objects.select_for_update().get(id=order_id)

        # 이미 처리된 주문은 스킵
        if order.status == 'paid':
            return {'status': 'already_processed', 'order_id': order_id}

        # 결제 처리
        order.status = 'paid'
        order.save()

        return {'status': 'success', 'order_id': order_id}
```

**Not Bad**:
```python
@shared_task
def process_payment(order_id):
    """상태 확인은 하지만 동시성 제어 미흡"""
    order = Order.objects.get(id=order_id)

    if order.status == 'paid':
        return

    # Race condition 발생 가능
    order.status = 'paid'
    order.save()
```

**Bad**:
```python
@shared_task
def process_payment(order_id):
    """멱등성 미보장 - 중복 실행 시 문제 발생"""
    order = Order.objects.get(id=order_id)

    # 상태 확인 없이 무조건 처리
    order.status = 'paid'
    order.save()

    # 중복 실행 시 중복 결제 발생 가능
    charge_customer(order.amount)
```

**이유**:
- Celery는 네트워크 장애 등으로 Task가 중복 실행될 수 있습니다
- 멱등성을 보장하지 않으면 데이터 불일치나 중복 처리가 발생합니다
- 트랜잭션과 상태 확인을 통해 안전한 Task 실행을 보장해야 합니다

**예외**: 읽기 전용 Task나 로깅 Task 등 부작용이 없는 경우는 간소화할 수 있습니다.
```

---

## 주의사항

1. **과도한 규칙 지양**: 실질적으로 도움이 되는 규칙에 집중합니다
2. **맥락 고려**: Java/Spring Boot와 Python/Django의 특성을 고려한 규칙을 작성합니다
3. **자동화 도구와 중복 방지**: 자동 포맷팅(import 순서, 들여쓰기 등)으로 처리되는 규칙은 문서에 포함하지 않습니다
4. **이모지 사용 금지**: 모든 표시는 텍스트(Best, Good, Not Bad, Bad)로 명시합니다
5. **언어 특화 규칙 강조**:
   - Java/Spring Boot: Controller, Service, Repository 패턴
   - Python/Django: Celery Task의 멱등성, 재시도, 타임아웃

---

**이 문서 자체도 위 규칙을 따라 작성되었습니다. 서브 에이전트는 이 스타일 가이드를 참조하여 일관성 있는 코드 컨벤션 문서를 생성해야 합니다.**
