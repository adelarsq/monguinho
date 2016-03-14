# Monguinho

Neste documento são mostrados os aspectos iniciais do [MongoDB](https://www.mongodb.org/). MongoDB é um banco livre, baseado em documentos para fácil desenvolvimento e escalável. Atualmente é um dos melhores bancos NoSQL disponíveis no mercado. Possui suporte a diversas linguagens, tais como [Javascript](https://docs.mongodb.org/getting-started/node), [Python](https://docs.mongodb.org/getting-started/python), [C++](https://docs.mongodb.org/getting-started/cpp), [Java](https://docs.mongodb.org/getting-started/java) e [C#](https://docs.mongodb.org/getting-started/csharp).


##Instalação

Antes de efetuar a instalação verifique no link https://docs.mongodb.org/manual/installation/ se a sua plataforma é suportada. Nesta mesma página se encontram os passos para instalar em cada página. Normalmente a instalação é simplesmente a chamada do gerenciador e pacotes ou a execução do instalador. Por exemplo, a seguir é mostrado como é efetuada a instalação em OSX utilizando [brew](http://brew.sh/):

`
brew install mongodb
`

## Mongo Shell

Como a maioria dos bancos é oferecida uma interface de comunicação estilo REPL. Para mais informaçõe acesse https://docs.mongodb.org/manual/mongo/.

## Comandos básicos

###Listar todos os bancos

`
show dbs
`

###Usar uma base

`
use database
`

###Comandos CRUD

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

##Fontes

- [Manual oficial](https://docs.mongodb.org/manual/)
- [An Introduction to MongoDB](https://scotch.io/tutorials/an-introduction-to-mongodb)
