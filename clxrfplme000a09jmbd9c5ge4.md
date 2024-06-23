---
title: "Automated Blog Content Generation Using AWS Bedrock"
datePublished: Sun Jun 23 2024 10:57:18 GMT+0000 (Coordinated Universal Time)
cuid: clxrfplme000a09jmbd9c5ge4
slug: automated-blog-content-generation-using-aws-bedrock
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719139955668/ee38cdf1-3fcc-4d26-87c1-c55d2d8987b8.png
tags: postman, aws, genai

---

## Introduction

In today's fast-paced digital era, maintaining a steady stream of engaging content is crucial yet challenging. Imagine a solution that automates blog content creation, ensuring quality and consistency with minimal effort. This blog explores how AWS Bedrock, combined with the powerful Llama 2 Chat 13B model, enables automated blog generation. Leveraging AWS services such as Lambda, API Gateway, and S3, we will guide you through setting up a seamless system that transforms how you produce content, saving time and enhancing productivity.

## Implementation Steps

Follow these detailed instructions to configure AWS Bedrock and AWS Lambda, enabling automated blog content generation with ease.

### AWS Bedrock Configuration

Preparing AWS Bedrock for automated blog content creation involves configuring model access and selecting the optimal AI model.

* **Access AWS Bedrock:**
    
    * Log in to the AWS Management Console.
        
    * Navigate to AWS Bedrock.
        
* **Grant Model Access:**
    
    * Click on **Model Access** within AWS Bedrock.
        
    * Grant access permissions for the required models, ensuring permissions are set appropriately.
        

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXcH_WXbm8r7D-QT4z7ZVs651K79hRQ_AsQQ15Cp6NHWbPDSyhj_QL02BufH5tF0gNdNxiodJELgbjF4AKrCFABet7_D12q31g1pNw5jcSQ2GRhpxU-8KzR3qWqqAPOq0HqPnuY_m4tpG9ox2kScN8Iszqs?key=eM4Tdxxln4L-Pc0NUnKniw align="center")

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfdl92APmrLWlc4kzwrTmYPNzcfu_hqhu3FCHyUS_Fu7bGcqsXSfLNQC8x4VPvQDlqlSNU51lR_3Tcyn-dnXb_pfYYTfUqByrhHf7POJqGMMHL4IH3VfXwgxtm4qFU6EVzia47EWFw2m8Aqj-ZhV9HYU18?key=eM4Tdxxln4L-Pc0NUnKniw align="left")

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXd0ZU9SbiM1Nc-rhOGHRTn6gTGl2m3Wpeh1yXXyJVfSdB2H-UmGHVh8xkJoOmYUVapM5WXyQ2Um1IDQk17aU7grHFGTvABzTz62Fd6eD70m4Rrj1dETT8WK-VInoaK1IkEZtPUbcE_mFANiYUYn3xCgcOz-?key=eM4Tdxxln4L-Pc0NUnKniw align="right")

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdLdhO6w7ZmM_8zGk0tDEGrYtLwalmZEgUjFy_7P6nCFFZSHZ2xPCWX_1NaSfKJ8K8gsdt4tc47f7QL_F5U-Fa4FZPH8ntghwsfSiYwZ8hziRw4MvQgClX6NsJ9h-WHjOB7USePMPKGgMZDeSU262Pu6DFx?key=eM4Tdxxln4L-Pc0NUnKniw align="left")

* **Select AI Model:**
    
    * Choose the Llama 2 Chat 13B model for blog content generation.
        
    * Ensure the model is configured to meet your specific requirements and objectives.
        

### Setting Up AWS Lambda

* Create a Lambda function with Python 3.12 runtime.
    
* Configure the Lambda function (e.g., setting timeout to 3 minutes).
    
* Below is the code snippet for configuring the Lambda function to automate blog content generation using AWS Bedrock.
    

```python
import boto3
import botocore.config
import json
from datetime import datetime

# Function to generate blog content using AWS Bedrock
def blog_generate_using_bedrock(blogtopic:str) -> str:
    prompt = f"""<s>[INST]Human: Write a 200 words blog on the topic {blogtopic}
    Assistant:[/INST]
    """
    body = {
        "prompt": prompt,
        "max_gen_len": 512,
        "temperature": 0.5,
        "top_p": 0.9
    }

    try:
        bedrock = boto3.client("bedrock-runtime", region_name="us-east-1",
                               config=botocore.config.Config(read_timeout=300, retries={'max_attempts': 3}))
        response = bedrock.invoke_model(body=json.dumps(body), modelId="meta.llama2-13b-chat-v1")

        response_content = response.get('body').read()
        response_data = json.loads(response_content)
        blog_details = response_data['generation']
        return blog_details
    except Exception as e:
        print(f"Error generating the blog: {e}")
        return ""

# Function to save generated blog content to S3
def save_blog_details_s3(s3_key, s3_bucket, generate_blog):
    s3 = boto3.client('s3')

    try:
        s3.put_object(Bucket=s3_bucket, Key=s3_key, Body=generate_blog)
        print("Blog saved to S3 successfully.")
    except Exception as e:
        print(f"Error when saving the blog to S3: {e}")

def lambda_handler(event, context):
    event = json.loads(event['body'])
    blogtopic = event['blog_topic']

    generate_blog = blog_generate_using_bedrock(blogtopic=blogtopic)

    if generate_blog:
        current_time = datetime.now().strftime('%H%M%S')
        s3_key = f"blog-output/{current_time}.txt"
        s3_bucket = 'aws_bedrock_course1'
        save_blog_details_s3(s3_key, s3_bucket, generate_blog)
    else:
        print("No blog was generated")

    return {
        'statusCode': 200,
        'body': json.dumps('Blog Generation is completed')
    }
```

