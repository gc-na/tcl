<!--
Meta Description: # Tcl의 lsort 명령어: 리스트 정렬의 모든 것 ## 개요 Tcl에서 `lsort` 명령어는 리스트의 요소를 정렬하는 데 사용됩니다. 이 명령어는 다양한 정렬 옵션을 제공하여 사용자가 원하는 방식으로 리스트를 정렬할 수 있도록 해줍니다. ## 문서화 `lsort...
Meta Keywords: lsort, set, mylist, tcl, sortedlist
-->

# Tcl의 lsort 명령어: 리스트 정렬의 모든 것

## 개요
Tcl에서 `lsort` 명령어는 리스트의 요소를 정렬하는 데 사용됩니다. 이 명령어는 다양한 정렬 옵션을 제공하여 사용자가 원하는 방식으로 리스트를 정렬할 수 있도록 해줍니다.

## 문서화
`lsort` 명령어는 주어진 리스트를 정렬하여 새로운 리스트를 반환합니다. 기본적으로 오름차순으로 정렬되지만, 다양한 옵션을 통해 내림차순 정렬, 사전식 정렬, 사용자 정의 정렬 등을 지원합니다.

### 사용법
```tcl
lsort ?옵션? 리스트
```

### 주요 옵션
- `-unique`: 중복된 요소를 제거한 후 정렬합니다.
- `-decreasing`: 내림차순으로 정렬합니다.
- `-dictionary`: 사전식으로 정렬합니다.
- `-index index`: 리스트의 각 요소가 리스트의 서브리스트일 경우, 특정 인덱스의 요소를 기준으로 정렬합니다.

### 예시
1. 기본 오름차순 정렬:
   ```tcl
   set myList {3 1 4 2}
   set sortedList [lsort $myList]
   # 결과: {1 2 3 4}
   ```

2. 내림차순 정렬:
   ```tcl
   set myList {3 1 4 2}
   set sortedList [lsort -decreasing $myList]
   # 결과: {4 3 2 1}
   ```

3. 중복 제거 후 정렬:
   ```tcl
   set myList {3 1 4 2 2 3}
   set sortedList [lsort -unique $myList]
   # 결과: {1 2 3 4}
   ```

4. 사전식 정렬:
   ```tcl
   set myList {apple banana Cherry date}
   set sortedList [lsort -dictionary $myList]
   # 결과: {apple banana Cherry date}
   ```

5. 서브리스트의 특정 인덱스 기준 정렬:
   ```tcl
   set myList {{a 1} {b 2} {a 3} {c 1}}
   set sortedList [lsort -index 0 $myList]
   # 결과: {{a 1} {a 3} {b 2} {c 1}}
   ```

## 설명
`lsort` 명령어는 리스트를 정렬할 때 매우 유용하지만, 몇 가지 주의할 점이 있습니다. 예를 들어, 리스트에 포함된 요소가 숫자와 문자열이 혼합되어 있다면, 기본적으로 문자열로 처리되어 정렬됩니다. 이로 인해 예상치 못한 결과가 나올 수 있습니다. 또한, 서브리스트의 인덱스를 기준으로 정렬할 때는 해당 인덱스가 존재하지 않는 경우 오류가 발생할 수 있습니다.

## 한 문장 요약
`lsort`는 Tcl에서 리스트의 요소를 다양한 방식으로 정렬할 수 있는 강력한 명령어입니다.