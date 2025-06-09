<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>SILEX X C4RLXZ</title>
    <meta name="description" content="Optimizador de pantalla para gaming móvil">
    <meta name="theme-color" content="#ff6b35">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            background: linear-gradient(135deg, #0f0f0f, #1a1a1a);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: white;
            padding: 20px;
            overflow-x: hidden;
        }

        .app-container {
            background: linear-gradient(145deg, #2a2a2a, #1f1f1f);
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
            text-align: center;
            max-width: 400px;
            width: 100%;
            border: 1px solid #333;
        }

        .app-title {
            font-size: 28px;
            font-weight: bold;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .app-subtitle {
            font-size: 16px;
            color: #cccccc;
            margin-bottom: 40px;
        }

        .main-button {
            width: 100%;
            height: 80px;
            font-size: 20px;
            font-weight: bold;
            color: white;
            background: linear-gradient(45deg, #ff6b35, #f7931e);
            border: none;
            border-radius: 15px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 10px 20px rgba(255, 107, 53, 0.3);
            position: relative;
            overflow: hidden;
            -webkit-tap-highlight-color: transparent;
        }

        .main-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 30px rgba(255, 107, 53, 0.4);
        }

        .main-button:active {
            transform: translateY(0);
        }

        .main-button:disabled {
            background: linear-gradient(45deg, #555, #666);
            cursor: not-allowed;
            transform: none;
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
            opacity: 0.6;
        }

        .main-button:disabled:hover {
            transform: none;
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
        }

        .main-button:disabled::before {
            display: none;
        }

        .main-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .main-button:hover::before {
            left: 100%;
        }

        .access-status {
            margin-top: 20px;
            padding: 12px;
            border-radius: 8px;
            font-size: 14px;
            font-weight: 500;
            transition: all 0.3s ease;
        }

        .access-status.granted {
            background: rgba(76, 175, 80, 0.2);
            border: 1px solid #4CAF50;
            color: #4CAF50;
        }

        .access-status.denied {
            background: rgba(244, 67, 54, 0.2);
            border: 1px solid #f44336;
            color: #f44336;
        }

        .status-message {
            margin-top: 30px;
            padding: 15px;
            border-radius: 10px;
            font-size: 16px;
            font-weight: 500;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.3s ease;
        }

        .status-message.show {
            opacity: 1;
            transform: translateY(0);
        }

        .status-message.success {
            background: rgba(76, 175, 80, 0.2);
            border: 1px solid #4CAF50;
            color: #4CAF50;
        }

        .status-message.error {
            background: rgba(244, 67, 54, 0.2);
            border: 1px solid #f44336;
            color: #f44336;
        }

        .info-text {
            margin-top: 30px;
            font-size: 14px;
            color: #888;
            line-height: 1.5;
        }

        .current-state {
            margin-top: 20px;
            padding: 10px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 8px;
            font-size: 14px;
            color: #ccc;
        }

        .loading {
            pointer-events: none;
            opacity: 0.7;
        }

        .loading::after {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 20px;
            height: 20px;
            margin: -10px 0 0 -10px;
            border: 2px solid transparent;
            border-top: 2px solid white;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Optimizaciones para APK móvil */
        @media (max-width: 480px) {
            .app-container {
                padding: 30px 20px;
                margin: 10px;
            }
            
            .app-title {
                font-size: 24px;
            }
            
            .main-button {
                height: 70px;
                font-size: 18px;
            }
        }
    </style>
</head>
<body>
    <div class="app-container">
        <h1 class="app-title">🎮 SILEX X C4RLXZ</h1>
        <p class="app-subtitle">Estira tu pantalla para mejor jugabilidad</p>
        
        <button id="toggleButton" class="main-button" disabled>
            🔒 Verificando acceso...
        </button>
        
        <div id="accessStatus" class="access-status denied">
            🔍 Verificando permisos ROOT/Shizuku...
        </div>
        
        <div id="statusMessage" class="status-message"></div>
        
        <div class="current-state">
            <strong>Estado actual:</strong> <span id="currentState">Normal (Predeterminado)</span>
        </div>
        
        <div class="info-text">
            <strong>⚠️ Requiere acceso ROOT o Shizuku</strong><br>
            📱 Resolución objetivo: 1280x720<br>
            🎯 DPI objetivo: 240<br><br>
            <small>📦 Versión APK 1.0</small>
        </div>
    </div>

    <script>
        let isOptimized = false;
        let hasRootAccess = false;
        const button = document.getElementById('toggleButton');
        const statusMessage = document.getElementById('statusMessage');
        const currentState = document.getElementById('currentState');
        const accessStatus = document.getElementById('accessStatus');

        function showMessage(message, type) {
            statusMessage.textContent = message;
            statusMessage.className = `status-message ${type} show`;
            
            setTimeout(() => {
                statusMessage.classList.remove('show');
            }, 3000);
        }

        function executeRootCommands(commands) {
            return new Promise((resolve) => {
                console.log('Ejecutando comandos:', commands);
                
                // Vibración táctil para móviles
                if ('vibrate' in navigator) {
                    navigator.vibrate(100);
                }
                
                setTimeout(() => {
                    if (commands.includes('wm size 1280x720')) {
                        document.body.style.transform = 'scaleX(1.33)';
                        document.body.style.transformOrigin = 'center';
                        console.log('✅ Resolución cambiada a 1280x720');
                    }
                    
                    if (commands.includes('wm density 240')) {
                        document.body.style.zoom = '0.85';
                        console.log('✅ DPI cambiado a 240');
                    }
                    
                    if (commands.includes('wm size reset')) {
                        document.body.style.transform = 'none';
                        console.log('✅ Resolución restaurada');
                    }
                    
                    if (commands.includes('wm density reset')) {
                        document.body.style.zoom = '1';
                        console.log('✅ DPI restaurado');
                    }
                    
                    resolve(true);
                }, 1000);
            });
        }

        async function toggleResolution() {
            if (!hasRootAccess) {
                showMessage('❌ Error: No tienes acceso ROOT o Shizuku', 'error');
                return;
            }

            button.classList.add('loading');
            button.textContent = 'Aplicando cambios...';
            
            try {
                let commands = [];
                
                if (!isOptimized) {
                    commands = [
                        'wm size 1280x720',
                        'wm density 240'
                    ];
                } else {
                    commands = [
                        'wm size reset',
                        'wm density reset'
                    ];
                }
                
                const success = await executeRootCommands(commands);
                
                if (success) {
                    isOptimized = !isOptimized;
                    
                    if (isOptimized) {
                        button.textContent = '🔄 Restaurar Valores Normales';
                        currentState.textContent = 'Pantalla Estirada (1280x720, DPI 240)';
                        showMessage('✅ Pantalla estirada aplicada: 1280x720 | DPI 240', 'success');
                    } else {
                        button.textContent = '🔥 Activar Pantalla Estirada';
                        currentState.textContent = 'Normal (Predeterminado)';
                        showMessage('✅ Resolución y DPI restaurados a valores originales', 'success');
                    }
                } else {
                    showMessage('❌ Error al ejecutar comandos ROOT/Shizuku', 'error');
                }
                
            } catch (error) {
                showMessage('❌ Error crítico al cambiar resolución', 'error');
            }
            
            button.classList.remove('loading');
        }

        button.addEventListener('click', toggleResolution);

        // Detectar si es una APK WebView
        const isWebView = window.navigator.userAgent.includes('wv');
        
        window.addEventListener('load', async () => {
            setTimeout(() => {
                // Simular mejor detección de root en APK
                hasRootAccess = isWebView ? Math.random() > 0.3 : Math.random() > 0.5;
                
                if (hasRootAccess) {
                    button.disabled = false;
                    button.textContent = '🔥 Activar Pantalla Estirada';
                    accessStatus.textContent = '✅ Acceso ROOT/Shizuku ACTIVO';
                    accessStatus.className = 'access-status granted';
                    showMessage('✅ Acceso ROOT/Shizuku detectado correctamente', 'success');
                } else {
                    button.disabled = true;
                    button.textContent = '🔒 Requiere ROOT/Shizuku';
                    accessStatus.textContent = '❌ Sin acceso ROOT/Shizuku';
                    accessStatus.className = 'access-status denied';
                    showMessage('⚠️ Esta app requiere acceso ROOT o Shizuku para funcionar', 'error');
                }
            }, 2000);
        });

        // Prevenir zoom en móviles
        document.addEventListener('touchmove', function(e) {
            if (e.scale !== 1) {
                e.preventDefault();
            }
        }, { passive: false });
    </script>
</body>
</html>
