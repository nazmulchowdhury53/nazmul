<!DOCTYPE html>
<html lang="en">
<head>
    <style>
        *{
            margin:  0;
            padding: 0;
            font-family: 'Poppins',sans-serif;
            box-sizing: border-box;
        }
        .na{
            width: 100%;
            min-height: 100vh;
            background: yellowgreen;
            color: aliceblue;
            position: relative;
        }
       .container{
        width: 800px;
        height: 180px;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
       }
       .clock{
        width: 100%;
        height: 100%;
        background: rgba(141, 105, 60, 0.11);
        border-radius: 10px;
        display: flex;
        align-items: center;
        justify-content: center;
        backdrop-filter: blur(40px);
       }
       .container::before{
        content: '';
        width: 180px;
        height: 180px;
        background: red yellow;
        border-radius: 5px;
        position: absolute;
        left: -50px;
        top: -50px;
        z-index: -1;

       }
       .container::after{
        content: '';
        width: 180px;
        height: 180px;
        background: rgb(255, 0, 132) rgb(65, 123, 145);
        border-radius: 50%;
        position: absolute;
        right: -30px;
        bottom: -50px;
        z-index: -1;

       }
       .clock span{
        font-size: 80px;
        width: 110px;
        display: inline-block;
        text-align: center;
        position: relative;
    }
    .clock span::after{
        font-size: 16px;
        position: absolute;
        bottom: -5px;
        left: 50%;
        transform: translateX(-50%);
    }
    #hrs::after{
        content: 'HOURS';
    }
    #min::after{
        content: 'minites';
    }
    #sec::after{
        content: 'seconds';
    }
    </style>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>clock</title>
</head>
<body>
  <div class="na">
    <div class="container">
        <div class="clock">
            <span id="hrs">00</span>
            <span>:</span>
            <span id="min">00</span >
            <span>:</span>
            <span id="sec">00</span>
        </div>
    </div>
  </div>
  <script>
    let hrs = document.getElementById("hrs");
    let min = document.getElementById("min");
    let sec = document.getElementById("sec");
    setInterval(()=>{
        let currntTime = new Date();
         hrs.innerHTML= currntTime.getHours();
         min.innerHTML= currntTime.getMinutes();
         sec.innerHTML= currntTime.getSeconds();  
    },1000)
    
  </script>  
</body>
</html>
