# 프로젝트 목적
- 언리얼 엔진5의 C++ 사용법을 학습하고, 이를 활용하여 3인칭 슈터 장르의 데모 게임을 제작하는 것 입니다.

# 참여 멤버
- 정훈 : https://github.com/nixeast

# 데모 소개 영상
- https://youtu.be/9Iyjt0d4WoY?si=xSyL3rG3vVkAF_xC

# 주요 업무
- 프로젝트 기획 및 스테이지 레벨디자인
- 아트 리소스 및 UI 통합
- 플레이어 캐릭터 및 AI 개발
- 게임UI, 인벤토리 개발
- 게임 UI 개발
- 상호작용 오브젝트 개발

# 프로젝트 상세 개요
- 기간 : 2024-02-04 ~ 2024-03-02
- 프로그래밍 언어 : Unreal C++, Unreal BluePrint

# 사용 엔진 버전
- 언리얼 엔진 5.1

# 핵심기능
1. 플레이어 캐릭터 조준
- 플레이어가 조준 입력버튼을 누르고 있을 경우 바라보는 방향을 포커싱 하는 기능입니다.
- 포커싱 도중에는 플레이어가 바라보고 있는 방향의 끝에 대상이 무엇인지 판단합니다.
- [코드 보러가기](https://github.com/nixeast/ProjectMS/blob/2cfd98d404b5902d36c088eb7d6d1ef14b1e663d/Source/ProjectMS/ProjectMSCharacter.cpp#L399)

2. 플레이어 캐릭터 사격
- 플레이어 캐릭터가 조준 도중일 경우 사격 버튼을 눌러 총알을 발사하는 기능입니다.
- 바라보고 있는 방향을 향해 충돌체크용 Line을 발사하여 대상을 체크합니다.
- 대상이 Enemy일 경우 일정량의 데미지를 전달합니다.
- [코드 보러가기](https://github.com/nixeast/ProjectMS/blob/2cfd98d404b5902d36c088eb7d6d1ef14b1e663d/Source/ProjectMS/ProjectMSCharacter.cpp#L228)

3. 아이템 획득
- 스테이지에 배치된 아이템에 접근하여 플레이어 캐릭터가 아이템을 획득합니다.
- 획득 시 획득에 필요한 시간이 카운드 되며 완료 시, 인벤토리에 저장됩니다.
- [코드 보러가기](https://github.com/nixeast/ProjectMS/blob/2cfd98d404b5902d36c088eb7d6d1ef14b1e663d/Source/ProjectMS/ProjectMSCharacter.cpp#L524)

5. 아이템 사용
- 인벤토리를 열어 획득한 아이템을 사용합니다.
- 단, 사용 가능한 아이템의 경우에 한하여 소비됩니다.
- [코드 보러가기](https://github.com/nixeast/ProjectMS/blob/99e2a881c5e9c3c5f3a259c5a8d31669dda8ae1a/Source/ProjectMS/InGameManager.cpp#L593)

6. Enemy 추격
- 적 캐릭터가 자신의 시야 센서 내에 플레이어 캐릭터가 접근할 시 추격 해 옵니다.
- [코드 보러가기](https://github.com/nixeast/ProjectMS/blob/99e2a881c5e9c3c5f3a259c5a8d31669dda8ae1a/Source/ProjectMS/Enemy.cpp#L70)

8. Enemy 공격
- 플레이어 캐릭터가 적 캐릭터의 공격범위 안에 위치할 시 공격 애니메이션을 실행합니다.
- 공격 애니메이션 실행 시 충돌체크를 실행하여 해당 시퀀스에서만 공격체크를 진행합니다.
- 플레이어가 공격을 받을 시 데미지를 전달받습니다.
- [코드 보러가기](https://github.com/nixeast/ProjectMS/blob/99e2a881c5e9c3c5f3a259c5a8d31669dda8ae1a/Source/ProjectMS/Enemy.cpp#L224)

9. 상호작용 오브젝트 작동
- 플레이어 캐릭터를 상호작용 오브젝트에 이동시켜 작동시킬 수 있습니다.
- 열리는 문의 경우에는 열리고, 열쇠와 같은 작동키가 필요한 오브젝트는 플레이어의 아이템 소지상태를 체크하여 작동유무를 판단합니다.
- [코드 보러가기](https://github.com/nixeast/ProjectMS/blob/99e2a881c5e9c3c5f3a259c5a8d31669dda8ae1a/Source/ProjectMS/Gate.cpp#L139)
