# San-Pedro-Guitar-Lessons
# San Pedro Guitar Lessons Website

A professional static website for guitar lesson services, built to demonstrate AWS cloud deployment skills and website development using basic templates and Adobe Creative Suite for image creation.

## Technologies Used
- HTML5/CSS3
- HTML5 UP Dimension template
- AWS S3
- AWS CloudFront
- AWS Lambda (serverless contact form processing)
- API Gateway (REST API endpoint)
- AWS SES (email delivery)
- Google Analytics
- Adobe Photoshop

## Architecture
- Static files hosted in S3 bucket configured for website hosting
- CloudFront distribution for global content delivery and HTTPS
- Lambda + API Gateway for contact form (planned)
- Route 53 for custom domain (planned)
- [Configuration & Website Images] San Pedro Guitar Screenshots - Portfolio

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
- www.sanpedroguitar.com

## Challenges & Solutions

**Form Submission Error**
- Problem: Contact form failed to deliver form submissions
- Cause: Lambda function accidentally set to US-EAST-1 (N. Virginia) instead of desired US-WEST-1 (N. California)
- Solution: Update region in Lambda function and redeploy.
- Learning: Pay attention to region details in different AWS tools


**CloudFront Timeout Issue**
- Problem: CloudFront URL was timing out/hanging
- Cause: Default root object was not configured
- Solution: Added `index.html` as default root object in CloudFront general settings
- Learning: CloudFront needs explicit configuration to serve index files at root paths

**Problem with "WWW" version of live site not working
- Problem: sanpedroguitar.com loads fine on life site, while www.sanpedroguitar.com does not. SSL certificate validation for the WWW
subdomain was stuck in "Pending Validation". 
- Cause: SSL validation needed to be set up properly for both names.
- Solution: Updated SSL validation, completed in Route 53 and CloudFront distribution configured for both domain names.
- Learning: Both versions of site resolve correctly with HTTPS.


## Project Status
✅ Local development complete
✅ Deployed to S3
✅ CloudFront CDN configured
✅ Contact form integration
✅ Custom domain setup
✅ Google Analytics implementation

## Next Steps

## Author
Keith Moore