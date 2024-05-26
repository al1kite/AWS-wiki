## S3 에 React 프로젝트 호스팅 하기

## 웹 호스팅 설정하기
S3 실습에서와 동일하게 버킷을 생성해준다.
생성된 버킷에 속성으로 들어가 정적 웹사이트 호스팅 편집을 눌러준다.
<img width="1099" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/6dff0f67-f4a9-44d5-90d7-50bef9be919a">
<img width="1084" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/1c8221d0-eddc-4e98-a1cb-6163a6ce7541">

정적 웹사이트 호스팅에서 정적 웹사이트 호스팅을 활성화 해주고 유형을 정적 웹 사이트 호스팅으로 해준 뒤,
인덱스 문서와 오류 문서를 모두 index.html 로 변경하고 저장한다.
<img width="847" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/2ef9fec9-54ea-42e4-a7bd-8f8f6e56a5a0">

### S3에 업로드하기
이제 생성된 버켓에 React 파일을 올려야 하는데 그 전에 React 빌드 파일을 준비해준다. 
```
npm run build
```
React 프로젝트에서 다음 명령어를 입력해 생성된 빌드 폴더 내부 파일을 전부 버킷에 업로드 해준다.
CI/CD 관련 스크립트 작성 과정은 일단 생략했다.
<img width="864" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/d8b93345-cdba-4fed-b39e-e0b587f808ae">
<img width="1314" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/f9fc7e0c-efa6-4b6b-9ed2-b571c527612d">
<img width="1330" src="https://github.com/cotes2020/jekyll-theme-chirpy/assets/102217402/33811f40-1680-431b-b19c-db9167d3af1d">

그럼 다음과 같이 정적 웹사이트 호스팅이 잘 되었고, 하단에 뜬 호스팅된 링크에 들어가거나 
index.html 에 들어가 동일한 링크인 생성된 객체 url 에 접속하면 웹사이트가 잘 뜨는 걸 확인할 수 있다.
