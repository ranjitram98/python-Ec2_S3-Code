import json
import boto3

s3 = boto3.client('s3')

def lambda_handler(event, context):
    print(event)
    
    user = event['detail']['userIdentity']['userName']

    instanceId = event['detail']['responseElements']['instancesSet']['items'][0]['instanceId']
    
    examplebucket = event['detail']['requestParameters']['bucketName']
    
    
    s3.put_bucket_tagging(
        Bucket= examplebucket,
        Tagging={
            'TagSet': [
                {
                    'Key': 'Owner',
                    'Value': user,
                },
            ],
        },
    )  
    return
