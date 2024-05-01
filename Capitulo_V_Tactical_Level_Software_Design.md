# Capítulo V: Tactical-Level Software Design.  
## 5.1. Bounded Context: Profile management
Este bounded context se centra en las clases y capas relacionadas con la gestión de perfiles de usuario, permitiendo a los usuarios ver y actualizar su información de perfil. A continuación, se detallan las principales componentes de este contexto:

## 5.1.1. Domain Layer. 
- **UserProfile:** Esta clase representa el perfil del usuario y contiene atributos como nombre, apellidos, dirección de correo electrónico, número de teléfono, foto de perfil, y otros detalles personales. También puede incluir métodos para actualizar la información del perfil.
- **ProfilePrivacySettings:** Esta clase define la configuración de privacidad del perfil, que permite a los usuarios controlar quién puede ver ciertos elementos de su perfil.
- **ProfileActivity:** Esta clase registra la actividad del usuario en su perfil, como cambios de foto de perfil, actualizaciones de información, etc. Esto puede ayudar a rastrear el historial de actividad del perfil.

## 5.1.2. Interface Layer. 
- **ProfileViewController:** Este controlador maneja las solicitudes relacionadas con la visualización del perfil del usuario. Permite a los usuarios ver su información de perfil y configurar la privacidad de sus datos.
- **ProfileUpdateController:** Este controlador se encarga de las solicitudes de actualización de información de perfil. Facilita a los usuarios la capacidad de modificar su información personal, incluyendo la foto de perfil.

## 5.1.3. Application Layer. 
- **ProfileViewService:** Este servicio de aplicación se encarga de procesar las solicitudes de visualización de perfiles de usuario. Accede a la base de datos para recuperar la información del perfil y aplica las configuraciones de privacidad antes de mostrarla al usuario.
- **ProfileUpdateService:** Se encarga de procesar las solicitudes de actualización de información de perfil. Valida los cambios propuestos por el usuario, actualiza los datos en la base de datos y registra la actividad correspondiente en el perfil.

## 5.1.4. Infrastructure Layer. 
- **ProfileRepository:** Su principal función es interactuar con la base de datos para realizar operaciones de lectura y escritura de información de perfiles de usuario. Almacena y recupera datos de perfil, configuraciones de privacidad y actividad.
- **ImageStorageService:** Este servicio se encarga de almacenar y recuperar imágenes de perfil de usuario, como las fotos de perfil. Puede estar conectado a un sistema de almacenamiento de objetos para gestionar eficazmente las imágenes.
- **PrivacySettingsRepository:** Almacena y recupera la configuración de privacidad de los perfiles de usuario.
- **ActivityLogRepository:** Registra y recupera la actividad del perfil de usuario.

## 5.1.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/profilecd.png" alt="profilecd" />
</div>

## 5.1.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.1.6.1. Bounded Context Domain Layer Class Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/class-diagrams/profile.png" alt="profile" />
</div>

## 5.1.6.2. Bounded Context Database Design Diagram. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/database-diagrams/profile.png" alt="profile" />
</div>


## 5.2. Bounded Context: Identity and Access Management 
Mediante el uso de este bounded context se abordan las clases y capas relacionadas con la identidad y el acceso de los usuarios al sistema. A continuación, se detallan las principales componentes de este contexto:

## 5.2.1. Domain Layer. 
*  **User** : Esta clase representa al usuario, teniendo como atributos el nombre de usuario, contraseña y un objeto de tipo Account. Tendría métodos para poder cerrar la cuenta y también para determinar si el usuario es dueño de la cuenta.
* **Account**: Esta clase representa la cuenta conectada al usuario, teniendo como atributos el nombre de usuario, un identificador, un objeto owner de tipo User y un rol para especificar a qué segmento objetivo pertenece. Entre sus métodos se encuentran cambiar el tipo de suscripción, crear un usuario, entre otros.

## 5.2.2. Interface Layer. 
* **SignIn Controller**: Este controlador maneja las solicitudes relacionadas con la autenticación e inicio de sesión de los usuarios. Permite el inicio de sesión y la gestión de cuentas de usuario existentes en la plataforma. Utiliza Firebase Authentication para la autenticación de usuarios.
* **SignUp Controller** :  Este controlador se encarga de las solicitudes de creación de nuevas cuentas de usuario. Facilita el registro de nuevos usuarios en la plataforma mediante Firebase Authentication.

