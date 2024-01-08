# Seat Chart API
Explain the API used in the project.

## API List

|No.|API no.|Method  |API name         |Functional overview                               |
|---|-------|--------|-----------------|--------------------------------------------------|
|1  |CSC0004|Get     |listSeatChartName|lấy tên của toàn bộ chart có trong hệ thống       |
|2  |CSC0002|Get     |seatChart2DDetail|lấy thông tin chi tiết của chart theo id tương ứng|
|3  |CSC0003|Get     |listEmployee     |lấy thông tin toàn bộ nhân viên                   |
|4  |CSC0004|Post    |addSeatChart     |thêm seat chart vào hệ thống                      |
|5  |CSC0004|Put     |upadteSeatChart  |cập nhật thông tin sửa đổi của seat chart         |
|6  |CSC0004|Delete  |deleteSeatChart  |xóa seat chart khỏi hệ thống                      |

## CSC0004_listSeatChartName
- GET `/CSC0004/listSeatChartName`
- Parameter : `type` (optional)
- Example return data
```
    "status": true,
    "message": "get data succes",
    "list": [
        {
            "id": 346,
            "name": "ccccc",
            "info": null,
            "type": 1,
            "layout": 1
        },
    ]
```
- This API will return all seat chart available in the system if not input parameter.
- Optional query parameters:
 - `type` : this version only have 2 type 1 or 2. that why if input another interger value will return `list :null`
- Validation check:
 - if input is not a number will return error with status code `400`:
 ```
    {
    "type": [
        "Not a valid integer."
        ]
    }
 ```
## CSC0002_seatChart2DDetail
- GET `/CSC0002/seatChart2DDetail` 
- Parameter : `seat_chart_id` must be a number (required)
- Example return data for input `seat_chart_id` = 331:
```
    {
    "status": true,
    "message": "",
    "data": {
        "id": 331,
        "name": "TSA",
        "info": null,
        "type": 1,
        "chart_file_key": "available/TSA_331.svg",
        "created_date": "2024/01/05",
        "layout": 1,
        "created_by": null,
        "updated_by": null,
        "updated_date": null
    },
    "url_getfile": "https://seat-chart.s3.amazonaws.com/available/TSA_331.svg?AWSAccessKeyId=ASIA2G6CIH5XD2JFH573&Signature=GOj4sgmV4on7Lzmt%2BGt7xaPnBxk%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEO%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaDmFwLXNvdXRoZWFzdC0xIkYwRAIgJ7pU4DANceN5i6WbEOBKDx1CgeaPWo8i%2F4Yuci3%2FRUUCIFoyAI96stinM4Yf6vDIzeblc0GMFoyMP3Yp5UOQAjEuKqkDCIj%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEQAxoMNzAyMDk3NjY5OTk4IgzU5BQlt8sm5wAy35wq%2FQKMoRoATjSmvm4C9rDxbtZaMG6wDSRWuyuKSEJvXuFas5%2FRnufRDDb7hjUY74g3W0BFJ%2FEeBs7KrFXGyH%2FIkA9c0XBxmnAG%2F1Co3IHcp8jvWazChqfQWeOHpqFv74dlNIPbc4957xYx9BTd3MucA1p5SCnu%2BJdTWb5mF9mfIOuRpge5sWHUzEocovUPWZft%2FOmOA%2BaLfJcnyos%2FGU8%2B7aRgxeC%2BKREq40Gr93PvMWozjhELOKjzbIaoZWnkBlmzVnhFrq0K8DrtZXTrmGl1SNscDzE84KDcc8ZLBu0A0mG61MGrirXj8hQe4AS9lyZSEZw3FqN%2Ffv7%2Ftu3DWEAXkJ0G4NPGfTECWhFOMkOtBkpexeqHJD6EvnM39ldOpbXgaLDV9G8PFHAcY6bWI07BgFSEX%2BIkiA%2FH0Wg%2Bka9pCSbL7ooRrsescnMs9xPSu1Fs0C9xLNd1gPj2MxoGIRhEzOs4qc07Gwif7aKrVmQY%2FFBZ%2FzkgVJmMD%2BjUubn5rjIwh8zerAY6ngEP3ajDXu9KMKx%2BpCUCXK%2F0VvGzvsFef4rCjbIVkNuruOt8eH6GaddXHoV68SGmOlnEj4SJy%2FzUcxLDRHN%2Bu7GJYmhaV664iTm2GuA5Qs1dQ3d7yJpDwmQUKawFL%2Bq0xDbyBRAPh0nI7jdKUAvKb73lnYPvAl0FcmP6zsEwkoeWAz7CwcXX5Qm6V5Xo3cO9RicXp1M%2Be8QT%2BhKwZvAE7w%3D%3D&Expires=1704440450"
}
```
- This API retrieve detailed information about a seat chart.
- Validation check:
 - if input is not a number will return error with status code `400`:
 ```
    {
    "type": [
        "Not a valid integer."
        ]
    }
 ```
 - if `seat_chart_id` does not exist in the system will return code `404`:

 ```
    {
    "status": false,
    "message": "Id: '3311' not found!"
    }
 ```
