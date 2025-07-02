# DevOps Portfolio Project

<p align="center">
  <img src="https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-blue?logo=githubactions" />
  <img src="https://img.shields.io/badge/Hosted%20On-AWS%20S3-orange?logo=amazonaws" />
  <img src="https://img.shields.io/badge/Built%20With-HTML%2FCSS%2FJS-yellow?logo=html5" />
</p>

A complete DevOps pipeline project that demonstrates automated deployment of a personal portfolio website using Git, GitHub Actions, and AWS S3 static hosting.

## 🚀 Project Overview

This project showcases a full DevOps workflow by automatically deploying a portfolio website to AWS S3 whenever code is pushed to the GitHub repository. The pipeline includes HTML/CSS/JavaScript frontend development, CI/CD automation, and cloud infrastructure setup.

## 🛠️ Tech Stack

- **Frontend**: HTML, CSS, JavaScript
- **Version Control**: Git, GitHub
- **CI/CD**: GitHub Actions
- **Cloud Provider**: Amazon Web Services (AWS)
- **Storage**: AWS S3
- **IAM**: AWS Identity and Access Management

## 📋 Project Structure

```
project-root/
├── index.html                 # Main portfolio HTML file
├── .github/
│   └── workflows/
│       └── main.yml          # GitHub Actions workflow
└── README.md                 # Project documentation
```

## 🔧 Implementation Steps

### Step 1: Frontend Development
Created a portfolio website with:
- `index.html` - Main HTML structure
- Embedded CSS for styling
- JavaScript for interactive features

### Step 2: GitHub Actions Setup
- Created `.github/workflows/main.yml` file
- Configured automated deployment workflow
- Set up triggers for push events

### Step 3: AWS IAM Configuration
1. **Created IAM User**:
   - Navigated to AWS IAM service
   - Created a new IAM user for deployment purposes

2. **Assigned Permissions**:
   - Granted **S3 Full Access** permissions to the IAM user
   - Generated Access Key ID and Secret Access Key

### Step 4: GitHub Secrets Configuration
1. **Repository Settings**:
   - Went to GitHub repository → Settings
   - Navigated to Security → Secrets and Variables → Actions

2. **Added AWS Credentials**:
   - Created new repository secrets:
     - `AWS_ACCESS_KEY_ID`: IAM user's access key
     - `AWS_SECRET_ACCESS_KEY`: IAM user's secret key

### Step 5: AWS S3 Bucket Setup
1. **Bucket Creation**:
   - Created new S3 bucket named `abhishekportfolio027`

2. **Public Access Configuration**:
   - Enabled public access for static website hosting
   - Configured bucket for static website hosting

3. **Bucket Policy**:
   Applied the following policy for public read access:
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::abhishekportfolio027/*"
       }
     ]
   }
   ```

### Step 6: Deployment
1. **Final Configuration**:
   - Updated GitHub Actions workflow with correct S3 bucket name
   - Committed changes to trigger the pipeline

2. **Verification**:
   - Pipeline executed successfully
   - Portfolio deployed to S3 bucket
   - Website accessible via S3 static hosting URL

## 🎯 Key Features

- **Automated Deployment**: Code changes trigger automatic deployment
- **Secure Credentials**: AWS credentials stored as GitHub secrets
- **Static Hosting**: Fast and cost-effective S3 static website hosting
- **Public Access**: Portfolio accessible to anyone via web URL

## 🔐 Security Considerations

- AWS credentials are securely stored in GitHub repository secrets
- IAM user has minimal required permissions (S3 access only)
- S3 bucket policy allows public read access for website content only

## 📊 Benefits Achieved

- **DevOps Integration**: Complete CI/CD pipeline implementation
- **Cloud Infrastructure**: Hands-on AWS services experience
- **Automation**: Reduced manual deployment efforts
- **Scalability**: Cloud-based hosting solution
- **Version Control**: Git-based development workflow

## 🌐 Live Demo

The portfolio is live and accessible at the S3 static website URL after successful deployment.

## 🚀 Future Enhancements

- Add custom domain with Route 53
- Implement CloudFront CDN for better performance
- Add SSL/TLS certificate
- Include automated testing in the pipeline
- Add monitoring and logging capabilities

## 📝 Lessons Learned

This project demonstrates practical DevOps skills including:
- Infrastructure as Code concepts
- CI/CD pipeline design
- Cloud services integration
- Security best practices
- Automated deployment strategies

---

**Note**: Remember to keep your AWS credentials secure and never commit them directly to your repository. Always use GitHub secrets or similar secure storage methods for sensitive information.
