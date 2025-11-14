<!DOCTYPE html>
<html lang="es" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Copiermaster C&G Soluciones Digitales S.A</title>

    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- Fuente Inter -->
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap">

    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <!-- Tone.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/tone/14.7.77/Tone.js"></script>

    <!-- YouTube Iframe API -->
    <script src="https://www.youtube.com/iframe_api"></script>

    <style>
        body {
            font-family: 'Inter', sans-serif;
            color: #5a5a5a;
            background-color: #f7f9fc;
        }

        /* Hero Video Styles */
        #hero-video-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
        }
        #hero-video-player {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 120%;
            height: 120%;
            transform: translateX(-50%) translateY(-50%) scale(1.5);
        }

        .hero-button-active {
            background-color: #8ac641;
            color: white;
        }

        /* Chat Widget Styles */
        #chat-widget {
            transition: opacity 0.5s, transform 0.5s;
        }
        #chat-window {
            height: 70vh;
            max-height: 500px;
            width: 90vw;
            max-width: 400px;
            transition: opacity 0.3s ease-in-out, transform 0.3s ease-in-out;
        }

        /* Botón palpitante Páginas Web */
        .pulse-btn {
            animation: pulse 1.2s infinite alternate;
        }
        @keyframes pulse {
            0% {
                transform: scale(1);
                box-shadow: 0 0 0 rgba(132, 204, 22, 0.4);
            }
            100% {
                transform: scale(1.05);
                box-shadow: 0 0 18px rgba(132, 204, 22, 0.85);
            }
        }

        /* Hover card marcas */
        #marcas-display {
            transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
        }
        #marcas-display:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 25px -5px rgb(0 0 0 / 0.1), 0 8px 10px -6px rgb(0 0 0 / 0.1);
        }
    </style>