**Note**

To ensure the Lambda function operates correctly, ensure you have the latest version of `boto3` installed:

For development, use any Python IDE such as VS Code. Follow these steps:

* Install `boto3` locally by running the command:
    
    ```python
    pip install boto3 -t python/
    ```
    
* Compress the `python/` directory into a zip file named `boto3_`[`layer.zip`](http://layer.zip).
    

Then, in the AWS Lambda console:

* Navigate to Layers → Create Layer.
    
* Upload `boto3_`[`layer.zip`](http://layer.zip) and configure the layer with Python runtime versions (3.10, 3.11, 3.12).
    

After creating the layer, proceed to the Lambda function settings:

1. Go to your Lambda function in the AWS Management Console.
    
2. Navigate to Layers → Add a layer → Custom layers.
    

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfNAxJAQVMEYUwZ4qocbTDTtiswy25kCB1kMbXzysCzlZN-TSe3_gWD6sbIZDAqEuISh03xsVKKFaIB_q121dQuAbAjcbG8doONsEgj5uJBZvBe5C1KyabhpPsD4MGCKWwRE_cwpplIK3yTZXNQVLfJQrL9?key=eM4Tdxxln4L-Pc0NUnKniw align="left")

### Integrating with AWS API Gateway

To integrate AWS API Gateway with AWS Lambda:

1. Navigate to API Gateway in the AWS Management Console.
    
2. Click on **Create API**.
    

After creating the API in AWS API Gateway:

3. Create routes to define how API requests are routed to AWS Lambda functions:
    
    * Define HTTP methods (e.g., POST, GET) and their corresponding Lambda function integrations.
        
    * Configure endpoint paths to align with your application's functional requirements.
        

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdeqv3Dt-IWKxLTbgzOkoo-G5noGHydIPpV2SnktIaENLdaPMcNbjmUQrhtIQVUp0IokrIaRn7qYZUDTtiLqq5OSAdjw_lXScUTIj0ByViZJfWCd171yfLGvSM5i84G_ld34i-OLfoJXyuj2WDyQfCxpFz4?key=eM4Tdxxln4L-Pc0NUnKniw align="left")

Next, create a stage and deploy your API in AWS API Gateway:

1. Navigate to API Gateway in the AWS Management Console.
    
2. Click on APIs → Stages → Create stage.
    
3. If needed, configure the stage settings, including stage name, deployment description, and stage variables.
    
4. Deploy the stage to make your API endpoints accessible.
    

### S3 Bucket

To create an S3 bucket with the correct format:

1. Navigate to Amazon S3 in the AWS Management Console.
    
2. Click on **Create bucket**.
    
3. Enter a unique bucket name following the S3 bucket naming conventions.
    
4. Select the region for your bucket.
    
5. Configure additional options as needed (e.g., versioning, logging).
    
6. Click **Create bucket** to finalize.
    

### Testing with Postman

To test your AWS API Gateway endpoint using Postman:

1. Open Postman and select **POST** as the request type.
    
2. Paste the URL generated from AWS API Gateway into the request URL field.
    
3. Configure headers and parameters as required by your API.
    
4. Add request body content.
    
5. Click **Send** to execute the POST request and observe the response.
    

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXfsO2QkEK-Q2Q-PJSwinNg7Lh6cyMgAMwrqS929SSiq0s0ArZkBYdFetRLvIANPzBU8sl2ILkbbDCjpvq0LTdXtWtboOjPVViTVuH4pITCSp1AEUpXxPN4NbR-s5QYX13bFe7H-6Mlyskm8CZlyub04sbQ?key=eM4Tdxxln4L-Pc0NUnKniw align="left")

### CloudWatch Logs Monitoring

To view logs for your AWS Lambda function in CloudWatch:

1. Navigate to AWS Lambda in the AWS Management Console.
    
2. Select your Lambda function.
    
3. Click on **Monitor** in the top menu.
    
4. Under **Monitoring tools**, click **View logs in CloudWatch**.
    
5. In the CloudWatch Logs console, navigate to your Lambda function's log group.
    
6. Review logs to monitor function execution, troubleshoot issues, and gather insights.
    

![](https://lh7-us.googleusercontent.com/docsz/AD_4nXdkKN9__rF-Xr1UkuHCo6A1iVN18FvHMQGuwnnaHDAqZmGHgSBbrgPVSonpw42yw0c1v5RT3Mkh7mT-M0XRqkzs-xiM78II1qUyezxcwlLT44GRUG8n9oEPGbdEbQsTtKWeSrnSYy0AX4BvlFzapADJoMk?key=eM4Tdxxln4L-Pc0NUnKniw align="left")

Now that CloudWatch confirms the blog content has been successfully generated, let’s conclude our journey with AWS Bedrock.

## Conclusion

Using AWS Bedrock and the Llama 2 Chat 13B model, along with AWS Lambda, API Gateway, and S3, we've optimized blog content creation. This setup ensures reliable and consistent production of quality content, utilizing AWS's advanced AI and cloud services to empower organizations to improve their content strategies effectively.