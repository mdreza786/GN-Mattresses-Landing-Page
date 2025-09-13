# GN-Mattresses-Landing-Page
A responsive landing page for GN-Mattresses, built with HTML, Tailwind CSS, and Firebase. It includes:  Hero section with call-to-action  Product showcase &amp; testimonials  Mattress recommendation form (Firestore + Firebase Auth)  Modern UI with Tailwind utility classes




<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Good Night Mattress - Experience Your Best Sleep Yet</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts - Inter -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            @apply text-gray-800 bg-gray-50;
        }
        .hero-bg {
            background-image: url('https://placehold.co/1920x1080/E0E7FF/5C76B0?text=Experience+Your+Best+Sleep');
            background-size: cover;
            background-position: center;
        }
    </style>
</head>
<body class="antialiased">

    <!-- Hero Section -->
    <header class="hero-bg h-screen flex flex-col items-center justify-center text-center p-4">
        <div class="bg-white/70 backdrop-blur-sm p-8 md:p-12 rounded-2xl shadow-xl max-w-2xl mx-auto">
            <h1 class="text-4xl md:text-6xl font-extrabold text-indigo-900 leading-tight mb-4">
                Experience Your Best Sleep Yet
            </h1>
            <p class="text-lg md:text-xl text-gray-700 mb-8 max-w-lg mx-auto">
                Discover the perfect mattress for your body and mind. Our innovative designs ensure comfort, support, and truly restorative sleep.
            </p>
            <a href="#form-section" class="inline-block bg-indigo-600 text-white font-semibold py-3 px-8 rounded-full shadow-lg hover:bg-indigo-700 transition-colors duration-300">
                Find Your Perfect Mattress
            </a>
        </div>
    </header>

    <main class="container mx-auto px-4 py-16 md:py-24">

        <!-- Value Proposition Section -->
        <section class="text-center mb-24">
            <h2 class="text-3xl md:text-4xl font-bold text-gray-900 mb-12">Why Choose Good Night Mattress?</h2>
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="flex flex-col items-center p-6 bg-white rounded-2xl shadow-md transition-transform transform hover:scale-105">
                    <svg class="w-16 h-16 text-indigo-500 mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8c1.657 0 3 1.343 3 3v2a3 3 0 01-3 3 3 3 0 01-3-3v-2c0-1.657 1.343-3 3-3z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18c1.558 0 2.923-.526 4-1.342V15a3 3 0 00-3-3h-2a3 3 0 00-3 3v1.658c1.077.816 2.442 1.342 4 1.342z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 21a9 9 0 110-18 9 9 0 010 18z"></path></svg>
                    <h3 class="text-xl font-semibold mb-2">Orthopedic Support</h3>
                    <p class="text-gray-600 text-center">Engineered for perfect spinal alignment and pressure relief.</p>
                </div>
                <div class="flex flex-col items-center p-6 bg-white rounded-2xl shadow-md transition-transform transform hover:scale-105">
                    <svg class="w-16 h-16 text-indigo-500 mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.674M12 3v13m0 0l-3.253-3.253M12 16l3.253-3.253M16 4.75h-.25c-1.38 0-2.5-1.12-2.5-2.5V.25c0-1.38 1.12-2.5 2.5-2.5h.25c1.38 0 2.5 1.12 2.5 2.5V2.25c0 1.38-1.12 2.5-2.5 2.5z"></path></svg>
                    <h3 class="text-xl font-semibold mb-2">100-Night Trial</h3>
                    <p class="text-gray-600 text-center">Try it in your own home with no risk. Love it or return it.</p>
                </div>
                <div class="flex flex-col items-center p-6 bg-white rounded-2xl shadow-md transition-transform transform hover:scale-105">
                    <svg class="w-16 h-16 text-indigo-500 mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 20l-4-4m0 0l4-4m-4 4h10a4 4 0 010 8H7"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M11 20l4-4m0 0l-4-4m4 4h-10a4 4 0 010-8h4"></path></svg>
                    <h3 class="text-xl font-semibold mb-2">Free Shipping</h3>
                    <p class="text-gray-600 text-center">Delivered directly to your door, absolutely free of charge.</p>
                </div>
                <div class="flex flex-col items-center p-6 bg-white rounded-2xl shadow-md transition-transform transform hover:scale-105">
                    <svg class="w-16 h-16 text-indigo-500 mb-4" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path></svg>
                    <h3 class="text-xl font-semibold mb-2">Eco-Friendly</h3>
                    <p class="text-gray-600 text-center">Made with sustainably sourced materials for a greener planet.</p>
                </div>
            </div>
        </section>

        <!-- Product Showcase Section -->
        <section class="mb-24">
            <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-900 mb-12">Our Best-Sellers</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Product Card 1 -->
                <div class="bg-white rounded-2xl shadow-md overflow-hidden transition-transform transform hover:scale-105">
                    <img src="https://placehold.co/600x400/D1C4E9/4527A0?text=The+OrthoRelax" alt="The OrthoRelax Mattress" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-900 mb-2">The OrthoRelax</h3>
                        <p class="text-gray-600 mb-4">Perfect for those with back or joint pain, offering firm support and superior comfort.</p>
                        <a href="#" class="inline-block text-indigo-600 font-semibold hover:text-indigo-800 transition-colors duration-300">Learn More &rarr;</a>
                    </div>
                </div>
                <!-- Product Card 2 -->
                <div class="bg-white rounded-2xl shadow-md overflow-hidden transition-transform transform hover:scale-105">
                    <img src="https://placehold.co/600x400/BBDEFB/1565C0?text=The+CloudMemory" alt="The CloudMemory Mattress" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-900 mb-2">The CloudMemory</h3>
                        <p class="text-gray-600 mb-4">A plush memory foam mattress that cradles your body for a weightless feel.</p>
                        <a href="#" class="inline-block text-indigo-600 font-semibold hover:text-indigo-800 transition-colors duration-300">Learn More &rarr;</a>
                    </div>
                </div>
                <!-- Product Card 3 -->
                <div class="bg-white rounded-2xl shadow-md overflow-hidden transition-transform transform hover:scale-105">
                    <img src="https://placehold.co/600x400/FFE0B2/EF6C00?text=The+CoolHybrid" alt="The CoolHybrid Mattress" class="w-full h-48 object-cover">
                    <div class="p-6">
                        <h3 class="text-2xl font-semibold text-gray-900 mb-2">The CoolHybrid</h3>
                        <p class="text-gray-600 mb-4">Combines the best of memory foam and innerspring for support and cooling.</p>
                        <a href="#" class="inline-block text-indigo-600 font-semibold hover:text-indigo-800 transition-colors duration-300">Learn More &rarr;</a>
                    </div>
                </div>
            </div>
        </section>

        <!-- "Find Your Perfect Mattress" Form Section -->
        <section id="form-section" class="bg-indigo-50 p-8 md:p-16 rounded-3xl shadow-lg mb-24">
            <h2 class="text-3xl md:text-4xl font-bold text-center text-indigo-900 mb-6">Find Your Perfect Mattress</h2>
            <p class="text-center text-gray-700 mb-10 max-w-2xl mx-auto">Tell us a little about your sleep preferences and we'll help you find the mattress of your dreams.</p>
            <form id="recommendation-form" class="max-w-xl mx-auto space-y-6">
                <div>
                    <label for="firmness" class="block text-gray-700 font-medium mb-2">Preferred Firmness</label>
                    <select id="firmness" name="firmness" class="w-full p-3 rounded-md border border-gray-300 focus:outline-none focus:ring-2 focus:ring-indigo-500">
                        <option value="">Select an option</option>
                        <option value="soft">Soft</option>
                        <option value="medium">Medium</option>
                        <option value="firm">Firm</option>
                    </select>
                </div>
                <div>
                    <label for="position" class="block text-gray-700 font-medium mb-2">Sleeping Position</label>
                    <select id="position" name="position" class="w-full p-3 rounded-md border border-gray-300 focus:outline-none focus:ring-2 focus:ring-indigo-500">
                        <option value="">Select an option</option>
                        <option value="back">Back Sleeper</option>
                        <option value="side">Side Sleeper</option>
                        <option value="stomach">Stomach Sleeper</option>
                        <option value="combination">Combination Sleeper</option>
                    </select>
                </div>
                <div>
                    <label for="custom-needs" class="block text-gray-700 font-medium mb-2">Custom Needs / Notes</label>
                    <textarea id="custom-needs" name="custom-needs" rows="4" placeholder="e.g., 'I have lower back pain,' or 'I get hot at night'" class="w-full p-3 rounded-md border border-gray-300 focus:outline-none focus:ring-2 focus:ring-indigo-500"></textarea>
                </div>
                <button type="submit" class="w-full bg-indigo-600 text-white font-semibold py-3 rounded-full shadow-lg hover:bg-indigo-700 transition-colors duration-300">
                    Get My Recommendation
                </button>
            </form>
            <div id="status-message" class="mt-4 text-center font-semibold"></div>
        </section>

        <!-- Testimonial Section -->
        <section class="mb-24">
            <h2 class="text-3xl md:text-4xl font-bold text-center text-gray-900 mb-12">What Our Customers Say</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div class="bg-white p-8 rounded-2xl shadow-md">
                    <div class="flex items-center mb-4">
                        <span class="text-yellow-400 text-xl">&#9733;&#9733;&#9733;&#9733;&#9733;</span>
                    </div>
                    <p class="text-gray-600 mb-4 italic">"I've never slept better. The OrthoRelax has completely changed my mornings. No more back pain!"</p>
                    <p class="font-semibold text-gray-800">- Jane Doe</p>
                </div>
                <div class="bg-white p-8 rounded-2xl shadow-md">
                    <div class="flex items-center mb-4">
                        <span class="text-yellow-400 text-xl">&#9733;&#9733;&#9733;&#9733;&#9733;</span>
                    </div>
                    <p class="text-gray-600 mb-4 italic">"The CloudMemory feels like sleeping on a cloud. It's so comfortable and I fall asleep so much faster."</p>
                    <p class="font-semibold text-gray-800">- John Smith</p>
                </div>
                <div class="bg-white p-8 rounded-2xl shadow-md">
                    <div class="flex items-center mb-4">
                        <span class="text-yellow-400 text-xl">&#9733;&#9733;&#9733;&#9733;&#9733;</span>
                    </div>
                    <p class="text-gray-600 mb-4 italic">"I was skeptical about a hybrid, but the CoolHybrid is perfect. It's supportive and I don't overheat."</p>
                    <p class="font-semibold text-gray-800">- Alex Chen</p>
                </div>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
        <div class="container mx-auto px-4 text-center">
            <p class="text-lg font-semibold mb-2">Good Night Mattress</p>
            <p class="text-gray-400 mb-4">Your journey to a better sleep starts here.</p>
            <div class="flex justify-center space-x-4 mb-4">
                <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
                    <!-- Facebook SVG -->
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.872v-6.985h-2.54v-2.897h2.54V9.75c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.77-1.63 1.563v1.817h2.774l-.443 2.897h-2.331v6.985C18.343 21.128 22 16.991 22 12z" /></svg>
                </a>
                <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
                    <!-- Twitter SVG -->
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path d="M22.185 5.567a8.557 8.557 0 01-2.43.664 4.298 4.298 0 001.884-2.333 8.58 8.58 0 01-2.718 1.033A4.288 4.288 0 0014.24 6.95c-3.79 0-6.862 3.072-6.862 6.862 0 .536.06 1.056.177 1.558-5.704-.285-10.748-3.013-14.126-7.149-.59 1.01-.93 2.185-.93 3.428 0 2.379 1.21 4.478 3.045 5.708a4.277 4.277 0 01-1.942-.536v.086c0 3.328 2.368 6.095 5.503 6.726a4.34 4.34 0 01-1.93.074c.875 2.73 3.42 4.718 6.442 4.773a8.625 8.625 0 005.617-1.928c2.978 1.905 6.516 3.023 10.334 3.023.63 0 1.25-.038 1.86-.112a14.716 14.716 0 003.54-1.373c-2.484-1.972-4.622-4.492-5.912-7.39a12.78 12.78 0 01-1.258-3.328 11.082 11.082 0 00-1.282-2.903c-.237-.502-.45-.98-.67-1.482z" /></svg>
                </a>
                <a href="#" class="text-gray-400 hover:text-white transition-colors duration-300">
                    <!-- Instagram SVG -->
                    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path d="M12 2C6.477 2 2 6.477 2 12s4.477 10 10 10 10-4.477 10-10S17.523 2 12 2zm3.212 2.5a.788.788 0 11-.788-.788.788.788 0 01.788.788zM12 7c-2.761 0-5 2.239-5 5s2.239 5 5 5 5-2.239 5-5-2.239-5-5-5zm0 8a3 3 0 110-6 3 3 0 010 6zm4-8.5a1.5 1.5 0 100-3 1.5 1.5 0 000 3z" /></svg>
                </a>
            </div>
            <p class="text-sm text-gray-400">&copy; 2024 Good Night Mattress. All rights reserved.</p>
        </div>
    </footer>

    <!-- Firebase and custom script -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInWithCustomToken, signInAnonymously } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, addDoc, setDoc, doc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';
        const firebaseConfig = JSON.parse(typeof __firebase_config !== 'undefined' ? __firebase_config : '{}');

        // Initialize Firebase
        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const auth = getAuth(app);
        
        let userId = '';

        // Handle user authentication
        async function authenticateUser() {
            if (typeof __initial_auth_token !== 'undefined') {
                try {
                    const userCredential = await signInWithCustomToken(auth, __initial_auth_token);
                    userId = userCredential.user.uid;
                } catch (error) {
                    console.error("Error signing in with custom token:", error);
                    // Fallback to anonymous sign-in if custom token fails
                    const anonUserCredential = await signInAnonymously(auth);
                    userId = anonUserCredential.user.uid;
                }
            } else {
                const anonUserCredential = await signInAnonymously(auth);
                userId = anonUserCredential.user.uid;
            }
        }
        
        authenticateUser();

        // Get elements
        const form = document.getElementById('recommendation-form');
        const statusMessage = document.getElementById('status-message');

        // Form submission handler
        form.addEventListener('submit', async (e) => {
            e.preventDefault();

            statusMessage.textContent = 'Submitting your request...';
            statusMessage.className = 'mt-4 text-center font-semibold text-gray-500';

            const firmness = document.getElementById('firmness').value;
            const position = document.getElementById('position').value;
            const customNeeds = document.getElementById('custom-needs').value;
            
            if (!firmness && !position && !customNeeds) {
                statusMessage.textContent = 'Please fill out at least one field.';
                statusMessage.className = 'mt-4 text-center font-semibold text-red-500';
                return;
            }

            const customerData = {
                firmness,
                position,
                customNeeds,
                timestamp: new Date(),
                userId: userId // Use the authenticated user ID
            };

            try {
                // Save data to Firestore in a public collection
                const publicDataRef = collection(db, `artifacts/${appId}/public/data/customer-needs`);
                await addDoc(publicDataRef, customerData);

                statusMessage.textContent = 'Thank you! Your request has been sent. We will get back to you shortly.';
                statusMessage.className = 'mt-4 text-center font-semibold text-green-500';
                form.reset();
            } catch (error) {
                console.error("Error writing document:", error);
                statusMessage.textContent = 'An error occurred. Please try again later.';
                statusMessage.className = 'mt-4 text-center font-semibold text-red-500';
            }
        });
    </script>
</body>
</html>
