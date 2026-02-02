<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Multilinks Concept (Hub) - Educational & Remote Cyber Cafe Services</title>
    <!-- Importing FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* --- CSS VARIABLES & RESET --- */
        :root {
            --primary-green: #008751; /*Green */
            --dark-green: #006b3f;
            --white: #ffffff;
            --light-gray: #f4f4f4;
            --text-dark: #333333;
            --text-light: #666666;
            --shadow: 0 4px 6px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Calibri', 'Segoe UI', sans-serif; /* Requested Font */
            background-color: var(--light-gray);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        ul {
            list-style: none;
        }

        /* --- NAVIGATION --- */
        header {
            background-color: var(--white);
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem 20px;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: var(--primary-green);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo i {
            color: var(--primary-green);
        }

        .nav-links {
            display: flex;
            gap: 20px;
        }

        .nav-item {
            cursor: pointer;
            font-weight: 600;
            color: var(--text-dark);
            padding: 8px 16px;
            border-radius: 4px;
            transition: var(--transition);
        }

        .nav-item:hover, .nav-item.active {
            color: var(--white);
            background-color: var(--primary-green);
        }

        /* Mobile Menu Button */
        .menu-toggle {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* --- PAGE STRUCTURE (SPA Logic) --- */
        .page-section {
            display: none; /* Hidden by default */
            min-height: 80vh;
            animation: fadeIn 0.5s ease;
        }

        .page-section.active-page {
            display: block; /* Show active page */
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* --- HERO SECTION (Page 1) --- */
        .hero {
            background: linear-gradient(rgba(0, 135, 81, 0.8), rgba(0, 107, 63, 0.9)), 
                        url('https://lh3.googleusercontent.com/p/AF1QipM314sK9funLHgA4HMIOOfnuvfFrMXCmiFHZl7D=s680-w680-h510-rw') no-repeat center center/cover;
            color: var(--white);
            text-align: center;
            padding: 100px 20px;
            margin-bottom: 40px;
        }

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            font-weight: bold;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-btn {
            display: inline-block;
            background-color: var(--white);
            color: var(--primary-green);
            padding: 12px 30px;
            border-radius: 50px;
            font-weight: bold;
            font-size: 1.1rem;
            transition: var(--transition);
            cursor: pointer;
            border: 2px solid var(--white);
        }

        .cta-btn:hover {
            background-color: transparent;
            color: var(--white);
        }

        /* --- INTRO & CONTACT CARDS --- */
        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }

        .card {
            background: var(--white);
            padding: 25px;
            border-radius: 8px;
            box-shadow: var(--shadow);
            border-left: 5px solid var(--primary-green);
        }

        .card h3 {
            color: var(--primary-green);
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .contact-list li {
            margin-bottom: 10px;
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.1rem;
        }

        /* --- PAGE 2: NYSC & EDUCATION --- */
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            color: var(--primary-green);
            font-size: 2.2rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .nysc-content {
            background: var(--white);
            padding: 40px;
            border-radius: 8px;
            box-shadow: var(--shadow);
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .nysc-header {
            display: flex;
            align-items: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .nysc-img {
            width: 100%;
            max-width: 300px;
            height: auto;
            border-radius: 8px;
            border: 1px solid #ddd;
        }

        .nysc-text p {
            margin-bottom: 15px;
            font-size: 1.05rem;
        }

        .external-link {
            color: var(--primary-green);
            font-weight: bold;
            text-decoration: underline;
        }

        /* --- PAGE 3: SERVICES GRID --- */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }

        .service-card {
            background: var(--white);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
            display: flex;
            flex-direction: column;
        }

        .service-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(0,0,0,0.15);
        }

        .service-img {
            height: 160px;
            background-color: #ddd;
            object-fit: cover;
            width: 100%;
        }

        .service-body {
            padding: 20px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .service-icon {
            font-size: 2rem;
            color: var(--primary-green);
            margin-bottom: 10px;
        }

        .service-title {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 10px;
            color: var(--dark-green);
        }

        .service-desc {
            font-size: 0.95rem;
            color: var(--text-light);
            margin-bottom: 20px;
        }

        .service-btn {
            margin-top: auto;
            align-self: flex-start;
            color: var(--primary-green);
            font-weight: bold;
            border: 1px solid var(--primary-green);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.9rem;
            transition: var(--transition);
        }

        .service-btn:hover {
            background-color: var(--primary-green);
            color: var(--white);
        }

        /* --- FOOTER --- */
        footer {
            background-color: #222;
            color: var(--white);
            padding: 40px 20px;
            margin-top: 60px;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }

        .footer-col h4 {
            color: var(--primary-green);
            margin-bottom: 20px;
            font-size: 1.2rem;
        }

        .footer-col ul li {
            margin-bottom: 10px;
        }

        .footer-col ul li a:hover {
            color: var(--primary-green);
        }

        .copyright {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid #444;
            font-size: 0.9rem;
            color: #aaa;
        }

        /* --- FLOATING WHATSAPP AD --- */
        .whatsapp-float {
            position: fixed;
            width: 60px;
            height: 60px;
            bottom: 30px;
            right: 30px;
            background-color: #25d366;
            color: #FFF;
            border-radius: 50px;
            text-align: center;
            font-size: 30px;
            box-shadow: 2px 2px 3px #999;
            z-index: 100;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }

        .whatsapp-float:hover {
            transform: scale(1.1);
            background-color: #20b858;
        }

        /* --- GOOGLE ADSENSE PLACEHOLDER --- */
        .ad-container {
            width: 100%;
            height: 100px;
            background-color: #e0e0e0;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #888;
            border: 1px dashed #aaa;
            margin: 20px 0;
            font-size: 0.9rem;
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            .nav-links {
                display: none; /* Hide for simple implementation, normally toggleable */
            }
            .menu-toggle { display: block; }
            .hero h1 { font-size: 2rem; }
            .nysc-header { flex-direction: column; }
            .nysc-img { max-width: 100%; }
        }
    </style>
</head>
<body>

    <!-- Header / Navigation -->
    <header>
        <div class="navbar">
            <div class="logo">
                <i class="fa-solid fa-link"></i> MULTILINKS CONCEPT
            </div>
            <div class="menu-toggle">
                <i class="fa-solid fa-bars"></i>
            </div>
            <ul class="nav-links">
                <li class="nav-item active" onclick="showPage('home')">Home</li>
                <li class="nav-item" onclick="showPage('nysc')">NYSC & Education</li>
                <li class="nav-item" onclick="showPage('services')">Remote Cafe Services</li>
                <li class="nav-item" onclick="showPage('services')">Contact</li>
            </ul>
        </div>
    </header>

    <!-- Google Ad Placeholder -->
    <div class="ad-container">
        Google Advertisement Space
    </div>

    <!-- PAGE 1: HOME -->
    <section id="home" class="page-section active-page">
        <div class="hero">
            <h1>Multilinks Concept (Hub)</h1>
            <p>Your premier destination for Educational Information, NYSC Guidelines, JAMB Solutions, and Remote Cyber Cafe Services.</p>
            <div class="cta-btn" onclick="showPage('services')">Explore Our Services</div>
        </div>

        <div class="container">
            <div class="section-title">Welcome to Multilinks Concept</div>
            <p style="text-align: center; max-width: 800px; margin: 0 auto; color: #555;">
                We bridge the gap between students and success. From registration to certification, we provide seamless remote support for all your educational and corporate documentation needs. We are the Hub of solutions.
            </p>

            <div class="info-grid">
                <!-- Quick Contact Card -->
                <div class="card">
                    <h3><i class="fa-solid fa-phone"></i> Quick Contact</h3>
                    <ul class="contact-list">
                        <li><i class="fa-solid fa-envelope"></i> aladesulutaiwo@gmail.com</li>
                        <li><i class="fa-solid fa-envelope"></i> multilinksconcept@gmail.com</li>
                        <li><i class="fa-solid fa-phone"></i> 07035861155</li>
                        <li><i class="fa-brands fa-whatsapp"></i> 08118466763</li>
                    </ul>
                </div>

                <!-- Quick Links Card -->
                <div class="card">
                    <h3><i class="fa-solid fa-link"></i> Quick Links</h3>
                    <ul class="contact-list">
                        <li><i class="fa-solid fa-chevron-right"></i> <a href="https://portal.nysc.org.ng/nysc/" target="_blank">NYSC Official Portal</a></li>
                        <li><i class="fa-solid fa-chevron-right"></i> <a href="https://efacility.jamb.gov.ng/checkmatriculationlist" target="_blank">JAMB e-Facility</a></li>
                        <li><i class="fa-solid fa-chevron-right"></i> <a href="#" onclick="showPage('services')">Remote Cafe Services</a></li>
                    </ul>
                </div>

                <!-- About Us Card -->
                <div class="card">
                    <h3><i class="fa-solid fa-info-circle"></i> Who We Are</h3>
                    <p>A dedicated team providing remote support for NYSC, JAMB, School Fees, Legal Documentation, and more. Fast, reliable, and secure.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- PAGE 2: NYSC & EDUCATION INFO -->
    <section id="nysc" class="page-section">
        <div class="container">
            <div class="section-title">NYSC & Educational Information</div>
            
            <div class="nysc-content">
                <!-- NYSC Section -->
                <article class="nysc-header">
                    <!-- Image generated via Picsum to represent NYSC Camp/Reg -->
                    <img src="https://tse1.mm.bing.net/th/id/OIP.hekY7e32k_ZFXgTTkiB1VwHaFr?rs=1&pid=ImgDetMain&o=7&rm=3" alt="NYSC Orientation Camp Representation" class="nysc-img">
                    <div class="nysc-text">
                        <h2 style="color: var(--primary-green); margin-bottom: 15px;">NYSC Information & Guidelines</h2>
                        <p>
                            The National Youth Service Corps (NYSC) is a program set up by the Nigerian government to involve Nigerian graduates in nation building. 
                            Preparing for your service year requires attention to detail. At Multilinks Concept, we guide you through the entire pre-registration process on the 
                            <a href="https://www.nysc.gov.ng/about.html#:~:text=The%20NYSC%20scheme%20was%20created,The%20unfortunate%20antecedents%20in%20our" target="_blank" class="external-link">About NYSC Scheme</a>.
                        </p>
                        <p>
                            <strong>Key Requirements for Registration:</strong>
                        </p>
                        <ul style="list-style: disc; margin-left: 20px; color: #444;">
                            <li>Matriculation Number and Course of Study.</li>
                            <li>Correct Date of Birth (must match WAEC/NECO records).</li>
                            <li>Functional Gmail address (for receiving Call-up letters).</li>
                            <li>Scanned copies of passport photograph (white background) and signature.</li>
                            <li>Valid ID Card (National ID, International Passport, or Driver's License).</li>
                        </ul>
                        <p style="margin-top: 15px;">
                            We assist with correcting wrong information, date of birth modification, and ensuring smooth Senate List verification.
                        </p>
                    </div>
                </article>

                <hr style="border: 0; border-top: 1px solid #eee;">

                <!-- JAMB Section -->
                <article class="nysc-header">
                    <img src="https://efacility.jamb.gov.ng/assets/admin/img/logo_big.png" alt="JAMB Matriculation List" class="nysc-img">
                    <div class="nysc-text">
                        <h2 style="color: var(--primary-green); margin-bottom: 15px;">JAMB Matriculation List Solutions</h2>
                        <p>
                            Are you a Nigerian student seeking admission or regularization? The JAMB Matriculation List is the primary proof that you are a bona fide student of a tertiary institution. 
                            If your name is not on this list, you cannot be mobilized for NYSC.
                        </p>
                        <p>
                            We provide swift solutions for checking your name on the <a href="https://efacility.jamb.gov.ng/checkmatriculationlist" target="_blank" class="external-link">JAMB Matriculation List</a>, 
                            regularization of part-time students, and correction of data.
                        </p>
                    </div>
                </article>
            </div>
        </div>
    </section>

    <!-- PAGE 3: REMOTE CAFE SERVICES -->
    <section id="services" class="page-section">
        <div class="container">
            <div class="section-title">Our Remote Cafe Services</div>
            <p style="text-align: center; margin-bottom: 30px; color: #555;">
                We bring the Cyber Cafe to your fingertips. Click any service to contact us via WhatsApp or Call.
            </p>

            <div class="services-grid">
                
                <!-- Service 1: NYSC -->
                <div class="service-card">
                    <img src="https://portal.nysc.org.ng/nysc/img/homepage-slider/login.png" alt="NYSC Registration" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-users-viewfinder"></i></div>
                        <h3 class="service-title">NYSC Pre-Registration & Portal Link</h3>
                        <p class="service-desc">Full guidelines and registration support for prospective corps members via the official portal.</p>
                        <a href="https://portal.nysc.org.ng/nysc/" class="service-btn">Portal Link</a>
                    </div>
                </div>

                <!-- Service 2: JAMB -->
                <div class="service-card">
                    <img src="https://efacility.jamb.gov.ng/assets/admin/img/logo_big.png" alt="JAMB Solutions" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-graduation-cap"></i></div>
                        <h3 class="service-title">JAMB Matriculation List</h3>
                        <p class="service-desc">Check your name, regularize admission, and resolve JAMB related issues.</p>
                        <a href="https://efacility.jamb.gov.ng/checkmatriculationlist" class="service-btn">Check List</a>
                    </div>
                </div>

                <!-- Service 3: NERD -->
                <div class="service-card">
                    <img src="https://esmat.ned.gov.ng/ai/img/nerd_logo.png" alt="Project Upload" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-cloud-upload-alt"></i></div>
                        <h3 class="service-title">NERD & Project Upload</h3>
                        <p class="service-desc">Assistance with NERD registration and uploading final year projects/journals.</p>
                        <a href="https://wa.me/2348118466763?text=I%20need%20help%20with%20Project%20Upload" class="service-btn">Contact Us</a>
                    </div>
                </div>

                <!-- Service 4: School Fees -->
                <div class="service-card">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRVt86hdKP2dgv592RdCotX8kckmT0dtY0TTg&s" alt="School Fee Payment" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-money-bill-wave"></i></div>
                        <h3 class="service-title">School Fee & Certificate</h3>
                        <p class="service-desc">Remote payment of school fees, certificate fees, and processing transcript collection requests.</p>
                        <a href="https://wa.me/2348118466763?text=I%20want%20to%20pay%20School%20Fees" class="service-btn">Contact Us</a>
                    </div>
                </div>

                <!-- Service 5: Editing of Documents -->
                <div class="service-card">
                    <img src="https://www.scanwritr.com/wp-content/uploads/2018/05/screen4-1.png" alt="Document Editing" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-file-pen"></i></div>
                        <h3 class="service-title">Document Editing</h3>
                        <p class="service-desc">Professional editing of Word, PDF, Excel, and Images (Conversions, formatting, and corrections).</p>
                        <a href="https://wa.me/2348118466763?text=I%20need%20Document%20Editing%20services" class="service-btn">Contact Us</a>
                    </div>
                </div>

                <!-- Service 6: Professional CV Making -->
                <div class="service-card">
                    <img src="https://media.istockphoto.com/id/2198633806/photo/digital-editor-corrects-errors-in-manuscript.jpg?s=612x612&w=0&k=20&c=YRS0QEzwpBZlCokx31tshD-i9lPxhn-4HlYiXj8NDLA=" alt="CV Design" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-id-card"></i></div>
                        <h3 class="service-title">Professional CV Making</h3>
                        <p class="service-desc">Create a winning CV and Resume tailored to your dream job and sector.</p>
                        <a href="https://wa.me/2348118466763?text=I%20need%20a%20Professional%20CV" class="service-btn">Contact Us</a>
                    </div>
                </div>

                <!-- Service 7: Research -->
                <div class="service-card">
                    <img src="https://img.freepik.com/free-photo/cropped-photo-serious-young-man-sitting-office-coworking_171337-17650.jpg?semt=ais_hybrid&w=740&q=80" alt="Research Projects" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-magnifying-glass"></i></div>
                        <h3 class="service-title">Project/Journal Research</h3>
                        <p class="service-desc">Academic research assistance, abstract writing, and full project material compilation.</p>
                        <a href="https://wa.me/2348118466763?text=I%20need%20Project%20Research%20help" class="service-btn">Contact Us</a>
                    </div>
                </div>

                <!-- Service 8: Graphics -->
                <div class="service-card">
                    <img src="https://cdn.dribbble.com/userupload/10023163/file/original-d24712a6fde04b3bb159c32ce84cb70f.png?resize=400x0" alt="Graphics Design" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-palette"></i></div>
                        <h3 class="service-title">Graphics & ID Card</h3>
                        <p class="service-desc">High-quality ID Card design for schools, organizations, and events.</p>
                        <a href="https://wa.me/2348118466763?text=I%20need%20Graphics%20Design" class="service-btn">Contact Us</a>
                    </div>
                </div>

                <!-- Service 9: Exam PINs -->
                <div class="service-card">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRQsaTRei1JAGZwl2-XM_mY6ds1r10PVVtSUg&s" alt="Exam PINs" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-barcode"></i></div>
                        <h3 class="service-title">WAEC, NECO, JAMB PIN</h3>
                        <p class="service-desc">Quick delivery of Scratch cards and E-PINs for WAEC, NECO, NABTEB, and JAMB.</p>
                        <a href="https://wa.me/2348118466763?text=I%20want%20to%20buy%20Exam%20PINs" class="service-btn">Buy PIN</a>
                    </div>
                </div>

                <!-- Service 10: Legal Documents -->
                <div class="service-card">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR13M81wpTF-gX6xEWE70Fcjpw23XIQ5jx56Q&s" alt="Legal Documents" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-scale-balanced"></i></div>
                        <h3 class="service-title">Land Deed & Ownership</h3>
                        <p class="service-desc">Processing Land Deed of Agreements and Vehicle Change of Ownership documentation.</p>
                        <a href="https://wa.me/2348118466763?text=I%20need%20Legal%20Documentation" class="service-btn">Contact Us</a>
                    </div>
                </div>

                <!-- Service 11: CAC Registration and Others-->
                <div class="service-card">
                    <img src="data:image/jpeg;base64,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" alt="CAC Registration" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-building"></i></div>
                        <h3 class="service-title">CAC/SMEDAN Registration</h3>
                        <p class="service-desc">Business name registration and incorporation with the Corporate Affairs Commission.</p>
                        <a href="https://wa.me/2348118466763?text=I%20need%20CAC%20Registration" class="service-btn">Contact Us</a>
                    </div>
                </div>

                <!-- Service 12: NIN Related Services -->
                <div class="service-card">
                    <img src="https://nimc.gov.ng/assets/self-service-C_MhR-9l.png" alt="NIN Modification" class="service-img">
                    <div class="service-body">
                        <div class="service-icon"><i class="fa-solid fa-fingerprint"></i></div>
                        <h3 class="service-title">NIN Modification</h3>
                        <p class="service-desc">Support for National Identity Number (NIN) data modification and enrollment.</p>
                        <a href="https://wa.me/2348118466763?text=I%20need%20NIN%20Modification" class="service-btn">Contact Us</a>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-col">
                <h4>Multilinks Concept (Hub)</h4>
                <p>Your reliable partner for educational empowerment and remote documentation services.</p>
            </div>
            <div class="footer-col">
                <h4>Contact Us</h4>
                <ul>
                    <li><i class="fa-solid fa-envelope"></i> aladesulutaiwo@gmail.com</li>
                    <li><i class="fa-solid fa-envelope"></i> multilinksconcept@gmail.com</li>
                    <li><i class="fa-solid fa-phone"></i> 07035861155</li>
                    <li><i class="fa-brands fa-whatsapp"></i> 08118466763</li>
                </ul>
            </div>
            <div class="footer-col">
                <h4>Useful Links</h4>
                <ul>
                    <li><a href="https://portal.nysc.org.ng/nysc/">NYSC Portal</a></li>
                    <li><a href="https://efacility.jamb.gov.ng/checkmatriculationlist">JAMB Matriculation List</a></li>
                    <li><a href="#" onclick="showPage('home')">Back to Home</a></li>
                </ul>
            </div>
        </div>
        <div class="copyright">
            &copy; 2026 Multilinks Concept (Hub). All Rights Reserved.
        </div>
    </footer>

    <!-- Floating WhatsApp Button -->
    <a href="https://wa.me/2348118466763" class="whatsapp-float" target="_blank" title="Chat on WhatsApp">
        <i class="fa-brands fa-whatsapp"></i>
    </a>

    <!-- JavaScript for Page Navigation (3 Pages Logic) -->
    <script>
        function showPage(pageId) {
            // Hide all pages
            const pages = document.querySelectorAll('.page-section');
            pages.forEach(page => {
                page.classList.remove('active-page');
            });

            // Remove active class from nav items
            const navItems = document.querySelectorAll('.nav-item');
            navItems.forEach(item => {
                item.classList.remove('active');
            });

            // Show selected page
            document.getElementById(pageId).classList.add('active-page');

            // Highlight active nav item (approximate matching)
            // Find the nav item that calls this function with pageId
            navItems.forEach(item => {
                if(item.getAttribute('onclick').includes(pageId)) {
                    item.classList.add('active');
                }
            });

            // Scroll to top
            window.scrollTo(0, 0);
        }

        // Simple Mobile Menu Toggle
        const menuToggle = document.querySelector('.menu-toggle');
        const navLinks = document.querySelector('.nav-links');

        menuToggle.addEventListener('click', () => {
            if (navLinks.style.display === 'flex') {
                navLinks.style.display = 'none';
            } else {
                navLinks.style.display = 'flex';
                navLinks.style.flexDirection = 'column';
                navLinks.style.position = 'absolute';
                navLinks.style.top = '60px';
                navLinks.style.left = '0';
                navLinks.style.width = '100%';
                navLinks.style.backgroundColor = '#fff';
                navLinks.style.padding = '20px';
                navLinks.style.boxShadow = '0 4px 6px rgba(0,0,0,0.1)';
            }
        });
    </script>
</body>
</html>
