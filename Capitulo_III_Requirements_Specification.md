<div align="justify">

## 3.1. To-Be Scenario Mapping.

En esta sección, abordaremos el To-Be Scenario Mapping para nuestro segmento agencia de tours, donde describiremos cómo deben configurarse las experiencias durante cada fase. Este mapa representa una visión de cómo deberían evolucionar la gestión de los equipajes, maletas de cada tour a medida que se implementan cambios y mejoras en los procesos y sistemas. A continuación, se incluye una representación gráfica del mismo:

<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/main/Resources/scenario-mapping/To_Be.png" alt="scenario6" />
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
            <td>5</td>
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
      <th>Scenarios &amp; Acceptance Criteria</th>
      <th>Epic ID</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>US01</td>
      <td>Integración de Balanzas Inteligentes</td>
      <td>Como agencia de tours, quiero integrar balanzas inteligentes en los puntos de registro de equipaje para monitorear el peso del equipaje de los pasajeros en tiempo real.</td>
      <td>
        SC01: Integración Exitosa<br><br>
        AC01: Balanza conectada<br>
        Dado que se ha instalado una balanza inteligente en el punto de registro de equipaje.<br>
        Cuando se inicie la conexión de la balanza a la plataforma.<br>
        Entonces la plataforma recibirá datos de peso en tiempo real de la balanza.<br><br>
        SC02: Alerta de Exceso de Peso<br><br>
        AC02: Peso dentro de límites<br>
        Dado que la plataforma está recibiendo datos de peso en tiempo real de la balanza.<br>
        Cuando el peso del equipaje está dentro de los límites establecidos.<br>
        Entonces no se generará ninguna alerta.<br><br>
        SC03: Alerta de Exceso de Peso<br><br>
        AC03: Peso excede límites<br>
        Dado que la plataforma está recibiendo datos de peso en tiempo real de la balanza.<br>
        Cuando el peso del equipaje excede los límites establecidos.<br>
        Entonces se generará una alerta automática de exceso de peso.<br>
      </td>
      <td>EP01</td>
    </tr>
    <tr>
      <td>US02</td>
      <td>Integración de Sensores de Impacto y Vibración</td>
      <td>Como agencia de tours, quiero integrar sensores de impacto y vibración en los compartimentos de almacenamiento del vehículo para detectar movimientos bruscos o golpes durante el transporte.</td>
      <td>
        SC04: Integración Exitosa<br><br>
        AC04: Sensor conectado<br>
        Dado que se ha instalado un sensor de impacto y vibración en el compartimento de almacenamiento del vehículo.<br>
        Cuando se inicie la conexión del sensor a la plataforma.<br>
        Entonces la plataforma recibirá datos de movimientos y golpes en tiempo real.<br><br>
        SC05: Detección de Movimiento Brusco<br><br>
        AC05: Sin movimiento brusco<br>
        Dado que la plataforma está recibiendo datos de movimientos y golpes en tiempo real del sensor.<br>
        Cuando no se detecte ningún movimiento brusco o golpe.<br>
        Entonces no se generará ninguna alerta.<br><br>
        SC06: Detección de Movimiento Brusco<br><br>
        AC06: Movimiento brusco detectado<br>
        Dado que la plataforma está recibiendo datos de movimientos y golpes en tiempo real del sensor.<br>
        Cuando se detecte un movimiento brusco o golpe.<br>
        Entonces se generará una alerta automática de movimiento brusco.<br>
      </td>
      <td>EP01</td>
    </tr>
    <tr>
      <td>US03</td>
      <td>Análisis de Datos de Balanzas Inteligentes</td>
      <td>Como agencia de tours, quiero que la plataforma analice los datos de peso recibidos de las balanzas inteligentes para identificar situaciones de exceso de peso.</td>
      <td>
        SC07: Análisis de Datos<br><br>
        AC07: Peso dentro de límites<br>
        Dado que la plataforma está recibiendo datos de peso en tiempo real de la balanza.<br>
        Cuando el peso del equipaje está dentro de los límites establecidos.<br>
        Entonces la plataforma no generará ninguna alerta de exceso de peso.<br><br>
        SC08: Análisis de Datos<br><br>
        AC08: Peso excede límites<br>
        Dado que la plataforma está recibiendo datos de peso en tiempo real de la balanza.<br>
        Cuando el peso del equipaje excede los límites establecidos.<br>
        Entonces la plataforma generará una alerta automática de exceso de peso.<br>
      </td>
      <td>EP02</td>
    </tr>
    <tr>
      <td>US04</td>
      <td>Análisis de Datos de Sensores de Impacto y Vibración</td>
      <td>Como agencia de tours, quiero que la plataforma analice los datos de los sensores de impacto y vibración para identificar movimientos bruscos o golpes.</td>
      <td>
        SC09: Análisis de Datos<br><br>
        AC09: Sin movimiento brusco<br><
        Dado que la plataforma está recibiendo datos de movimientos y golpes en tiempo real del sensor.<br>
        Cuando no se detecte ningún movimiento brusco o golpe.<br>
        Entonces la plataforma no generará ninguna alerta de movimiento brusco.<br><br>
        SC10: Análisis de Datos<br><br>
        AC10: Movimiento brusco detectado<br>
        Dado que la plataforma está recibiendo datos de movimientos y golpes en tiempo real del sensor.<br>
        Cuando se detecte un movimiento brusco o golpe.<br>
        Entonces la plataforma generará una alerta automática de movimiento brusco.<br>
      </td>
      <td>EP02</td>
    </tr>
    <tr>
      <td>US05</td>
      <td>Registro de Incidentes de Manejo Brusco</td>
      <td>Como agencia de tours, quiero que la plataforma registre y notifique cualquier incidente de manejo brusco detectado por los sensores de impacto y vibración.</td>
      <td>
        SC11: Registro de Incidentes<br><br>
        AC11: Sin incidentes<br>
        Dado que la plataforma está recibiendo datos de movimientos y golpes en tiempo real del sensor.<br>
        Cuando no se detecte ningún movimiento brusco o golpe.<br>
        Entonces la plataforma no registrará ningún incidente de manejo brusco.<br><br>
        SC12: Registro de Incidentes<br><br>
        AC12: Incidente detectado<br>
        Dado que la plataforma está recibiendo datos de movimientos y golpes en tiempo real del sensor.<br>
        Cuando se detecte un movimiento brusco o golpe.<br>
        Entonces la plataforma registrará y notificará el incidente de manejo brusco.<br>
      </td>
      <td>EP02</td>
    </tr>
    <tr>
      <td>US06</td>
      <td>Generación de Alertas por Exceso de Peso</td>
      <td>Como agencia de tours, quiero recibir alertas automáticas en tiempo real cuando se detecte un exceso de peso para poder reorganizar la carga.</td>
      <td>
        SC13: Generación de Alertas<br><br>
        AC13: Peso dentro de límites<br>
        Dado que la plataforma está recibiendo datos de peso en tiempo real de la balanza.<br>
        Cuando el peso del equipaje está dentro de los límites establecidos.<br>
        Entonces no se generará ninguna alerta.<br><br>
        SC14: Generación de Alertas<br><br>
        AC14: Peso excede límites<br>
        Dado que la plataforma está recibiendo datos de peso en tiempo real de la balanza.<br>
        Cuando el peso del equipaje excede los límites establecidos.<br>
        Entonces se generará una alerta automática de exceso de peso.<br>
      </td>
      <td>EP03</td>
    </tr>
    <tr>
      <td>US07</td>
      <td>Funcionalidad de Reorganización de Carga</td>
      <td>Como agencia de tours, quiero poder reorganizar la carga del equipaje en base a las alertas recibidas por exceso de peso para garantizar un viaje seguro.</td>
      <td>
        SC15: Reorganización de Carga<br><br>
        AC15: Carga reorganizada con éxito<br>
        Dado que el conductor recibe una alerta de exceso de peso.<br>
        Cuando el conductor reorganiza la carga del equipaje según las instrucciones de la alerta.<br>
        Entonces la carga se reorganiza con éxito y se confirma la acción realizada.<br><br>
        SC16: Reorganización de Carga<br><br>
        AC16: Carga no reorganizada<br>
        Dado que el conductor recibe una alerta de exceso de peso.<br>
        Cuando el conductor no reorganiza la carga del equipaje según las instrucciones de la alerta.<br>
        Entonces la carga no se reorganiza y se requiere confirmación.<br>
      </td>
      <td>EP03</td>
    </tr>
    <tr>
      <td>US08</td>
      <td>Registro de Acciones de Reorganización de Carga</td>
      <td>Como agencia de tours, quiero que la plataforma registre las acciones de reorganización de carga realizadas por el conductor para futuras referencias.</td>
      <td>
        SC17: Registro de Acciones<br><br>
        AC17: Acción registrada con éxito<br>
        Dado que el conductor reorganiza la carga del equipaje según las instrucciones de la alerta.<br>
        Cuando se confirma la acción realizada por el conductor.<br>
        Entonces la plataforma registra la acción de reorganización de carga con éxito.<br><br>
        SC18: Registro de Acciones<br><br>
        AC18: Acción no registrada<br>
        Dado que el conductor reorganiza la carga del equipaje según las instrucciones de la alerta.<br>
        Cuando no se confirma la acción realizada por el conductor.<br>
        Entonces la plataforma no registra la acción de reorganización de carga y se requiere confirmación.<br>
      </td>
      <td>EP03</td>
    </tr>
    <tr>
      <td>US09</td>
      <td>Generación de Reportes de Reorganización de Carga</td>
      <td>Como agencia de tours, quiero generar reportes periódicos sobre las acciones de reorganización de carga realizadas para evaluar el desempeño y eficacia del sistema.</td>
      <td>
        SC19: Generación de Reportes<br><br>
        AC19: Reporte generado con éxito<br>
        Dado que se han realizado acciones de reorganización de carga.<br>
        Cuando se genera un reporte periódico sobre las acciones de reorganización de carga.<br>
        Entonces el reporte se genera con éxito y se puede consultar la información detallada.<br>
      </td>
      <td>EP03</td>
    </tr>
    <tr>
      <td>US10</td>
      <td>Capacitación para Conducción Segura</td>
      <td>Como agencia de tours, quiero ofrecer capacitación y orientación al conductor sobre cómo manejar y reorganizar la carga de manera segura.</td>
      <td>
        SC20: Capacitación Exitosa<br><br>
        AC20: Conductor capacitado<br>
        Dado que el conductor necesita orientación sobre cómo manejar y reorganizar la carga de manera segura.<br>
        Cuando el conductor completa la capacitación y confirma su finalización.<br>
        Entonces la plataforma registra que el conductor ha sido capacitado y está listo para conducir de manera segura.<br>
      </td>
      <td>EP03</td>
    </tr>
  </tbody>
