<!DOCTYPE html>
<html>

<head>
    <title>Happy Birthday, Ronith!</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f7f7f7;
            overflow: hidden;
        }

        h1 {
            color: #333;
        }

        p {
            color: #666;
        }

        .birthday-wish {
            margin-top: 50px;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        .video-background {
            position: fixed;
            top: 0;
            right: 0;
            bottom: 0;
            left: 0;
            z-index: -1;
            pointer-events: none;
        }

        #video-frame {
            width: 100%;
            height: 100%;
        }
    </style>
</head>

<body>
    <div class="video-background">
        <iframe id="video-frame" src="https://www.youtube.com/watch?v=AwNqDqzx3js"
            frameborder="0" allowfullscreen></iframe>
    </div>

    <div class="birthday-wish">
        <h1>Happy Birthday, Ronith!</h1>
        <p>Wishing you a day filled with love, laughter, and joy.</p>
        <p>May this year be your best one yet!</p>
        <p>Enjoy your special day to the fullest!</p>
    </div>

    <script>
        // Adjust the iframe height to match the window height
        window.addEventListener('resize', function () {
            var videoFrame = document.getElementById('video-frame');
            videoFrame.style.height = window.innerHeight + 'px';
        });

        // Pause the video when the window is not visible
        document.addEventListener('visibilitychange', function () {
            var videoFrame = document.getElementById('video-frame');
            if (document.visibilityState === 'visible') {
                videoFrame.contentWindow.postMessage('{"event":"command","func":"playVideo","args":""}', '*');
            } else {
                videoFrame.contentWindow.postMessage('{"event":"command","func":"pauseVideo","args":""}', '*');
            }
        });
    </script>
</body>

</html>
