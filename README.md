# denntaku
電卓（分数以外）
<!DOCTYPE html>
<meta charset="UTF-8">
<html><body>
    <style>
    button
    {
        width: 50px;
        height: 50px;
    }
    </style>
    <div>Hello WebCalc!</div>
    <input style="font-size: 28px; text-align: right;" /><br />
    <script>
    function update( _v ) // input tag を更新する関数
    {
        document.querySelector( 'input' ).value = _v
    }

    function append( _v ) // 数字ボタンが押されたので数字を後ろに追加する
    {
        document.querySelector( 'input' ).value += _v
    }

    function calc() // 「＝」ボタンが押されたので計算する
    {
        const v = document.querySelector( 'input' ).value
        try {
            const f = new Function( 'return ' + v )
            update( f().toString() )
        } catch( _error ) {
            update( _error ) // 計算に失敗した場合は、そのエラーの内容を表示する
        }
    }
    </script>
    <button onclick="append( '1' )" >1</button>
    <button onclick="append( '2' )" >2</button>
    <button onclick="append( '3' )" >3</button>
    <button onclick="append( '4' )" >4</button>
    <button onclick="append( '5' )" >5</button><br />
    <button onclick="append( '6' )" >6</button>
    <button onclick="append( '7' )" >7</button>
    <button onclick="append( '8' )" >8</button>
    <button onclick="append( '9' )" >9</button>
    <button onclick="append( '0' )" >0</button><br />
    <button onclick="append( '.' )" >.</button>
    <button onclick="append( '+' )" >+</button>
    <button onclick="append( '-' )" >-</button>
    <button onclick="append( '*' )" >*</button>
    <button onclick="append( '/' )" >/</button><br />
    <button onclick="append( '**' )" >^</button>
    <button onclick="append( '**0.5' )" >√</button>

    <button onclick="calc()" style="width:105px;">=</button>

    <button onclick="update( '' ) " >CLR</button>
</body></html>
