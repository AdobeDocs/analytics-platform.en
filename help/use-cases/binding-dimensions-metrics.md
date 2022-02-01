---
title: Using binding dimensions and metrics in CJA
description: Attribute dimensions to object arrays for complex persistence analysis.
exl-id: 5e7c71e9-3f22-4aa1-a428-0bea45efb394
feature: Use Cases
---
# Using binding dimensions and metrics in CJA

Customer Journey Analytics offers several ways to persist dimension values beyond the hit that they are set on. One of the persistence methods that Adobe offers is known as Binding. In previous versions of Adobe Analytics, this concept was known as merchandising.

While you can use binding dimensions with top-level event data, this concept is best used when working with [Arrays of objects](object-arrays.md). You can attribute a dimension to one part of an object array without applying it to all of the attributes in a given event. For example, you can attribute a search term to one product in your shopping cart object array without binding that search term to the entire event.

## Example 1: Use binding dimensions to attribute additional product attributes to a purchase

You can bind dimension items within an object array to another dimension. When the bound dimension item appears, CJA recalls the bound dimension and includes it in the event for you. Consider the following customer journey:

1. A visitor views a product page on a washing machine.

    ```json
    {
        "PersonID": "1",
        "product_views": 1,
        "product": [
            {
                "name": "Washing Machine 2000",
                "color": "white",
                "type": "front loader",
            },
        ],
        "timestamp": 1534219229
    }
    ```

1. The visitor then views a product page on a dryer.

    ```json
    {
        "PersonID": "1",
        "product_views": 1,
        "product": [
            {
                "name": "Dryer 2000",
                "color": "neon orange",
            },
        ],
        "timestamp": 1534219502
    }
    ```

1. Ultimately they make a purchase. The color of each product wasn't included in the purchase event.

    ```json
    {
        "PersonID": "1",
        "orders": 1,
        "product": [
            {
                "name": "Washing Machine 2000",
                "price": 1600,
            },
            {
                "name": "Dryer 2000",
                "price": 499
            }
        ],
        "timestamp": 1534219768
    }
    ```

If you wanted to look at revenue by color without a binding dimension, the dimension `product.color` persists and incorrectly attributes credit to the dryer's color:

| product.color | revenue |
| --- | --- |
| neon orange | 2099 |

You can go into the Data View Manager and bind product color to product name:

![Binding dimension](assets/binding-dimension.png)

When you set this persistence model, Adobe takes note of the product name whenever product color is set. When it recognizes the same product name in a subsequent event for this visitor, the product color is brought over as well. The same data when you bind product color to product name would look similar to the following:

| product.color | revenue |
| --- | --- |
| white | 1600 |
| neon orange | 499 |

## Example 2: Use binding metrics to tie search term to a product purchase

One of the most common merchandising methods in Adobe Analytics has been to bind a search term to a product so each search term gets credit for it's appropriate product. Consider the following customer journey:

1. A visitor arrives to your site and searches for "boxing gloves".

    ```json
    {
        "PersonID": "1",
        "page_name": "Search results",
        "search": "1",
        "search_term": "boxing gloves",
        "product": [
            {
                "name": "Beginner gloves",
                "color": "Red",
                "price": "25.69"
            },
            {
                "name": "Tier 3 gloves",
                "color": "Black",
                "price": "89.99"
            },
            {
                "name": "Professional gloves",
                "color": "Blue",
                "price": "224.99"
            }
        ]
    }
    ```

1. They find a pair of gloves that they like, and add it to their cart.

    ```json
    {
        "PersonID": "1",
        "page_name": "Shopping cart",
        "cart_add": "1",
        "product": [
            {
                "name": "Tier 3 gloves",
                "color": "Black",
                "price": "89.99"
            }
        ]
    }
    ```

