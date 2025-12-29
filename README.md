<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Kho Ứng Dụng - Nguyễn Danh Thành Trung</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@800&family=Inter:wght@400;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root {
            --cyan: #00f2fe; 
            --white: #fff;
            --glass: rgba(255, 255, 255, 0.03);
            --border: rgba(255, 255, 255, 0.1);
            --red: #ff4757;
            --ios-blue: #007AFF;
        }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Inter', sans-serif; }

        body { 
            background: radial-gradient(circle at 50% 0%, #1e1b4b, #030712);
            color: var(--white); 
            min-height: 100vh; 
            display: grid; 
            place-items: center;
            overflow-x: hidden; 
            perspective: 1000px;
            padding: 20px 0;
        }

        canvas { position: fixed; inset: 0; z-index: -1; pointer-events: none; }
        
        .card {
            width: 92%; max-width: 400px;
            padding: 40px 20px;
            background: var(--glass); 
            backdrop-filter: blur(25px); 
            -webkit-backdrop-filter: blur(25px);
            border: 1px solid var(--border); 
            border-radius: 35px;
            box-shadow: 0 20px 50px rgba(0,0,0,0.5); 
            text-align: center;
            will-change: transform; 
            transition: transform 0.2s ease-out;
            animation: cardAppear 1s ease-out;
            z-index: 10;
        }

        @keyframes cardAppear {
            from { opacity: 0; transform: scale(0.9) translateY(30px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }

        .header { margin-bottom: 30px; }

        .header-icon {
            font-size: 2.5rem;
            color: var(--cyan);
            margin-bottom: 15px;
            animation: fadeInUp 0.8s ease backwards 0.2s;
            filter: drop-shadow(0 0 10px rgba(0, 242, 254, 0.5));
        }

        h1 { 
            font-family: 'Montserrat', sans-serif;
            font-size: clamp(1.2rem, 5.5vw, 1.6rem);
            font-weight: 800; 
            margin-bottom: 8px;
            background: linear-gradient(to right, #fff 20%, var(--cyan) 40%, #fff 60%, var(--cyan) 80%, #fff 100%);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shine 4s linear infinite, fadeInUp 0.8s ease backwards 0.4s;
        }

        @keyframes shine { to { background-position: 200% center; } }

        .tag { 
            color: var(--cyan); font-size: 0.65rem; font-weight: 700; 
            text-transform: uppercase; letter-spacing: 2px; 
            margin-bottom: 30px; opacity: 0.7; 
            animation: fadeInUp 0.8s ease backwards 0.6s;
        }

        .links { display: grid; gap: 14px; }

        .install-item {
            display: flex; 
            align-items: center; 
            padding: 12px;
            background: rgba(255,255,255,0.05); 
            border: 1px solid var(--border);
            border-radius: 22px; 
            color: inherit; 
            text-decoration: none;
            transition: 0.3s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            animation: fadeInUp 0.6s ease backwards;
        }

        .install-item:nth-child(1) { animation-delay: 0.7s; }
        .install-item:nth-child(2) { animation-delay: 0.8s; }
        .install-item:nth-child(3) { animation-delay: 0.9s; }

        .install-item:hover { 
            background: rgba(255,255,255,0.1); 
            border-color: var(--cyan); 
            transform: translateX(8px);
            box-shadow: 0 5px 15px rgba(0, 242, 254, 0.15);
        }

        .app-thumb {
            width: 52px; height: 52px;
            border-radius: 12px;
            object-fit: cover;
            margin-right: 15px;
            border: 1px solid rgba(255,255,255,0.1);
        }

        .app-meta { flex: 1; text-align: left; }
        .app-name { display: block; font-size: 0.95rem; font-weight: 700; color: var(--white); }
        .app-desc { display: block; font-size: 0.75rem; color: #fff; opacity: 0.6; margin-top: 2px; }

        .btn-get {
            background: rgba(255,255,255,0.1);
            color: var(--cyan);
            font-size: 0.75rem;
            font-weight: 800;
            padding: 6px 16px;
            border-radius: 20px;
            text-transform: uppercase;
            transition: 0.3s;
        }

        .install-item:hover .btn-get {
            background: var(--cyan);
            color: #000;
        }

        .btn-donate {
            position: fixed; top: 25px; right: 25px;
            display: flex; align-items: center; gap: 10px;
            padding: 10px 18px;
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(15px); -webkit-backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            border-radius: 50px; color: #fff; text-decoration: none;
            font-weight: 600; font-size: 0.85rem; z-index: 1000;
            transition: all 0.3s;
            animation: fadeInDown 0.8s ease backwards 1.2s;
        }

        .btn-donate i { color: var(--red); animation: heartBeat 1.5s infinite; }

        @keyframes heartBeat {
            0%, 70%, 100% { transform: scale(1); }
            14%, 42% { transform: scale(1.3); }
        }

        .btn-donate:hover {
            transform: translateY(3px);
            background: rgba(255, 255, 255, 0.15);
            border-color: var(--red);
        }

        .footer-notice {
            margin-top: 30px;
            font-size: 0.75rem;
            opacity: 0.5;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            animation: fadeInUp 0.8s ease backwards 1.1s;
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(15px); filter: blur(5px); }
            to { opacity: 1; transform: translateY(0); filter: blur(0); }
        }

        @keyframes fadeInDown {
            from { opacity: 0; transform: translateY(-20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @media (max-width: 480px) { 
            .card { padding: 35px 15px; } 
            .btn-donate { top: 15px; right: 15px; padding: 8px 14px; font-size: 0.75rem; }
        }
    </style>
</head>
<body>

    <canvas id="p"></canvas>

    <a href="https://ngdanhthanhtrung.github.io/Bank/" class="btn-donate" target="_blank">
        <i class="fa-solid fa-heart"></i>
        <span>Donate</span>
    </a>

    <div class="card" id="c">
        <div class="header">
            <div class="header-icon"><i class="fa-solid fa-layer-group"></i></div>
            <h1>Kho Ứng Dụng</h1>
            <p class="tag">IOS Apps</p>
        </div>
        
        <div class="links">
            <a href="itms-services://?action=download-manifest&url=https://dl.dropboxusercontent.com/scl/fi/wb4px2o3iigi9598hjyw1/Locket_2.7.1._vannquocisme.ipa?rlkey=pmcrxt4f8pezg0myoy8arlxlj&amp;st=7k799h8n&amp;dl=1" class="install-item">
                <img src="https://github.com/NgDanhThanhTrung/APP/raw/main/locket/logo_locket.jpg" class="app-thumb" alt="Locket">
                <div class="app-meta">
                    <span class="app-name">Locket Gold</span>
                    <span class="app-desc">Widget chia sẻ ảnh</span>
                </div>
                <div class="btn-get">Nhận</div>
            </a>

            <a href="itms-services://?action=download-manifest&url=https://dl.3u.com/soft/2025/09/27/z_932747118_878459483_1.ipa" class="install-item">
                <img src="https://github.com/NgDanhThanhTrung/APP/raw/main/shadowrocket/logo_shadowrocket.jpg" class="app-thumb" alt="Shadowrocket">
                <div class="app-meta">
                    <span class="app-name">Shadowrocket</span>
                    <span class="app-desc">Proxy & VPN Tool</span>
                </div>
                <div class="btn-get">Nhận</div>
            </a>

            <a href="itms-services://?action=download-manifest&url=https://dl.dropboxusercontent.com/scl/fi/tmhrqw3ycsjytzgjgc4wi/RoPhim.ipa?rlkey=jvmisc73unllst9qqo06w6pjl&st=xarldr6f&dl=1" class="install-item">
                <img src="https://github.com/NgDanhThanhTrung/APP/raw/main/rophim/logo_rophim.jpg" class="app-thumb" alt="Rophim">
                <div class="app-meta">
                    <span class="app-name">Rophim</span>
                    <span class="app-desc">Phim chất lượng cao</span>
                </div>
                <div class="btn-get">Nhận</div>
            </a>
        </div>

        <div class="footer-notice" id="safariNotice">
            <i class="fa-brands fa-safari"></i>
            <span>Vui lòng dùng Safari để cài đặt</span>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('p'), ctx = canvas.getContext('2d'), card = document.getElementById('c');
        let dots = [];

        const init = () => {
            canvas.width = window.innerWidth; canvas.height = window.innerHeight;
            dots = Array.from({length: 45}, () => ({
                x: Math.random() * canvas.width, y: Math.random() * canvas.height,
                vx: (Math.random() - 0.5) * 0.4, vy: (Math.random() - 0.5) * 0.4
            }));
        }

        const anim = () => {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = "rgba(0, 242, 254, 0.2)";
            dots.forEach(d => {
                d.x += d.vx; d.y += d.vy;
                if(d.x < 0 || d.x > canvas.width) d.vx *= -1;
                if(d.y < 0 || d.y > canvas.height) d.vy *= -1;
                ctx.beginPath(); ctx.arc(d.x, d.y, 1, 0, 7); ctx.fill();
            });
            requestAnimationFrame(anim);
        }

        window.onmousemove = e => {
            let x = (window.innerWidth/2 - e.pageX)/25, y = (window.innerHeight/2 - e.pageY)/25;
            card.style.transform = `rotateY(${x}deg) rotateX(${-y}deg)`;
        }
        
        window.onmouseleave = () => {
            card.style.transform = `rotateY(0deg) rotateX(0deg)`;
        }

        const isSafari = /^((?!chrome|android).)*safari/i.test(navigator.userAgent);
        if (!isSafari) {
            const notice = document.getElementById('safariNotice');
            notice.style.color = 'var(--red)';
            notice.querySelector('span').innerText = 'Hãy chuyển sang Safari để cài đặt';
        }

        window.onresize = init;
        init(); anim();
    </script>
</body>
</html>
