# 配列や変数に値を代入して処理を繰り返す
```Ruby
for i in (0..1)<Br>
 puts i<Br>
end<Br>
```
=>出力結果<Br>
０<Br>
１
# 入れ子構造にできる
```Ruby
for i in (0..1)<Br>
 puts i<Br>
 for j in (0..1)<Br>
  puts j<Br>
 end<Br>
end<Br>
```
=>出力結果<Br>
0  親の１回目<Br>
0  子の１回目<Br>
1  子の２回目<Br>
1  親の２回目<Br>
0  子の１回目<Br>
1  子の２回目<Br>