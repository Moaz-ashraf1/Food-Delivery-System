# Food Delivery System

## 📌 About The Project

The **Food Delivery System** is a scalable, secure, and feature-rich platform designed to manage the complete food ordering lifecycle — from restaurant discovery to payment settlement and analytics.

The system supports **multi-restaurants**, **multiple payment methods**, **real-time order tracking**, and **advanced analytics dashboards** for both the platform and restaurants.

It is built to be:

-  Multi-country & multi-language ready
-  High performance & scalable
-  Secure with full payment auditing
-  Data-driven with detailed insights

---

##  System Feature List

Below is a structured overview highlighting all the key features available in the platform

---

# 👤 User Management Features

##  Authentication & Account Management

- **Login**
    
    Users can log in using their phone number or email address.
    
- **Registration**
    
    Create a new user account.
    
- **Password Recovery**
    
    Reset password using OTP verification.
    
- **Change Password**
    
    Update the current password securely.
    

---

##  User Profile & Settings

- **View Profile**
    
    View personal profile information.
    
- **Edit Profile**
    - Edit Email
    - Edit First Name
    - Edit Last Name
    - Edit Phone Number

---

##  Address Management

- **Add Address**
    
    Save a new delivery address.
    
- **Edit Address**
    
    Update an existing address.
    
- **Delete Address**
    
    Remove an address.
    
- **Set Default Address**
    
    Select a default address for orders.
    

---

# 🔍 Discovery & Browsing Features

##  Restaurant & Food Browsing

- **Browse Restaurants by Category**
    
    Discover restaurants by food category (Burger, Pizza, etc.).
    
- **Browse Restaurant Menu**
    
    View restaurant menus.
    
- **Browse Product Details**
    
    View detailed dish information.
    

---

##  Ratings & Recommendations

- **Top-Rated Restaurants**
    
    Discover restaurants with the highest ratings.
    
- **Top-Rated Dishes**
    
    View the most popular and highly rated dishes.
    

---

##  Sorting & Filtering

Restaurants can be sorted by:

- Recommendations
- Alphabetical Order (A–Z)
- High Rating
- Fast Delivery
- Nearest Location (Based on user location)

---

##  Search

- **Search Restaurants**
    
    Search by restaurant name or category.
    
- **Search Food Items**
    
    Search for specific dishes.
    

---

##  Nearby Restaurants

- Detect and display restaurants closest to the user using geolocation data.

---

# 🛒 Cart Management

- Add products to cart
- Apply discount / voucher codes
- Edit cart contents
- Increase or decrease product quantity
- View cart details
- Remove specific items
- Clear the entire cart

---

# 📦 Order Management

- **Place Order**
    
    Submit an order successfully.
    
- **Cancel Order**
    
    Cancel orders by customer or restaurant.
    
- **Real-Time Order Tracking**
    - Pending
    - Preparing
    - Out for Delivery
    - Delivered
- **Notifications**
    
    Instant updates when order status changes.
    
- **Order History**
    
    View completed, canceled, or failed orders.
    
- **Detailed Order View**
    
    Full order breakdown and timeline.
    
- **Automated Confirmation**
    
    Email or SMS confirmation after order placement.
    
- **Payment Options**
    - Cash on Delivery (COD)
    - Online Payment
    - Wallet Payment

---

# 💳 Payment & Wallet System

> Not just a payment gateway — a full financial ecosystem
> 

##  Payment Integration

- Initiate payments via payment API
- Verify completed payments
- Process refunds

---

##  Payment Verification & Validation

- Validate Transaction ID (non-duplicate)
- Verify paid amount matches order amount
- Confirm correct Order ID

---

##  Multiple Payment Methods

- Credit Cards
- Debit Cards
- Digital Wallets
- Cash on Delivery (COD)

---

##  Transaction Management

- **Restaurant Dashboard**
    - View successful, failed, and refunded transactions
- **System Dashboard**
    - Global view of all platform transactions

---

##  Real-Time Payment Status

- Pending
- Completed
- Failed
- Refunded
- Voided

---

##  Digital Receipts

- Automatically generate digital receipts for every successful transaction.

---

##  Security & Error Handling

