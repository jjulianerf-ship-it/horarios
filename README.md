<!DOCTYPE html>
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
        .form-section {
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
        .dark-mode .form-section {
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
                    <th>  Lunes</th>
                    <th>  Martes</th>
                    <th>  Miércoles</th>
                    <th>  Jueves</th>
                    <th>  Viernes</th>
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

        <h2>Trabajos por Hacer</h2>
        <div class="trabajos" id="trabajos-list">
            <!-- Los trabajos se agregarán aquí dinámicamente -->
        </div>

        <div class="form-section">
            <h2>Agregar Trabajo</h2>
            <form id="trabajo-form">
                <label for="materia">Materia:</label>
                <select id="materia" name="materia" required>
                    <option value="Estadísticas y Diseño de Experimentos">Estadísticas y Diseño de Experimentos</option>
                    <option value="Economía">Economía</option>
                    <option value="Organización Industrial">Organización Industrial</option>
                    <option value="Práctica Profesionalizante I: Organización de la Producción">Práctica Profesionalizante I: Organización de la Producción</option>
                </select>
                <label for="descripcion">Descripción:</label>
                <input type="text" id="descripcion" name="descripcion" required>
                <label for="fecha">Fecha de entrega:</label>
                <input type="date" id="fecha" name="fecha" required>
                <button type="submit">Agregar</button>
            </form>
        </div>

        <h2>Calendario</h2>
        <div class="calendar-controls">
            <button id="prev-month">« Mes Anterior</button>
            <button id="next-month">Mes Siguiente »</button>
        </div>
        <div class="calendar" id="calendar"></div>

        <div class="mode-toggle">
            <button id="toggle-mode">Modo Oscuro</button>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const calendar = document.getElementById('calendar');
            const prevMonthButton = document.getElementById('prev-month');
            const nextMonthButton = document.getElementById('next-month');
            const toggleModeButton = document.getElementById('toggle-mode');
            const body = document.body;
            const trabajosList = document.getElementById('trabajos-list');

            let currentMonth = new Date().getMonth();
            let currentYear = new Date().getFullYear();

            function renderCalendar(month, year) {
                const firstDay = new Date(year, month).getDay();
                const lastDate = new Date(year, month + 1, 0).getDate();
                const calendarHeader = `<table>
                    <thead>
                        <tr>
                            <th>Dom</th>
                            <th>Lun</th>
                            <th>Mar</th>
                            <th>Mié</th>
                            <th>Jue</th>
                            <th>Vie</th>
                            <th>Sáb</th>
                        </tr>
                    </thead>
                    <tbody><tr>`;

                let calendarBody = calendarHeader;
                for (let i = 0; i < firstDay; i++) {
                    calendarBody += `<td></td>`;
                }

                for (let day = 1; day <= lastDate; day++) {
                    if ((firstDay + day - 1) % 7 === 0 && day !== 1) {
                        calendarBody += `</tr><tr>`;
                    }
                    let className = 'date';
                    if (new Date().getDate() === day && new Date().getMonth() === month && new Date().getFullYear() === year) {
                        className += ' today';
                    }
                    calendarBody += `<td class="${className}">${day}</td>`;
                }

                while ((firstDay + lastDate) % 7 !== 0) {
                    calendarBody += `<td></td>`;
                    lastDate++;
                }

                calendarBody += `</tr></tbody></table>`;
                calendar.innerHTML = calendarBody;
            }

            function toggleMode() {
                body.classList.toggle('dark-mode');
                toggleModeButton.textContent = body.classList.contains('dark-mode') ? 'Modo Claro' : 'Modo Oscuro';
            }

            prevMonthButton.addEventListener('click', function() {
                if (currentMonth === 0) {
                    currentMonth = 11;
                    currentYear--;
                } else {
                    currentMonth--;
                }
                renderCalendar(currentMonth, currentYear);
            });

            nextMonthButton.addEventListener('click', function() {
                if (currentMonth === 11) {
                    currentMonth = 0;
                    currentYear++;
                } else {
                    currentMonth++;
                }
                renderCalendar(currentMonth, currentYear);
            });

            toggleModeButton.addEventListener('click', toggleMode);

            renderCalendar(currentMonth, currentYear);

            document.getElementById('trabajo-form').addEventListener('submit', function(e) {
                e.preventDefault();
                const materia = document.getElementById('materia').value;
                const descripcion = document.getElementById('descripcion').value;
                const fecha = document.getElementById('fecha').value;

                const trabajoDiv = document.createElement('div');
                trabajoDiv.className = 'trabajo';
                trabajoDiv.innerHTML = `
                    <div class="materia">${materia}</div>
                    <ul>
                        <li>
                            <input type="checkbox" class="checkbox" />
                            <span class="descripcion">${descripcion}</span>
                            - <span class="fecha">${fecha}</span>
                        </li>
                    </ul>
                    <div class="edit-buttons">
                        <button class="edit-button">Editar</button>
                        <button class="remove-button">Eliminar</button>
                    </div>
                `;
                trabajosList.appendChild(trabajoDiv);
                document.getElementById('trabajo-form').reset();

                // Agregar eventos de edición y eliminación
                trabajoDiv.querySelector('.remove-button').addEventListener('click', function() {
                    trabajosList.removeChild(trabajoDiv);
                });

                trabajoDiv.querySelector('.edit-button').addEventListener('click', function() {
                    const descripcionSpan = trabajoDiv.querySelector('.descripcion');
                    const fechaSpan = trabajoDiv.querySelector('.fecha');
                    const checkbox = trabajoDiv.querySelector('.checkbox');

                    const newDescripcion = prompt("Ingrese la nueva descripción:", descripcionSpan.textContent);
                    const newFecha = prompt("Ingrese la nueva fecha de entrega:", fechaSpan.textContent);

                    if (newDescripcion !== null) {
                        descripcionSpan.textContent = newDescripcion;
                    }
                    if (newFecha !== null) {
                        fechaSpan.textContent = newFecha;
                    }
                    checkbox.checked = false; // Resetear el checkbox
                });

                trabajoDiv.querySelector('.checkbox').addEventListener('change', function() {
                    const isChecked = this.checked;
                    if (isChecked) {
                        trabajoDiv.querySelector('.descripcion').classList.add('completed');
                    } else {
                        trabajoDiv.querySelector('.descripcion').classList.remove('completed');
                    }
                });
            });
        });
    </script>
</body>
</html>
