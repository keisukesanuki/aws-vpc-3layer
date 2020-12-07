# aws-vpc-3layer

## なにこれ？

awsに3層のVPC環境を構築するplaybookです。  
作成するリソースは下記の通りです。  

* VPC  
* SUBNET  
* INTERNETGATEWAY  
* NATGATEWAY  
* ROUTETABLE  


## 使い方

### 0.botoとaws cliの導入

```
pip install boto boto3 awscli
```

### 1.リポジトリをclone

```
git clone [URL]
cd aws-vpc-3layer
```

### 2.作成したいリソースに併せて適切に変数を設定

```
cp -p roles/aws_vpc/vars/main.yml.example roles/aws_vpc/vars/main.yml
vi roles/aws_vpc/vars/main.yml
```

### 3.実行

```
ansible-playbook -i hosts vpc_create.yml
```

## 変数の詳細

### 1.region

vpcを作成するリージョンを定義  

### 2.profile

プロファイルを定義

### 3.vpc_name

作成するVPCの名前を定義

### 4.igw_name

作成するINTERNETGATEWAYの名前を定義

### 5.ngw_name

作成するNATGATEWAYの名前を定義

### 6.ngw_subnet_name

NATGATEWAYを配置するサブネット名を定義

### 7.rttable_pub_name

パブリックサブネットに紐づけるルートテーブル名を定義

### 8.rttable_dmz_name

DMZサブネットに紐づけるルートテーブル名を定義

### 9.pub_subnet

パブリックサブネットのサイダー/az/名前を定義

### 10.dmz_subnet

DMZサブネットのサイダー/az/名前を定義

### 11.pri_subnet

プライベートサブネットのサイダー/az/名前を定義

### 12.atache_igw_subnet

INTERNETGATEWAYに紐づけるサブネットをサイダーで定義

### 13.atache_ngw_subnet

INTERNETGATEWAYに紐づけるサブネットをサイダーで定義
