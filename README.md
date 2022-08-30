
<!DOCTYPE html>

<html>

<head>

    <meta charset="utf-8">

    <meta name="viewport" content="width=device-width, initial-scale=1">

    <title>Clock</title>
    <style type="text/css">
        * {

            margin: 0;

            padding: 0;

            box-sizing: border-box;

            font-family: 'Poppins', sans-serif;

        }

        body {

            display: flex;

            justify-content: center;

            align-items: center;

            min-height: 100vh;

            background: #2f363e;

        }

        .container {

            position: relative;

            background: #2f363e;

            /* min-height: 500px; */

            border-radius: 20px;

            border-top-left-radius: 225px;

            border-top-right-radius: 225px;

            box-shadow: 25px 25px 75px rgba(0, 0, 0, 0.75),

                10px 10px 70px rgba(0, 0, 0, 0.25),

                inset 5px 5px 10px rgba(0, 0, 0, 0.5),

                inset 5px 5px 20px rgba(255, 255, 255, 0.2),

                inset -5px -5px 15px rgba(0, 0, 0, 0.75);

            display: flex;

            justify-content: center;

            align-items: center;

            flex-direction: column;

        }

        .clock {

            position: relative;

            width: 450px;

            height: 450px;

            background: #2f363e;

            border-radius: 50%;

            box-shadow: 10px 50px 70px rgba(0, 0, 0, 0.25),

                inset 5px 5px 10px rgba(0, 0, 0, 0.5),

                inset 5px 5px 20px rgba(255, 255, 255, 0.2),

                inset -5px -5px 15px rgba(0, 0, 0, 0.75);

            display: flex;

            justify-content: center;

            align-items: center;

            margin-bottom: 30px;

        }

        .clock::before {

            content: '';

            position: absolute;

            width: 8px;

            height: 8px;

            background: #2f363e;

            border: 3px solid #fff;

            border-radius: 50%;

            z-index: 100000;

        }

        .clock span {

            position: absolute;

            inset: 20px;

            color: #fff;

            text-align: center;

            transform: rotate(calc(30deg * var(--i)));

            /* 360 / 12 = 30deg */

        }

        .clock span b {

            font-size: 2rem;

            opacity: 0.25;

            font-weight: 600;

            display: inline-block;

            transform: rotate(calc(-30deg * var(--i)));



        }

        .circle {

            position: absolute;

            width: 300px;

            height: 300px;

            border: 2px solid rgba(0, 0, 0, 0.25);

            border-radius: 50%;

            display: flex;

            justify-content: center;

            align-items: flex-start;

            z-index: 10;

        }

        .circle i {

            position: absolute;

            width: 6px;

            height: 50%;

            background: var(--clr);

            opacity: 0.75;

            transform-origin: bottom;

            transform: scaleY(0.5);

        }

        .circle:nth-child(1) i {

            width: 2px;

        }



        .circle:nth-child(2) i {

            width: 6px;

        }





        .circle2 {

            width: 240px;

            height: 240px;

            z-index: 9;

        }

        .circle3 {

            width: 180px;

            height: 180px;

            z-index: 8;

        }

        .circle::before {

            content: '';

            position: absolute;

            top: -8.5px;

            width: 15px;

            height: 15px;

            border-radius: 50%;

            background: var(--clr);

            box-shadow: 0 0 20px var(--clr),

                0 0 60px var(--clr);

        }

        /* Digital clock style  */

        #time {

            margin-bottom: 40px;

            display: flex;

            padding: 10px 20px;

            font-size: 2rem;

            font-weight: 600;

            border: 2px solid rgba(0, 0, 0, 0.5);

            border-radius: 40px;

            box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.5),

                inset 5px 5px 20px rgba(255, 255, 255, 0.2),

                inset -5px -5px 15px rgba(0, 0, 0, 0.75);

        }

        #time div {

            position: relative;

            width: 60px;

            text-align: center;

            font-weight: 500;

            color: var(--clr);

        }

        #time div:nth-child(1)::after,

        #time div:nth-child(2)::after {

            content: ':';

            position: absolute;

            right: -4px;

        }

        #time div:last-child {

            font-size: 0.5em;

            display: flex;

            justify-content: center;

            align-items: center;

            color: #fff;

        }

        #time div:nth-child(2)::after {

            animation: animate 1s steps(1) infinite;

        }

        @keyframes animate {
            0% {

                opacity: 1;

            }

            50% {

                opacity: 0;

            }

        }
    </style>
