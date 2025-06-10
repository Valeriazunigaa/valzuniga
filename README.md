
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>COBACH 20 - Alimentación Sustentable</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 20px;
      line-height: 1.6;
      background: #ffe6f0; /* rosa claro */
      color: #b30059; /* rosa fuerte */
    }
    h1, h2, h3 {
      color: #b30059;
    }
    ul {
      margin-left: 20px;
    }
    button.paw-button {
      background-color: #e60073; /* rosa fuerte */
      color: white;
      border: none;
      padding: 10px 18px;
      margin-right: 10px;
      margin-bottom: 15px;
      cursor: pointer;
      border-radius: 5px;
      font-weight: bold;
      transition: background-color 0.3s ease;
    }
    button.paw-button:hover {
      background-color: #99004d;
    }
    .hidden {
      display: none;
    }
    #infoDisplay {
      margin-top: 20px;
      padding: 15px;
      border: 2px solid #e60073;
      background: #ffe6f0;
      border-radius: 8px;
      min-height: 150px;
    }
    section.content-section {
      margin-bottom: 30px;
      background: white;
      padding: 15px 20px;
      border-radius: 8px;
      box-shadow: 0 0 8px #f7c2da;
    }
    form {
      background: white;
      padding: 20px;
      border-radius: 8px;
      box-shadow: 0 0 8px #f7c2da;
      max-width: 500px;
    }
    label {
      margin-top: 15px;
      display: block;
      font-weight: bold;
      color: #b30059;
    }
    input, textarea {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      border: 1px solid #f7c2da;
      border-radius: 5px;
      resize: vertical;
      font-family: inherit;
    }
    button[type="submit"] {
      background-color: #b30059;
      color: white;
      border: none;
      padding: 12px 20px;
      margin-top: 20px;
      cursor: pointer;
      font-weight: bold;
      border-radius: 5px;
      transition: background-color 0.3s ease;
    }
    button[type="submit"]:hover {
      background-color: #80003b;
    }
    footer {
      margin-top: 40px;
      text-align: center;
      color: #80003b;
      font-size: 0.9em;
    }
    /* Contenedor de imágenes */
    .image-gallery {
      display: flex;
      flex-wrap: wrap;
      gap: 15px;
      justify-content: center;
      margin: 30px 0;
    }
    .image-gallery img {
      width: 150px;
      height: 150px;
      object-fit: cover;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(179, 0, 89, 0.3);
      transition: transform 0.3s ease;
      cursor: pointer;
    }
    .image-gallery img:hover {
      transform: scale(1.05);
    }
    /* Audio player */
    #himno-container {
      margin: 20px 0;
      text-align: center;
 
  <script>
    // Obtener los botones y el contenedor para mostrar info
    const pawButtons = document.querySelectorAll('.paw-button');
    const infoDisplay = document.getElementById('infoDisplay');
    const feedbackForm = document.getElementById('feedbackForm');

    // Contenido para cada sección
    const buttonContent = {
      recetas: `
        <h3>Recetas Saludables para Alumnos</h3>
        <ul>
          <li><strong>Ensalada de frutas:</strong> mezcla manzana, plátano, naranja y fresas con un poco de jugo de limón.</li>
          <li><strong>Barras de avena caseras:</strong> avena, miel, frutos secos y pasas horneadas ligeramente.</li>
          <li><strong>Sándwich integral:</strong> pan integral con pollo, lechuga, jitomate y aguacate.</li>
          <li><strong>Palomitas naturales:</strong> hechas en casa sin mantequilla ni sal extra.</li>
          <li><strong>Yogur con frutas:</strong> yogur natural con trozos de fruta fresca.</li>
        </ul>
      `,
      impacto: `
        <h3>Importancia e Impacto de una Alimentación Saludable</h3>
        <p>Cambiar nuestra alimentación tiene efectos positivos en nuestro desarrollo físico y mental:</p>
        <ul>
          <li>Mejora la concentración y el rendimiento académico.</li>
          <li>Fortalece el sistema inmunológico, ayudándonos a evitar enfermedades.</li>
          <li>Contribuye al crecimiento saludable y adecuado.</li>
          <li>Reduce el riesgo de enfermedades crónicas a largo plazo.</li>
          <li>Promueve hábitos sostenibles y cuida el medio ambiente.</li>
        </ul>
      `,
      opciones: `
        <h3>Opciones de Cambio en el Plantel</h3>
        <ul>
          <li>Ofrecer frutas y snacks saludables en la cafetería.</li>
          <li>Instalar bebederos con agua potable para reducir el uso de botellas plásticas.</li>
          <li>Fomentar el uso de loncheras reutilizables y evitar empaques desechables.</li>
          <li>Organizar talleres y ferias sobre alimentación saludable.</li>
          <li>Incentivar el cultivo en huertos escolares para proveer alimentos frescos.</li>
        </ul>
      `
    };

    // Agregar evento a cada botón para mostrar la información correspondiente
    pawButtons.forEach(button => {
      button.addEventListener('click', () => {
        const key = button.dataset.info;
        if (buttonContent[key]) {
          infoDisplay.innerHTML = buttonContent[key];
          infoDisplay.scrollIntoView({ behavior: 'smooth', block: 'start' });
        } else {
          infoDisplay.innerHTML = '<p>No hay información disponible para esta sección.</p>';
        }
      });
    });

    // Manejo del envío del formulario (solo para demo)
    feedbackForm.addEventListener('submit', (event) => {
      event.preventDefault();

      const nombre = document.getElementById('nombre').value.trim();
      const email = document.getElementById('email').value.trim();
      const propuesta = document.getElementById('propuesta').value.trim();

      if (nombre && email && propuesta) {
        console.log('Formulario Enviado:');
        console.log('Nombre:', nombre);
        console.log('Email:', email);
        console.log('Propuesta/Comentario:', propuesta);

        alert('¡Gracias por tu propuesta/comentario! Lo hemos recibido.');
        feedbackForm.reset();
      } else {
        alert('Por favor llena todos los campos antes de enviar.');
      }
    });
  </script>
</body>
</html>
