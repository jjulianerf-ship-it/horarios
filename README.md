<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Horario y Trabajos por Hacer</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            color: #333;
            margin: 0;
            padding: 0;
            transition: background-color 0.3s, color 0.3s;
        }
        header {
            background-color: #333;
            color: #fff;
            padding: 10px 20px;
            text-align: center;
        }
        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        th, td {
            border: 1px solid black;
            text-align: center;
            padding: 10px;
        }
        th {
            background-color: #d3d3d3;
        }
        .yellow {
            background-color: #ffe599;
        }
        .green {
            background-color: #b6d7a8;
        }
        .blue {
            background-color: #9fc5e8;
        }
        .trabajos {
            margin-top: 20px;
        }
        .trabajo {
            margin-bottom: 15px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f9f9f9;
        }
        .materia {
            font-weight: bold;
            font-size: 18px;
            margin-bottom: 5px;
        }
        ul {
            list-style-type: none;
            margin-left: 0;
            padding-left: 0;
        }
        li {
            display: flex;
            align-items: center;
            margin-bottom: 5px;
        }
        input[type="checkbox"] {
            margin-right: 10px;
        }
        .completed {
            text-decoration: line-through;
            color: gray;
        }
        .form-section, .links-section {
            margin-top: 20px;
            padding: 10px;
            background-color: #e9ecef;
            border-radius: 5px;
        }
        label {
            font-weight: bold;
        }
        input[type="text"], select {
            width: calc(100% - 22px);
            padding: 10px;
            margin: 10px 0;
            box-sizing: border-box;
        }
        button {
            background-color: #28a745;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #218838;
        }
        .calendar {
            margin-top: 20px;
        }
        .calendar table {
            width: 100%;
            border-collapse: collapse;
        }
        .calendar th {
            background-color: #d3d3d3;
            padding: 10px;
        }
        .calendar td {
            padding: 10px;
            border: 1px solid #ccc;
            text-align: center;
        }
        .calendar td.active {
            background-color: #d3d3d3;
        }
        .calendar td.date {
            background-color: #fff;
        }
        .calendar td.date.today {
            background-color: #ffeb3b;
        }
        .calendar td.date.event {
            background-color: #b6d7a8;
        }
        .notification {
            background-color: #ffcccb;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
        }
        .mode-toggle {
            margin-top: 20px;
            text-align: right;
        }
        .mode-toggle button {
            background-color: #007bff;
            color: white;
        }
        .dark-mode {
            background-color: #333;
            color: #f4f4f4;
        }
        .dark-mode header {
            background-color: #444;
        }
        .dark-mode .container {
            background-color: #555;
        }
        .dark-mode th {
            background-color: #666;
        }
        .dark-mode .calendar td.date {
            background-color: #666;
        }
        .dark-mode .form-section, .dark-mode .links-section {
            background-color: #6c757d;
        }
        .dark-mode button {
            background-color: #28a745;
            color: white;
        }
        .dark-mode button:hover {
            background-color: #218838;
        }
        .edit-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 10px;
        }
        .edit-buttons button {
            background-color: #007bff;
            color: white;
            border: none;
            cursor: pointer;
            padding: 5px 10px;
            border-radius: 5px;
        }
        .edit-buttons button:hover {
            background-color: #0056b3;
        }
        .remove-button {
            background-color: #dc3545;
        }
        .remove-button:hover {
            background-color: #c82333;
        }
        .edit-task {
            display: none;
            margin-top: 10px;
            padding: 10px;
            background-color: #e9ecef;
            border-radius: 5px;
        }
        .calendar-controls {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <header>
        <h1>Horario y Trabajos por Hacer</h1>
    </header>

    <div class="container">
        <h2>Horario de Clases</h2>
        <table>
            <thead>
                <tr>
                    <th>Inicio</th>
                    <th>Lunes</th>
                    <th>Martes</th>
                    <th>Miércoles</th>
                    <th>Jueves</th>
                    <th>Viernes</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>13:00</td>
                    <td class="yellow">ORGANIZACIÓN INDUSTRIAL<br>(Viale)</td>
                    <td class="yellow">PROFESIONALIZANTE I:<br>ORGANIZACIÓN DE LA PRODUCCIÓN<br>(Daneri)<br>PRÁCTICA</td>
                    <td class="blue">ECONOMÍA<br>(Ventañú)</td>
                    <td class="green">ESTADÍSTICAS y<br>DISEÑO DE EXPERIMENTOS<br>(Ortiz)</td>
                    <td class="yellow">ORGANIZACIÓN INDUSTRIAL<br>(Viale)</td>
                </tr>
                <tr>
                    <td>14:00</td>
                    <td class="yellow">ORGANIZACIÓN INDUSTRIAL<br>(Viale)</td>
                    <td class="yellow">PROFESIONALIZANTE I:<br>ORGANIZACIÓN DE LA PRODUCCIÓN<br>(Daneri)<br>PRÁCTICA</td>
                    <td class="blue">ECONOMÍA<br>(Ventañú)</td>
                    <td class="green">ESTADÍSTICAS y<br>DISEÑO DE EXPERIMENTOS<br>(Ortiz)</td>
                    <td class="yellow">ORGANIZACIÓN INDUSTRIAL<br>(Viale)</td>
                </tr>
                <tr>
                    <td>15:10</td>
                    <td class="green">ESTADÍSTICAS y<br>DISEÑO DE EXPERIMENTOS<br>(Ortiz)</td>
                    <td class="yellow">PROFESIONALIZANTE I:<br>ORGANIZACIÓN DE LA PRODUCCIÓN<br>(Daneri)<br>PRÁCTICA</td>
                    <td class="blue">ECONOMÍA<br>(Ventañú)</td>
                    <td class="yellow">ORGANIZACIÓN INDUSTRIAL<br>(Viale)</td>
                    <td class="yellow">ORGANIZACIÓN INDUSTRIAL<br>(Viale)</td>
                </tr>
                <tr>
                    <td>16:10</td>
                    <td class="green">ESTADÍSTICAS y<br>DISEÑO DE EXPERIMENTOS<br>(Ortiz)</td>
                    <td class="yellow">PROFESIONALIZANTE I:<br>ORGANIZACIÓN DE LA PRODUCCIÓN<br>(Daneri)<br>PRÁCTICA</td>
                    <td class="blue">ECONOMÍA<br>(Ventañú)</td>
                    <td class="yellow">ORGANIZACIÓN INDUSTRIAL<br>(Viale)</td>
                    <td class="yellow">ORGANIZACIÓN INDUSTRIAL<br>(Viale)</td>
             
                </tr>
            </tbody>
        </table>

        <div id="trabajos" class="trabajos">
            <h2>Trabajos por Hacer</h2>
            <!-- Aquí se mostrarán los trabajos -->
        </div>

        <div class="form-section">
            <h3>Agregar Trabajo</h3>
            <label for="materia">Materia:</label>
            <select id="materia">
                <option value="">Selecciona una materia</option>
                <!-- Las materias se insertarán aquí -->
                    <option value="Estadísticas y Diseño de Experimentos">Estadísticas y Diseño de Experimentos</option>
                    <option value="Economía">Economía</option>
                    <option value="Organización Industrial">Organización Industrial</option>
                    <option value="Práctica Profesionalizante I: Organización de la Producción">Práctica Profesionalizante I: Organización de la Producción</option>
            </select>
            <label for="descripcion">Descripción:</label>
            <input type="text" id="descripcion">
            <label for="fecha">Fecha de Entrega:</label>
            <input type="date" id="fecha">
            <button onclick="agregarTrabajo()">Agregar Trabajo</button>
        </div>

        <div class="links-section">
            <h3>Enlaces Relacionados</h3>
            <ul id="links">
                <!-- Los enlaces se mostrarán aquí -->
            </ul>
            <label for="link-titulo">Título del Enlace:</label>
            <input type="text" id="link-titulo">
            <label for="link-url">URL del Enlace:</label>
            <input type="text" id="link-url">
            <button onclick="agregarLink()">Agregar Enlace</button>
        </div>

        <div class="calendar">
            <h3>Calendario</h3>
            <div class="calendar-controls">
                <button onclick="cambiarMes(-1)">Anterior</button>
                <button onclick="cambiarMes(1)">Siguiente</button>
            </div>
            <table>
                <thead>
                    <tr id="calendario-header">

                        <!-- Los días de la semana se insertarán aquí -->
                    </tr>
                </thead>
                <tbody id="calendario-body">
                    <!-- Los días del mes se insertarán aquí -->
                </tbody>
            </table>
        </div>

        <div class="notification">
            Novedades de la versión 1.0.2
Ahora, si recargas o entras mediante el link, no se borran los trabajos.
También tenemos un apartado nuevo donde puedes agregar tus propios links de las páginas que más usas.

ADVERTENCIA: Solo se guarda en el dispositivo desde el que entraste.


        </div>

<div class="links-section">
    <h2>Enlaces Útiles</h2>
    <ul>
        <li><a href="https://floorplanner.com/projects/160842477/editor" target="_blank">Enlace 1 futura virtual carpeta</a></li>
        <li><a href="https://www.example.com" target="_blank">Enlace 2 trabajos</a></li>
        <li><a href="https://www.example.com" target="_blank">Enlace 3 apps y programas</a></li>
        <li><a href="https://www.youtube.com/watch?v=wO1cIvij6PA" target="_blank">importante NO tocar</a></li>
    </ul>
</div>

        <div class="mode-toggle">
            <button onclick="toggleDarkMode()">Activar Modo Oscuro</button>
        </div>
    </div>

    <script>
        const trabajos = document.getElementById('trabajos');
        const materiasSelect = document.getElementById('materia');
        const linksList = document.getElementById('links');

        function cargarTrabajos() {
            const trabajosGuardados = JSON.parse(localStorage.getItem('trabajos')) || [];
            trabajos.innerHTML = '';
            trabajosGuardados.forEach((trabajo, index) => {
                trabajos.innerHTML += `
                    <div class="trabajo ${trabajo.completado ? 'completed' : ''}">
                        <div class="materia">${trabajo.materia}</div>
                        <div>${trabajo.descripcion}</div>
                        <div>${trabajo.fecha}</div>
                        <div class="edit-buttons">
                            <button onclick="editarTrabajo(${index})">Editar</button>
                            <button class="remove-button" onclick="eliminarTrabajo(${index})">Eliminar</button>
                            <button onclick="marcarCompleto(${index})">${trabajo.completado ? 'Marcar Incompleto' : 'Marcar Completo'}</button>
                        </div>
                        <div id="edit-task-${index}" class="edit-task">
                            <label for="edit-descripcion-${index}">Descripción:</label>
                            <input type="text" id="edit-descripcion-${index}" value="${trabajo.descripcion}">
                            <label for="edit-fecha-${index}">Fecha de Entrega:</label>
                            <input type="date" id="edit-fecha-${index}" value="${trabajo.fecha}">
                            <button onclick="guardarEdicion(${index})">Guardar</button>
                        </div>
                    </div>
                `;
            });
        }

        function agregarTrabajo() {
            const materia = document.getElementById('materia').value;
            const descripcion = document.getElementById('descripcion').value;
            const fecha = document.getElementById('fecha').value;

            if (materia && descripcion && fecha) {
                const trabajosGuardados = JSON.parse(localStorage.getItem('trabajos')) || [];
                trabajosGuardados.push({ materia, descripcion, fecha, completado: false });
                localStorage.setItem('trabajos', JSON.stringify(trabajosGuardados));
                cargarTrabajos();
                document.getElementById('materia').value = '';
                document.getElementById('descripcion').value = '';
                document.getElementById('fecha').value = '';
            } else {
                alert('Por favor, completa todos los campos.');
            }
        }

        function eliminarTrabajo(index) {
            const trabajosGuardados = JSON.parse(localStorage.getItem('trabajos')) || [];
            trabajosGuardados.splice(index, 1);
            localStorage.setItem('trabajos', JSON.stringify(trabajosGuardados));
            cargarTrabajos();
        }

        function editarTrabajo(index) {
            const editTaskDiv = document.getElementById(`edit-task-${index}`);
            if (editTaskDiv.style.display === 'none' || editTaskDiv.style.display === '') {
                editTaskDiv.style.display = 'block';
            } else {
                editTaskDiv.style.display = 'none';
            }
        }

        function guardarEdicion(index) {
            const descripcion = document.getElementById(`edit-descripcion-${index}`).value;
            const fecha = document.getElementById(`edit-fecha-${index}`).value;

            if (descripcion && fecha) {
                const trabajosGuardados = JSON.parse(localStorage.getItem('trabajos')) || [];
                trabajosGuardados[index] = { ...trabajosGuardados[index], descripcion, fecha };
                localStorage.setItem('trabajos', JSON.stringify(trabajosGuardados));
                cargarTrabajos();
            } else {
                alert('Por favor, completa todos los campos.');
            }
        }

        function marcarCompleto(index) {
            const trabajosGuardados = JSON.parse(localStorage.getItem('trabajos')) || [];
            trabajosGuardados[index].completado = !trabajosGuardados[index].completado;
            localStorage.setItem('trabajos', JSON.stringify(trabajosGuardados));
            cargarTrabajos();
        }

        function agregarLink() {
            const linkTitulo = document.getElementById('link-titulo').value;
            const linkUrl = document.getElementById('link-url').value;

            if (linkTitulo && linkUrl) {
                const linksGuardados = JSON.parse(localStorage.getItem('links')) || [];
                linksGuardados.push({ titulo: linkTitulo, url: linkUrl });
                localStorage.setItem('links', JSON.stringify(linksGuardados));
                cargarLinks();
                document.getElementById('link-titulo').value = '';
                document.getElementById('link-url').value = '';
            } else {
                alert('Por favor, completa todos los campos.');
            }
        }

        function cargarLinks() {
            const linksGuardados = JSON.parse(localStorage.getItem('links')) || [];
            linksList.innerHTML = '';
            linksGuardados.forEach(link => {
                linksList.innerHTML += `
                    <li>
                        <a href="${link.url}" target="_blank">${link.titulo}</a>
                    </li>
                `;
            });
        }

        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
            const button = document.querySelector('.mode-toggle button');
            button.textContent = document.body.classList.contains('dark-mode') ? 'Desactivar Modo Oscuro' : 'Activar Modo Oscuro';
        }

        // Funciones del calendario
        let mesActual = new Date().getMonth();
        let anoActual = new Date().getFullYear();

        function cargarCalendario() {
            const header = document.getElementById('calendario-header');
            const body = document.getElementById('calendario-body');

            // Días de la semana
            header.innerHTML = `
                <th>Dom</th>
                <th>Lun</th>
                <th>Mar</th>
                <th>Mié</th>
                <th>Jue</th>
                <th>Vie</th>
                <th>Sab</th>
            `;

            // Primer día del mes
            const primerDia = new Date(anoActual, mesActual, 1).getDay();
            const diasEnMes = new Date(anoActual, mesActual + 1, 0).getDate();

            let filas = '';
            let dia = 1;

            // Vaciar el calendario
            body.innerHTML = '';

            // Espacios en blanco antes del primer día
            let fila = '<tr>';
            for (let i = 0; i < primerDia; i++) {
                fila += '<td></td>';
            }

            // Días del mes
            for (let i = primerDia; dia <= diasEnMes; i++) {
                fila += `<td>${dia}</td>`;
                dia++;
                if (i % 7 === 6) {
                    fila += '</tr>';
                    body.innerHTML += fila;
                    fila = '<tr>';
                }
            }

            // Rellenar el último renglón
            if (fila !== '<tr>') {
                while (dia % 7 !== 1) {
                    fila += '<td></td>';
                    dia++;
                }
                fila += '</tr>';
                body.innerHTML += fila;
            }
        }

        function cambiarMes(mes) {
            mesActual += mes;
            if (mesActual < 0) {
                mesActual = 11;
                anoActual--;
            } else if (mesActual > 11) {
                mesActual = 0;
                anoActual++;
            }
            cargarCalendario();
        }

        document.addEventListener('DOMContentLoaded', () => {
            cargarTrabajos();
            cargarLinks();
            cargarCalendario();
        });
    </script>
</body>
</html>
