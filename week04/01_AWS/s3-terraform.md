### **Workshop Title: Managing AWS S3 with Terraform**  
---

### **1. Workshop Objectives**  
By the end of this workshop, you will:  
1. **✅ Understand S3 Basics:** Learn the fundamentals of AWS S3.  
2. **🔧 Set Up Terraform:** Set up Terraform to provision cloud resources.  
3. **🛠️ Manage S3 Buckets:** Use Terraform to create and manage S3 buckets in AWS.  
4. **✨ Bonus:** Extend your Terraform configuration to add other AWS resources such as IAM roles, policies, and more.  

---

### **2. Prerequisites**  
1. **Tools Needed:**  
   - AWS account  
   - Terraform installed  
   - AWS CLI configured (with `aws configure`)  

2. **Skills:**  
   - Basic understanding of cloud computing and AWS S3.  
   - Familiarity with Infrastructure as Code (IaC) and Terraform.

---

### **3. Workshop Steps**  

#### **Part 1: Setting Up Terraform**  

**Step 1: Install Terraform**  
1. Ensure that you have Terraform installed on your machine.  
   - **Hint:** Follow the [Terraform installation guide](https://learn.hashicorp.com/tutorials/terraform/install-cli).

**Step 2: Initialize Your Terraform Project**  
1. Create a new directory for your Terraform configuration.  
2. Initialize the directory as a Terraform project with `terraform init`.  
   - **Hint:** Look up how to initialize a Terraform working directory.

**Step 3: Configure AWS Provider**  
1. You need to configure the AWS provider to use your credentials and region.  
2. Create a `provider.tf` file with the AWS provider configuration.  
   - **Hint:** Use `aws` as the provider and specify the region you want to work in. Look up the `provider` block for Terraform.

---

#### **Part 2: Provision an S3 Bucket**  

**Step 4: Create an S3 Bucket with Terraform**  
1. Define the resource for an S3 bucket in a new file, `s3.tf`.  
2. Define the `aws_s3_bucket` resource, providing the name of the bucket and optional configurations (like versioning, region, etc.).  
3. Write a basic S3 bucket configuration in Terraform.  
   - **Hint:** Look up how to create S3 buckets in Terraform. Use `aws_s3_bucket` to define the resource.

```hcl
resource "aws_s3_bucket" "my_bucket" {
  bucket = "my-unique-bucket-name"
  acl    = "private"
}
```

---

#### **Part 3: Manage S3 Bucket Configurations**  

**Step 5: Enable Versioning**  
1. Modify your S3 bucket configuration to enable versioning.  
2. Write the necessary Terraform code to enable versioning for the bucket.  
   - **Hint:** Versioning can be enabled by adding a `versioning` block to the `aws_s3_bucket` resource.

**Step 6: Enable Server-Side Encryption (Optional)**  
1. Add server-side encryption to the S3 bucket.  
2. Configure the bucket to use an AWS-managed encryption key (SSE-S3).  
   - **Hint:** Look for the `server_side_encryption_configuration` block in Terraform’s documentation.

---

#### **Part 4: Use Terraform to Deploy and Manage Resources**  

**Step 7: Apply Your Terraform Configuration**  
1. Run `terraform apply` to provision the S3 bucket and apply your configuration.  
2. Review the changes Terraform will make and confirm the operation.  
3. After the bucket is created, check the AWS Console to see the bucket.

**Step 8: Modify the S3 Bucket**  
1. Modify your S3 bucket configuration (e.g., changing the `acl` to `public-read`, adding lifecycle rules, etc.).  
2. Run `terraform apply` again to apply changes to the bucket.  

---

#### **Bonus Part: Extend with IAM and Permissions**  

**Challenge 1: Add IAM Policy for S3 Access**  
1. Create a new IAM policy to give access to the S3 bucket.  
2. Attach the IAM policy to a user, group, or role.  
3. Use Terraform to define and apply the IAM policy.

**Hint for Students:**  
- Use the `aws_iam_policy` and `aws_iam_user_policy_attachment` resources in Terraform to manage policies and their attachments.

**Challenge 2: Configure S3 Bucket Lifecycle Rules**  
1. Add lifecycle rules to your S3 bucket to transition old objects to Glacier or delete them after a set period.  
2. Write the necessary `lifecycle_rule` configuration in Terraform.  

---

### **Final Challenge for You**  

**Goal:** Extend your Terraform configuration to:  
1. Create an S3 bucket with versioning and encryption.  
2. Add an IAM policy for access management to the S3 bucket.  
3. Set up lifecycle rules for the S3 bucket to automatically archive or delete objects.  
4. Optionally, add an S3 bucket website configuration to serve static content.

---

### **Resources and Documentation**  
1. [Terraform AWS Provider Documentation](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)  
2. [AWS S3 Documentation](https://docs.aws.amazon.com/s3/index.html)  
3. [Terraform CLI Commands](https://www.terraform.io/docs/commands/index.html)

---