## CSC0003_listEmployee
- GET `/CSC0003/listEmployee`
- Parameter :
    - `page` : must be a number (required)
    - `number_of_page` : Number of members displayed on a page.Must be a number (optional)
    - `keysearch` : search keywords (optional)
    - `seatchart_id`: id of seat chart (optional)
- Example return data for input `page` = 1 :
```
    {
    "number_of_page": 120,
    "total_record": 120,
    "status": true,
    "message": "get data succes",
    "page": 1,
    "list": [
        {
            "employee_id": "0506",
            "employee_name": "PHAN TRƯỜNG THỦY",
            "avatar": "0506.png",
            "position_id": "21",
            "position_name": "Manager",
            "department_id": "19",
            "department_name": "システム開発 2部",
            "official_date": "2013-09-23",
            "seat_chart": [
                {
                    "employee_id": "0506",
                    "seat_chart_id": 331,
                    "seat_chart_name": "TSA"
                },
                {
                    "employee_id": "0506",
                    "seat_chart_id": 330,
                    "seat_chart_name": "QTSC"
                }
            ]
        }
    ]
}
```
- If we input only page API wil return all member exist in the system
- We can see here that 120 records are returned, but I only took 1 record as an example
- If optional items are entered, the corresponding data will be returned
- Validation check:
- `page` `number_of_page` `seatchart_id` must be a number.If one of this input is not a number will return error with status code `400`: 
 ```
    {
    "page": [
        "Not a valid integer."
        ]
    }
 ```
- If not input `page` will return error with status code `400`: 
 ```
    {
    "_schema": [
        "Invalid input type."
        ]
    }
 ```
## CSC0004_addSeatChart
- POST `/CSC0004/addSeatChart`
- Allows you to submit a new seatchart.
- The request body needs to be in JSON format and include the following properties:
    - `is_clone` - boolean - required (Used to determine whether you are creating a new seat chart or duplicate seat chart from another seat chart)
    - when `is_clone`=true:
        - `name` - string - required (length from 2 to 20 and must be the name of the seat chart available in the system)
    - when `is_clone`=false:
        - `name` - string - required (length from 2 to 20 and must **not** be the name of the seat chart available in the system)
        - `info` - String - required 
        - `type` - integer - required (must be 1 or 2)
        - `layout` - integer - required (must be 1 or 2)
- Example input data:
    - `is_clone`= false:
    ```
    {
    "is_clone": false,
    "name": "test12345",
    "info": null,
    "type": 1,
    "layout": 1
    }
    ```
    - `is_clone`=true:
    ```
    "is_clone": true,
    "name": "QTSC",
    ```
