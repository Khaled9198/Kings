<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D Dropship Haven - Custom 3D Printed Products</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Icon library for icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <!-- Three.js for 3D interactive scenes -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <!-- OrbitControls for 3D interaction -->
    <script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/controls/OrbitControls.js"></script>
    <style>
        /* Custom styles for 3D scene */
        #hero-3d {
            width: 100%;
            height: 500px;
            background: linear-gradient(135deg, #7c3aed, #e879f9);
            border-radius: 10px;
            margin: 20px 0;
        }
        /* Smooth animations */
        .product-card:hover {
            transform: scale(1.05);
            transition: transform 0.3s ease;
        }
        /* Fallback for images */
        .image-container {
            background: #f0f0f0;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 14px;
            color: #666;
        }
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
</head>
<body class="bg-gray-100 font-sans">
    <!-- Header -->
    <header class="bg-white shadow-md sticky top-0 z-10">
        <div class="container mx-auto px-4 py-4 flex justify-between items-center">
            <div class="flex items-center space-x-2">
                <i class="fas fa-cube text-2xl text-purple-600"></i>
                <h1 class="text-2xl font-bold text-gray-800">3D Dropship Haven</h1>
            </div>
            <nav class="hidden md:flex space-x-6">
                <a href="#products" class="text-gray-600 hover:text-purple-600 transition">Products</a>
                <a href="#about" class="text-gray-600 hover:text-purple-600 transition">About</a>
                <a href="#contact" class="text-gray-600 hover:text-purple-600 transition">Contact</a>
            </nav>
            <button class="md:hidden" id="menu-btn">
                <i class="fas fa-bars text-2xl text-gray-600"></i>
            </button>
        </div>
        <!-- Mobile menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-white border-t px-4 py-2">
            <a href="#products" class="block py-2 text-gray-600">Products</a>
            <a href="#about" class="block py-2 text-gray-600">About</a>
            <a href="#contact" class="block py-2 text-gray-600">Contact</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="bg-gradient-to-r from-purple-600 to-pink-600 text-white py-20">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-4xl md:text-6xl font-bold mb-4">Bring 3D Magic to Life</h2>
            <p class="text-xl mb-8">Custom 3D dropshipping: Personalize, print, and ship unique creations worldwide.</p>
            <button class="bg-white text-purple-600 px-8 py-4 rounded-full hover:bg-purple-100 transition" id="cta-btn">Start Exploring</button>
            <!-- 3D Interactive Scene -->
            <div id="hero-3d"></div>
        </div>
    </section>

    <!-- Products Section -->
    <section id="products" class="py-20">
        <div class="container mx-auto px-4">
            <h2 class="text-3xl font-bold text-center mb-10">Featured 3D Products</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Product 1 -->
                <div class="product-card bg-white rounded-lg shadow-md p-6">
                    <div class="image-container mb-4" style="height: 200px;">
                        <img src="https://placehold.co/400x300" alt="Detailed 3D printed customized phone case with intricate geometric patterns, gradients from blue to purple, featuring a central logo placeholder in minimalist design" onerror="this.style.display='none'; this.nextSibling.style.display='block';" />
                        <div style="display: none; padding: 20px;">3D Customized Phone Case with Geometric Patterns</div>
                    </div>
                    <h3 class="text-xl font-bold mb-2">Custom Phone Case</h3>
                    <p class="text-gray-600 mb-4">Personalize your phone with 3D printed designs. Colors: Blue to Purple gradient, intricate patterns.</p>
                    <div class="flex justify-between items-center">
                        <span class="text-2xl font-bold text-purple-600">$29.99</span>
                        <button class="bg-purple-600 text-white px-4 py-2 rounded hover:bg-purple-700 transition">Add to Cart</button>
                    </div>
                </div>
                <!-- Product 2 -->
                <div class="product-card bg-white rounded-lg shadow-md p-6">
                    <div class="image-container mb-4" style="height: 200px;">
                        <img src="https://placehold.co/400x300" alt="Elegant 3D printed personalized jewelry set including necklaces and earrings with floral motifs, gold metallic finish, intricate engraving on a satin background showing craftsmanship" onerror="this.style.display='none'; this.nextSibling.style.display='block';" />
                        <div style="display: none; padding: 20px;">Custom Jewelry Set with Floral Engravings</div>
                    </div>
                    <h3 class="text-xl font-bold mb-2">Personalized Jewelry</h3>
                    <p class="text-gray-600 mb-4">Elegant necklaces and earrings with custom engravings. Finish: Gold metallic, floral themes.</p>
                    <div class="flex justify-between items-center">
                        <span class="text-2xl font-bold text-purple-600">$49.99</span>
                        <button class="bg-purple-600 text-white px-4 py-2 rounded hover:bg-purple-700 transition">Add to Cart</button>
                    </div>
                </div>
                <!-- Product 3 -->
                <div class="product-card bg-white rounded-lg shadow-md p-6">
                    <div class="image-container mb-4" style="height: 200px;">
                        <img src="https://placehold.co/400x300" alt="Functional 3D printed home decor lamp base with modular design, white matte finish, abstract geometric shapes illuminated with soft LED lighting in a modern living room setting" onerror="this.style.display='none'; this.nextSibling.style.display='block';" />
                        <div style="display: none; padding: 20px;">Custom Lamp Base with Geometric Modules</div>
                    </div>
                    <h3 class="text-xl font-bold mb-2">Custom Lamp Base</h3>
                    <p class="text-gray-600 mb-4">Modular home decor lamps with unique shapes. Lighting: Soft LED, geometric modules.</p>
                    <div class="flex justify-between items-center">
                        <span class="text-2xl font-bold text-purple-600">$69.99</span>
                        <button class="bg-purple-600 text-white px-4 py-2 rounded hover:bg-purple-700 transition">Add to Cart</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="bg-white py-20">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-3xl font-bold mb-8">Why Choose 3D Dropship Haven?</h2>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <div class="flex flex-col items-center">
                    <i class="fas fa-truck text-4xl text-purple-600 mb-4"></i>
                    <h3 class="text-xl font-semibold mb-2">Fast Shipping</h3>
                    <p class="text-gray-600">Global dropshipping with quick delivery times.</p>
                </div>
                <div class="flex flex-col items-center">
                    <i class="fas fa-paint-brush text-4xl text-purple-600 mb-4"></i>
                    <h3 class="text-xl font-semibold mb-2">Custom Designs</h3>
                    <p class="text-gray-600">Personalize every product with our 3D configurator.</p>
                </div>
                <div class="flex flex-col items-center">
                    <i class="fas fa-gem text-4xl text-purple-600 mb-4"></i>
                    <h3 class="text-xl font-semibold mb-2">Quality Assurance</h3>
                    <p class="text-gray-600">High-quality 3D printing and finishing options.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="bg-gray-200 py-20">
        <div class="container mx-auto px-4 text-center">
            <h2 class="text-3xl font-bold mb-8">Get in Touch</h2>
            <form class="max-w-md mx-auto" action="#" method="post">
                <input type="text" placeholder="Your Name" class="w-full mb-4 px-4 py-2 border rounded" required>
                <input type="email" placeholder="Your Email" class="w-full mb-4 px-4 py-2 border rounded" required>
                <textarea placeholder="Your Message" rows="5" class="w-full mb-4 px-4 py-2 border rounded" required></textarea>
                <button type="submit" class="bg-purple-600 text-white px-6 py-3 rounded hover:bg-purple-700 transition">Send Message</button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-800 text-white py-8">
        <div class="container mx-auto px-4 text-center">
            <p>&copy; 2023 3D Dropship Haven. All rights reserved.</p>
            <div class="flex justify-center space-x-4 mt-4">
                <i class="fab fa-facebook text-2xl hover:text-purple-400 transition"></i>
                <i class="fab fa-instagram text-2xl hover:text-purple-400 transition"></i>
                <i class="fab fa-twitter text-2xl hover:text-purple-400 transition"></i>
            </div>
        </div>
    </footer>

    <!-- JavaScript -->
    <script>
        // Mobile menu toggle
        document.getElementById('menu-btn').addEventListener('click', function() {
            document.getElementById('mobile-menu').classList.toggle('hidden');
        });

        // Scroll to products on CTA button click
        document.getElementById('cta-btn').addEventListener('click', function() {
            document.getElementById('products').scrollIntoView({ behavior: 'smooth' });
        });

        // 3D Scene Initialization for Hero
        function init3DScene() {
            const scene = new THREE.Scene();
            const camera = new THREE.PerspectiveCamera(75, window.innerWidth / 500, 0.1, 1000);
            const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
            renderer.setSize(window.innerWidth, 500);
            document.getElementById('hero-3d').appendChild(renderer.domElement);

            // Add Orbit Controls
            const controls = new THREE.OrbitControls(camera, renderer.domElement);
            controls.enableDamping = true;
            controls.dampingFactor = 0.05;

            // Lighting
            const ambientLight = new THREE.AmbientLight(0x404040, 1);
            scene.add(ambientLight);
            const directionalLight = new THREE.DirectionalLight(0xffffff, 1);
            directionalLight.position.set(10, 10, 5);
            scene.add(directionalLight);

            // Add a simple 3D cube as placeholder for custom products
            const geometry = new THREE.BoxGeometry(2, 2, 2);
            const material = new THREE.MeshPhongMaterial({ color: 0x7c3aed, shininess: 100 });
            const cube = new THREE.Mesh(geometry, material);
            scene.add(cube);

            // Animation loop
            function animate() {
                requestAnimationFrame(animate);
                cube.rotation.x += 0.01;
                cube.rotation.y += 0.01;
                controls.update();
                renderer.render(scene, camera);
            }

            camera.position.z = 5;
            animate();

            // Handle window resize
            window.addEventListener('resize', function() {
                camera.aspect = window.innerWidth / 500;
                camera.updateProjectionMatrix();
                renderer.setSize(window.innerWidth, 500);
            });
        }

        // Initialize 3D scene on page load
        window.addEventListener('load', init3DScene);
    </script>
</body>
</html>
</content>
</create_file>

<attempt_completion>
I've created a standalone HTML file for your 3D dropshipping website. This is a responsive, single-page site using HTML, CSS (with TailwindCSS), and JavaScript. It includes:

- A hero section with an interactive 3D scene (using Three.js for a rotating cube as a demo).
- Product showcase with placeholder images (detailed alt text for AI generation).
- About and contact sections.
- Mobile-friendly navigation.

The site simulates a dropshipping store with custom 3D products. Open the `index.html` file in your browser to preview it. If you need modifications, let me know!
</attempt_completion>
