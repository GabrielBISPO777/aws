# aws
teste de projeto AWS 


import boto3

# Cria uma sessão com a AWS
session = boto3.Session(
    aws_access_key_id='SUA_ACCESS_KEY',
    aws_secret_access_key='SUA_SECRET_KEY',
    region_name='us-east-1'  # Você pode mudar para a região desejada
)

# Cria um cliente para o S3
s3 = session.client('s3')

# Lista os buckets
response = s3.list_buckets()

print("Buckets disponíveis:")
for bucket in response['Buckets']:
    print(f'  {bucket["Name"]}')
