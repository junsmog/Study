# 소스트리를 활용한 GitHub 사용법#

외부 저장소인 `GitHub`는 대중적으로 사용하지만, 사용법의 불편함을 느낀 사람들은 접근 조차 시도를 못하는 경우를 발견하였었습니다. 조금 더 쉽게 접근할 수 없을까? 생각 했을 때 `소스트리` 라는 좋은 툴이 있어서 `소스트리` 을 활용하여 `GitHub` 사용할 수 있는 방법을 공유 하려고 합니다.

## 소스트리 다운로드

`소스트리 `는 터미널(윈도우에서는 명령프로토콜)을 통하여 `GitHub`을 등록했던 것을 조금 더 명확하고 쉽게 GUI 을 제공한 툴입니다. [소스트리](https://www.sourcetreeapp.com/) 사이트에 방문하여 소스트리를 다운받아 설치합니다.

##Github 계정 연결하기##

`소스트리` 설치 후 어플리케이션을 실행하여 `설정` 으로 넘어갑니다. 왼쪽 하단에 `추가...` 버튼이 보입니다. 추가 버튼을 클릭하여 계정 추가 화면으로 진입합니다.  

[![Alt text](https://github.com/FaithDeveloper/Study/blob/master/github/image/git001.png?raw=true)](https://github.com/FaithDeveloper/Study/blob/master/github/image/git001.png?raw=true)

계정 추가 화면에서 `호스트` 항목이 있습니다. 호스트를 클릭 하면 `Bitbucket`, `GitHub`을 선택할 수 있는 카테고리가 나오며  `GitHub`을 클릭 합니다. 그 후 `사용자 이름` 항목에서 `계정연결` 을 클릭하여 `GitHub` 계정을 로그인하여 연결합니다.

[![Alt text](https://github.com/FaithDeveloper/Study/blob/master/github/image/git002.png?raw=true)](https://github.com/FaithDeveloper/Study/blob/master/github/image/git002.png?raw=true)

위 과정까지 완료 `GitHub` 계정 연결이 완료 되었습니다.

## 원격 저장소 연결하기##

소스트리는 원격으로 GitHub에 저장된 저장소를 가져오는 `클론` 기능과 로컬에 있는 데이터를 GitHub에 업로드하는 `푸시` 기능이 있습니다. 먼저 원격 저장소 연결하는 방법을 설명하겠습니다. 

GitHub 계정 연결 완료 후 소스트리 어플리케이션 화면으로 돌아오게되면 상단에 `로컬`,`원격` 이렇게 나눠져 있는 것을 확인할 수 있습니다. 원격 저장소에 있는 저장소 내용을 가져올 계획이니 `원격` 을 클릭 합니다.

밑에 사진과 같이 저장소 이름과 `클론` 이라는 버튼이 보입니다. `클론` 버튼을 클릭합니다. 그러면 원격 저장소에 있는 프로젝트가 다운 받아집니다.

```
Git Clone(클론)이란?

git clone 은 사실 다른 명령어를 몇 개 실행합니다. 디렉토리를 만들고 디렉토리로 들어가고 나서 git init 명령으로 빈 Git 저장소를 만듭니다. 그다음 입력한 URL을 origin 이라는(기본값) 이름의 리모트로 추가하고(git remote add) git fetch 명령으로 리모트 저장소에서 데이터를 가져옵니다. 마지막으로 최종 커밋을 워킹 디렉토리에 Checkout 합니다(git checkout). 따라서 git clone 을 하면 별도의 설정 없이 git add, git commit, git push 할 수 있습니다.
```

