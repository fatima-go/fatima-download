# release history #

## 2026 ##

| Date       | Content                                                          |
|------------|------------------------------------------------------------------|
| 2026.05.17 | fatima-core v1.3.0 전체적으로 반영                               |
| 2026.06.25 | fatima-core v1.3.3 대비 juno,jupiter,saturn의 shutdown 로직 보완 |
| 2026.08.31 | roclip에 -b 옵션 지원 (juno, roclip 반영)                        |
| 2026.09.11 | fatima-core v1.3.6 반영 (v1.3.5 gRPC 배포·운영 API, rolog용 LogLevelControl, rohis용 DeploymentHistory)<br/>fatima-cmd : rolog·rohis gRPC TUI 추가(패키지 선택, 로그레벨 즉시 변경, 배포 이력 조회), roproc·rostart·rostop 화면 개선(상세 이동 제거, 할 일 없는 프로세스 선택 차단, 실행 확인 강조, 삭제 시 프로세스명 입력), rodeploy Upload 화면부터 시작 및 legacy juno 포함 그룹 확인, startro가 PATH가 아닌 app 디렉터리 바이너리 실행, roupdate가 파일을 교체 방식으로 복사(macOS 격리 속성 유지 문제 해결)<br/>juno : 로그레벨·배포 이력 gRPC 제공, 0.0.0.0 대신 실제 IP로 jupiter 등록, 중지된 프로세스 rostop 시 알림 억제 방지, rohis -g/-a 조회 수정, gRPC 배포 후 이력 보관 규칙 적용<br/>jupiter : -p 없이 로컬 패키지 자동 선택(로컬 클라이언트, 단일 패키지) |
| 2026.09.15 | fatima-core v2.0.0 및 fatima-opm v1.0.0 반영 : 운영 전용 API·통신 규격을 fatima-opm으로 분리하고 juno·jupiter·fatima-cmd에 적용, 기존 v1.x 프로그램의 강제 업데이트는 불필요(v2 전환 시 core import 경로에 `/v2` 추가)<br/>rodeploy : 배포 관리 세션 및 재접속 지원, heartbeat 10초·마지막 수신 후 20초 만료 기준 적용, CLI 이탈 시 미실행 배포 취소 및 실행 중 대상의 결과 확인 후 종료, 실패·미확정 결과 정리와 기존 작업 상태·복구 안내 개선<br/>jupiter : 첫 서버 확인 후 나머지 서버 순차 배포 시 대상 간 기본 5초 대기 및 다음 배포 시작 시각 제공(`deployment.v2.target.interval.seconds`로 조정, 0은 대기 없음)<br/>juno : 지연 도착한 배포 실행 요청의 취소 보장, `remote.operation.allow` IP 제한을 프로세스 시작·중지·등록 변경에만 적용(조회·배포 제외)<br/>fatima-cmd : roproc의 juno 직접 연결, rostart·rostop·roproc 패키지 선택 안내 개선, 구형 서버의 미지원 RPC 안내, rodeploy 대상 간 대기 카운트다운, lcproc 리비전 조회·전환 및 복제 TUI 추가(실행 확인·실행 중 프로세스 전환 차단·기존 텍스트 방식 유지) |
| 2026.09.16 | fatima-cmd : rodis·rostart·rostop·roproc·rocron·rolog·rohis·roclip·roclric의 패키지 선택 규칙 통일(`-p` 지정 우선, 미지정 시 클라이언트 IP와 일치하는 패키지 자동 선택, 같은 IP에 여러 패키지가 있으면 해당 목록에서 선택, IP 일치가 없으면 단일 패키지 자동 선택 또는 전체 목록에서 선택)<br/>조회 옵션·직접 실행·기존 HTTP 경로에도 동일 적용, 비대화형 및 `--plain`·`--json` 실행은 자동 선택이 불가능한 경우 `-p` 지정 안내, 패키지 목록 재진입 시 전체 목록 표시<br/>lcproc : 현재 가리키는 리비전으로 전환 요청 시 동일 리비전 안내 후 변경 생략(중지 요청·링크 재생성 없음), TUI·리비전 직접 지정·기존 텍스트 방식에 적용, 실행 직전 현재 리비전 재확인 |