- Server-side transaction validation
- Secure data handling
- User-friendly error messages

---

##  Auditing & Logging

- Full request & response logging
- Timestamped payment lifecycle records
- Used for debugging and dispute resolution

---

##  Financial Auditing

- Revenue reconciliation
- Vendor payouts calculation
- Platform commission tracking

---

# 🎁 Offers & Promotions

- **Voucher Codes**
    
    Apply promo codes during checkout.
    
- **Restaurant Offers**
    
    Deals like *Buy 1 Get 1* or special discounts.
    

---

# 📊 Analytics & Dashboard (System)

##  Platform Statistics

- Total Restaurants Count
- Total Customers Count
- Active Customers Count
- Daily Orders Count
- Total Orders Count
- Daily Cancelled Orders
- Total Cancelled Orders

---

##  Financial Metrics

- Daily Transactions Amount
- Total Transactions Amount
- Daily Financial Report
- Monthly Financial Report

---

# 🏪 Analytics & Dashboard (Restaurant)

##  Order Analytics

- Daily Orders Count
- Daily Undelivered Orders
- Total Orders Count
- Daily Cancelled Orders
- Total Cancelled Orders

---

##  Financial Analytics

- Daily Sales Amount
- Total Sales Amount

---

##  Reports & Insights

### Daily Transactions Report

Includes:

- Total orders
- Successful & canceled orders
- Total revenue
- Platform commission
- Net payout for restaurant

### Monthly Transactions Report

Helps restaurants with:

- Accounting
- Performance analysis
- Revenue tracking

---

##  Localization & Regional Settings

Designed to support users across different regions and cultures.

- **Multi-Language Support**
    
    The platform allows users to seamlessly switch between multiple languages such as English, Arabic, and more.
    
- **Multi-Region & Currency Support**
    
    Supports multiple countries with localized currencies, formats, and regional settings.
    
- **Smart Region Detection**
    
    Automatically detects the user’s location using IP address or GPS data on first launch to deliver localized content, pricing, and currency.

---
# 📝 USE CASE: PLACE ORDER

##  FLOW CHART

```mermaid
flowchart TD
    A([Start]) --> B([Browse restaurants and products])
    B --> C([Add product to cart])
    C --> D([Enter cart])
    D --> E([Increase or decrease quantity / Add product])
    E --> F{Quantity = 0?}
    F -- Yes --> G([End])
    F -- No --> H([Continue browsing or proceed to checkout])
    H --> I([Choose address: Add new / Select from saved / Use default])
    I --> J{Is address available?}
    J -- No --> K([Enter new address])
    J -- Yes --> L([Check for voucher])
    K --> L
    L --> M{Is voucher available?}
    M -- Yes --> N([Apply voucher])
    M -- No --> O([Choose payment method])
    N --> O
    O --> P{Pay by card or Cash on Delivery?}
    P -- Card --> Q([Enter card details])
    P -- COD --> R([Confirm order])
    Q --> R
    R --> S([Place order])
```

##  Sequence Diagram

```mermaid
sequenceDiagram
    actor User
    participant System
    participant DB
    participant PaySystem
    participant SMSSystem

    User->>System: Enter system
    User->>System: Browse restaurants and products
    User->>System: Add product to cart
    System->>User: Show message "View cart"
    User->>System: Enter cart
    User->>System: Add/Increase/Decrease quantity
    alt Quantity = 0
        System->>User: Send message "There is nothing in your cart yet"
    else Quantity > 0
        User->>System: Continue browsing or go to checkout
        alt Go to checkout
            System->>DB: Get addresses
            DB-->>System: Return addresses
            System->>User: Show addresses
            alt Use default or saved address
                User->>System: Choose address
            else Add new address
                User->>System: Enter new address details
                System->>DB: Save new address
            end
            User->>System: Enter voucher (if found)
            alt Pay by card
                User->>System: Enter card details
                System->>PaySystem: Send payment request
                PaySystem-->>System: Send payment response
                System->>DB: Validate and update payment status
            else Cash on Delivery
                User->>System: Place order
            end
        end
    end
    System->>SMSSystem: Send order confirmation
    SMSSystem-->>User: Notify order placed

```

##  Pseudocode

