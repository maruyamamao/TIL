## c#の実数型とは
小数点以下まで扱える型のこと

## 実数型の種類と書き方
### float（単精度浮動小数点、 ±1.5 × 10⁻⁴⁵ ～ ±3.4 × 10³⁸）
使用用途はメモリ節約したいとき、精度がそこまでいらない計算の時

※文字の最後に「f」をつける、double扱いになるため
```c#:書き方
class flo{
    public static void Main(){
        float a = 3.14f;
        float b = 1.23e10f;  // 1.23 × 10^10
        
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
3.i4
1.23E+10
```
```c#:エラー
class flo{
    public static void Main(){
        float a = 3.14;
        
        Console.WriteLine(a);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(4,19): error CS0664: Literal of type double cannot be implicitly converted to type `float'. Add suffix `f' to create a literal of this type
```


### double（倍精度浮動小数点、 ±5.0 × 10⁻³²⁴ ～ ±1.7 × 10³⁰⁸）
使用用途は一般的な計算（デフォルト）、特に指定がなければこれを使う

※「f」はつけなくてよい
```c#:書き方
class flo{
    public static void Main(){
        double a = 3.14159265358979;
        double b = 1.23e100;
        
        Console.WriteLine(a);
        Console.WriteLine(b);
    }
}
```
```html:結果
3.14159265358979
1.23E+100
```


### decimal（高精度、 ±1.0 × 10⁻²⁸ ～ ±7.9 × 10²⁸）
使用用途はお金・金額計算、誤差を絶対に出したくない処理の時

※文字の最後に「m」をつける
```c#:書き方
class flo{
    public static void Main(){
        decimal a = 3.14m;
        
        Console.WriteLine(a);
    }
}
```
```html:結果
3.14
```
```c#:エラー
class flo{
    public static void Main(){
        decimal b = 3.14;
        
        Console.WriteLine(b);
    }
}


Compilation failed: 1 error(s), 0 warnings
Main.cs(4,21): error CS0664: Literal of type double cannot be implicitly converted to type `decimal'. Add suffix `m' to create a literal of this type
```

## なぜ「decimal型」が必要なのか
floatとdoubleは計算時に誤差がでる
```c#:doubleの場合
double x = 0.1 + 0.2;
Console.WriteLine(x);  // 0.30000000000000004
```
decimalなら誤差が出ず、正確に計算できるため
```c#:decimalの場合
decimal x = 0.1m + 0.2m;
Console.WriteLine(x);  // 0.3
```

## 実数型の種類のまとめ
|型の名前|読み方|入る値の範囲|ビット数|
|:--------|:---------|:-------|:-------|
|float|フロート|±1.5 × 10⁻⁴⁵ ～ ±3.4 × 10³⁸|32|
|double|ダブル|±5.0 × 10⁻³²⁴ ～ ±1.7 × 10³⁰⁸|64|
|decimal|デシマル|±1.0 × 10⁻²⁸ ～ ±7.9 × 10²⁸|128|



