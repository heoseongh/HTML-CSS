# CODE
>HTML
```HTML
<body>
    <div class="container">
        <ul class="underline-hover">
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Service</a></li>
            <li><a href="#">Portfolio</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
    </div>
</body>
```
>CSS
```HTML
<style>
    @import url(https://fonts.googleapis.com/css?family=Quicksand);

    body {
        font-family: 'Quicksand';
        margin: 0;
        padding: 0;
        font-size: 14px;
        background-color: #f4f4f4;
    }

    .container {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        /* transform 과 position 차이??? */
    }

    .underline-hover {
        /* 아래 애들을 쓰려면 .underline-hover에 li선택자 까지 붙혀줘야함. */
        /*display: inline-block;*/
        /*float: left;*/
        display: flex;
        list-style: none;
        width: 600px;
        background-color: white;
        padding: 50px;
        margin: 0;
        border-radius: 10px;
        box-shadow: 0 0 30px rgba(0, 0, 0, 0.1);
    }

    .underline-hover li {
        margin: 0 30px;
    }

    .underline-hover li a {
        color: #222;
        text-decoration: none;
        position: relative;
    }

    /* 마우스 올리기 전 */
    .underline-hover li a:before {
        content: '';
        background-color: dodgerblue;
        width: 0;
        height: 2px;
        /* positon : absolute로 하면 가장 가까운 부모에게 붙어버린다. */
        /* 부모 position : relative로 해야함. */
        position: absolute;
        left: 50%;
        /* 중앙부터 밑줄이 나타나게 하기 위해서 */
        /* X축을 -50% 당긴다*/
        transform: translateX(-50%);
        bottom: -10px;
        /* before라는 가상 클래스가 변하는 것이기 때문에 */
        transition: 0.2s;
    }

    /* 마우스 올라간 후 before를 어떻게 바꾸는지 */
    .underline-hover li a:hover:before {
        width: 100%;
        /* 마우스를 올리면 밑줄이 사라지게 0으로 설정 */
    }

</style>
```