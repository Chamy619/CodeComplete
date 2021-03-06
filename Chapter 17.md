# 17장 특이한 제어 구조

**목차**

- **17.1 여러 곳에서 반환하는 루틴**
- **17.2 재귀문**
- **17.3 goto 문**
- **17.4 특이한 제어 구조에 대한 관점**

## 17.1 여러 곳에서 반환하는 루틴

**return 문 사용 시 참고할 가이드**

- 더 읽기 쉬운 코드를 만들기 위해서 return을 사용하라.
- 복잡한 오류 처리를 단순화하기 위해서 보호절(루틴 중간에 사용되는 return 이나 exit)을 사용하라.
- 한 루틴에 있는 리턴의 수를 최소화하라.

## 17.2 재귀문

**재귀 호출 사용 팁**

- 재귀 호출이 중단되는지 확인하라.
- 무한 재귀 호출을 막기 위해서 안전 카운터를 사용하라.
- 한 루틴으로 재귀 호출을 제한하라.
- 스택을 감시하라.
- 팩토리얼이나 피보나치 수열을 계산하기 위해서 재귀문을 사용하지 말라.

## 17.3 goto 문

**goto 문 사용 가이드라인**

- 구조적인 제어 구현을 직접 지원하지 않는 언어에스는 그러한 구조를 흉내 내기 위해서 goto 문을 사용하라. goto 문을 사용할 때는 정확하게 흉내낸다. goto 문의 유연성을 남용하지 않도록 한다.
- goto 문과 같은 기능을 다른 방법으로 구현할 수 있을 때는 goto 문을 사용하지 않는다.
- 효율성을 높이기 위해 사용된 goto 문의 성능을 측정하라. 대부분의 경우 읽기 쉽고 효율성도 떨어지지 않는 코드를 goto 문 없이 재작성할 수 있다. 예외적인 경우라면 성능 향상에 대한 기록을 남겨 goto를 사용하지 않는 개발자가 goto 문을 봤을 때 제거하지 않도록 한다.
- 구조적인 구현을 흉내 내는 것이 아니라면 한 루틴에 하나의 goto 레이블만 사용한다.
- 구조적인 구현을 흉내내는것이 아니라면 goto 문이 뒤로 후퇴하지 않고 앞으로 전진만 하도록 한다.
- 모든 goto 레이블이 사용되었는지 확인한다. 사용되지 않은 레이블이 있다는 것은 해당 레이블로 이동하는 코드가 빠졌다는 것을 의미한다. 레이블이 사용되지 않는다면 그 레이블을 삭제한다.
- goto 문으로 인하여 접근되지 않는 코드가 만들어지지 않았는지 확인한다.
- 관리자는 goto 문 하나에 매달리다가 전체를 망칠 수도 있다는 점을 명심해야 한다. 개발자가 다른 대안을 알면서도 goto를 사용하려고 한다면 아마 그 goto 문은 문제가 없을 것이다.

## 17.4 특이한 제어 구조에 대한 관점

> 소프트웨어 개발 분야는 개발자가 코드를 이용할 수 있는 것을 제한함으로써 크게 발전했다. 새인적으로는 자유로운 제어 구조에 강한 회의를 느낀다. 이 장에서 소개한 대부분의 구조가 결국에는 계산된 goto 레이블이나 변수 루틴 진입점, 자기 수정 코드, 구조에 대한 유연성과 편리함과 복잡성을 다루기 위한 능력을 선호하는 다른 구조들처럼 개발자들로부터 외면당할 것이라고 생각한다.
