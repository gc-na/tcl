<!--
Meta Description: # Tcl의 lindex: 리스트에서 요소를 추출하는 명령어 ## 개요 Tcl의 `lindex` 명령어는 리스트에서 특정 인덱스에 위치한 요소를 반환하는 기능을 제공합니다. 이 명령어는 리스트 구조를 다루는 데 있어 매우 유용하며, 다양한 프로그래밍 시나리오에서 사용됩...
Meta Keywords: lindex, 요소를, set, mylist, 리스트의
-->

# Tcl의 lindex: 리스트에서 요소를 추출하는 명령어

## 개요
Tcl의 `lindex` 명령어는 리스트에서 특정 인덱스에 위치한 요소를 반환하는 기능을 제공합니다. 이 명령어는 리스트 구조를 다루는 데 있어 매우 유용하며, 다양한 프로그래밍 시나리오에서 사용됩니다.

## 문서화

### 목적
`lindex`는 주어진 리스트에서 특정 위치에 있는 요소를 선택할 수 있도록 해주는 명령어입니다. 리스트는 Tcl에서 기본적인 데이터 구조로, 여러 값을 순서대로 저장할 수 있습니다.

### 사용법
`lindex` 명령어의 기본 구문은 다음과 같습니다:

```tcl
lindex list index
```

- **list**: 요소를 추출할 대상 리스트입니다.
- **index**: 가져오고자 하는 요소의 위치를 나타내는 정수입니다. 인덱스는 0부터 시작합니다.

### 세부 사항
- 인덱스가 음수인 경우, 리스트의 끝에서부터 요소를 선택합니다. 예를 들어, `-1`은 마지막 요소를 나타냅니다.
- 리스트가 비어 있거나 인덱스가 범위를 초과할 경우, Tcl은 오류를 발생시킵니다.

## 예제

### 기본 사용 예제
```tcl
set myList {apple banana cherry}
set fruit [lindex $myList 1]
puts $fruit  ;# 출력: banana
```

### 음수 인덱스 예제
```tcl
set myList {apple banana cherry}
set lastFruit [lindex $myList -1]
puts $lastFruit  ;# 출력: cherry
```

### 인덱스 오류 예제
```tcl
set myList {apple banana cherry}
set invalidFruit [lindex $myList 5]  ;# 오류 발생
```

## 설명
`lindex`를 사용할 때 주의해야 할 점은 인덱스가 리스트의 범위를 초과하지 않도록 하는 것입니다. 예를 들어, 리스트의 길이가 3인 경우 유효한 인덱스는 0, 1, 2이며, 이 외의 인덱스를 사용할 경우 Tcl에서 오류가 발생합니다. 또한, 음수 인덱스를 사용할 경우 리스트의 길이에 따라 접근할 수 있는 요소가 결정되므로, 이를 염두에 두어야 합니다.

## 한 줄 요약
`lindex`는 Tcl에서 리스트의 특정 인덱스에 위치한 요소를 반환하는 명령어입니다.