# A Fine Cipher
## 問題
怪しげなグループから暗号化された文字列を受信した、これを解読する。
## 解法
encのみ渡されて暗号化ファイルはなし、NOTEに'Make sure you wrap the flag'とあることから一問目のようにFlagのフォーマットから推測するのも難しい...
手がかりがなさげに見えるが'A Fine Cipher'とGoogle検索にかけてみるとAffine Cipherというものが出てくる。
Affine暗号は以下の形式で暗号化する単純な暗号である。
```
F(x) = (α * x + β) mod 26
```
考えられるαとβはそれぞれ0~25までの26通りずつなので26^2通りを総当たりすればよい。計算量はO(α*β*|S|)で余裕で実行可能。
ちなみに、復号された文字列に"CRYPTO"や"CTF"などが入っていそうと当たりをつけておくと効率的に候補を探せるのだが、解いた時には思いつかずに気合の目grepをした。
