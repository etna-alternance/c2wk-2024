### **Workshop Topic: Encryption and Security with Bcrypt and SHA-256**

In this workshop, we’ll explore the critical topic of **encryption and security** in modern applications. Protecting sensitive information such as passwords is essential, and we'll learn how to use **Bcrypt** and **SHA-256**, two widely used hashing algorithms, to achieve this.

The goal is to help you understand:
1. Why encryption and hashing are important.
2. The differences between Bcrypt and SHA-256.
3. How to implement secure practices in a Node.js environment.

---

### **Learning Objectives**

By the end of this workshop, you will:
- 🛡 Understand the difference between **encryption**, **hashing**, and **salting**.
- 🔐 Use **Bcrypt** to hash and verify passwords securely.
- 🧮 Learn about **SHA-256** and where it fits in cryptographic processes.
- 👨‍💻 Implement hashing and encryption in your own Node.js application.

---

### **Step 1: Understand the Basics**  

#### **What is Hashing?**
- 🏗 **Definition**: Hashing is the process of transforming input data (e.g., a password) into a fixed-size string of characters, which represents the data uniquely.
- 💡 **Key Property**: It’s a one-way function—meaning you can’t reverse the hash to get the original data.
- Example Algorithms: MD5, SHA-256, Bcrypt.

#### **What is Salting?**
- 🌊 **Definition**: Adding a unique random value (salt) to the input before hashing to protect against precomputed attacks (like rainbow tables).
- Bcrypt has built-in salting. With SHA-256, you need to handle the salt manually.

#### **Encryption vs. Hashing**
- 🔑 **Encryption**: A two-way process where data is encoded and can be decoded using a key.
- 🔐 **Hashing**: A one-way process that secures data but cannot be reversed.

---

### **Step 2: Compare Bcrypt and SHA-256**

| Feature               | Bcrypt                           | SHA-256                          |
|-----------------------|-----------------------------------|-----------------------------------|
| **Type**             | Adaptive hashing                 | Cryptographic hash function      |
| **Salting**          | Built-in                         | Manual                           |
| **Use Case**         | Password hashing                 | General-purpose cryptographic needs (e.g., digital signatures) |
| **Strength**         | Adjustable cost factor           | Fixed complexity                 |
| **Security**         | Resistant to brute force attacks | Faster but less adaptable        |

---

### **Step 3: Practical Examples**  

#### **Bcrypt: Hash and Verify Passwords**
Bcrypt is ideal for password hashing because it’s slow (deliberately!) and resists brute force attacks. Here's what you'll need to think about:
1. Use the `bcrypt` library.
2. Hash passwords when they’re created.
3. Verify hashed passwords during login.

👉 Tasks for you:  
- Install Bcrypt in a Node.js project:  
  ```bash
  npm install bcrypt
  ```
- Think about how the **salt rounds** setting affects the strength and speed of hashing. What would you choose for a balance?

#### **SHA-256: Hashing Data**
SHA-256 is fast and widely used for general-purpose hashing. It doesn’t have built-in salting, so you’ll need to generate and store the salt yourself. It’s great for tasks like creating digital signatures or file verification but less ideal for password hashing.

👉 Tasks for you:  
- Use the `crypto` module in Node.js to hash data with SHA-256.  
- Explore adding a salt to your hash. Why is this important?

---

### **Step 4: Security Best Practices**  

- 🛡 **Always hash passwords before storing them**: Never save plaintext passwords in your database.  
- 🌟 **Use salting**: This ensures each hash is unique, even for identical passwords.  
- ⚙️ **Understand your algorithm**: Choose the right hashing algorithm for your use case (e.g., Bcrypt for passwords, SHA-256 for digital signatures).  
- 🔐 **Use secure connections**: Always transmit data over HTTPS to avoid interception.

---

### **Step 5: Challenges**

#### **Challenge 1: Password Storage**
- Write a function that:
  1. Hashes a password using Bcrypt.
  2. Verifies if a provided password matches the hashed one.
- Test your function with different password lengths and salt rounds.

#### **Challenge 2: SHA-256 Salting**
- Write a function to:
  1. Hash a string (e.g., an API key) using SHA-256.
  2. Add a unique salt and verify the integrity of the original string.

#### **Challenge 3: Compare Speed**
- Measure the time it takes to hash a password using Bcrypt and SHA-256.  
- Experiment with different salt rounds for Bcrypt. How does it impact performance?

---

### **Documentation and References**
- **Bcrypt**: [Bcrypt GitHub Repository](https://github.com/kelektiv/node.bcrypt.js)  
- **SHA-256**: [Node.js Crypto Documentation](https://nodejs.org/api/crypto.html#crypto_crypto_createhash_algorithm_options)  
- **Password Security**: [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)  

---

### **Final Thoughts**  
Hashing and encryption are foundational to modern web security. Understanding how and when to use tools like **Bcrypt** and **SHA-256** will make your applications more secure and protect your users' data from potential attacks.  

Let’s build a secure application! 🔐