## 5.2.3. Application Layer. 
* **SignIn CommandHandler:** Este comando se encarga de manejar las solicitudes de inicio de sesión de usuarios en el sistema. Cuando recibe una solicitud de inicio de sesión del SignIn Controller, verifica las credenciales utilizando Firebase Authentication y permite o deniega el acceso según el resultado.
* **SignUp CommandHandler:** Se encarga de gestionar las solicitudes de creación de nuevas cuentas de usuario en la plataforma. Cuando recibe una solicitud de registro del SignUp Controller, utiliza Firebase Authentication para registrar al nuevo usuario y, si la operación tiene éxito, crea una cuenta de usuario en la base de datos.
* **Account Reporting CommandHandler:** Este Command Handler se encarga de procesar las solicitudes de reporte de cuentas de usuario.

## 5.2.4. Infrastructure Layer. 
* **SignUp Application Service:** Este componente es parte de la capa de infraestructura y se encarga de gestionar la lógica de aplicación relacionada con el registro de usuarios. Trabaja en conjunto con el SignUp CommandHandler para crear nuevas cuentas de usuario utilizando Firebase Authentication. Además, puede estar conectado a la base de datos para almacenar información adicional sobre los usuarios registrados.
* **SignIn Application Service:** Se encarga de gestionar la lógica de aplicación relacionada con el inicio de sesión de usuarios. Colabora con el SignIn CommandHandler para autenticar a los usuarios utilizando Firebase Authentication.
* **User Repository:**  Su principal función es interactuar con la base de datos para realizar operaciones de lectura y escritura de información de usuarios. Almacena y recupera datos de usuarios, como perfiles, credenciales y roles.
* **FireBase Adapter:** Se encarga de comunicarse con Firebase Authentication para realizar operaciones como el registro y el inicio de sesión de usuarios. 
  
## 5.2.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/iacd.png" alt="iacd" />
</div>

## 5.2.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.2.6.1. Bounded Context Domain Layer Class Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/class-diagrams/ia.png" alt="ia" />
</div>

## 5.2.6.2. Bounded Context Database Design Diagram. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/database-diagrams/profile.png" alt="profile" />
</div>

## 5.3. Bounded Context: Iot Asset management
## 5.3.1. Domain Layer. 
*  **IoTDevice** : Esta clase representa un dispositivo IoT genérico y actúa como una entidad padre para varios tipos de dispositivos IoT teniendo como atibutos IP y MAC address.
* **Scale**: Clase hija que representa una balanza IoT utilizada en el negocio para poder gestionar el peso adecuado por unidad terrestre destinada a la experiencia turística.
* **Vibration and Shock Sensor**: Esta clase representa un sensor IoT utilizado para medir movimientos de los equipajes dirante el transcurso en el vehículo con principales funciones como registrar y mantener información específica del sensor.

## 5.3.2. Interface Layer. 
* **Scale Controller**: Es responsable de gestionar las solicitudes y las interacciones relacionadas con la balanza como coordinar con la Application Layer para ejecutar operaciones específicas en las balanzas, como tomar mediciones de peso y registrar datos.
* **Vibration and Shock Sensor**:  Se encarga de gestionar las solicitudes y las operaciones relacionadas con los sensores de vibración como validar los datos de entrada relacionados con los sensores  y coordinar con la capa de aplicación para obtener datos de movimientos específicos de los sensores.

## 5.3.3. Application Layer. 
* **Scale CommandHandler:** Este command handler se encarga de procesar comandos relacionados con las balanzas IoT, como comandos para realizar mediciones de peso, calibración de balanzas, etc.
* **Vibration and Shock Sensor CommandHandler:** Este handler procesa comandos relacionados con los sensores de vibración IoT, como comandos para obtener mediciones de vibraciones Cuando se recibe un comando relacionado con sensores de posibles choques, este handler toma las mediciones correspondientes, las valida y actualiza el estado de los sensores de vibraciones en la capa de dominio.

## 5.3.4. Infrastructure Layer.
* **IoT Asset Scale Application Service:** Este servicio de aplicación se encarga de coordinar las operaciones relacionadas con las balanzas IoT. Recibe las consultas de la capa de aplicacion y las valida para que pueda interactuar con el scale repository.
* **IoT Asset Vibration and Schock Sensor Application Service:**  Recibe solicitudes relacionadas con sensores vibraciones desde la capa de interfaz o la capa de aplicación. Asimismo, valida y procesa estas solicitudes, garantizando que se cumplan las reglas de negocio y la lógica específica de los sensores.
* **Scale Repository:**  Almacena y recupera información sobre las balanzas IoT, incluyendo su estado, configuración y mediciones registradas.
* **Vibration and Schock Sensor Repository:** Almacena y recupera datos de los sensores de virbaciones y choques.
## 5.3.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/iotcd.png" alt="iotcd" />
</div>

## 5.3.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.3.6.1. Bounded Context Domain Layer Class Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/class-diagrams/iot.png" alt="iot" />
</div>

