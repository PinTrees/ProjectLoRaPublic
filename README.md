# 프로젝트 로라 요약 기획서

프로젝트 “로라”는 “뱀파이어 서바이벌”과 “앤터 더 건전”에서 영감을 받아 개발중인 2D 도트 그래픽 게임입니다. 게임은 WinAPI를 이용하여 PC(Windows) 플랫폼에서 플레이할 수 있도록 개발되었으며, 이진교(팀장), 조민기(엔진), 이호준(프로그래머)으로 구성된 개발팀이 참여합니다.

개발 정보
개발 엔진: WinAPI
플랫폼: PC (Windows)
그래픽: 2D 도트 그래픽 (에셋 사용)
개발인원: 이진교(팀장), 조민기(엔진), 이호준(프로그래머)


## 게임 특징
1. 로그라이크
- 사방에서 몰려오는 적들을 죽이고 살아남는 게임이며, 보물상자와 레벨업을 통해 능력치를 랜덤으로 강화합니다.
2. 다양한 몬스터
- 플레이어 주변에서 몬스터들이 생성되어 압박을 가합니다. 높은 능력치를 가진 플레이어는 적들을 효과적으로 처치할 수 있으며, 생존 순간의 긴장감과 강력한 능력으로 적들을 쓸어버리는 타격감이 게임의 주요 요소입니다.
3. 타격감
- 플레이어는 총기를 사용하여 게임을 플레이 합니다. 게임 내의 총기 조작과 몬스터화의 타격감을 중점으로 개발될 예정입니다.
4. 효과
- 총알의 이펙트는 게임 내에서 오랜 시간동안 보여지게 되는 요소이므로, 매우 중요하게 고려되고 개발될 예정입니다.


## 게임 플레이 방식
1. 솔로플레이
- 이 게임은 솔로 플레이로 진행됩니다.
2. 난이도
- 적들의 체력, 플레이어의 공격력, 생성 속도, 적의 종류 등을 차등 적용하여 3개의 난이도 옵션을 고려중입니다.
3. 조작
- 캐릭터는 WASD를 사용하여 이동하며, 마우스 위치를 향해 총을 겨누고 좌클릭으로 발사합니다. 우클릭으로 대쉬 기능을 사용할 수 있습니다.
4. 능력치
- 플레이어는 공격력, 체력, 명중도(발사각), 경험치 등의 능력치를 가지고 있습니다.
5. 총 능력치
- 총기는 공격력, 공격 속도, 장전 수, 장전 속도, 탄의 공격력, 탄 개수(발사 시 탄 개수), 발사 각도 등으로 구성됩니다.
6. 무기
- 기본 무기는 모두 총기로 구성되어 있으며, 다른 아이템이나 무기는 추가 고려사항 입니다.


## 코딩 스탠다드

## 기본원칙

1. 가독성
3. 자동완성 서식 준수 Ctrl + K + D

## 기초 코딩 표준

1. 클래스와 구조체의 이름에 파스칼 표기법 사용
```c++
class DatabaseManager
struct Vector2Int
```

2. 함수 내 지역변수 및 함수 매개변수에 카멜 표기법 사용
```c++
void Print(const int dataInfo)
{
  int dataIndex;
}
```

3. 함수의 이름은 동사를 선 작성 한다
```c++
void PlaySound();
```

4. 퍼블릭 함수에 파스칼 표기법 사용
```c++
public:
  void PlaySound();
```

5. 프라이빗 함수에 카멜 표기법 사용
```c++
private:
  void normalize();
```
   

7. 외부 변수가 동일한 이름을 사용중이라면 내부 변수에 _ 추가
```c++
class Class
{
private:
    int count;
public:
    void Func(const int _count)
    {
        count = _count;
    }
}
```

6. 상수 또는 #define 으로 정의된 변수의 이름은 대문자 언더바 표기법 사용
 ```c++
const int MAX_COUNT = 1;
#define MAX_LENGTH 50
```

6. 클래스 내부 멤버 변수명은 앞에 m 표기.
```c++
 class Item
 {
 protected:
     int mID;
 private:
     string mName;
 }
```

8. bool 변수는 앞에 b 사용
 ```c++
bool bDeath;	
bool isDeath;
```

8. 인터페이스를 선언할 때는 앞에 I 표기
 ```c++
class IComponent
```

9. 클래스 멤버 변수에 접근할 때는 항상 setter와 getter를 사용.
```c++
class Employee
{
private:
    string mName;
public:
    const string& GetName() const;
    void SetName(const string& name);
}
```

10. 인클루드 순서
 ```c++
#pragma once
#include <vector>
#include <stdlib.h>

#include "GameObject.h"
```

11. 가능한 모든 경우에 NULL 대신 nullptr 사용
 ```c++
Cobject* data = nullptr;
```

### 코드 포멧
1. 중괄호( {} )
 ```c++
class Data
{
}

if (true)
{

}

// Get Set 예외
public int GetInt() {}
```

2. 포인터나 참조 기호는 자료형 뒤에 표기
```c++
int&  number;
int*  number;
```

3. nullptr 비교연산은 항상 nullptr을 우선 작성한다.
```c++
if(nullptr == data)
{
}
```

### 함수
1. 함수의 명확한 행동 정의
2. cont 사용
```c++
const Monster* GetMonsterByIndex(const int index) const;

// 명확하지 않은 함수 이름
bool CheckHp();

// 명확한 함수 이름
bool IsDeath();
```

3. 함수에서 매개변수를 통해 값을 반환할 때(out 매개변수)는 포인터를 사용하며, 매개변수 이름 앞에 out_을 표기
```c++
void GetSceneSize(int* out_width, int* const out_height)
{
}
```

### Class
1. 생성자 작성법
2. 각 라인당 하나의 변수 초기화
```c++
MyClass::MyClass(const int var1, const int var2)
   : mVar1(var1)
   , mVar2(var2)
   , mVar3(0)
{
}
```


### Enum

1. 항상 enum class 를 사용.
2. enum 앞 E 표기.
 ```c++
enum class EDirection
{
    Top,
    Bottom,
    Left,
    Right
}
```

