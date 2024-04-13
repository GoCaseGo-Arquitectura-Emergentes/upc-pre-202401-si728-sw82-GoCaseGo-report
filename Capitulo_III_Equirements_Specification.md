<div align="justify">


## 3.1. To-Be Scenario Mapping.
En esta sección, abordaremos el To-Be Scenario Mapping para nuestro segmento agencia de tours, donde describiremos cómo deben configurarse las experiencias durante cada fase. Este mapa representa una visión de cómo deberían evolucionar la gestión de los equipajes, maletas de cada tour a medida que se implementan cambios y mejoras en los procesos y sistemas. A continuación, se incluye una representación gráfica del mismo:

<div align="center">
  <img src="./Resources/scenario-mapping/To_Be.png" alt="scenario6" />
</div>

## 3.2. User Stories.
En esta sección, profundizaremos en la definición y elaboración de las User Stories relacionadas con nuestro proyecto. Las User Stories son una herramienta fundamental en el desarrollo de software y proyectos de diseño centrados en el usuario.

### Epics

<table>
    <thead>
        <tr>
            <th>Epic ID</th>
            <th>Título</th>
            <th>Descripción</th>
            <th>Número de User Stories asociados</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>EP01</td>
            <td>Integración de Dispositivos IoT</td>
            <td>Integrar y configurar balanzas inteligentes y sensores de impacto y vibración en la plataforma.</td>
            <td>2</td>
        </tr>
        <tr>
            <td>EP02</td>
            <td>Análisis y Monitorización de Equipaje</td>
            <td>Analizar los datos recibidos de las balanzas y sensores para identificar situaciones de riesgo.</td>
            <td>3</td>
        </tr>
        <tr>
            <td>EP03</td>
            <td>Funcionalidades de Reorganización de Carga</td>
            <td>Implementar funcionalidades para la reorganización de la carga basada en las alertas recibidas.</td>
            <td>6</td>
        </tr>
    </tbody>
</table>

### User Stories
En esta sección, profundizaremos en la definición y elaboración de las User Stories relacionadas con nuestro proyecto. Estas User Stories son una herramienta fundamental en el desarrollo de software y proyectos de diseño centrados en el usuario.