- Example create success should return like that :
```
{
    "status": true,
    "message": "Create seat chart success!",
    "url_upload": "https://seat-chart.s3.amazonaws.com/available/1234_416.svg?AWSAccessKeyId=ASIA2G6CIH5XAYELOD5C&Signature=bb25Laz8JgAbOm2eMy%2FPHqFyw8M%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEDcaDmFwLXNvdXRoZWFzdC0xIkgwRgIhALxzLt%2FG2pv10l0iSOIpsw0Us70aM5OpSRmLNy3BMwwoAiEAv3OM%2FxmZdOUfPjGz7H4P0NHjfhUeQDZv%2B%2B2MEN1fy5YqnwMI0P%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARADGgw3MDIwOTc2Njk5OTgiDEuX63NQGpPgrGb16irzAtxHZSjTy87f48Aes7SPp9OYBoK96RPvQuFTAu%2BsuqKHhDJHWqlwR0x6OFwlUQl5DfaCC8v6iYWFyHIYrjw7z632eztDwBZ%2FhP3zQllVTf2Ri1UGOSrEMVK9hpZNa4zK831A8KlCrRjfIUy9kGUwjc0RvnqOOLzmyhqLrn4LbNZjuRUDt%2B01gTyl5r2mKGL%2BdTWekwqoSQxWx%2F1aOjTEtuMSMqHCsAWzp0uf6%2B8Tc4h65oj6rRpO2qTg2NnZFHJc1P%2Fut3KerNla4yBFsC8MUsqqziFL9GDRL6EJ%2BeIKFdJGdNKOQsfAI0vX8yZsiLCRJ187j4bzKyjgY3mXRfwpbiOQOf2OuvkjalBK7I51gorrKf2payCobwVfPV9vCPBaEE2Z1oAkyaMoSHO9OBqTiKHuq1aOEuxBqmwJ0aiKD6XLy8ypCpg11BXFQCmVAun0PyVynqp2d3DYI3xIQwmaZ%2BxHQ6UnHjoSjSqxaLDQuoQZSVILMJG87qwGOpwBFUDbdHowUN5bzxwZThb7RTo1hMDe%2BAvBGzPEOZPYwTkNX7Okrw8IfeXU9n2Y3Thfa8TWw9OpzXKbxMVhDC775sgszCXsL8dZPWNFIOc2UGe3UR8FF7maI62FZf3m8kfZjoe2UEi9fHLsxh%2B55iWWDm8G2Mn%2FgMGRVq4Rp2BbgnEkNibRcicbcYQhFWwjrEcx219Q1W%2B5HGE3hezZ&Expires=1704700371",
    "data": {
        "id": 416
    }
}
```
- Validation check :
    - If one of required field is missing will be return `400` code and messenger . Example for `is_clone` is missng:
    ```
    {
    "is_clone": [
        "Missing data for required field."
        ]
    }
     ```
    - If `name` not enought length from 2 to 20 will return code `400` and messenger error:
    ```
    "The Name of seatchart must have between 2 and 20 characters."
    ```
    - If `type` or `layout` is not an integer will return code `400` and messenger error for example:
    ```
    {
    "type": [
        "Not a valid integer."
        ]
    }
    ```
    - If `type` or `layout` is not 1 or 2 will return code `400` and messenger error for example:
    ```
    {
    "type": [
        "Must be one of: 1, 2."
        ]
    }
    ```
    - If `is_clone`=false and Seat chart name already exists in the system will return code `400` and messenger error for example:
    ```
    {
    "status": false,
    "message": "Name: '111' already exists in the system"
    }
    ``` 
## CSC0004_updateSeatChart
- PUT `/CSC0004/updateSeatChart`
- Edit name and type of an existing seat chart.
- The request body needs to be in JSON format and include the following properties:
    - `id` - integer - required (must be the id of the seat chart available in the system)
    - `name` - string - required (length from 2 to 20 and must **not** be the name of the seat chart available in the system)
    - `type` - integer - required (must be 1 or 2) 
