<p>📌 기본 사용법</p>
<pre><code>short BitConverter.ToInt16(byte[] value, int startIndex)력하세요</code></pre><p>🔹 매개변수
value: 변환할 바이트 배열
startIndex: 변환을 시작할 value 배열의 인덱스 (0부터 시작)</p>
<p>🔹 반환값
value[startIndex]와 value[startIndex + 1]을 short로 변환한 값</p>
<p>📌 예제 코드
✔ 기본 예제</p>
<pre><code>using System;


class Program
{
    static void Main()
    {
        byte[] byteArray = { 0x01, 0x00, 0xFF, 0x7F, 0x00, 0x80 };

        short value1 = BitConverter.ToInt16(byteArray, 0); // 0x0001 -&gt; 1
        short value2 = BitConverter.ToInt16(byteArray, 2); // 0x7FFF -&gt; 32767 (Int16.MaxValue)
        short value3 = BitConverter.ToInt16(byteArray, 4); // 0x8000 -&gt; -32768 (Int16.MinValue)

        Console.WriteLine(value1); // 1
        Console.WriteLine(value2); // 32767
        Console.WriteLine(value3); // -32768
    }
}</code></pre><p>📌 설명</p>
<p>byteArray[0] = 0x01, byteArray[1] = 0x00 → 0x0001 → 1
byteArray[2] = 0xFF, byteArray[3] = 0x7F → 0x7FFF → 32767 (최대 short 값)
byteArray[4] = 0x00, byteArray[5] = 0x80 → 0x8000 → -32768 (최소 short 값)</p>
<p>📌 예외 처리
ArgumentNullException: byte[]가 null이면 예외 발생
ArgumentOutOfRangeException: startIndex가 배열 범위를 벗어나면 예외 발생</p>