<p>BitConverter.GetBytes 메서드는 숫자형 데이터(int, short, double, float 등)를 바이트 배열(byte[])로 변환하는 데 사용됩니다.</p>
<p>📌 기본 사용법</p>
<pre><code>byte[] BitConverter.GetBytes(data);</code></pre><p>🔹 매개변수
data: 변환할 숫자형 값 (int, short, long, float, double, bool, char, ushort, uint, ulong)</p>
<p>🔹 반환값
byte[] 배열 (리틀 엔디언 또는 빅 엔디언 형식)</p>
<p>📌 예제 코드
✔ 정수 변환</p>
<pre><code>using System;

class Program
{
    static void Main()
    {
        int number = 12345;
        byte[] bytes = BitConverter.GetBytes(number);

        Console.WriteLine(string.Join(&quot;, &quot;, bytes)); // 리틀 엔디언: 57, 48, 0, 0
    }
}</code></pre><p>📢 기본적으로 BitConverter는 시스템의 엔디언 방식을 따름 (Windows는 리틀 엔디언)</p>
<p>12345의 16진수 값: 0x00003039
리틀 엔디언 저장 방식: [0x39, 0x30, 0x00, 0x00]</p>
<p>✔ BitConverter.ToInt32와 함께 사용 (복원)</p>
<pre><code>
int original = 12345;
byte[] bytes = BitConverter.GetBytes(original);
int restored = BitConverter.ToInt32(bytes, 0);

Console.WriteLine(restored); // 12345</code></pre>