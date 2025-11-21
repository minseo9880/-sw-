# Linux 명령어 조사: top, ps, jobs, kill

## 📊 명령어 요약 표

| 명령어 | 주요 기능 | 사용 빈도 |
|--------|-----------|-----------|
| **top** | 실시간 시스템 모니터링 | ⭐⭐⭐⭐⭐ |
| **ps** | 프로세스 상태 확인 | ⭐⭐⭐⭐ |
| **jobs** | 백그라운드 작업 관리 | ⭐⭐⭐ |
| **kill** | 프로세스 제어 및 종료 | ⭐⭐⭐⭐ |

# 1. top
```bash
# 1. top - 실시간 시스템 모니터링
# 주요 기능: CPU, 메모리 사용량 확인, 프로세스 상태 모니터링
top
top -p 1234  # 특정 PID만 모니터링
top -u username  # 특정 사용자 프로세스만 보기
```
# 2. ps
```bash
# 2. ps - 프로세스 상태 출력
# 주요 옵션:
ps aux        # 모든 프로세스 상세 정보
ps -ef        # 전체 프로세스 목록
ps -u username # 특정 사용자 프로세스
ps -e --forest # 프로세스 트리 구조로 보기
```
# 3. jobs
```bash
# 3. jobs - 백그라운드 작업 관리
# 주요 기능: 현재 쉘의 백그라운드/중지된 작업 표시
sleep 100 &   # 백그라운드로 실행
jobs          # 작업 목록 보기
jobs -l       # 작업 번호와 PID 함께 출력
jobs -p       # PID만 출력
```
# 4. kill
```bash
# 4. kill - 프로세스 종료/시그널 전송
# 주요 시그널:
kill 1234              # SIGTERM(15)로 정상 종료
kill -9 1234           # SIGKILL(9)로 강제 종료
kill -STOP 1234        # SIGSTOP(19)로 일시 중지
kill -CONT 1234        # SIGCONT(18)로 재개
kill -l                # 사용 가능한 시그널 목록 보기
```
# 5. 실제 사용 예시 시나리오
## 프로세스 찾아서 종료하기
```bash
ps aux | grep firefox  # firefox 프로세스 찾기
kill -9 5678          # 찾은 PID로 강제 종료
```
## 백그라운드 작업 관리
```bash
sleep 300 &           # 백그라운드 작업 실행
jobs -l               # 작업 상태 확인
kill %1               # 작업 번호 1번 종료
```
## 시스템 모니터링
```bash
top                   # 시스템 상태 실시간 확인
