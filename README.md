# RegisterService
Formulario para registrar servicios de terceros en linea.
Proyecto: Formulario de Datos con Firebase
Este proyecto es una aplicación web simple que permite a los usuarios guardar, consultar y modificar datos en una base de datos de Firebase usando un formulario. Las funciones principales del programa se activan mediante tres botones:

Guardar: Guarda los datos ingresados en Firebase.
Consultar: Busca los datos en Firebase utilizando el número de cotización.
Modificar: Actualiza los datos en Firebase según el número de cotización ingresado.
Características
Guardar datos: Los usuarios pueden guardar su nombre, correo electrónico y un número de cotización único en Firebase.
Consulta de datos: Los usuarios pueden consultar datos ingresando el número de cotización y obteniendo la información asociada.
Modificación de datos: Los usuarios pueden modificar el nombre y correo electrónico asociados a un número de cotización.
Pre-requisitos
Para ejecutar este proyecto, necesitas tener configurado un proyecto en Firebase y habilitar Firestore como base de datos.

Configuración de Firebase
Crea un proyecto de Firebase: Dirígete a la consola de Firebase y crea un nuevo proyecto.
Habilita Firestore: En la consola de Firebase, navega hasta Firestore Database y haz clic en “Crear base de datos”.
Agrega la configuración a tu proyecto: Copia el objeto de configuración de Firebase y pégalo en el archivo script.js en la sección firebaseConfig.

Javascript
const firebaseConfig = {
    apiKey: "TU_API_KEY",
    authDomain: "TU_DOMINIO.firebaseapp.com",
    projectId: "TU_ID_PROYECTO",
    storageBucket: "TU_BUCKET.appspot.com",
    messagingSenderId: "ID_MENSAJES",
    appId: "TU_APP_ID"
};

Estructura del Proyecto
El proyecto consta de tres archivos principales:

index.html: Contiene el formulario y los tres botones para guardar, consultar y modificar los datos.
script.js: Contiene el código JavaScript para interactuar con Firebase.
styles.css: (Opcional) Contiene los estilos para la interfaz del formulario.
Uso del Proyecto
Guardar datos:

Rellena los campos de "Número de Cotización", "Nombre" y "Correo Electrónico".
Haz clic en el botón Guardar para almacenar los datos en Firebase.
Consultar datos:

Ingresa el "Número de Cotización" y haz clic en Consultar.
Si el número de cotización existe, el formulario se completará con el nombre y correo electrónico correspondientes.
Modificar datos:

Ingresa el "Número de Cotización", el "Nombre" y el "Correo Electrónico" a actualizar.
Haz clic en Modificar para guardar los cambios.
Código de Ejemplo
Aquí un fragmento de código del archivo script.js:

Javascript
// Función para guardar datos
async function saveData() {
    const quotationNumber = document.getElementById("quotationNumber").value;
    const name = document.getElementById("name").value;
    const email = document.getElementById("email").value;

    try {
        await db.collection("users").add({
            quotationNumber: quotationNumber,
            name: name,
            email: email,
            timestamp: firebase.firestore.FieldValue.serverTimestamp()
        });
        alert("Datos guardados exitosamente");
    } catch (error) {
        console.error("Error al guardar los datos:", error);
    }
} 

Notas
Configuración de seguridad: Si estás en desarrollo, configura las reglas de Firestore para permitir lecturas y escrituras sin restricciones. Asegúrate de ajustar estas configuraciones para producción.
Depuración: Usa la consola del navegador para ver errores o mensajes de confirmación de cada operación.
Contacto
Para preguntas o sugerencias, puedes comunicarte con el equipo de desarrollo.
