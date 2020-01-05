# OS
To learn Computer Operating System (2019/1/5 시작)

# Chapter (공부한 내용을 담은 폴더 - 추가 중)
- [[Chapter1~2]_Operating_System_Structure]()
- [[Chapter3]_Process]()
- [[Chapter4]_Threads]()
- [[Chapter5]_Process_Synchronization]()
- [[Chapter6]_CPU_Scheduling]()
- [[Chapter7]_Deadlocks]()
- [[Chapter8]_Main_memory]()
- [[Chapter9]_Virtual_memory]()
- [[Chapter10]_Mass_Storage_Structure]()
- [[Chapter11]_File-System_Interface]()
- [[Chapter12]_File-System_Implementation]()
- [[Chapter13]_Input_and_Output]()

# PintOS
- `PintOS`는 교육용 운영체제로, x86 아키텍쳐를 지원하며 `Bochs`와 `QEMU`같은 시뮬레이터를 기반으로 작동합니다.

- PintOS에서 User Program, Thread, Virtual Memory, File-System에 대해 기본적인 설명을 실제로 구현할 수 있습니다.

## PintOS 설치 하기
### 1. Ubuntu 환경 준비
- (Mac) : `Docker`에서 Ubuntu image를 받아 가상 환경에 Ubuntu를 깔아 줍니다. 이때, 우분투 이미지 파일로 **ubuntu-12.04.05-desktop** 버전을 받습니다.
### 2. gcc-4.4 버전 설치
- 우분투에 설치되어 있는 gcc 버전이 너무 높으면 컴파일이 안되는 이슈가 생깁니다. 그러므로 4.4버전으로 인스톨 합니다.
### 3. Bochs 설치
- Bochs 공식 사이트에서 최신 버전을 찾아 다운로드 합니다.
- 다운로드가 완료 되었다면 다음 명령어로 압축을 해제 합니다.
```
tar xvf bochs-2.6.2.tar.gz
```
- **압축이 풀린 폴더로 이동한 후**, 아래 명령어로 설치합니다.
```
./configure --enable-gdb-stub --with-nogui
make
sudo make install
```
### 4. PintOS 설치
- PintOS 파일을 찾아서 설치 합니다.
- 설치된 파일을 다음 명령어로 압축 해제 합니다.
```
tar xvf pintos.tar.gz
```
- `pintos/src/threads`폴더로 이동 후, 아래의 명령어 `make`로 컴파일 합니다.
### 5. PintOS 환경 변수 설정
- 파일 경로를 설정하기 위해 `bashrc` 파일을 열어 줍니다.
```
sudo vi ~/.bashrc
```
- 마지막 라인에 파일 경로를 다음과 같이 입력합니다.
```
export PATH="$PATH:(핀토스 설치한 경로)/ubuntu/
pintos/src/utils"
```
- 수정된 사항을 반영하는 명령어를 넣어줍니다.
```
source ~/.bashrc
```
### PintOS 설치 확인 하기
`pintos/src/threads/`경로에서 아래 명령어를 실행하여 설치가 바르게 되었는지 확인 합니다.
```
pintos -- run alarm-multiple
```