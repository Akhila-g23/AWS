AWSTemplateFormatVersion: '2010-03-16'
Resources:
  MyS3Bucket:
    Type: 'AWS::S3::Bucket'
    Properties:
      BucketName: 'Github-s3-bucket'
      AccessControl: Private
      VersioningConfiguration:
        Status: Enabled
Outputs:
  BucketName:
    Description: "Name of the S3 bucket"
    Value: !Ref MyS3Bucket