</head>
<body class="bg-gray-100">

    <!-- NAVBAR -->
    <nav class="bg-white shadow-md fixed w-full z-50">
        <div class="container mx-auto px-6 py-4 flex justify-between items-center">
            <!-- Logo -->
            <a href="index.html" class="flex items-center space-x-3">
                <img src="https://i.postimg.cc/6qRNQd57/468963711-3994290450845859-6671631898219414239-n-removebg-preview.webp"
                     alt="Copiermaster C&G Soluciones Digitales S.A Logo"
                     class="h-24 md:h-32">
            </a>

            <!-- Botón menú móvil -->
            <div class="md:hidden">
                <button id="menu-button" class="text-gray-700 focus:outline-none">
                    <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                              d="M4 6h16M4 12h16m-4 6h4"></path>
                    </svg>
                </button>
            </div>

            <!-- Menú escritorio -->
            <div class="hidden md:flex space-x-6 items-center">
                <a href="index.html" class="text-lime-500 font-semibold transition duration-300">Inicio</a>
                <a href="soluciones.html" class="text-gray-700 hover:text-lime-500 font-semibold transition duration-300">Soluciones</a>
                <a href="nosotros.html" class="text-gray-700 hover:text-lime-500 font-semibold transition duration-300">Nosotros</a>
                <a href="contacto.html" class="text-gray-700 hover:text-lime-500 font-semibold transition duration-300">Contacto</a>

                <a href="soporte.html"
                   class="bg-lime-500 text-white px-6 py-2 rounded-full font-semibold shadow-md hover:bg-lime-600 transition duration-300 transform hover:scale-105">
                    Soporte
                </a>

                <!-- Botón Páginas Web (palpitante) -->
                <a href="https://botandlanding.crisslombeida.com/"
                   target="_blank" rel="noopener noreferrer"
                   class="pulse-btn bg-lime-500 text-white px-6 py-2 rounded-full font-semibold shadow-md hover:bg-lime-600 transition duration-300 transform hover:scale-105">
                    Páginas Web
                </a>
            </div>
        </div>

        <!-- Menú móvil -->
        <div id="mobile-menu" class="hidden md:hidden bg-white shadow-inner">
            <a href="index.html" class="block py-3 px-6 text-lime-500">Inicio</a>
            <a href="soluciones.html" class="block py-3 px-6 text-gray-700 hover:bg-gray-100">Soluciones</a>
            <a href="nosotros.html" class="block py-3 px-6 text-gray-700 hover:bg-gray-100">Nosotros</a>
            <a href="contacto.html" class="block py-3 px-6 text-gray-700 hover:bg-gray-100">Contacto</a>
            <a href="soporte.html" class="block py-3 px-6 text-white bg-lime-500 text-center font-semibold">Soporte</a>
            <a href="https://botandlanding.crisslombeida.com/"
               target="_blank" rel="noopener noreferrer"
               class="block py-3 px-6 text-white bg-lime-500 text-center font-semibold pulse-btn">
               Páginas Web
            </a>
        </div>
    </nav>

    <!-- HERO -->
    <header id="inicio" class="relative text-white overflow-hidden min-h-[80vh] md:min-h-[90vh] flex flex-col justify-end">
        <!-- Video -->
        <div id="hero-video-container">
            <div id="hero-video-player"></div>
        </div>
        <!-- Overlay -->
        <div class="absolute inset-0 bg-black opacity-60"></div>

        <!-- Contenido -->
        <div class="relative container mx-auto px-6 lg:px-8 z-10 pb-16 flex-grow flex items-end">
            <div class="max-w-4xl text-center md:text-left">
                <h1 id="hero-title"
                    class="text-4xl lg:text-5xl xl:text-6xl font-extrabold mb-4 transition-opacity duration-500">
                </h1>
                <p id="hero-subtitle"
                   class="text-lg lg:text-xl font-medium mb-8 text-gray-300 transition-opacity duration-500">
                </p>
                <a href="soluciones.html"
                   class="bg-lime-500 text-white text-lg font-semibold px-10 py-4 rounded-full shadow-lg hover:bg-lime-600 transition duration-300 transform hover:scale-105 inline-block">
                    Conoce Más
                </a>
            </div>
        </div>

        <!-- Botones hero -->
        <div id="hero-buttons" class="relative bg-black bg-opacity-30 p-4 z-10">
            <div class="container mx-auto flex justify-center md:justify-start space-x-2">
                <button data-index="0"
                        class="hero-button text-white px-4 py-2 rounded-lg font-semibold transition duration-300 hover:bg-gray-700">
                    Copiermaster C&G
                </button>
                <button data-index="1"
                        class="hero-button text-white px-4 py-2 rounded-lg font-semibold transition duration-300 hover:bg-gray-700">
                    Marcas
                </button>
                <button data-index="2"
                        class="hero-button text-white px-4 py-2 rounded-lg font-semibold transition duration-300 hover:bg-gray-700">
                    Páginas Web
                </button>
            </div>
        </div>
    </header>

    <!-- SOLUCIONES OUTSOURCING -->
    <section class="py-20 bg-white">
        <div class="container mx-auto px-6">
            <div class="text-center mb-12">
                <h2 class="text-4xl font-bold text-gray-800 mb-4 border-b-4 border-lime-500 inline-block pb-2">
                    Nuestras Soluciones de Outsourcing de Impresión
                </h2>
                <p class="text-lg text-gray-600 mt-4">
                    Diseñamos un ecosistema de impresión a la medida de tus objetivos.
                </p>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="bg-gray-50 p-8 rounded-2xl shadow-lg flex items-start space-x-4">
                    <i data-lucide="printer" class="h-8 w-8 text-lime-500"></i>
                    <div>
                        <h3 class="text-2xl font-bold text-gray-800 mb-2">Gestión de Flota de Impresión</h3>
                        <p class="text-gray-600">
                            Equipos, consumibles, mantenimiento y soporte en un único servicio predecible.
                        </p>
                    </div>
                </div>
                <div class="bg-gray-50 p-8 rounded-2xl shadow-lg flex items-start space-x-4">
                    <i data-lucide="file-scan" class="h-8 w-8 text-lime-500"></i>
                    <div>
                        <h3 class="text-2xl font-bold text-gray-800 mb-2">Digitalización y Gestión Documental</h3>
                        <p class="text-gray-600">
                            Convierta sus archivos en activos digitales seguros, accesibles y fáciles de gestionar.
                        </p>
                    </div>
                </div>
                <div class="bg-gray-50 p-8 rounded-2xl shadow-lg flex items-start space-x-4">
                    <i data-lucide="lock" class="h-8 w-8 text-lime-500"></i>
                    <div>
                        <h3 class="text-2xl font-bold text-gray-800 mb-2">Impresión Segura</h3>
                        <p class="text-gray-600">
                            Proteja su información confidencial con soluciones de autenticación y control de acceso.
                        </p>
                    </div>
                </div>
                <div class="bg-gray-50 p-8 rounded-2xl shadow-lg flex items-start space-x-4">
                    <i data-lucide="leaf" class="h-8 w-8 text-lime-500"></i>
                    <div>
                        <h3 class="text-2xl font-bold text-gray-800 mb-2">Sostenibilidad</h3>
                        <p class="text-gray-600">
                            Reduzca su huella de carbono con equipos eficientes y políticas de impresión inteligentes.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- SECCIÓN IMAGEN + LISTA -->
    <section class="py-20 bg-white">
        <div class="container mx-auto px-6 flex flex-col lg:flex-row items-center gap-12">
            <div class="lg:w-1/2">
                <img src="https://i.postimg.cc/NfSwPKjk/487094689-684597497409854-2985743454668687314-n.webp"
                     alt="Soluciones Tecnológicas"
                     class="w-full">
            </div>
            <div class="lg:w-1/2">
                <h2 class="text-4xl font-bold text-gray-800 mb-4">Descubre nuestras soluciones tecnológicas</h2>
                <div class="space-y-6">
                    <div class="flex items-start space-x-4">
                        <i data-lucide="printer" class="h-8 w-8 text-lime-500 mt-1"></i>
                        <div>
                            <h3 class="text-xl font-semibold text-gray-800">Servicio de impresión gestionado</h3>
                        </div>
                    </div>
                    <div class="flex items-start space-x-4">
                        <i data-lucide="share-2" class="h-8 w-8 text-lime-500 mt-1"></i>
                        <div>
                            <h3 class="text-xl font-semibold text-gray-800">Comunicaciones gráficas</h3>
                        </div>
                    </div>
                    <div class="flex items-start space-x-4">
                        <i data-lucide="sparkles" class="h-8 w-8 text-lime-500 mt-1"></i>
                        <div>
                            <h3 class="text-xl font-semibold text-gray-800">Transformación Digital</h3>
                        </div>
                    </div>
                    <div class="flex items-start space-x-4">
                        <i data-lucide="eye" class="h-8 w-8 text-lime-500 mt-1"></i>
                        <div>
                            <h3 class="text-xl font-semibold text-gray-800">Visual Communication</h3>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- MARCAS (SIN CUADROS AZULES) -->
    <section id="marcas" class="py-20 bg-gray-100">
        <div class="container mx-auto px-6 text-center">
            <h2 class="text-3xl font-bold text-gray-800 mb-4">Nuestras Marcas Aliadas</h2>
            <p class="text-xl text-gray-600 mb-12">
                Trabajamos con los líderes de la industria para ofrecerte la mejor tecnología.
            </p>

            <div id="marcas-display"
                 class="bg-white p-8 rounded-2xl shadow-xl max-w-5xl mx-auto flex flex-col md:flex-row items-center gap-8">
                <div class="md:w-1/2">
                    <img src="https://i.postimg.cc/VLTPtfV9/111111.png"
                         alt="Equipo Ricoh"
                         class="max-h-80 mx-auto">
                </div>
                <div class="md:w-1/2 text-left flex flex-col self-stretch">
                    <h3 class="text-4xl font-bold text-gray-800 mb-4">Ricoh</h3>
                    <p class="text-gray-600 mb-6 flex-grow">
                        Líder en equipos de oficina y soluciones de impresión de producción. Ofrecemos una amplia
                        gama de productos para satisfacer todas sus necesidades.
                    </p>
                    <a href="https://www.ricoh-americalatina.com/es"
                       target="_blank" rel="noopener noreferrer"
                       class="bg-lime-500 text-white text-md font-semibold px-6 py-3 rounded-full shadow-lg hover:bg-lime-600 transition duration-300 transform hover:scale-105 inline-block text-center mt-auto">
                        Conoce más de la marca
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- RESULTADOS -->
    <section class="py-20 bg-gray-50">
        <div class="container mx-auto px-6 text-center">
            <h2 class="text-4xl font-bold text-gray-800 mb-12">Resultados que Hablan por Sí Mismos</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="bg-white p-8 rounded-2xl shadow-lg border-t-4 border-lime-500">
                    <p class="text-5xl font-extrabold text-lime-600 mb-2">30%</p>
                    <p class="text-lg font-semibold text-gray-700">Reducción Promedio de Costos</p>
                </div>
                <div class="bg-white p-8 rounded-2xl shadow-lg border-t-4 border-lime-500">
                    <p class="text-5xl font-extrabold text-lime-600 mb-2">99%</p>
                    <p class="text-lg font-semibold text-gray-700">Uptime Garantizado de Equipos</p>
                </div>
                <div class="bg-white p-8 rounded-2xl shadow-lg border-t-4 border-lime-500">
                    <p class="text-5xl font-extrabold text-lime-600 mb-2">40%</p>
                    <p class="text-lg font-semibold text-gray-700">Aumento de Productividad del Equipo de TI</p>
                </div>
                <div class="bg-white p-8 rounded-2xl shadow-lg border-t-4 border-lime-500">
                    <p class="text-5xl font-extrabold text-lime-600 mb-2">100%</p>
                    <p class="text-lg font-semibold text-gray-700">Satisfacción de Nuestros Clientes</p>
                </div>
            </div>
        </div>
    </section>

    <!-- APORTE A LA COMUNIDAD -->
    <section class="py-20 bg-white">
        <div class="container mx-auto px-6">
            <div class="text-center mb-12">
                <h2 class="text-4xl font-bold text-gray-800 mb-4 border-b-4 border-lime-500 inline-block pb-2">
                    Aporte a la Comunidad
                </h2>
                <p class="text-lg text-gray-600 mt-4 max-w-3xl mx-auto">
                    En Copiermaster C&G creemos que la tecnología tiene sentido cuando mejora la vida de las personas.
                    Por eso acompañamos a emprendedores, instituciones educativas y proyectos locales con soluciones
                    que generan impacto real en la Amazonía y en todo el Ecuador.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="bg-gray-50 p-8 rounded-2xl shadow-lg">
                    <div class="flex items-center mb-4 space-x-3">
                        <i data-lucide="school" class="h-8 w-8 text-lime-500"></i>
                        <h3 class="text-xl font-semibold text-gray-800">Educación</h3>
                    </div>
                    <p class="text-gray-600">
                        Apoyamos a instituciones educativas con soluciones de impresión, material pedagógico y
                        automatización de procesos para que puedan enfocarse en lo más importante: enseñar.
                    </p>
                </div>

                <div class="bg-gray-50 p-8 rounded-2xl shadow-lg">
                    <div class="flex items-center mb-4 space-x-3">
                        <i data-lucide="store" class="h-8 w-8 text-lime-500"></i>
                        <h3 class="text-xl font-semibold text-gray-800">Emprendimientos Locales</h3>
                    </div>
                    <p class="text-gray-600">
                        Impulsamos negocios locales ayudándoles a digitalizar su operación, mejorar su imagen y
                        conectar con nuevos clientes a través de soluciones tecnológicas.
                    </p>
                </div>

                <div class="bg-gray-50 p-8 rounded-2xl shadow-lg">
                    <div class="flex items-center mb-4 space-x-3">
                        <i data-lucide="heart-handshake" class="h-8 w-8 text-lime-500"></i>
                        <h3 class="text-xl font-semibold text-gray-800">Responsabilidad Social</h3>
                    </div>
                    <p class="text-gray-600">
                        Participamos en proyectos comunitarios, donaciones de servicios y acompañamiento tecnológico
                        para organizaciones que trabajan por el desarrollo social.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- FOOTER -->
    <footer class="bg-gray-900 text-white py-12">
        <div class="container mx-auto px-6 grid grid-cols-1 md:grid-cols-4 gap-8">
            <div>
                <img src="https://i.postimg.cc/6qRNQd57/468963711-3994290450845859-6671631898219414239-n-removebg-preview.webp"
                     alt="Copiermaster C&G Logo"
                     class="h-36 mb-4">
            </div>
            <div>
                <h4 class="text-lg font-bold mb-4">Marcas</h4>
                <ul class="space-y-2">
                    <li><a href="nosotros.html#marcas" class="text-gray-400 hover:text-lime-500 transition duration-300">Nuestras Marcas</a></li>
                    <li><a href="soluciones.html" class="text-gray-400 hover:text-lime-500 transition duration-300">Equipos</a></li>
                </ul>
            </div>
            <div>
                <h4 class="text-lg font-bold mb-4">Bot &amp; Landing</h4>
                <ul class="space-y-2">
                    <li>
                        <a href="https://botandlanding.crisslombeida.com/"
                           target="_blank" rel="noopener noreferrer"
                           class="text-gray-400 hover:text-lime-500 transition duration-300">
                           Páginas Web
                        </a>
                    </li>
                    <li><a href="soluciones.html" class="text-gray-400 hover:text-lime-500 transition duration-300">Soluciones</a></li>
                </ul>
            </div>
            <div>
                <h4 class="text-lg font-bold mb-4">Legal</h4>
                <ul class="space-y-2">
                    <li><a href="#" class="text-gray-400 hover:text-lime-500 transition duration-300">Política de Calidad</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-lime-500 transition duration-300">Política de Privacidad</a></li>
                    <li><a href="#" class="text-gray-400 hover:text-lime-500 transition duration-300">Términos y Condiciones</a></li>
                </ul>
            </div>
        </div>
        <div class="container mx-auto px-6 mt-10 border-t border-gray-700 pt-8 text-center">
            <p class="text-gray-500 text-sm">
                &copy; 2024 Copiermaster C&G Soluciones Digitales S.A. Todos los derechos reservados.
            </p>
        </div>
    </footer>

    <!-- CHAT WIDGET -->
    <div id="chat-widget" class="fixed bottom-5 right-5 z-50 opacity-0 transform translate-y-4">
        <!-- Botón -->
        <button id="chat-bubble" class="bg-teal-500 text-white rounded-full shadow-lg w-16 h-16 flex items-center justify-center">
            <i data-lucide="message-circle" class="h-8 w-8"></i>
        </button>
        <!-- Ventana -->
        <div id="chat-window" class="hidden absolute bottom-20 right-0 bg-white rounded-2xl shadow-2xl flex flex-col">
            <div class="bg-teal-500 text-white p-4 rounded-t-2xl flex justify-between items-center">
                <div class="flex items-center gap-3">
                    <img src="https://placehold.co/40x40/ffffff/333333?text=P" alt="Criss" class="rounded-full">
                    <h3 class="font-bold">Criss</h3>
                </div>
                <button id="close-chat" class="text-white hover:text-gray-200">
                    <i data-lucide="x" class="h-6 w-6"></i>
                </button>
            </div>
            <div class="flex-1 p-4 space-y-4 bg-gray-100 bg-pattern overflow-y-auto">
                <div class="flex items-start gap-2">
                    <img src="https://placehold.co/32x32/ffffff/333333?text>P" alt="Criss" class="rounded-full">
                    <div class="bg-white p-3 rounded-lg rounded-tl-none shadow">
                        <p class="text-sm">¡Hola! ¿Cómo puedo ayudarte? 👋</p>
                    </div>
                </div>
            </div>
            <div class="p-4 bg-white border-t border-gray-200">
                <div class="flex flex-col gap-2">
                    <button class="text-teal-600 border border-teal-500 rounded-full px-4 py-2 text-sm font-semibold hover:bg-teal-50 transition">
                        ¡Hola!
                    </button>
                    <button class="text-teal-600 border border-teal-500 rounded-full px-4 py-2 text-sm font-semibold hover:bg-teal-50 transition">
                        Necesito más información
                    </button>
                    <button class="text-teal-600 border border-teal-500 rounded-full px-4 py-2 text-sm font-semibold hover:bg-teal-50 transition">
                        ¿Hay alguien disponible?
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- SCRIPTS -->
    <script>
        // YouTube Player
        var player;
        function onYouTubeIframeAPIReady() {
            player = new YT.Player('hero-video-player', {
                videoId: 'PwFWg96_Omk',
                playerVars: {
                    autoplay: 1,
                    controls: 0,
                    mute: 1,
                    loop: 0,
                    playlist: 'PwFWg96_Omk',
                    start: 0,
                    end: 110
                },
                events: {
                    onReady: onPlayerReady,
                    onStateChange: onPlayerStateChange
                }
            });
        }
        function onPlayerReady(event) {
            event.target.playVideo();
        }
        function onPlayerStateChange(event) {
            if (event.data === YT.PlayerState.ENDED) {
                player.seekTo(0);
            }
        }

        document.addEventListener('DOMContentLoaded', () => {
            // Menú móvil
            const menuButton = document.getElementById('menu-button');
            const mobileMenu = document.getElementById('mobile-menu');
            menuButton.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
            document.querySelectorAll('#mobile-menu a').forEach(link => {
                link.addEventListener('click', () => {
                    mobileMenu.classList.add('hidden');
                });
            });

            // Hero slider (solo textos)
            const heroTitle = document.getElementById('hero-title');
            const heroSubtitle = document.getElementById('hero-subtitle');
            const heroButtonsContainer = document.getElementById('hero-buttons');

            if (heroButtonsContainer) {
                const heroButtons = heroButtonsContainer.querySelectorAll('.hero-button');
                let currentHeroIndex = 0;
                let heroInterval;

                const heroContent = [
                    {
                        title: '16 años impulsando tecnología',
                        subtitle: 'Conectamos empresas, optimizamos procesos y cuidamos tu información.'
                    },
                    {
                        title: 'Tecnología de impresión para tu crecimiento',
                        subtitle: 'Trabajamos con las principales marcas del mundo para tu negocio.'
                    },
                    {
                        title: 'Páginas web que venden por ti',
                        subtitle: 'Creamos landing pages enfocadas en resultados y generación de clientes.'
                    }
                ];

                function updateHeroSection(index) {
                    const content = heroContent[index];
                    heroTitle.style.opacity = 0;
                    heroSubtitle.style.opacity = 0;

                    setTimeout(() => {
                        heroTitle.textContent = content.title;
                        heroSubtitle.textContent = content.subtitle;
                        heroTitle.style.opacity = 1;
                        heroSubtitle.style.opacity = 1;
                    }, 500);

                    heroButtons.forEach((button, btnIndex) => {
                        button.classList.toggle('hero-button-active', btnIndex === index);
                    });

                    currentHeroIndex = index;
                }

                function startHeroSlider() {
                    heroInterval = setInterval(() => {
                        const nextIndex = (currentHeroIndex + 1) % heroContent.length;
                        updateHeroSection(nextIndex);
                    }, 7000);
                }

                function resetHeroInterval() {
                    clearInterval(heroInterval);
                    startHeroSlider();
                }

                heroButtonsContainer.addEventListener('click', (e) => {
                    const button = e.target.closest('.hero-button');
                    if (button) {
                        const index = parseInt(button.dataset.index, 10);
                        updateHeroSection(index);
                        resetHeroInterval();
                    }
                });

                updateHeroSection(0);
                startHeroSlider();
            }

            // Chat widget
            const chatWidget = document.getElementById('chat-widget');
            const chatBubble = document.getElementById('chat-bubble');
            const chatWindow = document.getElementById('chat-window');
            const closeChatButton = document.getElementById('close-chat');
            let chatOpened = false;

            const openChat = () => {
                chatWindow.classList.remove('hidden');
                chatBubble.classList.add('hidden');
                chatOpened = true;
            };

            const closeChat = () => {
                chatWindow.classList.add('hidden');
                chatBubble.classList.remove('hidden');
                chatOpened = false;
            };

            chatBubble.addEventListener('click', openChat);
            closeChatButton.addEventListener('click', closeChat);

            setTimeout(() => {
                const playSoundAndOpenChat = async () => {
                    try {
                        await Tone.start();
                        const synth = new Tone.Synth().toDestination();
                        synth.triggerAttackRelease("E5", "8n");
                        chatWidget.classList.remove('opacity-0', 'translate-y-4');
                        setTimeout(openChat, 500);
                    } catch (error) {
                        console.error("No se pudo reproducir el sonido o abrir el chat automáticamente.", error);
                        chatWidget.classList.remove('opacity-0', 'translate-y-4');
                    }
                };
                playSoundAndOpenChat();
            }, 5000);

            // Inicializar iconos
            lucide.createIcons();
        });
    </script>
</body>
</html>