1. The visitor then searches for "tennis racket".

    ```json
    {
        "PersonID": "1",
        "page_name": "Search results",
        "search": "1",
        "search_term": "tennis racket",
        "product": [
            {
                "name": "Shock absorb racket",
                "price": "34.99"
            },
            {
                "name": "Women's open racket",
                "price": "49.99"
            },
            {
                "name": "Extreme racket",
                "price": "134.99"
            }
        ]
    }
    ```

1. They find a racket that they like, and add it to their cart.

    ```json
    {
        "PersonID": "1",
        "page_name": "Shopping cart",
        "cart_add": "1",
        "product": [
            {
                "name": "Tier 3 gloves",
                "color": "Black",
                "price": "89.99"
            },
            {
                "name": "Shock absorb racket",
                "price": "34.99"
            }
        ]
    }
    ```

1. The visitor searches a third time for "shoes".

    ```json
    {
        "PersonID": "1",
        "page_name": "Search results",
        "search": "1",
        "search_term": "shoes",
        "product": [
            {
                "name": "Men's walking shoes",
                "color": "Grey",
                "price": "54.95"
            },
            {
                "name": "Tennis shoes",
                "color": "White",
                "price": "42.59"
            },
            {
                "name": "Skate shoes",
                "color": "Black",
                "price": "79.99"
            }
        ]
    }
    ```

1. They find a pair of shoes that they like, and add it to their cart.

    ```json
    {
        "PersonID": "1",
        "page_name": "Shopping cart",
        "cart_add": "1",
        "product": [
            {
                "name": "Tier 3 gloves",
                "color": "Black",
                "price": "89.99"
            },
            {
                "name": "Shock absorb racket",
                "price": "34.99"
            },
            {
                "name": "Skate shoes",
                "color": "Black",
                "price": "79.99"
            }
        ]
    }
    ```

1. The visitor goes through the checkout process and purchases these three items.

    ```json
    {
        "PersonID": "1",
        "page_name": "Thank you for your purchase",
        "purchase": "1",
        "product": [
            {
                "name": "Tier 3 gloves",
                "color": "Black",
                "price": "89.99"
            },
            {
                "name": "Shock absorb racket",
                "price": "34.99"
            },
            {
                "name": "Skate shoes",
                "color": "Black",
                "price": "79.99"
            }
        ]
    }
    ```

If you use a traditional allocation model with search term, all three products attribute revenue to only a single search term. For example, if you used first allocation with the search term dimension:

| search_term | revenue |
| --- | --- |
| boxing gloves | $204.97 |

If you used last allocation with the search term dimension, all three products still attribute revenue to a single search term:

| search_term | revenue |
| --- | --- |
| shoes | $204.97 |

While this example includes only one visitor, many visitors who search for different things can misattribute search terms to different products, making it difficult to determine what the best search results actually are.

With a binding dimension, Adobe takes note of the dimension item that it is bound to. When that same binding value is seen in a subsequent event, it brings over the dimension item so that you can attribute the desired metric to it. In this example, we can set the binding dimension for search_term to product name. When we set this dimension in the Data View manager, we are also required to set a binding metric because the binding dimension is in an object array. A binding metric acts as a trigger for a binding dimension, so it only binds itself on events where the binding metric is present. In this example implementation, the search results page always includes a search term dimension and a searches metric. We can bind search terms to product name whenever the Searches metric is present.

![Binding metric](assets/binding-metric.png)

Setting the search term dimension to this persistence model executes the following logic:

* When search_term is in an event, check for the presence of product name.
* If product name is not there, do nothing.
* If product name is there, check for the presence of the Searches metric.
* If the Searches metric is not there, do nothing.
* If the Searches metric is there, bind the search term to all product names. It acts as though it at the same level as product name for that event. In this example, it is treated as product.search_term.
* If the same product name is seen in a subsequent event, the bound search term exists there as well.

In Analysis Workspace, the resulting report would look similar to the following:

| search_term | revenue |
| --- | --- |
| boxing gloves | $89.99 |
| tennis racket | $34.99 |
| shoes | $79.99 |
