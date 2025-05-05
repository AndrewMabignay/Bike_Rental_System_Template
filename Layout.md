                           +--------------------+
                           |     Home Page      |
                           +--------------------+
                                     |
                                     v
                    +-------------------------------+
                    |  User Authentication (Login)  |
                    |       or Registration         |
                    +-------------------------------+
                             |               |
                    +--------+               +--------+
                    |                                 |
                    v                                 v
        +---------------------+           +-------------------------+
        |   Admin Dashboard   |           |   Customer Dashboard    |
        +---------------------+           +-------------------------+
        | - Manage Bikes      |           | - Browse Products       |
        | - Manage Categories |           | - Filter by Category    |
        | - Manage Brands     |           | - View Bike Details     |
        | - Manage Subcats    |           | - Add to Cart           |
        | - Manage Users      |           | - Place Order           |
        | - Manage Orders     |           | - View Order History    |
        | - View Messages     |           | - Submit Inquiry (Contact)|
        +---------------------+           +-------------------------+
                    |                                 |
                    +------------+   +----------------+
                                 |   |
                                 v   v
                          +----------------+
                          |     Logout     |
                          +----------------+

                           Shared Tables:
                         ---------------------
                         | - Users           |
                         | - Bikes           |
                         | - Categories      |
                         | - Subcategories   |
                         | - Brands          |
                         | - Orders          |
                         | - Order_Items     |
                         | - Messages        |
                         ---------------------



+----------------------------+
|       Admin Sidebar        |
+----------------------------+
| 🏠 Dashboard Overview      |
| 🚴 Manage Bikes            |
| 🗂️  Manage Categories      |
| ➕ Subcategories           |
| 🏷️  Manage Brands          |
| 📦 Manage Inventory        |
| 🛒 Manage Orders           |
| 👥 Manage Users            |
| ✉️  Customer Inquiries     |
| ⚙️  Settings (Optional)    |
| 🚪 Logout                  |
+----------------------------+
[] ------ DASHBOARD OVERVIEW ------
+--------------------------------------------+
|              Admin Dashboard               |
+--------------------------------------------+
| Summary Cards:                             |
| - Total Bikes     - Total Orders           |
| - Total Sales     - Registered Users       |
+--------------------------------------------+
| Graphs & Charts (Optional)                 |
+--------------------------------------------+


[] ------ MANAGE BIKES ------
+--------------------------------------------+
|               Manage Bikes                 |
+--------------------------------------------+
| [Add New Bike]                             |
+--------------------------------------------+
| # | Bike Name | Category | Brand | Price   |
|---|-----------|----------|-------|-------- |
| 1 | Roadster  | Road     | Giant | $1200   |
| 2 | MTB Pro   | Mountain | Trek  | $850    |
+--------------------------------------------+
| [Edit] [Delete] buttons on each row        |
+--------------------------------------------+



[] ------ MANAGE BRANDS ------
+--------------------------------------------+
|               Manage Brands                |
+--------------------------------------------+
| [Add New Brand]                            |
+--------------------------------------------+
| # | Brand Name | Logo | Actions            |
|---|------------|------|--------------------|
| 1 | Giant      | img  | [Edit] [Delete]    |
| 2 | Trek       | img  | [Edit] [Delete]    |
+--------------------------------------------+



[] ------ MANAGE CATEGORIES ------
+--------------------------------------------+
|             Manage Categories              |
+--------------------------------------------+
| [Add New Category]                         |
+--------------------------------------------+
| # | Category Name       | Actions          |
|---|---------------------|------------------|
| 1 | Bikes               | [Edit] [Delete]  |
| 2 | Accessories         | [Edit] [Delete]  |
+--------------------------------------------+



-- SUBCATEGORIES [MANAGE_SUBCATEGORIES] --
+--------------------------------------------+
| 🔍 Search: [___________]   [ Add New ➕ ]   |
+--------------------------------------------+

| # | Subcategory Name | Parent Category | Actions     |
|---|------------------|-----------------|-------------|
| 1 | Mountain Bike    | Bikes           | [✏️ Edit] [🗑️ Delete] |
| 2 | Road Bike        | Bikes           | [✏️ Edit] [🗑️ Delete] |
| 3 | Cycling Shoes    | Apparel         | [✏️ Edit] [🗑️ Delete] |
| 4 | Handle Grips     | Accessories     | [✏️ Edit] [🗑️ Delete] |

<< Pagination here if needed >>

+---------------------------+
|     Add Subcategory       |
+---------------------------+
| Subcategory Name: [_____] |
| Parent Category:  [▼]     | ← dropdown of existing categories
| [ Save ]     [ Cancel ]   |
+---------------------------+


----- FILE STRUCTURE -----
bike-shop/
├── app/
│   ├── Console/
│   ├── Exceptions/
│   ├── Http/
│   │   ├── Controllers/
│   │   │   ├── Admin/
│   │   │   │   ├── BikeController.php
│   │   │   │   ├── BrandController.php
│   │   │   │   ├── CategoryController.php
│   │   │   │   ├── SubcategoryController.php
│   │   │   │   ├── OrderController.php
│   │   │   │   ├── UserController.php
│   │   │   │   └── DashboardController.php
│   │   │   ├── Auth/
│   │   │   ├── HomeController.php
│   │   │   └── ContactController.php
│   │   ├── Middleware/
│   │   └── Requests/
│   ├── Models/
│   │   ├── Bike.php
│   │   ├── Brand.php
│   │   ├── Category.php
│   │   ├── Subcategory.php
│   │   ├── Order.php
│   │   ├── OrderItem.php
│   │   ├── User.php
│   │   └── Message.php
│   └── Providers/
│
├── database/
│   ├── factories/
│   ├── migrations/
│   │   ├── create_bikes_table.php
│   │   ├── create_categories_table.php
│   │   ├── create_subcategories_table.php
│   │   ├── create_brands_table.php
│   │   ├── create_orders_table.php
│   │   ├── create_order_items_table.php
│   │   ├── create_users_table.php
│   │   └── create_messages_table.php
│   └── seeders/
│
├── public/
│   ├── assets/
│   │   ├── css/
│   │   ├── js/
│   │   └── images/
│   └── index.php
│
├── resources/
│   ├── views/
│   │   ├── admin/
│   │   │   ├── bikes/
│   │   │   ├── brands/
│   │   │   ├── categories/
│   │   │   ├── subcategories/
│   │   │   ├── orders/
│   │   │   └── dashboard.blade.php
│   │   ├── customer/
│   │   │   ├── home.blade.php
│   │   │   ├── shop.blade.php
│   │   │   ├── cart.blade.php
│   │   │   ├── checkout.blade.php
│   │   └── layouts/
│   │       ├── admin.blade.php
│   │       ├── app.blade.php
│   │       └── guest.blade.php
│   └── lang/
│
├── routes/
│   ├── web.php
│   ├── admin.php (optional for grouped routes)
│   └── auth.php
│
├── .env
├── artisan
├── composer.json
└── README.md