## 5.3.6.2. Bounded Context Database Design Diagram. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/database-diagrams/iot.png" alt="iot" />
</div>

## 5.4. Bounded Context: Notification management 
Mediante el uso de este bounded context se abordan las clases y capas relacionadas con las notificaciones hacia los usuarios por parte del sistema. A continuación, se detallan los principales componentes de este Bounded:

## 5.4.1. Domain Layer. 
*  **Notification** : Esta clase representa la notificación que se enviara al usuario final, dentro de esta clase se encuentran atributos tales como : 
   - **message:** Este atributo representa el mensaje que será enviado al usuario
   -  **isEnable:** Este atributo representa un booleano, con este se puede saber si el usuario cuenta con las notificaciones activadas.
   -  **type:** Este atributo cuenta con los valores del enumerator **NotificationType**, representa que tipo de notificación  será enviada.
   -  **receiver:** Este atributo cuenta con los valores de la entidad **NotificationReceiver**, conteniendo la información necesaria para enviar la notificación  al usuario.
* **NotificationReceiver:** Esta clase representa el modelo que es necesario para poder obtener la información necesaria para enviar la notificación al usuario, como atributos tiene:
    - **name:** Atributo que representa el nombre del usuario al que se le enviara la notificación.
    - **email:** Correo al que se le enviara la notificación en caso sea necesario. 
### **Enum**:
* **NotificationType**: Representa el tipo de notificación que será enviada. Los tipos de notificaciones son los siguientes: 
    - **VIBRATION-SHOCK**      Representa las alertas de posibles caídas
    - **REGISTRATION:** Son las notificaciones del registro, estas serán enviadas por email
## 5.4.2. Interface Layer. 
* **Notification Controller:** Este controlador maneja las solicitudes relacionadas con las notificaciones vía correo y notificaciones móviles. Además, recopila los datos para luego almacenarlos en la base de datos.
  
## 5.4.3. Application Layer. 
- **VibrationShockNotificationCommandHandler:** Este CommandHandler gestiona las notificaciones de recomendaciones de vestimenta **(NotificationType.VIBRATION-SHOCK)**.
- **RegistrationNotificationCommandHandler:** Este CommandHandler se encarga de enviar notificaciones por correo electrónico del registro **(NotificationType.REGISTRATION)** al usuario final.

## 5.4.4. Infrastructure Layer. 
- **Notification Service:** Este servicio se encarga de gestionar el envío de notificaciones a través de diferentes canales, como correo electrónico o notificaciones móviles. Implementa la lógica para entregar las notificaciones al usuario final según las preferencias y la elección del canal.
- **Notification Repository** El repositorio de notificaciones almacena y gestiona las notificaciones enviadas. Esto incluye el seguimiento de qué notificaciones se han enviado, cuándo se enviaron y a quién se enviaron. Además, permite realizar consultas y búsquedas relacionadas con el historial de notificaciones.
  
## 5.4.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/notcd.png" alt="notcd" />
</div>

## 5.4.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.4.6.1. Bounded Context Domain Layer Class Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/class-diagrams/not.png" alt="iot" />
</div>

## 5.4.6.2. Bounded Context Database Design Diagram. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/database-diagrams/not.png" alt="iot" />
</div>

## 5.5. Bounded Context: Subscription and payments 
## 5.5.1. Domain Layer.
#### Entities:

* **Subscription**: Esta entidad representa una suscripción en el sistema. Tiene atributos como ID de suscripción, fecha de inicio, fecha de vencimiento y métodos para gestionar la suscripción, como renovarla o cancelarla.

* **Payment**: La entidad Payment modela los pagos realizados en el sistema. Contiene información sobre el ID de pago, el monto, la fecha y otros detalles relevantes. También incluye métodos para registrar y procesar pagos.

#### Object Values:

* **PaymentHistory**: Este object value almacena el historial de pagos asociado a una suscripción. Contiene detalles como las fechas de los pagos anteriores, el estado de los pagos y otros datos relacionados con el historial de pagos.

#### Aggregates:

* **SubscriptionAggregate**: Este aggregate agrupa la entidad de Suscripción (Subscription) y el historial de pagos (PaymentHistory) relacionado. Define las reglas de negocio que garantizan la consistencia entre suscripciones y pagos.
#### Enumeraciones:

* **PaymentStatus**: Esta enumeración representa el estado de un pago, incluyendo valores como "Procesado" o "Fallido". Se utiliza para rastrear el estado de los pagos en el sistema.

## 5.5.2. Interface Layer. 
* **Payment Controller**: El controlador Payment maneja las solicitudes relacionadas con los pagos. Proporciona endpoints,registrar historiales de pagos y gestionar la interacción con los usuarios en términos de suscripciones y pagos.

