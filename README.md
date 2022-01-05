# microservices

Ecommerce website - this is a small ecommerce website model.

The ecommerce website has 3 microservices
User service
Inventory service
Payment service

All the 3 of the microservices are deployed on different ports.
User service: Opening the port leads to the home page. The home page has menu that has few options like:    
(i) view members option lists the members that are registered on this website
(ii) register button registers new users. It asks for the user name, first name, last name, email address, contact number, password and to confirm password. This checks the format of the parameters and gives an error if there is anything wrong with the format.
It also checks if the user already exists with the same attributes and gives an error in that case. It also creates a unique id to the user. The user then gets added to the users database.
(iii) login button  asks for the unique id and password. This unique id is given to the user while he registers. It checks for login details in its database and gives replies accordingly.

After logging the user gets to choose 3 options
(i) view items list : This displays the items available from the inventory database. This is a dynamic query. Every time the user asks for the items list, the service asks the inventory database via rest template communication and gives the list of items. The items are displayed along with their price and quantity. This option here depends on the 2nd microservice i.e inventory service
(ii) addToCart option : This option enables the user to add items to his cart. He has to fill  in the item id and item quantity. He can add only 1 item type at a time. After the user adds items to his cart, the item's quantity is decreased in the inventory database.
(iii) mycart option: This option enables the user to view his list of items.
He can click on the payment option. This option depends on the 3rd microservice i..e payment service.

Inventory service : The port opens to the home page that has a menu with few options like    
(i) add new items : this option enables the admin to add new items to the inventory database. This option asks for the item name, quantity, price. This function also generated a unique id to the item. The items then get added to the category database.
(ii) update items : this function updates the quantity of the existing items. This updating requires the item id and the required quantity.
(iii) delete the items : this option deletes the items in the inventory database. This option requires an item id.
(iv) view items list : this option views the list of items in the database.

Payment service : This microservice does the payment functionality. When the user is in his cart and wishes to pay for the items in his cart, he uses this function. When the user clicks on this payment button it asks for confirmation of password and then redirects to this microservice. 
This microservice has a database that contains the card details. When the user enters details of the card, this function checks if the card details are matching with the database and replies accordingly. 

Initially the microservices communicate via REST API.

How to run the code:
Open a eclipse/vs editor. Download all the 3 files and run it on editor's inbuilt spring boot apllication.
