import json
import urllib3
import os

SLACK_URL = os.environ['SLACK_URL']


def lambda_handler(event, context):

    message = {
        'text': f"Issue Created: {event['issue']['html_url']}"
    }
    http = urllib3.PoolManager()
    response = http.request('POST', SLACK_URL, body=json.dumps(message).encode('utf-8'), headers={'Content-Type': 'application/json'})
    return {
        'statusCode': response.status,
        'body': response.data.decode('utf-8')
    }
