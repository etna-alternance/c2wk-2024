### **Workshop Topic: Advanced Data Management with React Query and Axios**

In this hands-on workshop, we’ll explore how to manage API calls and server-side state efficiently using **React Query** and **Axios** in a React project. This session focuses on **mutations** and **queries** with React Query, showcasing practical patterns for data fetching, caching, and error handling, while promoting clean architecture with services.

---

### **Learning Objectives**

By the end of this workshop, you will:

- 🧩 Learn how to structure React Query hooks for **mutations** and **queries**.
- 🛠 Use **Axios services** to centralize API logic and simplify reuse.
- 🎯 Manage server-state effectively with query keys and mutation strategies.
- 🚀 Implement type-safe patterns using TypeScript for robust code.

---

### **Step 1: Conceptual Foundation**

#### **React Query Overview**

[React Query Docs](https://tanstack.com/query/v3/docs/framework/react/installation)

- **Queries**: Fetch and cache data. Ideal for read operations.
- **Mutations**: Create, update, or delete data. Focused on write operations.
- **Keys**: Identify and organize server state for optimal caching and invalidation.

#### **Axios Services**

- Centralized HTTP logic allows you to manage headers, tokens, and base URLs.
- Clean separation between business logic (services) and UI components.

#### **Benefits of Combining React Query and Axios**

1. Efficient state management with minimal boilerplate.
2. Clear separation of concerns (UI vs. API logic).
3. Enhanced debugging with React Query DevTools.

---

### **Step 2: Implementing React Query Hooks**

#### **Mutations**

- Use `useMutation` for creating or modifying server data.
- Customize behavior with `mutationFn`, `onSuccess`, and `onError`.

**Task**:

- Implement a mutation for user registration (`useUserCreate`).
- Think about:
  - What happens on success (e.g., show a toast notification)?
  - How will you handle errors gracefully?

---

#### **Queries**

- Use `useQuery` to fetch and cache server data.
- Optimize queries with retry logic, stale time, and query keys.

**Task**:

- Set up a query to fetch user information (`useGetUser`).
- Explore:
  - How retries and caching work out of the box.
  - How to manage query keys for distinct data.

---

### **Step 3: Hands-On with API Services**

#### **Service Layer Design**

- Centralize all API logic in a service class, such as `userService`.
- Create reusable methods like `CreateUser`, `UserLogin`, and `GetUserInfo`.

**Your Tasks**:

1. Investigate how Axios handles requests:
   - What are the benefits of using an instance (`Fetch`) with a base URL and headers?
2. Explore error handling at the service level:
   - What should happen when the API returns a `401` or `500` error?

---

### **Step 4: Building the Application**

#### **Combine Hooks and Services**

- Connect `useMutation` and `useQuery` hooks to methods in `userService`.
- Pass type-safe arguments (e.g., `UserLogin`, `UserRegister`) to mutations.

#### **Manage Side Effects**

- Explore how to:
  - **Invalidate Queries**: Automatically refresh data after a mutation.
  - **Show Notifications**: Inform users about success or failure.
  - **Retry Logic**: Control retry behavior for failed queries.

---

### **Step 5: Challenges**

#### **Challenge 1: Create and Login Users**

- Use `useUserCreate` and `useUserLogin` to manage user creation and login flows.
- Customize hooks to handle:
  - Success (e.g., store tokens).
  - Errors (e.g., show error messages).

#### **Challenge 2: Fetch and Display User Info**

- Use `useGetUser` to fetch user details.
- Think about:
  - How to display a loading state.
  - How to handle a `403` error if the user is not authenticated.

#### **Challenge 3: Handle Token Expiry**

- Use Axios interceptors to refresh tokens seamlessly.
- Experiment with:
  - Re-trying failed queries automatically after refreshing tokens.

---

### **Best Practices**

1. **Use Query and Mutation Keys**:

   - Organize server state with descriptive keys (e.g., `CREATE_USER_KEY`).

2. **Centralize API Logic**:

   - Keep Axios services in a single file to ensure consistency.

3. **Error Handling**:

   - Handle errors at the service level and provide meaningful feedback in the UI.

4. **Type Safety**:

   - Use TypeScript to define request/response types (e.g., `UserLogin`, `AuthToken`).

5. **Leverage DevTools**:
   - Install React Query DevTools for easy debugging:
     ```bash
     npm install @tanstack/react-query-devtools
     ```

---

### **Final Thoughts**

This workshop has introduced the tools and patterns to build scalable, type-safe React applications using **React Query** and **Axios**. By centralizing API logic and leveraging React Query’s hooks, you can streamline data fetching and state management while maintaining a clean architecture.

Your next steps:

- Build your own hooks for CRUD operations.
- Experiment with query invalidation.
- Explore advanced features like pagination and token management.

Happy coding! 🚀
