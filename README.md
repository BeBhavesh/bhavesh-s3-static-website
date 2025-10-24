# Bhavesh's Static Website Deployment

This repository hosts a **static website** and an automated **GitHub Actions workflow** to deploy it to **AWS S3**.  
The workflow ensures that every push to `main` (or manual trigger) automatically syncs your website files to the S3 bucket.

---

## 🚀 Features

- Automatic deployment to **AWS S3**
- Supports manual workflow runs with `workflow_dispatch`
- Keeps `.git` and `.github` folders excluded during deployment
- Success message after deployment
- Fully configurable via **GitHub Secrets** for AWS credentials

---

## 📦 Deployment Workflow

The GitHub Actions workflow is defined in `.github/workflows/deploy.yml`:

### Workflow Steps:

1. **Checkout code**
   ```yaml
   uses: actions/checkout@v3

2. Configure AWS credentials

uses: aws-actions/configure-aws-credentials@v4
with:
  aws-access-key-id: ${{ secrets.AWS_ACC
  
  
3. Deploy files to S3

run: aws s3 sync . s3://bhavesh-s3-static-website --exclude ".git/*" --exclude ".github/*" --delete


4. Success message

run: echo "🎉 Website successfully deployed to S3!"
