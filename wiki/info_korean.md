<!--
Meta Description: # Tcl의 info 명령어: 변수 및 프로시저 정보 확인 ## 개요 Tcl의 `info` 명령어는 현재 Tcl 환경에서 변수, 프로시저, 패키지 등의 정보를 조회하는 데 사용됩니다. 이 명령어는 디버깅 및 스크립트 상태를 확인하는 데 매우 유용합니다. ## 문서화 #...
Meta Keywords: info, puts, 프로시저, 명령어는, tcl
-->

# Tcl의 info 명령어: 변수 및 프로시저 정보 확인

## 개요
Tcl의 `info` 명령어는 현재 Tcl 환경에서 변수, 프로시저, 패키지 등의 정보를 조회하는 데 사용됩니다. 이 명령어는 디버깅 및 스크립트 상태를 확인하는 데 매우 유용합니다.

## 문서화
### 목적
`info` 명령어는 Tcl 스크립트의 상태를 파악하고, 변수 및 프로시저의 존재 여부와 속성에 대한 정보를 제공합니다. 이를 통해 개발자는 코드의 흐름과 상태를 보다 쉽게 이해할 수 있습니다.

### 사용법
`info` 명령어는 여러 가지 서브커맨드를 지원합니다. 주요 서브커맨드는 다음과 같습니다:

- `exists <variable>`: 지정된 변수가 존재하는지 여부를 확인합니다.
- `vars`: 현재 스코프에서 정의된 모든 변수를 나열합니다.
- `commands`: 현재 스코프에서 정의된 프로시저를 나열합니다.
- `level`: 현재 프로시저 호출 수준을 반환합니다.
- `loaded`: 현재 로드된 패키지를 나열합니다.

### 예시
```tcl
# 변수 존재 여부 확인
set myVar 10
puts [info exists myVar]  ;# true

# 현재 스코프의 변수 나열
set foo 20
set bar 30
puts [info vars]          ;# foo bar

# 현재 스코프의 프로시저 나열
proc myProc {} { return 1 }
puts [info commands]      ;# myProc

# 현재 호출 수준 확인
proc outerProc {} {
    puts [info level]     ;# 1
    innerProc
}
proc innerProc {} {
    puts [info level]     ;# 2
}
outerProc

# 로드된 패키지 확인
package require Tcl 8.6
puts [info loaded]        ;# Tcl 8.6
```

## 설명
`info` 명령어를 사용할 때 몇 가지 주의해야 할 점이 있습니다. 
- `info exists`를 사용할 때 변수가 정의되지 않은 경우, `false`를 반환합니다.
- `info vars`와 `info commands`는 현재 스코프에 따라 다르게 동작합니다. 글로벌 변수와 프로시저는 다른 스코프에 있을 수 있으므로, 사용자의 기대와 다를 수 있습니다.
- 호출 수준을 확인하는 `info level`은 계층 구조가 깊어질수록 정확한 값을 확인하는 데 유용하지만, 복잡한 프로시저 호출에서는 혼란스러울 수 있습니다.

## 한 줄 요약
Tcl의 `info` 명령어는 변수 및 프로시저에 대한 정보를 조회하고, 스크립트의 상태를 파악하는 데 유용한 도구입니다.