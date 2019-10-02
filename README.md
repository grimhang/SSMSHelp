# SSMS 사용법 가이드

***
## 1. SSMS 한글로 바꾸기
  점프서버는 영문OS라서 SSMS도 영문으로 깔았을 텐데 한글로 표시언어를 바꾸자.  
  SSMS실행 / Tools / Options / Environment / International Settings에 현재는 Same as Microsoft Windows로 되어 있다.  
  한국어를 선택하고 SSMS 재실행하면 한글로 바꿔있다.

* #### 1.1 한글 전환 문제
  sql을 작성중 다른 화면으로 이동했다 돌아오면 한글 상태로 자판이 자동 변경되는 문제가 있다.  
  15년 넘은 버그로 해결이 안되고 있다.  
  다음과 같이 임시 조치 가능  
    > 메뉴 / 쿼리 / 쿼리 옵션 창에서 영문으로 자판을 바꾸면 그 다음부터는 영문이 기본값.  

## 2. 코딩글꼴 D2로 바꾸기
  고정폭 글꼴을 지정하자. 한글에 가장 좋은 D2글꼴을 파일서버/설치파일/d2 에서 받아 설치하자  

  SSMS / 도구 / 옵션 / 환경 / 글꼴 및 색 에서 바꿀수 있다.  
  <img width="600" height="" src="image/01_fontchange.png" border="5"></img>
    

## 3. 단축키 사용하기
  특정한 쿼리 명령어를 사용자 단축키를 지정할수 있다.  
  SSMS / 도구 / 옵션 / 환경 / 키보드 / 쿼리 바로 가기 에서 지정하자. 지정완료 후 ssms 재실행  
  
  이름을 선택하고 해당 단축키 실행하면 된다

<table>
    <tr>
        <th>단축키</th>
        <th>sql</th>
        <th>기능</th>
    </tr>
    <tr>
        <td>ctrl + 3</td>
        <td>SELECT * <br> FROM INFORMATION_SCHEMA.TABLES<br>ORDER BY TABLE_NAME</td>
        <td>테이블 리스트 보기</td>
    </tr>
    <tr>
        <td>ctrl + 4</td>
        <td>SP_COLUMNS</td>
        <td>테이블 컬럼리스트 보기</td>
    </tr>
    <tr>
        <td>ctrl + 5</td>
        <td>SP_HELPTEXT</td>
        <td>프로시저, 함수명의 소스 보기.<br>
            단 결과가 표형태로 나와 불편한데 <br>
              메뉴 / 쿼리 / 결과처리방법 / 표형태로 결과표시(Ctrl + T)으로 바꾸고 실행.</td>
    </tr>
    <tr>
        <td>ctrl + 6</td>
        <td>SP_HELPINDEX</td>
        <td>테이블의 인덱스 보기</td>
    </tr>
</table>

## 4. SSMS 기본 캐릭터셋 바꾸기 (UTF-8 BOM)
  SQL 소스에 한글을 쓰면 저장할때마다 매번 적합하지 않은 캐릭터 셋이라고 하여 다른 인코딩으로 저장하도록 메시지가 뜰 수도 있다.
  아예 처음부터 한글 지원 인코딩되게 SQL템플릿을 수정하자.  

  아래 위치에 있는 SQLFile.sql을 "파일서버/설치폴더/SSMS/SQLFile.sql" 파일로 바꿔치기 한다.  
>  C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\SqlWorkbenchProjectItems\Sql\SQLFile.sql