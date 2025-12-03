# San-Pedro-Guitar-Lessons
# San Pedro Guitar Lessons Website

A professional static website for guitar lesson services, built to demonstrate AWS cloud deployment skills.

## Technologies Used
- HTML5/CSS3
- HTML5 UP Dimension template
- AWS S3
- AWS CloudFront
- AWS Lambda + API Gateway for contact form

## Architecture
- Static files hosted in S3 bucket configured for website hosting
- CloudFront distribution for global content delivery and HTTPS
- Lambda + API Gateway for contact form (planned)
- Route 53 for custom domain (planned)
- ! [Configuration & Website Images] San Pedro Guitar Screenshots - Portfolio

### S3 Configuration
- Bucket: `sanpedroguitar`
- Region: us-west-1
- Static website hosting enabled
- Public read access configured via bucket policy

### CloudFront Configuration
- Distribution domain: `d21yj99qybpbhg.cloudfront.net`
- HTTPS enabled
- Origin: S3 website endpoint

## Live Sites
- S3 endpoint: http://sanpedroguitar.s3-website-us-west-1.amazonaws.com
- CloudFront (CDN): https://d21yj99qybpbhg.cloudfront.net

## Challenges & Solutions

**CloudFront Timeout Issue**
- Problem: CloudFront URL was timing out/hanging
- Cause: Default root object was not configured
- Solution: Added `index.html` as default root object in CloudFront general settings
- Learning: CloudFront needs explicit configuration to serve index files at root paths

## Project Status
✅ Local development complete
✅ Deployed to S3
✅ CloudFront CDN configured
- [x] Contact form integration
⏳ Custom domain setup (planned)

## Next Steps
- Set up custom domain via Route 53
- Add SSL certificate for custom domain

## Author
Keith Moore