</head>

<body>



    <div class="container">

        <div class="clock">

            <div class="circle" id="sc" style="--clr:#04fc43;"><i></i></div>

            <div class="circle circle2" id="mn" style="--clr:#fee800;"><i></i></div>

            <div class="circle circle3" id="hr" style="--clr:#ff2972;"><i></i></div>

            <span style="--i:1;"><b>1</b></span>

            <span style="--i:2;"><b>2</b></span>

            <span style="--i:3;"><b>3</b></span>

            <span style="--i:4;"><b>4</b></span>

            <span style="--i:5;"><b>5</b></span>

            <span style="--i:6;"><b>6</b></span>

            <span style="--i:7;"><b>7</b></span>

            <span style="--i:8;"><b>8</b></span>

            <span style="--i:9;"><b>9</b></span>

            <span style="--i:10;"><b>10</b></span>

            <span style="--i:11;"><b>11</b></span>

            <span style="--i:12;"><b>12</b></span>

        </div>



        <!-- digital clock -->

        <div id="time">

            <div id="hours" style="--clr:#ff2972;">00</div>

            <div id="minutes" style="--clr:#fee800;">00</div>

            <div id="seconds" style="--clr:#04fc43;">00</div>

            <div id="ampm">PM</div>

        </div>

    </div>

    <script type="text/javascript">

        let hr = document.querySelector('#hr')

        let mn = document.querySelector('#mn')

        let sc = document.querySelector('#sc')



        setInterval(() => {

            let day = new Date();

            let hh = day.getHours() * 30;

            let mm = day.getMinutes() * 6;

            let ss = day.getSeconds() * 6;



            hr.style.transform = `rotateZ(${hh + (mm / 12)}deg)`;

            mn.style.transform = `rotateZ(${mm}deg)`;

            sc.style.transform = `rotateZ(${ss}deg)`;



            //Digital clock

            let hours = document.getElementById('hours');

            let minutes = document.getElementById('minutes');

            let seconds = document.getElementById('seconds');



            let h = new Date().getHours();

            let m = new Date().getMinutes();

            let s = new Date().getSeconds();



            let am = h >= 12 ? "PM" : "AM";



            // convert 24hr clock to 12hr clock

            if (h > 12) {

                h = h - 12;

            }



            // add zero before single digit number

            h = (h < 10) ? "0" + h : h

            m = (m < 10) ? "0" + m : m

            s = (s < 10) ? "0" + s : s





            hours.innerHTML = h;

            minutes.innerHTML = m;

            seconds.innerHTML = s;

            ampm.innerHTML = am;

        })



    </script>
<!-- Code injected by live-server -->
<script type="text/javascript">
	// <![CDATA[  <-- For SVG support
	if ('WebSocket' in window) {
		(function () {
			function refreshCSS() {
				var sheets = [].slice.call(document.getElementsByTagName("link"));
				var head = document.getElementsByTagName("head")[0];
				for (var i = 0; i < sheets.length; ++i) {
					var elem = sheets[i];
					var parent = elem.parentElement || head;
					parent.removeChild(elem);
					var rel = elem.rel;
					if (elem.href && typeof rel != "string" || rel.length == 0 || rel.toLowerCase() == "stylesheet") {
						var url = elem.href.replace(/(&|\?)_cacheOverride=\d+/, '');
						elem.href = url + (url.indexOf('?') >= 0 ? '&' : '?') + '_cacheOverride=' + (new Date().valueOf());
					}
					parent.appendChild(elem);
				}
			}
			var protocol = window.location.protocol === 'http:' ? 'ws://' : 'wss://';
			var address = protocol + window.location.host + window.location.pathname + '/ws';
			var socket = new WebSocket(address);
			socket.onmessage = function (msg) {
				if (msg.data == 'reload') window.location.reload();
				else if (msg.data == 'refreshcss') refreshCSS();
			};
			if (sessionStorage && !sessionStorage.getItem('IsThisFirstTime_Log_From_LiveServer')) {
				console.log('Live reload enabled.');
				sessionStorage.setItem('IsThisFirstTime_Log_From_LiveServer', true);
			}
		})();
	}
	else {
		console.error('Upgrade your browser. This Browser is NOT supported WebSocket for Live-Reloading.');
	}
	// ]]>
</script></body>

</html>
