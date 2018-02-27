"use strict";
(function () { 
    let itemsList = [];
    
    //adds items as objects to the array
    function addItem (name, price) {
        itemsList.push({name , price});
    }
    
    //returns a sorted array of all item objects (sorted by price)
    function items () {
        itemsList.sort(function (key, value) {
            return key.price - value.price;
        });
        return itemsList;
    }
    
    //finds and returns the most expensive item based on price
    function getMostExpensive () {
        let most = itemsList[0];
        for (let i = 1; i <= itemsList.length - 1; i++) {
            let currentItem = itemsList[i];
            if (+currentItem.price > +most.price) {
                most = itemsList[i];
            }
        }
        return most;
    }
    
    //finds and returns the least expensive item based on price
    function getLeastExpensive () {
        let least = itemsList[0];
        for (let i = 1; i <= itemsList.length - 1; i++) {
            let currentItem = itemsList[i];
            if (+currentItem.price < +least.price) {
                least = itemsList[i];
            }
        }
        return least;
    }
    
    //finds the item by Name and removes the object from the array
    function removeItem (itemName) {
        for (let i = 0; i < itemsList.length; i++) {
            if (itemName == itemsList[i].name) {
                return itemsList.splice(i, 1);
            }
        }
    }
	
    //finds and returns an item by name
    function getItemByName (itemName) {
        for (let i = 0; i <= itemsList.length; i++) {
            if (itemName == itemsList[i].name) {
                return itemsList[i];
            } 
        }
        return itemName + " not in list";
    }
	
    //finds and returns an item by price
    function getItemByPrice (itemPrice) {
        for (let i = 0; i < itemsList.length; i++) {
            if (itemPrice == itemsList[i].price) {
                return itemsList[i];
            }
        }
        return itemPrice + " not in list";
    }

    exports.addItem = addItem;
    exports.items = items;
    exports.getMostExpensive = getMostExpensive;
    exports.getLeastExpensive = getLeastExpensive;
    exports.removeItem = removeItem;
    exports.getItemByName = getItemByName;
    exports.getItemByPrice = getItemByPrice;
})();