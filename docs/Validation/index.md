## Use marshmallow library to validate
### 1. Install the library: pip install marshmallow
### 2. Import marshmallow library
```
    from marshmallow import Schema, fields, ValidationError, validate
```
### 3.	Khởi tạo Schema 
```
   class RequestSchema(Schema):
    name = fields.Str(
        required=True,
        validate=[
            validate.Length(min=2, max=20,
                               error="The Name of seatchart must have between {min} and {max} characters."),
            validate.Regexp(r"^(?!\s*$).+",
                               error="The Name can't be empty string!")
        ]
    )
    is_clone = fields.Boolean(
        required=True
    )
    info = fields.Str(
        required=False,
        allow_none=True
    )
    type = fields.Int(
        required=False,
        validate=validate.OneOf([1,2])
    )
    layout = fields.Int(
        required=False,
        validate=validate.OneOf([1,2])
    )
 
```
### 4. properties:
    - page = fields.Int(): Defines the data type (Str, Boolean,…)
    - required=True (or False): Constraint settings
    - allow_none=True (or False): allowed Null or not
    - validate: https://marshmallow.readthedocs.io/en/stable/quickstart.html#validation

### 5. Perform validation
```
    body = json.loads(event['body'])
    RequestSchema().load(body)

```

### 6. Validate except
```
    except ValidationError as validErr:
        response = validErr.messages
```