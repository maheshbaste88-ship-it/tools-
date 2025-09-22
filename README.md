# tools-<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ToolKit Pro - Your All-in-One Online Tools Solution</title>
    <meta name="description" content="Free online tools for images, PDFs, and more. Optimize, convert, and edit files with our easy-to-use tools.">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/pdf-lib/1.17.1/pdf-lib.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
    <style>
        :root {
            --primary: #4361ee;
            --secondary: #3a0ca3;
            --accent: #7209b7;
            --success: #4cc9f0;
            --light: #f8f9fa;
            --dark: #212529;
            --gray: #6c757d;
            --border-radius: 12px;
            --box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
            text-decoration: none;
        }

        .logo i {
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--dark);
            font-weight: 600;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: var(--primary);
            transition: var(--transition);
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            font-size: 1.5rem;
            color: var(--dark);
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            padding: 80px 0;
            text-align: center;
            background: linear-gradient(135deg, var(--primary) 0%, var(--secondary) 100%);
            color: white;
            border-radius: 0 0 var(--border-radius) var(--border-radius);
            margin-bottom: 50px;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }

        .hero p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto 30px;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            background: white;
            color: var(--primary);
            padding: 15px 30px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .cta-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
        }

        /* Tools Section */
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            font-size: 2.5rem;
            color: var(--secondary);
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: var(--accent);
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }

        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 80px;
        }

        .tool-card {
            background: white;
            border-radius: var(--border-radius);
            overflow: hidden;
            box-shadow: var(--box-shadow);
            transition: var(--transition);
            position: relative;
        }

        .tool-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }

        .tool-icon {
            height: 120px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--accent) 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            color: white;
        }

        .tool-content {
            padding: 25px;
        }

        .tool-content h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--secondary);
        }

        .tool-content p {
            color: var(--gray);
            margin-bottom: 20px;
        }

        .tool-link {
            display: inline-block;
            background: var(--primary);
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
        }

        .tool-link:hover {
            background: var(--secondary);
        }

        /* Features Section */
        .features {
            background: white;
            padding: 80px 0;
            border-radius: var(--border-radius);
            margin-bottom: 80px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
        }

        .feature {
            text-align: center;
            padding: 0 20px;
        }

        .feature-icon {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, var(--success) 0%, var(--primary) 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 2rem;
            color: white;
        }

        .feature h3 {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: var(--secondary);
        }

        .feature p {
            color: var(--gray);
        }

        /* Testimonials */
        .testimonials {
            margin-bottom: 80px;
        }

        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .testimonial {
            background: white;
            padding: 30px;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            position: relative;
        }

        .testimonial::before {
            content: '"';
            position: absolute;
            top: 10px;
            left: 20px;
            font-size: 5rem;
            color: rgba(67, 97, 238, 0.1);
            font-family: Georgia, serif;
        }

        .testimonial p {
            font-style: italic;
            margin-bottom: 20px;
            position: relative;
            z-index: 1;
        }

        .testimonial-author {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .author-avatar {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--primary);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }

        .author-info h4 {
            color: var(--secondary);
            margin-bottom: 5px;
        }

        .author-info p {
            font-style: normal;
            font-size: 0.9rem;
            color: var(--gray);
            margin: 0;
        }

        /* Footer */
        footer {
            background: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            color: var(--success);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #adb5bd;
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: white;
            padding-left: 5px;
        }

        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            text-decoration: none;
            transition: var(--transition);
        }

        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #adb5bd;
            font-size: 0.9rem;
        }

        /* Tool Modal Styles */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.7);
            z-index: 1000;
            overflow-y: auto;
        }

        .modal-content {
            background: white;
            margin: 50px auto;
            padding: 30px;
            border-radius: var(--border-radius);
            width: 90%;
            max-width: 800px;
            position: relative;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--gray);
            transition: var(--transition);
        }

        .close-modal:hover {
            color: var(--dark);
        }

        .modal-title {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: var(--secondary);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tool-interface {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
        }

        @media (min-width: 768px) {
            .tool-interface {
                grid-template-columns: 1fr 1fr;
            }
        }

        .upload-area {
            border: 3px dashed var(--primary);
            border-radius: var(--border-radius);
            padding: 40px 20px;
            text-align: center;
            cursor: pointer;
            transition: var(--transition);
        }

        .upload-area:hover {
            background: rgba(67, 97, 238, 0.05);
        }

        .upload-area i {
            font-size: 3rem;
            color: var(--primary);
            margin-bottom: 15px;
        }

        .tool-controls {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .control-group {
            margin-bottom: 15px;
        }

        .control-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }

        .slider-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .slider-container input[type="range"] {
            flex: 1;
            height: 8px;
            -webkit-appearance: none;
            appearance: none;
            background: #ddd;
            border-radius: 4px;
            outline: none;
        }

        .slider-container input[type="range"]::-webkit-slider-thumb {
            -webkit-appearance: none;
            appearance: none;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: var(--primary);
            cursor: pointer;
        }

        .slider-value {
            font-weight: 600;
            color: var(--primary);
            min-width: 50px;
            text-align: center;
        }

        .tool-button {
            background: var(--primary);
            color: white;
            border: none;
            padding: 12px 20px;
            border-radius: var(--border-radius);
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }

        .tool-button:hover {
            background: var(--secondary);
        }

        .tool-button:disabled {
            background: var(--gray);
            cursor: not-allowed;
        }

        .results {
            margin-top: 30px;
            display: none;
        }

        .results-title {
            font-size: 1.4rem;
            margin-bottom: 15px;
            color: var(--secondary);
        }

        .image-comparison {
            display: grid;
            grid-template-columns: 1fr;
            gap: 20px;
            margin-bottom: 20px;
        }

        @media (min-width: 768px) {
            .image-comparison {
                grid-template-columns: 1fr 1fr;
            }
        }

        .image-box {
            text-align: center;
        }

        .image-box h4 {
            margin-bottom: 10px;
            color: var(--dark);
        }

        .image-placeholder {
            width: 100%;
            height: 200px;
            background: #f5f7fb;
            border-radius: var(--border-radius);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--gray);
            overflow: hidden;
            border: 1px solid #e2e8f0;
        }

        .image-placeholder img {
            max-width: 100%;
            max-height: 100%;
            object-fit: contain;
        }

        .stats-box {
            background: #f5f7fb;
            border-radius: var(--border-radius);
            padding: 15px;
            border: 1px solid #e2e8f0;
        }

        .stat {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid #ddd;
        }

        .stat:last-child {
            border-bottom: none;
        }

        .loading {
            display: none;
            text-align: center;
            margin: 20px 0;
        }

        .loading-spinner {
            border: 5px solid #f3f3f3;
            border-top: 5px solid var(--primary);
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 0 auto;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        /* Responsive Styles */
        @media (max-width: 992px) {
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .nav-links {
                gap: 20px;
            }
        }

        @media (max-width: 768px) {
            .navbar {
                flex-wrap: wrap;
            }
            
            .nav-links {
                display: none;
                width: 100%;
                flex-direction: column;
                gap: 15px;
                margin-top: 20px;
            }
            
            .nav-links.active {
                display: flex;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }

        @media (max-width: 576px) {
            .hero {
                padding: 60px 0;
            }
            
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .tools-grid {
                grid-template-columns: 1fr;
            }
            
            .features-grid {
                grid-template-columns: 1fr;
            }
            
            .modal-content {
                padding: 20px;
                margin: 20px auto;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <nav class="navbar">
                <a href="#" class="logo">
                    <i class="fas fa-toolbox"></i>
                    ToolKit Pro
                </a>
                
                <button class="mobile-menu-btn" id="mobileMenuBtn">
                    <i class="fas fa-bars"></i>
                </button>
                
                <div class="nav-links" id="navLinks">
                    <a href="#">Home</a>
                    <a href="#image-tools">Image Tools</a>
                    <a href="#pdf-tools">PDF Tools</a>
                    <a href="#">Other Tools</a>
                    <a href="#">Pricing</a>
                    <a href="#">Contact</a>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>All Your File Tools in One Place</h1>
            <p>Optimize, convert, edit, and enhance your images and PDFs with our powerful, easy-to-use online tools. No installation required.</p>
            <a href="#image-tools" class="cta-button">Explore Tools <i class="fas fa-arrow-right"></i></a>
        </div>
    </section>

    <!-- Image Tools Section -->
    <div class="container" id="image-tools">
        <h2 class="section-title">Image Tools</h2>
        
        <div class="tools-grid">
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-compress-alt"></i>
                </div>
                <div class="tool-content">
                    <h3>Image Compressor</h3>
                    <p>Reduce image file size without losing quality. Perfect for web optimization.</p>
                    <a href="#" class="tool-link" data-tool="compressor">Use Tool</a>
                </div>
            </div>
            
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-exchange-alt"></i>
                </div>
                <div class="tool-content">
                    <h3>Image Converter</h3>
                    <p>Convert between JPG, PNG, WEBP, and other popular image formats.</p>
                    <a href="#" class="tool-link" data-tool="converter">Use Tool</a>
                </div>
            </div>
            
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-crop-alt"></i>
                </div>
                <div class="tool-content">
                    <h3>Image Resizer</h3>
                    <p>Resize images to exact dimensions while maintaining aspect ratio.</p>
                    <a href="#" class="tool-link" data-tool="resizer">Use Tool</a>
                </div>
            </div>
        </div>
    </div>

    <!-- PDF Tools Section -->
    <div class="container" id="pdf-tools">
        <h2 class="section-title">PDF Tools</h2>
        
        <div class="tools-grid">
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-file-pdf"></i>
                </div>
                <div class="tool-content">
                    <h3>PDF Compressor</h3>
                    <p>Reduce PDF file size for easier sharing and storage.</p>
                    <a href="#" class="tool-link" data-tool="pdf-compressor">Use Tool</a>
                </div>
            </div>
            
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-file-word"></i>
                </div>
                <div class="tool-content">
                    <h3>PDF to Image</h3>
                    <p>Convert PDF pages to high-quality images (JPG, PNG).</p>
                    <a href="#" class="tool-link" data-tool="pdf-to-image">Use Tool</a>
                </div>
            </div>
            
            <div class="tool-card">
                <div class="tool-icon">
                    <i class="fas fa-lock"></i>
                </div>
                <div class="tool-content">
                    <h3>PDF Merger</h3>
                    <p>Combine multiple PDF files into a single document.</p>
                    <a href="#" class="tool-link" data-tool="pdf-merger">Use Tool</a>
                </div>
            </div>
        </div>
    </div>

    <!-- Features Section -->
    <section class="features">
        <div class="container">
            <h2 class="section-title">Why Choose Our Tools</h2>
            
            <div class="features-grid">
                <div class="feature">
                    <div class="feature-icon">
                        <i class="fas fa-bolt"></i>
                    </div>
                    <h3>Lightning Fast</h3>
                    <p>Our tools process files quickly, saving you valuable time.</p>
                </div>
                
                <div class="feature">
                    <div class="feature-icon">
                        <i class="fas fa-shield-alt"></i>
                    </div>
                    <h3>Secure & Private</h3>
                    <p>Your files are processed securely and never stored on our servers.</p>
                </div>
                
                <div class="feature">
                    <div class="feature-icon">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <h3>Mobile Friendly</h3>
                    <p>Access our tools from any device, anywhere, anytime.</p>
                </div>
                
                <div class="feature">
                    <div class="feature-icon">
                        <i class="fas fa-tags"></i>
                    </div>
                    <h3>Free to Use</h3>
                    <p>Most of our tools are completely free with no hidden costs.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <div class="container">
        <h2 class="section-title">What Our Users Say</h2>
        
        <div class="testimonial-grid">
            <div class="testimonial">
                <p>This website saved me so much time! The image compression tool is fantastic and reduced my website loading time significantly.</p>
                <div class="testimonial-author">
                    <div class="author-avatar">JS</div>
                    <div class="author-info">
                        <h4>John Smith</h4>
                        <p>Web Developer</p>
                    </div>
                </div>
            </div>
            
            <div class="testimonial">
                <p>As a student, I frequently need to convert documents. The PDF to Word converter works perfectly every time.</p>
                <div class="testimonial-author">
                    <div class="author-avatar">MJ</div>
                    <div class="author-info">
                        <h4>Maria Johnson</h4>
                        <p>University Student</p>
                    </div>
                </div>
            </div>
            
            <div class="testimonial">
                <p>I use these tools daily for my small business. They're reliable, fast, and completely free. Highly recommended!</p>
                <div class="testimonial-author">
                    <div class="author-avatar">RD</div>
                    <div class="author-info">
                        <h4>Robert Davis</h4>
                        <p>Small Business Owner</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>ToolKit Pro</h3>
                    <p>Your all-in-one solution for image and PDF tools. Fast, secure, and easy to use.</p>
                    <div class="social-links">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3>Image Tools</h3>
                    <ul class="footer-links">
                        <li><a href="#" data-tool="compressor">Image Compressor</a></li>
                        <li><a href="#" data-tool="converter">Image Converter</a></li>
                        <li><a href="#" data-tool="resizer">Image Resizer</a></li>
                        <li><a href="#">Watermark Tool</a></li>
                        <li><a href="#">Background Remover</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>PDF Tools</h3>
                    <ul class="footer-links">
                        <li><a href="#" data-tool="pdf-compressor">PDF Compressor</a></li>
                        <li><a href="#" data-tool="pdf-to-image">PDF to Image</a></li>
                        <li><a href="#" data-tool="pdf-merger">PDF Merger</a></li>
                        <li><a href="#">PDF Splitter</a></li>
                        <li><a href="#">PDF Editor</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Company</h3>
                    <ul class="footer-links">
                        <li><a href="#">About Us</a></li>
                        <li><a href="#">Contact</a></li>
                        <li><a href="#">Privacy Policy</a></li>
                        <li><a href="#">Terms of Service</a></li>
                        <li><a href="#">Blog</a></li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 ToolKit Pro. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <!-- Tool Modals -->
    <div id="tool-modal" class="modal">
        <div class="modal-content">
            <span class="close-modal">&times;</span>
            <h2 class="modal-title" id="modal-title"><i class="fas fa-cog"></i> Tool</h2>
            
            <div class="tool-interface" id="tool-interface">
                <!-- Tool content will be inserted here dynamically -->
            </div>
        </div>
    </div>

    <script>
        // Mobile menu toggle
        document.getElementById('mobileMenuBtn').addEventListener('click', function() {
            document.getElementById('navLinks').classList.toggle('active');
        });

        // Tool modal functionality
        const modal = document.getElementById('tool-modal');
        const modalTitle = document.getElementById('modal-title');
        const toolInterface = document.getElementById('tool-interface');
        const closeModal = document.querySelector('.close-modal');
        
        // Close modal when clicking X or outside
        closeModal.addEventListener('click', () => {
            modal.style.display = 'none';
        });
        
        window.addEventListener('click', (e) => {
            if (e.target === modal) {
                modal.style.display = 'none';
            }
        });
        
        // Tool links
        document.querySelectorAll('.tool-link, .footer-links a[data-tool]').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const tool = this.getAttribute('data-tool');
                openToolModal(tool);
            });
        });
        
        // Open tool modal with specific tool
        function openToolModal(tool) {
            modal.style.display = 'block';
            
            // Set modal title and content based on tool
            switch(tool) {
                case 'compressor':
                    modalTitle.innerHTML = '<i class="fas fa-compress-alt"></i> Image Compressor';
                    toolInterface.innerHTML = getImageCompressorHTML();
                    break;
                case 'converter':
                    modalTitle.innerHTML = '<i class="fas fa-exchange-alt"></i> Image Converter';
                    toolInterface.innerHTML = getImageConverterHTML();
                    break;
                case 'resizer':
                    modalTitle.innerHTML = '<i class="fas fa-crop-alt"></i> Image Resizer';
                    toolInterface.innerHTML = getImageResizerHTML();
                    break;
                case 'pdf-compressor':
                    modalTitle.innerHTML = '<i class="fas fa-file-pdf"></i> PDF Compressor';
                    toolInterface.innerHTML = getPDFCompressorHTML();
                    break;
                case 'pdf-to-image':
                    modalTitle.innerHTML = '<i class="fas fa-file-image"></i> PDF to Image Converter';
                    toolInterface.innerHTML = getPDFToImageHTML();
                    break;
                case 'pdf-merger':
                    modalTitle.innerHTML = '<i class="fas fa-object-group"></i> PDF Merger';
                    toolInterface.innerHTML = getPDFMergerHTML();
                    break;
            }
            
            // Initialize the tool functionality
            initializeTool(tool);
        }
        
        // Get HTML for Image Compressor tool
        function getImageCompressorHTML() {
            return `
                <div class="upload-area" id="upload-area">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Drag & Drop your image here</p>
                    <p>or</p>
                    <span><i class="fas fa-file-image"></i> Select Image</span>
                    <input type="file" id="file-input" accept="image/*" style="display: none;">
                </div>
                <div class="tool-controls">
                    <div class="control-group">
                        <label for="compression-level">Compression Level</label>
                        <div class="slider-container">
                            <input type="range" id="compression-level" min="0" max="100" value="70">
                            <span class="slider-value" id="compression-value">70%</span>
                        </div>
                    </div>
                    <div class="control-group">
                        <label for="image-quality">Image Quality</label>
                        <div class="slider-container">
                            <input type="range" id="image-quality" min="10" max="100" value="80">
                            <span class="slider-value" id="quality-value">80%</span>
                        </div>
                    </div>
                    <button class="tool-button" id="compress-btn">Compress Image</button>
                    <div class="loading" id="loading">
                        <div class="loading-spinner"></div>
                        <p>Compressing image...</p>
                    </div>
                    <div class="results" id="results">
                        <h3 class="results-title">Compression Results</h3>
                        <div class="image-comparison">
                            <div class="image-box">
                                <h4>Original Image</h4>
                                <div class="image-placeholder" id="original-image">
                                    <p>No image selected</p>
                                </div>
                            </div>
                            <div class="image-box">
                                <h4>Compressed Image</h4>
                                <div class="image-placeholder" id="compressed-image">
                                    <p>Compressed image will appear here</p>
                                </div>
                            </div>
                        </div>
                        <div class="stats-box">
                            <div class="stat">
                                <span>Original Size:</span>
                                <span id="original-size">0 KB</span>
                            </div>
                            <div class="stat">
                                <span>Compressed Size:</span>
                                <span id="compressed-size">0 KB</span>
                            </div>
                            <div class="stat">
                                <span>Size Reduction:</span>
                                <span id="reduction">0%</span>
                            </div>
                        </div>
                        <button class="tool-button" id="download-btn"><i class="fas fa-download"></i> Download Compressed Image</button>
                    </div>
                </div>
            `;
        }
        
        // Get HTML for Image Converter tool
        function getImageConverterHTML() {
            return `
                <div class="upload-area" id="upload-area">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Drag & Drop your image here</p>
                    <p>or</p>
                    <span><i class="fas fa-file-image"></i> Select Image</span>
                    <input type="file" id="file-input" accept="image/*" style="display: none;">
                </div>
                <div class="tool-controls">
                    <div class="control-group">
                        <label for="format-select">Convert To</label>
                        <select id="format-select" class="tool-button" style="width: 100%; padding: 12px;">
                            <option value="jpg">JPG</option>
                            <option value="png">PNG</option>
                            <option value="webp">WEBP</option>
                        </select>
                    </div>
                    <div class="control-group">
                        <label for="image-quality">Image Quality</label>
                        <div class="slider-container">
                            <input type="range" id="image-quality" min="10" max="100" value="90">
                            <span class="slider-value" id="quality-value">90%</span>
                        </div>
                    </div>
                    <button class="tool-button" id="convert-btn">Convert Image</button>
                    <div class="loading" id="loading">
                        <div class="loading-spinner"></div>
                        <p>Converting image...</p>
                    </div>
                    <div class="results" id="results">
                        <h3 class="results-title">Conversion Results</h3>
                        <div class="image-comparison">
                            <div class="image-box">
                                <h4>Original Image</h4>
                                <div class="image-placeholder" id="original-image">
                                    <p>No image selected</p>
                                </div>
                            </div>
                            <div class="image-box">
                                <h4>Converted Image</h4>
                                <div class="image-placeholder" id="converted-image">
                                    <p>Converted image will appear here</p>
                                </div>
                            </div>
                        </div>
                        <button class="tool-button" id="download-btn"><i class="fas fa-download"></i> Download Converted Image</button>
                    </div>
                </div>
            `;
        }
        
        // Get HTML for Image Resizer tool
        function getImageResizerHTML() {
            return `
                <div class="upload-area" id="upload-area">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Drag & Drop your image here</p>
                    <p>or</p>
                    <span><i class="fas fa-file-image"></i> Select Image</span>
                    <input type="file" id="file-input" accept="image/*" style="display: none;">
                </div>
                <div class="tool-controls">
                    <div class="control-group">
                        <label for="width-input">Width (px)</label>
                        <input type="number" id="width-input" class="tool-button" style="width: 100%; padding: 12px;" placeholder="Enter width" value="800">
                    </div>
                    <div class="control-group">
                        <label for="height-input">Height (px)</label>
                        <input type="number" id="height-input" class="tool-button" style="width: 100%; padding: 12px;" placeholder="Enter height" value="600">
                    </div>
                    <div class="control-group">
                        <label>
                            <input type="checkbox" id="maintain-aspect" checked> Maintain aspect ratio
                        </label>
                    </div>
                    <button class="tool-button" id="resize-btn">Resize Image</button>
                    <div class="loading" id="loading">
                        <div class="loading-spinner"></div>
                        <p>Resizing image...</p>
                    </div>
                    <div class="results" id="results">
                        <h3 class="results-title">Resize Results</h3>
                        <div class="image-comparison">
                            <div class="image-box">
                                <h4>Original Image</h4>
                                <div class="image-placeholder" id="original-image">
                                    <p>No image selected</p>
                                </div>
                            </div>
                            <div class="image-box">
                                <h4>Resized Image</h4>
                                <div class="image-placeholder" id="resized-image">
                                    <p>Resized image will appear here</p>
                                </div>
                            </div>
                        </div>
                        <button class="tool-button" id="download-btn"><i class="fas fa-download"></i> Download Resized Image</button>
                    </div>
                </div>
            `;
        }
        
        // Get HTML for PDF tools (simplified for demo)
        function getPDFCompressorHTML() {
            return `
                <div class="upload-area" id="upload-area">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Drag & Drop your PDF file here</p>
                    <p>or</p>
                    <span><i class="fas fa-file-pdf"></i> Select PDF</span>
                    <input type="file" id="file-input" accept=".pdf" style="display: none;">
                </div>
                <div class="tool-controls">
                    <div class="control-group">
                        <label for="compression-level">Compression Level</label>
                        <div class="slider-container">
                            <input type="range" id="compression-level" min="0" max="100" value="70">
                            <span class="slider-value" id="compression-value">70%</span>
                        </div>
                    </div>
                    <button class="tool-button" id="compress-btn">Compress PDF</button>
                    <div class="loading" id="loading">
                        <div class="loading-spinner"></div>
                        <p>Compressing PDF...</p>
                    </div>
                    <div class="results" id="results">
                        <h3 class="results-title">PDF Compression Results</h3>
                        <div class="stats-box">
                            <div class="stat">
                                <span>Original Size:</span>
                                <span id="original-size">0 KB</span>
                            </div>
                            <div class="stat">
                                <span>Compressed Size:</span>
                                <span id="compressed-size">0 KB</span>
                            </div>
                            <div class="stat">
                                <span>Size Reduction:</span>
                                <span id="reduction">0%</span>
                            </div>
                        </div>
                        <button class="tool-button" id="download-btn"><i class="fas fa-download"></i> Download Compressed PDF</button>
                    </div>
                </div>
            `;
        }
        
        function getPDFToImageHTML() {
            return `
                <div class="upload-area" id="upload-area">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Drag & Drop your PDF file here</p>
                    <p>or</p>
                    <span><i class="fas fa-file-pdf"></i> Select PDF</span>
                    <input type="file" id="file-input" accept=".pdf" style="display: none;">
                </div>
                <div class="tool-controls">
                    <div class="control-group">
                        <label for="format-select">Convert To</label>
                        <select id="format-select" class="tool-button" style="width: 100%; padding: 12px;">
                            <option value="jpg">JPG</option>
                            <option value="png">PNG</option>
                        </select>
                    </div>
                    <div class="control-group">
                        <label for="page-range">Page Range (e.g., 1-3,5)</label>
                        <input type="text" id="page-range" class="tool-button" style="width: 100%; padding: 12px;" placeholder="All pages" value="">
                    </div>
                    <button class="tool-button" id="convert-btn">Convert PDF to Images</button>
                    <div class="loading" id="loading">
                        <div class="loading-spinner"></div>
                        <p>Converting PDF...</p>
                    </div>
                    <div class="results" id="results">
                        <h3 class="results-title">PDF to Image Results</h3>
                        <div id="converted-images" style="display: grid; grid-template-columns: repeat(auto-fill, minmax(200px, 1fr)); gap: 15px; margin-bottom: 20px;">
                            <p>Converted images will appear here</p>
                        </div>
                        <button class="tool-button" id="download-btn"><i class="fas fa-download"></i> Download All Images as ZIP</button>
                    </div>
                </div>
            `;
        }
        
        function getPDFMergerHTML() {
            return `
                <div class="upload-area" id="upload-area" style="min-height: 200px;">
                    <i class="fas fa-cloud-upload-alt"></i>
                    <p>Drag & Drop your PDF files here</p>
                    <p>or</p>
                    <span><i class="fas fa-file-pdf"></i> Select PDFs</span>
                    <input type="file" id="file-input" accept=".pdf" multiple style="display: none;">
                </div>
                <div class="tool-controls">
                    <div id="file-list" style="margin-bottom: 20px;"></div>
                    <button class="tool-button" id="merge-btn">Merge PDFs</button>
                    <div class="loading" id="loading">
                        <div class="loading-spinner"></div>
                        <p>Merging PDFs...</p>
                    </div>
                    <div class="results" id="results">
                        <h3 class="results-title">PDF Merge Results</h3>
                        <div class="stats-box">
                            <div class="stat">
                                <span>Merged PDF Size:</span>
                                <span id="merged-size">0 KB</span>
                            </div>
                            <div class="stat">
                                <span>Number of Pages:</span>
                                <span id="page-count">0</span>
                            </div>
                        </div>
                        <button class="tool-button" id="download-btn"><i class="fas fa-download"></i> Download Merged PDF</button>
                    </div>
                </div>
            `;
        }
        
        // Initialize tool functionality
        function initializeTool(tool) {
            // Common file upload functionality
            const uploadArea = document.getElementById('upload-area');
            const fileInput = document.getElementById('file-input');
            
            if (uploadArea && fileInput) {
                uploadArea.addEventListener('click', () => {
                    fileInput.click();
                });
                
                fileInput.addEventListener('change', handleFileSelect);
                
                // Drag and drop functionality
                ['dragenter', 'dragover', 'dragleave', 'drop'].forEach(eventName => {
                    uploadArea.addEventListener(eventName, preventDefaults, false);
                });
                
                function preventDefaults(e) {
                    e.preventDefault();
                    e.stopPropagation();
                }
                
                ['dragenter', 'dragover'].forEach(eventName => {
                    uploadArea.addEventListener(eventName, highlight, false);
                });
                
                ['dragleave', 'drop'].forEach(eventName => {
                    uploadArea.addEventListener(eventName, unhighlight, false);
                });
                
                function highlight() {
                    uploadArea.style.borderColor = 'var(--secondary)';
                    uploadArea.style.backgroundColor = 'rgba(67, 97, 238, 0.1)';
                }
                
                function unhighlight() {
                    uploadArea.style.borderColor = 'var(--primary)';
                    uploadArea.style.backgroundColor = 'transparent';
                }
                
                uploadArea.addEventListener('drop', handleDrop, false);
                
                function handleDrop(e) {
                    const dt = e.dataTransfer;
                    const files = dt.files;
                    if (files.length) {
                        handleFiles(files);
                    }
                }
                
                function handleFileSelect(e) {
                    const files = e.target.files;
                    if (files.length) {
                        handleFiles(files);
                    }
                }
                
                function handleFiles(files) {
                    // Tool-specific file handling
                    if (tool.includes('pdf')) {
                        handlePDFFiles(files, tool);
                    } else {
                        handleImageFiles(files, tool);
                    }
                }
            }
            
            // Tool-specific initialization
            switch(tool) {
                case 'compressor':
                    initImageCompressor();
                    break;
                case 'converter':
                    initImageConverter();
                    break;
                case 'resizer':
                    initImageResizer();
                    break;
                case 'pdf-compressor':
                    initPDFCompressor();
                    break;
                case 'pdf-to-image':
                    initPDFToImage();
                    break;
                case 'pdf-merger':
                    initPDFMerger();
                    break;
            }
        }
        
        // Image file handling
        function handleImageFiles(files, tool) {
            const file = files[0];
            if (!file.type.match('image.*')) {
                alert('Please select an image file.');
                return;
            }
            
            const reader = new FileReader();
            reader.onload = function(e) {
                const img = new Image();
                img.onload = function() {
                    // Display original image
                    const originalImage = document.getElementById('original-image');
                    if (originalImage) {
                        originalImage.innerHTML = '';
                        const displayedImg = document.createElement('img');
                        displayedImg.src = e.target.result;
                        originalImage.appendChild(displayedImg);
                    }
                    
                    // Store file data for processing
                    window.currentFile = file;
                    window.originalImageData = e.target.result;
                };
                img.src = e.target.result;
            };
            reader.readAsDataURL(file);
        }
        
        // PDF file handling
        function handlePDFFiles(files, tool) {
            if (tool === 'pdf-merger') {
                // For merger, handle multiple files
                window.pdfFiles = window.pdfFiles || [];
                window.pdfFiles.push(...files);
                
                // Update file list
                const fileList = document.getElementById('file-list');
                if (fileList) {
                    fileList.innerHTML = '';
                    window.pdfFiles.forEach((file, index) => {
                        const fileItem = document.createElement('div');
                        fileItem.className = 'stat';
                        fileItem.innerHTML = `
                            <span>${file.name}</span>
                            <span>${(file.size / 1024).toFixed(2)} KB</span>
                        `;
                        fileList.appendChild(fileItem);
                    });
                }
            } else {
                // For single PDF tools
                const file = files[0];
                if (!file.type.includes('pdf') && !file.name.toLowerCase().endsWith('.pdf')) {
                    alert('Please select a PDF file.');
                    return;
                }
                
                window.currentFile = file;
                
                // Display file info
                const originalSize = document.getElementById('original-size');
                if (originalSize) {
                    originalSize.textContent = `${(file.size / 1024).toFixed(2)} KB`;
                }
            }
        }
        
        // Initialize Image Compressor
        function initImageCompressor() {
            const compressionLevel = document.getElementById('compression-level');
            const compressionValue = document.getElementById('compression-value');
            const imageQuality = document.getElementById('image-quality');
            const qualityValue = document.getElementById('quality-value');
            const compressBtn = document.getElementById('compress-btn');
            const downloadBtn = document.getElementById('download-btn');
            const loading = document.getElementById('loading');
            const results = document.getElementById('results');
            
            // Update slider values
            if (compressionLevel && compressionValue) {
                compressionLevel.addEventListener('input', () => {
                    compressionValue.textContent = `${compressionLevel.value}%`;
                });
            }
            
            if (imageQuality && qualityValue) {
                imageQuality.addEventListener('input', () => {
                    qualityValue.textContent = `${imageQuality.value}%`;
                });
            }
            
            // Compression function
            if (compressBtn) {
                compressBtn.addEventListener('click', compressImage);
            }
            
            function compressImage() {
                if (!window.currentFile) {
                    alert('Please select an image first.');
                    return;
                }
                
                loading.style.display = 'block';
                compressBtn.disabled = true;
                
                setTimeout(() => {
                    const img = new Image();
                    img.onload = function() {
                        // Create canvas
                        const canvas = document.createElement('canvas');
                        canvas.width = img.width;
                        canvas.height = img.height;
                        const ctx = canvas.getContext('2d');
                        ctx.drawImage(img, 0, 0);
                        
                        // Get quality value
                        const qualityValue = parseInt(document.getElementById('image-quality').value) / 100;
                        
                        // Get compressed image data
                        const compressedDataURL = canvas.toDataURL('image/jpeg', qualityValue);
                        window.compressedImageData = compressedDataURL;
                        
                        // Display compressed image
                        const compressedImage = document.getElementById('compressed-image');
                        if (compressedImage) {
                            compressedImage.innerHTML = '';
                            const compressedImg = document.createElement('img');
                            compressedImg.src = compressedDataURL;
                            compressedImage.appendChild(compressedImg);
                        }
                        
                        // Calculate compressed size
                        const compressedSizeBytes = calculateImageSize(compressedDataURL);
                        const compressedSizeElement = document.getElementById('compressed-size');
                        if (compressedSizeElement) {
                            compressedSizeElement.textContent = `${(compressedSizeBytes / 1024).toFixed(2)} KB`;
                        }
                        
                        // Calculate reduction percentage
                        const originalSizeBytes = window.currentFile.size;
                        const reductionElement = document.getElementById('reduction');
                        if (reductionElement) {
                            const reductionPercent = ((originalSizeBytes - compressedSizeBytes) / originalSizeBytes * 100).toFixed(2);
                            reductionElement.textContent = `${reductionPercent}%`;
                        }
                        
                        // Show results and download button
                        results.style.display = 'block';
                        loading.style.display = 'none';
                        compressBtn.disabled = false;
                    };
                    img.src = window.originalImageData;
                }, 800);
            }
            
            // Download functionality
            if (downloadBtn) {
                downloadBtn.addEventListener('click', downloadImage);
            }
            
            function downloadImage() {
                if (!window.compressedImageData) return;
                
                const link = document.createElement('a');
                link.download = 'compressed-image.jpg';
                link.href = window.compressedImageData;
                link.click();
            }
        }
        
        // Initialize Image Converter
        function initImageConverter() {
            const convertBtn = document.getElementById('convert-btn');
            const downloadBtn = document.getElementById('download-btn');
            const loading = document.getElementById('loading');
            const results = document.getElementById('results');
            
            if (convertBtn) {
                convertBtn.addEventListener('click', convertImage);
            }
            
            function convertImage() {
                if (!window.currentFile) {
                    alert('Please select an image first.');
                    return;
                }
                
                loading.style.display = 'block';
                convertBtn.disabled = true;
                
                setTimeout(() => {
                    const img = new Image();
                    img.onload = function() {
                        // Create canvas
                        const canvas = document.createElement('canvas');
                        canvas.width = img.width;
                        canvas.height = img.height;
                        const ctx = canvas.getContext('2d');
                        ctx.drawImage(img, 0, 0);
                        
                        // Get format and quality
                        const formatSelect = document.getElementById('format-select');
                        const format = formatSelect ? formatSelect.value : 'jpg';
                        const qualityValue = parseInt(document.getElementById('image-quality').value) / 100;
                        
                        // Get converted image data
                        let mimeType = 'image/jpeg';
                        if (format === 'png') mimeType = 'image/png';
                        if (format === 'webp') mimeType = 'image/webp';
                        
                        const convertedDataURL = canvas.toDataURL(mimeType, format === 'png' ? undefined : qualityValue);
                        window.convertedImageData = convertedDataURL;
                        
                        // Display converted image
                        const convertedImage = document.getElementById('converted-image');
                        if (convertedImage) {
                            convertedImage.innerHTML = '';
                            const convertedImg = document.createElement('img');
                            convertedImg.src = convertedDataURL;
                            convertedImage.appendChild(convertedImg);
                        }
                        
                        // Show results and download button
                        results.style.display = 'block';
                        loading.style.display = 'none';
                        convertBtn.disabled = false;
                    };
                    img.src = window.originalImageData;
                }, 800);
            }
            
            // Download functionality
            if (downloadBtn) {
                downloadBtn.addEventListener('click', downloadImage);
            }
            
            function downloadImage() {
                if (!window.convertedImageData) return;
                
                const formatSelect = document.getElementById('format-select');
                const format = formatSelect ? formatSelect.value : 'jpg';
                
                const link = document.createElement('a');
                link.download = `converted-image.${format}`;
                link.href = window.convertedImageData;
                link.click();
            }
        }
        
        // Initialize Image Resizer
        function initImageResizer() {
            const widthInput = document.getElementById('width-input');
            const heightInput = document.getElementById('height-input');
            const maintainAspect = document.getElementById('maintain-aspect');
            const resizeBtn = document.getElementById('resize-btn');
            const downloadBtn = document.getElementById('download-btn');
            const loading = document.getElementById('loading');
            const results = document.getElementById('results');
            
            // Maintain aspect ratio
            if (widthInput && heightInput && maintainAspect) {
                widthInput.addEventListener('input', function() {
                    if (maintainAspect.checked && window.originalImage) {
                        const ratio = window.originalImage.height / window.originalImage.width;
                        heightInput.value = Math.round(this.value * ratio);
                    }
                });
                
                heightInput.addEventListener('input', function() {
                    if (maintainAspect.checked && window.originalImage) {
                        const ratio = window.originalImage.width / window.originalImage.height;
                        widthInput.value = Math.round(this.value * ratio);
                    }
                });
            }
            
            if (resizeBtn) {
                resizeBtn.addEventListener('click', resizeImage);
            }
            
            function resizeImage() {
                if (!window.currentFile) {
                    alert('Please select an image first.');
                    return;
                }
                
                const width = parseInt(widthInput.value) || 800;
                const height = parseInt(heightInput.value) || 600;
                
                if (width <= 0 || height <= 0) {
                    alert('Please enter valid dimensions.');
                    return;
                }
                
                loading.style.display = 'block';
                resizeBtn.disabled = true;
                
                setTimeout(() => {
                    const img = new Image();
                    img.onload = function() {
                        // Store original image dimensions
                        window.originalImage = {
                            width: img.width,
                            height: img.height
                        };
                        
                        // Create canvas with new dimensions
                        const canvas = document.createElement('canvas');
                        canvas.width = width;
                        canvas.height = height;
                        const ctx = canvas.getContext('2d');
                        
                        // Draw image with new dimensions
                        ctx.drawImage(img, 0, 0, width, height);
                        
                        // Get resized image data
                        const resizedDataURL = canvas.toDataURL('image/jpeg', 0.9);
                        window.resizedImageData = resizedDataURL;
                        
                        // Display resized image
                        const resizedImage = document.getElementById('resized-image');
                        if (resizedImage) {
                            resizedImage.innerHTML = '';
                            const resizedImg = document.createElement('img');
                            resizedImg.src = resizedDataURL;
                            resizedImage.appendChild(resizedImg);
                        }
                        
                        // Show results and download button
                        results.style.display = 'block';
                        loading.style.display = 'none';
                        resizeBtn.disabled = false;
                    };
                    img.src = window.originalImageData;
                }, 800);
            }
            
            // Download functionality
            if (downloadBtn) {
                downloadBtn.addEventListener('click', downloadImage);
            }
            
            function downloadImage() {
                if (!window.resizedImageData) return;
                
                const link = document.createElement('a');
                link.download = 'resized-image.jpg';
                link.href = window.resizedImageData;
                link.click();
            }
        }
        
        // Initialize PDF tools (simplified for demo)
        function initPDFCompressor() {
            const compressBtn = document.getElementById('compress-btn');
            const downloadBtn = document.getElementById('download-btn');
            const loading = document.getElementById('loading');
            const results = document.getElementById('results');
            
            if (compressBtn) {
                compressBtn.addEventListener('click', compressPDF);
            }
            
            function compressPDF() {
                if (!window.currentFile) {
                    alert('Please select a PDF file first.');
                    return;
                }
                
                loading.style.display = 'block';
                compressBtn.disabled = true;
                
                // Simulate PDF compression (in a real app, you would use a PDF library)
                setTimeout(() => {
                    // For demo purposes, we'll simulate compression
                    const originalSize = window.currentFile.size;
                    const compressedSize = originalSize * 0.7; // 30% reduction
                    
                    const compressedSizeElement = document.getElementById('compressed-size');
                    if (compressedSizeElement) {
                        compressedSizeElement.textContent = `${(compressedSize / 1024).toFixed(2)} KB`;
                    }
                    
                    const reductionElement = document.getElementById('reduction');
                    if (reductionElement) {
                        const reductionPercent = ((originalSize - compressedSize) / originalSize * 100).toFixed(2);
                        reductionElement.textContent = `${reductionPercent}%`;
                    }
                    
                    // Show results and download button
                    results.style.display = 'block';
                    loading.style.display = 'none';
                    compressBtn.disabled = false;
                    
                    // Store compressed PDF data (in a real app, this would be the actual compressed PDF)
                    window.compressedPDFData = 'simulated-compressed-pdf-data';
                }, 1500);
            }
            
            if (downloadBtn) {
                downloadBtn.addEventListener('click', downloadPDF);
            }
            
            function downloadPDF() {
                if (!window.compressedPDFData) {
                    alert('Please compress a PDF first.');
                    return;
                }
                
                // In a real application, this would download the actual compressed PDF
                alert('In a full implementation, this would download the compressed PDF. This is a demo version.');
            }
        }
        
        function initPDFToImage() {
            const convertBtn = document.getElementById('convert-btn');
            const downloadBtn = document.getElementById('download-btn');
            const loading = document.getElementById('loading');
            const results = document.getElementById('results');
            
            if (convertBtn) {
                convertBtn.addEventListener('click', convertPDFToImage);
            }
            
            function convertPDFToImage() {
                if (!window.currentFile) {
                    alert('Please select a PDF file first.');
                    return;
                }
                
                loading.style.display = 'block';
                convertBtn.disabled = true;
                
                // Simulate PDF to image conversion
                setTimeout(() => {
                    // For demo purposes, we'll show placeholder images
                    const convertedImages = document.getElementById('converted-images');
                    if (convertedImages) {
                        convertedImages.innerHTML = '';
                        
                        // Create 3 placeholder images (simulating pages)
                        for (let i = 1; i <= 3; i++) {
                            const imgContainer = document.createElement('div');
                            imgContainer.style.textAlign = 'center';
                            
                            const img = document.createElement('img');
                            img.src = 'https://via.placeholder.com/200x280/4361ee/ffffff?text=Page+' + i;
                            img.style.width = '100%';
                            img.style.borderRadius = '8px';
                            
                            const pageLabel = document.createElement('p');
                            pageLabel.textContent = `Page ${i}`;
                            pageLabel.style.marginTop = '5px';
                            pageLabel.style.fontSize = '0.9rem';
                            
                            imgContainer.appendChild(img);
                            imgContainer.appendChild(pageLabel);
                            convertedImages.appendChild(imgContainer);
                        }
                    }
                    
                    // Show results and download button
                    results.style.display = 'block';
                    loading.style.display = 'none';
                    convertBtn.disabled = false;
                }, 1500);
            }
            
            if (downloadBtn) {
                downloadBtn.addEventListener('click', downloadImages);
            }
            
            function downloadImages() {
                alert('In a full implementation, this would download the converted images as a ZIP file. This is a demo version.');
            }
        }
        
        function initPDFMerger() {
            const mergeBtn = document.getElementById('merge-btn');
            const downloadBtn = document.getElementById('download-btn');
            const loading = document.getElementById('loading');
            const results = document.getElementById('results');
            
            if (mergeBtn) {
                mergeBtn.addEventListener('click', mergePDFs);
            }
            
            function mergePDFs() {
                if (!window.pdfFiles || window.pdfFiles.length < 2) {
                    alert('Please select at least 2 PDF files to merge.');
                    return;
                }
                
                loading.style.display = 'block';
                mergeBtn.disabled = true;
                
                // Simulate PDF merging
                setTimeout(() => {
                    // Calculate total size and page count
                    let totalSize = 0;
                    let totalPages = 0;
                    
                    window.pdfFiles.forEach(file => {
                        totalSize += file.size;
                        // Simulate page count (3 pages per file for demo)
                        totalPages += 3;
                    });
                    
                    const mergedSizeElement = document.getElementById('merged-size');
                    if (mergedSizeElement) {
                        mergedSizeElement.textContent = `${(totalSize / 1024).toFixed(2)} KB`;
                    }
                    
                    const pageCountElement = document.getElementById('page-count');
                    if (pageCountElement) {
                        pageCountElement.textContent = totalPages;
                    }
                    
                    // Show results and download button
                    results.style.display = 'block';
                    loading.style.display = 'none';
                    mergeBtn.disabled = false;
                    
                    // Store merged PDF data (in a real app, this would be the actual merged PDF)
                    window.mergedPDFData = 'simulated-merged-pdf-data';
                }, 1500);
            }
            
            if (downloadBtn) {
                downloadBtn.addEventListener('click', downloadMergedPDF);
            }
            
            function downloadMergedPDF() {
                if (!window.mergedPDFData) {
                    alert('Please merge PDFs first.');
                    return;
                }
                
                alert('In a full implementation, this would download the merged PDF. This is a demo version.');
            }
        }
        
        // Helper function to calculate image size from data URL
        function calculateImageSize(dataURL) {
            const overhead = dataURL.indexOf(',') + 1;
            const base64 = dataURL.substring(overhead);
            const decoded = atob(base64);
            return decoded.length;
        }
    </script>
</body>
</html>
