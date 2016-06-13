# Shopify
# Hide products listed within a Shopify collection based upon price amount
This code allows you to hide any products that are set to $0 price amounts. 
This becomes useful when a shop owner has variable prices based upon vendor or tiered membership accounts. 

## Usage

### Requirements

Shopify storefront


### Installation

* This code is to be applied, in most cases, within the raw product.liquid file. Once it's applied to this file it becomes a global variable for all products contained within the shops collection(s) 

### Getting Started

1. Create duplicate products of those which are hidden based upon vendor or tiered membership.
2. Set duplicate prducts all to $0.00
3. Open up product.liquid 
4. Look for an instance of:  {{ current_variant.price | money }}
5. Apply the opening statement " {% unless product.price == 0 %} " above the line of code seen above. 
Example is listed below. 

   ```ruby
   {{ current_variant.price | money }}
   {% unless product.price == 0 %}
   ```

Apply the ending statement " {% endunless %} " as seen in the example below. It's placement might vary depending upon div's and span's already wrapped around the product(s)

   ```ruby
              {% unless product.price == 0 %}
                      {{ current_variant.price | money }}
                      {% if price.compare_at_price_max > compare_price %} 
                      <span class="price_compair">  {{ compare_at_price | money }}  </span> 
                      {% endif %}                      
              {% endunless %}
              
              
   ```

