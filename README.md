# try-pulumi

https://www.pulumi.com/docs/get-started/aws/

Install Pulumi CLI

```sh
curl -fsSL https://get.pulumi.com | sh
```

Confiture AWS account

create dotenv

create AWS user and user's access key

```
❯ mkdir quickstart && cd quickstart && pulumi new aws-go
Manage your Pulumi stacks by logging in.
Run `pulumi login --help` for alternative login options.
Enter your access token from https://app.pulumi.com/account/tokens
    or hit <ENTER> to log in using your browser                   :


  Welcome to Pulumi!

  Pulumi helps you create, deploy, and manage infrastructure on any cloud using
  your favorite language. You can get started today with Pulumi at:

      https://www.pulumi.com/docs/get-started/

  Tip: Resources you create with Pulumi are given unique names (a randomly
  generated suffix) by default. To learn more about auto-naming or customizing resource
  names see https://www.pulumi.com/docs/intro/concepts/resources/#autonaming.


This command will walk you through creating a new Pulumi project.

Enter a value or leave blank to accept the (default), and press <ENTER>.
Press ^C at any time to quit.

project name: (quickstart) try-pulumi
project description: (A minimal AWS Go Pulumi program)
Created project 'try-pulumi'

Please enter your desired stack name.
To create a stack in an organization, use the format <org-name>/<stack-name> (e.g. `acmecorp/dev`).
stack name: (dev)
Created stack 'dev'

aws:region: The AWS region to deploy into: (us-east-1) ap-northeast-1
Saved config

Installing dependencies...

<omit go download log>

Finished installing dependencies

Your new project is ready to go!

To perform an initial deployment, run `pulumi up`
```

```
~/repos/github.com/anoriqq/try-pulumi/quickstart feature/1*
❯ l -TL=3 .
Permissions  Size Date Modified    Git Name
drwxr-xr-x      - 2023-04-26 22:26  -N  ./
.rw-r--r--  3.0Ki 2023-04-26 22:26  -N ├──  go.mod
.rw-r--r--   24Ki 2023-04-26 22:26  -N ├──  go.sum
.rw-r--r--    404 2023-04-26 22:26  -N ├──  main.go
.rw-r--r--     37 2023-04-26 22:26  -N ├──  Pulumi.dev.yaml
.rw-r--r--     74 2023-04-26 22:26  -N └──  Pulumi.yaml
```

```sh
pulumi up
```

https://app.pulumi.com/anoriqq/try-pulumi/dev/updates/1

add allow policy of S3-full-access to AWS user (Pulumi-aoba)

create s3 bucket

https://app.pulumi.com/anoriqq/try-pulumi/dev/updates/2

create s3 bucket object

https://app.pulumi.com/anoriqq/try-pulumi/dev/updates/3

update s3 bucket object to website

https://app.pulumi.com/anoriqq/try-pulumi/dev/updates/4

to get website url from output: http://my-bucket-31fe94a.s3-website-ap-northeast-1.amazonaws.com/

destroy

```sh
~/repos/github.com/anoriqq/try-pulumi/quickstart feature/1
❯ pulumi destroy
Previewing destroy (dev)

View in Browser (Ctrl+O): https://app.pulumi.com/anoriqq/try-pulumi/dev/previews/92944ba7-21e8-48c8-8d3c-3feb6fd6afdb

     Type                               Name                 Plan
 -   pulumi:pulumi:Stack                try-pulumi-dev       delete
 -   ├─ aws:s3:BucketObjectv2           index.html           delete
 -   ├─ aws:s3:BucketPublicAccessBlock  public-access-block  delete
 -   ├─ aws:s3:BucketOwnershipControls  ownership-controls   delete
 -   └─ aws:s3:Bucket                   my-bucket            delete


Outputs:
  - bucketEndpoint: "http://my-bucket-31fe94a.s3-website-ap-northeast-1.amazonaws.com"
  - bucketName    : "my-bucket-31fe94a"

Resources:
    - 5 to delete

Do you want to perform this destroy? yes
Destroying (dev)

View in Browser (Ctrl+O): https://app.pulumi.com/anoriqq/try-pulumi/dev/updates/5

     Type                               Name                 Status
 -   pulumi:pulumi:Stack                try-pulumi-dev       deleted
 -   ├─ aws:s3:BucketObjectv2           index.html           deleted (1s)
 -   ├─ aws:s3:BucketPublicAccessBlock  public-access-block  deleted (0.56s)
 -   ├─ aws:s3:BucketOwnershipControls  ownership-controls   deleted (0.89s)
 -   └─ aws:s3:Bucket                   my-bucket            deleted (0.54s)


Outputs:
  - bucketEndpoint: "http://my-bucket-31fe94a.s3-website-ap-northeast-1.amazonaws.com"
  - bucketName    : "my-bucket-31fe94a"

Resources:
    - 5 deleted

Duration: 5s

The resources in the stack have been deleted, but the history and configuration associated with the stack are still maintained.
If you want to remove the stack completely, run `pulumi stack rm dev`.
```
