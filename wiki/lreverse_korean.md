<!--
Meta Description: # Tcl lreverse: 리스트 반전 명령어 ## 개요 Tcl에서 `lreverse`는 주어진 리스트의 요소를 반전시키는 명령어입니다. 이 명령어는 리스트의 순서를 역으로 변경하여 새로운 리스트를 생성합니다. ## 문서화 `lreverse` 명령어는 주어진 리스트의...
Meta Keywords: lreverse, 리스트의, tcl, 리스트를, set
-->

# Tcl lreverse: 리스트 반전 명령어

## 개요
Tcl에서 `lreverse`는 주어진 리스트의 요소를 반전시키는 명령어입니다. 이 명령어는 리스트의 순서를 역으로 변경하여 새로운 리스트를 생성합니다.

## 문서화
`lreverse` 명령어는 주어진 리스트의 요소들을 거꾸로 나열하여 반환합니다. 이 명령어는 리스트의 구조를 변경하지 않고, 원본 리스트는 그대로 유지됩니다.

### 사용법
```tcl
lreverse list
```

- **list**: 반전할 대상이 되는 리스트입니다.

### 반환값
`lreverse`는 반전된 리스트를 반환합니다.

## 예제
다음은 `lreverse` 명령어의 기본 사용 예제입니다.

```tcl
set myList {1 2 3 4 5}
set reversedList [lreverse $myList]
puts $reversedList  ; # 출력: 5 4 3 2 1
```

또 다른 예제입니다:

```tcl
set fruits {apple banana cherry}
set reversedFruits [lreverse $fruits]
puts $reversedFruits  ; # 출력: cherry banana apple
```

## 설명
- **일반적인 오류**: `lreverse`는 반드시 리스트 형식의 인자를 받아야 합니다. 만약 리스트가 아닌 값을 입력할 경우, Tcl은 에러를 발생시킵니다.
- **가변 인자 처리**: `lreverse`는 단일 리스트만 처리할 수 있습니다. 여러 리스트를 동시에 반전할 수 없으므로, 각 리스트에 대해 개별적으로 호출해야 합니다.
- **비파괴적**: 원본 리스트는 변경되지 않으며, 새로운 리스트가 생성되어 반환됩니다. 이는 함수형 프로그래밍의 원칙을 따릅니다.

## 한 줄 요약
`lreverse`는 Tcl에서 리스트의 요소 순서를 반전시켜 새로운 리스트를 생성하는 명령어입니다.