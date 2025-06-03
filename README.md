<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="author" content="PinStyle Store">
    <meta name="description" content="Tienda oficial de pines y stickers personalizados - PinStyle">
    <title>PinStyle - Tienda Oficial de Pines y Stickers</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
            overflow-x: hidden;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            margin-bottom: 50px;
            background: rgba(255, 255, 255, 0.95);
            padding: 40px;
            border-radius: 25px;
            backdrop-filter: blur(15px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            animation: fadeInUp 0.8s ease;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            font-size: 3.5em;
            margin-bottom: 15px;
            background: linear-gradient(45deg, #667eea, #764ba2, #f093fb);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: 800;
            letter-spacing: -2px;
        }

        .subtitle {
            color: #666;
            font-size: 1.4em;
            margin-bottom: 25px;
            font-weight: 300;
        }

        .description {
            color: #666;
            margin-bottom: 20px;
            line-height: 1.8;
            font-size: 1.1em;
            max-width: 800px;
            margin-left: auto;
            margin-right: auto;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 40px;
            margin-bottom: 50px;
        }

        .product-card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 35px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(15px);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            position: relative;
            overflow: hidden;
        }

        .product-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
            transition: left 0.6s;
        }

        .product-card:hover::before {
            left: 100%;
        }

        .product-card:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 30px 60px rgba(0, 0, 0, 0.15);
        }

        .product-title {
            font-size: 2.2em;
            color: #4a5568;
            margin-bottom: 20px;
            text-align: center;
            font-weight: 700;
        }

        .product-icon {
            text-align: center;
            font-size: 5em;
            margin-bottom: 25px;
            filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.1));
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        .custom-pin-icon {
            width: 120px;
            height: 120px;
            display: block;
            margin: 0 auto 25px;
            filter: drop-shadow(0 4px 8px rgba(0, 0, 0, 0.1));
        }

        .size-options {
            margin-bottom: 25px;
        }

        .size-options h3 {
            color: #4a5568;
            margin-bottom: 15px;
            font-size: 1.3em;
            font-weight: 600;
        }

        .size-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 15px;
        }

        .size-option {
            padding: 20px 15px;
            border: 2px solid #e2e8f0;
            border-radius: 15px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            background: white;
            position: relative;
            overflow: hidden;
        }

        .size-option::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea, #764ba2);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .size-option:hover {
            border-color: #667eea;
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.2);
        }

        .size-option.selected {
            border-color: #667eea;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            transform: scale(1.05);
        }

        .size-option.selected::before {
            opacity: 1;
        }

        .size-name, .size-price {
            position: relative;
            z-index: 1;
        }

        .size-name {
            font-weight: 700;
            margin-bottom: 8px;
            font-size: 1.1em;
        }

        .size-price {
            color: #e53e3e;
            font-size: 1.4em;
            font-weight: 800;
        }

        .selected .size-price {
            color: white;
        }

        .quantity-section {
            margin: 25px 0;
        }

        .quantity-section h3 {
            color: #4a5568;
            margin-bottom: 15px;
            font-size: 1.3em;
            font-weight: 600;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin-top: 15px;
        }

        .quantity-btn {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            border: none;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 1.5em;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            font-weight: bold;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
        }

        .quantity-btn:hover {
            transform: scale(1.15);
            box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);
        }

        .quantity-btn:active {
            transform: scale(0.95);
        }

        .quantity-display {
            font-size: 1.8em;
            font-weight: 800;
            min-width: 60px;
            text-align: center;
            color: #4a5568;
        }

        .total-price {
            text-align: center;
            margin: 25px 0;
            font-size: 1.8em;
            color: #e53e3e;
            font-weight: 800;
            padding: 15px;
            background: rgba(229, 62, 62, 0.1);
            border-radius: 15px;
            border: 2px solid rgba(229, 62, 62, 0.2);
        }

        .add-to-cart {
            width: 100%;
            padding: 18px;
            background: linear-gradient(135deg, #48bb78, #38a169);
            color: white;
            border: none;
            border-radius: 15px;
            font-size: 1.2em;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            text-transform: uppercase;
            letter-spacing: 1px;
            position: relative;
            overflow: hidden;
        }

        .add-to-cart::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.6s;
        }

        .add-to-cart:hover::before {
            left: 100%;
        }

        .add-to-cart:hover {
            transform: translateY(-3px);
            box-shadow: 0 15px 35px rgba(72, 187, 120, 0.4);
        }

        .add-to-cart:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none;
            box-shadow: none;
        }

        .cart-section {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 25px;
            padding: 40px;
            backdrop-filter: blur(15px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
            animation: fadeInUp 0.8s ease 0.3s both;
        }

        .cart-title {
            font-size: 2.2em;
            color: #4a5568;
            margin-bottom: 30px;
            text-align: center;
            font-weight: 700;
        }

        .cart-items {
            margin-bottom: 25px;
        }

        .cart-item {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            background: rgba(247, 250, 252, 0.8);
            margin-bottom: 15px;
            border-radius: 15px;
            border-left: 5px solid #667eea;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .cart-item:hover {
            transform: translateX(5px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .cart-total {
            text-align: center;
            font-size: 1.8em;
            color: #e53e3e;
            font-weight: 800;
            margin: 30px 0;
            padding: 25px;
            background: linear-gradient(135deg, rgba(229, 62, 62, 0.1), rgba(229, 62, 62, 0.05));
            border-radius: 15px;
            border: 2px solid rgba(229, 62, 62, 0.2);
        }

        .checkout-btn {
            width: 100%;
            padding: 25px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
            border: none;
            border-radius: 15px;
            font-size: 1.3em;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            text-transform: uppercase;
            letter-spacing: 1px;
            position: relative;
            overflow: hidden;
        }

        .checkout-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.6s;
        }

        .checkout-btn:hover::before {
            left: 100%;
        }

        .checkout-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 20px 40px rgba(102, 126, 234, 0.4);
        }

        .empty-cart {
            text-align: center;
            color: #666;
            font-style: italic;
            font-size: 1.2em;
            padding: 40px;
        }

        .remove-btn {
            background: linear-gradient(135deg, #e53e3e, #c53030);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.9em;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .remove-btn:hover {
            transform: scale(1.05);
            box-shadow: 0 4px 12px rgba(229, 62, 62, 0.3);
        }

        @media (max-width: 768px) {
            .container {
                padding: 15px;
            }
            
            .products-grid {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            .size-grid {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 2.5em;
            }
            
            .product-card {
                padding: 25px;
            }
            
            .cart-section {
                padding: 25px;
            }
        }

        .notification {
            position: fixed;
            top: 20px;
            right: 20px;
            background: linear-gradient(135deg, #48bb78, #38a169);
            color: white;
            padding: 15px 25px;
            border-radius: 10px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
            transform: translateX(400px);
            transition: transform 0.3s ease;
            z-index: 1000;
            font-weight: 600;
        }

        .notification.show {
            transform: translateX(0);
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>🎨 PinStyle</h1>
            <p class="subtitle">Pines y Stickers Personalizados</p>
            <p class="description">Expresa tu estilo único con nuestros pines de alta calidad y stickers resistentes. Perfectos para personalizar tu ropa, mochila o cualquier superficie. Diseños exclusivos y materiales premium.</p>
        </header>

        <div class="products-grid">
            <!-- Pines -->
            <div class="product-card">
                <div class="product-icon">
                    <svg class="custom-pin-icon" viewBox="0 0 120 120">
                        <!-- Pin redondo tipo bola 8 -->
                        <circle cx="30" cy="35" r="15" fill="#2d3748" stroke="#4a5568" stroke-width="2"/>
                        <circle cx="30" cy="35" r="8" fill="#fff"/>
                        <text x="26" y="39" font-family="Arial" font-size="8" fill="#2d3748" font-weight="bold">8</text>
                        
                        <!-- Pin estrella -->
                        <path d="M60 20 L67 32 L60 44 L53 32 Z" fill="#667eea"/>
                        <path d="M60 20 L72 26 L60 32 L48 26 Z" fill="#fff" stroke="#667eea" stroke-width="1"/>
                        <path d="M50 23 L70 23 M50 29 L70 29" stroke="#667eea" stroke-width="1.5"/>
                        
                        <!-- Pin rectangular -->
                        <rect x="75" y="25" width="25" height="25" rx="3" fill="#fff" stroke="#764ba2" stroke-width="2"/>
                        <path d="M78 32 L97 32 M78 38 L97 38 M78 44 L97 44" stroke="#764ba2" stroke-width="1.2"/>
                        <rect x="82" y="28" width="4" height="19" fill="#764ba2"/>
                        
                        <!-- Pin planeta -->
                        <circle cx="30" cy="80" r="12" fill="#fff" stroke="#4a5568" stroke-width="2"/>
                        <circle cx="30" cy="80" r="8" fill="none" stroke="#667eea" stroke-width="1.5"/>
                        <ellipse cx="30" cy="80" rx="10" ry="4" fill="none" stroke="#667eea" stroke-width="1.5"/>
                        <circle cx="30" cy="76" r="1.5" fill="#764ba2"/>
                        
                        <!-- Pin con texto -->
                        <rect x="50" y="70" width="30" height="10" rx="5" fill="#fff" stroke="#4a5568" stroke-width="2"/>
                        <text x="65" y="77" font-family="Arial" font-size="5" fill="#4a5568" text-anchor="middle" font-weight="bold">PINS</text>
                        
                        <!-- Pin anime -->
                        <rect x="75" y="65" width="18" height="25" rx="3" fill="#fff" stroke="#4a5568" stroke-width="2"/>
                        <circle cx="80" cy="74" r="1.5" fill="#2d3748"/>
                        <circle cx="88" cy="74" r="1.5" fill="#2d3748"/>
                        <path d="M81 80 Q84 83 87 80" stroke="#e53e3e" stroke-width="1.2" fill="none"/>
                        <path d="M78 70 L81 72 M90 70 L87 72" stroke="#4a5568" stroke-width="1"/>
                        
                        <!-- Brillos -->
                        <circle cx="45" cy="15" r="2" fill="#ffd700" opacity="0.8"/>
                        <circle cx="15" cy="55" r="1.5" fill="#ffd700" opacity="0.6"/>
                        <circle cx="90" cy="55" r="1.8" fill="#ffd700" opacity="0.7"/>
                        <circle cx="105" cy="20" r="1.2" fill="#ffd700" opacity="0.5"/>
                    </svg>
                </div>
                <h2 class="product-title">Pines Premium</h2>
                <p class="description">Pines de alta calidad con respaldo metálico resistente. Perfectos para chaquetas, mochilas y accesorios. Diseños únicos y duraderos.</p>
                
                <div class="size-options">
                    <h3>Selecciona el tamaño:</h3>
                    <div class="size-grid">
                        <div class="size-option" onclick="selectSize('pin', 'chico', 10)">
                            <div class="size-name">Chico</div>
                            <div class="size-price">$10</div>
                        </div>
                        <div class="size-option" onclick="selectSize('pin', 'mediano', 18)">
                            <div class="size-name">Mediano</div>
                            <div class="size-price">$18</div>
                        </div>
                        <div class="size-option" onclick="selectSize('pin', 'grande', 25)">
                            <div class="size-name">Grande</div>
                            <div class="size-price">$25</div>
                        </div>
                    </div>
                </div>

                <div class="quantity-section">
                    <h3>Cantidad:</h3>
                    <div class="quantity-controls">
                        <button class="quantity-btn" onclick="changeQuantity('pin', -1)">−</button>
                        <span class="quantity-display" id="pin-quantity">1</span>
                        <button class="quantity-btn" onclick="changeQuantity('pin', 1)">+</button>
                    </div>
                </div>

                <div class="total-price" id="pin-total">Selecciona un tamaño</div>
                <button class="add-to-cart" onclick="addToCart('pin')" id="pin-add-btn" disabled>Agregar al Carrito</button>
            </div>

            <!-- Stickers -->
            <div class="product-card">
                <div class="product-icon">
                    <svg class="custom-pin-icon" viewBox="0 0 160 120">
                        <!-- Gato negro -->
                        <ellipse cx="25" cy="45" rx="12" ry="18" fill="#2d3748"/>
                        <path d="M15 35 L20 25 L25 35 M25 35 L30 25 L35 35" stroke="#2d3748" stroke-width="2" fill="none"/>
                        <circle cx="20" cy="38" r="1.5" fill="white"/>
                        <circle cx="30" cy="38" r="1.5" fill="white"/>
                        <path d="M15 42 L12 40 M35 42 L38 40" stroke="#2d3748" stroke-width="1.5"/>
                        <path d="M25 50 Q35 55 45 50" stroke="#2d3748" stroke-width="3" fill="none"/>
                        
                        <!-- Estrellas -->
                        <path d="M55 15 L57 20 L62 20 L58 23 L60 28 L55 25 L50 28 L52 23 L48 20 L53 20 Z" fill="none" stroke="#2d3748" stroke-width="2"/>
                        <path d="M70 25 L71.5 28 L75 28 L72.2 30.5 L73.5 34 L70 31.5 L66.5 34 L67.8 30.5 L65 28 L68.5 28 Z" fill="none" stroke="#2d3748" stroke-width="1.8"/>
                        
                        <!-- Guitarra -->
                        <ellipse cx="90" cy="35" rx="8" ry="20" fill="none" stroke="#2d3748" stroke-width="2"/>
                        <rect x="88" y="15" width="4" height="15" fill="none" stroke="#2d3748" stroke-width="2"/>
                        <path d="M85 20 L95 20 M85 22 L95 22 M85 24 L95 24" stroke="#2d3748" stroke-width="1"/>
                        <circle cx="90" cy="42" r="2" fill="none" stroke="#2d3748" stroke-width="1.5"/>
                        
                        <!-- Conejo -->
                        <ellipse cx="120" cy="25" rx="8" ry="12" fill="none" stroke="#2d3748" stroke-width="2"/>
                        <ellipse cx="116" cy="18" rx="2" ry="8" fill="none" stroke="#2d3748" stroke-width="1.5"/>
                        <ellipse cx="124" cy="18" rx="2" ry="8" fill="none" stroke="#2d3748" stroke-width="1.5"/>
                        <circle cx="117" cy="23" r="1" fill="#2d3748"/>
                        <circle cx="123" cy="23" r="1" fill="#2d3748"/>
                        <path d="M118 27 L122 27" stroke="#2d3748" stroke-width="1.5"/>
                        
                        <!-- Onda de sonido -->
                        <path d="M135 15 Q140 12 145 15 Q150 18 155 15 Q160 12 165 15" stroke="#2d3748" stroke-width="2" fill="none"/>
                        <path d="M135 20 Q140 17 145 20 Q150 23 155 20" stroke="#2d3748" stroke-width="2" fill="none"/>
                        
                        <!-- Disco de vinilo -->
                        <circle cx="25" cy="85" r="12" fill="#2d3748"/>
                        <circle cx="25" cy="85" r="8" fill="none" stroke="white" stroke-width="1"/>
                        <circle cx="25" cy="85" r="3" fill="white"/>
                        <text x="22" y="88" font-family="Arial" font-size="4" fill="#2d3748" font-weight="bold">♪</text>
                        
                        <!-- Cassette -->
                        <rect x="60" y="75" width="25" height="15" rx="2" fill="none" stroke="#2d3748" stroke-width="2"/>
                        <circle cx="67" cy="82" r="3" fill="none" stroke="#2d3748" stroke-width="1.5"/>
                        <circle cx="78" cy="82" r="3" fill="none" stroke="#2d3748" stroke-width="1.5"/>
                        <rect x="70" y="80" width="5" height="4" fill="none" stroke="#2d3748" stroke-width="1"/>
                        
                        <!-- Telaraña -->
                        <path d="M110 70 L125 70 L125 85 L110 85 Z" fill="none" stroke="#2d3748" stroke-width="1.5"/>
                        <path d="M110 75 L125 75 M115 70 L115 85 M120 70 L120 85" stroke="#2d3748" stroke-width="1"/>
                        <path d="M112 72 Q117 74 122 72 M112 77 Q117 79 122 77 M112 82 Q117 84 122 82" stroke="#2d3748" stroke-width="1" fill="none"/>
                        
                        <!-- Pixel art cat -->
                        <rect x="140" y="70" width="3" height="3" fill="#2d3748"/>
                        <rect x="143" y="70" width="3" height="3" fill="#2d3748"/>
                        <rect x="146" y="70" width="3" height="3" fill="#2d3748"/>
                        <rect x="140" y="73" width="3" height="3" fill="#2d3748"/>
                        <rect x="146" y="73" width="3" height="3" fill="#2d3748"/>
                        <rect x="140" y="76" width="9" height="3" fill="#2d3748"/>
                        <rect x="141" y="79" width="7" height="3" fill="#2d3748"/>
                        <circle cx="142" cy="72" r="0.8" fill="yellow"/>
                        <circle cx="147" cy="72" r="0.8" fill="yellow"/>
                        
                        <!-- MEOW text style -->
                        <text x="10" y="105" font-family="Arial Black" font-size="8" fill="none" stroke="#2d3748" stroke-width="1.5" font-weight="bold">MEOW</text>
                        
                        <!-- Star Girl text -->
                        <text x="70" y="105" font-family="Arial Black" font-size="7" fill="#2d3748" font-weight="bold" transform="rotate(-5 70 105)">★ GIRL</text>
                        
                        <!-- Decorative elements -->
                        <circle cx="45" cy="10" r="1.5" fill="#667eea" opacity="0.7"/>
                        <circle cx="100" cy="10" r="1.2" fill="#764ba2" opacity="0.6"/>
                        <circle cx="15" cy="65" r="1" fill="#f093fb" opacity="0.5"/>
                        <circle cx="130" cy="55" r="1.3" fill="#667eea" opacity="0.8"/>
                    </svg>
                </div>
                <h2 class="product-title">Stickers Premium</h2>
                <p class="description">Stickers resistentes al agua con adhesivo de larga duración. Ideales para laptops, botellas y superficies lisas. Colores vibrantes que no se desvanecen.</p>
                
                <div class="size-options">
                    <h3>Selecciona el tamaño:</h3>
                    <div class="size-grid">
                        <div class="size-option" onclick="selectSize('sticker', 'chico', 10)">
                            <div class="size-name">Chico</div>
                            <div class="size-price">$10</div>
                        </div>
                        <div class="size-option" onclick="selectSize('sticker', 'mediano', 15)">
                            <div class="size-name">Mediano</div>
                            <div class="size-price">$15</div>
                        </div>
                        <div class="size-option" onclick="selectSize('sticker', 'grande', 20)">
                            <div class="size-name">Grande</div>
                            <div class="size-price">$20</div>
                        </div>
                    </div>
                </div>

                <div class="quantity-section">
                    <h3>Cantidad:</h3>
                    <div class="quantity-controls">
                        <button class="quantity-btn" onclick="changeQuantity('sticker', -1)">−</button>
                        <span class="quantity-display" id="sticker-quantity">1</span>
                        <button class="quantity-btn" onclick="changeQuantity('sticker', 1)">+</button>
                    </div>
                </div>

                <div class="total-price" id="sticker-total">Selecciona un tamaño</div>
                <button class="add-to-cart" onclick="addToCart('sticker')" id="sticker-add-btn" disabled>Agregar al Carrito</button>
            </div>
        </div>

        <!-- Carrito de Compras -->
        <div class="cart-section">
            <h2 class="cart-title">🛒 Carrito de Compras</h2>
            <div class="cart-items" id="cart-items">
                <div class="empty-cart">Tu carrito está vacío</div>
            </div>
            <div class="cart-total" id="cart-total" style="display: none;">Total: $0</div>
            <button class="checkout-btn" onclick="checkout()" id="checkout-btn" style="display: none;">Proceder al Pago</button>
        </div>
    </div>

    <div class="notification" id="notification"></div>

    <script>
        let cart = [];
        let productSelections = {
            pin: { size: null, price: 0, quantity: 1 },
            sticker: { size: null, price: 0, quantity: 1 }
        };

        function selectSize(product, size, price) {
            const productCard = event.target.closest('.product-card');
            const sizeOptions = productCard.querySelectorAll('.size-option');
            sizeOptions.forEach(el => el.classList.remove('selected'));
            
            event.target.closest('.size-option').classList.add('selected');
            
            productSelections[product].size = size;
            productSelections[product].price = price;
            
            updateProductTotal(product);
            enableAddButton(product);
        }

        function changeQuantity(product, delta) {
            const currentQuantity = productSelections[product].quantity;
            const newQuantity = Math.max(1, currentQuantity + delta);
            productSelections[product].quantity = newQuantity;
            
            document.getElementById(`${product}-quantity`).textContent = newQuantity;
            updateProductTotal(product);
        }

        function updateProductTotal(product) {
            const { price, quantity } = productSelections[product];
            if (price > 0) {
                const total = price * quantity;
                document.getElementById(`${product}-total`).textContent = `Total: $${total}`;
            }
        }

        function enableAddButton(product) {
            const button = document.getElementById(`${product}-add-btn`);
            button.disabled = false;
            button.style.opacity = '1';
        }

        function showNotification(message) {
            const notification = document.getElementById('notification');
            notification.textContent = message;
            notification.classList.add('show');
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }

        function addToCart(product) {
            const selection = productSelections[product];
            if (!selection.size) return;

            const item = {
                id: Date.now(),
                type: product === 'pin' ? 'Pin Premium' : 'Sticker Premium',
                size: selection.size.charAt(0).toUpperCase() + selection.size.slice(1),
                quantity: selection.quantity,
                unitPrice: selection.price,
                totalPrice: selection.price * selection.quantity
            };

            cart.push(item);
            updateCartDisplay();
            
            showNotification(`¡${item.type} agregado al carrito!`);
        }

        function updateCartDisplay() {
            const cartItems = document.getElementById('cart-items');
            const cartTotal = document.getElementById('cart-total');
            const checkoutBtn = document.getElementById('checkout-btn');

            if (cart.length === 0) {
                cartItems.innerHTML = '<div class="empty-cart">Tu carrito está vacío</div>';
                cartTotal.style.display = 'none';
                checkoutBtn.style.display = 'none';
                return;
            }

            let totalAmount = 0;
            let cartHTML = '';

            cart.forEach(item => {
                totalAmount += item.totalPrice;
                cartHTML += `
                    <div class="cart-item">
                        <div>
                            <strong>${item.type}</strong> - ${item.size}<br>
                            <span style="color: #666;">Cantidad: ${item.quantity} × $${item.unitPrice}</span>
                        </div>
                        <div style="text-align: right;">
                            <div style="font-size: 1.2em; font-weight: bold; margin-bottom: 8px;">$${item.totalPrice}</div>
                            <button class="remove-btn" onclick="removeFromCart(${item.id})">Eliminar</button>
                        </div>
                    </div>
                `;
            });

            cartItems.innerHTML = cartHTML;
            cartTotal.textContent = `Total: $${totalAmount}`;
            cartTotal.style.display = 'block';
            checkoutBtn.style.display = 'block';
        }

        function removeFromCart(itemId) {
            cart = cart.filter(item => item.id !== itemId);
            updateCartDisplay();
            showNotification('Producto eliminado del carrito');
        }

        function checkout() {
            if (cart.length === 0) return;

            const total = cart.reduce((sum, item) => sum + item.totalPrice, 0);
            let orderSummary = "🎉 RESUMEN DE TU PEDIDO 🎉\n\n";
            
            cart.forEach(item => {
                orderSummary += `• ${item.type} (${item.size})\n  Cantidad: ${item.quantity} - $${item.totalPrice}\n\n`;
            });
            
            orderSummary += `💰 TOTAL: $${total}\n\n¡Gracias por elegir PinStyle!\nTu pedido será procesado pronto. 🚀`;
            
            alert(orderSummary);
            
            cart = [];
            updateCartDisplay();
            showNotification('¡Pedido realizado con éxito!');
        }

        // Inicialización
        document.addEventListener('DOMContentLoaded', function() {
            updateCartDisplay();
        });
    </script>
</body>
</html>
