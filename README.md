<!DOCTYPE html>
<html lang="en">
<head>

    <!-- Google tag (gtag.js) -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-SXZXLHB0V4"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-SXZXLHB0V4');
</script>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tienda Online</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f8f8f8;
            margin-bottom: 100px;
        }

        header {
            background-color: #333;
            color: #fff;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
        }

        .logo img {
            width: 200px;
            height: auto;
        }

        .navigation ul {
            list-style: none;
            padding: 0;
            margin: 0;
        }

        .navigation ul li {
            display: inline-block;
            margin-right: 20px;
        }

        .user-cart button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .user-cart button:hover {
            background-color: #45a049;
        }

        nav ul {
            list-style: none;
            padding: 0;
            text-align: center;
        }

        nav li {
            display: inline-block;
            margin-right: 20px;
        }

        nav li:last-child {
            margin-right: 0;
        }

        nav button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        nav button:hover {
            background-color: #45a049;
        }

        .productos-container {
            width: 80%;
            margin: 0 auto;
        }

        .productos-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }

        .producto {
            width: calc(33.33% - 10px);
            margin-right: 10px;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .productos-row .producto:nth-child(3n) {
            margin-right: 0;
        }

        .producto:last-child {
            margin-right: 0;
        }

        #producto {
            max-width: 800px;
            margin: 20px auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        #producto img {
            max-width: 100%;
            height: auto;
            border-radius: 5px;
            margin-bottom: 10px;
        }

        #producto h3 {
            color: #333;
        }

        #producto p {
            color: #666;
        }

        #producto button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        #producto button:hover {
            background-color: #45a049;
        }

        footer {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 20px;
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
        }

        .modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.4);
            padding-top: 60px;
        }

        .modal-content {
            background-color: #fefefe;
            margin: 5% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }

        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <header>
        <div class="logo">
            <img src="Downloads/electrotec.png" alt="Logo de la tienda">
        </div>
        <div class="left-buttons">
            <button onclick="mostrarProductosMasVendidos()">Inicio</button>
            <button onclick="verProductos()">Productos</button>
            <button onclick="abrirModal('contactoModal')">Contacto</button>
        </div>
        <div class="right-buttons">
            <button onclick="abrirModal('carritoModal')">Carrito</button>
            <button onclick="perfilUsuario()">Perfil de Usuario</button>
            <button onclick="mostrarLogin()">Iniciar Sesión</button>
        </div>
    </header>

    <!-- Formulario de inicio de sesión -->
    <div id="loginForm" style="display:none;">
        <h2>Iniciar Sesión</h2>
        <form>
            <input type="text" placeholder="Correo electrónico">
            <input type="password" placeholder="Contraseña">
            <button type="submit">Iniciar Sesión</button>
            <button onclick="regresarAlInicio()">Regresar al Inicio</button>
        </form>
        <p><a href="#">Crear nuevo usuario</a></p>
    </div>
    
    <div class="productos-container">
        <!-- Primera fila de productos -->
        <div class="productos-row">
            <!-- Primer producto -->
            <div class="producto">
                <!-- Contenido del primer producto -->
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion1')">Ver Descripción</button>
                <div id="descripcion1" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>

            <!-- Segundo producto -->
            <div class="producto">
                <!-- Contenido del segundo producto -->
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion2')">Ver Descripción</button>
                <div id="descripcion2" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>

            <!-- Tercer producto -->
            <div class="producto">
                <!-- Contenido del tercer producto -->
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion3')">Ver Descripción</button>
                <div id="descripcion3" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>
        </div>

        <!-- Segunda fila de productos -->
        <div class="productos-row">
            <!-- Cuarto producto -->
            <div class="producto">
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion4')">Ver Descripción</button>
                <div id="descripcion4" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>

            <!-- Quinto producto -->
            <div class="producto">
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion5')">Ver Descripción</button>
                <div id="descripcion5" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>

            <!-- Sexto producto -->
            <div class="producto">
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion6')">Ver Descripción</button>
                <div id="descripcion6" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>
        </div>

        <!-- Tercera fila de productos -->
        <div class="productos-row">
            <!-- Séptimo producto -->
            <div class="producto">
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion7')">Ver Descripción</button>
                <div id="descripcion7" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>

            <!-- Octavo producto -->
            <div class="producto">
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion8')">Ver Descripción</button>
                <div id="descripcion8" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>

            <!-- Noveno producto -->
            <div class="producto">
                <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
                <h3>KIT ARDUINO</h3>
                <button onclick="mostrarDescripcion('descripcion9')">Ver Descripción</button>
                <div id="descripcion9" style="display:none;">
                    <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                    <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
                </div>
            </div>
        </div>

    <!-- Aquí se agregarían más filas de productos según sea necesario -->
     <!-- Tercera fila de productos -->
     <div class="productos-row">
        <!-- Décimo producto -->
        <div class="producto">
            <img src="file:///C:/Users/aldo2/OneDrive/Im%C3%A1genes/KIT%20DE%20ARDUINO.jpg" alt="Producto 1" style="width: 200px; height: auto;">
            <h3>KIT ARDUINO</h3>
            <button onclick="mostrarDescripcion('descripcion10')">Ver Descripción</button>
            <div id="descripcion10" style="display:none;">
                <p>TZT-Kit de iniciación RFID para Arduino Uno R3, placa de pruebas y soporte, Motor paso a paso, Servo, 1602 LCD, cable de puente, Uno R3, el más nuevo</p>
                <button onclick="agregarAlCarrito()">Agregar al Carrito</button>
            </div>
        </div>
    </div>

    <footer>
        <p>&copy; 2024 Tienda Online. Todos los derechos reservados.</p>
    </footer>

    <!-- Ventana modal para carrito -->
    <div id="carritoModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="cerrarModal('carritoModal')">&times;</span>
            <h2>Carrito de Compras</h2>
            <p>No hay productos en el carrito.</p>
            <button onclick="pagar()">Pagar</button>
        </div>
    </div>

    <!-- Ventana modal para contacto -->
    <div id="contactoModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="cerrarModal('contactoModal')">&times;</span>
            <h2>Información de Contacto</h2>
            <p>Nombre de la Tienda: ELECTROTEC</p>
            <p>Correo Electrónico: info@ELECTROTEC.com</p>
            <p>Redes Sociales:</p>
            <ul>
                <li>Facebook: <a href="#">ELECTROTEC</a></li>
                <li>Twitter: <a href="#">@ELECTROTEC</a></li>
                <li>Instagram: <a href="#">@ELECTROTEC</a></li>
            </ul>
        </div>
    </div>

    <script>
        // Función para mostrar el formulario de inicio de sesión
        function mostrarLogin() {
    // Ocultar el contenido principal
    var contenidoPrincipal = document.querySelector('.productos-container');
    contenidoPrincipal.style.display = 'none';

    // Mostrar el formulario de inicio de sesión
    var loginForm = document.getElementById("loginForm");
    loginForm.style.display = "block";

    
    // Mostrar el formulario de inicio de sesión
    var loginForm = document.getElementById("loginForm");
    loginForm.style.display = "block";
}

        // Función para redireccionar a la página de productos
        function verProductos() {
            alert("Redireccionando a la página de Productos");
            // Aquí puedes agregar la lógica de redirección
        }

        // Función para redireccionar a la página de perfil de usuario
        function perfilUsuario() {
            alert("Redireccionando a la página de Perfil de Usuario");
            // Aquí puedes agregar la lógica de redirección
        }

        // Función para agregar un producto al carrito
        function agregarAlCarrito() {
            alert("Producto agregado al carrito");
            // Aquí puedes agregar la lógica de agregar al carrito
        }

        // Función para abrir un modal específico
        function abrirModal(idModal) {
            var modal = document.getElementById(idModal);
            modal.style.display = "block";
        }

        // Función para cerrar un modal específico
        function cerrarModal(idModal) {
            var modal = document.getElementById(idModal);
            modal.style.display = "none";
        }

        // Función para procesar el pago
        function pagar() {
            alert("¡Pago procesado con éxito!");
            // Aquí puedes agregar la lógica de procesamiento de pago
        }

        // Función para mostrar la descripción de un producto
        function mostrarDescripcion(idDescripcion) {
            var descripcion = document.getElementById(idDescripcion);
            if (descripcion.style.display === "none") {
                descripcion.style.display = "block";
            } else {
                descripcion.style.display = "none";
            }
        }

        // Función para cerrar el modal al hacer clic fuera de él
        window.onclick = function(event) {
            var modals = document.getElementsByClassName("modal");
            for (var i = 0; i < modals.length; i++) {
                var modal = modals[i];
                if (event.target == modal) {
                    modal.style.display = "none";
                }
            }
        }
        // Función para mostrar los cuatro productos más vendidos
function mostrarProductosMasVendidos() {
    // Ocultar todos los productos
    var productos = document.querySelectorAll('.producto');
    productos.forEach(function(producto) {
        producto.style.display = 'none';
    });
    // Mostrar solo los cuatro primeros productos
    for (var i = 0; i < 4; i++) {
        productos[i].style.display = 'block';
    }
}

// Función para mostrar todos los productos
function verProductos() {
    // Mostrar todos los productos
    var productos = document.querySelectorAll('.producto');
    productos.forEach(function(producto) {
        producto.style.display = 'block';
    });
}
// Función para regresar al inicio
function regresarAlInicio() {
    // Ocultar el formulario de inicio de sesión
    var loginForm = document.getElementById("loginForm");
    loginForm.style.display = "none";
    
    // Mostrar el contenido principal
    var contenidoPrincipal = document.querySelector('.productos-container');
    contenidoPrincipal.style.display = 'block';
}

    </script>
</body>
</html>
