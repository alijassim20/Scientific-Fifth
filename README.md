# Scientific-Fifth
نتائج الصف الخامس العلمي 
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>نتائج الطلاب - اعدادية التآخي للبنين</title>
<link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Cairo:wght@300;400;600;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --dark: #111111;
    --darker: #0d0d0d;
    --gold: #c9a84c;
    --gold-light: #e8c97a;
    --gold-dim: #8a6e2e;
    --white: #f5f0e8;
    --cream: #ede5d0;
    --gray: #888;
    --red: #c0392b;
    --green: #27ae60;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'Cairo', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Decorative background */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: 
      radial-gradient(ellipse at 20% 20%, rgba(201,168,76,0.06) 0%, transparent 50%),
      radial-gradient(ellipse at 80% 80%, rgba(201,168,76,0.04) 0%, transparent 50%);
    pointer-events: none;
    z-index: 0;
  }

  .container {
    position: relative;
    z-index: 1;
    max-width: 700px;
    margin: 0 auto;
    padding: 20px;
  }

  /* Header */
  .header {
    text-align: center;
    padding: 40px 20px 30px;
    border-bottom: 1px solid rgba(201,168,76,0.2);
    margin-bottom: 40px;
  }

  .header-ministry {
    font-size: 12px;
    color: var(--gold-dim);
    letter-spacing: 2px;
    margin-bottom: 6px;
  }

  .header-school {
    font-family: 'Amiri', serif;
    font-size: 28px;
    color: var(--gold);
    font-weight: 700;
    line-height: 1.4;
    margin-bottom: 4px;
  }

  .header-sub {
    font-size: 13px;
    color: var(--gray);
    margin-bottom: 2px;
  }

  .header-year {
    font-size: 13px;
    color: var(--gold-dim);
    font-weight: 600;
  }

  .gold-line {
    width: 80px;
    height: 2px;
    background: linear-gradient(90deg, transparent, var(--gold), transparent);
    margin: 16px auto;
  }

  /* Login Card */
  .login-card {
    background: var(--dark);
    border: 1px solid rgba(201,168,76,0.15);
    border-radius: 12px;
    padding: 40px;
    box-shadow: 0 20px 60px rgba(0,0,0,0.5);
  }

  .login-title {
    font-size: 18px;
    color: var(--gold);
    text-align: center;
    margin-bottom: 30px;
    font-weight: 700;
  }

  .form-group {
    margin-bottom: 20px;
  }

  .form-label {
    display: block;
    font-size: 13px;
    color: var(--gray);
    margin-bottom: 8px;
    font-weight: 600;
  }

  .form-input {
    width: 100%;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(201,168,76,0.2);
    border-radius: 8px;
    padding: 14px 16px;
    color: var(--white);
    font-family: 'Cairo', sans-serif;
    font-size: 15px;
    direction: ltr;
    text-align: center;
    letter-spacing: 3px;
    transition: border-color 0.3s, box-shadow 0.3s;
    outline: none;
  }

  .form-input:focus {
    border-color: var(--gold);
    box-shadow: 0 0 0 3px rgba(201,168,76,0.1);
  }

  .form-input::placeholder {
    color: rgba(255,255,255,0.2);
    letter-spacing: 1px;
  }

  .btn-login {
    width: 100%;
    background: linear-gradient(135deg, var(--gold-dim), var(--gold));
    border: none;
    border-radius: 8px;
    padding: 15px;
    color: var(--black);
    font-family: 'Cairo', sans-serif;
    font-size: 16px;
    font-weight: 700;
    cursor: pointer;
    transition: all 0.3s;
    margin-top: 8px;
  }

  .btn-login:hover {
    background: linear-gradient(135deg, var(--gold), var(--gold-light));
    transform: translateY(-1px);
    box-shadow: 0 8px 25px rgba(201,168,76,0.3);
  }

  .error-msg {
    color: #e74c3c;
    font-size: 13px;
    text-align: center;
    margin-top: 14px;
    display: none;
  }

  /* Results Page */
  .results-page {
    display: none;
  }

  .student-header {
    text-align: center;
    margin-bottom: 30px;
  }

  .student-name {
    font-family: 'Amiri', serif;
    font-size: 26px;
    color: var(--gold);
    margin-bottom: 6px;
  }

  .student-meta {
    font-size: 13px;
    color: var(--gray);
  }

  .results-table-wrap {
    background: var(--dark);
    border: 1px solid rgba(201,168,76,0.15);
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 20px;
  }

  table {
    width: 100%;
    border-collapse: collapse;
  }

  .table-header {
    background: var(--black);
    padding: 14px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 1px solid rgba(201,168,76,0.15);
  }

  .table-header-title {
    color: var(--gold);
    font-size: 14px;
    font-weight: 700;
  }

  thead tr {
    background: rgba(201,168,76,0.08);
  }

  thead th {
    padding: 12px 16px;
    color: var(--white);
    font-size: 13px;
    font-weight: 700;
    border-bottom: 1px solid rgba(201,168,76,0.1);
  }

  tbody tr {
    border-bottom: 1px solid rgba(255,255,255,0.04);
    transition: background 0.2s;
  }

  tbody tr:hover {
    background: rgba(201,168,76,0.04);
  }

  tbody tr:last-child {
    border-bottom: none;
  }

  td {
    padding: 13px 16px;
    font-size: 14px;
  }

  td:first-child {
    color: var(--white);
    font-weight: 600;
  }

  td:last-child {
    text-align: center;
    direction: ltr;
  }

  .score-high { color: #2ecc71; font-weight: 700; }
  .score-mid  { color: var(--gold); font-weight: 700; }
  .score-low  { color: #e74c3c; font-weight: 700; }

  .summary-card {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    margin-bottom: 20px;
  }

  .summary-item {
    background: var(--dark);
    border: 1px solid rgba(201,168,76,0.12);
    border-radius: 10px;
    padding: 18px;
    text-align: center;
  }

  .summary-label {
    font-size: 11px;
    color: var(--gray);
    margin-bottom: 6px;
    display: block;
  }

  .summary-value {
    font-size: 22px;
    font-weight: 700;
    color: var(--gold);
  }

  .btn-back {
    width: 100%;
    background: transparent;
    border: 1px solid rgba(201,168,76,0.3);
    border-radius: 8px;
    padding: 12px;
    color: var(--gold-dim);
    font-family: 'Cairo', sans-serif;
    font-size: 14px;
    cursor: pointer;
    transition: all 0.3s;
    margin-bottom: 30px;
  }

  .btn-back:hover {
    border-color: var(--gold);
    color: var(--gold);
  }

  /* Admin Panel */
  .admin-panel {
    display: none;
  }

  .admin-title {
    font-size: 20px;
    color: var(--gold);
    margin-bottom: 24px;
    font-weight: 700;
    text-align: center;
  }

  .search-wrap {
    background: var(--dark);
    border: 1px solid rgba(201,168,76,0.15);
    border-radius: 12px;
    padding: 30px;
    margin-bottom: 24px;
  }

  .search-input {
    width: 100%;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(201,168,76,0.2);
    border-radius: 8px;
    padding: 14px 16px;
    color: var(--white);
    font-family: 'Cairo', sans-serif;
    font-size: 14px;
    outline: none;
    transition: border-color 0.3s;
    margin-bottom: 16px;
  }

  .search-input:focus {
    border-color: var(--gold);
  }

  .search-results {
    max-height: 400px;
    overflow-y: auto;
  }

  .search-item {
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(201,168,76,0.08);
    border-radius: 8px;
    padding: 14px 16px;
    margin-bottom: 8px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    transition: all 0.2s;
  }

  .search-item:hover {
    background: rgba(201,168,76,0.06);
    border-color: rgba(201,168,76,0.2);
  }

  .search-item-name {
    font-size: 14px;
    color: var(--white);
    font-weight: 600;
  }

  .search-item-code {
    font-size: 13px;
    color: var(--gold);
    direction: ltr;
    font-weight: 700;
    background: rgba(201,168,76,0.1);
    padding: 4px 10px;
    border-radius: 20px;
  }

  .footer {
    text-align: center;
    padding: 30px 0;
    color: rgba(255,255,255,0.15);
    font-size: 11px;
    border-top: 1px solid rgba(255,255,255,0.05);
    margin-top: 20px;
  }

  .footer span { color: var(--gold-dim); }

  /* Scrollbar */
  ::-webkit-scrollbar { width: 4px; }
  ::-webkit-scrollbar-track { background: var(--darker); }
  ::-webkit-scrollbar-thumb { background: var(--gold-dim); border-radius: 2px; }

  @media (max-width: 480px) {
    .login-card { padding: 24px; }
    .summary-card { grid-template-columns: 1fr 1fr; }
    .header-school { font-size: 22px; }
    td { padding: 10px 12px; font-size: 13px; }
  }
</style>
</head>
<body>
<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div class="header-ministry">جمهورية العراق — وزارة التربية</div>
    <div class="header-ministry">المديرية العامة لتربية صالح الدين — قسم تربية بيجي</div>
    <div class="gold-line"></div>
    <div class="header-school">اعدادية التآخي للبنين</div>
    <div class="header-sub">سجل درجات الطلاب</div>
    <div class="header-year">للعام الدراسي (2025 – 2026)</div>
    <div class="gold-line"></div>
    <div class="header-sub">المدير: خالد رسول فهد</div>
  </div>

  <!-- LOGIN PAGE -->
  <div id="loginPage">
    <div class="login-card">
      <div class="login-title">🔐 أدخل الرقم السري لعرض النتيجة</div>
      <div class="form-group">
        <label class="form-label">الرقم السري</label>
        <input type="text" id="codeInput" class="form-input" autocomplete="off" />
      </div>
      <button class="btn-login" onclick="doLogin()">دخول</button>
      <div class="error-msg" id="errorMsg">❌ الرقم السري غير صحيح</div>
    </div>
  </div>

  <!-- RESULTS PAGE -->
  <div id="resultsPage" class="results-page">
    <button class="btn-back" onclick="goBack()">← رجوع</button>
    <div class="student-header">
      <div class="student-name" id="resName"></div>
      <div class="student-meta" id="resMeta"></div>
    </div>
    <div class="summary-card">
      <div class="summary-item">
        <span class="summary-label">المجموع الكلي</span>
        <div class="summary-value" id="resTotal"></div>
      </div>
      <div class="summary-item">
        <span class="summary-label">المعدل العام</span>
        <div class="summary-value" id="resAvg"></div>
      </div>
    </div>
    <div class="results-table-wrap">
      <div class="table-header">
        <span class="table-header-title">درجات الفصل الأول</span>
      </div>
      <table>
        <thead><tr><th>المادة</th><th>الدرجة</th></tr></thead>
        <tbody id="resTableBody"></tbody>
      </table>
    </div>
  </div>

  <!-- ADMIN PANEL -->
  <div id="adminPanel" class="admin-panel">
    <button class="btn-back" onclick="goBack()">← رجوع</button>
    <div class="admin-title">🛡️ لوحة المدير — خالد رسول فهد</div>
    <div class="search-wrap">
      <input type="text" class="search-input" id="adminSearch" placeholder="ابحث باسم الطالب..." oninput="searchStudents()" />
      <div class="search-results" id="searchResults"></div>
    </div>
  </div>

  <div class="footer">
    اعدادية التآخي للبنين &nbsp;|&nbsp; <span>قسم تربية بيجي</span> &nbsp;|&nbsp; 2025–2026
  </div>
</div>

<script>
const SUBJECTS = [
  'التربية الإسلامية','اللغة العربية','اللغة الإنكليزية',
  'الرياضيات','الفيزياء','الكيمياء','علم الأحياء',
  'التربية الرياضية','التربية الفنية'
];

// Students data: [name, code, [scores...]]
const STUDENTS = [
  ['أبو بكر ندا عباس',         'SL2001', [50,45,25,26,34,38,33,60,60]],
  ['احمد اياد حمود',           'SL2002', [100,93,80,84,90,86,94,100,100]],
  ['احمد رياض حميد',           'SL2003', [100,95,55,50,90,76,61,70,70]],
  ['احمد علي احمد',            'SL2004', [100,86,75,50,95,63,74,70,70]],
  ['احمد ماهر حميد نجرس',      'SL2005', [98,56,65,32,56,57,51,60,60]],
  ['احمد نعيم كردي',           'SL2006', [98,72,50,32,60,60,58,60,60]],
  ['إسحاق هشام صباح جمعة',     'SL2007', [100,53,60,32,50,34,43,60,60]],
  ['اسد محمود عوض',            'SL2008', [98,75,65,38,60,56,53,60,60]],
  ['بلال نمير محمد مطلك',      'SL2009', [95,56,60,28,70,41,60,60,60]],
  ['حارث علي محمد خلف',        'SL2010', [100,97,97,64,95,80,91,100,100]],
  ['حذيفة عدنان نايف',         'SL2011', [77,45,52,36,37,50,50,60,60]],
  ['حسين احمد حسين',           'SL2012', [80,63,60,40,80,51,52,60,60]],
  ['خالد حسن شرقي',            'SL2013', [100,90,75,56,75,66,61,60,60]],
  ['خالد فاروق دحام',          'SL2014', [100,80,90,53,90,86,85,100,100]],
  ['ريقان ثامر جدوع حلو',      'SL2015', [100,85,55,52,75,81,81,80,80]],
  ['شجاع عامر ثابت',           'SL2016', [73,66,60,26,30,43,54,60,60]],
  ['ضياء احسان علي',           'SL2017', [87,60,30,28,39,38,41,60,60]],
  ['عبد الحق نجم عبد الله',    'SL2018', [95,60,60,33,80,52,53,60,60]],
  ['عبد الرحمن طالل محمود',    'SL2019', [71,55,50,29,34,35,50,60,60]],
  ['عبد الرحمن ياسر احميد',    'SL2020', [100,63,40,53,35,54,54,60,60]],
  ['عبد الله عثمان عطية',      'SL2021', [100,85,95,35,90,59,73,100,100]],
  ['عبد الله نزهان دخيل',      'SL2022', [85,66,40,35,36,39,57,60,60]],
  ['علي حسين خلف',             'SL2023', [90,76,55,42,50,40,44,60,60]],
  ['عمر احمد عبد الله',        'SL2024', [95,100,65,39,56,43,50,60,60]],
  ['عمر ذاكر مصلح احميد',      'SL2025', [88,53,60,45,56,35,30,60,60]],
  ['عمر قحطان فرحان',          'SL2026', [100,60,60,28,50,41,50,60,60]],
  ['ليث علي احميد طه',         'SL2027', [100,68,72,63,80,59,53,80,80]],
  ['محمد حسن موسى',            'SL2028', [67,53,25,28,95,33,51,60,60]],
  ['محمد حسين خلف',            'SL2029', [100,83,85,50,80,72,61,80,80]],
  ['محمد عبد الواحد عبد الله', 'SL2030', [100,75,70,56,90,73,71,90,90]],
  ['محمد مراد خلف',            'SL2031', [70,68,55,30,30,34,55,60,60]],
  ['معاوية إبراهيم شلال',      'SL2032', [93,68,95,42,95,59,61,60,60]],
  ['منتظر دخيل احمد عبد الله', 'SL2033', [100,50,25,30,30,33,29,60,60]],
  ['مهند مثنى احميد',          'SL2034', [95,80,60,60,85,50,52,60,60]],
  ['مهند مكي احمد',            'SL2035', [100,100,97,97,100,98,100,100,100]],
  ['يعقوب خلف عبد الله',       'SL2036', [93,68,55,62,90,50,70,70,70]],
  ['يوسف فؤاد عكلة',           'SL2037', [100,60,65,25,60,51,57,60,60]],
  ['يوسف محمد محمود',          'SL2038', [100,88,75,67,95,53,55,70,70]],
  ['اثير جمال محمود فارس',     'SL2039', [90,90,98,25,50,60,73,70,70]],
  ['احمد عمر شعيب',            'SL2040', [88,60,65,35,50,42,54,60,60]],
  ['احمد لازم محمد محمود',     'SL2041', [50,50,60,52,50,70,79,70,70]],
  ['انس عدنان دخيل',           'SL2042', [60,60,25,32,85,35,33,60,60]],
  ['أنور رمضان حسن',           'SL2043', [57,40,60,28,25,35,33,60,60]],
  ['أنور سمير حمد',            'SL2044', [88,60,50,50,25,51,54,60,60]],
  ['بشير جاسم محمد خلف',       'SL2045', [85,52,50,36,30,60,72,70,70]],
  ['رجب عماد رجب',             'SL2046', [100,80,95,50,50,64,67,70,70]],
  ['رداد زياد خلف',            'SL2047', [94,25,75,42,30,85,75,70,70]],
  ['سرمد إبراهيم مزهر',        'SL2048', [93,50,70,29,50,40,51,60,60]],
  ['سفيان حسن محمود عواد',     'SL2049', [82,30,40,29,30,43,70,70,70]],
  ['سلوان عنتر حمد',           'SL2050', [78,50,70,52,58,35,50,60,60]],
  ['سيف برهان خزعل',           'SL2051', [100,80,95,52,85,57,59,70,70]],
  ['طالل فرج عتيج',            'SL2052', [98,57,60,26,70,39,50,60,60]],
  ['عبد الباري معد عيد',       'SL2053', [100,70,95,50,62,43,55,70,70]],
  ['عبد الرحمن احمد شعيب',     'SL2054', [98,75,60,35,50,51,51,60,60]],
  ['عبد الرحمن رعد خلف',       'SL2055', [85,60,25,25,25,35,44,60,60]],
  ['عبد الرحمن عمار علي',      'SL2056', [85,70,70,40,50,50,61,60,60]],
  ['عبد الرحمن ندا عباس',      'SL2057', [60,25,40,27,30,42,43,60,60]],
  ['عبد السلام عبد الله عبد',  'SL2058', [100,95,95,70,95,98,98,100,100]],
  ['عبد السلام علي فارس',      'SL2059', [100,80,95,43,80,58,58,70,70]],
  ['عبد السلام نجم عبد الله',  'SL2060', [77,52,40,30,30,33,39,60,60]],
  ['عبد الكريم محمد عيد علي',  'SL2061', [100,80,70,40,90,51,72,100,100]],
  ['عبد الله خلف احمد',        'SL2062', [98,92,75,61,90,69,73,70,70]],
  ['عبد الله عماد خلف',        'SL2063', [100,57,60,29,27,41,52,60,60]],
  ['عبد الله محمود حمد',       'SL2064', [78,41,30,32,25,34,53,60,60]],
  ['عبيدة وعد عيد',            'SL2065', [100,60,50,43,90,55,58,60,60]],
  ['علي جبار احمد',            'SL2066', [100,70,40,25,50,39,57,60,60]],
  ['علي حسام جاسم',            'SL2067', [81,78,55,51,34,66,55,60,60]],
  ['عمار اركان عباس',          'SL2068', [100,94,98,63,90,58,58,90,90]],
  ['لازم حازم محمد جدوع',      'SL2069', [100,75,60,37,32,50,54,60,60]],
  ['ليث عماد خلف',             'SL2070', [82,25,25,28,50,36,52,60,60]],
  ['مصطفى ناطق عواد',          'SL2071', [71,53,35,34,55,41,40,60,60]],
  ['منتظر جاسم حسين',          'SL2072', [100,40,30,28,50,41,52,60,60]],
  ['هيثم هاشم محمد جدوع',      'SL2073', [100,65,75,42,30,50,57,60,60]],
  ['وسام اثير جبار بكر',       'SL2074', [100,90,75,75,51,75,75,100,100]],
  ['وسام ظاهر مجيد',           'SL2075', [100,80,75,59,90,71,71,90,90]],
  ['يوسف عبد الملك علي',       'SL2076', [100,78,70,42,90,50,51,70,70]],
];

const ADMIN_CODE = 'alijassim';

function getScoreClass(score) {
  if (score >= 75) return 'score-high';
  if (score >= 50) return 'score-mid';
  return 'score-low';
}

function doLogin() {
  const code = document.getElementById('codeInput').value.trim();
  const errEl = document.getElementById('errorMsg');
  errEl.style.display = 'none';

  if (code === ADMIN_CODE) {
    showAdmin();
    return;
  }

  const student = STUDENTS.find(s => s[1] === code);
  if (student) {
    showResults(student);
  } else {
    errEl.style.display = 'block';
    document.getElementById('codeInput').style.borderColor = '#e74c3c';
    setTimeout(() => {
      document.getElementById('codeInput').style.borderColor = '';
    }, 2000);
  }
}

document.getElementById('codeInput').addEventListener('keydown', e => {
  if (e.key === 'Enter') doLogin();
});

function showResults(student) {
  const [name, code, scores] = student;
  document.getElementById('loginPage').style.display = 'none';
  document.getElementById('resultsPage').style.display = 'block';

  document.getElementById('resName').textContent = name;
  document.getElementById('resMeta').textContent = 'الصف: الخامس العلمي  |  رقم السري: ' + code;

  const tbody = document.getElementById('resTableBody');
  tbody.innerHTML = '';
  let total = 0;

  SUBJECTS.forEach((subj, i) => {
    const sc = scores[i];
    total += sc;
    const tr = document.createElement('tr');
    tr.innerHTML = `<td>${subj}</td><td class="${getScoreClass(sc)}">${sc}</td>`;
    tbody.appendChild(tr);
  });

  const avg = (total / SUBJECTS.length).toFixed(1);
  document.getElementById('resTotal').textContent = total;
  document.getElementById('resAvg').textContent = avg + '%';
}

function showAdmin() {
  document.getElementById('loginPage').style.display = 'none';
  document.getElementById('adminPanel').style.display = 'block';
  renderAll();
}

function renderAll() {
  renderSearchResults(STUDENTS);
}

function searchStudents() {
  const q = document.getElementById('adminSearch').value.trim();
  if (!q) { renderSearchResults(STUDENTS); return; }
  const filtered = STUDENTS.filter(s => s[0].includes(q) || s[1].includes(q));
  renderSearchResults(filtered);
}

function renderSearchResults(list) {
  const container = document.getElementById('searchResults');
  if (list.length === 0) {
    container.innerHTML = '<p style="color:var(--gray);text-align:center;padding:20px">لا توجد نتائج</p>';
    return;
  }
  container.innerHTML = list.map(s =>
    `<div class="search-item" onclick="viewStudentAdmin('${s[1]}')">
      <span class="search-item-name">${s[0]}</span>
      <span class="search-item-code">${s[1]}</span>
    </div>`
  ).join('');
}

function viewStudentAdmin(code) {
  const student = STUDENTS.find(s => s[1] === code);
  if (student) {
    document.getElementById('adminPanel').style.display = 'none';
    showResults(student);
    // Store that we came from admin
    window._fromAdmin = true;
  }
}

function goBack() {
  document.getElementById('resultsPage').style.display = 'none';
  document.getElementById('adminPanel').style.display = 'none';
  document.getElementById('codeInput').value = '';
  document.getElementById('errorMsg').style.display = 'none';

  if (window._fromAdmin) {
    window._fromAdmin = false;
    document.getElementById('adminPanel').style.display = 'block';
  } else {
    document.getElementById('loginPage').style.display = 'block';
  }
}
</script>
</body>
</html>
