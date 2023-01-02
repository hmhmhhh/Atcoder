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
[abc270_b](https://atcoder.jp/contests/abc270/tasks/abc270_b)の問題は適切に、
場合分けすることが必要で、個人的に教育的だった。


# 20230101  
しばらく仕事のため中断していた。
文字列と数字のキャストは以下のようにできる。
~~~
#include <bits/stdc++.h>
using namespace std;
 
int main() {
  string s = "100";
  int n = stoi(s);
  cout << n << endl;
  string ss=to_string(n);
  cout<<ss<<endl;
}
100
100
~~~  
・ビット操作:  
~~~
(1<<i): i番目に1他0のもの1<<3:100  
~~~

・配列の参照:　　
vec.at(i): i番目を参照
・文字列Sからの抽出
S.substr(init,length):init文字目からlength文字抽出する。

・atoi(S.at(i))ができないのはなぜだ？S.at(i)がchar型だから？このへん面倒くさいなぁ。。


・[ABC_266](https://atcoder.jp/contests/abc266/tasks/abc266_b)  

# 20230102  
int型の変数cをchar型に変換する方法は
~~~
char('0'+c)
~~~
で書けるようだ。