- Example update success should return like that:
```
{
    "status": true,
    "message": "Update seatchart success.",
    "url_upload": "https://seat-chart.s3.amazonaws.com/available/123_412.svg?AWSAccessKeyId=ASIA2G6CIH5XAXHECFJP&Signature=nCSpqJ8FTACHiyd5P8ItyltxbEY%3D&x-amz-security-token=IQoJb3JpZ2luX2VjEDcaDmFwLXNvdXRoZWFzdC0xIkcwRQIgcJXZHAW2lwvmPmMTsq19ajuMlzoRF8dPrdi4zg%2FKaPQCIQDbGemWG5alUNyEExm4nCr7FCoHkXacZ8pYSo5wM64eXCqlAwjQ%2F%2F%2F%2F%2F%2F%2F%2F%2F%2F8BEAMaDDcwMjA5NzY2OTk5OCIM9aI%2F73bRw%2FuQRXsfKvkCZBgwtT5svwAUML%2BjBDganeoIaL0aNsuT1RoG2E5fo98t8mZLJ73dJWrApQ938D57sgKEQYcYlxwi%2BxKWK1UVXrRbHWfNYdjWTSdaiIHn3WvDtCuVWsCl2yRRx%2BkCFsqfe1VKlv4S%2FOjW4dgAQjvb%2BUvt5iIfoslNJOiJsXkRmaN9VjUrhst1SWVgG5H28cmfAYNpq23YjioXbjrPzpv1Fvf%2B0Vxh54D%2BDc7cutviYuKdpfXrg2kNW35FdJQusP%2B2XfEJpm0%2B5TOvZygc%2Bw%2FtGVXvhafMPbs1zE1JuIGGvONpieaqOMKv2sSxdrzihYFdGa4%2BK%2BdY%2B7tz7ediozQS6VqCiqIG5vj294UuG8rMXsFtvX5cF%2BcuQG5sCzhljqMSR3TJHi817lWiyAPmmkNsRd%2BnshvBK9NYISZx%2B0Yybw%2F2WkTMSqpA7Jk4A02tv3CJqYqKf%2B9k%2FxYAu0nQxmHnV7LESaunsWPd%2F5rEVMNByweu%2FNuRqlSmkmowjbjurAY6nQF71bYyfVi74SY8faXMit%2FcIQyaxPaz%2FS7rsDM8Zd8Q6FNTnfpljRolCI1TlRlNKm60J4wpIrvfYtObtBOGJfZDqb9%2BVXN5OWwuaveFZVsyUSJESn1kjSbjwQD3n2xlFaE%2Btq7kDn%2Fms7I4RbzBYAdT5ysNdjqUBZYc2WObIjcuPcq7jCpKcmgumY0o2rM9zcpHfkgvoGPSaZYGHgqt&Expires=1704700477"
}
```
- validation check :
    - If `name` not enought length from 2 to 20 will return code `400` and messenger error:
    ```
    "The Name of seatchart must have between 2 and 20 characters."
    ```
    - If `name` already exists in the system will return code `400` and messenger error for example:
    ```
    {
    "status": false,
    "message": "Name: '111' already exists in the system"
    }
    ```
    - If input `id` is not a integer or blank will return error :
    ```
    {
    "id": [
        "Not a valid integer."
        ]
    }
    ```
    - If input `id` not already exists in the system will return code `404` and messenger error for example :
    ```
    {
    "status": false,
    "message": "Id: '9999' not found!"
    }
    ```
    - If `type` is not an integer will return code `400` and messenger error for example:
    ```
    {
    "type": [
        "Not a valid integer."
        ]
    }
    ```
    - If `type` is not 1 or 2 will return code `400` and messenger error for example:
    ```
    {
    "type": [
        "Must be one of: 1, 2."
        ]
    }
    ```
## CSC0004_deleteSeatChart
- DELETE `/CSC0004/deleteSeatChart`
- Delete an existing seat chart.
- The request body needs to be in JSON format and include the following properties:
    - `id` - integer - required (must be the id of the seat chart available in the system)
- Example delete success should return like that:
```
    {
    "status": true,
    "message": "Delete seat chart: TSA 3 success.",
    "data": {
        "id": "361"
        }
    }
```
- Validation check :
    - If input `id` is not a integer or blank will return error :
    ```
    {
    "id": [
        "Not a valid integer."
        ]
    }
    ```