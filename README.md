<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة الاختبارات العلمية - أنشئ مصطلحاتك الخاصة</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Tajawal', 'Segoe UI', system-ui, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #e9edf2 100%);
            padding: 2rem 1rem;
            min-height: 100vh;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        .card {
            background: white;
            border-radius: 28px;
            box-shadow: 0 20px 35px -10px rgba(0, 0, 0, 0.1);
            padding: 1.8rem;
            margin-bottom: 2rem;
            transition: all 0.2s ease;
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            flex-wrap: wrap;
            border-bottom: 2px solid #eef2f6;
            padding-bottom: 1rem;
            margin-bottom: 1.5rem;
        }

        h2 {
            font-size: 1.6rem;
            color: #1e2a3e;
            font-weight: 700;
        }

        h3 {
            font-size: 1.3rem;
            color: #0f3b5e;
            margin-bottom: 1rem;
            border-right: 5px solid #2c7da0;
            padding-right: 1rem;
        }

        .term-form {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 1.5rem;
            align-items: flex-end;
        }

        .input-group {
            flex: 1;
            min-width: 180px;
        }

        .input-group label {
            display: block;
            font-weight: 600;
            color: #2c3e50;
            margin-bottom: 0.4rem;
            font-size: 0.85rem;
        }

        input {
            width: 100%;
            padding: 0.75rem 1rem;
            border-radius: 16px;
            border: 1px solid #cfdfed;
            background: #fefefe;
            font-size: 1rem;
            transition: 0.2s;
        }

        input:focus {
            outline: none;
            border-color: #2c7da0;
            box-shadow: 0 0 0 3px rgba(44,125,160,0.2);
        }

        button {
            background: #2c7da0;
            color: white;
            border: none;
            padding: 0.75rem 1.8rem;
            border-radius: 40px;
            font-weight: bold;
            font-size: 0.95rem;
            cursor: pointer;
            transition: 0.2s;
            box-shadow: 0 2px 6px rgba(0,0,0,0.05);
        }

        button:hover {
            background: #1f5e7a;
            transform: translateY(-2px);
        }

        .btn-outline {
            background: transparent;
            border: 1px solid #2c7da0;
            color: #2c7da0;
        }

        .btn-outline:hover {
            background: #2c7da0;
            color: white;
        }

        .btn-danger {
            background: #b23c1c;
        }
        
        .btn-danger:hover {
            background: #8e2e12;
        }

        .btn-warning {
            background: #d97706;
        }
        
        .btn-warning:hover {
            background: #b45309;
        }

        .terms-list {
            max-height: 320px;
            overflow-y: auto;
            border: 1px solid #e2e8f0;
            border-radius: 24px;
            padding: 0.5rem;
        }

        .term-item {
            background: #f8fafc;
            margin: 0.5rem 0;
            padding: 0.7rem 1rem;
            border-radius: 60px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .term-text {
            font-weight: 500;
        }
        
        .badge {
            background: #e2eaf1;
            padding: 0.2rem 0.9rem;
            border-radius: 30px;
            font-size: 0.8rem;
        }
        
        .warning-badge {
            background: #fed7aa;
            color: #9b4a00;
            padding: 0.5rem 1rem;
            border-radius: 16px;
            font-size: 0.9rem;
            margin-bottom: 1rem;
            text-align: center;
        }

        .quiz-section {
            margin-bottom: 2rem;
            background: #ffffffdd;
            border-radius: 24px;
            padding: 1rem;
            box-shadow: 0 4px 12px rgba(0,0,0,0.03);
        }

        table {
            width: 100%;
            border-collapse: collapse;
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 1px 2px rgba(0,0,0,0.05);
        }

        th, td {
            border-bottom: 1px solid #eef2f8;
            padding: 1rem 0.8rem;
            text-align: right;
            vertical-align: middle;
        }

        th {
            background: #f1f6fa;
            font-weight: 700;
            color: #1e4663;
        }

        .quiz-input {
            width: 95%;
            padding: 0.6rem;
            border-radius: 14px;
            border: 1px solid #cbdde9;
        }

        select {
            width: 100%;
            padding: 0.6rem;
            border-radius: 14px;
            border: 1px solid #cbdde9;
            background: white;
            font-size: 0.95rem;
        }

        .result-area {
            text-align: center;
            margin-top: 1.8rem;
            padding: 1.5rem;
            background: #f0f7fc;
            border-radius: 40px;
        }

        .score {
            font-size: 2.5rem;
            font-weight: 800;
            color: #1f6392;
        }

        .flex-btns {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 1rem;
        }
        
        .disabled-btn {
            opacity: 0.5;
            cursor: not-allowed;
            pointer-events: none;
        }
        
        .empty-state {
            text-align: center;
            padding: 2rem;
            color: #6c757d;
        }

        @media (max-width: 700px) {
            .card { padding: 1.2rem; }
            th, td { font-size: 0.85rem; }
        }
    </style>
</head>
<body>
<div class="container">
    <!-- قسم إدارة المصطلحات -->
    <div class="card">
        <div class="card-header">
            <h2>📚 بنك المصطلحات العلمية</h2>
            <span id="termCountBadge" class="badge">0 مصطلح</span>
        </div>
        
        <div class="term-form">
            <div class="input-group">
                <label>🇬🇧 المصطلح (إنجليزي)</label>
                <input type="text" id="engTerm" placeholder="مثال: Nutrition" autocomplete="off">
            </div>
            <div class="input-group">
                <label>🇸🇦 الترجمة (عربي)</label>
                <input type="text" id="arabicTerm" placeholder="مثال: تغذية">
            </div>
            <button id="addTermBtn">➕ إضافة مصطلح</button>
        </div>
        
        <div id="termsListContainer" class="terms-list">
            <div class="empty-state">📭 لا توجد مصطلحات بعد. أضف مصطلحاتك العلمية أولاً</div>
        </div>
        
        <div id="minTermsWarning" class="warning-badge" style="margin-top: 1rem; background: #fee2e2; color: #991b1b; display: none;">
            ⚠️ تحتاج إلى 10 مصطلحات على الأقل لبدء الاختبار. أضف المزيد من المصطلحات.
        </div>
    </div>

    <!-- قسم الاختبار الديناميكي -->
    <div class="card" id="quizCard">
        <div class="card-header">
            <h2>📝 الاختبار العلمي (15 درجة)</h2>
            <button id="generateQuizBtn" class="btn-outline">🎲 إنشاء اختبار جديد</button>
        </div>

        <div id="quizDynamicArea">
            <div class="empty-state">📌 أضف 10 مصطلحات على الأقل ثم اضغط "إنشاء اختبار جديد"</div>
        </div>

        <div id="resultArea" style="display: none;">
            <div id="scoreDisplay"></div>
            <div class="flex-btns">
                <button id="submitQuizBtn" style="background:#2c7da0;">✔️ إنهاء الاختبار وحساب الدرجة</button>
                <button id="newQuizSameBankBtn" class="btn-outline">🔄 اختبار آخر (مصطلحات مختلفة)</button>
            </div>
        </div>
    </div>
</div>

<script>
    // ---------------------- قاعدة المصطلحات (فارغة تماماً في البداية) -------------------------
    let masterTerms = [];    // كل عنصر {id, eng, ar}
    let nextId = 1;

    // متغيرات تخزين بيانات الاختبار الحالي
    let currentQuiz = {
        section1: [],   // [{id, eng, ar, userAnswer}]
        section2: [],
        section3: []    // [{id, eng, ar, options: [], selectedAnswer}]
    };

    // عرض المصطلحات في اللوحة
    function renderTermsList() {
        const container = document.getElementById('termsListContainer');
        if (!masterTerms.length) {
            container.innerHTML = '<div class="empty-state">📭 لا توجد مصطلحات بعد. أضف مصطلحاتك العلمية أولاً</div>';
            return;
        }
        let html = '';
        masterTerms.forEach((term) => {
            html += `
                <div class="term-item">
                    <span class="term-text"><strong>${escapeHtml(term.eng)}</strong>  →  ${escapeHtml(term.ar)}</span>
                    <button class="remove-term-btn" data-id="${term.id}" style="background:#b91c1c; padding:0.3rem 1rem; border-radius:30px;">✖ حذف</button>
                </div>
            `;
        });
        container.innerHTML = html;
        
        // ربط أزرار الحذف
        document.querySelectorAll('.remove-term-btn').forEach(btn => {
            btn.addEventListener('click', (e) => {
                const id = Number(btn.dataset.id);
                masterTerms = masterTerms.filter(t => t.id !== id);
                renderTermsList();
                updateTermCount();
                checkQuizAvailability();
                // عند حذف مصطلح، نقوم بتعطيل الاختبار الحالي
                disableQuiz();
            });
        });
    }
    
    function escapeHtml(str) {
        if (!str) return '';
        return str.replace(/[&<>]/g, function(m) {
            if (m === '&') return '&amp;';
            if (m === '<') return '&lt;';
            if (m === '>') return '&gt;';
            return m;
        });
    }

    function updateTermCount() {
        const count = masterTerms.length;
        document.getElementById('termCountBadge').innerText = count + ' مصطلح';
        
        const warningDiv = document.getElementById('minTermsWarning');
        if (count < 10) {
            warningDiv.style.display = 'block';
            warningDiv.innerHTML = `⚠️ تحتاج إلى 10 مصطلحات على الأقل لبدء الاختبار. لديك ${count} مصطلح. أضف ${10 - count} مصطلح آخر.`;
        } else {
            warningDiv.style.display = 'none';
        }
    }
    
    function checkQuizAvailability() {
        const generateBtn = document.getElementById('generateQuizBtn');
        if (masterTerms.length < 10) {
            generateBtn.classList.add('disabled-btn');
            generateBtn.title = 'تحتاج إلى 10 مصطلحات على الأقل';
        } else {
            generateBtn.classList.remove('disabled-btn');
            generateBtn.title = '';
        }
    }
    
    function disableQuiz() {
        // إخفاء الاختبار الحالي
        document.getElementById('quizDynamicArea').innerHTML = '<div class="empty-state">📌 أضف 10 مصطلحات على الأقل ثم اضغط "إنشاء اختبار جديد"</div>';
        document.getElementById('resultArea').style.display = 'none';
        currentQuiz = { section1: [], section2: [], section3: [] };
    }

    // إضافة مصطلح جديد
    function addTerm(eng, ar) {
        if (!eng.trim() || !ar.trim()) {
            alert("الرجاء ملء الحقلين (إنجليزي وعربي)");
            return false;
        }
        
        // التحقق من عدم وجود تكرار في الإنجليزي
        const existingEng = masterTerms.some(t => t.eng.toLowerCase() === eng.trim().toLowerCase());
        if (existingEng) {
            alert("هذا المصطلح الإنجليزي موجود بالفعل!");
            return false;
        }
        
        masterTerms.push({ id: nextId++, eng: eng.trim(), ar: ar.trim() });
        renderTermsList();
        updateTermCount();
        checkQuizAvailability();
        return true;
    }

    // ----- دوال مساعدة للاختبار -----
    function getRandomItems(arr, count) {
        if (count > arr.length) count = arr.length;
        const shuffled = [...arr];
        for (let i = shuffled.length - 1; i > 0; i--) {
            const j = Math.floor(Math.random() * (i + 1));
            [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
        }
        return shuffled.slice(0, count);
    }

    // إنشاء اختبار جديد كامل
    function generateFullQuiz() {
        if (masterTerms.length < 10) {
            alert(`لا يمكن إنشاء الاختبار! تحتاج إلى 10 مصطلحات على الأقل. لديك ${masterTerms.length} مصطلح.`);
            return false;
        }

        const allTerms = [...masterTerms];
        
        // القسم1: 5 مصطلحات عشوائية (كتابة العربي)
        let sec1Items = getRandomItems(allTerms, 5);
        
        // القسم2: 5 مصطلحات مختلفة عن القسم1 قدر الإمكان
        let remainingTerms = allTerms.filter(t => !sec1Items.some(s1 => s1.id === t.id));
        let sec2Items = [];
        if (remainingTerms.length >= 5) {
            sec2Items = getRandomItems(remainingTerms, 5);
        } else {
            // إذا لم يبقَ كافٍ، نأخذ من الكل ولكن نتجنب التكرار الكبير
            sec2Items = getRandomItems(allTerms, 5);
        }
        
        // القسم3: 5 مصطلحات للتوصيل (إنجليزي -> عربي) مع خيارات عشوائية
        let sec3ItemsRaw = getRandomItems(allTerms, 5);
        let sec3WithOptions = sec3ItemsRaw.map(item => {
            // اختيار 4 ترجمات عربية عشوائية من مصطلحات أخرى
            let otherTerms = masterTerms.filter(t => t.id !== item.id);
            let randomArabics = getRandomItems(otherTerms, 4).map(t => t.ar);
            let optionsSet = [item.ar, ...randomArabics];
            // خلط الخيارات
            for (let i = optionsSet.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [optionsSet[i], optionsSet[j]] = [optionsSet[j], optionsSet[i]];
            }
            return {
                id: item.id,
                eng: item.eng,
                correctAr: item.ar,
                options: optionsSet,
                selectedAnswer: ""
            };
        });

        currentQuiz = {
            section1: sec1Items.map(item => ({ ...item, userAnswer: "" })),
            section2: sec2Items.map(item => ({ ...item, userAnswer: "" })),
            section3: sec3WithOptions
        };
        
        renderQuizToDOM();
        document.getElementById('resultArea').style.display = 'block';
        return true;
    }

    // عرض الاختبار في الـ DOM
    function renderQuizToDOM() {
        const container = document.getElementById('quizDynamicArea');
        if (!container) return;
        
        let html = `
            <div class="quiz-section">
                <h3>📖 القسم الأول: اكتب المصطلح باللغة العربية (5 درجات)</h3>
                <table>
                    <thead>
                        <tr><th>#</th><th>المصطلح (إنجليزي)</th><th>إجابتك (عربي)</th></tr>
                    </thead>
                    <tbody>
        `;
        currentQuiz.section1.forEach((item, idx) => {
            html += `
                <tr>
                    <td>${idx+1}</td>
                    <td>${escapeHtml(item.eng)}</td>
                    <td><input type="text" class="quiz-input sec1-input" data-id="${item.id}" placeholder="أدخل الترجمة العربية"></td>
                </tr>
            `;
        });
        html += `</tbody></table></div>`;

        // القسم الثاني (عكس: اكتب بالإنجليزية)
        html += `<div class="quiz-section"><h3>🇬🇧 القسم الثاني: اكتب المصطلح باللغة الإنجليزية (5 درجات)</h3>
        <table><thead><tr><th>#</th><th>المصطلح (عربي)</th><th>إجابتك (إنجليزي)</th></tr></thead><tbody>`;
        currentQuiz.section2.forEach((item, idx) => {
            html += `
                <tr>
                    <td>${idx+1}</td>
                    <td>${escapeHtml(item.ar)}</td>
                    <td><input type="text" class="quiz-input sec2-input" data-id="${item.id}" placeholder="أدخل المصطلح الإنجليزي"></td>
                </tr>
            `;
        });
        html += `</tbody></table></div>`;

        // القسم الثالث: توصيل (منسدلة)
        html += `<div class="quiz-section"><h3>🔗 القسم الثالث: وصّل المصطلح الإنجليزي بالترجمة العربية الصحيحة (5 درجات)</h3>
        <table><thead><tr><th>المصطلح (إنجليزي)</th><th>اختر الترجمة الصحيحة</th></tr></thead><tbody>`;
        currentQuiz.section3.forEach((item) => {
            let optionsHtml = `<select class="sec3-select" data-id="${item.id}"><option value="">-- اختر الإجابة --</option>`;
            item.options.forEach(opt => {
                optionsHtml += `<option value="${escapeHtml(opt)}">${escapeHtml(opt)}</option>`;
            });
            optionsHtml += `</select>`;
            html += `<tr><td><strong>${escapeHtml(item.eng)}</strong></td><td>${optionsHtml}</td></tr>`;
        });
        html += `</tbody></table></div>`;
        container.innerHTML = html;

        // ربط الأحداث لتحديث الإجابات
        document.querySelectorAll('.sec1-input').forEach(inp => {
            inp.addEventListener('input', (e) => {
                const termId = Number(inp.dataset.id);
                const val = inp.value;
                const termObj = currentQuiz.section1.find(t => t.id === termId);
                if (termObj) termObj.userAnswer = val;
            });
        });
        
        document.querySelectorAll('.sec2-input').forEach(inp => {
            inp.addEventListener('input', (e) => {
                const termId = Number(inp.dataset.id);
                const val = inp.value;
                const termObj = currentQuiz.section2.find(t => t.id === termId);
                if (termObj) termObj.userAnswer = val;
            });
        });
        
        document.querySelectorAll('.sec3-select').forEach(sel => {
            sel.addEventListener('change', (e) => {
                const termId = Number(sel.dataset.id);
                const selected = sel.value;
                const sec3Item = currentQuiz.section3.find(item => item.id === termId);
                if (sec3Item) sec3Item.selectedAnswer = selected;
            });
        });
    }

    // حساب الدرجة الكلية (15)
    function calculateAndShowScore() {
        if (currentQuiz.section1.length === 0) {
            alert("يرجى إنشاء اختبار أولاً بالضغط على 'إنشاء اختبار جديد'");
            return;
        }
        
        let totalScore = 0;

        // القسم الأول: مقارنة النص المدخل مع الترجمة العربية الصحيحة
        for (let item of currentQuiz.section1) {
            const userAns = item.userAnswer?.trim().toLowerCase() || "";
            const correct = item.ar.toLowerCase();
            if (userAns === correct) totalScore += 1;
        }

        // القسم الثاني: مقارنة النص المدخل مع المصطلح الإنجليزي
        for (let item of currentQuiz.section2) {
            const userAns = item.userAnswer?.trim().toLowerCase() || "";
            const correctEng = item.eng.toLowerCase();
            if (userAns === correctEng) totalScore += 1;
        }

        // القسم الثالث: مقارنة الاختيار مع الترجمة الصحيحة
        for (let item of currentQuiz.section3) {
            if (item.selectedAnswer && item.selectedAnswer === item.correctAr) {
                totalScore += 1;
            }
        }

        const scoreElement = document.getElementById('scoreDisplay');
        let gradeMessage = "";
        if (totalScore === 15) gradeMessage = "🎉 ممتاز! إتقان كامل!";
        else if (totalScore >= 12) gradeMessage = "👍 جيد جداً!";
        else if (totalScore >= 9) gradeMessage = "📘 جيد، يمكنك تحسين أدائك";
        else gradeMessage = "📚 تحتاج إلى مراجعة المصطلحات أكثر";
        
        scoreElement.innerHTML = `<div class="score">${totalScore} / 15</div>
                                  <div style="font-size:1.1rem; margin-top:0.5rem;">${gradeMessage}</div>`;
        
        document.getElementById('resultArea').style.display = 'block';
        document.getElementById('resultArea').scrollIntoView({ behavior: 'smooth', block: 'center' });
    }

    // إنشاء اختبار جديد عشوائي
    function generateNewRandomQuiz() {
        if (masterTerms.length < 10) {
            alert(`لا يمكن إنشاء الاختبار! تحتاج إلى 10 مصطلحات على الأقل. لديك ${masterTerms.length} مصطلح.`);
            return;
        }
        generateFullQuiz();
    }

    // تهيئة المستمعين
    function bindGlobalActions() {
        document.getElementById('addTermBtn').addEventListener('click', () => {
            const eng = document.getElementById('engTerm').value;
            const ar = document.getElementById('arabicTerm').value;
            if (addTerm(eng, ar)) {
                document.getElementById('engTerm').value = '';
                document.getElementById('arabicTerm').value = '';
            }
        });
        
        document.getElementById('generateQuizBtn').addEventListener('click', () => {
            if (masterTerms.length >= 10) {
                generateNewRandomQuiz();
            } else {
                alert(`لا يمكن إنشاء الاختبار! تحتاج إلى 10 مصطلحات على الأقل. لديك ${masterTerms.length} مصطلح.`);
            }
        });
        
        document.getElementById('submitQuizBtn').addEventListener('click', () => {
            calculateAndShowScore();
        });
        
        document.getElementById('newQuizSameBankBtn').addEventListener('click', () => {
            if (masterTerms.length >= 10) {
                generateNewRandomQuiz();
            } else {
                alert("لا توجد مصطلحات كافية لإنشاء اختبار جديد");
            }
        });
        
        // إضافة Enter key للإضافة السريعة
        const inputs = ['engTerm', 'arabicTerm'];
        inputs.forEach(id => {
            document.getElementById(id).addEventListener('keypress', (e) => {
                if (e.key === 'Enter') {
                    e.preventDefault();
                    document.getElementById('addTermBtn').click();
                }
            });
        });
    }

    // بداية التشغيل (بدون أي مصطلحات مسبقة)
    function init() {
        masterTerms = [];
        nextId = 1;
        renderTermsList();
        updateTermCount();
        checkQuizAvailability();
        bindGlobalActions();
        disableQuiz();
    }
    
    init();
</script>
</body>
</html>
