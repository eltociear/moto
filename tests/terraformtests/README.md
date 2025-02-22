Documentation on how to run Terraform Tests can be found here:

http://docs.getmoto.org/en/latest/docs/contributing/development_tips/tests.html#terraform-tests

To get started you need to have [Go](https://go.dev/doc/install) installed.

One time setup:

```bash
go mod init moto
```

To see a list of available tests:

```bash
cd tests/terraformtests/terraform-provider-aws
git submodule init
git submodule update
go test ./internal/service/elb/ -v -list TestAcc
```

To run a specific test:

```bash
moto_server -p 4566
make terraformtests SERVICE_NAME=elb TEST_NAMES=NewTestName
```

To see the list of tests that currently pass:

```bash
python tests/terraformtests/get_tf_services.py
python tests/terraformtests/get_tf_tests.py ec2
```

