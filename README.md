# lukano21.github.io
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>USACH Support</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        body {
            background-color: #f0e6ff;
        }

        .container {
            max-width: 100%;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .login-container, .menu-container, .support-container, .report-container {
            width: 100%;
            max-width: 400px;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            margin: 20px auto;
            display: none;
        }

        .active {
            display: block;
        }

        .icon {
            width: 60px;
            height: 60px;
            background: #6b46c1;
            border-radius: 50%;
            margin: 20px auto;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .input-field {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 2px solid #6b46c1;
            border-radius: 5px;
            outline: none;
        }

        .button {
            width: 100%;
            padding: 12px;
            background: #6b46c1;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin: 10px 0;
        }

        .menu-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 20px;
        }

        .menu-item {
            background: #6b46c1;
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            cursor: pointer;
        }

        .back-button {
            background: #4a5568;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 20px;
        }

        .map-container {
            width: 100%;
            height: 300px;
            background: #ddd;
            margin: 20px 0;
            border-radius: 10px;
        }

        .support-options {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
            margin-top: 20px;
        }

        .support-option {
            background: #6b46c1;
            color: white;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            cursor: pointer;
        }

        @media (max-width: 768px) {
            .container {
                padding: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Login Section -->
        <div class="login-container active" id="login">
            <div class="icon">👤</div>
            <input type="email" class="input-field" placeholder="Correo electrónico USACH" required>
            <input type="password" class="input-field" placeholder="Contraseña" required>
            <button class="button" onclick="showSection('menu')">Iniciar sesión</button>
        </div>

        <!-- Main Menu Section -->
        <div class="menu-container" id="menu">
            <h2>Menú Principal</h2>
            <div class="menu-grid">
                <div class="menu-item" onclick="showSection('map')">🗺️ Mapa</div>
                <div class="menu-item" onclick="showSection('support')">💬 Apoyo</div>
                <div class="menu-item" onclick="showSection('report')">📝 Reporte</div>
                <div class="menu-item" onclick="showSection('info')">ℹ️ Info</div>
            </div>
        </div>

        <!-- Map Section -->
        <div class="map-container" id="map" style="display: none;">
            <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 20px;">
                <button class="back-button" style="margin: 0;" onclick="showSection('menu')">←</button>
                <h2>Mapa USACH</h2>
            </div>
            
            <div class="map-area">
                <!-- Contenedor del mapa con un fondo morado claro similar al de la imagen -->
                <div class="interactive-map">
                    <img src="/api/placeholder/800/400" alt="Mapa USACH" style="width: 100%; height: auto; object-fit: contain;">
                </div>
                
                <div class="map-legend">
                    <div class="legend-item">
                        <span class="color-box" style="background-color: #4CAF50;"></span>
                        <span>Sector Deportivo</span>
                    </div>
                    <div class="legend-item">
                        <span class="color-box" style="background-color: #FFA726;"></span>
                        <span>Sector A</span>
                    </div>
                    <div class="legend-item">
                        <span class="color-box" style="background-color: #FFD700;"></span>
                        <span>Sector B</span>
                    </div>
                    <div class="legend-item">
                        <span class="color-box" style="background-color: #FF5252;"></span>
                        <span>Sector C</span>
                    </div>
                    <div class="legend-item">
                        <span class="color-box" style="background-color: #8BC34A;"></span>
                        <span>Sector D</span>
                    </div>
                    <div class="legend-item">
                        <span class="color-box" style="background-color: #40C4FF;"></span>
                        <span>Sector E</span>
                    </div>
                    <div class="legend-item">
                        <span class="color-box" style="background-color: #E91E63;"></span>
                        <span>Sector F</span>
                    </div>
                    <div class="legend-item">
                        <span class="color-box" style="background-color: #009688;"></span>
                        <span>Sector G</span>
                    </div>
                </div>
            </div>
        </div>

        <style>
            .map-area {
                background: #f8f4ff;
                padding: 20px;
                border-radius: 10px;
                box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            }

            .interactive-map {
                width: 100%;
                max-width: 800px;
                margin: 0 auto 20px;
                border-radius: 8px;
                overflow: hidden;
            }

            .map-legend {
                display: grid;
                grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
                gap: 10px;
                padding: 15px;
                background: white;
                border-radius: 8px;
            }

            .legend-item {
                display: flex;
                align-items: center;
                gap: 8px;
            }

            .color-box {
                width: 20px;
                height: 20px;
                border-radius: 4px;
            }

            @media (max-width: 768px) {
                .map-legend {
                    grid-template-columns: repeat(2, 1fr);
                }
            }
        </style>

        <!-- Support Section -->
        <div class="support-container" id="support">
            <h2>Apoyo</h2>
            <div class="support-options">
                <div class="support-option" onclick="showSection('emergency-contacts')">📞 Llamada telefónica</div>
                <div class="support-option" onclick="showSection('chat')">💭 Chat en línea</div>
                <div class="support-option" onclick="showSection('clinics')">📅 Agendar cita</div>
            </div>
            <button class="back-button" onclick="showSection('menu')">Volver al menú</button>
        </div>

        <!-- Emergency Contacts Section -->
        <div class="support-container" id="emergency-contacts" style="display: none;">
            <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 20px;">
                <button class="back-button" style="margin: 0;" onclick="showSection('support')">←</button>
                <h2>Contactos de Emergencia</h2>
            </div>
            
            <div class="contact-list">
                <div class="contact-card">
                    <div>
                        <div class="contact-name">Juan Pérez</div>
                        <div class="contact-phone">+56 9 1234 5678</div>
                    </div>
                    <button class="call-button">Llamar</button>
                </div>
            </div>
            
            <button class="button" style="margin-top: 20px;">Agregar Contacto</button>
        </div>

        <!-- Chat Section -->
        <div class="support-container" id="chat" style="display: none;">
            <div style="display: flex; justify-content: space-between; align-items: center; background: #6b46c1; padding: 15px; color: white; border-radius: 10px 10px 0 0;">
                <button class="back-button" style="margin: 0;" onclick="showSection('support')">←</button>
                <h2 style="margin: 0;">Siddal</h2>
                <div style="width: 30px;"></div>
            </div>
            
            <div class="chat-messages" style="height: 400px; background: #f8f4ff; padding: 15px; overflow-y: auto;">
                <!-- Messages will appear here -->
            </div>
            
            <div style="display: flex; gap: 10px; padding: 15px; background: white; border-radius: 0 0 10px 10px;">
                <input type="text" class="input-field" style="margin: 0;" placeholder="Escribe un mensaje...">
                <button class="button" style="width: auto; margin: 0; padding: 12px 20px;">Enviar</button>
            </div>
        </div>

        <!-- Clinics Section -->
        <div class="support-container" id="clinics" style="display: none;">
            <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 20px;">
                <button class="back-button" style="margin: 0;" onclick="showSection('support')">←</button>
                <h2>Clínicas en la Región Metropolitana</h2>
            </div>
            
            <div class="clinics-list">
                <a href="https://www.alemana.cl" target="_blank" class="clinic-card">
                    <h3>Clínica Alemana</h3>
                    <p>Av. Vitacura 5951, Vitacura</p>
                </a>
                
                <a href="https://www.clinicalascondes.cl" target="_blank" class="clinic-card">
                    <h3>Clínica Las Condes</h3>
                    <p>Estoril 450, Las Condes</p>
                </a>
                
                <a href="https://www.clinicasantamaria.cl" target="_blank" class="clinic-card">
                    <h3>Clínica Santa María</h3>
                    <p>Av. Santa María 0500, Providencia</p>
                </a>
            </div>
        </div>

        <style>
            .contact-card {
                display: flex;
                justify-content: space-between;
                align-items: center;
                padding: 15px;
                background: white;
                border-radius: 8px;
                margin-bottom: 10px;
                box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            }

            .contact-name {
                font-weight: bold;
                margin-bottom: 5px;
            }

            .contact-phone {
                color: #666;
            }

            .call-button {
                background: #4CAF50;
                color: white;
                border: none;
                padding: 8px 16px;
                border-radius: 5px;
                cursor: pointer;
            }

            .clinic-card {
                display: block;
                padding: 15px;
                background: white;
                border-radius: 8px;
                margin-bottom: 10px;
                box-shadow: 0 2px 4px rgba(0,0,0,0.1);
                text-decoration: none;
                color: inherit;
                transition: transform 0.2s;
            }

            .clinic-card:hover {
                transform: translateY(-2px);
            }

            .clinic-card h3 {
                margin: 0 0 5px 0;
                color: #6b46c1;
            }

            .clinic-card p {
                margin: 0;
                color: #666;
            }
        </style>

        <!-- Info Section -->
        <div class="info-container" id="info" style="display: none;">
            <div class="info-content">
                <h2 style="text-align: center; margin-bottom: 30px;">Información</h2>
                
                <div class="info-item">
                    <div class="info-icon" style="background: #E2E8F0;">
                        📁
                    </div>
                    <p class="info-text">
                        Permite registrar y reportar incidentes en un mapa, detallando la ubicación, el rango etario, el cargo de las personas involucradas y el tipo de incidente (acoso, violencia, etc.).
                    </p>
                </div>

                <div class="info-item">
                    <div class="info-icon" style="background: #E2E8F0;">
                        ⚠️
                    </div>
                    <p class="info-text">
                        Permite contactar rápidamente a un ser querido o persona de confianza en caso de emergencia, enviando automáticamente la ubicación y una alerta.
                    </p>
                </div>

                <div class="info-item">
                    <div class="info-icon" style="background: #E2E8F0;">
                        👥
                    </div>
                    <p class="info-text">
                        Ofrece un canal de apoyo psicológico para asesoramiento y orientación en situaciones de crisis, con acceso a profesionales y recursos de bienestar.
                    </p>
                </div>

                <button class="back-button" onclick="showSection('menu')">Volver al menú</button>
            </div>
        </div>

        <style>
            .info-container {
                max-width: 600px;
                margin: 0 auto;
                padding: 20px;
            }
            
            .info-item {
                display: flex;
                align-items: flex-start;
                margin-bottom: 30px;
                background: white;
                padding: 20px;
                border-radius: 10px;
                box-shadow: 0 2px 4px rgba(0,0,0,0.1);
            }
            
            .info-icon {
                width: 50px;
                height: 50px;
                min-width: 50px;
                border-radius: 50%;
                display: flex;
                align-items: center;
                justify-content: center;
                font-size: 24px;
                margin-right: 15px;
            }
            
            .info-text {
                margin: 0;
                line-height: 1.5;
                color: #4A5568;
            }
        </style>

        <!-- Report Section -->
        <div class="report-container" id="report">
            <div style="display: flex; align-items: center; gap: 10px; margin-bottom: 20px;">
                <button class="back-button" style="margin: 0;" onclick="showSection('menu')">←</button>
                <h2>Crear Reporte</h2>
            </div>

            <div class="report-form">
                <div class="form-group">
                    <label>¿Qué edad tiene usted al momento de la situación?</label>
                    <div class="radio-group">
                        <label class="radio-label">
                            <input type="radio" name="age" value="17-21">
                            17 - 21
                        </label>
                        <label class="radio-label">
                            <input type="radio" name="age" value="22-26">
                            22 - 26
                        </label>
                        <label class="radio-label">
                            <input type="radio" name="age" value="mas26">
                            Más de 26
                        </label>
                    </div>
                </div>

                <div class="form-group">
                    <label>¿Qué rango tienen las personas involucradas?</label>
                    <div class="radio-group">
                        <label class="radio-label">
                            <input type="radio" name="role" value="profesor" onchange="toggleOtherRole(false)">
                            Profesor
                        </label>
                        <label class="radio-label">
                            <input type="radio" name="role" value="funcionario" onchange="toggleOtherRole(false)">
                            Funcionario
                        </label>
                        <label class="radio-label">
                            <input type="radio" name="role" value="otros" onchange="toggleOtherRole(true)">
                            Otros
                        </label>
                    </div>
                    <input type="text" id="otherRole" class="input-field" placeholder="Especifique cargo, deje vacío si desconoce" style="display: none;">
                </div>

                <div class="form-group">
                    <label>¿Cuál fue el tipo de incidente/situación ocurrida?</label>
                    <textarea class="input-field" rows="4" placeholder="Describe el incidente..."></textarea>
                </div>

                <button class="button">Enviar Reporte</button>
            </div>
        </div>

        <style>
            .report-form {
                display: flex;
                flex-direction: column;
                gap: 20px;
            }

            .form-group {
                display: flex;
                flex-direction: column;
                gap: 10px;
            }

            .form-group label {
                font-weight: bold;
                color: #2D3748;
            }

            .radio-group {
                display: flex;
                flex-direction: column;
                gap: 8px;
            }

            .radio-label {
                display: flex;
                align-items: center;
                gap: 8px;
                cursor: pointer;
            }

            .radio-label input[type="radio"] {
                width: 18px;
                height: 18px;
                cursor: pointer;
            }
        </style>

        <script>
            function toggleOtherRole(show) {
                const otherRoleInput = document.getElementById('otherRole');
                otherRoleInput.style.display = show ? 'block' : 'none';
                if (!show) {
                    otherRoleInput.value = '';
                }
            }
        </script>
    </div>

    <script>
        function showSection(sectionId) {
            // Hide all sections
            document.querySelectorAll('.login-container, .menu-container, .map-container, .support-container, .report-container, .info-container, #emergency-contacts, #chat, #clinics')
                .forEach(container => container.style.display = 'none');
            
            // Show selected section
            document.getElementById(sectionId).style.display = 'block';
        }
    </script>
</body>
</html>
