# TIL
-당일 학습한 내용을 정리합니다.

## 2023-03-27
- git bash / iterms2 설치
- 기초 리눅스 명령어
- vim 사용법
## 2023-03-28
- commit
    - 개념
    - 커밋을 언제 만드는가
    - 커밋 크기
- 저장소
    - 개념
    - 일반 폴더와 저장소의 차이(`.git`폴더 유무)
## 2023-03-29
- 커밋 만들기
    -   `git commit -m "작성할 메시지"`
- 스테이징 영역
    - `git add` 명령어로 커밋에 포함시키고 싶은 파일만 스테이징 영역에 추가
    - `git push origin main`
## 2023-04-03
- python
    - 문자열의 메소드
        - `s.capitalize` 첫번째 글자만 대문자, 나머지 소문자로 반환
        - `s.center` 문자열 가운데 정렬한 길이의 width의 문자열 반환
        - `s.count` 문자열s에 문자열 sub가 출현한 횟수 반환
        - `s.endswith` 문자열 s가 ~로 끝나면 `true`, 아니면 `false`
        - `s.find` 문자열 s에 문자열의 첫번째 위치 반환. 인덱스 `start`,`end`가 있으면 그 위치에서 찾기 시작
        - `s,join` 문자열의 원소로 갖는 문자열을 문자열로 연결하여 반환
        - `s.strip` 앞뒤 공백 제거
        - `s.split` 워드 단위로 분리한 문자열을 원소로 갖는 리스트 반환
        - `s.title` 각 단어 첫 글자를 대문자로 변환하여 반환
        - `s.lower` s의 글자를 모두 소문자로 바꾼 문자열을 반환
        - `s.upper` s의 글자를 모두 대문자로 바꾼 문자열을 반환
        - `s.isalnum` s에 숫자 문자만 있으면 `true`, 특수문자가 포함 되면 `false`
        - `s.isalpha` s에 문자만 있으면 `true` , 그렇지 않으면 `false`
        - `s.isdigit` s에 0~9 사이 숫자만 있으면 `true`, 그렇지 않으면 `false`
    - 포맷 문자열
        - ` f'...{ }...` 
- 깃 고급 특강
    - 커밋 개념 복습
        - 커밋 메시지 입력 : `git commit -m` , `git commit --message`
        - 깃헙에 보내기 명령어 : `git remote add origin https://github.com/somedding/(저장소이름).git` , `git branch -M main` , `git push -u origin main` 
        - 깃헙에 커밋 후 push  `git push -u origin main`
    - 브랜치 
        - `git branch (브랜치 이름)` : `q` 누르거나 `command + c`로 나갈 수 있다
        - branch 확인하기 : `git branch`
        - 작업하는 브랜치 변경하기 : `git switch (브랜치 이름)` `git checkout (브랜치이름)`
        - branch 병합 : 
    - 기타
        - 커밋 수정 : `git commit reset`
        