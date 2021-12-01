# weblink
stream_file = """
<div id='vidiv'>    
    
    <title>Download """ + str(file_name[:-4]) + """</title>
    <link rel="icon" href="https://i.imgur.com/SeYCR1M.jpg" type="image/gif" sizes="16x16"> 
    <link rel="stylesheet" href="https://cdn.fluidplayer.com/v2/current/fluidplayer.min.css" type="text/css"/>
    <script src="https://cdn.fluidplayer.com/v2/current/fluidplayer.min.js"></script>
    <video id="video-fully-responsive">
        <source src="/""" + str(file_id) + """/""" + str(file_name) + """" type="video/mp4"/>
    </video>
    <script type="text/javascript">
        var video = document.querySelector("video");
        var src = video.firstElementChild
        src.addEventListener('error', function(evt) {
            // video.addEventListener('play', function(evt) {
            //     document.getElementById('vidiv').style.display = 'none';
            // })
            document.getElementById('vidiv').style.display = 'none';
        });
        
        fluidPlayer(
            "video-fully-responsive",
            {
                layoutControls: {
                    title: """ + str(json.dumps(file_name[:-4])) + """,
                    playButtonShowing: true,
                    fillToContainer: true,
                    preload: false,
                    controlBar: {
                        autoHide: true,
                        autoHideTimeout: 3,
                        animated: true
                    },
                    playbackRateEnabled: true,
                    allowTheatre: true
                }
            }
        );
        
        
    </script>
    
</div>
"""
    else: 
        stream_file = ''

    htmltext = """
<!DOCTYPE html>
<head>
    <meta name="referrer" content="always" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Global site tag (gtag.js) - Google Analytics -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=UA-158041490-1"></script>
    <script>
        window.dataLayer = window.dataLayer || [];
        function gtag(){dataLayer.push(arguments);}
        gtag('js', new Date());
        gtag('config', 'UA-158041490-1');
    </script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <style>
        .container {
            text-align: center;
            margin: 0% auto;
        }
        
        @media (orientation: landscape) {
            .container {
                max-width: 750px;
            }
        }
        
        .main {
            /* border: 1px solid DodgerBlue;  */
            padding: 0px 2%;
        }
        
        h1 {
            margin-top: 5%;
            color: grey;
            width: fit-width;
            word-wrap: break-word;
            line-height: 20px;
        }
        
        .filename {
            color: DodgerBlue;
            font-size: calc(10px + 1.1vw);
            word-wrap: break-word;
            font-weight: bold;
        }
        
        #video-fully-responsive {
            width: 100%;
        }
        
        #vast_video_loading_video-fully-responsive {
            height: 0;
        }
        
        .btn {
            background-color: DodgerBlue;
            border: none;
            color: white;
            padding: 12px 30px;
            cursor: pointer;
            font-size: 20px;
            margin: 0% auto;
            margin-top: 20px;
            /* margin-bottom: 20px; */
            width: 100%;
        }
        
        .btn:hover {
            background-color: RoyalBlue;
        }
        
        .btnn {
            background-color: #f0ad4e;
            border: none;
            color: white;
            padding: 5px;
            cursor: pointer;
            font-size: 15px;
            margin: 0% auto;
            margin-top: 10px;
            margin-bottom: 20px;
            width: 20%;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="main">
            <p class="filename">""" + str(file_name) + """</p>
            """ + stream_file + """
            <a href="/""" + str(file_id) + """/""" + str(file_name) + """">
                <button class="btn"><i class="fa fa-download"></i> Download</button>
            </a>
            <a href="https://telegram.me/filestolink" target="_blank" style="text-decoration: none;">
                <button class="btnn">Join our channel</button>
            </a>
        </div>
    </div>
    <div class="ads" style="text-align: center;">
       
    </div>```
