<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Servicios Técnicos</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f4f4;
      color: #333;
      overflow-x: hidden;
    }
    header {
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: white;
      background-color: rgba(0, 0, 0, 0.5);
      position: relative;
      overflow: hidden;
    }
    .background-slider {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }
    .background-image {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
      opacity: 0;
      transform: scale(1);
      animation: zoomFade 32s infinite;
    }
    .background-image:nth-child(1) {
      background-image: url('https://i.imgur.com/GH25rWS.jpg');
      animation-delay: 0s;
    }
    .background-image:nth-child(2) {
      background-image: url('https://i.imgur.com/9YxCT3x.jpg');
      animation-delay: 8s;
    }
    .background-image:nth-child(3) {
      background-image: url('https://i.imgur.com/9uY9T6a.jpg');
      animation-delay: 16s;
    }
    .background-image:nth-child(4) {
      background-image: url('https://images.unsplash.com/photo-1584820927498-c1712169c30e');
      animation-delay: 24s;
    }
    @keyframes zoomFade {
      0% { opacity: 0; transform: scale(1); }
      12.5% { opacity: 1; transform: scale(1.1); }
      37.5% { opacity: 1; transform: scale(1.1); }
      50% { opacity: 0; transform: scale(1.1); }
      100% { opacity: 0; transform: scale(1); }
    }
    .service-image-slider {
      width: 150px;
      height: 150px;
      position: relative;
      margin-right: 20px;
      border-radius: 10px;
      overflow: hidden;
    }
    .service-image {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;
      opacity: 0;
      transform: scale(1);
      animation: serviceZoomFade 12s infinite;
    }
    .service-image.static {
      animation: none;
      opacity: 1;
    }
    .service-image:nth-child(1) { animation-delay: 0s; }
    .service-image:nth-child(2) { animation-delay: 4s; }
    .service-image:nth-child(3) { animation-delay: 8s; }
    @keyframes serviceZoomFade {
      0% { opacity: 0; transform: scale(1); }
      12.5% { opacity: 1; transform: scale(1.1); }
      37.5% { opacity: 1; transform: scale(1.1); }
      50% { opacity: 0; transform: scale(1.1); }
      100% { opacity: 0; transform: scale(1); }
    }
    h1 {
      font-size: 48px;
      margin-bottom: 20px;
    }
    .header-subtitle {
      font-size: 24px;
      font-weight: bold;
      color: white;
      margin-bottom: 10px;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
    }
    .oval-button {
      padding: 20px 40px;
      font-size: 24px;
      cursor: pointer;
      background-color: white;
      color: #007bff;
      border: none;
      border-radius: 50px;
      transition: background-color 0.3s ease, color 0.3s ease;
      position: relative;
      z-index: 1;
    }
    .oval-button.loading {
      background-color: #28a745;
      color: white;
      cursor: not-allowed;
    }
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 40px 20px;
      background-color: white;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }
    h2 {
      color: #007bff;
      text-align: center;
      margin-bottom: 40px;
    }
    .service {
      display: flex;
      align-items: center;
      margin-bottom: 40px;
      padding: 20px;
      background-color: #f9f9f9;
      border-radius: 10px;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
    }
    .service img {
      width: 150px;
      height: 150px;
      object-fit: cover;
      border-radius: 10px;
      margin-right: 20px;
    }
    .service div {
      flex: 1;
    }
    .service h3 {
      margin-top: 0;
      color: #333;
    }
    .service p {
      margin: 10px 0;
    }
    select, input, textarea {
      padding: 8px;
      border-radius: 5px;
      border: 1px solid #ccc;
      margin: 10px 0;
      width: 100%;
      max-width: 300px;
    }
    .form-container {
      margin-top: 20px;
      padding: 20px;
      background-color: #f9f9f9;
      border-radius: 10px;
    }
    .form-container button {
      padding: 10px 20px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .form-container button:hover {
      background-color: #0056b3;
    }
  </style>
</head>
<body>
  <header id="inicio">
    <div class="background-slider">
      <div class="background-image"></div>
      <div class="background-image"></div>
      <div class="background-image"></div>
      <div class="background-image"></div>
    </div>
    <div class="header-subtitle">Servicio a Domicilio Express en Hermosillo</div>
    <h1>Agenda tu Servicio Técnico Aquí</h1>
    <a href="#formateo-service"><button class="oval-button" onclick="startLoading(this)">Agenda Ahora</button></a>
  </header>

  <section id="mis-servicios">
    <div class="container">
      <h2>Mis Servicios</h2>
      
      <div class="service" id="formateo-service">
        <div class="service-image-slider" id="formateo-slider">
          <img class="service-image" src="https://i.imgur.com/ZAo0SMG.jpg" alt="Windows 10">
          <img class="service-image" src="https://i.imgur.com/2FsoPCl.jpg" alt="Windows 11">
          <img class="service-image" src="https://i.imgur.com/wzH2Xc2.jpg" alt="Formateo">
        </div>
        <div>
          <h3>Formateo con Respaldo e Instalación de Windows</h3>
          <p id="formateo-text">Formateamos tu equipo, respaldamos tus datos y instalamos Windows 10 o 11 con beneficios personalizados.</p>
          <label>Elige la versión de Windows:</label>
          <select id="windows-version" onchange="updateFormateo()">
            <option value="">Selecciona...</option>
            <option value="10">Windows 10</option>
            <option value="11">Windows 11</option>
          </select>
        </div>
      </div>

      <div class="service">
        <div class="service-image-slider" id="programas-slider">
          <img class="service-image" src="https://i.imgur.com/V2yJuhP.jpg" alt="Microsoft Office">
          <img class="service-image" src="https://i.imgur.com/wHVVBGh.jpg" alt="Antivirus">
          <img class="service-image" src="https://i.imgur.com/V1nw66N.jpg" alt="Photoshop">
        </div>
        <div>
          <h3>Instalación de Programas Básicos</h3>
          <p id="programas-text">Instalamos Microsoft Office (2013-2024) con opciones de licencia genérica o permanente.</p>
          <label>Elige el programa:</label>
          <select id="programas-version" onchange="updateProgramas()">
            <option value="">Selecciona...</option>
            <option value="office">Microsoft Office</option>
            <option value="antivirus">Antivirus</option>
            <option value="photoshop">Photoshop</option>
          </select>
        </div>
      </div>

      <div class="service">
        <div class="service-image-slider" id="actualizacion-slider">
          <img class="service-image" src="https://i.imgur.com/v2UYRfB.jpg" alt="Mejora de RAM">
          <img class="service-image" src="https://i.imgur.com/lQtzOqI.jpg" alt="Cambio a SSD">
          <img class="service-image" src="https://i.imgur.com/2QKXLsC.jpg" alt="Actualización de Software">
          <img class="service-image" src="https://i.imgur.com/2QKXLsC.jpg" alt="Optimización">
        </div>
        <div>
          <h3>Actualización de Hardware y Software</h3>
          <p id="actualizacion-text">Optimizamos tu equipo con mejoras de hardware y actualizaciones de software.</p>
          <label>Elige el tipo de actualización:</label>
          <select id="actualizacion-type" onchange="updateActualizacion()">
            <option value="">Selecciona...</option>
            <option value="ram">Mejora de RAM</option>
            <option value="ssd">Cambio a SSD</option>
            <option value="software">Actualización de Software</option>
            <option value="optimizacion">Optimización</option>
          </select>
        </div>
      </div>

      <div class="form-container">
        <h3>Agendar Cita</h3>
        <form id="miFormulario">
          <label for="nombre">Nombre:</label>
          <input type="text" id="nombre" name="nombre" required><br>
          <label for="numero">Número:</label>
          <input type="tel" id="numero" name="numero" required><br>
          <label for="direccion">Dirección:</label>
          <textarea id="direccion" name="direccion" required></textarea><br>
          <label for="horario">Horario de preferencia:</label>
          <input type="text" id="horario" name="horario" required><br>
          <label for="servicio">Servicio:</label>
          <select id="servicio" name="servicio" required>
            <option value="">Selecciona...</option>
            <option value="Formateo con Respaldo e Instalación de Windows">Formateo con Respaldo e Instalación de Windows</option>
            <option value="Instalación de Programas Básicos">Instalación de Programas Básicos</option>
            <option value="Actualización de Hardware y Software">Actualización de Hardware y Software</option>
          </select><br>
          <label for="opcion">Opción:</label>
          <select id="opcion" name="opcion" required>
            <option value="">Selecciona...</option>
            <option value="Windows 10">Windows 10</option>
            <option value="Windows 11">Windows 11</option>
            <option value="Microsoft Office">Microsoft Office</option>
            <option value="Antivirus">Antivirus</option>
            <option value="Photoshop">Photoshop</option>
            <option value="Mejora de RAM">Mejora de RAM</option>
            <option value="Cambio a SSD">Cambio a SSD</option>
            <option value="Actualización de Software">Actualización de Software</option>
            <option value="Optimización">Optimización</option>
          </select><br>
          <button type="submit">Agendar</button>
        </form>
      </div>
    </div>
  </section>

  <script>
    function startLoading(button) {
      button.classList.add('loading');
      button.disabled = true;
      setTimeout(() => {
        button.classList.remove('loading');
        button.disabled = false;
        window.location.hash = '#formateo-service';
      }, 3000);
    }

    function updateFormateo() {
      const version = document.getElementById('windows-version').value;
      const slider = document.getElementById('formateo-slider');
      const text = document.getElementById('formateo-text');
      slider.innerHTML = '';
      let img;
      if (version === '10') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/ZAo0SMG.jpg';
        img.alt = 'Windows 10';
        text.textContent = 'Instalación de Windows 10 con respaldo de datos y configuración optimizada.';
      } else if (version === '11') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/2FsoPCl.jpg';
        img.alt = 'Windows 11';
        text.textContent = 'Instalación de Windows 11 con respaldo de datos y personalización avanzada.';
      } else {
        slider.innerHTML = `
          <img class="service-image" src="https://i.imgur.com/ZAo0SMG.jpg" alt="Windows 10">
          <img class="service-image" src="https://i.imgur.com/2FsoPCl.jpg" alt="Windows 11">
          <img class="service-image" src="https://i.imgur.com/wzH2Xc2.jpg" alt="Formateo">
        `;
        text.textContent = 'Formateamos tu equipo, respaldamos tus datos y instalamos Windows 10 o 11 con beneficios personalizados.';
        return;
      }
      slider.appendChild(img);
    }

    function updateProgramas() {
      const version = document.getElementById('programas-version').value;
      const slider = document.getElementById('programas-slider');
      const text = document.getElementById('programas-text');
      slider.innerHTML = '';
      let img;
      if (version === 'office') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/V2yJuhP.jpg';
        img.alt = 'Microsoft Office';
        text.textContent = 'Instalamos Microsoft Office (2013-2024) con licencia a tu elección.';
      } else if (version === 'antivirus') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/wHVVBGh.jpg';
        img.alt = 'Antivirus';
        text.textContent = 'Instalación de software antivirus para proteger tu equipo contra amenazas.';
      } else if (version === 'photoshop') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/V1nw66N.jpg';
        img.alt = 'Photoshop';
        text.textContent = 'Instalación de Adobe Photoshop para edición profesional de imágenes.';
      } else {
        slider.innerHTML = `
          <img class="service-image" src="https://i.imgur.com/V2yJuhP.jpg" alt="Microsoft Office">
          <img class="service-image" src="https://i.imgur.com/wHVVBGh.jpg" alt="Antivirus">
          <img class="service-image" src="https://i.imgur.com/V1nw66N.jpg" alt="Photoshop">
        `;
        text.textContent = 'Instalamos Microsoft Office (2013-2024) con opciones de licencia genérica o permanente.';
        return;
      }
      slider.appendChild(img);
    }

    function updateActualizacion() {
      const type = document.getElementById('actualizacion-type').value;
      const slider = document.getElementById('actualizacion-slider');
      const text = document.getElementById('actualizacion-text');
      slider.innerHTML = '';
      let img;
      if (type === 'ram') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/v2UYRfB.jpg';
        img.alt = 'Mejora de RAM';
        text.textContent = 'Aumenta la memoria RAM para mejorar la velocidad y multitarea.';
      } else if (type === 'ssd') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/lQtzOqI.jpg';
        img.alt = 'Cambio a SSD';
        text.textContent = 'Cambia a un disco SSD para arranques y cargas más rápidas.';
      } else if (type === 'software') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/2QKXLsC.jpg';
        img.alt = 'Actualización de Software';
        text.textContent = 'Actualizamos tu sistema operativo y programas a la última versión.';
      } else if (type === 'optimizacion') {
        img = document.createElement('img');
        img.className = 'service-image static';
        img.src = 'https://i.imgur.com/2QKXLsC.jpg';
        img.alt = 'Optimización';
        text.textContent = 'Optimizamos el rendimiento eliminando programas innecesarios y ajustando configuraciones.';
      } else {
        slider.innerHTML = `
          <img class="service-image" src="https://i.imgur.com/v2UYRfB.jpg" alt="Mejora de RAM">
          <img class="service-image" src="https://i.imgur.com/lQtzOqI.jpg" alt="Cambio a SSD">
          <img class="service-image" src="https://i.imgur.com/2QKXLsC.jpg" alt="Actualización de Software">
          <img class="service-image" src="https://i.imgur.com/2QKXLsC.jpg" alt="Optimización">
        `;
        text.textContent = 'Optimizamos tu equipo con mejoras de hardware y actualizaciones de software.';
        return;
      }
      slider.appendChild(img);
    }

    document.getElementById('miFormulario').addEventListener('submit', function(e) {
      e.preventDefault();
      const data = {
        nombre: this.nombre.value,
        numero: this.numero.value,
        direccion: this.direccion.value,
        horario: this.horario.value,
        servicio: this.servicio.value,
        opcion: this.opcion.value,
        timestamp: new Date().toISOString()
      };
      fetch('https://script.google.com/macros/s/AKfycbw93v-UVHZOuFnE7PtpM_5LNeH8kJkEoC6B6t_WT4Qmvp6wqGYwx8jlYSdY_doI6wH5/exec', {
        method: 'POST',
        body: JSON.stringify(data),
        headers: { 'Content-Type': 'application/json' }
      })
      .then(response => response.json())
      .then(data => {
        alert('¡Cita agendada con éxito! Te contactaremos pronto.');
        this.reset();
      })
      .catch(error => {
        alert('Error al enviar: ' + error);
      });
    });
  </script>
</body>
</html>
