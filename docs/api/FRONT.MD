# FROM API Reference

## Header Params (General)

| Parameter      | Type     | Description                |
| :------------- | :------- | :------------------------- |
| `access-token` | `string` | **Required**. Your API key |
| `token-type`   | `string` | **Required**. Bearer       |
| `client`       | `string` | **Required**.              |
| `expiry`       | `string` | **Required**.              |
| `uid`          | `string` | **Required**.              |

---

## **Orders**

## **Get all orders**

```http
  GET /front/v1/orders
```

| Parameter | Type     | Description          |
| :-------- | :------- | :------------------- |
| `search`  | `string` | Search parameter     |
| `status`  | `string` | Filter Status(0,1,2) |

> **search -** Deve buscar pelos campos:
>
> * Id pedido
> * Nome Cliente
> * Mesa

> **status -** Deve receber um array com os status [0,1,2]

Returns:

* 200

```json
{
  "orders": [
    {
      "id": 1,
      "name": "Customer name",
      "table_number": 32,
      "order_date": "2021-07-01T18:25:43.511Z",
      "status": 0,
      "employee": {
        "id": 1,
        "name": "Waiter Walt"
      },
      "items": [{
          "id": 100,
          "quantity": 1,
          "comment": "Sem cebola",
          "product": {
            "id": 1,
            "name": "Lanchão",
            "description": "2 pãos, tomate, cebolar e tudo mais",
            "category": {
              "id": 1,
              "nome": "Lanches"
            }
          }
        },
        {
          "id": 101,
          "quantity": 1,
          "comment": "",
          "product": {
            "id": 10,
            "name": "Coca Cola 2 litros",
            "description": "Coca cola",
            "category": {
              "id": 1,
              "nome": "Bebidas"
            }
          }
        }
      ]
    }
  ]
}
```

## **Get a order by ID**

```http
  GET /front/v1/orders/:id
```

| Parameter | Type  | Description            |
| :-------- | :---- | :--------------------- |
| `id`      | `int` | **Required**. Id Order |

Returns:

* 200

```json
{
  "id": 1,
  "name": "Customer name",
  "table_number": 32,
  "order_date": "2021-07-01T18:25:43.511Z",
  "status": 0,
  "employee": {
    "id": 1,
    "name": "Waiter Walt"
  },
  "items": [{
      "id": 100,
      "quantity": 1,
      "comment": "Sem cebola",
      "product": {
        "id": 1,
        "name": "Lanchão",
        "description": "2 pãos, tomate, cebolar e tudo mais",
        "category": {
          "id": 1,
          "nome": "Lanches"
        }
      }
    },
    {
      "id": 101,
      "quantity": 1,
      "comment": "",
      "product": {
        "id": 10,
        "name": "Coca Cola 2 litros",
        "description": "Coca cola",
        "category": {
          "id": 1,
          "nome": "Bebidas"
        }
      }
    }
  ]
}
```

## **Create an order**

```http
  POST /front/v1/orders
```

Request body:

```json
{
  "id": 1,
  "name": "Customer name",
  "table_number": 32,
  "employee_id": 1,
  "items": [
    {
      "product_id": 1,
      "quantity": 1,
      "comment": "Sem cebola"
    },
    {
      "product_id": 10,
      "quantity": 1,
      "comment": ""
    }
  ]
}
```

Returns:

* 200

```json
{
  "id": 1,
  "name": "Customer name",
  "table_number": 32,
  "order_date": "2021-07-01T18:25:43.511Z",
  "status": 0,
  "employee": {
    "id": 1,
    "name": "Waiter Walt"
  },
  "items": [{
      "id": 100,
      "quantity": 1,
      "comment": "Sem cebola",
      "product": {
        "id": 1,
        "name": "Lanchão",
        "description": "2 pãos, tomate, cebolar e tudo mais",
        "category": {
          "id": 1,
          "nome": "Lanches"
        }
      }
    },
    {
      "id": 101,
      "quantity": 1,
      "comment": "",
      "product": {
        "id": 10,
        "name": "Coca Cola 2 litros",
        "description": "Coca cola",
        "category": {
          "id": 1,
          "nome": "Bebidas"
        }
      }
    }
  ]
}
```

## **Cancel an order**

```http
  DELETE /front/v1/orders/:id
```

Returns:

* 204: No content

## **Update order status**

```http
  PATCH /front/v1/orders/:id/status
```

| Parameter | Type  | Description            |
| :-------- | :---- | :--------------------- |
| `id`      | `int` | **Required**. Id Order |

Request body:

```json
{
  "status": "2"
}
```

Returns:

* 200

```json
{
  "id": 1,
  "name": "Customer name",
  "table_number": 32,
  "order_date": "2021-07-01T18:25:43.511Z",
  "status": 0,
  "employee": {
    "id": 1,
    "name": "Waiter Walt"
  },
  "items": [{
      "id": 100,
      "quantity": 1,
      "comment": "Sem cebola",
      "product": {
        "id": 1,
        "name": "Lanchão",
        "description": "2 pãos, tomate, cebolar e tudo mais",
        "category": {
          "id": 1,
          "nome": "Lanches"
        }
      }
    },
    {
      "id": 101,
      "quantity": 1,
      "comment": "",
      "product": {
        "id": 10,
        "name": "Coca Cola 2 litros",
        "description": "Coca cola",
        "category": {
          "id": 1,
          "nome": "Bebidas"
        }
      }
    }
  ]
}
```

---

## **Product**

## **Get all products**

```http
  GET /front/v1/products
```

| Parameter | Type     | Description   |
| :-------- | :------- | :------------ |
| `search`  | `string` | Search params |

> **search params -** Deve buscar pelos campos:
>
> * Nome da categoria
> * Nome da produto
> * Descrição do produto

Returns:

* 200

```json
{
  "categories": [
    {
      "id": 1,
      "name": "Bebidas",
      "products": [
        {
          "id": 1,
          "name": "Coca cola lata",
          "description": "Coca cola lata",
          "price": 5.00
        },
        {
          "id": 2,
          "name": "Coca cola 2 L",
          "description": "Coca cola 2 L",
          "price": 12.00
        }
      ]
    },
    {
      "id": 2,
      "name": "Lanches",
      "products": [
        {
          "id": 3,
          "name": "X-TUDO",
          "description": "X-TUDO",
          "price": 25.00
        },
        {
          "id": 4,
          "name": "Cachorro quente",
          "description": "Cachorro quente",
          "price": 15.00
        }
      ]
    }
  ]
}
```

## **Get a product by ID**

```http
  GET /front/v1/products/:id
```

| Parameter | Type  | Description              |
| :-------- | :---- | :----------------------- |
| `id`      | `int` | **Required**. Id Product |

Returns:

* 200

```json
{
  "id": 4,
  "name": "Cachorro quente",
  "description": "Cachorro quente",
  "price": 15.00,
  "category": {
    "id": 1,
    "name": "Category name"
  }
}
```