* **Subscription Controller**: El controlador Subscription se encarga de las solicitudes relacionadas con las suscripciones. Ofrece endpoints para crear, renovar y cancelar suscripciones, así como para administrar el estado de las suscripciones de los usuarios.

## 5.5.3. Application Layer. 
* **Purchase Subscription Command Handler**: Este Command Handler se encarga de procesar las solicitudes de compra de suscripciones. Recibe comandos de compra de suscripción desde el Interface Layer y coordina la creación y activación de las suscripciones en el Domain Layer. Además, gestiona la facturación y los registros de pagos relacionados con las suscripciones adquiridas.

* **Renew Subscription Command Handler**: El Command Handler de renovación de suscripciones maneja las solicitudes para extender la duración de una suscripción existente. Al recibir un comando de renovación de suscripción, este handler interactúa con el Domain Layer para actualizar las fechas de vencimiento y gestionar los pagos asociados a la renovación.

* **Payment Process Command Handler**: El Command Handler de procesamiento de pagos administra las solicitudes relacionadas con el procesamiento de pagos. Recibe comandos para procesar pagos y se comunica con el Domain Layer para registrar los pagos exitosos y gestionar los casos de pagos fallidos.

## 5.5.4. Infrastructure Layer. 
* **Subscription Repository**: Este repositorio se encarga de la persistencia de datos relacionados con las suscripciones de usuarios. Almacena información sobre las suscripciones activas, su estado y fechas de vencimiento. Facilita la consulta y actualización de datos de suscripciones.

* **Payment Gateway Adapter**: Este adaptador se conecta con un servicio externo de pasarela de pago mediante nuestro payment gateway.

* **Logging Service**: Proporciona registros para auditoría, seguimiento y resolución de problemas. Captura información sobre pagos procesados, interacciones de usuarios y eventos críticos.

## 5.5.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/subcd.png" alt="subcd" />
</div>

## 5.5.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.5.6.1. Bounded Context Domain Layer Class Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/class-diagrams/sub.png" alt="subscription" />
</div>

## 5.5.6.2. Bounded Context Database Design Diagram. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/database-diagrams/sub.png" alt="subscription" />
</div>

## 5.6. Bounded Context: Tour Package Management 
## 5.6.1. Domain Layer. 
- **TourPackage:** Esta clase representa el paquete turistico ingresado por el segmento de agencia y contiene atributos como inicio, destino, precio, paradas, agencia ID, medios de pago.

## 5.6.2. Interface Layer. 
- **TourPackageController:** Este controlador se encarga de las solicitudes de actualización de información de paquetes turísticos. Facilita a las agencias un listado de las disponibles segun sus filtros indicados. Permite a las agencias crear, modificar o eliminar sus paquetes turísticos propios.
  
## 5.6.3. Application Layer. 
- **TourPackageService:** Se encarga de procesar las solicitudes de actualización de paquetes turísticos. Valida los cambios propuestos por el usuario, actualiza los datos en la base de datos y registra la actividad correspondiente en el perfil.

## 5.6.4. Infrastructure Layer. 
- **TourPackageRepository:** Almacena y recupera la configuración de los paquetes turísticos.
## 5.6.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/tourcd.png" alt="tourcd" />
</div>

## 5.6.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.6.6.1. Bounded Context Domain Layer Class Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/class-diagrams/tour.png" alt="tour" />
</div>

## 5.6.6.2. Bounded Context Database Design Diagram. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/database-diagrams/tour.png" alt="tour" />
</div>

## 5.7. Bounded Context: Transportation Management 
## 5.7.1. Domain Layer. 
- **Vehicle:** Esta clase representa el el vehiculo contiene el peso minimo, recomnedado, marca, asientos, tamaño, conductor.

## 5.7.2. Interface Layer. 
- **VehicleController:** Este controlador se encarga de las solicitudes de administrar los vehículos usados para los paquetes turísticos, controlarán el peso del equipaje.
## 5.7.3. Application Layer. 
- **VehicleService:** Se encarga de procesar las solicitudes de actualización de vehículos, añadir gps, añadir usuarios, modificar peso.
## 5.7.4. Infrastructure Layer. 
- **VehicleRepository:** Almacena y recupera la configuración de todos los vehículos usados en la actualidad y posteriormente por las agencias.
## 5.7.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/transportcd.png" alt="transportcd" />
</div>

## 5.7.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.7.6.1. Bounded Context Domain Layer Class Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/class-diagrams/transport.png" alt="transport" />
</div>

## 5.7.6.2. Bounded Context Database Design Diagram. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/database-diagrams/transport.png" alt="transport" />
</div>