## About
'당신의 사이퍼즈 취향을 분석해 드립니다'라는 목표로 시작된 '슬기로운 사퍼생활' 프로젝트는 네오플 OpenAPI에서 조회 가능한 (최대) 최근 100경기를 분석하여 입력한 능력자의 프로필, 선호 캐릭터 목록, 모스트 캐릭터, 승률이 높은 캐릭터 목록, 그리고 날짜별 승률과 그 분석 결과를 보여줍니다.



## Requirements
이 프로젝트는 파이썬 3로 작성되었으며 <code>requests</code>, <code>pandas</code>, <code>numpy</code> 외부 모듈이 사용되었습니다. 파이썬이 설치돼 있지 않은 환경에서는 이 링크를 통해 웹에서 테스트해볼 수 있습니다: https://repl.it/@ubless607/seulgiroun-sapeosaenghwal
```
Module not found 에러가 발생할 경우: 
pip install requests
pip install pandas
pip install numpy
```
## Usage
### 닉네임 입력
```
닉네임을 입력하세요: 착한어른이
공식/일반: 일반
```
사이퍼즈 닉네임과 게임 타입을 입력합니다. 존재하지 않는 닉네임을 입력할 경우 <code>닉네임이 존재하지 않습니다</code> 메세지가 나오며 프로그램이 종료됩니다. <code>공식</code>이나 <code>일반</code>이 아닌 다른 키워드를 입력할 경우 자동으로 <code>일반</code>이 입력됩니다.
### 프로필
```
** 착한어른이님의 프로필 **
급수 : 73
티어: 언랭
```
능력자의 급수와 티어를 표시합니다.
### 선호 캐릭터
```
** 선호 캐릭터 TOP6 **
루드빅 : 22
타라 : 12
미아 : 12
트릭시 : 9
나이오비 : 7
제키엘 : 5
```
능력자의 선호 캐릭터 TOP6를 표시합니다. 시즌 초기화 이후 플레이를 한 번도 진행하지 않은 경우 <CODE>전적이 존재하지 않습니다</CODE> 메세지가 나오며 프로그램이 종료됩니다.
### 모스트
```
** 만약 착한어른이님이 사이퍼즈 캐릭터였다면, 무소속의 루드빅(이)였을 거예요 **
평균 레벨 : 56
평균 킬/데스/어시: 6/8/8
평균 공격량: 30660
평균 피해량: 37500
평균 전투참여: 145
평균 시야점수: 226
평균 KDA: 1.83
```
능력자의 모스트 캐릭터와 그 소속을 표시합니다. 모스트 캐릭터의 평균 레벨,  킬/데스/어시, 공격량, 피해량, 전투참여, 시야점수, KDA를 보여줍니다.
### 캐릭터 승률
```
** 캐릭터 승률 : 3판 이상 플레이한 캐릭터만 표시 **
테이 : [5, 0, 1.0]
나이오비 : [5, 2, 0.71]
시드니 : [2, 1, 0.67]
루드빅 : [14, 8, 0.64]
루시 : [3, 2, 0.6]
타라 : [7, 5, 0.58]
미아 : [6, 6, 0.5]
트릭시 : [4, 5, 0.44]
히카르도 : [2, 3, 0.4]
샬럿 : [1, 2, 0.33]
제키엘 : [0, 5, 0.0]
```
능력자가 플레이한 게임에서 선택한 캐릭터들의 승률을 표시합니다. 표시 형식은 <code>캐릭터 : [승리 횟수, 패배 횟수, 승률]</code>입니다. 승률이 가장 높은 캐릭터부터 순차적으로 보여줍니다.
### 날짜별 승률
```
** 날짜별 승률 **
2019-08-05 : [4, 2, 0.67]
2019-08-06 : [7, 7, 0.5]
2019-08-07 : [10, 8, 0.56]
2019-08-08 : [11, 8, 0.58]
2019-08-09 : [3, 6, 0.33]
2019-08-10 : [10, 7, 0.59]
2019-08-11 : [4, 6, 0.4]
2019-08-12 : [3, 4, 0.43]
승률이 하락하고 있습니다. 착한어른이님의 모스트 '루드빅'이나 최근 승률이 좋은 '테이'(으)로 플레이해보는 것은 어떨까요?
```
능력자의 날짜별 승률을 표시합니다. 표시 형식은 <CODE>날짜 : [승리 횟수, 패배 횟수, 승률]</CODE>입니다. 또한  *linear regression* 기법을 사용하여 승률의 상승 여부를 분석합니다. slope가 0 이상인 경우 <code>승률이 상승하고 있습니다. 잘하고 있어요!</code>를 , 만약 slope가 0 미만이면 <code>승률이 하락하고 있습니다. 능력자님의 모스트 '캐릭터명'이나 최근 승률이 좋은 '캐릭터명'(으)로 플레이해보는 것은 어떨까요?</code> 메세지를 보여줍니다.

![Neople OPENAPI](license.png)
