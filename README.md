//almacenar a los amigos
let amigos = [];

// Función para agregar un amigo
function agregarAmigo() {
    const input = document.getElementById("amigo");
    const nombre = input.value.trim();

    // Validar que no esté vacío
    if (nombre === "") {
        alert("Por favor, inserte un nombre.");
        return;
    }

    // Agregar al array
    amigos.push(nombre);

    // Limpiar el campo
    input.value = "";

    // Mostrar la lista actualizada
    mostrarAmigos();
}

// Función para mostrar todos los amigos en la lista HTML
function mostrarAmigos() {
    const lista = document.getElementById("listaAmigos");
    lista.innerHTML = ""; // limpiar lista

    for (let i = 0; i < amigos.length; i++) {
        const li = document.createElement("li");
        li.textContent = amigos[i];
        lista.appendChild(li);
    }
}

// Función para sortear un amigo aleatorio
function sortearAmigo() {
    const resultado = document.getElementById("resultado");

    // Validar que haya amigos
    if (amigos.length === 0) {
        alert("No hay amigos para sortear. Agregue al menos uno.");
        return;
    }

    // Limpiar resultados previos
    resultado.innerHTML = "";

    // Generar índice aleatorio
    const indiceAleatorio = Math.floor(Math.random() * amigos.length);

    // Obtener el nombre sorteado
    const amigoSorteado = amigos[indiceAleatorio];

    // Mostrar el resultado como <li>
    const li = document.createElement("li");
    li.textContent = `Amigo secreto: ${amigoSorteado}`;
    resultado.appendChild(li);
}
