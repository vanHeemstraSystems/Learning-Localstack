# Learning-Localstack

A basic demo setting up Localstack's S3.

Read the tutorial [here](https://dev.to/goodidea/how-to-fake-aws-locally-with-localstack-27me).

Or, spin things up here:

1. Install [Docker](https://docs.docker.com/install/) if you haven't already.
2. Install the [AWS CLI](https://aws.amazon.com/cli/). Even though we aren't going to be working with "real" AWS, we'll use this to talk to our local docker containers.

```s
pip install awscli
```
Reference: https://aws.amazon.com/cli/
  - Run `aws configure` to set up some credentials. You can enter dummy credentials here if you'd like.

This will create some cli file in path `C:\Users\********\.aws`

3. run the docker
```s
docker-compose up
```

4.  endpoint 
web ui point: `http://localhost:8055`

S3 endpoint : `http://localhost:4572`


5. Create credentials

```s
C:\Study\VScode\Learning-Localstack>aws configure
AWS Access Key ID [None]: test
AWS Secret Access Key [None]: test
Default region name [None]: test
Default output format [None]: test
```

6. create s3 bucket

```s
aws --endpoint-url=http://localhost:4572 s3 mb s3://demo-bucket
```

7. Attach an ACL to the bucket so it is readable
```s
aws --endpoint-url=http://localhost:4572 s3api put-bucket-acl --bucket demo-bucket --acl public-read
```

8.

Reference: 

https://medium.com/@matayoshi.mariano/aws-services-in-your-local-environment-with-docker-2a78621da695

https://dev.to/goodidea/how-to-fake-aws-locally-with-localstack-27me


https://dev.to/goodidea/how-to-fake-aws-locally-with-localstack-27me


https://s0dev0to.icopy.site/goodidea/how-to-fake-aws-locally-with-localstack-27me

<!-- 3. Copy the contents of `.env.example` into a new `.env` file. 

4. Initialize Localstack: `npm run localstack:init`.
  - This will create a new container, then stream the logs as it is setting up. It will start with `Waiting for all LocalStack services to be ready`. After a few moments, you'll see a final `Ready`. When you do, press Ctrl+C to exit the logs.
5. Configure the bucket: run `npm run localstack:config`
  - *Note: If you used a different BUCKET_NAME in your `.env` file, make sure to change the instances of `demo_bucket` in the `localstack:config` script in package.json to match.*.

Upload the test file:

`npm run test-upload` -->