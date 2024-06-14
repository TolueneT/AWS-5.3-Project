# **How to host a Static website in an AmazonS3 bucket.**

# _Steps to Host a Static Website on Amazon S3_

1. Create an S3 Bucket:

- Log in to the AWS Management Console.
- Navigate to S3 and click "Create bucket".
- Provide a globally unique name for your bucket (e.g., Scenario2-website-bucket).
- Choose a region close to your target audience.
- Uncheck "Block all public access" to make your bucket publicly accessible.

2. Upload Static Website Files:

- Click on the newly created bucket.
- Use the "Upload" button to add your HTML, CSS, JavaScript, and any other static files.

3. Set Bucket Permissions:

- Navigate to the "Permissions" tab of your bucket.
- Add a bucket policy to allow public read access. The policy should look like this:
  '''
  {
  "Version": "2012-10-17",
  "Statement": [
  {
  "Sid": "PublicReadGetObject",
  "Effect": "Allow",
  "Principal": "*",
  "Action": "s3:GetObject",
  "Resource": "arn:aws:s3:::Scenario2-website-bucket/*"
  }
  ]
  }
  '''
  4.Enable Static Website Hosting:
- Go to the "Properties" tab of your bucket.
- Scroll down to the "Static website hosting" section and click "Edit".
- Select "Enable" and provide the index document (e.g., index.html).
- Optionally, specify an error document (e.g., error.html).
- Save the changes and note the "Bucket website endpoint" URL (e.g., http://Scenario2-website-bucket.s3-website-us-east-1.amazonaws.com).

5. Integrate with a CDN (Optional):

- Use Amazon CloudFront to create a distribution for your S3 bucket.
- Specify the S3 bucket as the origin and configure the distribution settings.
- CloudFront will provide a domain name that you can use as the website URL or configure your custom domain to point to the CloudFront distribution for better performance and security.

# _Considerations for Domain Configuration and CDN Integration_

1. **Domain Configuration:** Use Route 53 to manage your DNS settings. Create an A record or CNAME record pointing to your S3 bucket or CloudFront distribution.
2. **CDN Integration:** CloudFront can help reduce latency by caching your content at edge locations around the world. This is particularly useful for global audiences.

# Sample Architectural Diagram

_Here's a simple architecture diagram for hosting a static website on Amazon S3 with CloudFront CDN and Route 53 for custom domain management._
![Digram draw.io](Images/Sample%20Architectural%20Diagram.jpg)

# **Implementation of the Steps**

1. Create S3 Bucket:
   'aws s3 mb s3://my-static-website-bucket'
   ![Digram draw.io](Images/scenario2bucket.JPG)
2. Upload Files:index.html
   ![Digram draw.io](Images/obect.JPG)
3. Set Public Read Policy:
   ![Digram draw.io](Images/policybucket.JPG)
4. Enable Static Website Hosting:
   ![Digram draw.io](Images/staticweb.JPG)
5. Verify the bucket: It worked!
   ![Digram draw.io](Images/worked.JPG)
