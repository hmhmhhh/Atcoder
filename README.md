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
で書けるようだ。逆にcharを1intにする際には
~~~
   S.at(j) - '0';
~~~
のように引き算にする必要がある。


・ビットに関連する知識まとめ  (参考)[https://qiita.com/drken/items/7c6ff2aa4d8fce1c9361]
| 定義 | 内容 |例|
----|---- |----
|a&b  | AND | 
| a|b | OR|
|if (bit&(1<<i)|i桁目に1があるかどうか|

bit探索の方法。{00...000,11...111(n桁)}までの探索は、以下のコードで可能
~~~
for (int bit=0;bit<(1<<n);b++){
....
}
~~~

# 20230107  
 ~~~
 vector<vector<int>> cn(N+1);
 ~~~
 第二成分の配列の大きさが決まっていない書き方。代入は
 ~~~
  cn.at(b).push_back(a);
 ~~~
 で可能
 
 
 
# 20220108   
(Queueの使い方)[https://atcoder.jp/contests/apg4b/tasks/APG4b_aa]
~~~
#include<queue>
queue<int> Q;
int main(){
Q.push(1);1をQに追加
if(Q.empty): Qが空か判定
pos=Q.front():先頭の要素をposに代入
Q.pop();先頭の要素を除外
Q.popback()
Q.push(a):aを最後尾に大入
}
~~~
https://atcoder.jp/contests/abc256/submissions/me2
pow(2,N)は実数
 
 
 # 20230112  
mapは自動的にソートされている。

~~~
cout << q.rbegin()->first - q.begin()->first << endl;
~~~
自分の回答参照https://atcoder.jp/contests/abc253/tasks/abc253_c

# 2023-01-15  
(この試験)[https://atcoder.jp/contests/abc285]に参加したがABCDの４問完答だった。
Cでの躓いた点としては、long long 型のpow関数を使用する際には
~~~
long long ll_pow(long long a, long long n){
    long long ans = 1;
    for (long long i = 0; i < n;i++){
        ans *= a;
    }
    return ans;
}
~~~
のように自作の関数を使用するべき点を知らなかった。
またD問題では深さ優先を使おうとしてbool型の関数を定義したのだが、なぜか正しい返り値を返さず結局参照することで値返し、
成功したが非常にイライラした。

~~~
s.erase(unique(s.begin(), s.end()), s.end());
~~~
https://atcoder.jp/contests/abc036/submissions/me



~~~
map<int,vector<int>>
~~~
とすると、連想配列とベクトルを合わせるようにできる。

mapfor
~~~
for (auto p : score) {
  auto k = p.first;
  auto v = p.second;
  cout << k << " => " << v << endl;
}
~~~



~~~
https://atcoder.jp/contests/abc231/tasks/abc231_c
~~~


#2023 0127 
~~~
int main() {
  vector<int> V = {1, 2, 3, 4, 5};
  int idx = lower_bound(V.begin(), V.end(), 0) - V.begin();
  cout << idx << endl;
  idx = lower_bound(V.begin(), V.end(), 1) - V.begin();
  cout << idx << endl;
  idx = lower_bound(V.begin(), V.end(), 2) - V.begin();
  cout << idx << endl;
  idx = lower_bound(V.begin(), V.end(), 5) - V.begin();
  cout << idx << endl;
  idx = lower_bound(V.begin(), V.end(), 6) - V.begin();
  cout << idx << endl;
  cout << "-------------------------" << endl;
  idx = upper_bound(V.begin(), V.end(), 0) - V.begin();
  cout << idx << endl;
  idx = upper_bound(V.begin(), V.end(), 2) - V.begin();
  cout << idx << endl;
  idx = upper_bound(V.begin(), V.end(), 5) - V.begin();
  cout << idx << endl;
  idx = upper_bound(V.begin(), V.end(), 6) - V.begin();
  cout << idx << endl;
}
~~~
結果
~~~
0
0
1
4
5
-------------------------
0
2
5
5
~~~

良問
https://atcoder.jp/contests/abc211/tasks/abc211_d



配列が等しい同化は"="/を使用することが出来る。
https://atcoder.jp/contests/abc254/editorial/4051　の29行目

https://atcoder.jp/contests/abc279/tasks/abc279_d 

# AtCoder Beginner Contest 226 は解答AC
