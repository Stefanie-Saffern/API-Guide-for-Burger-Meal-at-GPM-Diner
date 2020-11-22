# Endpoint: POST/MyOrder
The POST sends the customer's order, takeout status, and time it is placed to the cook.   

| Method | Syntax|
| ---| ---|
| POST | base_URL://myorder/option/order#/table#/timestamp |


## POST Order Burger Meal
### POST/meal/lunch/burgermeal/Arguments (Query Parameter) 
 
| Argument | Data Type  | Description | Required |
| --- | --- | --- | --- |
| main  | string | The main course for lunch is a burger meal. The hamburger can be an all-beef patty or veggie patty. The default value for the hamburger is an all-beef patty. | Yes |
| main_size | int | The size can be 150 grams or 300 grams. The 300 gram patty will cost an additional $4.| Yes |
|hamburger_bun | string | The hamburger bun can be white bread bun or whole wheat bread bun. The default value is white bread bun.| Yes |
| bun_quantity | int | The burger meal comes with only 1 bun and there is no option to receive a meal without a bun. The default value is 1.| No |
| topping_1 | string | The toppings are tomatoes, lettuce, pickles, or onions. The default value for toppings is tomatoes and lettuce. Each additional topping is $1. If you don’t want toppings, the value is null and no more toppings will be offered. The price of the burger meal will remain the same. | No | 
| topping_2 | string  | The toppings are tomatoes, lettuce, pickles, or onions. If you don’t want a topping 2, the value is null and no more toppings will be offered. | No
| topping_3 | string  | The toppings are tomatoes, lettuce, pickles, or onions. If you don’t want a topping 3, the value is null and no more toppings will be offered. | No |
| topping_4 | string | The toppings are tomatoes, lettuce, pickles, or onions. If you don’t want a topping 4, the value is null. | No |
| side_1 | string | The side can be french fries, onion rings, baked potato, or sweet potato fries. The default value is french fries & onion rings.The price of the meal will remain the same. If you don’t want sides, the value is null and no more sides will be offered. |
| side_2 | string | The side can be french fries, onion rings, baked potato, or sweet potato fries. If you don’t want side 2, the value is null and no more sides will be offered. | No |
|side_3 | string | The side can be french fries, onion rings, baked potato, or sweet potato fries. If you don’t want side 3, the value is null and no more sides will be offered.| No |
|sidd_4 | string | The side can be french fries, onion rings, baked potato, or sweet potato fries. If you don’t want side 4, the value is null. | No |
| sauces | string | The sauces are ketchup, BBQ sauce, mayo or chimichurri. There is no limit to the amount of condiments you can order. The default value is ketchup. If you don’t want any condiments, the value is null and no more sauce will be offered. | No|
|sauces_quantity | int | There is no additional charge or limit to the amount or types of sauces. The default value is 1. |
| drink | string | There is no additional charge or limit to the amount or types of condiments. The default value is 1.| No |
|drink_quantity | int | The default value is null. | No |

### Request Example (cURL)

```JSON
curl -H "Content-Type: application/json" -X POST -d'{
   "mealType":"lunch",
   "mealCat":{
  	"main":"burgerMeal",
  	"burger":{
     	"pattyType":"”beef”",
     	"pattyQty":1,
     	"pattyWeightG":300,
     	"pattyCook":"MR",
     	"bunType":"wholeWheat",
     	"condiment1":"ketchup",
     	"condiment2":"secretSauce",
     	"topping1":"lettuce",
     	"topping2":"pickles",
     	"topping3":"None",
     	"topping4":"None"
  	},
  	"sides":{
     	"side1":{
        	"type":"frenchFries",
        	"size":"large"
     	},
     	"side2":{
        	"type":"none",
        	"size":""
     	}
  	},
  	"drink":{
     	"type":"Coke",
     	"size":"large",
     	"ice":"yes"
  	}
   }
}'
http://URL/
```

### POST Response Example

 ![](https://lh6.googleusercontent.com/lg4CSP8V6ZZB08WIpkIXw73NXNWMLoUWJEZG_imtidHrrr49KSYCLKzfvnSSHaRsPdMR-pSMRznkHirUoYFMxoS6-NsQvhYfXdNYqfSQAz4JVeiGqHw9m3DyOw0-MDod8XTw5Mk)

[Error Codes](https://github.com/Stefanie-Saffern/API-Guide-for-Burger-Meal-at-GPM-Diner/blob/main/error%20codes) &mdash; reference of additional error codes.

### Response Schema 
| Argument | Data Type | Description |
| --- | --- | --- | 
|main_type | string | The burger meal that you ordered— all-beef patty or veggie patty. |
| timestamp | date | The time that you ordered the burger meal. main string. The type of hamburger that you ordered— all-beef patty or veggie burger.|
|hamburger_size| omt | The size of the hamgurger patty that you ordered&mdash; all-beef patty or veggie burger. |
|topping_quantity| int | The number of toppings that you ordered. The types of toppings you ordered.|
|sides_quantity| int  | The number of sides that you ordered. The types of sides that you ordered. side string The sides that you ordered. side quantity number. The number of sides you ordered.|
|sauces_quantity| int | The number of sauces that you ordered. The types of sauces that you ordered. sauce string. The sauces that you ordered. sauce quantity order number. The number of sauces you ordered.|
|drink_quantity| int | The number of drinks that you ordered. The type of drink that you ordered. drink string. The drink that you ordered. drink_quantity order number. The number of drinks you ordered.|
|order| string| The name of the customer who placed the order.|
|order_id| uuid| The unique identifier for the customer who placed the order. |
| cook| string | The name of the cook assigned to cook the meal. |
|cook_id| uuid| The unique identifier for the cook assignmed to cook your meal. |
|price_base| string | The base price of the meal (does not include additions).|
|price_add| string| The price of additions made to the meal. |price_total| string| The total cost of the meal (price_base + price_add). |

