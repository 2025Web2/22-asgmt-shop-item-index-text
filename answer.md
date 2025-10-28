---
sort: 3
---

# 課題の解答

以下は、課題の解答例です。
課題に合格されなかった方は、こちらのコードを参考にしてください。

**resources/views/item/index.blade.php(ジャンル別商品一覧画面)**

```php
<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet" href="{{ asset('css/minishop.css')}}">
<title>ショッピングサイト</title>
</head>
<body>
<h3>ジャンル別商品一覧</h3>
    <table>
        <tr>
            <th>&nbsp;</th>
            <th>商品名</th>
            <th>メーカー・著者<br>アーティスト</th>
            <th>価格</th>
            <th>詳細</th>
        </tr>
    @foreach( $items  as  $item )
        <tr>
        <td class="td_mini_img"><img class="mini_img" src="{{ asset('images/'.$item->image )}}"></td>
        <td class="td_item_name"> {{  $item->name }} </td>
        <td class="td_item_maker"> {{  $item->maker }}  </td>
        <td class="td_right">&yen; {{  number_format( $item->price) }} </td>
        <!-- リンク先についてはここでは一旦空欄とします -->
        <td><a href="">詳細</a></td>
        </tr>
    @endforeach
    </table>
    <br>
    <a href="{{ route('index') }}">ジャンル選択に戻る</a>
</body>
</html>
```
