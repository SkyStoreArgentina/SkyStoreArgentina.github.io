<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Sky Store Argentina</title>

  <style>
     @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap');

    * {
      box-sizing: border-box;
    }

    @keyframes gradientAnimation {
      0% {
        background-position: 0% 50%;
      }
      50% {
        background-position: 100% 50%;
      }
      100% {
        background-position: 0% 50%;
      }
    }

    body {
      margin: 0;
      padding: 40px 20px;
      font-family: Arial, sans-serif;
      color: #333;

      /* Fondo animado */
      background: linear-gradient(-45deg, #ff6b6b, #f7d794, #6a89cc, #82ccdd);
      background-size: 400% 400%;
      animation: gradientAnimation 20s ease infinite;
    }

    h1 {
      font-family: 'Poppins', Arial, sans-serif;
      font-size: 3rem;
      font-weight: 700;
      text-align: center;
      margin-bottom: 20px;
      background: linear-gradient(90deg, #2563eb, #6a89cc, #82ccdd);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      filter: drop-shadow(2px 2px 4px rgba(0, 0, 0, 0.3));
      letter-spacing: 2px;
      user-select: none;
    }
    p.lead {
      text-align: center;
      font-size: 1.2rem;
      color: #666;
      max-width: 600px;
      margin: 0 auto 40px;
    }
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
      gap: 20px;
      max-width: 1200px;
      margin: 0 auto;
    }
    .card {
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
      overflow: hidden;
      cursor: pointer;
      transition: all 0.3s ease;
      position: relative;
      height: auto;
      min-height: 400px;
    }
    .card.expanded {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 90%;
      max-width: 800px;
      max-height: 90vh;
      z-index: 1000;
      box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
      overflow-y: auto;
    }
    .card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
      display: block;
      transition: height 0.3s ease;
    }
    .card.expanded img {
      height: 250px;
    }
    .card-content {
      padding: 20px;
      position: relative;
    }
    .card-content h3 {
      margin: 0 0 12px;
      font-size: 1.5rem;
      color: #111;
    }
    .short-description {
      color: #666;
      font-size: 1rem;
      line-height: 1.5;
      margin-bottom: 16px;
    }
    .full-description {
      display: none;
      color: #444;
      font-size: 1rem;
      line-height: 1.6;
      margin-top: 16px;
      padding-top: 16px;
      border-top: 1px solid #eee;
    }
    .card.expanded .short-description {
      display: none;
    }
    .card.expanded .full-description {
      display: block;
    }
    .price {
      font-size: 1.75rem;
      font-weight: bold;
      color: #2563eb;
      margin-top: 16px;
      text-align: center;
    }
    .close-btn {
      position: absolute;
      top: 15px;
      right: 15px;
      background: rgba(0, 0, 0, 0.7);
      color: white;
      border: none;
      border-radius: 50%;
      width: 30px;
      height: 30px;
      font-size: 18px;
      cursor: pointer;
      display: none;
      align-items: center;
      justify-content: center;
      z-index: 10;
    }
    .card.expanded .close-btn {
      display: flex;
    }
    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.7);
      z-index: 999;
      display: none;
    }
    .overlay.active {
      display: block;
    }
    footer {
      margin-top: 60px;
      text-align: center;
      color: #f0f4ff;
      font-size: 1.1rem;
      font-family: 'Poppins', Arial, sans-serif;
      background: rgba(37, 99, 235, 0.8);
      padding: 20px 15px;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(37, 99, 235, 0.4);
      user-select: none;
    }
    @media (max-width: 768px) {
      .card.expanded {
        width: 95%;
        max-height: 85vh;
      }
      .card img {
        height: 150px;
      }
      .card.expanded img {
        height: 180px;
      }
    }
  </style>
