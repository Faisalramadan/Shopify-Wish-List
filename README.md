Shopify-Wish-List
=================

**IMPORTANT CHANGE**

@zakhardage reports that the wish list no longer works. Check out his [repo](https://github.com/zakhardage/Shopify-Wish-List) for details. I'm now taking this off my clients site.

**CHANGES IN THIS BRANCH:**

* Works with product variants
* Assumes you are using Shopify's `option_selection.js`
* Assumes you are using jQuery
* Shows message when wish list is empty
* Uses AJAX to add items to wish list
* Uses AJAX to remove items from wish list
* Added images to wish list
* Option to remove items from wish list when added to cart

Also, it will (I think—I haven't tested it) be reliant on using `product.selected_or_first_available_variant` instead of just `product` in your product template. See the [Skeleton Theme](https://github.com/Shopify/skeleton-theme) for examples of this.

---

non-app wish list using customer.tags

To make this wish list work, you'll need to add an include tag for wishlist-product.liquid in your product page -- make sure that it is not within the add-to-cart form. And you'll need to add an include tag for wishlist-page.liquid in a page with the handle wish-list.

There's no in-line styling so this should pick up your product and page template styling.

The wish list works by adding the product id to the customers account tags. To remove the item, another tag is added
with an "x" preceding the product id. Re-adding the item to the wish list adds another "x". At this point there are
three tags for the one product. If a customer went crazy with the wish list, adding and removing and re-adding
products, it could fill up their customer tags quickly. If there's any issue with their account or interference
with an app (like a wholesale app), I'd look first to their tags.
