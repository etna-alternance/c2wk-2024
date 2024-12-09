
---

### **Workshop Title: Building and Dockerizing Full-Stack Apps with GitLab CI/CD**  
---

### **1. Workshop Objectives**  
By the end of this workshop, you will:  
1. **🛠️ Setup:** Create a GitLab project for a full-stack application.  
2. **🔧 Build:** Set up a pipeline to build the React frontend and Express backend.  
3. **✅ Test:** Write and execute automated tests for both frontend and backend.  
4. **🐳 Dockerize:** Build Docker images for both the backend and frontend.  
5. **🚀 Deploy:** Push the Docker images to a registry (e.g., GitLab Container Registry) and optionally run them locally or on a cloud platform.  

---

### **2. Prerequisites**  
1. **Tools Needed:**  
   - GitLab account  
   - Git installed  
   - Docker installed  
   - Node.js and npm  

2. **Skills:**  
   - Familiarity with TypeScript, React, and Express.  
   - Basic understanding of Git, GitLab, and Docker.  

---

### **3. Workshop Step-by-Step**  

#### **Step 1: Plan the CI/CD Pipeline 🛠️**  
1. Define the stages for your pipeline. You’ll need stages for:  
   - Installing dependencies.  
   - Building the application.  
   - Running tests.  
   - Creating Docker images.  
   - Pushing Docker images to a registry.  

2. Think about the jobs and tasks you’ll perform in each stage.  

---

#### **Step 2: Write the `.gitlab-ci.yml` File 🛠️**  
1. Create a `.gitlab-ci.yml` file in the root of your project.  
2. Add placeholders for each stage.  
3. Define variables for the Docker image names and tags.  

---

#### **Step 3: Install Stage 🔧**  
1. Add a job for the `install` stage to install dependencies.  
2. Specify how to install the dependencies for both the backend and frontend.  

---

#### **Step 4: Build Stage 🔧**  
1. Add a job for the `build` stage to handle both services.  
2. Think about how you’ll compile the backend TypeScript code and build the frontend React app.  

---

#### **Step 5: Test Stage ✅**  
1. Add a `test` stage to run tests for both services.  
2. Write basic tests for the backend API and the frontend React components.  
3. Define the commands to execute these tests in the pipeline.  

---

#### **Step 6: Dockerize Stage 🐳**  
1. Write a **Dockerfile** for both the backend and frontend.  
2. Add a job for the `dockerize` stage to build Docker images for both services.  
3. Specify how you’ll build the images and tag them with unique identifiers (e.g., the GitLab commit SHA).  

---

#### **Step 7: Publish Stage 🚀**  
1. Configure the `publish` stage to push your Docker images to GitLab’s Container Registry.  
2. Think about the commands you’ll need to log in to the registry and push the images.  
3. Check how to access the registry URL and authentication details in GitLab’s documentation.  

---

#### **Step 8: Run the Pipeline 🚀**  
1. Push your `.gitlab-ci.yml` file to the repository.  
2. Monitor the pipeline as it runs.  
3. Debug any issues by checking the logs for each job.  

---

#### **Optional Step 9: Deploy Locally 🚀**  
1. Once your images are in the registry, figure out how to pull them locally using `docker pull`.  
2. Run the containers for your backend and frontend using the images from the registry.  
3. Test the application in your browser.  

---

### **4. Final Challenge for You**  
Now that your pipeline is complete:  
1. Ensure it installs dependencies, builds, tests, and creates Docker images for both services.  
2. Confirm the images are successfully pushed to the GitLab Container Registry.  
3. Optionally, try deploying your Docker images on a cloud platform or orchestrator like Kubernetes.

Explore additional features of GitLab CI/CD, such as environment variables, caching, and conditional jobs, to enhance your pipeline.
