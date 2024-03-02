
###### Liquid is used to dynamically output objects and their properties. You can further modify that output by creating logic with tags, or directly altering it with a filter. Objects and object properties are output using one of six basic data types. Liquid also includes basic logical and comparison operators for use with tags


### Liquid is a template based web development kid that is used to create dynamic websites using it's awesome features , this load the data in the **Server side** and send it to the client unlike html , CSS and java script


## Folder Structure

In Shopify, Liquid templates are organized in a specific folder structure within the theme of your store. Understanding this structure is essential for managing your theme and creating customizations efficiently. Let's break down the routing and folder structure:

1. **Layouts**: Layouts are the outermost structure of your theme. They define the overall structure of your pages, including headers, footers, and any common elements across multiple pages. You typically have at least one layout file. Examples include `theme.liquid`, `layout.liquid`, or custom-named layout files. These files encapsulate the common structure of your store.
    
2. **Templates**: Templates define the layout for specific types of pages in your store, such as product pages, collection pages, and the cart page. Each template corresponds to a specific URL route or page type. For example:
    
    - `product.liquid`: Defines the layout for individual product pages.
    - `collection.liquid`: Defines the layout for collection pages.
    - `cart.liquid`: Defines the layout for the shopping cart page.
    - `page.liquid`: Defines the layout for static pages like About Us, Contact, etc.
    
1. **Sections**: Sections are reusable components that can be included in templates to add additional functionality or customize the layout. They allow you to break down your templates into smaller, manageable pieces. For example, you might have a `featured-products.liquid` section that displays a carousel of featured products. Sections are typically included within layout and template files using the `section` tag.
    
4. **Snippets**: Snippets are reusable code snippets that can be included in any Liquid template or section. They are useful for storing code that you want to reuse across multiple templates. Common examples include header snippets, footer snippets, and navigation snippets. Snippets are included using the `include` tag.
    
5. **Assets**: The `assets` directory contains static files such as images, stylesheets (CSS), JavaScript files, and fonts used in your theme. These files are typically referenced in your Liquid templates using absolute or relative paths.
    
6. **Configurations**: The `config` directory contains theme configuration files, including `settings_schema.json`, which defines the settings that merchants can customize in the theme editor.
    
7. **Locales**: The `locales` directory contains language translation files for your theme. These files allow you to provide translations for different languages, making your store accessible to a broader audience.

## How routing in shopify

In Shopify, routing refers to the process of determining which template to use to render a specific page or URL on your online store. Unlike traditional web development frameworks where routing is explicitly defined in a configuration file or code, Shopify handles routing internally based on the structure of your theme and the type of content being requested.

Here's how routing works in Shopify:

**URL Structure**: The URL structure of your Shopify store is based on the type of content being accessed. For example:
    
    - Product pages: `https://yourstore.com/products/product-handle`
    - Collection pages: `https://yourstore.com/collections/collection-handle`
    - Pages (static content): `https://yourstore.com/pages/page-handle`
    - Blog posts: `https://yourstore.com/blogs/blog-handle/post-title`


