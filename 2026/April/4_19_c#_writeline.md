# C#文字列表示

### Write()メソッド
Write()メソッドは（）の中の文字列を画面に表示し、改行はしない。
```c#:書き方
class Hello{
    public static void Main(){
        Console.Write("Hello");
        Console.Write(" = ");
        Console.Write("こんにちは");
    }
}
```
```html:結果
Hello = こんにちは
```
### WriteLine()メソッド
WriteLine()メソッドは（）の中の文字列を画面に表示し、改行する。
```c#:書き方
class Hola{
    public static void Main(){
        Console.WriteLine("Hola");
        Console.WriteLine(" = ");
        Console.WriteLine("こんにちは");
    }
}
```
```html:結果
Hola
 = 
こんにちは
```
