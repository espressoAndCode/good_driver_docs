## Helpful Links
[eBay Catalog API Overview](https://developer.ebay.com/api-docs/commerce/catalog/overview.html)
[eBay Developer Sandbox](https://developer.ebay.com/tools/sandbox)
[eBay Developer Login Page](https://developer.ebay.com/signin)

## eBay API
[All API Documents](https://developer.ebay.com/docs#Brs)

## eBay 'Browse' API

[search](https://developer.ebay.com/api-docs/buy/browse/resources/item_summary/methods/search) GET `/item_summary/search`
[getItem](https://developer.ebay.com/api-docs/buy/browse/resources/item/methods/getItem) GET `/item/{item_id}`
[addItem](https://developer.ebay.com/api-docs/buy/browse/resources/shopping_cart/methods/addItem) POST `/shopping_cart/add_item`

## eBay 'FINDING' API

Here is a sample call to the Finding API:

```
    f.execute('findItemsAdvanced', 
                {'keywords': 'shoes'}
             )
```

Here is a sample return object for a call to the Finding API

```
 res: {
   'itemId': '154101365612',
   'title': "adidas Originals OZWEEGO Shoes Men's",
   'globalId': 'EBAY-US',
   'subtitle': 'Free Shipping and Free 30 Day Returns on All Orders',
   'primaryCategory': {
     'categoryId': '15709',
     'categoryName': 'Athletic Shoes'
   },
   'galleryURL': 'https://thumbs1.ebaystatic.com/pict/154101365612404000000004_1.jpg',
   'viewItemURL': 'https://www.ebay.com/itm/adidas-Originals-OZWEEGO-Shoes-Mens-/154101365612?var=454239212707',
   'paymentMethod': 'PayPal',
   'autoPay': 'true',
   'postalCode': '293**',
   'location': 'Spartanburg,SC,USA',
   'country': 'US',
   'shippingInfo': {
     'shippingServiceCost': {
       '_currencyId': 'USD',
       'value': '0.0'
     },
     'shippingType': 'Free',
     'shipToLocations': 'Worldwide',
     'expeditedShipping': 'false',
     'oneDayShippingAvailable': 'false',
     'handlingTime': '4'
   },
   'sellingStatus': {
     'currentPrice': {
       '_currencyId': 'USD',
       'value': '35.99'
     },
     'convertedCurrentPrice': {
       '_currencyId': 'USD',
       'value': '35.99'
     },
     'sellingState': 'Active',
     'timeLeft': 'P4DT18H52M9S'
   },
   'listingInfo': {
     'bestOfferEnabled': 'false',
     'buyItNowAvailable': 'false',
     'startTime': datetime.datetime(2020, 9, 24, 10, 17, 44),
     'endTime': datetime.datetime(2020, 10, 24, 10, 17, 44),
     'listingType': 'FixedPrice',
     'gift': 'false',
     'watchCount': '28'
   },
   'returnsAccepted': 'true',
   'condition': {
     'conditionId': '1000',
     'conditionDisplayName': 'New with box'
   },
   'isMultiVariationListing': 'true',
   'discountPriceInfo': {
     'originalRetailPrice': {
       '_currencyId': 'USD',
       'value': '110.0'
     },
     'pricingTreatment': 'STP',
     'soldOnEbay': 'false',
     'soldOffEbay': 'false'
   },
   'topRatedListing': 'false'
 }
```
