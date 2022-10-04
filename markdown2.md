### 学習記録
#### 2022-9-18

### 学習対象

- 〈教材〉JavaScriptの基礎を学ぼう
<br> 4章 変数を理解しよう
<br> 5章 定数を理解しよう
<br> 6章 条件分岐のif文を理解しよう
<br> 7章 条件分岐のswitch文を理解しよう

### 得たこと(自分の言葉で説明できる状態)

1. 変数
<br>// 変数の宣言
<br>let userName;
<br>// 値の代入
<br>userName = '侍太郎';
<br>// 変数の宣言・値の代入
<br>let userNumber = 55;
<br>// コンソールへの出力
<br>console.log(userName);
<br>console.log(userNumber);
<br>// 値の再代入
<br>userName = '侍花子';
<br>userNumber = 88;
<br>// コンソールへの出力
<br>console.log(userName);
<br>console.log(userNumber);

2. 定数
<br>// 定数の宣言・値の代入
<br>const shippingFee = 500;
<br>// コンソールへの出力
<br>console.log(shippingFee);
<br>// 値の再代入（エラー）
<br>shippingFee = 800;
<br>// コンソールへの出力
<br>console.log(shippingFee);

3. 条件分岐if文
<br>// 算術演算子を使った場合の戻り値を出力する
<br>console.log(45 + 18);
<br>// 比較演算子を使った場合の戻り値を出力する
<br>console.log(45 > 18);
<br>// 等価演算子を使った場合の戻り値を出力する
<br>console.log('5' == 5);
<br>// 厳密等価演算子を使った場合の戻り値を出力する
<br>console.log('5' === 5);
<br>// 変数numに0~4までのランダムな整数を代入する
<br>let num = Math.floor(Math.random() * 5);
<br>// 変数numの値を出力する　（確認用）
<br>console.log(num);
<br>// 変数numの値が4であれば、「大当たりです」という文字列出力する
<br>if (num === 4) {
<br>console.log('大当たりです');
<br>}
<br>// 変数numの値が3であれば、「あたりです」という文字列を出力する
<br>else if (num === 3) {
<br>console. log('当たりです');
<br>}
<br>// それ以外のときは、「はずれです」という文字を出力する
<br>else {
<br>console.log('はずれです');
<br>}

4. 条件分岐switch文
<br>// 変数numに0~4までのランダムな整数を代入する
<br>num =Math.floor(Math.random() * 5);
<br>// 変数numの値を出力する（確認用）
<br>console.log(num);
<br>// 変数numの値によって。出力する文字列を切り替える
<br>switch (num) {
    <br>case 2:
        <br>console.log('小吉です');
        <br>break;
    <br>case 3:
        <br>console.log('中吉です');
        <br>break;
    <br>case 4:
        <br>console.log('大吉です');
        <br>break;
    <br>default:
        <br>console.log('末吉です');
        <br>break;
}

    

### 難しかったこと

- if文とswitch文の構文が混合してしまう


### 解決できなかったこと




---------------------------------



### 学習記録
#### 2022-9-19

### 学習対象


- 〈教材〉JavaScriptの基礎を学ぼう
<br> 7章 条件分岐のswitch文を理解しよう
<br> 8章 繰り返し処理を理解しよう
<br> 9章 配列を理解しよう
<br> 10章 オブジェクトを理解しよう
<br>11章 関数を理解しよう
<br>12章 引数・戻り値を理解しよう

### 得たこと(自分の言葉で説明できる状態)

1. 繰り返し処理while文
<br>// 変数numに0~4までのランダムな整数を代入する
<br>let num = Math.floor(Math.random() * 5);
<br>// 変数numの最初の値を出力する　（確認用）
<br>console.log('最初の値は' + num + 'です');
<br>// 変数numの値が0以外である間、変数numの値を出力し続ける
<br>while (num !== 0) {
<br>// 変数numに0~4までのランダムな整数を再代入する
<br>num = Math.floor(Math.random() * 5);
<br>// 次の条件で比較される、変数numの現在の値を出力する
<br>console.log('現在の値は' + num + 'です');
<br>}

2. 繰り返し処理for文
<br>// １～１０までの数値を順番に出力する
<br>for (let i = 1; i <= 10; i++) {
<br>console.log(i);
<br>}

3. 配列
<br>// 配置の宣言と値の代入を行う
<br>const userNames = ['侍太郎', '侍一郎', '侍二郎', '侍三郎', '侍四郎'];
<br>// 配置の値を出力する
<br>console.log(userNames);
<br>// 2番目の要素を更新する
<br>userNames[1] = '侍花子';
<br>// 6番目に要素を追加する
<br>userNames[5] = '侍五郎';
<br>// 配置の値を出力する
<br>console.log(userNames);
<br>// 3番目の要素を出力する
<br>console.log(userNames[2]);

4. オブジェクト
<br>// オブジェクトの宣言と値の代入を行う
<br>const personalData = { name: '侍太郎', age :'36', gender :'男性'};
<br>// オブジェクトの値を出力する
<br>console.log(personalData);
<br>// 'age'というキーの値を更新する
<br>personalData.age = 37;
<br>// 新しくプロパティ（キーと値）を追加する
<br>personalData.address = '東京都';
<br>// オブジェクトの値を出力する
<br>console.log(personalData);
<br>console.log(personalData.gender);

5. 関数
<br>// 朝のあいさつを出力する関数を定義する
<br>const sayGoodMorning = () => {
<br>console.log('おはようございます');
<br>console.log('昨日はよく眠れましたか？');
<br>console.log('今日も一日頑張りましょう！');
<br>}
<br>// 夜のあいさつを出力する関数を定義する
<br>const sayGoodEvening = () => {
<br>console.log('こんばんは！');
<br>console.log('今日も一日お疲れ様でした。');
<br>}
<br>// 朝のあいさつを出力する関数を呼び出す
<br>sayGoodMorning();
<br>// 夜のあいさつを出力する関数を呼び出す
<br>sayGoodEvening();

6. 引数
<br>// 与えられた引数priceに送料を加算し、その値を出力する関数を定義する
<br>const calculateTotal = (price) => {
<br>console.log(price + 500 + '円');
<br>}
<br>// 関数を呼び出し、引数として購入金額を渡す
<br>calculateTotal(1200);
<br>// 与えられた引数priceと引数shippingFeeを加算し、その値を出力する関数を定義する
<br>const addTwoArguments = (price, shippingFee) => {
<br>console.log(price + shippingFee + '円');
<br>}
<br>// 関数を呼び起こし、引数として購入金額と送料を渡す
<br>addTwoArguments(1200, 500);

7. 戻り値
<br>// 与えられた引数numを2倍にし、その値を戻り値として返す関数を定義する
<br>const double = (num) => {
<br>return num * 2;
<br>}
<br>// 関数を戻り値を出力する
<br>console.log(double(30));



### 難しかったこと
- インクリメント演算子とデクリメント演算子についてよく理解できていない
- 戻り値


### 解決できなかったこと

