![GitHub Logo](/mongodb.png)

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

### Inserindo documentos

```javascript
db.ships.insert({name:'USS Enterprise-D',operator:'Starfleet',type:'Explorer',class:'Galaxy',crew:750,codes:[10,11,12]})
db.ships.insert({name:'USS Prometheus',operator:'Starfleet',class:'Prometheus',crew:4,codes:[1,14,17]})
db.ships.insert({name:'USS Defiant',operator:'Starfleet',class:'Defiant',crew:50,codes:[10,17,19]})
db.ships.insert({name:'IKS Buruk',operator:' Klingon Empire',class:'Warship',crew:40,codes:[100,110,120]})
db.ships.insert({name:'IKS Somraw',operator:' Klingon Empire',class:'Raptor',crew:50,codes:[101,111,120]})
db.ships.insert({name:'Scimitar',operator:'Romulan Star Empire',type:'Warbird',class:'Warbird',crew:25,codes:[201,211,220]})
db.ships.insert({name:'Narada',operator:'Romulan Star Empire',type:'Warbird',class:'Warbird',crew:65,codes:[251,251,220]})
````

### Procurando documentos

```javascript
db.ships.findOne() 
db.ships.find().prettyPrint() 
db.ships.find({}, {name:true, _id:false}) 
db.ships.findOne({'name':'USS Defiant'}) 
```

### Procurando documentos com operadores

```javascript
// $gt / $gte - greater than / greater than equals
db.ships.find({class:{$gt:’P'}})

// $lt / $lte - lesser than / lesser than equals
db.ships.find({class:{$lte:’P'}})

// $exists - does an attribute exist or not
db.ships.find({type:{$exists:true}})

// $regex - Perl-style pattern matching
db.ships.find({name:{$regex:’^USS\\sE’}})

// $type - search by type of an element
db.ships.find({name : {$type:2}}) 
```

### Atualizando documentos

```javascript
// Replaces the whole document
db.ships.update({name : 'USS Prometheus'}, {name : 'USS Something'})

// sets / changes certain attributes of a given document
db.ships.update({name : 'USS Something'}, {$set : {operator : 'Starfleet', class : 'Prometheus'}})

// removes an attribute from a given document
db.ships.update({name : 'USS Something'}, {$unset : {operator : 1}})
```

##Fontes

- [Manual oficial](https://docs.mongodb.org/manual/)
- [An Introduction to MongoDB](https://scotch.io/tutorials/an-introduction-to-mongodb)
