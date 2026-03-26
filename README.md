<html>
<head>
  <meta charset="UTF-8">
  <title>Redirecting...</title>
  <script>
    var url = "https://script.google.com/macros/s/AKfycbzJ55pA_zj5FRUNe7zKP38SH_SyPI9BkV2LBCxpKUJvsdDndrxv0Wy4fxYUqIwJ6Sv0ZQ/exec";

    function openApp() {
      var ua = navigator.userAgent || "";

      // Android → Chrome
      if (/android/i.test(ua)) {
        window.location.href = "intent://" + url.replace(/^https?:\/\//, '') + "#Intent;scheme=https;package=com.android.chrome;end";
        return;
      }

      // iOS → Safari
      if (/iPhone|iPad|iPod/i.test(ua)) {
        window.location.href = url;
        return;
      }

      // Browser ปกติ
      window.location.replace(url);
    }

    window.onload = function() {

      // แสดงปุ่มก่อน (กัน blank)
      document.getElementById("btn").style.display = "inline-block";

      // delay นิดนึงให้เห็น UI
      setTimeout(function() {
        openApp();
      }, 300);
    };
  </script>
</head>

<body style="font-family:sans-serif;text-align:center;padding:40px">
  <h2>กำลังเปิดเว็บไซต์...</h2>
  <p>หากไม่เด้งอัตโนมัติ กรุณากดปุ่มด้านล่าง</p>

  <button id="btn" onclick="openApp()" 
     style="display:none;padding:12px 20px;background:#16a34a;color:#fff;border:none;border-radius:8px;cursor:pointer">
     🔗 เปิดเว็บไซต์
  </button>
</body>
</html>