<table>
    <thead>
        <tr>
            <th>User Story ID</th>
            <th>Título</th>
            <th>Descripción</th>
            <th>Scenarios & Acceptance Criteria</th>
            <th>Epic ID</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>US01</td>
            <td>Integración de Balanzas Inteligentes</td>
            <td>Como agencia de tours, quiero integrar balanzas inteligentes en los puntos de registro de equipaje para monitorear el peso del equipaje de los pasajeros en tiempo real.</td>
            <td><p>SC01: Integración Exitosa</p><p>AC01: Balanza conectada</p><p>Dado que se ha instalado una balanza inteligente en el punto de registro de equipaje.</p><p>Cuando se inicie la conexión de la balanza a la plataforma.</p><p>Entonces la plataforma recibirá datos de peso en tiempo real de la balanza.</p><p>SC02: Alerta de Exceso de Peso</p><p>AC02: Peso dentro de límites</p><p>...</p></td>
            <td>EP01</td>
        </tr>
        <tr>
            <td>US02</td>
            <td>Integración de Sensores de Impacto y Vibración</td>
            <td>Como agencia de tours, quiero integrar sensores de impacto y vibración en los compartimentos de almacenamiento del vehículo para detectar movimientos bruscos o golpes durante el transporte.</td>
            <td><p>SC04: Integración Exitosa</p><p>AC04: Sensor conectado</p><p>Dado que se ha instalado un sensor de impacto y vibración en el compartimento de almacenamiento del vehículo.</p><p>Cuando se inicie la conexión del sensor a la plataforma.</p><p>Entonces la plataforma recibirá datos de movimientos y golpes en tiempo real.</p><p>SC05: Detección de Movimiento Brusco</p><p>AC05: Sin movimiento brusco</p><p>...</p></td>
            <td>EP01</td>
        </tr>
        <tr>
            <td>US03</td>
            <td>Análisis de Datos de Balanzas Inteligentes</td>
            <td>Como agencia de tours, quiero que la plataforma analice los datos de peso recibidos de las balanzas inteligentes para identificar situaciones de exceso de peso.</td>
            <td><p>SC07: Análisis de Datos</p><p>AC07: Peso dentro de límites</p><p>...</p></td>
            <td>EP02</td>
        </tr>
        <tr>
            <td>US04</td>
            <td>Análisis de Datos de Sensores de Impacto y Vibración</td>
            <td>Como agencia de tours, quiero que la plataforma analice los datos de los sensores de impacto y vibración para identificar movimientos bruscos o golpes.</td>
            <td><p>SC09: Análisis de Datos</p><p>AC09: Sin movimiento brusco</p><p>...</p></td>
            <td>EP02</td>
        </tr>
        <tr>
            <td>US05</td>
            <td>Registro de Incidentes de Manejo Brusco</td>
            <td>Como agencia de tours, quiero que la plataforma registre y notifique cualquier incidente de manejo brusco detectado por los sensores de impacto y vibración.</td>
            <td><p>SC11: Registro de Incidentes</p><p>AC11: Sin incidentes</p><p>...</p></td>
            <td>EP02</td>
        </tr>
        <tr>
            <td>US06</td>
            <td>Generación de Alertas por Exceso de Peso</td>
            <td>Como agencia de tours, quiero recibir alertas automáticas en tiempo real cuando se detecte un exceso de peso para poder reorganizar la carga.</td>
            <td><p>SC13: Generación de Alertas</p><p>AC13: Peso dentro de límites</p><p>...</p></td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US07</td>
            <td>Funcionalidad de Reorganización de Carga</td>
            <td>Como agencia de tours, quiero poder reorganizar la carga del equipaje en base a las alertas recibidas por exceso de peso para garantizar un viaje seguro.</td>
            <td><p>SC15: Reorganización de Carga</p><p>AC15: Carga reorganizada con éxito</p><p>...</p></td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US08</td>
            <td>Registro de Acciones de Reorganización de Carga</td>
            <td>Como agencia de tours, quiero que la plataforma registre las acciones de reorganización de carga realizadas por el conductor para futuras referencias.</td>
            <td><p>SC17: Registro de Acciones</p><p>AC17: Acción registrada con éxito</p><p>...</p></td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US09</td>
            <td>Generación de Reportes de Reorganización de Carga</td>
            <td>Como agencia de tours, quiero generar reportes periódicos sobre las acciones de reorganización de carga realizadas para evaluar el desempeño y eficacia del sistema.</td>
            <td><p>SC19: Generación de Reportes</p><p>AC19: Reporte generado con éxito</p><p>...</p></td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US10</td>
            <td>Capacitación para Conducción Segura</td>
            <td>Como agencia de tours, quiero ofrecer capacitación y orientación al conductor sobre cómo manejar y reorganizar la carga de manera segura.</td>
            <td><p>SC20: Capacitación Exitosa</p><p>AC20: Conductor capacitado</p><p>...</p></td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US11</td>
            <td>Integración con Sistemas de Reservas de Tours</td>
            <td>Como agencia de tours, quiero que la plataforma esté integrada con el sistema de reservas de tours para obtener información detallada sobre los viajes planificados y la capacidad del vehículo.</td>
            <td><p>SC21: Integración Exitosa</p><p>AC21: Sistema integrado</p><p>...</p></td>
            <td>EP03</td>
        </tr>
        <tr>
            <td>US12</td>
            <td>Notificaciones y Alertas Personalizadas</td>
            <td>Como pasajero, quiero recibir notificaciones y alertas personalizadas sobre el estado y seguridad de mi equipaje durante el viaje.</td>
            <td><p>SC22: Notificación de Estado de Equipaje</p><p>AC22: Notificación enviada</p><p>...</p></td>
            <td>EP03</td>
        </tr>
    </tbody>
</table>

## 3.3. Impact Mapping.
En esta sección, nuestro equipo presenta el Impact Mapping, el cual es una herramienta visual y colaborativa que ayuda a los equipos a alinear sus objetivos con los resultados deseados.

<div align="center">
  <img src="./Resources/scenario-mapping/Impact_Mapping.png" alt="scenario6" />
</div>

## 3.4. Product Backlog.
En el Product Backlog presentaremos una lista priorizada de nuestras user stories según el nivel de prioridad que acordamos en el equipo, esencial para el enfoque ágil.

