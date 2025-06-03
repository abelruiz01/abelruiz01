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