## 2025 ##

| Date       | Content                                                                                      |
|------------|----------------------------------------------------------------------------------------------|
| 2025.10.02 | juno : [[bug] goaway 처리시 panic 발생가능성](https://github.com/fatima-go/juno/issues/18) |
| 2025.09.16 | fatima v1.2.0 반영 (jupiter,juno,saturn,fatima-cmd)                                            |
| 2025.07.15 | fatima-cmd : [lccrypto 버그](https://github.com/fatima-go/fatima-cmd/issues/30)                |
| 2025.07.15 | fatima-cmd : [rodis 에서 프로세스 목록을 이름순으로 출력](https://github.com/fatima-go/fatima-cmd/issues/28) |

## 2024 ##

| Date       | Content                                                                                                                                                                                                                                                                                                                                                                                                     |
|------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 2025.04.25 | juno : [cron job 리스팅 기능 제공](https://github.com/fatima-go/juno/issues/13)<br>fatima-cmd : [cron job 리스팅 기능 제공](https://github.com/fatima-go/fatima-cmd/issues/26)                                                                                                                                                                                                                                                                                                                   |
| 2024.10.17 | juno : [프로세스 가동시 weight 적용](https://github.com/fatima-go/juno/issues/11)                                                                                                                                                                                                                                                                                                                                    |
| 2024.04.23 | fatima-cmd : [roupdate 에서 bin 파일 복사시 executable 모드 추가 필요](https://github.com/fatima-go/fatima-cmd/issues/18)<br/> fatima-cmd : [rodeploy 시에 보다 많은 정보 표시](https://github.com/fatima-go/fatima-cmd/issues/21)<br/> fatima-package : [m3 맥북에서 빌드시 ._ 파일 생성 이슈](https://github.com/fatima-go/fatima-package/issues/1)<br/>jupiter : [패키지 최초 가동시 platform 정보 미노출](https://github.com/fatima-go/jupiter/issues/7) |
| 2024.04.17 | juno : [goaway signal skip 방법 제공](https://github.com/fatima-go/juno/issues/9)                                                                                                                                                                                                                                                                                                                               |
| 2024.03.19 | saturn : [프로세스 배포 관련 알림은 별도 채널로 전송](https://github.com/fatima-go/saturn/issues/3)<br/>lcslack : 별도 채널 지원 추가                                                                                                                                                                                                                                                                                                 |
| 2024.02.27 | lccrypto : [Secret 관련 CLI Tool 신규 제공](https://github.com/fatima-go/fatima-cmd/issues/1)                                                                                                                                                                                                                                                                                                                     
| 2024.01.25 | jupiter : [사용자 인증시 암호 부분을 b64 스킴 추가 처리하도록 변경](https://github.com/fatima-go/jupiter/issues/3)<br/> fatima-cmd : [사용자 password 암호화 전송](https://github.com/fatima-go/fatima-cmd/pull/16), [roxxx 명령어에서 jupiter 주소의 마지막 슬래쉬 추가 처리](https://github.com/fatima-go/fatima-cmd/issues/14)<br/>juno : [프로세스 감시중 DEAD 일때 추가 정보 전달](https://github.com/fatima-go/juno/pull/7)<br/>                                     |                                                                                                  |

## 2023 ##

| Date       | Content                                                                                  |
|------------|------------------------------------------------------------------------------------------|
| 2023.10.06 | 다음의 프로세스에 fatima-core v1.1.0 적용 : jupiter, juno, saturn                             |
| 2023.09.26 | Mac 에서 압축한것을 풀때 hidden 파일 처리 여부 [#12](https://github.com/fatima-go/fatima-cmd/issues/12) |
| 2023.09.19 | lcproc 에서 버전정보 확인 시 날짜 추가 출력 [#8](https://github.com/fatima-go/fatima-cmd/issues/8)      |
