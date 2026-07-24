# Clase 02 - Introducción a MongoDB

## Levantar el servidor de base ed datos

```sh
mongod
```

## Conectarse al motor de base de datos

```sh
mongosh
```

## Listar las bases de datos

```sh
show dbs // show databases 
```

## Crear o seleccionar una DB

```js
use <nombre-db>
use <mongo_87347>
```

## Crear una colección

```js
db.createCollection('<nombre-de-la-colección') // El nombre de las colecciones debe ser un sustantivo en plural. Usar snake_case en caso de que el nombre de la colección tenga 2 o más palabras.
db.createCollection('productos')
```

## Crear un documento

```js
db.<colección>.insertOne({})
db.productos.insertOne(
    { 
        nombre: 'PC', 
        categoria: 'Informatica', 
        precio: 253 
        }
    )
// -------------
{
  acknowledged: true,
  insertedId: ObjectId('6a63ab2e803f336fe631147a') // identificador únicpp
}
```

## Crear uno o más documentos

```js
db.<colección>.insertMany([{},{},{}])
db.productos.insertMany(
    [
        {
            nombre: 'Tablet',
            categoria: 'Electro',
            precio: 123
        },
        {
            nombre: 'Celular',
            categoria: 'Electro',
            precio: 212
        },
        {
            nombre: 'Parlante',
            categoria: 'Audio',
            precio: 105
        }
    ]
)
// -------------
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('6a63ace5803f336fe631147b'),
    '1': ObjectId('6a63ace5803f336fe631147c'),
    '2': ObjectId('6a63ace5803f336fe631147d')
  }
}
```

# Listar elementos (documentos) dentro de una colección

```js
db.<nombre-colección>.find({})
db.productos.find() // db.productos.find({})
```

# Filtrar o buscar elementos en particular

```js
db.<nombre-colección>.find({ field: '' })
db.productos.find({
    nombre: 'PC'
}) 
```
