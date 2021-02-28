# botos3
S3 download
import boto3

def download_all_files():
    #initiate s3 resource
    s3 = boto3.resource('s3')
    # select bucket
    my_bucket = s3.Bucket('bucket_name')
    # download file into current directory
    for s3_object in my_bucket.objects.all():
        filename = s3_object.key
        my_bucket.download_file(s3_object.key, filename)
