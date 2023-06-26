코딩 컨벤션
=========
- 코딩 컨벤션은 유지보수를 위한 일종의 코딩 스타일 규약이다.

네이밍 시 대표적인 표기법
---------------------
- 카멜 표기법 : 첫 글자를 대문자로 적되, 맨 앞에 오는 글자는 소문자로 표기.<br>
**ex) userName**
- 파스칼 표기법(대문자 카멜 표기법) : 첫 글자를 대문자로 적는다. 맨 앞자도 대문자.<br>
 **ex) UserName**
- 헝가리안 표기법 : 접두어에 자료형을 알아볼 수 있게 표기.<br>
 **ex) strUserName**
- 스네이크 표기법 : 단어 사이에 언더바를 넣어서 표기.<br>
 **ex) user_name**

네이버/구글 JAVA 코딩 컨벤션
-------------------
### 1. Naming
- 식별자에는 영문/숫자/언더스코어(_)만 허용한다.
- 한국어 발음대로 표기 금지
- 대문자로 표기할 약어 명시(네이버) 
  - 클래스명, 변수명에 쓰일 단어 중 모든 글자를 대문자로 표기할 약어의 목록을 명시적으로 정의한다.<br>
     **ex) API**
- 클래스/인터페이스 이름에 파스칼 표기법 적용
<pre><code>ex) public class AccessToken {</code></pre>
- 클래스 이름은 면사나 명사절로 짓는다.
- 인터페이스의 이름은 명사/형용사 사용
<pre><code>ex) public interface AutoClosable {</code></pre>
- JUnit 등으로 작성한 테스트 코드를 담은 클래스는 "Test"를 마지막에 붙인다.(네이버)
<pre><code>ex) public class WatcherTest {</code></pre>
- 메서드 이름에 카멜 표기법을 사용.
- 메서드 이름은 동사/전치사로 시작.
<pre><code>ex) 
동사사용 : renderHtml()
전환메서드의 전치사 : toString()
</code></pre>
- 상수는 대문자와 언더스코어로 구성
<pre><code>ex) public final String POSTAL_CODE_EXPRESSION = "POST";
</code></pre>
- 변수에 카멜 표기법 적용.
- 임시 변수 외에는 1글자 이름 사용 금지.

### 2. 선언 
- 한 줄에 한 문장만 사용한다.
<pre><code>ex) 
int base = 0;
int weight = 2;
</code></pre>
- 배열 선언에 오는 대괄호는 변수명 뒤에 붙이지 않는다.
<pre><code>ex) String[] names;
</code></pre>
- long 형 값의 마지막에 'L' 붙이기 (네이버)
  - 소문자 'l' 보다 숫자 '1' 과의 차이가 커서 가독성이 높아진다.

### 3. 들여쓰기
- 네이버의 경우 탭(tab) 문자를 사용하여 들여쓴다. 탬 대신 스페이스를 사용하지 않는다. 이를 잘 준수하기 위해서 스페이스와 탭을 구별해서 보여주도록 에디터를 설정한다.
  - 탭의 크기는 4개의 스페이스
- 구글의 경우 탭 문자를 사용하지 않고, 2개의 스페이스를 사용한다.

### 4. 중괄호
- 줄의 마지막에 시작 중괄호 '{' 를 쓰고 새줄을 시작한다.
- 블럭을 마친 후에는 새줄에 중괄호를 닫는다 '}'
<pre><code>ex) 
if (exp == null) {
    return false;
}
</code></pre>
- 닫는 중괄호와 같은 줄에 else, catch, finally, while 선언
<pre><code>ex)
if (exp == null) {
    ...
} else {
    ...
}
</code></pre>
- 빈 블럭에 새줄 없이 중괄호 닫기 허용
<pre><code>ex) public void close() {}
</code></pre>
- 구글의 경우 catch 블록을 비워놓는 경우 주석을 활용한다.
<pre><code>ex) 
} catch (NumberFormatException ok) {
    // it's not numeric; that's fine, just continue;
}
</code></pre>

- 조건/반복문에 중괄호를 필수로 사용한다.
<pre><code>나쁜 예) if (exp == null) return false;
</code></pre>

### 5. 줄바꿈
- 네이버의 경우 최대 줄 너비는 120자 / 구글의 경우 100자 사용
- 줄바꿈 후 추가 들여쓰기
  - 네이버의 경우 줄바꿈 이후 이어지는 줄에는 최초 시작한 줄에서보다 적어도 1단계의 들여쓰기를 더 추가한다.
  - 구글도 최소 4개의 스페이스를 들여쓴다.

### 6. 빈 줄
- 메소드 사이에 빈 줄을 삽입한다.

### 7. 공백
- 중괄호 시작 전, 종료 후에 공백 삽입
<pre><code>ex)
public void printWarnMessage(String line) {
    ....
}
</code></pre>
- 제어문 키워드와 여는 소괄호 사이에 공백 삽입
<pre><code>ex)
if (maxLine > LIMITED) {
    reuturn false;
}
</code></pre>
- 타입 캐스팅에 쓰이는 소괄호 내부 공백 미삽입
<pre><code>ex) String message = (String)rawLine;
</code></pre>
- 구글에서는 세로 정렬 스타일을 권장하지 않는다. 
  - 가독성은 좋으나 유지보수에 악영향을 미친다. 
<pre><code>ex)
private int    x;
private Color  color;
</code></pre>

정적 코드 분석 도구
----------------
- JAVA : Checkstyle
- JS : ESLint