
# Anypoint Template: APIkit OData Extension

+ [License Agreement](#licenseagreement)
+ [Use Case](#usecase)
+ [Model Definition](#model)
+ [Model Scaffolding](#scaffolding)

# License Agreement <a name="licenseagreement"/>
Note that using this template is subject to the conditions of this [License Agreement](AnypointTemplateLicense.pdf).
Please review the terms of the license before downloading and using this template. In short, you are allowed to use the template for free with Mule ESB Enterprise Edition, CloudHub, or as a trial in Anypoint Studio.

# Use Case <a name="usecase"/>

This template is designed to serve as a starting point to create an OData API using the APIKIT OData Extension.
Note that all the required dependencies have been already included, and within your API directory you will find a `odata.raml` file, with an example a data model ready to be scaffolded.

# Model Definition <a name="model"/>

The model described in your `odata.raml` file must be defined as a `RAML Library`, where each `DataType` represents an `EntityModel`, like:

```raml
#%RAML 1.0 Library
uses:
  odata: !include libraries/odata.raml

types:
  Employee:
    properties:
      id:
        type: integer
        (odata.key)
      name:
        type: string
```

You must annotate at least one of the properties on each `Entity` by using the annotation `(odata.key)`.

The following annotations are optional for each property:

- `(odata.nullable)`: bool
- `(odata.precision)`: int
- `(odata.scale)`: int

There's an optional `(odata.remote)` annotation for the `Entity`'s, that allow you to provide the name of the `Entity` in the remote data source.

```raml
types:
  Employee:
  (odata.remote): SAP_VBAK
    properties:
      ...
```

# EDM Types

This is a list of all the supported EDM types, and how to declare them using RAML types.

### Edm.String

The String type represents fixed or variable length character data.

```
type: string
```

### Edm.Boolean

The Boolean data type is used to represent the mathematical concept of binary valued logic. There are no applicable facets for this type.

```
type: boolean
```

### Edm.Double

The Double type represents a floating point number with 15 digits precision that can represent values with approximate range of ± 2.23e -308 through ± 1.79e +308.

```
type: number
```

### Edm.Single

The Single type represents a floating point number with 7 digits precision that can represent values with approximate range of ± 1.18e -38 through ± 3.40e +38

```
type: number
format: float
```

### Binary

The binary data type is used to represent fixed or variable length binary data.

```
type: file
```

### DateTime

The DateTime type represents date and time with values ranging from 12:00:00 midnight, January 1, 1753 A.D. through 11:59:59 P.M, December 31, 9999 A.D..

```
type: date
```

### Edm.Int32

The Int32 type represents a signed 32-bit integer value.

```
type: integer
```

### Edm.Int64

The Int64 type represents a signed 64-bit integer value.

```
type: integer
format: int64
```

### Edm.Int16

The Int16 type represents a signed 16-bit integer value.

```
type: integer
format: int16
```

### Edm.Byte

The Byte type represents an unsigned 8-bit integer value.

```
type: integer
format: int8
```

### Edm.Decimal

The Decimal type represents numeric values with fixed precision and scale. The required precision and scale can be specified using optional `precision` and `scale` properties. This type can describe a numeric value ranging from negative 10^255 + 1 to positive 10^255 -1.

```
type: number
(odata.precision): 3
(odata.scale): 3
```

### Edm.Guid

This Guid type, as specified in [RFC4122], represents a 16-byte (128-bit) unique identifier value.

```
type: string
(odata.type): guid
```

### Edm.Time

The Time type represents the time of day with values ranging from 0:00:00.x to 23:59:59.y, where x and y depend upon the `precision`.

```
type: date
(odata.type): time
```

### Edm.DateTimeOffset

The DateTimeOffset type represents date and time as an Offset in minutes from GMT, with values ranging from 12:00:00 midnight, January 1, 1753 A.D. through 11:59:59 P.M, December 9999 A.D.

```
type: date
(odata.type): offset
```


# Model Scaffolding <a name="scaffold"/>

Once your model is already defined in the `odata.raml` inside `src/main/api`, right click on it and select `Mule > Generate OData API from RAML types`

This will generate an `api.raml` in the same directory as your `odata.raml`, and it will scaffold all your OData API endpoints as flows in an `api.xml` file. From this point you can start implementing all the endpoints in that file.
