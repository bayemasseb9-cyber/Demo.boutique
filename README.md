Enter<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Baye Shop Pro | Démo E-commerce</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com">
    <style>
        :root {
            --primary: #ff4757;
            --dark: #2f3542;
            --grey: #a4b0be;
            --light: #f1f2f6;
            --success: #2ed573;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; font-family: 'Poppins', sans-serif; }

        body { background-color: var(--light); color: var(--dark); }

        /* Barre de navigation */
        nav {
            background: white;
            padding: 15px 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 15px rgba(0,0,0,0.05);
        }
        nav h1 { color: var(--primary); font-weight: 800; font-size: 1.5rem; }
        .cart-icon { font-size: 1.2rem; position: relative; }
        .cart-count { 
            position: absolute; top: -10px; right: -10px; 
            background: var(--primary); color: white; 
            font-size: 0.7rem; padding: 2px 6px; border-radius: 50%; 
        }

        /* En-tête Boutique */
        .shop-header {
            text-align: center;
            padding: 60px 20px;
            background: white;
            margin-bottom: 40px;
        }
        .categories {
            margin-top: 20px;
            display: flex;
            justify-content: center;
            gap: 15px;
            flex-wrap: wrap;
        }
        .cat-btn {
            padding: 8px 20px;
            border-radius: 20px;
            border: 1px solid #ddd;
            cursor: pointer;
            transition: 0.3s;
            font-size: 0.9rem;
        }
        .cat-btn.active { background: var(--primary); color: white; border-color: var(--primary); }

        /* Grille de produits */
        .container { max-width: 1200px; margin: auto; padding: 0 20px 60px; }
        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        /* Carte Produit */
        .product-card {
            background: white;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.03);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
        }
        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 30px rgba(0,0,0,0.1);
        }

        .img-container { width: 100%; height: 300px; overflow: hidden; position: relative; }
        .product-img { 
            width: 100%; height: 100%; object-fit: cover; 
            transition: transform 0.5s ease;
        }
        .product-card:hover .product-img { transform: scale(1.1); }

        .badge-promo {
            position: absolute; top: 15px; left: 15px;
            background: var(--primary); color: white;
            padding: 5px 12px; border-radius: 8px; font-weight: bold; font-size: 0.8rem;
        }

        .product-info { padding: 25px; text-align: center; }
        .product-name { font-size: 1.1rem; font-weight: 600; margin-bottom: 8px; color: #2d3436; }
        
        .price-container { margin-bottom: 20px; }
        .old-price { text-decoration: line-through; color: var(--grey); font-size: 0.9rem; margin-right: 10px; }
        .current-price { color: var(--primary); font-size: 1.4rem; font-weight: 800; }

        .stock-status { 
            display: block; font-size: 0.75rem; color: var(--success); 
            margin-bottom: 15px; font-weight: 600;
        }

        /* Bouton WhatsApp Dynamique */
        .btn-wa {
            background: #25d366;
            color: white;
            text-decoration: none;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 15px;
            border-radius: 12px;
            font-weight: bold;
            transition: 0.3s;
        }
        .btn-wa:hover { background: #1eb954; filter: brightness(1.1); }

        /* Infos Livraison */
        .trust-info {
            display: flex; justify-content: center; gap: 30px; 
            margin-top: 50px; padding: 30px; border-top: 1px solid #eee;
            flex-wrap: wrap; text-align: center;
        }
        .trust-item { font-size: 0.85rem; color: #636e72; }
        .trust-item i { display: block; font-size: 1.5rem; margin-bottom: 10px; color: var(--dark); }

        @media (max-width: 600px) {
            .hero h1 { font-size: 1.8rem; }
        }
    </style>
</head>
<body>

<nav>
    <h1>BAYE<span>SHOP</span></h1>
    <div class="cart-icon">
        <i class="fas fa-shopping-bag"></i>
        <span class="cart-count">4</span>
    </div>
</nav>

<header class="shop-header">
    <h2>Nouvelle Collection 2026</h2>
    <p>Le meilleur de la mode livré chez vous au Sénégal</p>
    <div class="categories">
        <div class="cat-btn active">Tous</div>
        <div class="cat-btn">Chaussures</div>
        <div class="cat-btn">Accessoires</div>
        <div class="cat-btn">Vêtements</div>
    </div>
</header>

<div class="container">
    <div class="products-grid">
        
        <!-- Produit 1 : Chaussure -->
        <div class="product-card">
            <div class="badge-promo">-20%</div>
            <div class="img-container">
                <img src="image 0.jpg" class="product-img">
            </div>
            <div class="product-info">
                <h3 class="product-name">Nike Air Force One</h3>
                <span class="stock-status"><i class="fas fa-check"></i> En stock à Dakar</span>
                <div class="price-container">
                    <span class="old-price">55 000F</span>
                    <span class="current-price">44 000 FCFA</span>
                </div>
                <a href="https://wa.me" class="btn-wa">
                    <i class="fab fa-whatsapp"></i> Acheter sur WhatsApp
                </a>
            </div>
        </div>

        <!-- Produit 2 : Montre -->
        <div class="product-card">
            <div class="img-container">
                <img src="image 1.jpg" class="product-img">
            </div>
            <div class="product-info">
                <h3 class="product-name">Montre Minimaliste Silver</h3>
                <span class="stock-status"><i class="fas fa-check"></i> Expédié en 24h</span>
                <div class="price-container">
                    <span class="current-price">18 500 FCFA</span>
                </div>
                <a href="https://wa.me" class="btn-wa">
                    <i class="fab fa-whatsapp"></i> Acheter sur WhatsApp
                </a>
            </div>
        </div>

<!-- Produit 3 : Chaussure -->
        <div class="product-card">
            <div class="badge-promo">-10%</div>
            <div class="img-container">
                <img src="image 3.jpg" class="product-img">
            </div>
            <div class="product-info">
                <h3 class="product-name">
                <h3>Nike Air Max 270</h3>
                <span class="stock-status"><i class="fas fa-check"></i> En stock à Dakar</span>
                <div class="price-container">
                    <span class="old-price">44 000F</span>
                    <span class="current-price">40 000 FCFA</span>
                </div>
                <a href="https://wa.me" class="btn-wa">
                    <i class="fab fa-whatsapp"></i> Acheter sur WhatsApp
                </a>
            </div>
        </div>

        <!-- Produit 4 : Lunettes -->
        <div class="product-card">
            <div class="badge-promo">NEW</div>
            <div class="img-container">
                <img src="image 2.jpg" class="product-img">
            </div>
            <div class="product-info">
                <h3 class="product-name">Lunettes de Soleil Vintage</h3>
                <span class="stock-status"><i class="fas fa-check"></i> Qualité Premium</span>
                <div class="price-container">
                    <span class="current-price">12 000 FCFA</span>
                </div>
                <a href="https://wa.me" class="btn-wa">
                    <i class="fab fa-whatsapp"></i> Acheter sur WhatsApp
                </a>
            </div>
        </div>

    </div>

    <!-- Section Confiance -->
    <div class="trust-info">
        <div class="trust-item">
            <i class="fas fa-truck"></i>
            <strong>Livraison Rapide</strong>
            <p>Dakar & Banlieue</p>
        </div>
        <div class="trust-item">
            <i class="fas fa-undo"></i>
            <strong>Retour Facile</strong>
            <p>Sous 48 heures</p>
        </div>
        <div class="trust-item">
            <i class="fas fa-shield-alt"></i>
            <strong>Paiement Sûr</strong>
            <p>Wave / Orange Money / Cash</p>
        </div>
    </div>
</div>

<footer style="text-align: center; padding: 40px; background: white; color: #94a3b8; font-size: 0.8rem; border-top: 1px solid #eee;">
    <p>&copy; 2026 Baye Shop - Démo réalisée par Baye Masse Ba</p>
</footer>

</body>
</html>
