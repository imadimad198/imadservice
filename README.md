<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>الخدمات العامة المغربية</title>
  <style>
    body { font-family: sans-serif; background: #f5f5f5; margin: 0; padding: 0; }
    header { background: #0a8a24; color: white; padding: 20px; text-align: center; border-bottom: 6px solid #c40000; display:flex; justify-content:center; align-items:center; gap:10px; }
    header img { width:45px; }
    .welcome { text-align:center; padding:40px 20px; background:white; margin:20px; border-radius:15px; box-shadow:0 2px 6px rgba(0,0,0,0.15); }
    .welcome button { background:#0a8a24; color:white; padding:12px 25px; border:none; border-radius:8px; cursor:pointer; border-bottom:4px solid #c40000; font-size:18px; }
    .container { padding: 20px; display:none; }
    .card { background: white; padding: 20px; margin-bottom: 15px; border-radius: 12px; cursor: pointer; box-shadow: 0px 3px 6px rgba(0,0,0,0.2); border-right: 6px solid #0a8a24; border-left: 6px solid #c40000; transition:0.3s; }
    .card:hover { transform:scale(1.03); }
    .hidden { display: none; }
    .upload-box { margin: 10px 0; }
    button { background:#0a8a24; color:white; padding:10px 15px; border:none; border-radius:5px; cursor:pointer; border-bottom:4px solid #c40000; }
    footer { background:#c40000; color:white; text-align:center; padding:15px; margin-top:30px; border-top:6px solid #0a8a24; }
    footer a { color:white; font-weight:bold; text-decoration:none; }
  </style>
</head>
<body>

  <header>
    <img src="https://upload.wikimedia.org/wikipedia/commons/9/92/Flag_of_Morocco.svg" alt="Morocco">
    <h2>الخدمات العامة المغربية</h2>
  </header>

  <div class="welcome" id="welcomePage">
    <h2>مرحباً بك في منصة الخدمات</h2>
    <p>اختر خدمات البطاقة الوطنية و CNSS بكل سهولة</p>
    <button onclick="enterSite()">الدخول إلى الخدمات</button>
  </div>

  <div class="container" id="mainContent">
    <div class="card" onclick="showService('cin')">حجز موعد البطاقة الوطنية</div>
    <div class="card" onclick="showService('cnss')">حجز موعد CNSS</div>
    <div class="card" onclick="openWhatsapp()">خدمة الزبناء عبر واتساب</div>

    <div id="cin" class="hidden">
      <h3>حجز موعد البطاقة الوطنية</h3>
      <p>الوثائق المطلوبة:</p>
      <ul>
        <li>عقد الازدياد</li>
        <li>صورتان شخصيتان</li>
        <li>نسخة من بطاقة التعريف القديمة (إن وجدت)</li>
      </ul>
      <div class="upload-box">
        <label>تحميل الوثائق:</label>
        <input type="file" multiple>
      </div>
      <button onclick="submitForm('حجز موعد البطاقة الوطنية')">إرسال الطلب</button>
    </div>

    <div id="cnss" class="hidden">
      <h3>حجز موعد CNSS</h3>
      <p>الوثائق المطلوبة:</p>
      <ul>
        <li>نسخة من CIN</li>
        <li>شهادة السكنى</li>
      </ul>
      <div class="upload-box">
        <label>تحميل الوثائق:</label>
        <input type="file" multiple>
      </div>
      <button onclick="submitForm('حجز موعد CNSS')">إرسال الطلب</button>
    </div>

  </div>

  <footer>
    <p>© 2025 جميع الحقوق محفوظة لمنصة الخدمات المغربية</p>
    <p><a href="https://wa.me/0630881892">التواصل عبر واتساب</a></p>
  </footer>

  <script>
    function enterSite(){
      document.getElementById('welcomePage').style.display='none';
      document.getElementById('mainContent').style.display='block';
    }

    function showService(serviceId) {
      document.querySelectorAll('#cin, #cnss').forEach(div => div.classList.add('hidden'));
      document.getElementById(serviceId).classList.remove('hidden');
    }

    function submitForm(service) {
      alert('تم إرسال طلب خدمة: ' + service);
    }

    function openWhatsapp(){
      window.location.href = 'https://wa.me/0630881892';
    }
  </script>
</body>
</html>
