# Endpoint GET/Lunch/burgerMeal  
The GET/lunch gives the customer to access the burger meal section of the online menu for the General Putnam Motel Diner.    

| Method | Syntax |
| --- | --- |
| GET | base_url://lunch/bugerMeal |



The GET/mealType retrives the meal that is currently available, the burgerMeal.  
|Attribute | Data Type | Description |
| --- | ---| --- |
| mealType | string | The meal you order |
| timestamp | date | The time you place the order |

## GET Request Burgermeal

Retrieves the meal that is available at the current time.  

GET /meal  

Arguments (Query Parameters)  

There are no arguments.  

### Response Schema
| Attribute | Data Type | Description |
| --- | --- | --- |
| meal_type | string | The burger meal includes a choice of 2 toppings, 2 sides, and unlimited sauces. Customers can select from 4 types of toppings, sides, and sauces. Additional toppings, sides, and drinks can be added for an extra charge. |
| timestamp | date | 2020-01-21T07:44:45-05:00 The timestamp indicates the year, month, day, and time when the order is placed.|
| order_number | int | Each burger meal order is assigned a unique number, such as 123. |
| table_number | string | Table number 99 is designated for takeout orders only. |
| customer_id | uuid | Each UUID consists of a unique combination of characters and numerals to identify the customer. This”shdi64826” is an example of the uuid. |

### Response Example 
```JSON
curl -X GET "http://URL/tableNo?id=99"
# response
{
   "orderNum":123,
   "timestamp":"2020-01-21T07:44:45-05:00",
   "Item1":{
  	"ItemOrdered":{
     	"type":"burgerMeal",
     	"Cost":10.99
  	 }
   },
   "Item2":{
  	"ItemOrdered":{
     	"type":"salad",
     	"Cost":9.50
  	}
   }
}
```





