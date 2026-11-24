# ZombieApocalypse

좀비 아포칼립스에서 살아남는 협동 서바이벌 플러그인입니다.

[다운로드](https://github.com/beddeak/ZombieApocalypse/releases/latest)

## 설치 및 설정

Paper 26.2 · Java 25. 새 서버는 서버팩 ZIP을 빈 폴더에 풀고 Windows에서 `start.bat`을 실행하세요. 첫 실행 후 생성된 `eula.txt`를 읽고 동의하면 값을 변경한 뒤 다시 실행하세요. 기존 서버는 정지 후 `ZombieApocalypse-1.0.0.jar`을 `plugins/`에 넣고 다시 시작하세요.

첫 실행 후 `plugins/ZombieApocalypse/config.yml`을 편집하세요. 서버를 정상 종료하고 편집한 뒤 다시 시작하면 새 설정을 읽습니다. [기본 설정과 항목별 설명](src/main/resources/config.yml)

## 명령어

권한 `zombieapoc.admin`(기본 op). 게임 안에서는 `/apocalypse` 또는 `/apoc`, 콘솔에서는 앞의 `/`를 뺀다.

| 명령어 | 내용 |
| --- | --- |
| `/apoc start [월드] [초\|now]` | 타이틀과 3, 2, 1 뒤 시작(기본 6초, `now`는 바로). 10초보다 길게 주면 남은 시간 보스바도 뜬다. 시작되면 그 월드의 기존 몬스터가 사라지고, 라디오와 안테나 조합법이 레시피북에 추가된다 |
| `/apoc stop [월드]` | 종료(준비 중이면 취소). 커스텀 좀비를 모두 정리한다 |
| `/apoc status` | 준비 남은 시간 또는 날짜, 블러드문, 좀비 웨이브, 타입별 좀비 수, 조립과 엔딩 진행 |
| `/apoc stats [월드]` | 지금까지의 생존 기록(엔딩 때 나오는 것과 같은 표). 명령어를 쓴 사람에게만 보인다 |
| `/apoc reload` | `config.yml` 다시 읽기. 문법 오류면 이전 설정 유지 |
| `/apoc set [설정] [값]` | 플레이 중 실시간 조정. 값을 확인해 바로 적용하고 `config.yml`에 저장한다(첫 변경 때 원본은 `config.yml.bak`). 잘못된 값이면 바꾸지 않는다. 인자 없이 쓰면 주요 스폰 설정과 현재 값이 나오고, 줄을 클릭하면 입력창에 명령이 들어간다. 설정 이름은 탭으로 한 단계씩 완성된다. 예: `/apoc set spawning.extra.per-player-cap 60` |
| `/apoc limit [수]` | 서버 전체 좀비 상한(`spawning.extra.global-cap`, 기본 1000) 확인/변경. 바로 적용하고 `config.yml`에 저장 |
| `/apoc limit day <n> [월드]` | 지금 날짜를 n일차로 변경(`/apoc day set <n>`과 같음) |
| `/apoc spawn <타입> [수]` | 바라보는 곳에 소환. 콘솔은 `spawn <타입> <수> <월드> <x> <y> <z>` |
| `/apoc egg <타입\|all> [수] [플레이어]` | 테스트용 스폰알 지급. 우클릭한 곳에 그 타입 좀비가 나온다(아포칼립스가 켜진 월드에서만). `all`은 24종을 한 번에 |
| `/apoc molotov [수] [플레이어]` | 테스트용 화염병 지급(최대 64개) |
| `/apoc day [set <n>]` | 날짜 확인/변경 |
| `/apoc bloodmoon <start\|stop>` | 블러드문 강제 시작/종료 |
| `/apoc wave <start\|stop>` | 좀비 웨이브 바로 시작/종료 (`horde`도 같은 명령) |
| `/apoc radio <give [플레이어]\|status\|reset>` | 라디오와 안테나 지급(조립 없이 바로) / 엔딩 상태(라디오, 안테나, 조립) / 엔딩 초기화 |
| `/apoc finale <start\|skip>` | 피날레 바로 시작 / 건너뛰고 탈출 단계로 |
| `/apoc escape skip` | 탈출 단계를 끝내고 엔딩으로 |
