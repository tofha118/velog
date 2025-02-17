<p>📌 기본 사용법</p>
<pre><code>ArraySegment&lt;byte&gt; segment = new ArraySegment&lt;byte&gt;(byteArray, offset, count);</code></pre><p>🔹 매개변수
byteArray: 원본 byte[] 배열
offset: 시작 인덱스
count: 길이 (몇 개의 요소를 포함할지)</p>
<p>📌 예제 코드
✔ 기본 사용법</p>
<pre><code>using System;

class Program
{
    static void Main()
    {
        byte[] byteArray = { 10, 20, 30, 40, 50 };

        ArraySegment&lt;byte&gt; segment = new ArraySegment&lt;byte&gt;(byteArray, 1, 3);

        Console.WriteLine(string.Join(&quot;, &quot;, segment)); // 20, 30, 40
    }
}</code></pre><p>📌 설명</p>
<p>byteArray의 인덱스 1부터 3개(20, 30, 40)를 segment가 참조</p>
<p>📌 ArraySegment의 특징
참조형 → 원본 배열을 수정하면 ArraySegment도 변경됨
읽기/쓰기 가능 → 값 변경 가능
새로운 배열 생성 없음 → 성능 최적화</p>
<p>✔ 참조형 데이터 확인</p>
<pre><code>byteArray[2] = 99; // 원본 배열 변경
Console.WriteLine(string.Join(&quot;, &quot;, segment)); // 20, 99, 40</code></pre><p>💡 segment도 변경됨! (새로운 배열이 아니라 기존 배열을 참조하기 때문)</p>
<p>📌 ArraySegment의 주요 속성
속성    설명
.Array    원본 byte[] 배열 반환
.Offset    세그먼트 시작 인덱스
.Count    포함된 요소 개수</p>
<p>✔ 속성 사용 예제</p>
<pre><code>Console.WriteLine(segment.Array == byteArray); // True
Console.WriteLine(segment.Offset); // 1
Console.WriteLine(segment.Count);  // 3</code></pre>