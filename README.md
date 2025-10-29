<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>INGENIEROS NEZTRAN S.A.S. - Energía confiable, soluciones seguras</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
    <style>
        :root {
            --azul: #0057A3;
            --naranja: #FF7B00;
            --gris-claro: #f5f5f5;
            --gris-oscuro: #333;
            --blanco: #fff;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: var(--gris-claro);
            color: var(--gris-oscuro);
            line-height: 1.6;
        }
        
        header {
            background-color: var(--azul);
            color: var(--blanco);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .nav-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            color: var(--naranja);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 25px;
        }
        
        nav ul li a {
            color: var(--blanco);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }
        
        nav ul li a:hover {
            color: var(--naranja);
        }
        
        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
        }
        
        .portada {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://images.unsplash.com/photo-1509391366360-2e959784a276?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2072&q=80') no-repeat center center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: var(--blanco);
            padding-top: 70px;
        }
        
        .portada-content {
            max-width: 800px;
            padding: 0 20px;
        }
        
        .portada h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            animation: fadeInDown 1s;
        }
        
        .portada p {
            font-size: 1.5rem;
            margin-bottom: 30px;
            animation: fadeInUp 1s;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--naranja);
            color: var(--blanco);
            padding: 12px 30px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background-color: var(--azul);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--azul);
            display: inline-block;
            padding-bottom: 10px;
        }
        
        .section-title h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 3px;
            background-color: var(--naranja);
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .about-content {
            display: flex;
            align-items: center;
            gap: 40px;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-image {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }
        
        .about-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: transform 0.5s;
        }
        
        .about-image:hover img {
            transform: scale(1.05);
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background-color: var(--blanco);
            border-radius: 10px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s, box-shadow 0.3s;
            text-align: center;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
        }
        
        .service-card:hover .service-icon {
            transform: scale(1.1);
        }
        
        .service-card:hover .view-gallery {
            opacity: 1;
            transform: translateY(0);
        }
        
        .service-icon {
            font-size: 3rem;
            color: var(--azul);
            margin-bottom: 20px;
            transition: transform 0.3s;
        }
        
        .service-card h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--azul);
        }
        
        .view-gallery {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            background-color: var(--naranja);
            color: var(--blanco);
            padding: 10px;
            text-align: center;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.3s;
            font-weight: bold;
        }
        
        .norms-list {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .norm-item {
            background-color: var(--blanco);
            margin-bottom: 15px;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.05);
            display: flex;
            align-items: center;
            transition: transform 0.3s;
        }
        
        .norm-item:hover {
            transform: translateX(10px);
        }
        
        .norm-icon {
            font-size: 1.5rem;
            color: var(--naranja);
            margin-right: 15px;
        }
        
        .contact-container {
            display: flex;
            gap: 40px;
        }
        
        .contact-info {
            flex: 1;
        }
        
        .contact-form {
            flex: 1;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .contact-icon {
            font-size: 1.5rem;
            color: var(--azul);
            margin-right: 15px;
            width: 30px;
            text-align: center;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
        }
        
        textarea.form-control {
            min-height: 150px;
            resize: vertical;
        }
        
        .qr-section {
            background-color: var(--azul);
            color: var(--blanco);
            text-align: center;
            padding: 60px 0;
        }
        
        .qr-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 20px;
        }
        
        .qr-code {
            background-color: var(--blanco);
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
        }
        
        .qr-instructions {
            max-width: 600px;
            margin: 0 auto;
        }
        
        .qr-instructions h3 {
            font-size: 1.8rem;
            margin-bottom: 15px;
        }
        
        .qr-instructions p {
            margin-bottom: 10px;
            font-size: 1.1rem;
        }
        
        .qr-steps {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
            flex-wrap: wrap;
        }
        
        .qr-step {
            flex: 1;
            min-width: 200px;
            max-width: 250px;
            text-align: center;
        }
        
        .qr-step-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
            color: var(--naranja);
        }
        
        /* Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            z-index: 2000;
            overflow: auto;
        }
        
        .modal-content {
            background-color: var(--blanco);
            margin: 5% auto;
            padding: 20px;
            border-radius: 10px;
            width: 90%;
            max-width: 1000px;
            position: relative;
            animation: modalFadeIn 0.5s;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 2rem;
            color: var(--gris-oscuro);
            cursor: pointer;
            transition: color 0.3s;
        }
        
        .close-modal:hover {
            color: var(--naranja);
        }
        
        .modal-title {
            text-align: center;
            margin-bottom: 20px;
            color: var(--azul);
            font-size: 2rem;
        }
        
        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }
        
        .gallery-item {
            border-radius: 8px;
            overflow: hidden;
            height: 200px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .gallery-item:hover {
            transform: scale(1.03);
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }
        
        footer {
            background-color: var(--azul);
            color: var(--blanco);
            padding: 40px 0 20px;
        }
        
        .footer-content {
            display: flex;
            justify-content: space-between;
            margin-bottom: 30px;
        }
        
        .footer-logo {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 15px;
        }
        
        .footer-links h4, .footer-social h4 {
            margin-bottom: 15px;
            font-size: 1.2rem;
        }
        
        .footer-links ul {
            list-style: none;
        }
        
        .footer-links ul li {
            margin-bottom: 10px;
        }
        
        .footer-links ul li a {
            color: var(--blanco);
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links ul li a:hover {
            color: var(--naranja);
        }
        
        .social-icons {
            display: flex;
            gap: 15px;
        }
        
        .social-icons a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: var(--blanco);
            font-size: 1.2rem;
            transition: all 0.3s;
        }
        
        .social-icons a:hover {
            background-color: var(--naranja);
            transform: translateY(-5px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            font-size: 0.9rem;
        }
        
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes modalFadeIn {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @media (max-width: 768px) {
            .hamburger {
                display: block;
            }
            
            nav ul {
                position: fixed;
                top: 70px;
                left: -100%;
                width: 100%;
                height: calc(100vh - 70px);
                background-color: var(--azul);
                flex-direction: column;
                align-items: center;
                justify-content: flex-start;
                padding-top: 50px;
                transition: left 0.3s;
            }
            
            nav ul.active {
                left: 0;
            }
            
            nav ul li {
                margin: 15px 0;
            }
            
            .portada h1 {
                font-size: 2.5rem;
            }
            
            .portada p {
                font-size: 1.2rem;
            }
            
            .about-content, .contact-container {
                flex-direction: column;
            }
            
            .footer-content {
                flex-direction: column;
                gap: 30px;
            }
            
            .qr-steps {
                flex-direction: column;
                align-items: center;
            }
            
            .gallery-grid {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container nav-container">
            <div class="logo">
                <i class="fas fa-bolt"></i>
                <span>INGENIEROS NEZTRAN S.A.S.</span>
            </div>
            <div class="hamburger">
                <i class="fas fa-bars"></i>
            </div>
            <nav>
                <ul>
                    <li><a href="#inicio">Inicio</a></li>
                    <li><a href="#nosotros">Quiénes Somos</a></li>
                    <li><a href="#servicios">Servicios</a></li>
                    <li><a href="#normatividad">Normatividad</a></li>
                    <li><a href="#qr">QR Portafolio</a></li>
                    <li><a href="#contacto">Contacto</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="portada" id="inicio">
        <div class="portada-content">
            <h1>INGENIEROS NEZTRAN S.A.S.</h1>
            <p>Energía confiable, soluciones seguras.</p>
            <a href="#servicios" class="btn">Nuestros Servicios</a>
        </div>
    </section>

    <section id="nosotros">
        <div class="container">
            <div class="section-title">
                <h2>Quiénes Somos</h2>
            </div>
            <div class="about-content">
                <div class="about-text">
                    <p>Somos una empresa colombiana dedicada al servicio eléctrico a nivel local y nacional, desempeñándonos en los ámbitos de: diseño, instalaciones, adecuaciones, mantenimiento y control en el ámbito eléctrico.</p>
                    <br>
                    <p>INGENIEROS NEZTRAN S.A.S. nace para satisfacer un grupo de necesidades existente en el mercado como la atención personalizada permitiendo a los clientes determinar con claridad cuáles podrían ser las soluciones frente a la gran cantidad de problemas que se presentan en los ámbitos del uso y la aplicabilidad de la energía eléctrica.</p>
                    <br>
                    <p>Tenemos a nuestra disposición el capital humano y físico que sea necesario para efectuar la actividad o trabajo que nuestros clientes requieran, destacándonos por un servicio garantizado y familiar. Donde uno de nuestros objetivos es la plena satisfacción de las dos partes.</p>
                    <br>
                    <p>Los valores y principios que enmarcan nuestra actividad diaria se fundamentan en la confiabilidad que depositan en nosotros al poder presenciar un servicio correcto y legal en todos los ámbitos.</p>
                </div>
                <div class="about-image">
                    <img src="https://images.unsplash.com/photo-1558618047-3c8c76ca7d13?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2064&q=80" alt="Equipo de trabajo">
                </div>
            </div>
        </div>
    </section>

    <section id="servicios" style="background-color: var(--blanco);">
        <div class="container">
            <div class="section-title">
                <h2>Nuestros Servicios</h2>
            </div>
            <div class="services-grid">
                <div class="service-card" data-service="instalaciones">
                    <div class="service-icon">
                        <i class="fas fa-plug"></i>
                    </div>
                    <h3>Instalaciones Eléctricas</h3>
                    <p>Montaje de circuitos eléctricos residenciales, comerciales e industriales. Salidas para tomacorrientes, alumbrado, interruptores, tableros de distribución y más.</p>
                    <div class="view-gallery">Ver Galería</div>
                </div>
                <div class="service-card" data-service="reparaciones">
                    <div class="service-icon">
                        <i class="fas fa-tools"></i>
                    </div>
                    <h3>Reparaciones Eléctricas</h3>
                    <p>Reparaciones en circuitos de baja tensión, control de sobrecargas, caídas de voltaje, reestructuración de redes eléctricas e inspección de polo a tierra.</p>
                    <div class="view-gallery">Ver Galería</div>
                </div>
                <div class="service-card" data-service="fotovoltaicos">
                    <div class="service-icon">
                        <i class="fas fa-solar-panel"></i>
                    </div>
                    <h3>Sistemas Fotovoltaicos</h3>
                    <p>Estudio de dimensionamiento, diseño e instalación de sistemas fotovoltaicos autónomos y con inyección a la red para aprovechar la energía solar.</p>
                    <div class="view-gallery">Ver Galería</div>
                </div>
                <div class="service-card" data-service="mantenimiento">
                    <div class="service-icon">
                        <i class="fas fa-cogs"></i>
                    </div>
                    <h3>Mantenimiento</h3>
                    <p>Mantenimiento preventivo para evitar fallos, predictivo para anticipar problemas y correctivo para reparar averías y restablecer el funcionamiento óptimo.</p>
                    <div class="view-gallery">Ver Galería</div>
                </div>
                <div class="service-card" data-service="modernizacion">
                    <div class="service-icon">
                        <i class="fas fa-lightbulb"></i>
                    </div>
                    <h3>Modernización</h3>
                    <p>Asesoría para la actualización en el uso de herramientas que permitan un mejor uso de la energía, iluminación eficiente y sistemas automatizados.</p>
                    <div class="view-gallery">Ver Galería</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Modal para galerías de servicios -->
    <div id="galleryModal" class="modal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <h2 class="modal-title" id="modalServiceTitle">Galería de Servicio</h2>
            <div class="gallery-grid" id="serviceGallery">
                <!-- Las imágenes se cargarán dinámicamente aquí -->
            </div>
        </div>
    </div>

    <section id="normatividad">
        <div class="container">
            <div class="section-title">
                <h2>Normatividad y Reglamentación</h2>
            </div>
            <div class="norms-list">
                <div class="norm-item">
                    <div class="norm-icon">
                        <i class="fas fa-gavel"></i>
                    </div>
                    <div>
                        <h3>Ley 19 de 1990</h3>
                        <p>Régimen legal de los técnicos electricistas</p>
                    </div>
                </div>
                <div class="norm-item">
                    <div class="norm-icon">
                        <i class="fas fa-file-contract"></i>
                    </div>
                    <div>
                        <h3>Decreto 991 de 1991</h3>
                        <p>Decreto reglamentario de la Ley 19 de 1990</p>
                    </div>
                </div>
                <div class="norm-item">
                    <div class="norm-icon">
                        <i class="fas fa-file-contract"></i>
                    </div>
                    <div>
                        <h3>Decreto 0277 de 1993</h3>
                        <p>Normativa complementaria para técnicos electricistas</p>
                    </div>
                </div>
                <div class="norm-item">
                    <div class="norm-icon">
                        <i class="fas fa-scale-balanced"></i>
                    </div>
                    <div>
                        <h3>Ley 1264 de 2008</h3>
                        <p>Código de ética para el ejercicio de la profesión</p>
                    </div>
                </div>
                <div class="norm-item">
                    <div class="norm-icon">
                        <i class="fas fa-book"></i>
                    </div>
                    <div>
                        <h3>NTC 2050 (2020)</h3>
                        <p>Código eléctrico Colombiano</p>
                    </div>
                </div>
                <div class="norm-item">
                    <div class="norm-icon">
                        <i class="fas fa-file-signature"></i>
                    </div>
                    <div>
                        <h3>Resolución 40117 de 2024</h3>
                        <p>Reglamento técnico de instalaciones eléctricas RETIE</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="qr" class="qr-section">
        <div class="container">
            <div class="section-title">
                <h2 style="color: var(--blanco);">Portafolio Digital</h2>
            </div>
            <div class="qr-container">
                <div class="qr-code" id="qrcode"></div>
                <div class="qr-instructions">
                    <h3>Escanea para ver nuestro portafolio</h3>
                    <p>Utiliza la cámara de tu teléfono para escanear este código QR y acceder directamente a nuestro portafolio de servicios.</p>
                    <p>¡Comparte este código con tus contactos para que conozcan nuestros servicios!</p>
                </div>
                <div class="qr-steps">
                    <div class="qr-step">
                        <div class="qr-step-icon">
                            <i class="fas fa-camera"></i>
                        </div>
                        <h4>Paso 1</h4>
                        <p>Abre la aplicación de cámara en tu teléfono</p>
                    </div>
                    <div class="qr-step">
                        <div class="qr-step-icon">
                            <i class="fas fa-qrcode"></i>
                        </div>
                        <h4>Paso 2</h4>
                        <p>Enfoca el código QR con tu cámara</p>
                    </div>
                    <div class="qr-step">
                        <div class="qr-step-icon">
                            <i class="fas fa-mouse-pointer"></i>
                        </div>
                        <h4>Paso 3</h4>
                        <p>Toca el enlace que aparece en pantalla</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="contacto" style="background-color: var(--blanco);">
        <div class="container">
            <div class="section-title">
                <h2>Contacto</h2>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <h3>Información de Contacto</h3>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div>
                            <h4>Dirección</h4>
                            <p>Colombia</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-phone"></i>
                        </div>
                        <div>
                            <h4>Teléfono</h4>
                            <p>+57 XXX XXX XXXX</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div>
                            <h4>Correo Electrónico</h4>
                            <p>info@neztran.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-clock"></i>
                        </div>
                        <div>
                            <h4>Horario de Atención</h4>
                            <p>Lunes a Viernes: 8:00 am - 6:00 pm</p>
                            <p>Sábados: 8:00 am - 1:00 pm</p>
                        </div>
                    </div>
                </div>
                <div class="contact-form">
                    <h3>Envíanos un Mensaje</h3>
                    <form>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Nombre completo" required>
                        </div>
                        <div class="form-group">
                            <input type="email" class="form-control" placeholder="Correo electrónico" required>
                        </div>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Asunto">
                        </div>
                        <div class="form-group">
                            <textarea class="form-control" placeholder="Mensaje" required></textarea>
                        </div>
                        <button type="submit" class="btn">Enviar Mensaje</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-about">
                    <div class="footer-logo">
                        <i class="fas fa-bolt"></i> INGENIEROS NEZTRAN S.A.S.
                    </div>
                    <p>Empresa colombiana dedicada al servicio eléctrico a nivel local y nacional, ofreciendo soluciones confiables y seguras.</p>
                </div>
                <div class="footer-links">
                    <h4>Enlaces Rápidos</h4>
                    <ul>
                        <li><a href="#inicio">Inicio</a></li>
                        <li><a href="#nosotros">Quiénes Somos</a></li>
                        <li><a href="#servicios">Servicios</a></li>
                        <li><a href="#normatividad">Normatividad</a></li>
                        <li><a href="#qr">QR Portafolio</a></li>
                        <li><a href="#contacto">Contacto</a></li>
                    </ul>
                </div>
                <div class="footer-social">
                    <h4>Síguenos</h4>
                    <div class="social-icons">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-youtube"></i></a>
                    </div>
                </div>
            </div>
            <div class="copyright">
                <p>&copy; <span id="current-year"></span> INGENIEROS NEZTRAN S.A.S. - Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <script>
        // Año actual para el copyright
        document.getElementById('current-year').textContent = new Date().getFullYear();
        
        // Menú hamburguesa para móviles
        const hamburger = document.querySelector('.hamburger');
        const navMenu = document.querySelector('nav ul');
        
        hamburger.addEventListener('click', () => {
            navMenu.classList.toggle('active');
        });
        
        // Cerrar menú al hacer clic en un enlace
        document.querySelectorAll('nav ul li a').forEach(link => {
            link.addEventListener('click', () => {
                navMenu.classList.remove('active');
            });
        });
        
        // Smooth scroll para enlaces internos
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 70,
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Generar código QR
        document.addEventListener('DOMContentLoaded', function() {
            // Obtener la URL actual de la página
            const currentUrl = window.location.href;
            
            // Crear el código QR
            const qrcode = new QRCode(document.getElementById("qrcode"), {
                text: currentUrl,
                width: 200,
                height: 200,
                colorDark: "#0057A3",
                colorLight: "#ffffff",
                correctLevel: QRCode.CorrectLevel.H
            });
        });
        
        // Galerías de servicios
        const serviceCards = document.querySelectorAll('.service-card');
        const modal = document.getElementById('galleryModal');
        const closeModal = document.querySelector('.close-modal');
        const modalTitle = document.getElementById('modalServiceTitle');
        const serviceGallery = document.getElementById('serviceGallery');
        
        // Imágenes para cada servicio (URLs de ejemplo)
        const serviceImages = {
            instalaciones: [
                'https://images.unsplash.com/photo-1621905252507-b35492cc74b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2069&q=80',
                'https://images.unsplash.com/photo-1621905251189-08d45b3dadd0?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2069&q=80',
                'https://images.unsplash.com/photo-1558618047-3c8c76ca7d13?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2064&q=80',
                'https://images.unsplash.com/photo-1621905252507-b35492cc74b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2069&q=80'
            ],
            reparaciones: [
                'https://images.unsplash.com/photo-1581093458791-8a6b22bb9b5a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1581093458872-8c6b6b6b6b6b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1581093458791-8a6b22bb9b5a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1581093458872-8c6b6b6b6b6b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80'
            ],
            fotovoltaicos: [
                'https://images.unsplash.com/photo-1509391366360-2e959784a276?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2072&q=80',
                'https://images.unsplash.com/photo-1509391366360-2e959784a276?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2072&q=80',
                'https://images.unsplash.com/photo-1509391366360-2e959784a276?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2072&q=80',
                'https://images.unsplash.com/photo-1509391366360-2e959784a276?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2072&q=80'
            ],
            mantenimiento: [
                'https://images.unsplash.com/photo-1581093458791-8a6b22bb9b5a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1581093458872-8c6b6b6b6b6b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1581093458791-8a6b22bb9b5a?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80',
                'https://images.unsplash.com/photo-1581093458872-8c6b6b6b6b6b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80'
            ],
            modernizacion: [
                'https://images.unsplash.com/photo-1558618047-3c8c76ca7d13?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2064&q=80',
                'https://images.unsplash.com/photo-1621905252507-b35492cc74b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2069&q=80',
                'https://images.unsplash.com/photo-1558618047-3c8c76ca7d13?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2064&q=80',
                'https://images.unsplash.com/photo-1621905252507-b35492cc74b4?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2069&q=80'
            ]
        };
        
        // Títulos para cada servicio
        const serviceTitles = {
            instalaciones: 'Instalaciones Eléctricas',
            reparaciones: 'Reparaciones Eléctricas',
            fotovoltaicos: 'Sistemas Fotovoltaicos',
            mantenimiento: 'Mantenimiento',
            modernizacion: 'Modernización'
        };
        
        // Abrir modal al hacer clic en una tarjeta de servicio
        serviceCards.forEach(card => {
            card.addEventListener('click', function() {
                const serviceType = this.getAttribute('data-service');
                openGallery(serviceType);
            });
        });
        
        // Función para abrir la galería
        function openGallery(serviceType) {
            modalTitle.textContent = serviceTitles[serviceType];
            serviceGallery.innerHTML = '';
            
            serviceImages[serviceType].forEach(imageUrl => {
                const galleryItem = document.createElement('div');
                galleryItem.className = 'gallery-item';
                
                const img = document.createElement('img');
                img.src = imageUrl;
                img.alt = serviceTitles[serviceType];
                
                galleryItem.appendChild(img);
                serviceGallery.appendChild(galleryItem);
            });
            
            modal.style.display = 'block';
            document.body.style.overflow = 'hidden';
        }
        
        // Cerrar modal
        closeModal.addEventListener('click', function() {
            modal.style.display = 'none';
            document.body.style.overflow = 'auto';
        });
        
        // Cerrar modal al hacer clic fuera del contenido
        window.addEventListener('click', function(event) {
            if (event.target === modal) {
                modal.style.display = 'none';
                document.body.style.overflow = 'auto';
            }
        });
    </script>
</body>
</html>
