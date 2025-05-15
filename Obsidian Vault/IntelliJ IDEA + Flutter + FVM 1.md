> 이 문서에 macOS(15.4.1) / IntelliJ IDEA(2024.2.3 Ultimate Edition) 기준, Flutter를 FVM으로 세팅하는 방법을 정리했습니다.
***
## 0. 선행 작업
1. nicekos-flutter git clone
2. nicekos-flutter 프로젝트를 IntelliJ IDEA로 열고 터미널까지 킨 상태
3. 이후 터미널에서 명령어 입력 진행
***
## 1. Homebrew 설치
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
***
## 2. Homebrew 버전 확인
```shell
brew -v
```

### 2.1. Homebrew 버전 확인 불가 시 아래 명령어 차례대로 입력 진행 (계정명 확인 방법: Finder > 이동 > 홈 > 좌측 상단 확인)
```shell
echo '# Set PATH, MANPATH, etc., for Homebrew.' >> /Users/{계정명}/.zprofile
```

```shell
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/{계정명}/.zprofile
```

```shell
eval "$(/opt/homebrew/bin/brew shellenv)"
```
***
## 3. FVM(Flutter Version Manager) 설치

### 3.1. FVM Github Repository 추가
```shell
brew tap leoafarias/fvm
```
### 3.2. FVM 설치
```shell
brew install leoafarias/fvm/fvm
```
### 3.3 FVM 활성화
```shell
dart pub global activate fvm
```
***
## 4. FVM 사용
### 4.1. 현재 시점까지 릴리즈된 Flutter SDK 버전 및 출시일 확인
```shell
fvm releases
```
### 4.2. 특정 버전의 Flutter SDK 설치
```shell
fvm install 3.19.6
```
### 4.3. 특정 버전의 Flutter SDK 사용(프로젝트 단위)
```shell
fvm use 3.19.6
```
### 4.4. 설치된 Flutter SDK의 모든 버전 확인
```shell
fvm list
```
### 4.5. 현재 사용 중인 Flutter SDK 버전 확인
```shell
fvm flutter --version
```
### 4.6. Flutter Doctor
```shell
fvm flutter doctor
```
***
## 5. IntelliJ IDEA에서 Flutter, Dart 설정
1. 좌측 상단 IntelliJ IDEA 클릭 후 설정
2. 플러그인 > 마켓플레이스
3. Flutter 검색 후 설치
4. Dart 검색 후 설치
5. 설정 안에서 flutter 검색 또는 언어 및 프레임워크 > Flutter 접근
6. Flutter SDK path 비었을 경우는 괄호 안의 경로 참고하여 경로 설정 진행(/Users/zero.ryushin/fvm/versions/3.19.6)
7. 설정 안에서 dart 검색 또는 언어 및 프레임워크 > Dart 접근
8. 프로젝트 'nicekos-flutter'에서 Dart 지원 활성화 체크
9. Dart SDK 경로 비었을 경우는 괄호 안의 경로 참고하여 경로 설정 진행(/Users/zero.ryushin/fvm/versions/3.19.6/bin/cache/dart-sdk)
10. 다음 모듈에서 Dart 지원 활성화 안의 모든 체크박스 체크