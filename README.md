# S3 Buckets AWS

**Steps to achieve a "Hello World" with Amazon S3:**

- **Create an S3 Bucket:**
    - Sign in to the AWS Management Console and navigate to the Amazon S3 service.
    - Choose "Create bucket" and provide a globally unique name for your bucket.
    - Select an AWS Region, preferably one geographically close to your users for reduced latency and cost.
- **Create "Hello World" Content:**
    - Prepare a simple `index.html` file containing "Hello World" or similar content. For example:

Code

```html
        <!DOCTYPE html>
        <html>
        <head>
            <title>Hello S3</title>
        </head>
        <body>
            <h1>Hello, World! from Amazon S3</h1>
        </body>
        </html>
```

- **Upload Content to the S3 Bucket:**
    - In the S3 console, select your newly created bucket.
    - Choose "Upload" and add your `index.html` file (and any other static assets like CSS files or images if applicable).
- **Enable Static Website Hosting:**
    - Within your bucket's properties, locate and enable "Static website hosting."
    - Specify `index.html` as the index document.
- **Configure Bucket Policy for Public Access:**
    - To make your website publicly accessible, you need to add a bucket policy that grants `s3:GetObject` permission to anonymous users. An example policy:

```json
        {
            "Version": "2012-10-17",
            "Statement": [
                {
                    "Sid": "PublicReadGetObject",
                    "Effect": "Allow",
                    "Principal": "*",
                    "Action": "s3:GetObject",
                    "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
                }
            ]
        }
```

**Replace `YOUR_BUCKET_NAME` with your actual bucket name.**

- **Access Your "Hello World" Website:**
    - After enabling static website hosting, S3 provides an endpoint URL for your website. You can find this URL in the bucket's "Properties" tab under "Static website hosting."
    - Open this URL in a web browser to view your "Hello World" page hosted on Amazon S3.