```js 
FUNCTION PlaceOrder(user_id, cart_id, payment_method, address_id, voucher_code):

    // 1. User enters system
    // Actor: User
    DISPLAY "Welcome to Food App"

    // 2. User browsing
    // Actor: User
    products = System.BrowseRestaurantsAndProducts()
    UserAddsToCart(cart_id, products)

    // 3. System shows cart message
    // Actor: System
    System.ShowMessage("View cart")

    // 4. User enters cart and modifies quantity
    // Actor: User
    cart_items = System.GetCartItems(cart_id)
    UserModifyQuantity(cart_items)

    IF CartIsEmpty(cart_items):
        // Actor: System
        System.ShowMessage("There is nothing in your cart yet")
        RETURN Error("Cart empty")
    ELSE:
        UserChoosesNextAction = GetUserChoice("Continue browsing / Checkout")
        IF UserChoosesNextAction == "Checkout":

            // 5. Address handling
            // Actor: System & DB
            addresses = DB.GetAddresses(user_id)
            chosen_address = UserChooseAddress(addresses)

            IF chosen_address == "New Address":
                new_address = UserEnterAddressDetails()
                DB.SaveAddress(user_id, new_address)
                chosen_address = new_address

            // 6. Voucher
            voucher = UserEnterVoucher(voucher_code)
            IF voucher != None:
                System.ApplyVoucher(voucher)

            // 7. Payment Processing
            IF payment_method == "Card":
                card_details = UserEnterCardDetails()
                TRY:
                    payment_response = PaySystem.ProcessPayment(card_details, cart_items.total)
                    System.ValidatePayment(payment_response)
                    DB.UpdatePaymentStatus(cart_id, payment_response.status)
                CATCH Exception:
                    RETURN Error("Payment failed")
            ELSE IF payment_method == "Cash":
                System.PlaceOrder(cart_id, chosen_address, payment_method)

            // 8. Notification
            System.SendNotification("Order confirmed", user_id)
            SMSSystem.SendSMS("Order placed successfully", user_id)

    RETURN Success("Order completed")
END FUNCTION

```

---

# Database ERD 

## 🧱 STEP 1: ENTITIES

### 👤 User & Access

* User
* UserType
* Role
* UserRole
* Customer

---

### 🍴 Restaurant & Menu

* Restaurant
* RestaurantDetails
* RestaurantWorkingHours
* Menu
* MenuItem

---

### 🛒 Cart

* Cart
* CartItem

---

## 🧩 STEP 2: ATTRIBUTES 

### 👤 User

```
User
- user_id (PK)
- email (Unique)
- password_hash
- user_type_id (FK)
- is_active
- created_at
```

---

### 👤 UserType

```
UserType
- user_type_id (PK)
- name (Customer, RestaurantOwner, Admin)
```

---

### 👤 Role

```
Role
- role_id (PK)
- name (ManageMenu, ViewOrders, ManageCart)
```

---

### 👤 UserRole

```
UserRole
- user_id (FK)
- role_id (FK)
```

---

### 👤 Customer

```
Customer
- customer_id (PK)
- user_id (FK)
- phone
- default_address
```

---

### 🍴 Restaurant

```
Restaurant
- restaurant_id (PK)
- name
- food_type
- is_active
- owner_user_id (FK → User)
- created_at
```

---

### 🍴 RestaurantDetails

```
RestaurantDetails
- restaurant_id (PK & FK)
- description
- phone
- email
- address
- logo_url
```

---

### 🍴 RestaurantWorkingHours

```
RestaurantWorkingHours
- id (PK)
- restaurant_id (FK)
- day_of_week
- open_time
- close_time
```

---

### 📋 Menu

```
Menu
- menu_id (PK)
- restaurant_id (FK)
- name
- is_active
```

---

### 📋 MenuItem

```
MenuItem
- menu_item_id (PK)
- menu_id (FK)
- name
- description
- price
- is_available
```

---

### 🛒 Cart

```
Cart
- cart_id (PK)
- user_id (FK)
- status (Active, CheckedOut, Abandoned)
- created_at
```

---

### 🛒 CartItem

```
CartItem
- cart_item_id (PK)
- cart_id (FK)
- menu_item_id (FK)
- quantity
- price_at_time
```

