# 6장. 클래스 다루기

**목차**

- **6.1 클래스의 토대: 추상 데이터형(ADT)**
- **6.2 좋은 클래스 인터페이스**
- **6.3 설계와 구현에 관한 이슈**
- **6.4 클래스를 작성하는 이유**
- **6.5 프로그래밍 언어에 특화된 이슈**
- **6.6 클래스를 넘어서: 패키지**

## 6.1 클래스의 토대: 추상 데이터형

> 객체지향 프로그래밍을 이해하기 위해서는 ADT를 반드시 이해해야 한다. ADT를 이해하지 못하고서는 이름만 클래스인 클래스를 작서앟게 될 것이다. 그런 클래스는 실제로는 연관성이 높지 않은 데이터와 루틴을 편의를 위해 보관하는 상자와 다를 게 없다.

ADT를 사용하면 구현 세부 사항을 감출 수 있고, 변경이 전체에 영향을 미치지 않게 할 수 있다.
실제 존재하는 객체를 다룰 수 있게 해주기 때문에 ADT는 개발을 하는데 상당한 편의를 가져다 줄 수 있다. 예를 들어 스택을 만들 때, ADT는 add, pop, top, reset 4가지 기능만 보여주도록 해 사용자와 개발자 모두에게 이것만 신경쓸 수 있는 환경을 제공할 수 있다.

## 6.2 좋은 클래스 인터페이스

```
// 추상화를 잘 나타낸 클래스 인터페이스를 C++로 작성한 예제
class Emplyee {
    public:
        Employee();
        Employee(
            FullName name,
            String address,
            String workPhone,
            String homePhone,
            TaxId taxIdNumber,
            JobClassification jobClass
        );
        virtual ~Employee();
        // 공개 루틴
        FullName GetName() const;
        String GetAddress() const;
        String getWorkPhone() const;
        String GetHomePhone() const;
        TaxId getTaxIdNumber() const;
        JobClassification GetJobClassification() const;
        ...
    private:
        ...
};
```

> 이 클래스는 외부에 노출된 인터페이스 외에도 내부적인 작업을 처리하기 위해 여러 루틴과 데이터를 가지고 있겠지만, 클래스의 사용자는 그러한 부분에 대해 전혀 알 필요가 없다. 인터페이스에 있는 모든 루틴이 긴밀하게 연관되어 있어서 훌륭한 추상화를 제공하고 있다.
