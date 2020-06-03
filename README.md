# match-project-infrastructure
[マッチングアプリ](https://github.com/Kaikawa1028/match)のインフラリソースです

## 環境
- Terraform 0.12.19
- aws 2.45.0

## インフラ構成図
- 今回はサンプルアプリのため、dev環境のみしか用意していません。

![インフラ構成](https://gyazo.com/6222c449ac16ef22830be068927c98c3.ping)

## 環境構築

```
terraform init \
  -backend=true \
  -backend-config="bucket=match-project.terraform" \
  -backend-config="key=terraform.tfstate" \
  -backend-config="region=ap-northeast-1"
```

```
cd ./development
terraform init \
  -backend=true \
  -backend-config="bucket=match-project.terraform" \
  -backend-config="key=development.terraform.tfstate" \
  -backend-config="region=ap-northeast-1"
```

```
cd ../staging
terraform init \
  -backend=true \
  -backend-config="bucket=match-project.terraform" \
  -backend-config="key=staging.terraform.tfstate" \
  -backend-config="region=ap-northeast-1"
```

```
cd ../production
terraform init \
  -backend=true \
  -backend-config="bucket=match-project.terraform" \
  -backend-config="key=production.terraform.tfstate" \
  -backend-config="region=ap-northeast-1"
```

```
cd ../
```