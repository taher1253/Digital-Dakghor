<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ডিজিটাল ডাকঘর - Digital Dakghor</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Anek+Bangla:wght@400;600&family=Atma:wght@500;600;700&display=swap');

        :root {
            --postal-red: #9E2A2B;
            --postal-red-hover: #7E1F21;
            --cream-bg: #F5EBE0;
            --paper-bg: #FAF6F0;
            --card-bg: #322A26;
            --ink-color: #2B1E1A;
            --gold-accent: #D4AF37;
            --text-light: #E8DCC4;
        }

        body {
            margin: 0;
            padding: 30px 15px;
            background-color: var(--card-bg);
            background-image: radial-gradient(#423833 1px, transparent 1px);
            background-size: 20px 20px;
            font-family: 'Anek Bangla', sans-serif;
            color: var(--text-light);
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        header {
            text-align: center;
            margin-bottom: 30px;
        }

        header h1 {
            color: var(--gold-accent);
            margin: 0 0 8px 0;
            font-size: 2.5rem;
            letter-spacing: 1px;
            font-weight: 700;
        }

        header p {
            color: var(--cream-bg);
            margin: 0;
            font-size: 1.1rem;
            opacity: 0.9;
        }

        .container {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            justify-content: center;
            max-width: 1050px;
            width: 100%;
        }

        /* Form Card */
        .editor-card {
            background: #251F1C;
            padding: 25px;
            border-radius: 16px;
            flex: 1;
            min-width: 320px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.5);
            border: 1px solid #423833;
        }

        .editor-card h3 {
            color: var(--gold-accent);
            margin-top: 0;
            margin-bottom: 20px;
            border-bottom: 1px solid #423833;
            padding-bottom: 10px;
        }

        .form-group {
            margin-bottom: 18px;
        }

        label {
            display: block;
            margin-bottom: 6px;
            font-weight: 600;
            color: var(--cream-bg);
            font-size: 0.95rem;
        }

        input, select, textarea {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            border: 1px solid #4D3E38;
            background: #1A1513;
            color: #FFF;
            box-sizing: border-box;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--gold-accent);
            box-shadow: 0 0 8px rgba(212, 175, 55, 0.2);
        }

        textarea {
            height: 140px;
            resize: vertical;
        }

        .btn-submit {
            background-color: var(--postal-red);
            color: #FFF;
            border: 1px solid var(--gold-accent);
            padding: 14px 20px;
            font-size: 1.1rem;
            border-radius: 8px;
            cursor: pointer;
            width: 100%;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(158, 42, 43, 0.4);
            margin-top: 10px;
        }

        .btn-submit:hover {
            background-color: var(--postal-red-hover);
            transform: translateY(-2px);
        }

        /* Preview Area */
        .preview-card {
            flex: 1;
            min-width: 320px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .preview-card h3 {
            color: var(--gold-accent);
            margin-top: 0;
            margin-bottom: 20px;
        }

        .letter-paper {
            background-color: var(--paper-bg);
            color: var(--ink-color);
            padding: 30px;
            border-radius: 6px;
            width: 100%;
            box-sizing: border-box;
            min-height: 260px;
            box-shadow: 0 8px 20px rgba(0,0,0,0.4);
            position: relative;
            border: 1px solid #E0D5C1;
            background-image: linear-gradient(#E8DFCE 1px, transparent 1px);
            background-size: 100% 28px;
            line-height: 28px;
        }

        .letter-content {
            font-size: 1.25rem;
            white-space: pre-wrap;
            word-break: break-word;
        }

        /* Premium Envelope */
        .envelope {
            margin-top: 25px;
            width: 100%;
            height: 190px;
            background: linear-gradient(135deg, #9E2A2B, #7E1F21);
            border-radius: 12px;
            position: relative;
            box-shadow: 0 10px 20px rgba(0,0,0,0.5);
            display: flex;
            justify-content: center;
            align-items: center;
            border: 2px solid var(--gold-accent);
        }

        .stamp {
            position: absolute;
            top: 15px;
            right: 15px;
            width: 55px;
            height: 65px;
            background: #FDFBF7;
            border: 2px dashed var(--postal-red);
            color: var(--ink-color);
            font-size: 0.75rem;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0,0,0,0.2);
            border-radius: 3px;
        }

        .wax-seal {
            width: 55px;
            height: 55px;
            background: radial-gradient(circle, #D4AF37 0%, #AA820A 100%);
            border-radius: 50%;
            border: 2px solid #FFF8DC;
            box-shadow: 0 4px 8px rgba(0,0,0,0.4);
            display: flex;
            align-items: center;
            justify-content: center;
            color: #3A2800;
            font-weight: bold;
            font-size: 0.85rem;
            letter-spacing: 1px;
        }

        .font-atma { font-family: 'Atma', cursive; }
        .font-anek { font-family: 'Anek Bangla', sans-serif; }
    </style>
</head>
<body>

    <header>
        <h1>✉️ ডিজিটাল ডাকঘর</h1>
        <p>ইমেইলের যুগে, হারিয়ে যাওয়া চিঠির অনুভূতি।</p>
    </header>

    <div class="container">
        <div class="editor-card">
            <h3>চিঠি লিখুন ও কাস্টমাইজ করুন</h3>
            
            <div class="form-group">
                <label>প্রাপকের নাম:</label>
                <input type="text" id="receiverName" placeholder="যেমন: প্রিয় রবীন্দ্রনাথ" oninput="updateLetter()">
            </div>

            <div class="form-group">
                <label>আপনার চিঠি:</label>
                <textarea id="letterText" placeholder="এখানে আপনার মনের কথাগুলো লিখুন..." oninput="updateLetter()"></textarea>
            </div>

            <div class="form-group">
                <label>ফন্ট নির্বাচন করুন:</label>
                <select id="fontSelect" onchange="updateLetter()">
                    <option value="font-atma">হাতে লেখা স্টাইল (Atma)</option>
                    <option value="font-anek">ক্লাসিক স্টাইল (Anek Bangla)</option>
                </select>
            </div>

            <div class="form-group">
                <label>ডেলিভারির মোড:</label>
                <select id="deliveryMode">
                    <option value="digital">ডিজিটাল (রাত ১২টায় SMS মাধ্যমে)</option>
                    <option value="physical">ফিজিক্যাল (প্রিন্ট ও ডাকযোগে পাঠাও)</option>
                </select>
            </div>

            <div class="form-group">
                <label>প্রাপকের নম্বর / ঠিকানা:</label>
                <input type="text" id="contactInfo" placeholder="মোবাইল নম্বর বা সম্পূর্ণ ঠিকানা">
            </div>

            <button class="btn-submit" onclick="sendLetter()">চিঠি পাঠান ➔</button>
        </div>

        <div class="preview-card">
            <h3>চিঠির প্রিভিউ</h3>
            <div class="letter-paper" id="paper">
                <div class="letter-content font-atma" id="previewText">
প্রিয় [প্রাপকের নাম],

এখানে আপনার লেখা চিঠিটি রিয়েল-টাইমে ভেসে উঠবে...
                </div>
            </div>

            <div class="envelope">
                <div class="stamp">
                    📮<br>ডাকটিকিট<br>৳১০
                </div>
                <div class="wax-seal">
                    সিল
                </div>
            </div>
        </div>
    </div>

    <script>
        function updateLetter() {
            const name = document.getElementById('receiverName').value || '[প্রাপকের নাম]';
            const text = document.getElementById('letterText').value || 'এখানে আপনার লেখা চিঠিটি রিয়েল-টাইমে ভেসে উঠবে...';
            const font = document.getElementById('fontSelect').value;

            const preview = document.getElementById('previewText');
            preview.className = `letter-content ${font}`;
            preview.innerText = `প্রিয় ${name},\n\n${text}`;
        }

        function sendLetter() {
            const mode = document.getElementById('deliveryMode').value;
            const contact = document.getElementById('contactInfo').value;

            if(!contact) {
                alert('অনুগ্রহ করে মোবাইল নম্বর বা ঠিকানা প্রদান করুন!');
                return;
            }

            if(mode === 'digital') {
                alert('আপনার ডিজিটাল চিঠিটি প্রস্তুত! নির্ধারিত সময়ে এটি SMS আকারে পৌঁছে যাবে।');
            } else {
                alert('অর্ডারটি গ্রহণ করা হয়েছে! প্রিমিয়াম ভিন্টেজ কাগজে প্রিন্ট করে চিঠিটি ডাকযোগে পাঠানো হবে।');
            }
        }
    </script>
</body>
</html>
