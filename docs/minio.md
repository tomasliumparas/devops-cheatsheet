## Single bucket policy

=== "Policy"

    ```json
    {
        "Version": "2012-10-17",
        "Statement": [{
                "Effect": "Allow",
                "Action": [
                    "s3:ListBucket"
                ],
                "Resource": "arn:aws:s3:::velero"
            },
            {
                "Effect": "Allow",
                "Action": [
                    "s3:GetObject",
                    "s3:PutObject"
                ],
                "Resource": [
                    "arn:aws:s3:::velero/*"
                ]
            }
        ]
    }    
    ```


