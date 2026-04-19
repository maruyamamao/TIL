# C#の整数型
## C#の整数型の種類と書き方
- 「s」は、符号がつく整数型、s = signedのこと
- 「u」は、符号がつかない整数型、u = unsignedのこと
- intが基本（迷ったらこれ）
- longは大きい数のとき
- byte系はメモリ節約やデータ処理で使う
- uint / ulong はマイナスが使えない

### sbyte(符号あり、-128 ~ 127)
```c#:書き方
class Integer{
    public static void Main(){
        sbyte a = 127;
        sbyte b = -128;
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
127
-128
```
```c#:エラー
class Integer{
    public static void Main(){
        sbyte c = 128;
        Console.WriteLine(c);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(6,19): error CS0031: Constant value `128' cannot be converted to a `sbyte'
//エラーメッセージは「128は sbyte に入らないよ！」という意味
```


### byte（符号なし、0 ~ 255）
```c#:書き方
class Integer{
    public static void Main(){
        byte a = 0;
        byte b = 255;
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
0
255
```
```c#:エラー
class Integer{
    public static void Main(){
        byte c = -1;
        Console.WriteLine(c);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(6,19): error CS0031: Constant value `-1' cannot be converted to a `byte'
```


### short（符号あり、-32768 ~ 32767）
```c#:書き方
class Integer{
    public static void Main(){
        short a = 1000;
        short b = -1500;
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
1000
-1500
```
```c#:エラー
using System;
class Integer{
    public static void Main(){
        short c = -32769;
        Console.WriteLine(c);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(6,19): error CS0031: Constant value `-32769' cannot be converted to a `short'
```


### ushort（符号なし、0 ~ 65535）
```c#:書き方
class Integer{
    public static void Main(){
        ushort a = 0;
        ushort b = 65535;
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
0
65535
```
```c#:エラー
class Integer{
    public static void Main(){
        ushort c = -1;
        Console.WriteLine(c);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(6,19): error CS0031: Constant value `-1' cannot be converted to a `ushort'
```


### int（符号あり、-2147483648 ~ 2147483647）
```c#:書き方
class Integer{
    public static void Main(){
        int a = -20000;
        int b = 123456;
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
-20000
123456
```
```c#:エラー
class Integer{
    public static void Main(){
        int c = 2147483648;
        Console.WriteLine(c);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(6,19): error CS0031: Constant value `2147483648' cannot be converted to a `int'
```


### uint（符号なし、0 ~ 4294967295）
```c#:書き方
class Integer{
    public static void Main(){
        uint a = 0;
        uint b = 1234567890;
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
0
1234567890
```
```c#:エラー
class Integer{
    public static void Main(){
        uint c = -1;
        Console.WriteLine(c);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(6,19): error CS0031: Constant value `-1' cannot be converted to a `uint'
```


### long（符号あり、-9223372036854775808 ~ 9223372036854775807）
※ 数字の最後に L をつける！
```c#:書き方
class Integer{
    public static void Main(){
        long a = 1234567891234567891L;
        long b = -1234567891234567891L;
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
1234567891234567891
-1234567891234567891
```
```c#:エラー
class Integer{
    public static void Main(){
        long c = 10000000000000000000L;
        Console.WriteLine(c);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(6,19): error CS0031: Constant value `10000000000000000000L' cannot be converted to a `long'
```


### ulong（符号なし、0 ~ 18446744073709551615）
※ 数字の最後にUL をつける
```c#:書き方
class Integer{
    public static void Main(){
        ulong a = 0;
        ulong b = 1000000000000000000UL;
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
0
1000000000000000000
```
```c#:エラー
class Integer{
    public static void Main(){
        ulong c = -1;
        Console.WriteLine(c);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(6,19): error CS0031: Constant value `-1' cannot be converted to a `ulong'
```

## 整数型の種類まとめ
|型の名前|読み方|値の範囲|ビット数|
|:---|:---|:---|:---|
|sbyte|エスバイト|-128 ~ 127|8|
|byte|バイト|0 ~ 255|8|
|short|ショート|-32768 ~ 32767|16|
|ushort|ユーショート|0 ~ 65535|16|
|int|イント|-2147483648 ~ 2147483647|32|
|uint|ユーイント|0 ~ 4294967295|32|
|long|ロング|-9223372036854775808 ~ 9223372036854775807|64|
|ulong|ユーロング|0 ~ 18446744073709551615|64|