</head>
<body>
  <div class="overlay"></div>
  
  <h1>Sky Store</h1>
  <p class="lead">Donde la tecnología se vuelve tuya.</p>

  <div class="grid">
    <!-- Producto 1 -->
    <article class="card" onclick="expandCard(this)">
      <img src="https://i.blogs.es/68165f/redmi-14c/1366_521.jpeg" alt="Redmi 14C" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>XIAOMI Redmi 14C 128GB</h3>
        <div class="short-description">
          Redmi 14C 128GB 4GB RAM
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Pantalla: 6,88" HD+ (120 Hz)<br>
          • Procesador: MediaTek Helio G81-Ultra<br>
          • Memoria: 4 GB RAM + 128 GB (expandible)<br>
          • Cámaras: 50 MP trasera + 13 MP frontal<br>
          • Batería: 5160 mAh con carga rápida 18 W<br>
          • Extras: Android 14 (HyperOS), huella lateral, USB-C, jack 3.5 mm, radio FM<br>
          • Incuye cargador, cable, funda y llave SIM<br>
          • Dual SIM
        </div>
        <div class="price">$280.000</div>
      </div>
    </article>

    <!-- Producto 2 -->
    <article class="card" onclick="expandCard(this)">
      <img src="https://i02.appmifile.com/mi-com-product/fly-birds/poco-c71/pc/9edd6895a29749d902bf52fa20b2b533.jpg?f=webp" alt="POCO C71" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>POCO C71 128GB</h3>
        <div class="short-description">
          POCO C71 128GB 4GB RAM
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Pantalla: 6.53" IPS LCD, 720 x 1600 píxeles<br>
          • Procesador: Unisoc T612<br>
          • Memoria: 4 GB RAM + 128 GB almacenamiento interno<br>
          • Cámara trasera: 13 MP<br>
          • Cámara frontal: 5 MP<br>
          • Batería: 5000 mAh con carga rápida 10W<br>
          • Sistema operativo: Android 13, MIUI Go Edition<br>
          • Extras: Lector de huellas lateral, desbloqueo facial, Dual SIM<br>
          • Conectividad: 4G LTE, Wi-Fi, Bluetooth 5.0, GPS<br>
          • Puerto USB-C y jack 3.5 mm
        </div>
        <div class="price">$260.000</div>
      </div>
    </article>

    <!-- Producto 3 -->
    <article class="card" onclick="expandCard(this)">
      <img src="https://puntonetinsuperablesas.com/wp-content/uploads/2025/04/imagen_2025-04-25_110430118.png" alt="Tecno Spark 30C 128GB" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>Tecno Spark 30C 128GB</h3>
        <div class="short-description">
          Smartphone Tecno Spark 30C 128GB 4GB RAM
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Pantalla: 6.52" IPS LCD, 720 x 1600 píxeles<br>
          • Procesador: MediaTek Helio G85<br>
          • Memoria: 4 GB RAM + 128 GB almacenamiento interno<br>
          • Cámara trasera: Dual 16 MP + QVGA<br>
          • Cámara frontal: 8 MP<br>
          • Batería: 5000 mAh con carga rápida 18W<br>
          • Sistema operativo: Android 12, HiOS 8.6<br>
          • Extras: Lector de huellas lateral, desbloqueo facial<br>
          • Conectividad: 4G LTE, Wi-Fi, Bluetooth 5.0, GPS<br>
          • Puerto USB-C y jack 3.5 mm
        </div>
        <div class="price">$240.000</div>
      </div>
    </article>

    <!-- Producto 4 -->
    <article class="card" onclick="expandCard(this)">
      <img src="https://mexx-img-2019.s3.amazonaws.com/pendrive-kingston-exodia-64gb_42049_2.jpeg" alt="Pendrive Kingston 64GB" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>Pendrive Kingston 64GB</h3>
        <div class="short-description">
          Memoria USB Kingston 64GB
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Capacidad: 64GB<br>
          • Velocidad de transferencia: USB 3.0 hasta 100 MB/s<br>
          • Compatible con USB 2.0<br>
          • Diseño compacto y resistente<br>
          • Plug and Play, sin necesidad de drivers<br>
          • Compatible con Windows, macOS y Linux<br>
          • Ideal para almacenamiento y transferencia de archivos<br>
          • Protección contra golpes y vibraciones<br>
          • Garantía limitada de 5 años Kingston
        </div>
        <div class="price">$15.000</div>
      </div>
    </article>

    <!-- Producto 5 -->
     <article class="card" onclick="expandCard(this)">
      <img src="https://http2.mlstatic.com/D_NQ_NP_784923-MLA91974990406_092025-O.webp" alt="Colchón inflable doble plaza" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>Colchón Inflable Doble Plaza</h3>
        <div class="short-description">
          Colchón inflable doble plaza con inflado automático
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Tamaño: Doble plaza (aprox. 203 x 152 x 46 cm)<br>
          • Inflado automático en menos de 3 minutos<br>
          • Material resistente y duradero, impermeable<br>
          • Superficie suave y cómoda para dormir<br>
          • Válvula de desinflado rápido<br>
          • Fácil de transportar y almacenar<br>
          • Ideal para camping, visitas o uso en el hogar<br>
          • Incluye bomba eléctrica integrada<br>
          • Soporta hasta 300 kg de peso
        </div>
        <div class="price">$180.000</div>
      </div>
    </article>

    <!-- Producto 6 -->
