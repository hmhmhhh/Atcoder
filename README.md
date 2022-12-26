# 20221224  
[abc279_c](https://atcoder.jp/contests/abc279/tasks/abc279_c)にすこし詰まった。
並び変えて一致するか調べる際には、sortを利用するとよい。

[abc278_c](https://atcoder.jp/contests/abc278/tasks/abc278_c)はフォロワーの組が高々Qであることに気が付けなかった。
また空集合にリストが入っているかif文を書くと、エラーが生じることが分かった。
リストではなく文字列に変換してAC.
~~~  
>>>A=set()
>>>['1'] in A 
TypeError: unhashable type: 'list'
~~~  


# 20221225   
C++に少しずつ挑戦したいと思う。
文字列に関してエラーが出たが、charは'',stringは" "で囲む必要があるようだ  
int 型についてもエラーが[この鉄則A12](https://atcoder.jp/contests/tessoku-book/tasks/tessoku_book_l)を解いていっる時に生じた。intをlong long型することで即ACになった..はぁ。。

文字列の結合も意味不明。
~~~
#include <bits/stdc++.h>
using namespace std;
int main() {
  string hello = "Hello";
  cout << hello[1]+hello[0] << endl;
}
----
#結果:173
~~~
?????C++の仕様を勉強しなくては。。はぁ。。

# 20221226  
(abc270_b)[https://atcoder.jp/contests/abc270/tasks/abc270_b]の問題は適切に、
場合分けすることが必要で、個人的に教育的だった。
