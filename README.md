<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadena Trófica del Agroecosistema de Café</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @keyframes pulse-glow {
            0%, 100% { box-shadow: 0 0 20px rgba(255, 193, 7, 0.6); }
            50% { box-shadow: 0 0 40px rgba(255, 193, 7, 0.9); }
        }
        
        @keyframes flow {
            0% { transform: translateX(-10px); opacity: 0; }
            50% { opacity: 1; }
            100% { transform: translateX(10px); opacity: 0; }
        }
        
        .energy-flow {
            animation: flow 2s infinite;
        }
        
        .sun-glow {
            animation: pulse-glow 3s infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .floating {
            animation: float 3s ease-in-out infinite;
        }
    </style>
</head>
<body class="bg-gradient-to-b from-sky-200 via-green-100 to-green-200 min-h-screen p-6">
    <div class="max-w-6xl mx-auto">
        <!-- Título -->
        <div class="text-center mb-8">
            <h1 class="text-4xl font-bold text-green-800 mb-2">Cadena Trófica del Agroecosistema de Café</h1>
            <p class="text-lg text-green-600">Flujo de energía desde el sol hasta los predadores</p>
        </div>

        <!-- Cadena Trófica -->
        <div class="flex flex-col lg:flex-row items-center justify-center space-y-8 lg:space-y-0 lg:space-x-8 mb-8">
            
            <!-- 1. Energía Solar -->
            <div class="flex flex-col items-center group cursor-pointer" onclick="showInfo('sol')">
                <div class="w-24 h-24 bg-yellow-400 rounded-full sun-glow flex items-center justify-center text-4xl mb-4 transition-transform hover:scale-110">
                    ☀️
                </div>
                <div class="bg-white rounded-lg p-4 shadow-lg text-center max-w-xs">
                    <h3 class="font-bold text-yellow-600 mb-2">ENERGÍA SOLAR</h3>
                    <p class="text-sm text-gray-700">Fuente primaria de toda la energía del ecosistema</p>
                </div>
            </div>

            <!-- Flecha 1 -->
            <div class="flex items-center">
                <div class="text-3xl text-green-600 energy-flow">→</div>
            </div>

            <!-- 2. Plantas de Café (Productores) -->
            <div class="flex flex-col items-center group cursor-pointer floating" onclick="showInfo('cafe')">
                <div class="w-24 h-24 bg-green-500 rounded-lg flex items-center justify-center text-4xl mb-4 transition-transform hover:scale-110">
                    🌱
                </div>
                <div class="bg-white rounded-lg p-4 shadow-lg text-center max-w-xs">
                    <h3 class="font-bold text-green-600 mb-2">PLANTAS DE CAFÉ</h3>
                    <p class="text-sm text-gray-700"><strong>Productores</strong><br>Convierten energía solar en biomasa</p>
                </div>
            </div>

            <!-- Flecha 2 -->
            <div class="flex items-center">
                <div class="text-3xl text-green-600 energy-flow" style="animation-delay: 0.5s;">→</div>
            </div>

            <!-- 3. Broca del Café (Consumidor Primario) -->
            <div class="flex flex-col items-center group cursor-pointer" onclick="showInfo('broca')">
                <div class="w-24 h-24 bg-amber-600 rounded-lg flex items-center justify-center text-4xl mb-4 transition-transform hover:scale-110">
                    🐛
                </div>
                <div class="bg-white rounded-lg p-4 shadow-lg text-center max-w-xs">
                    <h3 class="font-bold text-amber-600 mb-2">BROCA DEL CAFÉ</h3>
                    <p class="text-sm text-gray-700"><strong>Consumidor Primario</strong><br>Herbívoro que se alimenta del café</p>
                </div>
            </div>

            <!-- Flecha 3 -->
            <div class="flex items-center">
                <div class="text-3xl text-green-600 energy-flow" style="animation-delay: 1s;">→</div>
            </div>

            <!-- 4. Moscas Parasitoides (Consumidor Secundario) -->
            <div class="flex flex-col items-center group cursor-pointer floating" onclick="showInfo('moscas')">
                <div class="w-24 h-24 bg-purple-500 rounded-lg flex items-center justify-center text-4xl mb-4 transition-transform hover:scale-110">
                    🪰
                </div>
                <div class="bg-white rounded-lg p-4 shadow-lg text-center max-w-xs">
                    <h3 class="font-bold text-purple-600 mb-2">MOSCAS PARASITOIDES</h3>
                    <p class="text-sm text-gray-700"><strong>Consumidor Secundario</strong><br>Parásitos de la broca</p>
                </div>
            </div>

            <!-- Flecha 4 -->
            <div class="flex items-center">
                <div class="text-3xl text-green-600 energy-flow" style="animation-delay: 1.5s;">→</div>
            </div>

            <!-- 5. Aves Insectívoras (Consumidor Terciario) -->
            <div class="flex flex-col items-center group cursor-pointer" onclick="showInfo('aves')">
                <div class="w-24 h-24 bg-blue-500 rounded-lg flex items-center justify-center text-4xl mb-4 transition-transform hover:scale-110">
                    🐦
                </div>
                <div class="bg-white rounded-lg p-4 shadow-lg text-center max-w-xs">
                    <h3 class="font-bold text-blue-600 mb-2">AVES INSECTÍVORAS</h3>
                    <p class="text-sm text-gray-700"><strong>Consumidor Terciario</strong><br>Predadores de insectos</p>
                </div>
            </div>
        </div>

        <!-- Panel de Información Detallada -->
        <div id="info-panel" class="bg-white rounded-xl shadow-xl p-6 mb-8 hidden">
            <div id="info-content"></div>
            <button onclick="closeInfo()" class="mt-4 bg-green-600 text-white px-4 py-2 rounded-lg hover:bg-green-700 transition-colors">
                Cerrar
            </button>
        </div>

        <!-- Niveles Tróficos -->
        <div class="bg-white rounded-xl shadow-lg p-6 mb-8">
            <h2 class="text-2xl font-bold text-green-800 mb-4 text-center">Niveles Tróficos</h2>
            <div class="grid grid-cols-1 md:grid-cols-4 gap-4">
                <div class="bg-yellow-50 p-4 rounded-lg border-l-4 border-yellow-400">
                    <h3 class="font-bold text-yellow-600">Nivel 0</h3>
                    <p class="text-sm">Energía Solar</p>
                </div>
                <div class="bg-green-50 p-4 rounded-lg border-l-4 border-green-400">
                    <h3 class="font-bold text-green-600">Nivel 1</h3>
                    <p class="text-sm">Productores (Plantas)</p>
                </div>
                <div class="bg-amber-50 p-4 rounded-lg border-l-4 border-amber-400">
                    <h3 class="font-bold text-amber-600">Nivel 2</h3>
                    <p class="text-sm">Consumidores Primarios</p>
                </div>
                <div class="bg-purple-50 p-4 rounded-lg border-l-4 border-purple-400">
                    <h3 class="font-bold text-purple-600">Nivel 3</h3>
                    <p class="text-sm">Consumidores Secundarios</p>
                </div>
            </div>
            <div class="mt-4">
                <div class="bg-blue-50 p-4 rounded-lg border-l-4 border-blue-400 max-w-md mx-auto">
                    <h3 class="font-bold text-blue-600">Nivel 4</h3>
                    <p class="text-sm">Consumidores Terciarios (Predadores)</p>
                </div>
            </div>
        </div>

        <!-- Flujo de Energía -->
        <div class="bg-gradient-to-r from-yellow-100 to-blue-100 rounded-xl shadow-lg p-6">
            <h2 class="text-2xl font-bold text-green-800 mb-4 text-center">Flujo de Energía</h2>
            <div class="text-center">
                <p class="text-lg mb-4">La energía fluye en una sola dirección a través de la cadena trófica:</p>
                <div class="bg-white rounded-lg p-4 inline-block shadow-md">
                    <span class="text-yellow-600 font-bold">100% Energía Solar</span>
                    <span class="mx-2">→</span>
                    <span class="text-green-600 font-bold">~1% Plantas</span>
                    <span class="mx-2">→</span>
                    <span class="text-amber-600 font-bold">~10% Herbívoros</span>
                    <span class="mx-2">→</span>
                    <span class="text-purple-600 font-bold">~10% Parásitos</span>
                    <span class="mx-2">→</span>
                    <span class="text-blue-600 font-bold">~10% Predadores</span>
                </div>
                <p class="text-sm text-gray-600 mt-4">Solo el 10% de la energía se transfiere entre niveles tróficos</p>
            </div>
        </div>
    </div>

    <script>
        const infoData = {
            sol: {
                title: "Energía Solar",
                content: `
                    <h3 class="text-2xl font-bold text-yellow-600 mb-4">☀️ Energía Solar</h3>
                    <p class="mb-4">La energía solar es la fuente primaria de toda la energía en el ecosistema del café. El sol proporciona la energía necesaria para que las plantas realicen la fotosíntesis.</p>
                    <div class="bg-yellow-50 p-4 rounded-lg">
                        <h4 class="font-bold mb-2">Características:</h4>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Fuente renovable e inagotable</li>
                            <li>Proporciona aproximadamente 1,000 W/m² en condiciones óptimas</li>
                            <li>Solo el 1-3% se convierte en biomasa vegetal</li>
                            <li>Esencial para la fotosíntesis</li>
                        </ul>
                    </div>
                `
            },
            cafe: {
                title: "Plantas de Café",
                content: `
                    <h3 class="text-2xl font-bold text-green-600 mb-4">🌱 Plantas de Café (Productores)</h3>
                    <p class="mb-4">Las plantas de café son los productores primarios del ecosistema. Convierten la energía solar en energía química mediante la fotosíntesis, creando la base de toda la cadena alimentaria.</p>
                    <div class="bg-green-50 p-4 rounded-lg">
                        <h4 class="font-bold mb-2">Función Ecológica:</h4>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Realizan fotosíntesis: CO₂ + H₂O + luz solar → glucosa + O₂</li>
                            <li>Producen biomasa (hojas, tallos, frutos)</li>
                            <li>Proporcionan hábitat para otros organismos</li>
                            <li>Base de la cadena trófica</li>
                        </ul>
                    </div>
                `
            },
            broca: {
                title: "Broca del Café",
                content: `
                    <h3 class="text-2xl font-bold text-amber-600 mb-4">🐛 Broca del Café (Consumidor Primario)</h3>
                    <p class="mb-4">La broca del café (Hypothenemus hampei) es un pequeño escarabajo que se alimenta directamente de los granos de café, siendo el principal herbívoro de este agroecosistema.</p>
                    <div class="bg-amber-50 p-4 rounded-lg">
                        <h4 class="font-bold mb-2">Características:</h4>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Consumidor primario (herbívoro)</li>
                            <li>Se alimenta del endospermo del grano de café</li>
                            <li>Causa importantes pérdidas económicas</li>
                            <li>Completa su ciclo de vida dentro del grano</li>
                            <li>Principal plaga del cultivo de café</li>
                        </ul>
                    </div>
                `
            },
            moscas: {
                title: "Moscas Parasitoides",
                content: `
                    <h3 class="text-2xl font-bold text-purple-600 mb-4">🪰 Moscas Parasitoides (Consumidor Secundario)</h3>
                    <p class="mb-4">Las moscas parasitoides son insectos que actúan como control biológico natural de la broca del café. Sus larvas se desarrollan dentro o sobre la broca, eventualmente matándola.</p>
                    <div class="bg-purple-50 p-4 rounded-lg">
                        <h4 class="font-bold mb-2">Función Ecológica:</h4>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Consumidor secundario (parásito)</li>
                            <li>Control biológico natural de la broca</li>
                            <li>Las hembras depositan huevos en/sobre la broca</li>
                            <li>Las larvas se alimentan de la broca hospedadora</li>
                            <li>Importantes para el manejo integrado de plagas</li>
                        </ul>
                    </div>
                `
            },
            aves: {
                title: "Aves Insectívoras",
                content: `
                    <h3 class="text-2xl font-bold text-blue-600 mb-4">🐦 Aves Insectívoras (Consumidor Terciario)</h3>
                    <p class="mb-4">Las aves insectívoras son los predadores tope en esta cadena trófica. Se alimentan de diversos insectos, incluyendo las moscas parasitoides, ayudando a mantener el equilibrio del ecosistema.</p>
                    <div class="bg-blue-50 p-4 rounded-lg">
                        <h4 class="font-bold mb-2">Rol Ecológico:</h4>
                        <ul class="list-disc list-inside space-y-1">
                            <li>Consumidor terciario (predador)</li>
                            <li>Control natural de poblaciones de insectos</li>
                            <li>Mantienen el equilibrio del ecosistema</li>
                            <li>Dispersan semillas de otras plantas</li>
                            <li>Indicadores de la salud del ecosistema</li>
                        </ul>
                    </div>
                `
            }
        };

        function showInfo(organism) {
            const panel = document.getElementById('info-panel');
            const content = document.getElementById('info-content');
            
            content.innerHTML = infoData[organism].content;
            panel.classList.remove('hidden');
            panel.scrollIntoView({ behavior: 'smooth' });
        }

        function closeInfo() {
            document.getElementById('info-panel').classList.add('hidden');
        }

        // Agregar efecto de hover a las flechas
        document.addEventListener('DOMContentLoaded', function() {
            const arrows = document.querySelectorAll('.energy-flow');
            arrows.forEach(arrow => {
                arrow.addEventListener('mouseenter', function() {
                    this.style.animationDuration = '0.5s';
                });
                arrow.addEventListener('mouseleave', function() {
                    this.style.animationDuration = '2s';
                });
            });
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'97810de1162a0ce3',t:'MTc1NjY5MDc3MC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

