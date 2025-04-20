<!--
Meta Description: # Tcl의 dict: 키-값 쌍을 다루는 강력한 데이터 구조 ## 개요 Tcl의 `dict`는 키-값 쌍을 저장하고 조작하는 데 사용되는 강력한 데이터 구조입니다. 해시 맵과 유사하게 작동하여, 데이터를 효율적으로 조회하고 수정할 수 있는 기능을 제공합니다. ## 문...
Meta Keywords: dict, mydict, set, dictname, 데이터
-->

# Tcl의 dict: 키-값 쌍을 다루는 강력한 데이터 구조

## 개요
Tcl의 `dict`는 키-값 쌍을 저장하고 조작하는 데 사용되는 강력한 데이터 구조입니다. 해시 맵과 유사하게 작동하여, 데이터를 효율적으로 조회하고 수정할 수 있는 기능을 제공합니다.

## 문서화
### 목적
`dict` 명령은 Tcl에서 키-값 쌍을 수집하고 조작하는 데 필요한 다양한 기능을 제공합니다. 이를 통해 데이터 구조를 간편하게 생성하고 관리할 수 있습니다.

### 사용법
`dict` 명령은 다음과 같은 기본 구문을 가지고 있습니다:

```tcl
dict create ?key value ...?
dict set dictName key value
dict get dictName key
dict exists dictName key
dict remove dictName key
dict keys dictName
dict values dictName
```

#### 주요 명령어
1. **create**: 새로운 딕셔너리를 생성합니다.
2. **set**: 특정 키에 대한 값을 설정합니다.
3. **get**: 특정 키에 대한 값을 조회합니다.
4. **exists**: 특정 키가 존재하는지 확인합니다.
5. **remove**: 특정 키와 그에 대한 값을 삭제합니다.
6. **keys**: 딕셔너리의 모든 키를 반환합니다.
7. **values**: 딕셔너리의 모든 값을 반환합니다.

## 예제
### 기본 사용 예
```tcl
# 딕셔너리 생성
set myDict [dict create name "Alice" age 30 city "Seoul"]

# 값 조회
set name [dict get $myDict name]  ;# "Alice"
set age [dict get $myDict age]    ;# 30

# 값 설정
dict set myDict country "South Korea"

# 키 존재 여부 확인
if {[dict exists $myDict city]} {
    puts "City exists"
}

# 키 및 값 삭제
dict remove myDict age

# 모든 키 및 값 출력
puts [dict keys $myDict]   ;# "name city country"
puts [dict values $myDict] ;# "Alice Seoul South Korea"
```

## 설명
- **빈 딕셔너리**: `dict create` 명령을 사용하여 빈 딕셔너리를 생성할 수 있습니다.
- **키 중복**: 동일한 키를 여러 번 설정하면, 마지막에 설정된 값이 유지됩니다.
- **타입 안전성**: `dict`는 키와 값으로 문자열뿐만 아니라 다양한 데이터 타입을 사용할 수 있습니다.
- **성능**: `dict`는 해시 테이블을 기반으로 하여, 일반적인 조회 및 수정 작업이 빠릅니다.

## 한 줄 요약
Tcl의 `dict`는 키-값 쌍을 효율적으로 저장하고 조작할 수 있는 강력한 데이터 구조입니다.