# Section 3 — System Design

Loom Link: https://www.loom.com/share/c4e3d09b5df8414798a6a6f6b1fc1ef3

UML Diagram: https://lucid.app/lucidchart/070b6a21-e214-433d-9651-21165d194213/edit?viewport_loc=-47%2C47%2C1617%2C895%2C0_0&invitationId=inv_f8789536-677f-4893-ba11-1206d98a683a

## Notes:

Feel free to add any notes or planning here.

There should be three classes in my system. First, there should be a Restaurant class that has a name property and a menu property. The name is just what the restaurant is called, and the menu shows what kind of food the restaurant has.

Then there should be a MenuItem class, which has the items that belong to the restaurant’s menu. Each menu item should have the name of the food and the price of that food.

Finally, there should be an Order class where people can order food from the restaurant’s menu. The Order class should have the customer’s name, the item of food they want, and the status of the order. This way, the restaurant has its menu, the menu has the items, and the order lets customers pick what they want to eat.

The Restaurant class should have an addItem method, because the restaurant needs a way to put items in the menu list. It should also have a removeItem method in case the restaurant removes an item from the menu, and a listMenu method that shows all the items.

The MenuItem class has name and price properties, which are inherited from the restaurant so we can see the items and their prices.

The Order class has an addItem method so the customer can order an item, and an updateStatus method that shows if the order is "pending," "in progress," "picked up," or "delivered."






