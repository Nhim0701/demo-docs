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
GET `/CSC0004/listSeatChartName`
Return list of seat chart.
Example return data
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
This API will return all seat chart available in the system if not input parameter.
Optional query parameters:
 - type : this version only have 2 type 1 or 2. that why if input another interger value will return `list :null`
Validation check:
 - if input is not a number will return error :
 ```
    {
    "type": [
        "Not a valid integer."
        ]
    }
 ```
 