<article class="card" onclick="expandCard(this)">
      <img src="https://trendblog.euronics.de/wp-content/uploads/2024/11/s24-fe-packung-1280x720.jpg" alt="Samsung S24 FE 8GB RAM 256GB" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>Samsung S24 FE 8GB RAM 256GB</h3>
        <div class="short-description">
          Smartphone Samsung Galaxy S24 FE 8GB RAM 256GB
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Pantalla: 6.4" Dynamic AMOLED 2X, 2340 x 1080 píxeles, 120Hz<br>
          • Procesador: Exynos 2200 / Snapdragon 8 Gen 1 (según región)<br>
          • Memoria: 8 GB RAM + 256 GB almacenamiento interno<br>
          • Cámara trasera: Triple 50 MP (principal) + 12 MP (ultra gran angular) + 8 MP (telefoto)<br>
          • Cámara frontal: 32 MP<br>
          • Batería: 4500 mAh con carga rápida 25W<br>
          • Sistema operativo: Android 13, One UI 5<br>
          • Extras: Resistencia IP68, lector de huellas en pantalla, carga inalámbrica<br>
          • Conectividad: 5G, Wi-Fi 6, Bluetooth 5.2, NFC<br>
          • Puerto USB-C
        </div>
        <div class="price">$1.700.000</div>
      </div>
    </article>

    <article class="card" onclick="expandCard(this)">
      <img src="https://okeyrosario.com.ar/wp-content/uploads/2020/04/soportemovil2.jpg" alt="HTV-73003 Soporte de TV 14-55" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>HTV-73003 Soporte de TV 14-55"</h3>
        <div class="short-description">
          Soporte para TV de 14 a 55 pulgadas modelo TV50 MO-03
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Compatible con televisores de 14" a 55"<br>
          • Modelo: TV50 MO-03<br>
          • Capacidad de carga: hasta 35 kg<br>
          • Material resistente de acero con acabado negro<br>
          • Instalación sencilla con kit de montaje incluido<br>
          • Soporte fijo para montaje en pared<br>
          • Compatible con estándares VESA 75x75, 100x100, 200x100, 200x200, 400x200, 400x400<br>
          • Diseño compacto y elegante<br>
          • Ideal para uso en hogares y oficinas
        </div>
        <div class="price">$21.000</div>
      </div>
    </article>


        <article class="card" onclick="expandCard(this)">
      <img src="https://http2.mlstatic.com/D_NQ_NP_635262-MLA81625814866_012025-O.webp" alt="Auricular Vincha Bluetooth Luz RGB" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>Auricular Vincha Bluetooth Luz RGB</h3>
        <div class="short-description">
          Auricular vincha inalámbrico con luces RGB y sonido envolvente
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Conectividad Bluetooth 5.0 para conexión estable y rápida<br>
          • Iluminación LED RGB personalizable<br>
          • Sonido estéreo de alta calidad con graves profundos<br>
          • Micrófono incorporado para llamadas y chat en juegos<br>
          • Diseño cómodo y ajustable para uso prolongado<br>
          • Batería recargable con hasta 12 horas de reproducción<br>
          • Controles táctiles para volumen, reproducción y llamadas<br>
          • Compatible con PC, consolas, smartphones y tablets<br>
          • Incluye cable de carga USB-C y cable auxiliar de 3.5 mm
        </div>
        <div class="price">$18.000</div>
      </div>
    </article>


<article class="card" onclick="expandCard(this)">
      <img src="https://solomayorista.ar/fotos/BL-91057.jpg" alt="Auricular Vincha Bluetooth Luz RGB" />
      <button class="close-btn" onclick="closeCard(event, this)">×</button>
      <div class="card-content">
        <h3>BALANZA DIGITAL DE BAÑO PERSONAL</h3>
        <div class="short-description">
          BALANZA DIGITAL DE BAÑO PERSONAL
        </div>
        <div class="full-description">
          <strong>Características principales:</strong><br>
          • Capacidad máxima de peso: 150-180 kg o más.<br>
          • Plataforma de vidrio templado (6‐8 mm) o vidrio + materiales resistentes al uso.<br>
          • Pantalla digital tipo LCD o LED, con dígitos grandes para fácil lectura.<br>
          • Apagado automático, para ahorrar batería.<br>
          • Indicador de batería baja y/o de sobrecarga del peso.<br>
          • Unidades de medida (kg / lb) intercambiables en algunos modelos.<br>
          • Diseño antideslizante / resistencia al vapor/mayor durabilidad en ambientes húmedos.<br>

        </div>
        <div class="price">$24.000</div>
      </div>
    </article>




  </div>

  <footer>
    <p>Para más información sobre nuestros productos, contáctenos.</p>
    <p>whatsapp: 11 6402-2879</p>
  </footer>

  <script>
    let expandedCard = null;

    function expandCard(card) {
      if (expandedCard) {
        closeCard(null, expandedCard.querySelector('.close-btn'));
      }
      
      expandedCard = card;
      card.classList.add('expanded');
      document.querySelector('.overlay').classList.add('active');
      document.body.style.overflow = 'hidden';
    }

    function closeCard(event, button) {
      if (event) {
        event.stopPropagation();
      }
      
      const card = button.closest('.card');
      card.classList.remove('expanded');
      document.querySelector('.overlay').classList.remove('active');
      document.body.style.overflow = 'auto';
      expandedCard = null;
    }

    // Cerrar al hacer clic fuera de la tarjeta expandida
    document.querySelector('.overlay').addEventListener('click', function() {
      if (expandedCard) {
        closeCard(null, expandedCard.querySelector('.close-btn'));
      }
    });

    // Cerrar con la tecla ESC
    document.addEventListener('keydown', function(e) {
      if (e.key === 'Escape' && expandedCard) {
        closeCard(null, expandedCard.querySelector('.close-btn'));
      }
    });
  </script>
</body>
</html>
