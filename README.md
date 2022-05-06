# json-server-base

Esse é o repositório com a base de JSON-Server + JSON-Server-Auth já configurada, feita para ser usada no desenvolvimento das API's nos Capstones do Q2.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### **Cadastro**

POST /register <br/>
POST /signup <br/>
POST /users

Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password.
Você pode ficar a vontade para adicionar qualquer outra propriedade no corpo do cadastro dos usuários.

### **Login**

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### **Pelúcias**

_POST_ /plushies

Essa Endpoint é usada para acrescentar pelúcias na lista "Plushies". O usuário deve estar logado para conseguir adicionar à lista, mas todos conseguem vê-la:

```javascript
{
    "name": "Turtle",
    "userId": 1 //obrigatório
	"price": 13,
	"category": "Animals",
}
```

E a resposta no caso de sucesso na requisição é:

```javascript
{
    "name": "Turtle",
    "userId": 1,
    "price": 13,
    "category": "Animals",
    "id": 3
}
```

_GET_ /plushies

Acessa a lista de pelúcias, retornando um array de objetos. disponível para visualização pública.

### **Lista de Desejos**

_POST_ /wishList

Essa Endpoint é usada para acrescentar pelúcias na lista "wishList". O usuário deve estar logado para conseguir adicionar à lista e para vê-la:

```javascript
{
    "name": "Turtle",
    "userId": 1 //obrigatório
	"price": 13,
	"category": "Animals",
}
```

E a resposta no caso de sucesso na requisição é:

```javascript
{
    "name": "Turtle",
    "userId": 1,
    "price": 13,
    "category": "Animals",
    "id": 3
}
```

_GET_ /whishList?userId=1

Acessa a lista de desejos do usuários cujo id está sendo passado, apenas usuários logados possuem acesso.
