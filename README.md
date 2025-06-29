<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>Video Wallpaper</title>
  <style>
    body { margin: 0; overflow: hidden; background: black; }
    video { width: 100vw; height: 100vh; object-fit: cover; }
  </style>
</head>
<body>
  <video id="video" autoplay muted></video>
  <script>
    // === 動画ファイル名一覧（同じフォルダにある動画） ===
    const videoList = ["ファイノン.mp4"]; // ←ここ書き換えて！
    let current = 0;

    const videoElement = document.getElementById("video");

    function playNext() {
      videoElement.src = videoList[current];
      videoElement.play();
      current = (current + 1) % videoList.length;
    }

    videoElement.addEventListener("ended", playNext);
    playNext();
  </script>
</body>
</html>
