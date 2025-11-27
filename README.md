# Laboratorio-de-aplicaciones-web-cliente-Proyecto-web-E-commerce
Proyecto web: E-commerce
📄 README – Proyecto Ecommerce
🛒 Trabajo Práctico – Aplicación Ecommerce

Aplicación web desarrollada con HTML5, CSS3 / Bootstrap 5, JavaScript, consumiendo la API FakeStore API, cumpliendo criterios de responsividad, accesibilidad y UX/UI.

👥 Participantes y Desarrollo
👤 Nicolás Pauwels

GitHub: agregar usuario

✨ Aportes principales

Implementación de la estructura HTML5 semántica (header, nav, main, section, footer).

Desarrollo del listado de productos y renderizado dinámico en cards.

Creación del modal de descripción del producto.

Integración de SweetAlert2 para alertas.

Lógica de agregar al carrito y sincronización con LocalStorage.

🧩 Fragmento de código desarrollado por Nicolás
// Render de productos
function renderProducts(products) {
    const container = document.getElementById("product-list");
    container.innerHTML = "";

    products.forEach(product => {
        const card = document.createElement("div");
        card.classList.add("col-md-4", "mb-3");

        card.innerHTML = `
            <div class="card h-100">
                <img src="${product.image}" class="card-img-top p-3" alt="${product.title}">
                <div class="card-body">
                    <h5 class="card-title">${product.title}</h5>
                    <p class="card-text fw-bold">$${product.price}</p>
                    <button class="btn btn-primary w-100" onclick="openModal(${product.id})">Ver detalle</button>
                </div>
            </div>
        `;
        container.appendChild(card);
    });
}

👤 Gastón [apellido]

GitHub: agregar usuario

✨ Aportes principales

Desarrollo del sidebar del carrito (offcanvas).

Funciones para sumar/restar cantidad, actualizar precios y eliminar productos.

Función vaciar carrito y finalizar compra, con persistencia en LocalStorage.

Implementación del buscador para filtrar productos.

Estilos y responsividad general utilizando Bootstrap 5.

🧩 Fragmento de código desarrollado por Gastón
// Actualizar cantidad dentro del carrito
function updateQuantity(id, action) {
    let cart = JSON.parse(localStorage.getItem("cart")) || [];
    let product = cart.find(item => item.id === id);

    if (action === "sumar") {
        product.quantity++;
    } else if (action === "restar" && product.quantity > 1) {
        product.quantity--;
    }

    localStorage.setItem("cart", JSON.stringify(cart));
    renderCart();
}

// Eliminar producto
function removeItem(id) {
    let cart = JSON.parse(localStorage.getItem("cart")) || [];
    cart = cart.filter(item => item.id !== id);
    localStorage.setItem("cart", JSON.stringify(cart));
    renderCart();
}

// Finalizar compra
function finalizePurchase() {
    localStorage.removeItem("cart");
    renderCart();
    Swal.fire("¡Gracias por su compra!", "El carrito ha sido vaciado.", "success");
}

📌 Funcionalidades desarrolladas

✔️ Listado de productos desde FakeStore API

✔️ Modal con detalles del producto

✔️ Carrito con LocalStorage

✔️ Sidebar con productos seleccionados

✔️ Sumar/restar cantidades, eliminar productos

✔️ Vaciar carrito y finalizar compra

✔️ Buscador de productos

✔️ Diseño responsive

✔️ Accesibilidad aplicada con etiquetas semánticas

✔️ Buenas prácticas UX/UI

▶️ Cómo ejecutar el proyecto

Descargar los archivos del TP.

Abrir ecommerce.html en un navegador.

¡Listo!

📚 Créditos

Proyecto desarrollado por Nicolás y Gaston como Trabajo Práctico académico.
