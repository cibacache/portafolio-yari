<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Portafolio Profesional</title>
    <style>
        :root {
            --color-principal: #ffffff;
            --color-secundario: #101010;
            --color-neutro: #f4f4f4;
            --color-acento: #ff0055;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            font-family: 'Montserrat', 'Helvetica Neue', Arial, sans-serif;
            background-color: var(--color-principal);
            color: var(--color-secundario);
        }

        body {
            line-height: 1.4;
        }

        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background-color: rgba(255, 255, 255, 0.95);
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
            z-index: 1000;
            padding: 18px 40px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-weight: 800;
            font-size: 1.4rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            text-decoration: none;
            color: var(--color-secundario);
        }

        .logo span {
            color: var(--color-acento);
        }

        nav a {
            text-decoration: none;
            color: var(--color-secundario);
            font-weight: 700;
            font-size: 0.85rem;
            text-transform: uppercase;
            margin-left: 24px;
            transition: color 0.3s ease;
        }

        nav a:hover {
            color: var(--color-acento);
        }

        section {
            padding: 120px 50px 80px;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .titulo-seccion {
            font-size: 2.3rem;
            text-transform: uppercase;
            font-weight: 800;
            margin-bottom: 30px;
            letter-spacing: 1px;
        }

        #inicio {
            position: relative;
            min-height: 100vh;
            overflow: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
        }

        .contenedor-video-youtube {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            pointer-events: none;
        }

        .contenedor-video-youtube iframe {
            position: absolute;
            top: 50%;
            left: 50%;
            width: 177.77vh;
            height: 100vh;
            min-width: 100%;
            min-height: 100%;
            transform: translate(-50%, -50%);
        }

        .filtro-oscuro {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.55);
            z-index: 2;
        }

        .contenido-hero {
            position: relative;
            z-index: 3;
            max-width: 920px;
            padding: 0 20px;
        }

        #inicio h1 {
            font-size: 4rem;
            font-weight: 700;
            letter-spacing: 5px;
        }

        #inicio h1 span {
            color: var(--color-acento);
        }

        #inicio p {
            font-size: 1.1rem;
            text-transform: uppercase;
            font-weight: 400;
            letter-spacing: 2px;
            margin-top: 18px;
        }

        .grid-proyectos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 24px;
            margin-top: 20px;
        }

        .tarjeta-proyecto {
            background-color: var(--color-principal);
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 16px 40px rgba(0, 0, 0, 0.06);
        }

        .video-responsive {
            position: relative;
            width: 100%;
            padding-bottom: 56.25%;
            overflow: hidden;
            background: #000;
        }

        .video-responsive iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: 0;
        }

        .proyecto-info {
            padding: 22px;
        }

        .proyecto-info h3 {
            font-size: 1.15rem;
            font-weight: 800;
            margin-bottom: 12px;
            text-transform: uppercase;
        }

        .proyecto-info p {
            font-weight: 300;
            line-height: 1.75;
            color: #444;
        }

        #sobre-mi p {
            text-align: justify;
            line-height: 1.8;
        }

        .contenedor-sobre-mi {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }

        .carrusel-sobre-mi {
            position: relative;
            width: 100%;
            aspect-ratio: 4 / 3;
            overflow: hidden;
            border-radius: 14px;
            background-color: #f4f4f4;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.18);
        }

        .slider-track {
            position: relative;
            display: flex;
            width: 100%;
            height: 100%;
            animation: slide-photos 30s ease-in-out infinite;
        }

        .slide {
            position: relative;
            min-width: 100%;
            flex-shrink: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            aspect-ratio: 4 / 3;
            background-color: #f4f4f4;
        }

        .slide img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .carrusel-sobre-mi:hover .slider-track {
            animation-play-state: paused;
        }

        @keyframes slide-photos {
            0%, 13.333% {
                transform: translateX(0);
            }
            16.666%, 30% {
                transform: translateX(-100%);
            }
            33.333%, 46.666% {
                transform: translateX(-200%);
            }
            50%, 63.333% {
                transform: translateX(-300%);
            }
            66.666%, 80% {
                transform: translateX(-400%);
            }
            83.333%, 100% {
                transform: translateX(-500%);
            }
        }

        .btn-cv {
            display: inline-block;
            margin-top: 20px;
            padding: 14px 30px;
            background-color: var(--color-secundario);
            color: var(--color-principal);
            text-decoration: none;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: background-color 0.3s ease;
        }

        .btn-cv:hover {
            background-color: var(--color-acento);
        }

        #contacto {
            background-color: var(--color-secundario);
            color: var(--color-principal);
        }

        .footer-contacto {
            text-align: center;
        }

        .footer-contacto a {
            color: var(--color-acento);
            text-decoration: none;
        }

        .footer-contacto a:hover {
            text-decoration: underline;
        }

        @media (max-width: 768px) {
            header {
                padding: 18px 20px;
                flex-direction: column;
                gap: 14px;
            }

            nav a {
                margin: 0 10px;
                font-size: 0.8rem;
            }

            section {
                padding: 120px 20px 60px;
            }

            .contenedor-sobre-mi {
                grid-template-columns: 1fr;
            }

            #inicio h1 {
                font-size: 2.8rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <a href="#inicio" class="logo">YARITZA MONDACA<span>.</span></a>
        <nav>
            <a href="#inicio">Inicio</a>
            <a href="#proyectos">Proyectos</a>
            <a href="#sobre-mi">Sobre mí</a>
            <a href="#contacto">Contacto</a>
        </nav>
    </header>

    <section id="inicio">
        <div class="contenedor-video-youtube">
            <iframe src="https://www.youtube.com/embed/4pi-T4LH3cc?autoplay=1&mute=1&loop=1&playlist=4pi-T4LH3cc&controls=0&rel=0&modestbranding=1&iv_load_policy=3"
                    allow="autoplay; encrypted-media"
                    allowfullscreen></iframe>
        </div>
        <div class="filtro-oscuro"></div>
        <div class="contenido-hero">
            <h1>PORTAFOLIO<span>.</span></h1>
            <p>Contenido audiovisual y fotografía con enfoque en la divulgación del conocimiento</p>
        </div>
    </section>

    <section id="proyectos">
        <h2 class="titulo-seccion">Proyectos destacados</h2>
        <div class="grid-proyectos">
            <div class="tarjeta-proyecto">
                <div class="video-responsive">
                    <iframe src="https://www.youtube.com/embed/BrDQabOUr4E" allowfullscreen></iframe>
                </div>
                <div class="proyecto-info">
                    <h3>Teoría de Lycal Radio</h3>
                    <p>Dirección, locución y montaje audiovisual del podcast La Teoría de Lycal Radio.</p>
                </div>
            </div>
            <div class="tarjeta-proyecto">
                <div class="video-responsive">
                    <iframe src="https://www.youtube.com/embed/2t5Kt0qk4ow" allowfullscreen></iframe>
                </div>
                <div class="proyecto-info">
                    <h3>Soli, la cazadora del desierto</h3>
                    <p>Locución y montaje audiovisual del audiolibro.</p>
                </div>
            </div>
            <div class="tarjeta-proyecto">
                <div class="video-responsive">
                    <iframe src="https://www.youtube.com/embed/A7o6tiGTN14" allowfullscreen></iframe>
                </div>
                <div class="proyecto-info">
                    <h3>Nivel Curioso CL</h3>
                    <p>Creadora del canal de datos curiosos con enfoque en la divulgación del conocimiento.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="sobre-mi">
        <h2 class="titulo-seccion">Sobre mí</h2>
        <div class="contenedor-sobre-mi">
            <div>
                <p style="font-size: 1.2rem; font-weight: 300; margin-bottom: 15px;">Periodista y especialista en generación de contenidos audiovisuales.</p>
                <p>Me dedico a la creación de contenido audiovisual y fotografía con un enfoque en la divulgación del conocimiento. Mi objetivo es transformar ideas y conceptos complejos en relatos narrativos visuales potentes y atractivos.</p>
                <p style="margin-top: 18px;">Cuento con más de 10 años de experiencia en generación de contenidos audiovisuales para medios digitales. Manejo redacción periodística, comunicación científica, escritura creativa, guión audiovisual, locución, equipos audiovisuales y edición de video.</p>
                <a href="curriculum.pdf" target="_blank" class="btn-cv">Descargar Currículum (PDF)</a>
            </div>

            
            <div class="carrusel-sobre-mi">
                <div class="slider-track">
                    <div class="slide"><img src="foto1.png" alt="Fotografía 1"></div>
                    <div class="slide"><img src="foto2.jpg" alt="Fotografía 2"></div>
                    <div class="slide"><img src="foto3.jpg" alt="Fotografía 3"></div>
                    <div class="slide"><img src="foto4.jpg" alt="Fotografía 4"></div>
                    <div class="slide"><img src="foto5.jpg" alt="Fotografía 5"></div>
                    <div class="slide"><img src="foto6.jpg" alt="Fotografía 6"></div>
                </div>
            </div>
        </div>
    </section>

    <section id="contacto">
        <div class="footer-contacto">
            <h2 class="titulo-seccion" style="color: white;">Contacto</h2>
            <p style="font-size: 1.2rem; color: #fff; margin-bottom: 12px;">Yaritza Mondaca Rodríguez</p>
            <p>Correo: <a href="mailto:ymondaca1@gmail.com">ymondaca1@gmail.com</a></p>
            <p>Instagram: <a href="https://instagram.com/ymondaca_1" target="_blank">@ymondaca_1</a></p>
