### 🚀 **Workshop: Building an Airbnb-Like Model with Prisma and Express** 🚀

Welcome to this part of the workshop, where we’ll design a backend for an Airbnb-like application using **Prisma** and **Express**! Not only will you define models for **Users 👤**, **Properties 🏡**, and **Bookings 📅**, but you’ll also learn how to connect your API to a database through Prisma and serve it using Express.  

By the end of this task, you’ll have an Express server that interacts with your database using Prisma.

---

### **Step 1: Plan the Data Models**  
Before coding, think about the core entities for an Airbnb-like app. Here’s a suggested breakdown:  

- **👤 User**
  - Represents hosts and guests.  
  - Fields to consider: `name`, `email`, `password`, `createdAt`.  
  - Relationship: A user can own multiple properties and make bookings.

- **🏡 Property**
  - Represents listings like houses or apartments.  
  - Fields to consider: `title`, `description`, `price`, `location`, `createdAt`.  
  - Relationship: A property belongs to one user (host) and can have multiple bookings.

- **📅 Booking**
  - Represents a reservation for a property by a guest.  
  - Fields to consider: `checkIn`, `checkOut`, `totalPrice`, `createdAt`.  
  - Relationship: A booking connects to both a property and a user (guest).

Draw a simple diagram or write down these relationships in a notebook to visualize them before proceeding.  

---

### **Step 2: Set Up Prisma**  
1. **Install Prisma**:  
   ```bash
   npm install prisma --save-dev
   npx prisma init
   ```

2. **Define Models**:  
   Open the `prisma/schema.prisma` file and start defining the models (check the **Documentation References** section for help). Use comments with emojis to make the schema visually engaging:  

   ```prisma
   // 👤 User model
   model User {
       // Add fields like id, name, email, etc.
   }

   // 🏡 Property model
   model Property {
       // Add fields like id, title, description, etc.
   }

   // 📅 Booking model
   model Booking {
       // Add fields like id, checkIn, checkOut, etc.
   }
   ```

---

### **Step 3: Connect to a Database**  
1. **Database Setup**:  
   Prisma needs a database connection string. Edit the `DATABASE_URL` in your `.env` file:  

   - Example for SQLite (development only):  
     ```plaintext
     DATABASE_URL="file:./dev.db"
     ```
   - For Postgres or MySQL, update the connection string accordingly.  

2. **Migrate Your Models**:  
   After defining your models, create the database structure by running:  
   ```bash
   npx prisma migrate dev --name init_airbnb_models
   ```

---

### **Step 4: Set Up Express**  
1. **Install Express and Prisma Client**:  
   In your project, install the required dependencies:  
   ```bash
   npm install express @prisma/client
   ```

2. **Initialize Prisma Client**:  
   Add the Prisma Client to your Express server file (e.g., `index.js`):  
   ```javascript
   const express = require('express');
   const { PrismaClient } = require('@prisma/client');

   const prisma = new PrismaClient();
   const app = express();

   app.use(express.json());
   ```

3. **Connect Express to Your Database**:  
   Think about what routes you’ll need to perform CRUD operations for your models. For example:
   - `POST /users` to create a user 👤.
   - `GET /properties` to list all properties 🏡.
   - `POST /bookings` to make a booking 📅.

   Here’s a small hint to guide you:  
   ```javascript
   // Example: Create a new user 👤
   app.post('/users', async (req, res) => {
       const { name, email, password } = req.body;
       const user = await prisma.user.create({
           data: { name, email, password },
       });
       res.json(user);
   });
   ```

   Add similar routes for properties and bookings!  

---

### **Step 5: Test Your API**  
Use **Postman** or **Thunder Client** to test your API.  

- **Create Sample Data**:  
  - 👤 Add a user (e.g., `name: "Alice"`).  
  - 🏡 Add a property owned by Alice.  
  - 📅 Make a booking for the property.

- **Verify Data**:  
  Launch Prisma Studio to check if the data is being saved correctly in your database:  
  ```bash
  npx prisma studio
  ```

---

### **Documentation References**  
- **Prisma Setup and Models**: [Prisma Docs](https://www.prisma.io/docs/getting-started)  
- **Express Integration**: [Express Docs](https://expressjs.com/)  
- **CRUD with Prisma**: [Prisma Client API](https://www.prisma.io/docs/reference/api-reference/prisma-client-reference)  

---

### **Challenges to Extend**  
- Add **⭐ Reviews**: Users can review properties. How would you model this?  
- Add **🏷️ Tags**: Properties can have tags like "Luxury," "Pet-Friendly," etc.  
- Add **🖼️ Images**: Allow properties to have multiple images.  

---

Take your time to think through each step. Building this backend will give you hands-on experience with both Prisma and Express, and you’ll understand how to create scalable APIs connected to a database. Let’s code! 🚀