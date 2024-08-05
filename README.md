

### Códigos de Estado de Respuesta HTTP

#### 1xx - Información
- **100 Continue**: El servidor ha recibido la solicitud y el cliente puede continuar con la solicitud.
- **101 Switching Protocols**: El servidor acepta cambiar el protocolo según la solicitud del cliente.

#### 2xx - Éxito
- **200 OK**: La solicitud ha tenido éxito.
- **201 Created**: La solicitud ha sido cumplida y se ha creado un nuevo recurso.
- **202 Accepted**: La solicitud ha sido aceptada para procesamiento, pero no ha sido completada.
- **203 Non-Authoritative Information**: La solicitud ha tenido éxito, pero la información devuelta puede no ser la del servidor original.
- **204 No Content**: La solicitud ha tenido éxito, pero no hay contenido que devolver.
- **205 Reset Content**: La solicitud ha tenido éxito, y el cliente debe reiniciar la vista del documento.
- **206 Partial Content**: El servidor está enviando solo una parte del recurso solicitado.

#### 3xx - Redirección
- **300 Multiple Choices**: Hay varias opciones para el recurso solicitado.
- **301 Moved Permanently**: El recurso solicitado ha sido movido permanentemente a una nueva URL.
- **302 Found**: El recurso solicitado ha sido encontrado en una URL diferente, pero se debería usar la URL original para futuras solicitudes.
- **303 See Other**: La respuesta a la solicitud puede encontrarse en otra URL.
- **304 Not Modified**: El recurso no ha sido modificado desde la última solicitud.
- **305 Use Proxy**: El recurso debe ser accedido a través de un proxy especificado.
- **307 Temporary Redirect**: El recurso solicitado se encuentra temporalmente en una URL diferente.
- **308 Permanent Redirect**: El recurso solicitado ha sido movido permanentemente a una URL diferente.

#### 4xx - Error del Cliente
- **400 Bad Request**: La solicitud no puede ser procesada debido a un error del cliente (por ejemplo, sintaxis incorrecta).
- **401 Unauthorized**: La solicitud requiere autenticación del usuario.
- **402 Payment Required**: Código reservado para futuras necesidades (por ejemplo, pagos).
- **403 Forbidden**: El servidor ha comprendido la solicitud, pero se niega a autorizarla.
- **404 Not Found**: El recurso solicitado no se encuentra en el servidor.
- **405 Method Not Allowed**: El método de solicitud no está permitido para el recurso solicitado.
- **406 Not Acceptable**: El recurso solicitado no es aceptable según los encabezados de la solicitud.
- **407 Proxy Authentication Required**: Se requiere autenticación con el proxy.
- **408 Request Timeout**: El servidor ha agotado el tiempo de espera para la solicitud del cliente.
- **409 Conflict**: La solicitud no pudo ser completada debido a un conflicto con el estado actual del recurso.
- **410 Gone**: El recurso solicitado ha sido eliminado permanentemente.
- **411 Length Required**: Se requiere el encabezado `Content-Length` en la solicitud.
- **412 Precondition Failed**: Una o más condiciones dadas en los encabezados de la solicitud han fallado.
- **413 Payload Too Large**: La solicitud es demasiado grande para que el servidor la procese.
- **414 URI Too Long**: La URI proporcionada es demasiado larga para que el servidor la procese.
- **415 Unsupported Media Type**: El tipo de medio de la solicitud no es soportado por el servidor.
- **416 Range Not Satisfiable**: El rango solicitado no puede ser satisfecho.
- **417 Expectation Failed**: La expectativa dada en el encabezado de la solicitud no puede ser cumplida por el servidor.

#### 5xx - Error del Servidor
- **500 Internal Server Error**: El servidor encontró una condición inesperada que impidió la solicitud.
- **501 Not Implemented**: El servidor no reconoce el método de solicitud o no lo puede implementar.
- **502 Bad Gateway**: El servidor actuó como una puerta de enlace o proxy y recibió una respuesta inválida del servidor de origen.
- **503 Service Unavailable**: El servidor no está disponible temporalmente (por ejemplo, sobrecargado o en mantenimiento).
- **504 Gateway Timeout**: El servidor actuó como una puerta de enlace o proxy y no recibió una respuesta a tiempo del servidor de origen.
- **505 HTTP Version Not Supported**: El servidor no soporta la versión del protocolo HTTP utilizada en



# Operadores de Sequelize

`Op` es un objeto en Sequelize que contiene varios operadores de comparación que puedes usar en tus consultas. Aquí hay una lista de algunos operadores comunes y sus usos:

- **Op.eq**: Igual a (=).
- **Op.ne**: No igual a (!=).
- **Op.gt**: Mayor que (>).
- **Op.gte**: Mayor o igual que (>=).
- **Op.lt**: Menor que (<).
- **Op.lte**: Menor o igual que (<=).
- **Op.between**: Entre un rango de valores.
- **Op.notBetween**: No entre un rango de valores.
- **Op.in**: En un conjunto de valores.
- **Op.notIn**: No en un conjunto de valores.
- **Op.like**: Similar a (usado para patrones de búsqueda).
- **Op.notLike**: No similar a.
- **Op.iLike**: Similar a (insensible a mayúsculas/minúsculas, solo para PostgreSQL).
- **Op.notILike**: No similar a (insensible a mayúsculas/minúsculas, solo para PostgreSQL).
- **Op.startsWith**: Comienza con.
- **Op.endsWith**: Termina con.
- **Op.substring**: Contiene.
- **Op.regexp**: Coincide con una expresión regular (solo para PostgreSQL).
- **Op.notRegexp**: No coincide con una expresión regular (solo para PostgreSQL).
- **Op.iRegexp**: Coincide con una expresión regular insensible a mayúsculas/minúsculas (solo para PostgreSQL).
- **Op.notIRegexp**: No coincide con una expresión regular insensible a mayúsculas/minúsculas (solo para PostgreSQL).

## Ejemplos de uso

### Op.eq y Op.ne

```javascript
const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.eq]: 100 // Igual a 100
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.ne]: 100 // No igual a 100
        }
    }
});


Op.eq y Op.ne
const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.eq]: 100 // Igual a 100
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.ne]: 100 // No igual a 100
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.gt]: 50 // Mayor que 50
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.gte]: 50 // Mayor o igual que 50
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.lt]: 200 // Menor que 200
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.lte]: 200 // Menor o igual que 200
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.between]: [50, 200] // Entre 50 y 200
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        quantity: {
            [Op.notBetween]: [50, 200] // No entre 50 y 200
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        status: {
            [Op.in]: ['available', 'reserved'] // En el conjunto ['available', 'reserved']
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        status: {
            [Op.notIn]: ['sold', 'damaged'] // No en el conjunto ['sold', 'damaged']
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        name: {
            [Op.like]: '%medicine%' // Similar a '%medicine%'
        }
    }
});

const inventories = await InventoryModel.findAll({
    where: {
        name: {
            [Op.notLike]: '%expired%' // No similar a '%expired%'
        }
    }
});


# Métodos de Sequelize

Sequelize ofrece una variedad de métodos para interactuar con tu base de datos. Aquí hay una lista de los métodos más comunes, sus usos, y ejemplos de cómo utilizarlos:

## findOne
Busca una sola entrada que coincida con los criterios.


const user = await UserModel.findOne({ where: { username: 'john_doe' } });
findAll
Busca todas las entradas que coincidan con los criterios.

javascript
Copiar código
const users = await UserModel.findAll({ where: { status: 'active' } });
findByPk
Busca una entrada por su clave primaria.

javascript
Copiar código
const user = await UserModel.findByPk(1); // Busca el usuario con ID 1
create
Crea una nueva entrada.

javascript
Copiar código
const newUser = await UserModel.create({ username: 'jane_doe', email: 'jane@example.com' });
update
Actualiza las entradas que coincidan con los criterios.

javascript
Copiar código
await UserModel.update({ status: 'inactive' }, { where: { lastLogin: { [Op.lt]: new Date() } } });
destroy
Elimina las entradas que coincidan con los criterios.

javascript
Copiar código
await UserModel.destroy({ where: { status: 'inactive' } });
count
Cuenta el número de entradas que coincidan con los criterios.

javascript
Copiar código
const count = await UserModel.count({ where: { status: 'active' } });
findOrCreate
Busca una entrada y la crea si no existe.

javascript
Copiar código
const [user, created] = await UserModel.findOrCreate({
  where: { username: 'john_doe' },
  defaults: { email: 'john@example.com' }
});
bulkCreate
Crea múltiples entradas en una sola operación.

javascript
Copiar código
const users = await UserModel.bulkCreate([
  { username: 'user1', email: 'user1@example.com' },
  { username: 'user2', email: 'user2@example.com' }
]);
upsert
Inserta o actualiza una entrada.

javascript
Copiar código
const user = await UserModel.upsert({ id: 1, username: 'john_doe', email: 'john_updated@example.com' });
Estos métodos te permiten realizar una amplia variedad de operaciones en tu base de datos de manera eficiente y con un código limpio y organizado.

### Códigos de Estado HTTP Más Comunes

#### 1xx - Información
- **100 Continue**: Indica que el servidor ha recibido la parte inicial de la solicitud y el cliente puede continuar con el resto.

#### 2xx - Éxito
- **200 OK**: La solicitud ha sido procesada con éxito y se ha devuelto el resultado.
- **201 Created**: La solicitud ha sido procesada y se ha creado un nuevo recurso.
- **204 No Content**: La solicitud ha tenido éxito, pero no hay contenido que devolver.

#### 3xx - Redirección
- **301 Moved Permanently**: El recurso solicitado se ha movido permanentemente a una nueva URL.
- **302 Found**: El recurso solicitado se encuentra temporalmente en una URL diferente.
- **304 Not Modified**: El recurso no ha sido modificado desde la última solicitud, por lo que el cliente puede usar la versión en caché.

#### 4xx - Error del Cliente
- **400 Bad Request**: La solicitud no se puede procesar debido a un error del cliente.
- **401 Unauthorized**: Se requiere autenticación para acceder al recurso.
- **403 Forbidden**: El servidor ha comprendido la solicitud pero se niega a autorizarla.
- **404 Not Found**: El recurso solicitado no se encuentra en el servidor.

#### 5xx - Error del Servidor
- **500 Internal Server Error**: El servidor encontró un error inesperado que impidió completar la solicitud.
- **502 Bad Gateway**: El servidor recibió una respuesta inválida de un servidor al que actuaba como puerta de enlace.
- **503 Service Unavailable**: El servidor no está disponible temporalmente (por ejemplo, por sobrecarga o mantenimiento).



### Ejemplo de Definición de Modelos en Sequelize con Dependencias Circulares

#### 1. Configuración de Sequelize

```javascript
// config/database.js
const { Sequelize } = require('sequelize');

const sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: 'mysql', // O el dialecto que estés usando
});

module.exports = sequelize;
```

#### 2. Definición de Modelos

```javascript
// models/User.js
const { DataTypes } = require('sequelize');
const sequelize = require('../config/database');
const Profile = require('./Profile');
const Post = require('./Post');

// Definir el modelo User
const User = sequelize.define('User', {
  name: {
    type: DataTypes.STRING,
    allowNull: false,
  },
  email: {
    type: DataTypes.STRING,
    allowNull: false,
    unique: true,
  },
});

// Relación uno a uno con Profile
User.hasOne(Profile, { foreignKey: 'userId' });
Profile.belongsTo(User, { foreignKey: 'userId' });

// Relación uno a muchos con Post
User.hasMany(Post, { foreignKey: 'userId' });
Post.belongsTo(User, { foreignKey: 'userId' });

module.exports = User;
```

```javascript
// models/Profile.js
const { DataTypes } = require('sequelize');
const sequelize = require('../config/database');

// Definir el modelo Profile
const Profile = sequelize.define('Profile', {
  bio: {
    type: DataTypes.TEXT,
    allowNull: true,
  },
  website: {
    type: DataTypes.STRING,
    allowNull: true,
  },
});

module.exports = Profile;
```

```javascript
// models/Post.js
const { DataTypes } = require('sequelize');
const sequelize = require('../config/database');
const Tag = require('./Tag');

// Definir el modelo Post
const Post = sequelize.define('Post', {
  title: {
    type: DataTypes.STRING,
    allowNull: false,
  },
  content: {
    type: DataTypes.TEXT,
    allowNull: false,
  },
});

// Relación muchos a muchos con Tag
Post.belongsToMany(Tag, { through: 'PostTags' });
Tag.belongsToMany(Post, { through: 'PostTags' });

module.exports = Post;
```

```javascript
// models/Tag.js
const { DataTypes } = require('sequelize');
const sequelize = require('../config/database');

// Definir el modelo Tag
const Tag = sequelize.define('Tag', {
  name: {
    type: DataTypes.STRING,
    allowNull: false,
  },
});

module.exports = Tag;
```

#### 3. Sincronización de la Base de Datos

```javascript
// sync.js
const sequelize = require('./config/database');
const User = require('./models/User');
const Profile = require('./models/Profile');
const Post = require('./models/Post');
const Tag = require('./models/Tag');

const syncDatabase = async () => {
  try {
    await sequelize.sync({ force: true }); // Esto borrará y recreará las tablas
    console.log('Database synchronized');
  } catch (error) {
    console.error('Error synchronizing database:', error);
  }
};

syncDatabase();
```

### Explicación de Relaciones

- **User y Profile**: Relación uno a uno. Cada usuario tiene un perfil asociado.
- **User y Post**: Relación uno a muchos. Cada usuario puede tener múltiples publicaciones.
- **Post y Tag**: Relación muchos a muchos. Cada publicación puede tener múltiples etiquetas y cada etiqueta puede estar asociada a múltiples publicaciones.

Este ejemplo debería darte una buena base para trabajar con dependencias circulares y relaciones en Sequelize. ¡Si necesitas más detalles o tienes alguna pregunta, avísame!


