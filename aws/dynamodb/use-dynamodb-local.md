# 다이나모DB 로컬 사용하기

## 설치하기

간편하고 깔끔한 구성을 위해서 AWS(Amazon Web Service)에서 제공하는 도커(Docker) 이미지를 사용합니다.

```
$ docker run -d -p 8000:8000 --name dynamodb amazon/dynamodb-local
```

## 사용하기

다이나모DB 로컬을 다루기 위해선 `awscli`를 사용해야 합니다.

### 설치하기

```bash
$ bower install awscli
```

### 설정하기

```bash
$ aws configure
AWS Access Key ID [None]: AKIA************
AWS Secret Access Key [None]: advp************************************
Default region name [None]: local  # 로컬에서 사용하기 때문에 리전을 local로 설정합니다.
Default output format [None]: json
```

`awscli`를 사용하기 위해선 AWS IAM(Identity and Access Management)에서 계정을 생성하고 발급받은 **Access Key ID**와 **Secret Access Key** 값을 입력해줘야 합니다.

### 사용하기

```bash
$ aws dynamodb list-tables --endpoint-url http://localhost:8000
```

다이나모DB 로컬에 접근하기 위해선 반드시 `--endpoint-url` 옵션에 `http://localhost:8000`을 입력해줘야 합니다. (기본 포트가 아닌 다른 포트를 사용한다면 해당 포트를 입력해주시면 됩니다.)

## 참조

- [도커 허브(Docker Hub), DynamoDB local](https://hub.docker.com/r/amazon/dynamodb-local)
- [AWS 공식 홈페이지, AWS Command Line Interface](https://aws.amazon.com/cli/?nc1=h_ls)
