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
