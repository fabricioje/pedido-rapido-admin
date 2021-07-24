# ADMIN API Reference

## Header Params (General)

| Parameter      | Type     | Description                |
| :------------- | :------- | :------------------------- |
| `access-token` | `string` | **Required**. Your API key |
| `token-type`   | `string` | **Required**. Bearer       |
| `client`       | `string` | **Required**.              |
| `expiry`       | `string` | **Required**.              |
| `uid`          | `string` | **Required**.              |

---

## **Category**

## **Get all categories**

```http
  GET /api/v1/categories
```

Returns:

* 200

```json
{
  "categories": [
    {
      "id": 1,
      "name": "Category 1"
    },
    {
      "id": 2,
      "name": "Category 2"
    }
  ]
}
```

## **Get a category by ID**

```http
  GET /api/v1/categories/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Category |

Returns:

* 200

```json
{
  "id": 1,
  "name": "Category 1"
}
```

## **Create a category**

```http
  POST /api/v1/categories
```

Request body:
```json
{
  "name": "Created Category"
}
```

Returns:

* 200

```json
{
  "id": 10,
  "name": "Created Category"
}
```


## **Update a category**

```http
  PATCH /api/v1/categories/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Category |

Request body:
```json
{
  "name": "Category name"
}
```

Returns:

* 200

```json
{
  "id": 1,
  "name": "Category name"
}
```

## **Delete a category**

```http
  DELETE /api/v1/categories/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Category |

Returns:

* 204: No content

---

## **Product**

## **Get all products**

```http
  GET /api/v1/products
```

Returns:

* 200

```json
{
  "products": [
    {
      "id": 1,
      "name": "Product name 1",
      "description": "Description of my product",
      "category": {
        "id": 1,
        "name": "Category name"
      }
    },
    {
      "id": 2,
      "name": "Product name 2",
      "description": "Description of my second product",
      "category": {
        "id": 1,
        "name": "Category name"
      }
    }
  ]
}
```

## **Get a product by ID**

```http
  GET /api/v1/products/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Product |

Returns:

* 200

```json
{
  "id": 1,
  "name": "Product name 1",
  "description": "Description of my product",
  "category": {
    "id": 1,
    "name": "Category name"
  }
}
```
## **Create a product**

```http
  POST /api/v1/products
```

Request body:
```json
{
  "name": "Created Product name",
  "description": "Description of my product",
  "category_id": 1
}
```

Returns:

* 200

```json
{
  "id": 10,
  "name": "Created Product name",
  "description": "Description of my product",
  "category": {
    "id": 1,
    "name": "Category name"
  }
}
```


## **Update a product**

```http
  PATCH /api/v1/products/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Product |

Request body:
```json
{
  "name": "Update Product name",
  "description": "Update Description",
  "category_id": 2
}
```

Returns:

* 200

```json
{
  "id": 10,
  "name": "Update Product name",
  "description": "Update Description",
  "category": {
    "id": 2,
    "name": "Category name"
  }
}
```

## **Delete a product**

```http
  DELETE /api/v1/products/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Product |

Returns:

* 204: No content

---

## **Employee**

## **Get all employees**

```http
  GET /api/v1/employees
```

Returns:

* 200

```json
{
  "employees": [
    {
      "id": 1,
      "name": "Admin employee",
      "occupation": 1
    },
    {
      "id": 2,
      "name": "Attendant employee",
      "occupation": 1
    },
    {
      "id": 3,
      "name": "Kitchen employee",
      "occupation": 1
    }
  ]
}
```
## **Get a employee by ID**

```http
  GET /api/v1/employees/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Employee |

Returns:

* 200

```json
{
  "id": 1,
  "name": "Admin employee",
  "occupation": 1
}
```
## **Create a employee**

```http
  POST /api/v1/employees
```

Request body:
```json
{
  "name": "New Admin employee",
  "occupation": 1
}
```

Returns:

* 200

```json
{
  "id": 10,
  "name": "New Admin employee",
  "occupation": 1
}
```


## **Update a employee**

```http
  PATCH /api/v1/employees/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Employee |

Request body:
```json
{
  "name": "Admin employee",
  "occupation": 1
}
```

Returns:

* 200

```json
{
  "id": 10,
  "name": "Admin employee",
  "occupation": 1
```

## **Delete a employee**

```http
  DELETE /api/v1/employees/:id
```

| Parameter | Type  | Description               |
| :-------- | :---- | :------------------------ |
| `id`      | `int` | **Required**. Id Employee |

Returns:

* 204: No content



