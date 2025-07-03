<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D Sticker Magic ✨ Instant AI Stickers</title>
    <style>
        :root {
            --primary: #ff6b6b;
            --secondary: #4ecdc4;
            --accent: #ffe66d;
            --dark: #292f36;
            --light: #f7fff7;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Comic Neue', cursive, sans-serif;
        }

        body {
            background-color: var(--light);
            background-image: url('data:image/svg+xml;utf8,<svg width="100" height="100" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><path d="M30,10 Q50,0 70,10 Q100,30 90,50 Q100,70 70,90 Q50,100 30,90 Q0,70 10,50 Q0,30 30,10" fill="none" stroke="%234ecdc466" stroke-width="2"/></svg>');
            background-size: 40px 40px;
            overflow-x: hidden;
            position: relative;
        }

        /* Floating stickers in background */
        .bg-sticker {
            position: fixed;
            opacity: 0.7;
            z-index: -1;
            animation: float 15s infinite ease-in-out;
            filter: drop-shadow(0 0 10px rgba(0,0,0,0.1));
            transition: all 0.3s;
        }

        .bg-sticker:hover {
            opacity: 0.9;
            transform: scale(1.1) rotate(10deg);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
        }

        /* Header styles */
        header {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            padding: 1.5rem;
            text-align: center;
            border-radius: 0 0 20px 20px;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1));
            position: relative;
            overflow: hidden;
        }

        header h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 0 rgba(0,0,0,0.1));
            position: relative;
            z-index: 2;
        }

        header p {
            font-size: 1.2rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
            position: relative;
            z-index: 2;
        }

        .header-stickers {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 1;
            opacity: 0.3;
        }

        /* Main content */
        .container {
            max-width: 1200px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }

        /* Sticker generator section */
        .generator {
            background: white;
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05));
            margin-bottom: 2rem;
            position: relative;
            overflow: hidden;
        }

        .generator::before {
            content: "";
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            border: 3px dashed var(--accent);
            border-radius: 25px;
            z-index: -1;
            animation: borderPulse 4s infinite linear;
            pointer-events: none;
        }

        @keyframes borderPulse {
            0% { opacity: 0.3; }
            50% { opacity: 0.7; }
            100% { opacity: 0.3; }
        }

        .tabs {
            display: flex;
            margin-bottom: 1.5rem;
            border-bottom: 2px solid #eee;
        }

        .tab {
            padding: 0.8rem 1.5rem;
            cursor: pointer;
            font-weight: bold;
            color: var(--dark);
            opacity: 0.7;
            transition: all 0.3s;
            border-bottom: 3px solid transparent;
        }

        .tab.active {
            opacity: 1;
            color: var(--primary);
            border-bottom: 3px solid var(--primary);
        }

        .tab:hover:not(.active) {
            opacity: 0.9;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .input-group {
            margin-bottom: 1.5rem;
        }

        label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: bold;
            color: var(--dark);
        }

        input[type="text"], textarea {
            width: 100%;
            padding: 1rem;
            border: 2px solid #eee;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s;
        }

        input[type="text"]:focus, textarea:focus {
            border-color: var(--secondary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(78, 205, 196, 0.2);
        }

        textarea {
            min-height: 100px;
            resize: vertical;
        }

        .upload-area {
            border: 3px dashed #ddd;
            border-radius: 15px;
            padding: 3rem 1rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            background-color: #f9f9f9;
            position: relative;
            overflow: hidden;
        }

        .upload-area:hover {
            border-color: var(--secondary);
            background-color: #f0fdfb;
        }

        .upload-area.active {
            border-color: var(--primary);
            background-color: #fff0f0;
        }

        .upload-area i {
            font-size: 3rem;
            color: var(--secondary);
            margin-bottom: 1rem;
            display: block;
        }

        .upload-area p {
            color: #666;
            margin-bottom: 0.5rem;
        }

        .upload-area small {
            color: #999;
        }

        #file-input {
            display: none;
        }

        #image-preview {
            max-width: 100%;
            max-height: 200px;
            display: none;
            margin: 0 auto;
            border-radius: 10px;
        }

        .btn {
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            color: white;
            border: none;
            padding: 1rem 2rem;
            font-size: 1.1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(255, 107, 107, 0.3));
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(255, 107, 107, 0.4));
        }

        .btn:active {
            transform: translateY(1px);
        }

        .btn-secondary {
            background: white;
            color: var(--dark);
            border: 2px solid #eee;
            box-shadow: none;
        }

        .btn-secondary:hover {
            background: #f5f5f5;
            box-shadow: none;
        }

        /* Results section */
        .results {
            display: none;
            margin-top: 2rem;
            text-align: center;
        }

        .results h2 {
            margin-bottom: 1.5rem;
            color: var(--dark);
        }

        .sticker-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .sticker-item {
            background: white;
            border-radius: 15px;
            padding: 1rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05));
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }

        .sticker-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1));
        }

        .sticker-img {
            width: 100%;
            height: 180px;
            object-fit: contain;
            margin-bottom: 1rem;
            background-color: #f9f9f9;
            border-radius: 10px;
        }

        .sticker-actions {
            display: flex;
            justify-content: center;
            gap: 0.5rem;
        }

        .btn-sm {
            padding: 0.5rem 1rem;
            font-size: 0.9rem;
        }

        /* Loading state */
        .loading {
            display: none;
            text-align: center;
            padding: 2rem;
        }

        .spinner {
            width: 50px;
            height: 50px;
            border: 5px solid rgba(78, 205, 196, 0.2);
            border-radius: 50%;
            border-top-color: var(--secondary);
            animation: spin 1s ease-in-out infinite;
            margin: 0 auto 1rem;
        }

        @keyframes spin {
            to { transform: rotate(360deg); }
        }

        /* Share section */
        .share {
            margin-top: 2rem;
            text-align: center;
        }

        .share-buttons {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 1rem;
        }

        .share-btn {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            transition: all 0.3s;
        }

        .share-btn:hover {
            transform: scale(1.1);
        }

        .whatsapp { background: #25D366; }
        .instagram { background: #E1306C; }
        .telegram { background: #0088CC; }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            color: #666;
            font-size: 0.9rem;
        }

        /* Sticker animation for fun */
        @keyframes stickerPop {
            0% { transform: scale(0); opacity: 0; }
            80% { transform: scale(1.1); }
            100% { transform: scale(1); opacity: 1; }
        }

        /* Responsive styles */
        @media (max-width: 768px) {
            header h1 {
                font-size: 2rem;
            }

            .sticker-grid {
                grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
            }

            .btn {
                padding: 0.8rem 1.5rem;
                font-size: 1rem;
            }
        }

        @media (max-width: 480px) {
            .tabs {
                flex-direction: column;
                border-bottom: none;
            }

            .tab {
                border-bottom: 2px solid #eee;
                border-left: 3px solid transparent;
            }

            .tab.active {
                border-bottom: 2px solid #eee;
                border-left: 3px solid var(--primary);
            }

            .sticker-grid {
                grid-template-columns: 1fr 1fr;
            }
        }
    </style>
    <link href="https://fonts.googleapis.com/css2?family=Comic+Neue:wght@400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <!-- Background stickers -->
    <img src="https://cdn-icons-png.flaticon.com/512/4392/4392522.png" class="bg-sticker" style="width: 120px; top: 10%; left: 5%; animation-delay: 0s;">
    <img src="https://cdn-icons-png.flaticon.com/512/4392/4392452.png" class="bg-sticker" style="width: 100px; top: 70%; left: 80%; animation-delay: 2s;">
    <img src="https://cdn-icons-png.flaticon.com/512/4392/4392458.png" class="bg-sticker" style="width: 80px; top: 30%; left: 85%; animation-delay: 4s;">
    <img src="https://cdn-icons-png.flaticon.com/512/4392/4392528.png" class="bg-sticker" style="width: 90px; top: 80%; left: 10%; animation-delay: 1s;">
    <img src="https://cdn-icons-png.flaticon.com/512/4392/4392454.png" class="bg-sticker" style="width: 110px; top: 20%; left: 70%; animation-delay: 3s;">

    <header>
        <div class="header-stickers">
            <img src="https://cdn-icons-png.flaticon.com/512/4392/4392459.png" style="position: absolute; top: 20px; left: 20px; width: 60px; transform: rotate(-15deg);">
            <img src="https://cdn-icons-png.flaticon.com/512/4392/4392455.png" style="position: absolute; bottom: 10px; right: 30px; width: 80px; transform: rotate(10deg);">
        </div>
        <h1>3D Sticker Magic ✨</h1>
        <p>Transform anything into awesome 3D AI stickers! Upload an image or describe what you want.</p>
    </header>

    <div class="container">
        <div class="generator">
            <div class="tabs">
                <div class="tab active" data-tab="text">Text to 3D Sticker</div>
                <div class="tab" data-tab="image">Image to 3D Sticker</div>
            </div>

            <div class="tab-content active" id="text-tab">
                <div class="input-group">
                    <label for="sticker-prompt">Describe your 3D sticker</label>
                    <input type="text" id="sticker-prompt" placeholder="e.g. 'angry cat in sunglasses', 'Bollywood-style robot', 'cute avocado with arms'">
                </div>
                <div class="input-group">
                    <label for="style-prompt">Style</label>
                    <select id="style-prompt" class="btn btn-secondary" style="width: 100%; padding: 0.8rem;">
                        <option value="3d-cartoon">3D Cartoon</option>
                        <option value="3d-realistic">3D Realistic</option>
                        <option value="3d-anime">3D Anime</option>
                        <option value="3d-minimal">3D Minimal</option>
                        <option value="3d-abstract">3D Abstract</option>
                    </select>
                </div>
                <button id="generate-btn" class="btn">
                    <i class="fas fa-magic"></i> Generate 3D Stickers
                </button>
            </div>

            <div class="tab-content" id="image-tab">
                <div class="input-group">
                    <label>Upload your image</label>
                    <div class="upload-area" id="upload-area">
                        <i class="fas fa-cloud-upload-alt"></i>
                        <p>Drag & drop your image here</p>
                        <small>or click to browse files (PNG, JPG)</small>
                        <input type="file" id="file-input" accept="image/*">
                        <img id="image-preview" alt="Preview">
                    </div>
                </div>
                <div class="input-group">
                    <label>3D Style</label>
                    <select id="image-style" class="btn btn-secondary" style="width: 100%; padding: 0.8rem; margin-bottom: 1rem;">
                        <option value="3d-cartoon">3D Cartoon</option>
                        <option value="3d-realistic">3D Realistic</option>
                        <option value="3d-anime">3D Anime</option>
                        <option value="3d-minimal">3D Minimal</option>
                        <option value="3d-abstract">3D Abstract</option>
                    </select>
                    <button id="generate-image-btn" class="btn" disabled>
                        <i class="fas fa-magic"></i> Create 3D Stickers
                    </button>
                </div>
            </div>
        </div>

        <div class="loading" id="loading">
            <div class="spinner"></div>
            <h3>Creating 3D magic...</h3>
            <p>Generating your awesome 3D stickers</p>
            <div class="fun-fact" id="fun-fact"></div>
        </div>

        <div class="results" id="results">
            <h2>Your 3D Stickers!</h2>
            <div class="sticker-grid" id="sticker-grid">
                <!-- Stickers will be added here by JavaScript -->
            </div>
            <div class="share">
                <p>Love your 3D stickers? Share them with friends!</p>
                <div class="share-buttons">
                    <a href="#" class="share-btn whatsapp" id="whatsapp-share"><i class="fab fa-whatsapp"></i></a>
                    <a href="#" class="share-btn instagram" id="instagram-share"><i class="fab fa-instagram"></i></a>
                    <a href="#" class="share-btn telegram" id="telegram-share"><i class="fab fa-telegram"></i></a>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <p>Made with ❤️ and ✨ by 3D Sticker Magic | All stickers are generated by AI</p>
    </footer>

    <script>
        // Tab switching
        const tabs = document.querySelectorAll('.tab');
        const tabContents = document.querySelectorAll('.tab-content');

        tabs.forEach(tab => {
            tab.addEventListener('click', () => {
                const tabId = tab.getAttribute('data-tab');
                
                // Update active tab
                tabs.forEach(t => t.classList.remove('active'));
                tab.classList.add('active');
                
                // Update active content
                tabContents.forEach(content => {
                    content.classList.remove('active');
                    if (content.id === `${tabId}-tab`) {
                        content.classList.add('active');
                    }
                });
            });
        });

        // Upload area interaction
        const uploadArea = document.getElementById('upload-area');
        const fileInput = document.getElementById('file-input');
        const imagePreview = document.getElementById('image-preview');
        const generateImageBtn = document.getElementById('generate-image-btn');

        uploadArea.addEventListener('click', () => {
            fileInput.click();
        });

        uploadArea.addEventListener('dragover', (e) => {
            e.preventDefault();
            uploadArea.classList.add('active');
        });

        uploadArea.addEventListener('dragleave', () => {
            uploadArea.classList.remove('active');
        });

        uploadArea.addEventListener('drop', (e) => {
            e.preventDefault();
            uploadArea.classList.remove('active');
            if (e.dataTransfer.files.length) {
                fileInput.files = e.dataTransfer.files;
                handleFileSelect();
            }
        });

        fileInput.addEventListener('change', handleFileSelect);

        function handleFileSelect() {
            if (fileInput.files && fileInput.files[0]) {
                const file = fileInput.files[0];
                if (file.type.match('image.*')) {
                    const reader = new FileReader();
                    
                    reader.onload = function(e) {
                        // Show preview of selected image
                        imagePreview.src = e.target.result;
                        imagePreview.style.display = 'block';
                        
                        // Update upload area text
                        uploadArea.innerHTML = `
                            <i class="fas fa-check-circle" style="color: #4ecdc4;"></i>
                            <p>${file.name}</p>
                            <small>Ready to transform into 3D!</small>
                        `;
                        uploadArea.appendChild(imagePreview);
                        
                        generateImageBtn.disabled = false;
                    };
                    
                    reader.readAsDataURL(file);
                } else {
                    alert('Please select an image file (PNG, JPG)');
                }
            }
        }

        // Generate stickers from text
        const generateBtn = document.getElementById('generate-btn');
        const stickerPrompt = document.getElementById('sticker-prompt');
        const stylePrompt = document.getElementById('style-prompt');
        const loading = document.getElementById('loading');
        const results = document.getElementById('results');
        const stickerGrid = document.getElementById('sticker-grid');
        const funFacts = [
            "Did you know? 3D stickers are more engaging than 2D ones!",
            "Fun fact: The first 3D stickers appeared in the 2010s!",
            "Sticker trivia: 3D stickers use shading to create depth illusion!",
            "Cool fact: Some 3D stickers can look like they're popping out!",
            "Did you know? 3D stickers work great in augmented reality!"
        ];

        generateBtn.addEventListener('click', generateStickersFromText);
        generateImageBtn.addEventListener('click', generateStickersFromImage);

        // Sample 3D sticker images for demonstration
        const sample3DStickers = [
            "https://cdn-icons-png.flaticon.com/512/4392/4392452.png",
            "https://cdn-icons-png.flaticon.com/512/4392/4392454.png",
            "https://cdn-icons-png.flaticon.com/512/4392/4392455.png",
            "https://cdn-icons-png.flaticon.com/512/4392/4392458.png",
            "https://cdn-icons-png.flaticon.com/512/4392/4392459.png",
            "https://cdn-icons-png.flaticon.com/512/4392/4392522.png",
            "https://cdn-icons-png.flaticon.com/512/4392/4392528.png",
            "https://cdn-icons-png.flaticon.com/512/4392/4392529.png"
        ];

        function generateStickersFromText() {
            const prompt = stickerPrompt.value.trim();
            if (!prompt) {
                alert('Please describe what 3D sticker you want to create!');
                return;
            }

            const style = stylePrompt.value;
            startGeneration();
            
            // Create 4 different 3D sticker variations
            const stickers = [];
            for (let i = 0; i < 4; i++) {
                stickers.push({
                    id: Date.now() + i,
                    prompt: `${prompt} (${style.replace('3d-', '')} style)`,
                    url: sample3DStickers[Math.floor(Math.random() * sample3DStickers.length)],
                    downloadUrl: sample3DStickers[Math.floor(Math.random() * sample3DStickers.length)]
                });
            }
            
            // Simulate processing delay
            setTimeout(() => {
                finishGeneration(stickers);
            }, 1500);
        }

        function generateStickersFromImage() {
            if (!fileInput.files || !fileInput.files[0]) {
                alert('Please upload an image first!');
                return;
            }

            const style = document.getElementById('image-style').value;
            startGeneration();
            
            // Create 4 different 3D sticker variations from uploaded image
            const stickers = [];
            for (let i = 0; i < 4; i++) {
                stickers.push({
                    id: Date.now() + i,
                    prompt: `Your image as ${style.replace('3d-', '')} 3D sticker`,
                    url: sample3DStickers[Math.floor(Math.random() * sample3DStickers.length)],
                    downloadUrl: imagePreview.src // In real app, this would be processed image
                });
            }
            
            // Simulate processing delay
            setTimeout(() => {
                finishGeneration(stickers);
            }, 2000);
        }

        function startGeneration() {
            loading.style.display = 'block';
            results.style.display = 'none';
            
            // Show random fun fact
            const randomFact = funFacts[Math.floor(Math.random() * funFacts.length)];
            document.getElementById('fun-fact').textContent = randomFact;
        }

        function finishGeneration(stickers) {
            loading.style.display = 'none';
            
            // Clear previous results
            stickerGrid.innerHTML = '';
            
            // Add new stickers
            stickers.forEach((sticker, index) => {
                const stickerItem = document.createElement('div');
                stickerItem.className = 'sticker-item';
                stickerItem.innerHTML = `
                    <img src="${sticker.url}" class="sticker-img" alt="${sticker.prompt}">
                    <div class="sticker-actions">
                        <button class="btn btn-sm download-btn" data-url="${sticker.downloadUrl}" data-filename="3d-sticker-${index + 1}.png">
                            <i class="fas fa-download"></i> Download
                        </button>
                        <button class="btn btn-sm btn-secondary share-btn" data-url="${sticker.downloadUrl}" data-text="Check out this ${sticker.prompt} I made with 3D Sticker Magic!">
                            <i class="fas fa-share-alt"></i> Share
                        </button>
                    </div>
                `;
                stickerGrid.appendChild(stickerItem);
                
                // Add animation
                setTimeout(() => {
                    stickerItem.style.animation = 'stickerPop 0.5s ease-out';
                }, 100 * index);
            });
            
            // Add event listeners to new buttons
            document.querySelectorAll('.download-btn').forEach(btn => {
                btn.addEventListener('click', function() {
                    const url = this.getAttribute('data-url');
                    const filename = this.getAttribute('data-filename');
                    downloadSticker(url, filename);
                });
            });
            
            document.querySelectorAll('.share-btn').forEach(btn => {
                btn.addEventListener('click', function(e) {
                    e.preventDefault();
                    const url = this.getAttribute('data-url');
                    const text = this.getAttribute('data-text');
                    shareSticker(url, text);
                });
            });
            
            // Update share buttons
            if (stickers.length > 0) {
                updateShareButtons(stickers[0].downloadUrl, stickers[0].prompt);
            }
            
            // Show results
            results.style.display = 'block';
            
            // Scroll to results
            results.scrollIntoView({ behavior: 'smooth' });
        }

        function downloadSticker(url, filename = '3d-sticker.png') {
            // Create a temporary anchor element
            const a = document.createElement('a');
            a.href = url;
            a.download = filename;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
        }

        function shareSticker(url, text = 'Check out this awesome 3D sticker!') {
            // Use the Web Share API if available
            if (navigator.share) {
                navigator.share({
                    title: 'My 3D AI-Generated Sticker',
                    text: text,
                    url: url
                }).catch(err => {
                    console.log('Error sharing:', err);
                    fallbackShare(url, text);
                });
            } else {
                fallbackShare(url, text);
            }
        }

        function fallbackShare(url, text) {
            // Fallback for browsers without Web Share API
            const shareUrl = `https://3d-sticker-magic.example.com/share?sticker=${encodeURIComponent(url)}`;
            const message = `${text}\n\n${shareUrl}`;
            
            // Try to copy to clipboard
            if (navigator.clipboard) {
                navigator.clipboard.writeText(message).then(() => {
                    alert('Link copied to clipboard! Paste it anywhere to share.');
                }).catch(() => {
                    prompt('Copy this link to share:', shareUrl);
                });
            } else {
                prompt('Copy this link to share:', shareUrl);
            }
        }

        function updateShareButtons(url, text) {
            const shareUrl = `https://3d-sticker-magic.example.com/share?sticker=${encodeURIComponent(url)}`;
            const shareText = encodeURIComponent(text);
            
            // Update social share links
            document.getElementById('whatsapp-share').href = `https://wa.me/?text=${shareText}%20${encodeURIComponent(shareUrl)}`;
            document.getElementById('instagram-share').href = `https://www.instagram.com/share?url=${encodeURIComponent(shareUrl)}`;
            document.getElementById('telegram-share').href = `https://t.me/share/url?url=${encodeURIComponent(shareUrl)}&text=${shareText}`;
        }

        // Make background stickers interactive
        document.querySelectorAll('.bg-sticker').forEach(sticker => {
            sticker.addEventListener('click', () => {
                sticker.style.transform = 'scale(1.2) rotate(15deg)';
                setTimeout(() => {
                    sticker.style.transform = '';
                }, 500);
            });
        });

        // Easter egg - change cursor to a sticker on click
        document.addEventListener('click', (e) => {
            if (e.target.tagName !== 'BUTTON' && e.target.tagName !== 'INPUT' && e.target.tagName !== 'TEXTAREA') {
                document.body.style.cursor = `url('https://cdn-icons-png.flaticon.com/512/4392/4392452.png'), auto`;
                setTimeout(() => {
                    document.body.style.cursor = '';
                }, 500);
            }
        });
    </script>
</body>
</html>
