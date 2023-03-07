# cubo-3d 

<!DOCTYPE html>
<html>
    <head>
      <meta charset="UTF-8">
            <title>Css Cubes</title>
              <link rel="stylesheet" href="style.css">    
                </head>
                  <body>
                    <div class="container">
                      <div class="cube">
                        <div style="--x:-1;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                        </div>
                       <div style="--x:0;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                       </div>
                       <div style="--x:1;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                       </div>
                    </div>  
                    
                    <div class="cube">
                       <div style="--x:-1;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                       </div>
                       <div style="--x:0;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                       </div>
                       <div style="--x:1;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                       </div>
                    </div>
                       <div class="cube">
                       <div style="--x:-1;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                       </div>
                       <div style="--x:0;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                       </div>
                       <div style="--x:1;--y:0;">
                          <span style="--i:3;"></span>
                          <span style="--i:2;"></span>
                          <span style="--i:1;"></span>
                      </div>
                  </div>
                </body>
              </html>
              
              CSS
              
              * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}


body {
    margin: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    /* background: #25335b; */
    background-image: url(cuboo.jpg);
    /* filter : blur(0px); desenfoque */

}

.container {
    position: relative;
    top: -80px;
    transform: skewY(-20deg);
    animation: animate 5s linear infinite;
}

/* Hace que anime con colores la funcion de arriba con la de abajo */

@keyframes animate {
    0% {
        filter: hue-rotate(0deg)
    }
    100% {
        filter: hue-rotate(360deg)
    }
}

/*   transform: skewY(-20deg); gira en forma 3d el cubo */
.container .cube {
    position: relative;
    z-index: 2;

}

.container .cube:nth-child(2) {
    z-index: 1;
    translate: -60px -60px;
}

.container .cube:nth-child(3) {
    z-index: 3;
    translate: 60px 60px;
}

.container .cube div {
    position: absolute;
    display: flex;
    flex-direction: column;
    gap: 30px;
    translate: calc(-70px * var(--x)) calc(-60px * var(--y));
}

.container .cube div span {
    position: relative;
    display: inline-block;
    width: 50px;
    height: 50px;
    background: #dcdcdc;
    z-index: calc(1 * var(--i));
    transition: 1.5s;
}

.container .cube div span:hover{
    transition: 0s;
    background: #ef4149;
    filter: drop-shadow(0 0 30px #ef4149);
}

.container .cube div span::before{
    content: "";
    position: absolute;
    left: -40px;
    width: 40px;
    height: 100%;
    background: #fff;
    transform-origin: right;
    transform: skewY(45deg);
}

.container .cube div span:hover::before{
    transition: 0s;
    background: #f75d64;
}

.container .cube div span::after{
    content: "";
    position: absolute;
    top: -40px;
    left: 0;
    width: 100%;
    height: 40px;
    background: #f2f2f2;
    transform-origin: bottom;
    transform: skewx(45deg);
}

.container .cube div span:hover::after{
    transition: 0s;
    background: #f14e55;
}




/* #dcdcdc */
