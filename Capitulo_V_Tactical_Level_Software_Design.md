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
## 5.3.2. Interface Layer. 
## 5.3.3. Application Layer. 
## 5.3.4. Infrastructure Layer. 
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
## 5.4.1. Domain Layer. 
## 5.4.2. Interface Layer. 
## 5.4.3. Application Layer. 
## 5.4.4. Infrastructure Layer. 
## 5.4.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/notcd.png" alt="notcd" />
</div>

## 5.4.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.4.6.1. Bounded Context Domain Layer Class Diagrams. 
## 5.4.6.2. Bounded Context Database Design Diagram. 

## 5.5. Bounded Context: Subscription and payments 
## 5.5.1. Domain Layer. 
## 5.5.2. Interface Layer. 
## 5.5.3. Application Layer. 
## 5.5.4. Infrastructure Layer. 
## 5.5.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/subcd.png" alt="subcd" />
</div>

## 5.5.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.5.6.1. Bounded Context Domain Layer Class Diagrams. 
## 5.5.6.2. Bounded Context Database Design Diagram. 

## 5.6. Bounded Context: Tour Package Management 
## 5.6.1. Domain Layer. 
## 5.6.2. Interface Layer. 
## 5.6.3. Application Layer. 
## 5.6.4. Infrastructure Layer. 
## 5.6.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/tourcd.png" alt="tourcd" />
</div>

## 5.6.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.6.6.1. Bounded Context Domain Layer Class Diagrams. 
## 5.6.6.2. Bounded Context Database Design Diagram. 

## 5.7. Bounded Context: Transportation Management 
## 5.7.1. Domain Layer. 
## 5.7.2. Interface Layer. 
## 5.7.3. Application Layer. 
## 5.7.4. Infrastructure Layer. 
## 5.7.5. Bounded Context Software Architecture Component Level Diagrams. 
<div align="center">
  <img src="https://raw.githubusercontent.com/GoCaseGo-Arquitectura-Emergentes/upc-pre-202401-si728-sw82-GoCaseGo-report/develop/Resources/c4-model/transportcd.png" alt="transportcd" />
</div>

## 5.7.6. Bounded Context Software Architecture Code Level Diagrams. 
## 5.7.6.1. Bounded Context Domain Layer Class Diagrams. 
## 5.7.6.2. Bounded Context Database Design Diagram. 
