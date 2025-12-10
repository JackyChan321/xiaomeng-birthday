<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <!-- Enhanced mobile viewport (critical for mobile) -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>小萌生日快乐！王浩静，我爱你 💕</title>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@300;400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: 'Noto Sans SC', sans-serif;
            overflow-x: hidden;
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a3e 30%, #2d1b69 70%, #000428 100%);
            color: #e0e0ff;
            min-height: 100vh;
            /* Remove custom cursor on mobile (useless for touch) */
            cursor: auto;
            padding-bottom: 80px; /* Reduced for mobile */
        }
        /* Starry sky background */
        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 80%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
                        radial-gradient(circle at 80% 20%, rgba(255, 119, 198, 0.3) 0%, transparent 50%),
                        radial-gradient(circle at 40% 40%, rgba(120, 219, 255, 0.2) 0%, transparent 50%);
            z-index: -2;
            pointer-events: none;
        }
        /* Twinkling stars */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            pointer-events: none;
        }
        .star {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #fff;
            border-radius: 50%;
            animation: twinkle 3s infinite ease-in-out;
            box-shadow: 0 0 8px rgba(255,255,255,0.8);
        }
        @keyframes twinkle {
            0%, 100% { opacity: 0.2; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.5); }
        }
        .container {
            max-width: 100%; /* Full width on mobile */
            margin: 0 auto;
            padding: 15px; /* Reduced padding for mobile */
            position: relative;
            z-index: 1;
        }
        /* Particle background - falling hearts */
        #particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: 0;
            pointer-events: none;
        }
        .heart {
            position: absolute;
            color: #ff69b4;
            font-size: 18px; /* Smaller for mobile */
            text-shadow: 0 0 8px #ff1493;
            animation: float 8s infinite linear;
        }
        @keyframes float {
            0% { transform: translateY(100vh) rotate(0deg) scale(0.5); opacity: 0.8; }
            50% { opacity: 1; scale(1); }
            100% { transform: translateY(-100px) rotate(360deg) scale(0.5); opacity: 0; }
        }
        /* Falling pink petals */
        .petal {
            position: absolute;
            background: linear-gradient(45deg, #ff9ff3, #ff6b9d);
            border-radius: 50% 0 50% 0;
            opacity: 0.8;
            box-shadow: 0 0 6px rgba(255, 159, 243, 0.6);
            animation: petalFloat 10s infinite linear;
            z-index: 0;
            width: 12px; /* Smaller for mobile */
            height: 12px;
        }
        @keyframes petalFloat {
            0% { transform: translateY(100vh) rotate(0deg) scale(0.8); opacity: 0; }
            10% { opacity: 0.9; }
            90% { opacity: 0.7; }
            100% { transform: translateY(-50px) rotate(720deg) scale(0.5); opacity: 0; }
        }
        /* Mouse-following heart (hidden on mobile - touch doesn't need it) */
        .follow-heart {
            display: none;
        }
        @keyframes followFade {
            0% { opacity: 1; transform: translate(-50%, -50%) scale(1); }
            100% { opacity: 0; transform: translate(-50%, -50%) scale(0.5); }
        }
        /* Hero section - Mobile optimized */
        .hero {
            text-align: center;
            padding: 60px 0 40px; /* Reduced padding */
            animation: fadeInUp 2.5s ease-out;
        }
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .hero h1 {
            font-size: 2.2em; /* Mobile-friendly size */
            background: linear-gradient(45deg, #ff6b9d, #ff1493, #ff9ff3, #c44569);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 15px;
            text-shadow: 0 0 20px rgba(255, 105, 180, 0.8);
            line-height: 1.3; /* Better line height for mobile */
        }
        .hero p {
            font-size: 1.1em; /* Smaller for mobile */
            margin-bottom: 20px;
            opacity: 0.95;
            text-shadow: 0 0 8px rgba(255,255,255,0.5);
            padding: 0 10px;
        }
        .cake {
            font-size: 3em; /* Smaller for mobile */
            animation: bounce 2s infinite, breath 3s infinite alternate;
            margin: 20px 0;
            text-shadow: 0 0 15px #ff69b4;
        }
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0) scale(1); }
            40% { transform: translateY(-15px) scale(1.05); }
            60% { transform: translateY(-8px) scale(1.02); }
        }
        @keyframes breath {
            0% { filter: drop-shadow(0 0 10px rgba(255,105,180,0.7)); }
            100% { filter: drop-shadow(0 0 20px rgba(255,105,180,1)); }
        }
        /* Highlighted memorial date */
        .memorial-date {
            display: inline-block;
            background: linear-gradient(45deg, #ff1493, #ff69b4);
            padding: 6px 15px; /* Smaller padding */
            border-radius: 50px;
            margin: 8px;
            font-weight: 700;
            font-size: 0.9em; /* Smaller text */
            box-shadow: 0 0 15px rgba(255, 20, 147, 0.6);
            animation: pulse 2s infinite;
        }
        @keyframes pulse {
            0% { transform: scale(1); box-shadow: 0 0 15px rgba(255, 20, 147, 0.6); }
            50% { transform: scale(1.05); box-shadow: 0 0 20px rgba(255, 20, 147, 0.8); }
            100% { transform: scale(1); box-shadow: 0 0 15px rgba(255, 20, 147, 0.6); }
        }
        /* Love story section - Mobile optimized */
        .story {
            padding: 40px 15px; /* Reduced padding */
            text-align: center;
            background: rgba(42, 27, 105, 0.6);
            backdrop-filter: blur(15px);
            border-radius: 20px; /* More rounded for mobile */
            margin: 30px 0;
            border: 1px solid rgba(255, 105, 180, 0.3);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
            animation: storyFade 3s ease-out;
        }
        @keyframes storyFade {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .story h2 {
            font-size: 1.8em; /* Mobile size */
            margin-bottom: 25px;
            background: linear-gradient(45deg, #ff9ff3, #ff6b9d);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 15px rgba(255, 159, 243, 0.6);
        }
        .story p {
            font-size: 1em; /* Mobile size */
            line-height: 1.8;
            max-width: 100%; /* Full width on mobile */
            margin: 0 auto 20px;
            opacity: 0.98;
            text-shadow: 0 0 5px rgba(255,255,255,0.3);
            padding: 0 10px;
        }

        /* ===== Photo carousel - FULLY MOBILE OPTIMIZED ===== */
        .photo-frame-section {
            text-align: center;
            margin-bottom: 30px;
        }
        .photo-frame-section h2 {
            font-size: 1.8em; /* Mobile size */
            background: linear-gradient(45deg, #ff9ff3, #ff69b4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 25px;
            text-shadow: 0 0 15px rgba(255, 159, 243, 0.6);
        }
        /* Carousel container - Touch-friendly */
        .carousel-container {
            position: relative;
            width: 100%;
            max-width: 100%; /* Full width on mobile */
            margin: 0 auto;
            border-radius: 15px; /* More rounded */
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(255, 105, 180, 0.4);
            border: 6px solid; /* Thinner border for mobile */
            border-image: linear-gradient(45deg, #ff69b4, #9370db, #ff69b4) 1;
            /* Prevent touch scrolling issues */
            touch-action: pan-y;
        }
        /* Carousel wrapper - Responsive height (16:9 ratio for mobile) */
        .carousel-wrapper {
            width: 100%;
            aspect-ratio: 3/4; /* Portrait ratio for mobile photos */
            overflow: hidden !important;
            position: relative;
        }
        .carousel-slide {
            width: 100%;
            height: 100%;
            transition: transform 0.3s ease; /* Faster transition for mobile */
            position: absolute;
            top: 0;
            left: 0;
        }
        /* Carousel photo */
        .carousel-photo {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        .carousel-container:hover .carousel-photo {
            transform: scale(1.02); /* Subtle zoom for mobile */
        }
        /* Carousel buttons - Larger touch targets */
        .carousel-btn {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 50px; /* Larger touch area */
            height: 50px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff69b4, #ff1493);
            border: none;
            color: white;
            font-size: 1.2em;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 10;
            box-shadow: 0 4px 10px rgba(255, 105, 180, 0.5);
            /* Larger touch target (invisible padding) */
            padding: 10px;
            margin: 0 5px;
        }
        .carousel-btn:hover {
            transform: translateY(-50%) scale(1.05);
            box-shadow: 0 6px 15px rgba(255, 105, 180, 0.7);
        }
        .prev-btn {
            left: 5px;
        }
        .next-btn {
            right: 5px;
        }
        /* Carousel indicators - Mobile-friendly */
        .carousel-indicators {
            position: relative;
            display: flex;
            gap: 8px;
            margin: 15px auto 0;
            justify-content: center;
            width: fit-content;
            background: rgba(0,0,0,0.2);
            padding: 6px 12px;
            border-radius: 20px;
            z-index: 20;
        }
        .indicator-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.5);
            cursor: pointer;
            transition: all 0.3s ease;
            /* Larger touch area */
            padding: 4px;
        }
        .indicator-dot.active {
            background: #ff69b4;
            transform: scale(1.2);
            box-shadow: 0 0 8px #ff69b4;
        }
        /* Carousel caption - Mobile optimized */
        .carousel-caption {
            position: absolute;
            bottom: 15px;
            left: 0;
            width: 100%;
            padding: 10px 15px;
            background: linear-gradient(transparent, rgba(0,0,0,0.7));
            color: #ffd1dc;
            font-size: 1em;
            text-align: center;
            text-shadow: 0 0 10px #ff1493;
            z-index: 15;
        }

        /* ===== Video player - Mobile optimized ===== */
        .music-theme-section {
            text-align: center;
            position: relative;
            padding: 25px 15px;
            background: rgba(255, 105, 180, 0.1);
            border-radius: 15px;
            border: 1px solid rgba(255, 105, 180, 0.2);
            margin: 30px 0;
        }
        .music-theme-section h2 {
            font-size: 1.8em;
            background: linear-gradient(45deg, #ff69b4, #ff9ff3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 20px;
        }
        .music-info {
            font-size: 1em;
            margin-bottom: 20px;
            color: #ffd1dc;
            text-shadow: 0 0 8px rgba(255, 159, 243, 0.7);
            padding: 0 10px;
        }
        /* Video container - Full width on mobile */
        .video-container {
            position: relative;
            width: 100%;
            max-width: 100%;
            margin: 0 auto 15px;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 8px 20px rgba(255, 105, 180, 0.3);
            border: 2px solid #ff69b4;
        }
        #themeVideo {
            width: 100%;
            height: auto;
            aspect-ratio: 16/9;
            background: rgba(0, 0, 0, 0.8);
            display: block;
        }
        /* Video cover overlay - Mobile friendly */
        .video-cover-overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(rgba(42, 27, 105, 0.6), rgba(29, 15, 70, 0.8));
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            z-index: 5;
            transition: all 0.3s ease;
        }
        .video-cover-overlay.hidden {
            display: none;
        }
        .video-cover-overlay i {
            font-size: 4em; /* Smaller for mobile */
            color: #ff69b4;
            text-shadow: 0 0 20px rgba(255, 105, 180, 0.8);
            transition: transform 0.3s ease;
        }
        .video-cover-overlay:hover i {
            transform: scale(1.05);
        }
        /* Music notes - Smaller for mobile */
        .music-notes {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }
        .note {
            position: absolute;
            font-size: 18px;
            color: #ff69b4;
            text-shadow: 0 0 10px #ff1493;
            animation: noteFloat 6s infinite ease-in-out;
            opacity: 0;
        }
        @keyframes noteFloat {
            0% {
                transform: translateY(100%) rotate(0deg);
                opacity: 0;
            }
            20% {
                opacity: 1;
            }
            80% {
                opacity: 1;
            }
            100% {
                transform: translateY(-20%) rotate(360deg);
                opacity: 0;
            }
        }

        /* ===== Photo + Video container ===== */
        .photo-music-section {
            margin: 40px 0;
            padding: 30px 15px;
            background: rgba(35, 18, 82, 0.7);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            border: 1px solid rgba(255, 105, 180, 0.4);
            box-shadow: 0 10px 30px rgba(0,0,0,0.4);
        }

        /* Eternal promise section - Mobile optimized */
        .promise {
            padding: 40px 15px;
            text-align: center;
        }
        .promise h2 {
            font-size: 1.8em;
            margin-bottom: 25px;
            background: linear-gradient(45deg, #ff9ff3, #ff6b9d, #c44569);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            text-shadow: 0 0 20px rgba(255, 159, 243, 0.8);
        }
        /* Love button - Larger touch target */
        .love-btn {
            background: linear-gradient(45deg, #ff1493, #c71585, #ff69b4);
            border: none;
            color: white;
            padding: 18px 35px; /* Larger touch area */
            font-size: 1.2em;
            border-radius: 60px;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 8px 20px rgba(255, 20, 147, 0.5);
            margin: 15px 0;
            text-shadow: 0 0 8px rgba(255,255,255,0.5);
            font-weight: 700;
            position: relative;
            overflow: hidden;
            /* Larger touch target */
            min-width: 200px;
        }
        .love-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: 0.6s;
        }
        .love-btn:hover::before {
            left: 100%;
        }
        .love-btn:hover {
            transform: translateY(-5px) scale(1.03);
            box-shadow: 0 12px 25px rgba(255, 20, 147, 0.7);
        }
        .love-btn:active {
            transform: translateY(-2px) scale(1.01);
        }
        /* Confession popup - Full width on mobile */
        .confession {
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) scale(0);
            background: rgba(255, 105, 180, 0.95);
            backdrop-filter: blur(15px);
            padding: 30px 20px;
            border-radius: 20px;
            border: 2px solid #fff;
            box-shadow: 0 0 50px rgba(255, 20, 147, 0.8);
            z-index: 9999;
            opacity: 0;
            transition: all 0.6s cubic-bezier(0.34, 1.56, 0.64, 1);
            width: 90%; /* Full width on mobile */
            max-width: 400px;
        }
        .confession.show {
            transform: translate(-50%, -50%) scale(1);
            opacity: 1;
        }
        .confession h3 {
            font-size: 1.8em;
            color: #fff;
            text-shadow: 0 0 15px rgba(255,255,255,0.8);
            margin-bottom: 15px;
        }
        .confession p {
            font-size: 1.1em;
            color: #fff;
            text-shadow: 0 0 8px rgba(255,255,255,0.6);
            margin-bottom: 10px;
        }
        /* Close button - Larger touch target */
        .close-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            background: #fff;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            font-size: 1.1em;
            color: #ff1493;
            cursor: pointer;
            box-shadow: 0 0 10px rgba(255,255,255,0.8);
        }
        /* Fireworks - Mobile optimized */
        .fireworks {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1000;
            display: none;
        }
        .firework-trail {
            position: absolute;
            width: 2px;
            background: linear-gradient(to top, transparent, #ffd700, #ff69b4);
            border-radius: 50%;
            animation: trailUp 1s ease-out forwards;
        }
        @keyframes trailUp {
            0% { 
                height: 0; 
                transform: translateY(100vh); 
                opacity: 1;
            }
            100% { 
                height: 120px; /* Shorter for mobile */
                transform: translateY(calc(var(--y) * 1px)); 
                opacity: 0;
            }
        }
        .firework-particle {
            position: absolute;
            pointer-events: none;
            border-radius: 50%;
            animation: explode 1.8s ease-out forwards;
            box-shadow: 0 0 10px currentColor;
            width: 4px; /* Smaller for mobile */
            height: 4px;
        }
        .firework-particle.heart {
            clip-path: path('M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z');
        }
        .firework-particle.star {
            clip-path: polygon(50% 0%, 61% 35%, 98% 35%, 68% 57%, 79% 91%, 50% 70%, 21% 91%, 32% 57%, 2% 35%, 39% 35%);
        }
        @keyframes explode {
            0% { 
                transform: translate(0,0) scale(0); 
                opacity: 1;
            }
            30% { 
                opacity: 1;
            }
            100% { 
                transform: translate(calc(var(--x) * 1px), calc(var(--y) * 1px)) scale(1); 
                opacity: 0;
            }
        }
        /* Music control button - Fixed for mobile (easier to reach) */
        .music-control {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 60px; /* Larger touch target */
            height: 60px;
            border-radius: 50%;
            background: linear-gradient(45deg, #ff1493, #ff69b4);
            border: none;
            color: white;
            font-size: 1.3em;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 20px rgba(255, 20, 147, 0.7);
            cursor: pointer;
            z-index: 999;
            transition: all 0.3s ease;
        }
        .music-control:hover {
            transform: scale(1.05);
            box-shadow: 0 0 25px rgba(255, 20, 147, 0.9);
        }

        /* Footer - Mobile optimized */
        .footer {
            position: relative;
            margin-top: 40px;
            padding: 40px 15px 20px;
            text-align: center;
            background: rgba(29, 15, 70, 0.7);
            backdrop-filter: blur(15px);
            border-radius: 20px 20px 0 0;
            border-top: 1px solid rgba(255, 105, 180, 0.4);
            box-shadow: 0 -8px 20px rgba(0,0,0,0.3);
        }
        /* Typewriter effect */
        .typewriter-container {
            font-size: 1.1em;
            margin-bottom: 25px;
            padding: 15px;
            background: rgba(255, 105, 180, 0.1);
            border-radius: 15px;
            border: 1px solid rgba(255, 105, 180, 0.2);
            min-height: 70px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 0 15px rgba(255, 105, 180, 0.2);
        }
        .typewriter-text {
            color: #ff9ff3;
            text-shadow: 0 0 10px rgba(255, 159, 243, 0.7);
            border-right: 2px solid #ff69b4;
            padding-right: 6px;
            animation: blink 1s infinite;
        }
        @keyframes blink {
            0%, 100% { border-color: transparent; }
            50% { border-color: #ff69b4; }
        }
        /* Blessings tags - Wrap nicely on mobile */
        .blessings {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px; /* Smaller gap */
            margin: 25px 0;
            padding: 0 10px;
        }
        .blessing-item {
            background: linear-gradient(45deg, rgba(255, 20, 147, 0.2), rgba(255, 105, 180, 0.2));
            padding: 10px 20px;
            border-radius: 50px;
            border: 1px solid rgba(255, 105, 180, 0.3);
            font-size: 0.9em;
            color: #ffd1dc;
            text-shadow: 0 0 8px rgba(255,255,255,0.4);
            animation: floatUp 6s infinite ease-in-out;
            /* Smaller for mobile */
            max-width: 120px;
            text-align: center;
        }
        .blessing-item:nth-child(2n) {
            animation-delay: 1s;
        }
        .blessing-item:nth-child(3n) {
            animation-delay: 2s;
        }
        @keyframes floatUp {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-8px); }
        }
        /* Signature section */
        .signature {
            margin-top: 30px;
            padding-top: 20px;
            border-top: 1px dashed rgba(255, 105, 180, 0.3);
        }
        .signature h3 {
            font-size: 1.4em;
            background: linear-gradient(45deg, #ff69b4, #ff9ff3);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }
        .signature p {
            font-size: 1em;
            opacity: 0.9;
            margin-bottom: 5px;
        }
        .signature .date {
            font-size: 0.9em;
            opacity: 0.7;
            margin-top: 8px;
            color: #ffd1dc;
        }
        /* Footer hearts */
        .footer-hearts {
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%);
            display: flex;
            gap: 8px;
        }
        .footer-heart {
            font-size: 20px;
            color: #ff69b4;
            text-shadow: 0 0 10px #ff1493;
            animation: bounce 2s infinite;
        }
        .footer-heart:nth-child(1) { animation-delay: 0s; }
        .footer-heart:nth-child(2) { animation-delay: 0.3s; }
        .footer-heart:nth-child(3) { animation-delay: 0.6s; }

        /* Extra small screens (iPhone SE, Galaxy A10) */
        @media (max-width: 400px) {
            .hero h1 {
                font-size: 1.8em;
            }
            .cake {
                font-size: 2.5em;
            }
            .love-btn {
                padding: 15px 25px;
                font-size: 1.1em;
                min-width: 180px;
            }
            .carousel-btn {
                width: 45px;
                height: 45px;
                font-size: 1em;
            }
            .confession h3 {
                font-size: 1.6em;
            }
            .confession p {
                font-size: 1em;
            }
        }
    </style>
</head>
<body>
    <!-- Starry sky background -->
    <div class="stars" id="stars"></div>
    
    <!-- Particle heart background -->
    <canvas id="particles"></canvas>

    <div class="container">
        <!-- Hero section -->
        <section class="hero">
            <h1>🎂 小萌20岁生日快乐！ 🎂</h1>
            <p>2025年12月12日</p>
            <div class="cake">
                <i class="fas fa-birthday-cake"></i>
            </div>
            <p>今天是你的特别日子，愿幸福永远伴你左右 💖</p>
            <div class="memorial-date">相遇纪念：10月28日 💘</div>
        </section>

        <!-- Love story section -->
        <section class="story">
            <h2>💕 我们的爱情故事 💕</h2>
            <p>一月之遇，满心是你。从直播间的那一眼，到微信里的每一次通话，你让我感受到初恋的甜蜜。</p>
            <p>相差六岁，相隔千里，却心心相印。<span class="memorial-date">10月28日</span>，我们相遇，一个多月了，我只想说：</p>
            <p>王浩静，我爱你。此生只爱你一人。</p>
            <p>往后余生，常伴你左右，守护这份浪漫。</p>
        </section>

        <!-- Photo + Video section -->
        <section class="photo-music-section">
            <!-- Photo carousel (Xiao Meng's photos only) -->
            <div class="photo-frame-section">
                <h2>💖 小萌的专属回忆 💖</h2>
                <!-- Carousel container -->
                <div class="carousel-container" id="carousel">
                    <!-- Carousel content wrapper -->
                    <div class="carousel-wrapper" id="carouselWrapper">
                        <div class="carousel-slide" id="carouselSlide">
                            <!-- Initial photo -->
                            <img src="pic5.jpeg" alt="Xiao Meng's cute moment" class="carousel-photo">
                        </div>
                    </div>
                    
                    <!-- Carousel navigation buttons -->
                    <button class="carousel-btn prev-btn" id="prevBtn">
                        <i class="fas fa-chevron-left"></i>
                    </button>
                    <button class="carousel-btn next-btn" id="nextBtn">
                        <i class="fas fa-chevron-right"></i>
                    </button>
                    
                    <!-- Carousel caption -->
                    <div class="carousel-caption" id="carouselCaption">我的可爱小萌 😘</div>
                </div>
                
                <!-- Carousel indicators (dots) - MOVED OUTSIDE the frame -->
                <div class="carousel-indicators" id="carouselIndicators"></div>
            </div>

            <!-- Video player section -->
            <div class="music-theme-section">
                <div class="music-notes" id="musicNotes"></div>
                <h2>🎬 我们的专属视频 🎬</h2>
                <p class="music-info">《呆萌机》- 只想和你一起走过每一天</p>
                
                <!-- Video container -->
                <div class="video-container">
                    <!-- Video player -->
                    <video id="themeVideo" controls poster="pic5.jpeg">
                        <source src="daimengji.mp4" type="video/mp4">
                        Your browser does not support video playback. Please update your browser.
                    </video>
                    
                    <!-- Video cover overlay -->
                    <div class="video-cover-overlay" id="videoCoverOverlay">
                        <i class="fas fa-play-circle"></i>
                    </div>
                </div>
                
                <p style="color: #ff9ff3; font-size: 1em; margin-top: 15px;">🎥 愿这个视频承载我们的美好回忆 🎥</p>
            </div>
        </section>

        <!-- Eternal promise section -->
        <section class="promise">
            <h2>🌟 永恒的承诺 🌟</h2>
            <p>小萌，生日快乐！愿我们的爱如星星般闪耀，永不熄灭。</p>
            <button class="love-btn" onclick="showFireworks()">
                <i class="fas fa-heart"></i> 我爱你，永远！
            </button>
            <p style="margin-top: 20px; font-size: 1.1em;">点击按钮，释放浪漫烟花 🎆</p>
        </section>

        <!-- Footer section -->
        <footer class="footer">
            <!-- Footer heart decorations -->
            <div class="footer-hearts">
                <div class="footer-heart">💖</div>
                <div class="footer-heart">💕</div>
                <div class="footer-heart">💘</div>
            </div>
            
            <!-- Typewriter effect love message -->
            <div class="typewriter-container">
                <div class="typewriter-text" id="typewriter"></div>
            </div>
            
            <!-- Blessings tags -->
            <div class="blessings">
                <div class="blessing-item">✨ 平安喜乐</div>
                <div class="blessing-item">💫 万事顺意</div>
                <div class="blessing-item">🥰 被爱包围</div>
                <div class="blessing-item">🎀 永远可爱</div>
                <div class="blessing-item">💞 爱意长存</div>
            </div>
            
            <!-- Signature -->
            <div class="signature">
                <h3>致我最爱的小萌 - 王浩静</h3>
                <p>你的专属守护天使 💌</p>
                <p>爱你的人永远在你身边</p>
                <div class="date">❤️ 2025年 · 生日专属 ❤️</div>
            </div>
        </footer>
    </div>

    <!-- Fireworks container -->
    <div id="fireworks" class="fireworks"></div>
    
    <!-- Confession popup -->
    <div class="confession" id="confession">
        <button class="close-btn" onclick="closeConfession()">×</button>
        <h3>💖 致我的小萌 💖</h3>
        <p>王浩静，生日快乐！</p>
        <p>遇见你是我此生最大的幸运</p>
        <p>愿我的爱能温暖你的每一天</p>
        <p>余生漫漫，我只爱你一人 ❤️</p>
    </div>

    <!-- Music control button -->
    <button class="music-control" id="musicBtn">
        <i class="fas fa-music"></i>
    </button>

    <!-- Background music -->
    <audio id="bgMusic" loop>
        <source src="happy-birthday-254480.mp3" type="audio/mpeg">
    </audio>

    <script>
        // Global variable declaration
        let currentIndex = 0;
        let noteInterval = null;
        let autoPlay = null;
        // Touch variables for carousel
        let touchStartX = 0;
        let touchEndX = 0;

        // Photo data for Xiao Meng (8 photos)
        const photoData = [
            {
                url: "pic5.jpeg",
                alt: "Xiao Meng's cute moment",
                caption: "我的可爱小萌 😘"
            },
            {
                url: "pic2.jpeg",
                alt: "Xiao Meng's beautiful moment",
                caption: "眼里的星光 ✨"
            },
            {
                url: "pic1.jpeg",
                alt: "Xiao Meng's playful moment",
                caption: "俏皮小可爱 😜"
            },
            {
                url: "pic10.jpeg",
                alt: "Xiao Meng's gentle moment",
                caption: "温柔的你超美 🥰"
            },
            {
                url: "pic7.jpeg",
                alt: "Xiao Meng's silly moment",
                caption: "憨憨小宝贝 😆"
            },
            {
                url: "pic4.jpeg",
                alt: "Xiao Meng's sweet & cool moment",
                caption: "甜酷小宝贝 😎"
            },
            {
                url: "pic8.jpeg",
                alt: "Xiao Meng's energetic moment",
                caption: "元气满满的你 💖"
            },
            {
                url: "pic6.jpeg",
                alt: "Xiao Meng's heart-stirring moment",
                caption: "一眼心动的你 💘"
            }
        ];

        // Generate twinkling stars
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const starCount = window.innerWidth > 768 ? 200 : 150; // Fewer stars on mobile
            
            for (let i = 0; i < starCount; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = `${Math.random() * 100}vw`;
                star.style.top = `${Math.random() * 100}vh`;
                star.style.animationDelay = `${Math.random() * 3}s`;
                star.style.width = `${Math.random() * 2 + 1}px`;
                star.style.height = star.style.width;
                starsContainer.appendChild(star);
            }
        }

        // Create falling heart particles
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.innerHTML = ['💖', '💕', '💗', '💝'][Math.floor(Math.random() * 4)];
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 4 + 5) + 's';
            heart.style.fontSize = (Math.random() * 8 + 12) + 'px';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 9000);
        }

        // Create falling pink petals
        function createPetal() {
            const petal = document.createElement('div');
            petal.className = 'petal';
            petal.style.left = Math.random() * 100 + 'vw';
            petal.style.animationDuration = (Math.random() * 6 + 8) + 's';
            petal.style.width = (Math.random() * 8 + 6) + 'px';
            petal.style.height = petal.style.width;
            petal.style.animationDelay = Math.random() * 5 + 's';
            document.body.appendChild(petal);
            setTimeout(() => petal.remove(), 12000);
        }

        // Enhanced fireworks effect
        function showFireworks() {
            // Show confession popup
            document.getElementById('confession').classList.add('show');
            
            const fireworks = document.getElementById('fireworks');
            fireworks.style.display = 'block';
            fireworks.innerHTML = '';

            // Firework color sets
            const colorSets = [
                ['#ff1493', '#ff69b4', '#ff9ff3'], // Pink series
                ['#ffd700', '#ff8c00', '#ff4500'], // Gold series
                ['#9370db', '#8a2be2', '#9932cc'], // Purple series
                ['#00ffff', '#00bfff', '#1e90ff']  // Blue series
            ];

            // Fewer fireworks on mobile
            const fireworkCount = window.innerWidth > 768 ? 15 : 10;

            // Create multiple fireworks
            for (let i = 0; i < fireworkCount; i++) {
                setTimeout(() => {
                    // Random position (centered for mobile)
                    const x = Math.random() * (window.innerWidth - 40) + 20;
                    const y = Math.random() * (window.innerHeight * 0.6);
                    
                    // Create firework trail
                    const trail = document.createElement('div');
                    trail.className = 'firework-trail';
                    trail.style.left = x + 'px';
                    trail.style.bottom = '0';
                    trail.style.setProperty('--y', y);
                    fireworks.appendChild(trail);
                    
                    // Explosion effect (after trail animation)
                    setTimeout(() => {
                        const colors = colorSets[Math.floor(Math.random() * colorSets.length)];
                        const particleCount = window.innerWidth > 768 ? 80 : 60; // Fewer particles on mobile
                        const shapes = ['', 'heart', 'star'];
                        
                        for (let j = 0; j < particleCount; j++) {
                            const particle = document.createElement('div');
                            particle.className = `firework-particle ${shapes[Math.floor(Math.random() * shapes.length)]}`;
                            
                            // Random angle and distance (smaller for mobile)
                            const angle = Math.random() * Math.PI * 2;
                            const distance = window.innerWidth > 768 ? (80 + Math.random() * 120) : (60 + Math.random() * 80);
                            const dx = Math.cos(angle) * distance;
                            const dy = Math.sin(angle) * distance;
                            
                            // Style settings
                            particle.style.left = x + 'px';
                            particle.style.top = y + 'px';
                            particle.style.setProperty('--x', dx);
                            particle.style.setProperty('--y', dy);
                            particle.style.width = (Math.random() * 4 + 2) + 'px';
                            particle.style.height = particle.style.width;
                            particle.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                            particle.style.color = particle.style.backgroundColor;
                            particle.style.animationDelay = (j * 0.01) + 's';
                            
                            fireworks.appendChild(particle);
                            
                            // Remove particle
                            setTimeout(() => particle.remove(), 2000);
                        }
                    }, 1000);
                }, i * 300);
            }

            // Hide fireworks container
            setTimeout(() => fireworks.style.display = 'none', 8000);
        }

        // Close confession popup
        function closeConfession() {
            document.getElementById('confession').classList.remove('show');
        }

        // Background music control (button only)
        function initMusic() {
            const music = document.getElementById('bgMusic');
            const musicBtn = document.getElementById('musicBtn');
            let isPlaying = false;

            // Music control only via button click
            musicBtn.addEventListener('click', () => {
                if (isPlaying) {
                    music.pause();
                    musicBtn.innerHTML = '<i class="fas fa-music"></i>';
                } else {
                    // Try to play music (handle browser autoplay restrictions)
                    music.play().catch(() => {
                        alert('请允许音频播放权限，再点击音乐按钮 💖');
                    });
                    musicBtn.innerHTML = '<i class="fas fa-pause"></i>';
                }
                isPlaying = !isPlaying;
            });
        }

        // Typewriter effect initialization
        function initTypewriter() {
            const texts = [
                "小萌，生日快乐！",
                "王浩静，我爱你！",
                "余生漫漫，只爱你一人～",
                "愿我的爱温暖你的每一天 ❤️"
            ];
            const typewriter = document.getElementById('typewriter');
            let textIndex = 0;
            let charIndex = 0;
            
            function type() {
                if (charIndex < texts[textIndex].length) {
                    typewriter.textContent += texts[textIndex].charAt(charIndex);
                    charIndex++;
                    setTimeout(type, 150);
                } else {
                    setTimeout(erase, 2000);
                }
            }
            
            function erase() {
                if (charIndex > 0) {
                    typewriter.textContent = texts[textIndex].substring(0, charIndex - 1);
                    charIndex--;
                    setTimeout(erase, 80);
                } else {
                    textIndex = (textIndex + 1) % texts.length;
                    setTimeout(type, 500);
                }
            }
            type();
        }

        // Create carousel indicators (dots)
        function createIndicators() {
            const carouselIndicators = document.getElementById('carouselIndicators');
            if (!carouselIndicators) return;
            
            photoData.forEach((_, index) => {
                const dot = document.createElement('div');
                dot.className = `indicator-dot ${index === 0 ? 'active' : ''}`;
                dot.setAttribute('data-index', index);
                dot.addEventListener('click', () => {
                    currentIndex = index;
                    updateCarousel();
                });
                carouselIndicators.appendChild(dot);
            });
        }

        // Update carousel content
        function updateCarousel() {
            const carouselSlide = document.getElementById('carouselSlide');
            const carouselCaption = document.getElementById('carouselCaption');
            if (!carouselSlide || !carouselCaption) return;
            
            const currentPhoto = photoData[currentIndex];
            carouselSlide.innerHTML = `<img src="${currentPhoto.url}" alt="${currentPhoto.alt}" class="carousel-photo">`;
            carouselCaption.textContent = currentPhoto.caption;
            
            const dots = document.querySelectorAll('.indicator-dot');
            dots.forEach((dot, index) => {
                dot.classList.toggle('active', index === currentIndex);
            });
        }

        // Bind carousel button events + touch swipe
        function bindCarouselEvents() {
            const prevBtn = document.getElementById('prevBtn');
            const nextBtn = document.getElementById('nextBtn');
            const carousel = document.getElementById('carousel');
            
            // Next/Prev button clicks
            if (prevBtn) {
                prevBtn.addEventListener('click', () => {
                    currentIndex = (currentIndex - 1 + photoData.length) % photoData.length;
                    updateCarousel();
                });
            }
            
            if (nextBtn) {
                nextBtn.addEventListener('click', () => {
                    currentIndex = (currentIndex + 1) % photoData.length;
                    updateCarousel();
                });
            }

            // Touch swipe functionality (mobile)
            carousel.addEventListener('touchstart', (e) => {
                touchStartX = e.changedTouches[0].screenX;
                // Pause autoplay on touch
                clearInterval(autoPlay);
            });

            carousel.addEventListener('touchend', (e) => {
                touchEndX = e.changedTouches[0].screenX;
                handleSwipe();
                // Resume autoplay after touch
                autoPlay = setInterval(() => {
                    currentIndex = (currentIndex + 1) % photoData.length;
                    updateCarousel();
                }, 3000);
            });

            // Handle swipe direction
            function handleSwipe() {
                const swipeThreshold = 50; // Minimum swipe distance
                const swipeDistance = touchEndX - touchStartX;
                
                if (swipeDistance > swipeThreshold) {
                    // Swipe right → prev photo
                    currentIndex = (currentIndex - 1 + photoData.length) % photoData.length;
                    updateCarousel();
                } else if (swipeDistance < -swipeThreshold) {
                    // Swipe left → next photo
                    currentIndex = (currentIndex + 1) % photoData.length;
                    updateCarousel();
                }
            }

            // Auto-play carousel (slower on mobile)
            const autoPlaySpeed = window.innerWidth > 768 ? 3000 : 4000;
            autoPlay = setInterval(() => {
                currentIndex = (currentIndex + 1) % photoData.length;
                updateCarousel();
            }, autoPlaySpeed);

            // Pause auto-play on mouse enter (desktop) / touch (mobile)
            const carouselSlide = document.getElementById('carouselSlide');
            if (carouselSlide) {
                carouselSlide.parentElement.addEventListener('mouseenter', () => {
                    clearInterval(autoPlay);
                });
                // Resume auto-play on mouse leave
                carouselSlide.parentElement.addEventListener('mouseleave', () => {
                    autoPlay = setInterval(() => {
                        currentIndex = (currentIndex + 1) % photoData.length;
                        updateCarousel();
                    }, autoPlaySpeed);
                });
            }
        }

        // Video player initialization (independent from background music)
        function initVideoPlayer() {
            const themeVideo = document.getElementById('themeVideo');
            const videoCoverOverlay = document.getElementById('videoCoverOverlay');
            const musicNotes = document.getElementById('musicNotes');
            const notes = ['🎵', '🎶', '♪', '♫', '♩'];
            
            if (!themeVideo || !videoCoverOverlay || !musicNotes) return;

            // Video load error handling
            themeVideo.addEventListener('error', () => {
                alert('视频加载失败！请检查视频文件是否存在且格式为MP4');
            });

            // Play video on cover click
            videoCoverOverlay.addEventListener('click', () => {
                themeVideo.play().then(() => {
                    videoCoverOverlay.classList.add('hidden');
                }).catch(err => {
                    console.log('Video playback failed: ', err);
                    alert('请点击视频内的播放按钮开始播放（浏览器自动播放限制）');
                });
            });

            // Generate video music notes (fewer on mobile)
            function createNote() {
                if (themeVideo.paused) return;
                
                const note = document.createElement('div');
                note.className = 'note';
                note.textContent = notes[Math.floor(Math.random() * notes.length)];
                note.style.left = `${Math.random() * 90 + 5}%`;
                note.style.bottom = '0';
                note.style.animationDelay = `${Math.random() * 2}s`;
                note.style.fontSize = `${Math.random() * 10 + 10}px`;
                
                musicNotes.appendChild(note);
                setTimeout(() => note.remove(), 4000);
            }

            // Video play event
            themeVideo.addEventListener('play', () => {
                videoCoverOverlay.classList.add('hidden');
                // Fewer initial notes on mobile
                const initialNotes = window.innerWidth > 768 ? 5 : 3;
                for (let i = 0; i < initialNotes; i++) {
                    setTimeout(createNote, i * 300);
                }
                // Slower note generation on mobile
                const noteSpeed = window.innerWidth > 768 ? 500 : 700;
                if (noteInterval) clearInterval(noteInterval);
                noteInterval = setInterval(createNote, noteSpeed);
            });

            // Video pause event
            themeVideo.addEventListener('pause', () => {
                clearInterval(noteInterval);
            });

            // Video end event
            themeVideo.addEventListener('ended', () => {
                clearInterval(noteInterval);
                videoCoverOverlay.classList.remove('hidden');
            });
        }

        // Initialize all functions on page load
        document.addEventListener('DOMContentLoaded', function() {
            // Basic effects (slower on mobile)
            createStars();
            const heartInterval = window.innerWidth > 768 ? 200 : 300;
            const petalInterval = window.innerWidth > 768 ? 500 : 600;
            setInterval(createHeart, heartInterval);
            setInterval(createPetal, petalInterval);
            initMusic(); 
            initTypewriter();
            
            // Carousel initialization
            createIndicators();
            updateCarousel();
            bindCarouselEvents();
            
            // Video initialization
            initVideoPlayer();
        });

        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({ behavior: 'smooth' });
            });
        });
    </script>
</body>
</html>
