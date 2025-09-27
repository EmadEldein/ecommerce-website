<p align="center">
  <img src="logolight.svg" alt="Eco Commerce Logo" width="120"/>
</p>

## 🚀 Project Name
**Eco e-Commerce** — A modern, flexible, and scalable e-commerce database structure.

# 🌍 Eco Commerce

## 📌 Overview
Eco Commerce is a modern **E-Commerce database schema** built with **Prisma ORM**.  
It’s designed to be flexible, scalable, and optimized for SEO-friendly product & category pages.  

---

## 📂 Core Models

### 🛍️ Product
Represents an item available in the store.

Fields:
- `id` → Product ID.
- `name` → Product name.
- `slug` → SEO-friendly unique slug.
- `description` → Product description.
- `price` → Base price.
- `discount` → Optional discount.
- `freeDelivery` → Free delivery flag.
- `imageUrl` → Main product image.
- `thumbnailUrl` → Thumbnail image.
- `images` → Additional product images (gallery).
- `variants` → Product variations (colors, sizes, etc).
- `categoryId` → Linked category.
- `createdAt` / `updatedAt`.

---

### 🖼️ ProductImage
Extra images for a product.

Fields:
- `id`
- `url`
- `productId`

---

### 🎨 ProductVariant
Allows products to have multiple variations.

Fields:
- `id`
- `name` (e.g., "Red - Large")
- `sku` (unique stock code)
- `price` (optional variant price)
- `stock` (inventory quantity)
- `productId`

---

### 🗂️ Category
Product categorization.

Fields:
- `id`
- `name`
- `slug` (SEO-friendly unique slug)
- `description`
- `imageUrl`
- `products`

---

## 🔗 Slugs
- Products → `/products/laptop-dell-inspiron`
- Categories → `/categories/electronics`

> Slugs are unique and auto-generated from names. Example: `"T-Shirt"` → `t-shirt`.

---

## 🖼️ Image Handling
It is recommended to use external storage:
- [Cloudinary](https://cloudinary.com)
- [Amazon S3](https://aws.amazon.com/s3/)

---

## 📊 Example

**Product:** T-Shirt  
- slug: `t-shirt`  
- price: 200  
- discount: 10  
- freeDelivery: true  
- imageUrl: `https://cdn.eco-commerce.com/products/tshirt-main.jpg`  
- thumbnailUrl: `https://cdn.eco-commerce.com/products/tshirt-thumb.jpg`  

**Variants:**
1. "Red - M" | SKU: `TSHIRT-RED-M` | Price: 200 | Stock: 10  
2. "Blue - L" | SKU: `TSHIRT-BLUE-L` | Price: 210 | Stock: 5  

**Gallery:**
- `https://cdn.eco-commerce.com/products/tshirt-side.jpg`  
- `https://cdn.eco-commerce.com/products/tshirt-back.jpg`  

**Category:**
- name: Clothing  
- slug: `clothing`  
- description: "Trendy fashion apparel"  
- imageUrl: `https://cdn.eco-commerce.com/categories/clothing-banner.jpg`  

---

## ⚙️ Tech Notes
- Prisma ORM  
- Auto timestamps (`createdAt`, `updatedAt`)  
- SEO-friendly URLs with slugs  
- Flexible product system (discounts, free delivery, variants, galleries)  

---


