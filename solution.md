## SSL expiration check
##  


1. Create Lambda Function using the Author from scratch option. 
    a. select python3.7
    b. choose to have new role created under permssions. 
   
   
2. Add API Gateway to trigger the function 
        API type: HTTP
        Authorization: NONE
        Cross-origin resource sharing (CORS): No
        Enable detailed metrics: No
        Method: ANY
        Resource path: /ssl-expiry
        Stage: default

3. Add Destination. 
    a. Presently testing with SNS notifications but could also add DynamoDB or an S3 bucket to archive results.
        
4. Prepare Python envornment    
    a.  $ conda env create -f environment.yml
        $ source activate ssl-expiry

5. 