### Order

```
Order
- order_id (PK)
- customer_id (FK)
- resturant_id (FK)
- order_date
- status
- payment_status
- total_amount
- currency
- delivery_address_info
- notes
```
### Order Item

```
OrderItem
- order_item_id (PK)
- order_id (FK)
- menu_item_id (FK)
- quantity
- unit_price
- total_price

```

### Payment Method

```
PaymentMethod
- payment_method_id (PK)
- name
```

### Transaction Status

```
TransactionStatus
- transaction_status_id (PK)
- name
```

### Payment

```
Payment
- payment_id (PK)
- order_id (FK)
- Payment_method_id (FK)
- amount
- currency
- status
- created_At
```

### Transaction

```
Transaction
- transaction_id (PK)
- payment_id (FK)
- transaction_status_id (FK)
- gateway_transaction_id
- transaction_amount
- transaction_date
```

---

## 🔗 STEP 3: RELATIONSHIPS 

#### User ↔ UserType

```
User * ---- 1 UserType
```

---

#### User ↔ Role

```
User * ---- * Role
(via UserRole)
```

---

#### User ↔ Customer

```
User 1 ---- 0..1 Customer
```

---

#### User ↔ Restaurant

```
User 1 ---- * Restaurant
(Owner)
```

---

#### Restaurant ↔ Menu

```
Restaurant 1 ---- * Menu
```

---

#### Menu ↔ MenuItem

```
Menu 1 ---- * MenuItem
```

---

#### Customer ↔ Cart

```
Customer 1 ---- * Cart

```

---

#### Cart ↔ CartItem

```
Cart 1 ---- * CartItem
```

---

#### MenuItem ↔ CartItem

```
MenuItem 1 ---- * CartItem
```

---

## ⛓ STEP 4: CONSTRAINTS

### 🔐 Uniqueness

* User.email UNIQUE
* UserType.name UNIQUE
* Role.name UNIQUE
* MenuItem (menu_id, name) UNIQUE

---


##  ERD Diagram

```mermaid
---
config:
  theme: redux-color
---
erDiagram
    USER {
        int user_id PK
        string email UK
        string password_hash
        int user_type_id FK
        boolean is_active
        datetime created_at
    }
    USERTYPE {
        int user_type_id PK
        string name UK
    }
    ROLE {
        int role_id PK
        string name UK
    }
    USERROLE {
        int user_id FK
        int role_id FK
    }
    CUSTOMER {
        int customer_id PK
        int user_id FK
        string phone
        string default_address
    }
    RESTAURANT {
        int restaurant_id PK
        string name
        string food_type
        boolean is_active
        int owner_user_id FK
        datetime created_at
    }
    RESTAURANTDETAILS {
        int restaurant_id PK,FK
        string description
        string phone
        string email
        string address
        string logo_url
    }
    RESTAURANTWORKINGHOURS {
        int id PK
        int restaurant_id FK
        string day_of_week
        string open_time
        string close_time
    }
    MENU {
        int menu_id PK
        int restaurant_id FK
        string name
        boolean is_active
    }
    MENUITEM {
        int menu_item_id PK
        int menu_id FK
        string name
        string description
        float price
        boolean is_available
    }
    CART {
        int cart_id PK
        int user_id FK
        string status
        datetime created_at
    }
    CARTITEM {
        int cart_item_id PK
        int cart_id FK
        int menu_item_id FK
        int quantity
        float price_at_time
    }
USERTYPE ||--o{ USER : "has users"
    USER ||--|| CUSTOMER : "is a"
     USER ||--o{ RESTAURANT : "owns"
CUSTOMER ||--o{ CART : "creates"
USER ||--o{ USERROLE : "has roles"
ROLE ||--o{ USERROLE : "assigned to users"
    RESTAURANT ||--o{ MENU : "has"
   RESTAURANT ||--|| RESTAURANTDETAILS : "details"
RESTAURANT ||--o{ RESTAURANTWORKINGHOURS : "working hours"
    MENU ||--o{ MENUITEM : "contains"
    CART ||--o{ CARTITEM : "has"
    MENUITEM ||--o{ CARTITEM : "added to"
```
