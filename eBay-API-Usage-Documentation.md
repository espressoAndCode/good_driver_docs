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

There are two parts required in the `POST` data object when creating a call to the Finding API, `source` (string) and `keywords` (List):
```
{
  "source": "string",
  "keywords": [
    "string"
  ]
}
```
The `source` value must be one of the Vendors listed in the Source table of the database. I recommend that you create a dropdown list from a call to `GET /sources` which will return a list of all sources in the DB. 
Also, notice that `keywords` is a list of strings, even if there is only one item in the list. You can enter as many search elements as required, and spaces are accepted as long as they are enclosed in quotation marks as shown below: 

```
{
  "keywords": [
    "truck",
    "floor mat"
  ]
}
```

Each call will return a list of up to 100 items matching the keyword criteria. Here is a sample return object for one item from that call:

```
item: {
  'itemId': '202637310539',
  'title': 'Canon EOS Rebel T7 24.1MP Digital SLR Camera with EF-S 18-55 IS II Lens',
  'globalId': 'EBAY-US',
  'primaryCategory': {
    'categoryId': '31388',
    'categoryName': 'Digital Cameras'
  },
  'galleryURL': 'https://thumbs4.ebaystatic.com/m/m09-7Oxghw4Owumm5fmWMGA/140.jpg',
  'viewItemURL': 'https://www.ebay.com/itm/Canon-EOS-Rebel-T7-24-1MP-Digital-SLR-Camera-EF-S-18-55-II-Lens-/202637310539',
  'productId': {
    '_type': 'ReferenceID',
    'value': '4030072379'
  },
  'paymentMethod': 'PayPal',
  'autoPay': 'true',
  'postalCode': '112**',
  'location': 'Brooklyn,NY,USA',
  'country': 'US',
  'shippingInfo': {
    'shippingServiceCost': {
      '_currencyId': 'USD',
      'value': '0.0'
    },
    'shippingType': 'Free',
    'shipToLocations': 'Worldwide',
    'expeditedShipping': 'true',
    'oneDayShippingAvailable': 'true',
    'handlingTime': '1'
  },
  'sellingStatus': {
    'currentPrice': {
      '_currencyId': 'USD',
      'value': '372.99'
    },
    'convertedCurrentPrice': {
      '_currencyId': 'USD',
      'value': '372.99'
    },
    'sellingState': 'Active',
    'timeLeft': 'P8DT4H22M9S'
  },
  'listingInfo': {
    'bestOfferEnabled': 'false',
    'buyItNowAvailable': 'false',
    'startTime': datetime.datetime(2019, 3, 27, 20, 6, 40),
    'endTime': datetime.datetime(2020, 10, 27, 20, 6, 40),
    'listingType': 'FixedPrice',
    'gift': 'false',
    'watchCount': '180'
  },
  'returnsAccepted': 'true',
  'condition': {
    'conditionId': '1000',
    'conditionDisplayName': 'New'
  },
  'isMultiVariationListing': 'false',
  'discountPriceInfo': {
    'originalRetailPrice': {
      '_currencyId': 'USD',
      'value': '447.0'
    },
    'pricingTreatment': 'STP',
    'soldOnEbay': 'false',
    'soldOffEbay': 'false'
  },
  'topRatedListing': 'true'
}
```
