# Back-End Directory
```
├── code
|  ├── csc0002_listSeatChartName.py
|  ├── csc0002_seatChart2DDetail.py
|  ├── csc0003_listEmployee.py
|  ├── csc0003_listEmployee_data.json
|  ├── csc0004_addModel.py
|  ├── csc0004_addSeatChart.py
|  ├── csc0004_deleteModel.py
|  ├── csc0004_deleteSeatChart.py
|  ├── csc0004_listSeatChartName.py
|  ├── csc0004_seatChartDetail.py
|  ├── csc0004_updateModel.py
|  ├── csc0004_updateSeatChart.py
|  └── getSvgS3.py
├── main.tf
├── modules
|  ├── api-gateway
|  ├── api_resource
|  ├── api_resource_child
|  ├── iam_role
|  └── lambda_layer_version
├── python
|  ├── bin
|  ├── boto3
|  ├── boto3-1.34.3.dist-info
|  ├── botocore
|  ├── botocore-1.34.3.dist-info
|  ├── certifi
|  ├── certifi-2023.11.17.dist-info
|  ├── charset_normalizer
|  ├── charset_normalizer-3.3.2.dist-info
|  ├── const.py
|  ├── dateutil
|  ├── db_connection.py
|  ├── db_select.py
|  ├── fuzzywuzzy
|  ├── fuzzywuzzy-0.18.0.dist-info
|  ├── idna
|  ├── idna-3.6.dist-info
|  ├── jmespath
|  ├── jmespath-1.0.1.dist-info
|  ├── jwt
|  ├── marshmallow
|  ├── marshmallow-3.20.1.dist-info
|  ├── packaging
|  ├── packaging-23.2.dist-info
|  ├── psycopg2
|  ├── psycopg2-2.9.9.dist-info
|  ├── psycopg2_binary-2.9.9.dist-info
|  ├── psycopg2_binary.libs
|  ├── PyJWT-2.8.0.dist-info
|  ├── python_dateutil-2.8.2.dist-info
|  ├── requests
|  ├── requests-2.31.0.dist-info
|  ├── s3transfer
|  ├── s3transfer-0.9.0.dist-info
|  ├── s3_utils.py
|  ├── six-1.16.0.dist-info
|  ├── six.py
|  ├── urllib3
|  ├── urllib3-2.0.7.dist-info
|  ├── urllib3-2.1.0.dist-info
|  └── utils.py
├── README.md
├── requirements.txt
├── variables.tf
└── variables.tfvars

```
## Description

### :fontawesome-regular-folder: Code
`code`Chứa các hàm lambda xử lý logic của API
### :fontawesome-regular-folder: Modules
`modules`Folder `modules` này dùng để chứa các modules con như lambda, api gateway, iam_role, lambda_layer_version
### :fontawesome-regular-folder: Python
`python`chứa các file thư viện tải xuống từ kho package, hoặc các file commons chứa các hàm xử lý dùng chung
### :fontawesome-regular-file: Main.tf
`main.tf`File này dùng để chứa các modules như là lambda, api gateway
### :fontawesome-regular-file: Requirements.txt
`requirements.txt`chứa danh sách các tên package được sử dụng trong source 
### :fontawesome-regular-file: Variables.tf
`variables.tf`File này để chứa các biến để sử dụng cho bên trong file main.tf, nếu nó được khai báo trong folder nào thì nó sẽ là khai báo biến cho file main.tf cùng cấp
### :fontawesome-regular-file: Variables.tfvars
`variables.tfvars`Thông thường file này sẽ chứa giá trị của các biến đã được khai báo