</table>

## 3.3. Impact Mapping.

En esta sección, nuestro equipo presenta el Impact Mapping, el cual es una herramienta visual y colaborativa que ayuda a los equipos a alinear sus objetivos con los resultados deseados.

<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/main/Resources/scenario-mapping/Impact_Mapping.png" alt="scenario6" />
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
            <td>US08</td>
            <td>Registro de Acciones de Reorganización de Carga</td>
            <td>Como agencia de tours, quiero que la plataforma registre las acciones de reorganización de carga realizadas por el conductor para futuras referencias.</td>
            <td>3</td>
        </tr>
        <tr>
            <td>8</td>
            <td>US09</td>
            <td>Generación de Reportes de Reorganización de Carga</td>
            <td>Como agencia de tours, quiero generar reportes periódicos sobre las acciones de reorganización de carga realizadas para evaluar el desempeño y eficacia del sistema.</td>
            <td>3</td>
        </tr>
        <tr>
            <td>9</td>
            <td>US05</td>
            <td>Registro de Incidentes de Manejo Brusco</td>
            <td>Como agencia de tours, quiero que la plataforma registre y notifique cualquier incidente de manejo brusco detectado por los sensores de impacto y vibración.</td>
            <td>2</td>
        </tr>
        <tr>
            <td>10</td>
            <td>US10</td>
            <td>Capacitación para Conducción Segura</td>
            <td>Como agencia de tours, quiero ofrecer capacitación y orientación al conductor sobre cómo manejar y reorganizar la carga de manera segura.</td>
            <td>3</td>
        </tr>
    </tbody>
</table>
</div>
