<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BetWin Casino - Bono de Bienvenida</title>
    <!-- Librería para generar QR -->
    <script src="https://cdn.jsdelivr.net/npm/qrcodejs@1.0.0/qrcode.min.js"></script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0a1a 0%, #1a0a2e 50%, #0a0a1a 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .container {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(20px);
            border-radius: 30px;
            padding: 45px 35px;
            max-width: 550px;
            width: 100%;
            border: 1px solid rgba(255, 215, 0, 0.2);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.9), 0 0 40px rgba(255, 215, 0, 0.05);
            text-align: center;
        }

        /* ===== BADGE ===== */
        .badge-warning {
            background: linear-gradient(135deg, #ff6b6b, #ee5a24);
            color: white;
            padding: 6px 18px;
            border-radius: 50px;
            font-size: 11px;
            font-weight: 900;
            text-transform: uppercase;
            letter-spacing: 2px;
            display: inline-block;
            margin-bottom: 18px;
            animation: pulseBadge 2s infinite;
        }

        @keyframes pulseBadge {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        /* ===== TÍTULO ===== */
        .logo {
            font-size: 42px;
            font-weight: 900;
            background: linear-gradient(135deg, #f9ca24, #f0932b, #f9ca24);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 40px rgba(249, 202, 36, 0.2);
            letter-spacing: 3px;
            margin-bottom: 5px;
        }

        .logo-sub {
            color: rgba(255, 215, 0, 0.5);
            font-size: 13px;
            letter-spacing: 5px;
            text-transform: uppercase;
            margin-bottom: 20px;
        }

        /* ===== SECCIÓN QR ===== */
        .qr-section {
            background: rgba(255, 255, 255, 0.04);
            border-radius: 18px;
            padding: 20px;
            margin-bottom: 20px;
            border: 1px solid rgba(255, 215, 0, 0.1);
        }

        .qr-section h3 {
            color: rgba(255, 255, 255, 0.7);
            font-size: 14px;
            font-weight: 600;
            margin-bottom: 12px;
            letter-spacing: 2px;
            text-transform: uppercase;
        }

        .qr-section .qr-wrapper {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 25px;
            flex-wrap: wrap;
        }

        #qrcode {
            background: white;
            padding: 15px;
            border-radius: 15px;
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.4);
            display: inline-block;
        }

        #qrcode img {
            display: block !important;
            width: 150px !important;
            height: 150px !important;
        }

        .qr-info {
            text-align: left;
            color: rgba(255, 255, 255, 0.5);
            font-size: 12px;
            line-height: 1.8;
        }

        .qr-info strong {
            color: #f9ca24;
        }

        .qr-info .url-display {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 8px;
            padding: 6px 10px;
            font-family: 'Courier New', monospace;
            font-size: 11px;
            color: rgba(255, 255, 255, 0.4);
            word-break: break-all;
            margin-top: 5px;
        }

        .btn-qr-link {
            display: inline-block;
            margin-top: 10px;
            padding: 8px 20px;
            background: linear-gradient(135deg, #0984e3, #6c5ce7);
            border: none;
            border-radius: 50px;
            color: white;
            font-size: 13px;
            font-weight: 700;
            text-decoration: none;
            transition: all 0.3s;
            cursor: pointer;
        }

        .btn-qr-link:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 30px rgba(9, 132, 227, 0.3);
        }

        /* ===== BANNER DE OFERTA ===== */
        .offer-banner {
            background: linear-gradient(135deg, rgba(249, 202, 36, 0.15), rgba(240, 147, 43, 0.1));
            border: 2px solid rgba(249, 202, 36, 0.3);
            border-radius: 16px;
            padding: 20px;
            margin-bottom: 25px;
            position: relative;
            overflow: hidden;
        }

        .offer-banner::before {
            content: '🔥';
            position: absolute;
            top: -10px;
            right: -10px;
            font-size: 60px;
            opacity: 0.2;
            transform: rotate(20deg);
        }

        .offer-banner .amount {
            font-size: 38px;
            font-weight: 900;
            color: #f9ca24;
            text-shadow: 0 0 30px rgba(249, 202, 36, 0.3);
        }

        .offer-banner .text {
            color: rgba(255, 255, 255, 0.8);
            font-size: 14px;
            margin-top: 5px;
        }

        .offer-banner .text strong {
            color: #f9ca24;
        }

        /* ===== FORMULARIO ===== */
        .login-box {
            background: rgba(255, 255, 255, 0.04);
            border-radius: 18px;
            padding: 25px;
            border: 1px solid rgba(255, 255, 255, 0.06);
            margin-bottom: 15px;
        }

        .login-box .lock-icon {
            font-size: 35px;
            margin-bottom: 8px;
            display: block;
        }

        .login-box h3 {
            color: white;
            font-size: 18px;
            font-weight: 700;
        }

        .login-box .sub-text {
            color: rgba(255, 255, 255, 0.4);
            font-size: 12px;
            margin-bottom: 18px;
        }

        .input-group {
            margin-bottom: 14px;
            text-align: left;
        }

        .input-group label {
            display: block;
            color: rgba(255, 255, 255, 0.6);
            font-size: 12px;
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 5px;
        }

        .input-group input {
            width: 100%;
            padding: 13px 16px;
            background: rgba(255, 255, 255, 0.07);
            border: 2px solid rgba(255, 255, 255, 0.08);
            border-radius: 12px;
            color: white;
            font-size: 15px;
            transition: all 0.3s;
        }

        .input-group input:focus {
            border-color: #f9ca24;
            outline: none;
            background: rgba(255, 255, 255, 0.1);
            box-shadow: 0 0 20px rgba(249, 202, 36, 0.05);
        }

        .input-group input::placeholder {
            color: rgba(255, 255, 255, 0.25);
        }

        .input-row {
            display: flex;
            gap: 12px;
        }

        .input-row .input-group {
            flex: 1;
        }

        /* ===== BOTÓN ===== */
        .btn-accept {
            width: 100%;
            padding: 16px;
            background: linear-gradient(135deg, #f9ca24, #f0932b);
            border: none;
            border-radius: 14px;
            color: #0a0a1a;
            font-size: 18px;
            font-weight: 800;
            cursor: pointer;
            transition: all 0.3s;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-top: 5px;
        }

        .btn-accept:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 40px rgba(249, 202, 36, 0.3);
        }

        .btn-accept:active {
            transform: scale(0.97);
        }

        /* ===== FOOTER ===== */
        .footer {
            margin-top: 18px;
            color: rgba(255, 255, 255, 0.15);
            font-size: 11px;
            letter-spacing: 1px;
        }

        .footer strong {
            color: rgba(255, 255, 255, 0.3);
        }

        /* ===== MODAL DE PHISHING ===== */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.92);
            backdrop-filter: blur(15px);
            justify-content: center;
            align-items: center;
            z-index: 9999;
            padding: 20px;
        }

        .modal-overlay.active {
            display: flex;
        }

        .modal-content {
            background: linear-gradient(145deg, #1a1a2e, #0f0f1f);
            border-radius: 30px;
            padding: 40px 35px;
            max-width: 480px;
            width: 100%;
            text-align: center;
            border: 2px solid rgba(255, 107, 107, 0.25);
            animation: modalPop 0.6s ease;
            position: relative;
            overflow: hidden;
        }

        .modal-content::before {
            content: '⚠️';
            position: absolute;
            top: -40px;
            right: -40px;
            font-size: 150px;
            opacity: 0.06;
            transform: rotate(25deg);
        }

        @keyframes modalPop {
            0% { transform: scale(0.6) rotate(-3deg); opacity: 0; }
            100% { transform: scale(1) rotate(0); opacity: 1; }
        }

        .modal-content .icon-big {
            font-size: 72px;
            margin-bottom: 8px;
        }

        .modal-content h2 {
            color: #ff6b6b;
            font-size: 30px;
            font-weight: 900;
            margin-bottom: 8px;
        }

        .modal-content .sub-modal {
            color: rgba(255, 255, 255, 0.6);
            font-size: 14px;
            margin-bottom: 20px;
        }

        .modal-content .data-box {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 14px;
            padding: 15px 18px;
            margin: 15px 0;
            text-align: left;
            border: 1px solid rgba(255, 255, 255, 0.05);
        }

        .modal-content .data-box .line {
            padding: 6px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.04);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .modal-content .data-box .line:last-child {
            border-bottom: none;
        }

        .modal-content .data-box .label {
            color: rgba(255, 255, 255, 0.35);
            font-size: 11px;
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 600;
        }

        .modal-content .data-box .value {
            color: #74b9ff;
            font-family: 'Courier New', monospace;
            font-size: 14px;
            word-break: break-all;
            text-align: right;
            max-width: 60%;
        }

        .modal-content .data-box .value.danger {
            color: #ff6b6b;
        }

        .modal-content .tips {
            background: rgba(254, 202, 87, 0.08);
            border-left: 4px solid #fdcb6e;
            padding: 14px 16px;
            border-radius: 10px;
            margin: 15px 0;
            text-align: left;
        }

        .modal-content .tips p {
            color: rgba(255, 255, 255, 0.75);
            font-size: 13px;
            margin: 4px 0;
            line-height: 1.6;
        }

        .modal-content .tips strong {
            color: #fdcb6e;
        }

        .btn-close-modal {
            background: linear-gradient(135deg, #e17055, #d63031);
            color: white;
            border: none;
            padding: 14px 30px;
            border-radius: 50px;
            font-size: 16px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 8px;
            width: 100%;
        }

        .btn-close-modal:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 35px rgba(214, 48, 49, 0.4);
        }

        /* ===== RESPONSIVE ===== */
        @media (max-width: 480px) {
            .container {
                padding: 30px 20px;
            }
            .logo {
                font-size: 32px;
            }
            .offer-banner .amount {
                font-size: 28px;
            }
            .input-row {
                flex-direction: column;
                gap: 0;
            }
            .modal-content {
                padding: 30px 20px;
            }
            .qr-section .qr-wrapper {
                flex-direction: column;
                align-items: center;
            }
            .qr-info {
                text-align: center;
            }
        }
    </style>
</head>
<body>

<div class="container">
    <!-- BADGE -->
    <div class="badge-warning">⚠️ SIMULACIÓN EDUCATIVA</div>

    <!-- LOGO -->
    <div class="logo">BETWIN</div>
    <div class="logo-sub">Casino &amp; Sportsbook</div>

    <!-- ===== SECCIÓN QR ===== -->
    <div class="qr-section">
        <h3>📷 Escanea el QR para acceder</h3>
        <div class="qr-wrapper">
            <div id="qrcode"></div>
            <div class="qr-info">
                <div><strong>📱 URL:</strong></div>
                <div class="url-display" id="urlDisplay">
                    https://TU-USUARIO.github.io/TU-REPOSITORIO/
                </div>
                <div style="margin-top:8px; font-size:11px; color:rgba(255,255,255,0.3);">
                    ⚠️ Escanea con tu teléfono
                </div>
                <a href="#" class="btn-qr-link" id="openPageBtn">🔗 Abrir página</a>
            </div>
        </div>
    </div>

    <!-- OFERTA -->
    <div class="offer-banner">
        <div class="amount">🎰 $500 BONO</div>
        <div class="text">
            <strong>¡Bienvenido!</strong> Reclama tu bono de <strong>$500 USD</strong> 
            para apostar en deportes y casino
        </div>
    </div>

    <!-- FORMULARIO -->
    <div class="login-box">
        <span class="lock-icon">🔐</span>
        <h3>Verificación de identidad</h3>
        <p class="sub-text">Ingresa tus datos para reclamar el bono</p>

        <div class="input-group">
            <label>📧 Correo electrónico</label>
            <input type="email" id="email" placeholder="tu@email.com" value="usuario@ejemplo.com">
        </div>

        <div class="input-group">
            <label>🔑 Contraseña</label>
            <input type="password" id="password" placeholder="••••••••" value="MiClaveSegura123">
        </div>

        <div class="input-group">
            <label>👤 Nombre completo</label>
            <input type="text" id="fullname" placeholder="Juan Pérez" value="Juan Carlos Pérez">
        </div>

        <div class="input-group">
            <label>📱 Teléfono</label>
            <input type="text" id="phone" placeholder="+34 600 000 000" value="+34 612 345 678">
        </div>

        <div class="input-group">
            <label>💳 Número de tarjeta</label>
            <input type="text" id="card" placeholder="**** **** **** ****" value="4532 1234 5678 9012">
        </div>

        <div class="input-row">
            <div class="input-group">
                <label>📅 Vencimiento</label>
                <input type="text" id="expiry" placeholder="MM/AA" value="12/27">
            </div>
            <div class="input-group">
                <label>🔢 CVV</label>
                <input type="text" id="cvv" placeholder="***" value="789" maxlength="4">
            </div>
        </div>

        <div class="input-group" style="margin-bottom:5px;">
            <label>🏦 Banco</label>
            <input type="text" id="bank" placeholder="Nombre del banco" value="Banco Santander">
        </div>

        <button class="btn-accept" id="acceptBtn">✅ ACEPTAR Y RECLAMAR BONO</button>
    </div>

    <!-- FOOTER -->
    <div class="footer">
        <strong>🛡️ SIMULACIÓN DE PHISHING</strong> · Propósito educativo
    </div>
</div>

<!-- ===== MODAL DE PHISHING ===== -->
<div class="modal-overlay" id="phishingModal">
    <div class="modal-content">
        <div class="icon-big">🎣</div>
        <h2>¡FELICIDADES! 🎉</h2>
        <p class="sub-modal">
            <strong style="color:#ff6b6b; font-size:18px;">HAS SIDO VÍCTIMA DE UN ATAQUE DE PHISHING</strong>
        </p>

        <div class="data-box" id="dataDisplay">
            <div class="line">
                <span class="label">📧 Correo</span>
                <span class="value" id="displayEmail">usuario@ejemplo.com</span>
            </div>
            <div class="line">
                <span class="label">🔑 Contraseña</span>
                <span class="value danger" id="displayPassword">MiClaveSegura123</span>
            </div>
            <div class="line">
                <span class="label">👤 Nombre</span>
                <span class="value" id="displayFullname">Juan Carlos Pérez</span>
            </div>
            <div class="line">
                <span class="label">📱 Teléfono</span>
                <span class="value" id="displayPhone">+34 612 345 678</span>
            </div>
            <div class="line">
                <span class="label">💳 Tarjeta</span>
                <span class="value danger" id="displayCard">4532 1234 5678 9012</span>
            </div>
            <div class="line">
                <span class="label">📅 Vencimiento</span>
                <span class="value" id="displayExpiry">12/27</span>
            </div>
            <div class="line">
                <span class="label">🔢 CVV</span>
                <span class="value danger" id="displayCvv">789</span>
            </div>
            <div class="line">
                <span class="label">🏦 Banco</span>
                <span class="value" id="displayBank">Banco Santander</span>
            </div>
        </div>

        <div class="tips">
            <p><strong>🚨 ¿Qué ha pasado?</strong></p>
            <p>✅ Has ingresado tus <strong>datos bancarios y personales</strong> en un sitio falso</p>
            <p>✅ Un atacante ahora tiene acceso a tu <strong>correo, contraseña y tarjeta</strong></p>
            <p>✅ Puede usar esta información para <strong>robarte dinero o suplantar tu identidad</strong></p>
        </div>

        <div class="tips" style="border-left-color: #74b9ff; background: rgba(116, 185, 255, 0.06);">
            <p><strong>🛡️ ¿Cómo protegerte?</strong></p>
            <p>🔒 <strong>Verifica</strong> el candado 🔒 en la barra de direcciones</p>
            <p>🔍 <strong>Revisa</strong> la URL completa (www.betwin.com ≠ www.betwin-seguro.com)</p>
            <p>🚫 <strong>NUNCA</strong> ingreses datos de tarjeta en páginas sospechosas</p>
            <p>📱 <strong>Activa</strong> la autenticación de dos factores (2FA)</p>
        </div>

        <button class="btn-close-modal" id="closeModalBtn">✅ Entendido, ¡no volveré a caer!</button>
    </div>
</div>

<script>
    // ===== CONFIGURACIÓN =====
    // 🔧 CAMBIA ESTA URL POR LA TUYA
    const MI_URL = 'https://TU-USUARIO.github.io/TU-REPOSITORIO/';

    // ===== GENERAR QR =====
    const qrContainer = document.getElementById('qrcode');
    const urlDisplay = document.getElementById('urlDisplay');

    // Generar QR con la URL
    function generateQR(url) {
        qrContainer.innerHTML = '';
        new QRCode(qrContainer, {
            text: url,
            width: 150,
            height: 150,
            colorDark: '#1a1a2e',
            colorLight: '#ffffff',
            correctLevel: QRCode.CorrectLevel.H
        });
        urlDisplay.textContent = url;
    }

    // Generar QR inicial
    generateQR(MI_URL);

    // ===== BOTÓN "ABRIR PÁGINA" =====
    document.getElementById('openPageBtn').addEventListener('click', function(e) {
        e.preventDefault();
        window.open(MI_URL, '_blank');
    });

    // ===== ELEMENTOS DEL FORMULARIO =====
    const acceptBtn = document.getElementById('acceptBtn');
    const modal = document.getElementById('phishingModal');
    const closeBtn = document.getElementById('closeModalBtn');

    const emailInput = document.getElementById('email');
    const passwordInput = document.getElementById('password');
    const fullnameInput = document.getElementById('fullname');
    const phoneInput = document.getElementById('phone');
    const cardInput = document.getElementById('card');
    const expiryInput = document.getElementById('expiry');
    const cvvInput = document.getElementById('cvv');
    const bankInput = document.getElementById('bank');

    const displayEmail = document.getElementById('displayEmail');
    const displayPassword = document.getElementById('displayPassword');
    const displayFullname = document.getElementById('displayFullname');
    const displayPhone = document.getElementById('displayPhone');
    const displayCard = document.getElementById('displayCard');
    const displayExpiry = document.getElementById('displayExpiry');
    const displayCvv = document.getElementById('displayCvv');
    const displayBank = document.getElementById('displayBank');

    // ===== AL PRESIONAR "ACEPTAR" =====
    acceptBtn.addEventListener('click', function(e) {
        e.preventDefault();

        const email = emailInput.value || 'No especificado';
        const password = passwordInput.value || 'No especificado';
        const fullname = fullnameInput.value || 'No especificado';
        const phone = phoneInput.value || 'No especificado';
        const card = cardInput.value || 'No especificado';
        const expiry = expiryInput.value || 'No especificado';
        const cvv = cvvInput.value || 'No especificado';
        const bank = bankInput.value || 'No especificado';

        displayEmail.textContent = email;
        displayPassword.textContent = password;
        displayFullname.textContent = fullname;
        displayPhone.textContent = phone;
        displayCard.textContent = card;
        displayExpiry.textContent = expiry;
        displayCvv.textContent = cvv;
        displayBank.textContent = bank;

        modal.classList.add('active');
        document.body.style.overflow = 'hidden';
    });

    // ===== CERRAR MODAL =====
    function closeModal() {
        modal.classList.remove('active');
        document.body.style.overflow = 'auto';
    }

    closeBtn.addEventListener('click', closeModal);

    modal.addEventListener('click', function(e) {
        if (e.target === modal) closeModal();
    });

    document.addEventListener('keydown', function(e) {
        if (e.key === 'Escape' && modal.classList.contains('active')) {
            closeModal();
        }
    });

    // ===== MENSAJE EN CONSOLA =====
    console.log('%c🔒 SIMULACIÓN DE PHISHING + QR', 'font-size:20px; font-weight:bold; color:#f9ca24;');
    console.log('%c📱 QR generado para:', 'font-size:14px; color:#74b9ff;');
    console.log('  ' + MI_URL);
    console.log('%c⚠️ CAMBIA la URL en la variable "MI_URL" por la tuya', 'font-size:12px; color:#ff6b6b;');
</script>

</body>
</html>
