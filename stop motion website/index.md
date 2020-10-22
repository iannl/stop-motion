<!DOCTYPE html>
<html>

<head>
    <link rel="shortcut icon" href="title.gif" />
    <title>Stop-motion</title>
</head>

<body id="body"></body>
<style>
    img {
        filter: contrast(100%);
        /*filter: blur(300%);*/
        filter: sepia();
    }
    
    button {
        height: 100px;
        width: 100px;
        position: fixed;
        margin-top: 100px;
    }
</style>


<script>
    var elem = document.documentElement;
    var size = 0
    var max_size = 150
    var scan = 0
    var images = ["title.gif", "Good_Test.gif", "My_Stop_Motion_Movie.gif", "great_gif_image.gif", "Animal_Chase.gif", "Animal_Chase_230-Better.gif", "Animal_Chase_300-Better.gif"];
    var full_yet = "no"

    function test() {
        size++
        var length = images.length
        document.getElementById("body").innerHTML = '<button style="height: 100px; width: ' + length * 153 + 'px; position: fixed; margin-top: 100px;" onclick="openFullscreen();">Go Fullscreen Mode</button> <img src=' + images[0] + ' width="' + size + 'px"> <img src=' + images[1] + ' width="' + size + 'px">  <img src=' + images[2] + ' width="' + size + 'px">  <img src=' + images[3] + ' width="' + size + 'px">  <img src=' + images[4] + ' width="' + size + 'px"> <img src=' + images[5] + ' width="' + size + 'px"> <img src=' + images[6] + ' width="' + size + 'px">'

    }

    function random_no() {
        var ran = Math.random();
        //jQuery('#random_no_container').html(ran);
    }

    window.setInterval(function() {


        if (scan < max_size) {
            if (full_yet = "yes") {
                scan++
                random_no();
                test()
                openFullscreen()
            }
        }
    }, 10);

    function openFullscreen() {
        full_yet = "yes"
        if (elem.requestFullscreen) {
            elem.requestFullscreen();
        } else if (elem.mozRequestFullScreen) { /* Firefox */
            elem.mozRequestFullScreen();
        } else if (elem.webkitRequestFullscreen) { /* Chrome, Safari & Opera */
            elem.webkitRequestFullscreen();
        } else if (elem.msRequestFullscreen) { /* IE/Edge */
            elem = window.top.document.body; //To break out of frame in IE
            elem.msRequestFullscreen();
        }
    }
</script>
</body>

</html>
