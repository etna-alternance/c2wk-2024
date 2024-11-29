# 🌟 **Workshop: Managing Git Branches, Pull Requests, Resolving Conflicts, and Using Stash**

## 🕒 **Duration:** 1h - 1h30  
### 🎯 **Objective:**  
Learn to:  
1. 📂 Create and manage Git branches effectively.  
2. ✅ Use pull requests (PRs).  
3. 🔧 Resolve conflicts with `git rebase` and follow best practices.  
4. 📬 Manage temporary changes with `git stash`.  
5. 🪄 Merge changes cleanly into the `main` branch.  

---

## 🛠️ **Workshop Steps**  

### **Step 1: Create a Git Repository**  

1. 🖥️ **Create a new repository** on GitLab and clone it:  
   ```bash
   git clone <REPO_URL>
   cd <REPO_NAME>
   ```  

2. 📄 **Add a `.gitignore` file** (optional but recommended):  
   ```bash
   echo "node_modules/" > .gitignore
   git add .gitignore
   git commit -m "Add .gitignore file"
   ```  

3. 🚀 **Push the repository** to a remote service:  
   ```bash
   git push origin main  # or master
   ```  

---

### **Step 2: Create a `develop` Branch**  

1. 🌱 **Create a `develop` branch** from `main` and switch to it:  
   ```bash
   git switch -c develop
   ```  

2. 📤 **Push the `develop` branch** to the remote repository:  
   ```bash
   git push --set-upstream origin develop
   ```  

---

### **Step 3: Add a TypeScript Program**  

1. ✍️ **Create a `hello-world.ts` file** with the following code:  
   ```typescript
   // hello-world.ts
   const greet = (name: string): string => {
       return `Hello, ${name}!`;
   };

   console.log(greet("World"));
   ```  

2. 📦 **Initialize the project** with a `package.json`:  
   ```bash
   npm init -y
   ```  

3. 🔧 **Install TypeScript** as a dev dependency:  
   ```bash
   npm install typescript --save-dev
   ```  

4. 📂 **Stage, commit, and push the changes**:  
   ```bash
   git add .
   git commit -m "add: hello-world.ts"
   git push origin develop
   ```  

---

### **Step 4: Using Git Stash**  

1. 🔄 **Switch back to the `develop` branch**:  
   ```bash
   git switch develop
   ```  

2. ✏️ **Make an incomplete change to `hello-world.ts` without committing it**:  
   ```typescript
   const greet = (name: string): string => {
       return `Hello, ${name}!`;
   };

   // Unfinished feature:
   const farewell = (name: string): string => {
       return `Goodbye, ${name}!`;
   };
   ```  

3. ⚡ **Stash the changes temporarily** to work on something else:  
   ```bash
   git stash push -m "WIP: Add farewell function"
   ```  

4. 🚀 **Switch to a new branch to fix a bug or implement a feature**:  
   ```bash
   git switch -c feature/fix-bug
   ```  

5. 🛠️ **Fix the bug or add the feature**, commit, and push as usual:  
   ```bash
   // Example of changes for fixing a bug.
   git add .
   git commit -m "Fix: Resolved greeting bug"
   git push --set-upstream origin feature/fix-bug
   ```  

6. 🔙 **Return to the `develop` branch** and apply the stashed changes:  
   ```bash
   git switch develop
   git stash apply
   ```  

7. 🔧 **Continue working on the stashed changes**, stage, and commit them:  
   ```bash
   git add .
   git commit -m "Add farewell function"
   git push origin develop
   ```  

---

### **Step 5: Create Feature Branches**  

#### 🌟 **First Branch:** `feature/add-greeting`  

1. 🌿 **Create a new branch**:  
   ```bash
   git switch -c feature/add-greeting
   ```  

2. 🛠️ **Modify `hello-world.ts`** to include a personalized greeting:  
   ```typescript
   const greet = (name: string, timeOfDay: string): string => {
       return `Good ${timeOfDay}, ${name}!`;
   };

   console.log(greet("World", "morning"));
   ```  

3. 💾 **Stage, commit, and push the changes**:  
   ```bash
   git add hello-world.ts
   git commit -m "Add personalized greeting with time of day"
   git push --set-upstream origin feature/add-greeting
   ```  

#### 🌟 **Second Branch:** `feature/change-greeting-style`  

1. 🔄 **Switch back to the `develop` branch** and create a second branch:  
   ```bash
   git checkout develop
   git pull origin develop
   git switch -c feature/change-greeting-style
   ```  

2. ✨ **Modify `hello-world.ts`** to change the greeting format:  
   ```typescript
   const greet = (name: string): string => {
       return `Hello there, ${name}!`;
   };

   console.log(greet("World"));
   ```  

3. 💾 **Stage, commit, and push the changes**:  
   ```bash
   git add hello-world.ts
   git commit -m "Change greeting format"
   git push --set-upstream origin feature/change-greeting-style
   ```  

---

### **Step 6: Merge Changes Using Pull Requests**  

1. 📝 **Create a PR** to merge `feature/add-greeting` into `develop`.  
2. ✅ **Merge the PR** into `develop`.  

3. 📝 **Create another PR** to merge `feature/change-greeting-style` into `develop`.  
   - ⚠️ **A conflict will occur** because both branches modified `hello-world.ts`.  

---

### **Step 7: Resolve Conflicts with Git Rebase**  

1. 🔄 **Check out the conflicting branch**:  
   ```bash
   git switch feature/change-greeting-style
   ```  

2. 🔧 **Rebase onto `develop`** to resolve conflicts:  
   ```bash
   git rebase develop
   ```  

3. 🛠️ **Resolve the conflict** in `hello-world.ts` by combining changes:  
   ```typescript
   const greet = (name: string, timeOfDay?: string): string => {
       if (timeOfDay) {
           return `Good ${timeOfDay}, ${name}!`;
       }
       return `Hello there, ${name}!`;
   };

   console.log(greet("World", "morning"));
   ```  

4. ✅ **Mark the conflict as resolved** and continue the rebase:  
   ```bash
   git add hello-world.ts
   git rebase --continue
   ```  

5. 📤 **Push the rebased branch** to the remote repository:  
   ```bash
   git push --force-with-lease
   ```  

6. ✅ **Merge the rebased branch** into `develop`.  

---

### **Step 8: Merge into `main`**  

1. 🌟 **Merge the updated `develop` branch** into `main`:  
   ```bash
   git switch main
   git merge develop
   git push origin main
   ```  

---

## 🎉 **Congratulations!** You’ve successfully:  
- Managed branches effectively.  
- Used pull requests to merge changes.  
- Used Git stash to handle temporary changes.  
- Resolved conflicts using `git rebase`.  
- Cleanly merged everything into the `main` branch. 🚀  