<p align="center">
  <img src="logolight.svg" alt="eco dev. Logo" width="200"/>
</p>

# 🛒 eco dev. E-commerce Database Schema (Prisma)

A **relational database schema** for a modern e-commerce platform built with **Prisma ORM**.  
It supports products, discounts, inventory, orders, payments, shipping, blogs, and more.

---

## 📑 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Entities & Relationships](#entities--relationships)
- [Entity Details](#entity-details)
- [ERD Diagram](#erd-diagram)
- [Setup](#setup)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

---

## 📌 Overview
This schema is designed to support a **full e-commerce workflow** including:
- User authentication and roles
- Product catalog and categories
- Discounts & free shipping
- Inventory management
- Shopping cart
- Orders, payments, shipping tracking
- Customer reviews
- Blog system with posts and comments
- Multiple delivery addresses per user

---

## 🚀 Features
- 👤 Users with roles: **Admin, Assistant, Customer**
- 🏷️ Products with status: **Draft, Active, Archived**
- 🎁 Discounts with **Percentage, Fixed, Free Shipping**
- 📦 Inventory tracking
- 🛒 Shopping cart with unique items per user
- 📑 Orders with payments and shipping
- ⭐ Product reviews
- 📝 Blog posts by Admin/Assistant + comments
- 🏠 Multiple delivery addresses per user

---

## 📂 Entities & Relationships

- **User → Address** (1-to-many)  
- **User → Order** (1-to-many)  
- **User → CartItem** (1-to-many)  
- **User → Review** (1-to-many)  
- **User → BlogPost** (1-to-many, if Admin/Assistant)  
- **User → BlogComment** (1-to-many)  
- **Order → OrderItem** (1-to-many)  
- **Order → Payment** (1-to-1)  
- **Order → Shipping** (1-to-1)  
- **Product → Inventory** (1-to-many)  
- **Product → Discount** (1-to-many)  
- **Category → Product** (1-to-many)  

---

## 📑 Entity Details

### 👤 User
- Roles: `ADMIN`, `ASSISTANT`, `CUSTOMER`
- Has addresses, orders, cart, reviews, blog posts, comments

### 🏠 Address
- Multiple per user  
- Linked to orders  
- Includes full name, phone, city, country, etc.  

### 🛍️ Product
- Belongs to category  
- Fields: `name`, `price`, `stock`, `sku`, `status`  
- Can have **discounts** and inventory logs  

### 🎁 Discount
- Linked to product  
- Type: `PERCENTAGE` or `FIXED`  
- Can include **free shipping** (`freeShipping = true`)  
- Active within `startDate` → `endDate`  

### 📦 Inventory
- Tracks stock changes  
- Fields: `change`, `reason`, `createdAt`  

### 🛒 CartItem
- Links user & product  
- Unique constraint `(userId, productId)`  
- Fields: `quantity`, `addedAt`  

### 📑 Order
- Linked to user + address  
- Contains multiple items  
- Has payment & shipping  

### 💳 Payment
- One per order  
- Fields: `method`, `amount`, `status`, `paidAt`  

### 🚚 Shipping
- One per order  
- Fields: `status`, `carrier`, `trackingNumber`  
- Status: `Pending`, `Shipped`, `Delivered`, `Canceled` 

### ⭐ Review
- User reviews a product  
- Fields: `rating`, `comment`  

### 📝 BlogPost
- Created by Admin/Assistant  
- Fields: `title`, `slug`, `content`, `isPublished`  
- Has comments  

### 💬 BlogComment
- By any user  
- Fields: `comment`, `createdAt`, `isVisible`  

---


