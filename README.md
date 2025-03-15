{
    "AWSTemplateFormatVersion": "2010-09-09",
    "Description": "Create Git Repo and S3 bucket ",    
    "Parameters": {
        "ProjectName": {"Type": "String"}
    },    
    
    "Resources": {        
        "s3Bucket": {
            "Type": "AWS::S3::Bucket",
            "Properties": {
                "AccessControl": "Private"                
            }
        },         
        "gitrepo": {
           "Type": "AWS::CodeCommit::Repository",
           "Properties": {
              "RepositoryDescription": "This is a dashboard project",
              "RepositoryName": {"Ref": "ProjectName"}
          }
        }       
        
    },
    "Outputs": {
        "Bucketname": {
            "Description": "Bucket name",
            "Value": {"Ref" : "s3Bucket"}
        },
        "GitRepo": {
            "Description": "Git repo name", 
            "Value": {"Ref": "gitrepo"}
        }
    }
}
