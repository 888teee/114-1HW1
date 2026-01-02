# 第2次隨堂題目-隨堂-QZ2
>
>學號：111111216
><br />
>姓名：唐滋翊
><br />
>作業撰寫時間：180 (mins，包含程式撰寫時間)
><br />
>最後撰寫文件日期：2023/09/22
>


```


1. 請撰寫Topic 1的P. 16，並1 寫程式後印出結果，該程式名為p16.js，與2 承1程式碼中的 Line3下中斷點，並印出此時變數age裡面的值為多少觀察。

Ans:

P16說明:
主要透過簡單的變數宣告與輸出，來練習 VS Code 的偵錯功能，程式執行時是由上而下同步執行的，在第三行下中斷點是為了在結果印出前先攔截程式。透過偵錯面板可以看到，此時變數已經被賦值為 18，這讓我們能直接觀察記憶體中的執行階段狀態。

var userName = "heimtengyun";
var age = 18;
console.log(userName, age);


2. 請撰寫Topic 1的P. 19，並1 寫程式後印出結果，該程式名為p19.js，與2 請同樣印出p. 20的三種結果，並說明為何可以造成該種原因

Ans:

P19說明:
利用 Node.js 內建的 http 模組來練習架設一個簡單的 Web 伺服器。程式的核心在於處理請求與回應，透過 request.url 抓取使用者在瀏覽器輸入的網址，並用 switch 邏輯做路由分發。當網址匹配到 / 或 /login 時，伺服器會回傳對應的中文內容；若路徑不匹配則進入 default 顯示「非法闖入」。

const http = require('http');

const server = http.createServer(function (request, response) {
    const url = request.url; 
    console.log(url);
    
    var answer = ''; 
    switch (url) {
        case '/':
            answer = '歡迎訪問首頁';
            break;
        case '/login':
            answer = '歡迎來到登錄頁';
            break;
        default:
            answer = '非法闖入';
            break;
    }
    
    response.setHeader('Content-Type', 'text/plain;charset=utf-8');
    response.end(answer);
});

server.listen('8888', function () {
    console.log("伺服器啟動成功，訪問：http://127.0.0.1:8888");
});


```

