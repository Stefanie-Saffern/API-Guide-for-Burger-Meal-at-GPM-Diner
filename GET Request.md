## GET Request Burgermeal

Retrieves the meal that is available at the current time.  

GET /meal  

Arguments (Query Parameters)  

There are no arguments.  

### Response Schema
| Attribute | Data Type | Description |
| --- | --- | --- |
| meal_type | string | The burger meal that comes with a choice of 2 toppings, 2 sides, and unlimited sauces. The customer chooses from 4 types of toppings, 4 types of sides, and 4 types of sauces. There is an option to add more toppings or sides and a drink for additional payment. |
| timestamp | date | 2020-01-21T07:44:45-05:00 The time stamp refers to the year, month, day, and time the order is placed.|
| order_number | int | A number is assigned to the burger meal order, for example 123. |
| table_number | string | Table number 99 is to identify takeout orders only. |
| customer_id | uuid | Each uuid will be made up of a unique combination of characters and numerals to identify the customer. This”shdi64826” is an example of the uuid. |

### Response Example 
**![](https://lh3.googleusercontent.com/gLjo0AJRke9kKl2zCk9bjv-hMqxNr6WGDdUu6VJ2TU5ZcHiEnbm0Cbr5NtAY_iZ5TGeh5nyGZa4AMhGyG5zKAvASacjy2KjG82NADpE8FQrk4LbXrwuZFpJ9V6asoY_Me-2cXB8)

### Endpoint GET/Lunch/burgerMeal

The GET gives the customer to access the burger meal section of the online menu for the General Putnam Motel Diner.  

| Method | Syntax |
| --- | --- |
| GET | base_url://lunch/bugerMeal |

### Endpoint POST/MyOrder
The Post sends the customers order, burger meal and its specifications, takeout status, and the time it is place to the cook at the General Putnam Motel Diner.  

|  Method | Syntax |
| --- | --- |
| POST | base_URL://myorder/option/order#/table#/timestamp |
