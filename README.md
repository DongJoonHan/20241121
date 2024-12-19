# 도구 정리

# 파일의 고유값 확인 (체크섬)
## 실행 명령
```sh
certutil -hashfile [파일명] SHA256|MD5
```

## 실행 예제
```sh
certutil -hashfile SW검증및이론_20240521_배포본.pdf SHA256
```

## 실행 결과 예제
```sh
SHA256의 SW검증및이론_20240521_배포본.pdf 해시:
b1546334433d666245218471a23d1e817319902efe393d91765a60558684c6cc
CertUtil: -hashfile 명령이 성공적으로 완료되었습니다.
```

# 페어와이즈 조합
## PICT 다운로드 (페어와이즈 조합 만드는 MS 프로그램: 오픈소스)
https://github.com/microsoft/pict

## PICT 사용법 (기본)
```
pict data.txt > result.xls
```
## PICT 사용법 (전수테스트 조합)
```
pict data.txt /o:max > result2.xls
```

## data.txt 예제
```
DM: eco, normal, sport1, sport2, crazy
RG: off, 1, 2, 3, 4
AL: blue, yellow, red, black, pink
wiper: off, auto, 1, 2, 3
SH: off, 1, 2, 3
```

# OpenJDK 다운로드 위치(17버전)
- 홈페이지: https://github.com/ojdkbuild/ojdkbuild
- 실제 다운 위치: https://github.com/ojdkbuild/ojdkbuild/releases/download/java-17-openjdk-17.0.3.0.6-1/java-17-openjdk-17.0.3.0.6-1.win.x86_64.msi

# CPD
# 다운로드
6.55.0이 CPD를 사용 가능하다.
https://sourceforge.net/projects/pmd/files/pmd/6.55.0/pmd-bin-6.55.0.zip/download

## 실행 명령
실행 시, 소스코드 폴더(분석 대상 폴더)의 대소문자가 동일해야 함!!

```
cpd --minimum-tokens 100 --files ./src --language cpp --format xml > cpd.xml || exit 0
```
or
```
C:\DevTools\pmd\bin\cpd --minimum-tokens 100 --files ./src --language cpp --format xml > cpd.xml || exit 0
```

뒤에 ||exit 0 이 있는 이유는, Jenkins는 exit 0을 정상이라고 보고, 나머지는 빌드 실패라 판단하는데 CPD는 기본으로 exit 1과 같은 방식으로 종료해서, 정상 처리해도 빌드 실패가 발생함. 이를 예방하기 위해 exit 0을 추가함.

# CLOC (라인수, 주석라인수 확인)
## 다운로드
https://github.com/AlDanial/cloc

## 사용법
```
cloc.exe .
```

# Lizard
## 설치
CMD를 관리자 권한으로 실행 필요
```
pip install lizard
```

## 실행 명령(Command-Line for CSV)
```
lizard ./src --csv > lizard.csv
```
## CSV 출력 결과 예제
![image](https://github.com/user-attachments/assets/a869bdeb-c91d-48c3-a30f-228d0a50564b)

