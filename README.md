

<img width="1347" height="647" alt="news-homepage" src="https://github.com/user-attachments/assets/736a808f-256c-4b2b-843d-ef0ae0d4be7d" />


# My AWS S3 Static Website

[Live Website Link] http://news-homepage.s3-website.eu-north-1.amazonaws.com/#
[Documentation Link] https://docs.google.com/document/d/1Y-NDRAG4oSkXwKY0QlZefA__YlLwzI7EU_YJ744ibOU/edit?usp=sharing
---

## Project Overview

This is a **static website** deployed on **AWS S3**. The project demonstrates:

- Hosting static HTML, CSS, and JavaScript files  
- Configuring S3 bucket policies for public access  
- Enabling AWS S3 **Static Website Hosting**  

---

## File Structure

Ensure your repository mirrors the deployed structure:
assets
design 
styles
.gitignore
index
style-guide


**Notes:**

- `index.html` is the entry point (all lowercase)  
- All files should reside in the **root** of the bucket for proper static hosting  

---

## Deployment Steps (Summary)

1. **Create S3 Bucket**  
   - Name it appropriately (e.g., `my-static-site`)  

2. **Upload Website Files**  
   - Upload `index.html`, `style.css`, `script.js` **directly to the root**  
   - Do not upload as a folder  

3. **Enable Static Website Hosting**  
   - Properties → Static Website Hosting → Enable → Host a static website  
   - Set **Index document** = `index.html`  

4. **Configure Bucket Policy for Public Access**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "AllowPublicRead",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}

```
5. Disable Block Public Access in Permissions

6. Test the Website

- Open the Website endpoint URL

- Ensure your site loads successfully
