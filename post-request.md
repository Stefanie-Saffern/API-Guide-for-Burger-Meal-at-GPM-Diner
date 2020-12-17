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
| bun_quantity | int | The burger meal comes with only 1 bun and there is no option to receive a meal without a bun. The default value is 1.| Yes |
| topping_1 | string | The toppings are tomatoes, lettuce, pickles, or onions. The default value for toppings is tomatoes and lettuce. Each additional topping is $1. If you don’t want toppings, the value is null and no more toppings will be offered. The price of the burger meal will remain the same. | No | 
| topping_2 | string  | The toppings are tomatoes, lettuce, pickles, or onions. If you don’t want a topping 2, the value is null and no more toppings will be offered. | No
| topping_3 | string  | The toppings are tomatoes, lettuce, pickles, or onions. If you don’t want a topping 3, the value is null and no more toppings will be offered. | No |
| topping_4 | string | The toppings are tomatoes, lettuce, pickles, or onions. If you don’t want a topping 4, the value is null. | No |
| side_1 | string | The side can be french fries, onion rings, baked potato, or sweet potato fries. The default value is french fries & onion rings.The price of the meal will remain the same. If you don’t want sides, the value is null and no more sides will be offered. |
| side_2 | string | The side can be french fries, onion rings, baked potato, or sweet potato fries. If you don’t want side 2, the value is null and no more sides will be offered. | No |
|side_3 | string | The side can be french fries, onion rings, baked potato, or sweet potato fries. If you don’t want side 3, the value is null and no more sides will be offered.| No |
|sidd_4 | string | The side can be french fries, onion rings, baked potato, or sweet potato fries. If you don’t want side 4, the value is null. | No |
| sauces | string | The sauces are ketchup, BBQ sauce, mayo or chimichurri. There is no limit to the amount of condiments you can order. The default value is ketchup. If you don’t want any condiments, the value is null and no more sauce will be offered. | No|
|sauces_quantity | int | There is no additional charge or limit to the amount or types of sauces. The default value is 1. | No|
| drink | string | You can order a can of soda for an additional $5. The choices are: Coke, Diet Coke, Sprite, or Diet Sprite.| No |
|drink_quantity | int | The amount of sodas you can order are 1 to 4 cans. The default value is null. | No |

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

[Error Codes](error-codes.md) &mdash; reference of additional error codes.


