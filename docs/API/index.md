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
- Return list of seat chart.
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
 - if `input` is not a number will return error with status code `400`:
 ```
    {
    "type": [
        "Not a valid integer."
        ]
    }
 ```
## CSC0002_seatChart2DDetail
- GET `/CSC0002/seatChart2DDetail` 
- Retrieve detailed information about a seat chart.
- Require input param : `seat_chart_id` must be a number 
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
 