<table>
    <thead>
        <tr>
            <th># Orden</th>
            <th>User Story ID</th>
            <th>Título</th>
            <th>Descripción</th>
            <th>Story Points (1/2/3/5/8)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>US01</td>
            <td>Integración de Balanzas Inteligentes</td>
            <td>Como agencia de tours, quiero integrar balanzas inteligentes en los puntos de registro de equipaje para monitorear el peso del equipaje de los pasajeros en tiempo real.</td>
            <td>8</td>
        </tr>
        <tr>
            <td>2</td>
            <td>US02</td>
            <td>Integración de Sensores de Impacto y Vibración</td>
            <td>Como agencia de tours, quiero integrar sensores de impacto y vibración en los compartimentos de almacenamiento del vehículo para detectar movimientos bruscos o golpes durante el transporte.</td>
            <td>8</td>
        </tr>
        <tr>
            <td>3</td>
            <td>US06</td>
            <td>Generación de Alertas por Exceso de Peso</td>
            <td>Como agencia de tours, quiero recibir alertas automáticas en tiempo real cuando se detecte un exceso de peso para poder reorganizar la carga.</td>
            <td>2</td>
        </tr>
        <tr>
            <td>4</td>
            <td>US03</td>
            <td>Análisis de Datos de Balanzas Inteligentes</td>
            <td>Como agencia de tours, quiero que la plataforma analice los datos de peso recibidos de las balanzas inteligentes para identificar situaciones de exceso de peso.</td>
            <td>3</td>
        </tr>
        <tr>
            <td>5</td>
            <td>US04</td>
            <td>Análisis de Datos de Sensores de Impacto y Vibración</td>
            <td>Como agencia de tours, quiero que la plataforma analice los datos de los sensores de impacto y vibración para identificar movimientos bruscos o golpes.</td>
            <td>3</td>
        </tr>
        <tr>
            <td>6</td>
            <td>US07</td>
            <td>Funcionalidad de Reorganización de Carga</td>
            <td>Como agencia de tours, quiero poder reorganizar la carga del equipaje en base a las alertas recibidas por exceso de peso para garantizar un viaje seguro.</td>
            <td>5</td>
        </tr>
        <tr>
            <td>7</td>
            <td>US12</td>
            <td>Notificaciones y Alertas Personalizadas</td>
            <td>Como pasajero, quiero recibir notificaciones y alertas personalizadas sobre el estado y seguridad de mi equipaje durante el viaje.</td>
            <td>2</td>
        </tr>
        <tr>
            <td>8</td>
            <td>US08</td>
            <td>Registro de Acciones de Reorganización de Carga</td>
            <td>Como agencia de tours, quiero que la plataforma registre las acciones de reorganización de carga realizadas por el conductor para futuras referencias.</td>
            <td>3</td>
        </tr>
        <tr>
            <td>9</td>
            <td>US09</td>
            <td>Generación de Reportes de Reorganización de Carga</td>
            <td>Como agencia de tours, quiero generar reportes periódicos sobre las acciones de reorganización de carga realizadas para evaluar el desempeño y eficacia del sistema.</td>
            <td>3</td>
        </tr>
        <tr>
            <td>10</td>
            <td>US05</td>
            <td>Registro de Incidentes de Manejo Brusco</td>
            <td>Como agencia de tours, quiero que la plataforma registre y notifique cualquier incidente de manejo brusco detectado por los sensores de impacto y vibración.</td>
            <td>2</td>
        </tr>
        <tr>
            <td>11</td>
            <td>US10</td>
            <td>Capacitación para Conducción Segura</td>
            <td>Como agencia de tours, quiero ofrecer capacitación y orientación al conductor sobre cómo manejar y reorganizar la carga de manera segura.</td>
            <td>3</td>
        </tr>
        <tr>
            <td>12</td>
            <td>US11</td>
            <td>Integración con Sistemas de Reservas de Tours</td>
            <td>Como agencia de tours, quiero que la plataforma esté integrada con el sistema de reservas de tours para obtener información detallada sobre los viajes planificados y la capacidad del vehículo.</td>
            <td>5</td>
        </tr>
    </tbody>
</table>
</div>