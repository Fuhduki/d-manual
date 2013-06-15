# 問題の回答

## 001

* 問1

~~~~d
import std.stdio;

void main()
{
    writeln("%s, %s", "Hello", "World!");
}
~~~~


* 問2

~~~~d
import std.stdio;

void main(){
    writeln("Hello, World");
}
~~~~

* 問3 解答なし


## 002

* 問1 解答省略

* 問2 解答なし


## 003

* 問1

コンピュータでは、負の数は2の補数を用いて表されます。
2の補数の前に1の補数の説明をしましょう。

2進数における1の補数とは、各ビットの反転になります。
たとえば、8bitの`3`は`00000011`ですから、1の補数は`11111100`になります。
2の補数は、この1の補数に1を加算した値です。
すなわち、`11111101`が`3`の2の補数で、`-3`の2進数表現です。

このようにすることで、例えば`3 + -3`は

~~~~
  00000011
+ 11111101
----------
 100000000

->00000000   <- 先頭1bit(MSB)を無視した8bitは0を示す
~~~~

というように、オーバーフローしてちゃんと`0`になります。

`>>`はMSBを維持しながら、シフトするので、`-3 >> 1`は`11111110`になります。
`11111110`は、10進数表現に直すとどうなるかが問題ですが、逆に`1`を引いてからビット反転すれば、絶対値の10進数表現になります。
つまり、`11111110 - 1 => 11111101 =(flip)> 00000010`となり、`-2`であることがわかります。

* 問2

`>>>`は符号を維持しませんが、ビット表現の特性で`<<`はオーバーフローしない限り符号を維持し続けます。
というのは、正の数であれば、整数値はMSBから`0`がいくつか続いた後`1`がやっと出現します。
負の数であれば、MSBはからは`1`が幾つか続いた後`0`がやっと出現します。
よって、オーバーフローにならない限りは、値の符号は変わらないことがわかります。


## 004

* 問1

~~~~d
import std.stdio;
import std.array;

void main()
{
    string line = readln();
    line.popFront();
    line.popFront();
    write(line);

    line = readln();
    line.popFront();
    line.popFront();
    write(line);

    line = readln();
    line.popFront();
    line.popFront();
    write(line);
}
~~~~


* 問2

~~~~
%2$s - %1$x1016
~~~~


* 問3

~~~~
3
3
~~~~

## 005

* 問1 ブロックに注意


## 006

* 問1

インクリメントに注意


* 問2 解答例

~~~~d
{
    auto index = <exprUpper>;
    auto exprLower = <exprLower>;
    for(; index > exprLower; --index){
        auto <identifier> = index - 1;
        <statement>
    }
}
~~~~


* 問3

~~~~d
import std.stdio;

void main()
{
    int sum;

    foreach(i; 0 .. 1000)
        if((i % 3) == 0 || (i % 5) == 0)
            sum += i;

    writeln(sum);
}
~~~~


* 問4

~~~~d
import std.stdio;

void main()
{
    int fib = 1;
    int fib_1 = 1;
    int fib_2 = 0;

    int sum = 0;

    while(fib < 4_000_000)
    {
        if(fib % 2 == 0)
        sum += fib;

        fib_2 = fib_1;
        fib_1 = fib;
        fib = fib_2 + fib_1;
    }

    writeln(sum);
}
~~~~

~~~~

~~~~


* 問5

~~~~d
import std.stdio;

void main()
{
    int sumPow2;
    int pow2Sum;

    foreach(i; 1 .. 101){
        sumPow2 += i;
        pow2Sum += i ^^ 2;
    }

    sumPow2 ^^= 2;
    writeln(sumPow2 - pow2Sum);
}
~~~~

~~~~
25164150
~~~~


* 問6

~~~~d
import std.stdio;

void main()
{
    int cnt;
    int sum;

    while(1){
        int n;
        readf("%s\n", &n);

        if(n < 0){
            writeln(sum / cnt);
            break;
        }else if(n < 10)
            continue;
        
        sum += n;
        ++cnt;
    }
}
~~~~

## 007

* 問1

~~~~d
import std.stdio, std.string;

void main()
{
    string line = readln().chomp();

    int v1, v2;
    dchar op;
    int sw;

    foreach(c; line){
        switch(c){
            case '0': .. case '9':
                if(!sw)
                    v1 = v1 * 10 + (c - '0');
                else
                    v2 = v2 * 10 + (c - '0');
                break;

            case ' ':
                continue;

            case '+', '-', '*', '/':
                if(sw){
                    writeln("数式がおかしいよ！");
                    return;
                }

                op = c;
                sw = 1;
                break;

            default:
                writeln("数式がおかしいよ！");
                return;
        }
    }

    switch(op){
        case '+':
            writeln(v1 + v2);
            break;

        case '-':
            writeln(v1 - v2);
            break;

        case '*':
            writeln(v1 * v2);
            break;

        case '/':
            writeln(v1 / v2);
            break;

        default:
            writeln("数式がおかしいよ！");
            return;
    }
}
~~~~