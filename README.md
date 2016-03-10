# Monguinho

Estudando monguinho

#Instalação

`
brew install mongodb
`

#Listar todos os bancos

`
show dbs
`

#Comandos CRUD

Create:
```javascript
// save one user
$ db.users.save({ name: 'Chris' });

// save multiple users
$ db.users.save([{ name: 'Chris'}, { name: 'Holly' }]);
```

Read:
```javascript
// show all users
$ db.users.find();

// find a specific user
$ db.users.find({ name: 'Holly' });
```

Update:
```javascript
db.users.update({ name: 'Holly' }, { name: 'Holly Lloyd' });
```

Delete:
```javascript
// remove all
db.users.remove({});

// remove one
db.users.remove({ name: 'Holly' });
```

#Fontes

[an-introduction-to-mongodb](https://scotch.io/tutorials/an-introduction-to-mongodb)
