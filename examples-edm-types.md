Examples of EDM Types
=====================

### Integer (32-bit)

```javascript
{
  "field": {
      "type": "Edm.Int32",
      "name": "id",
      "nullable": false,
      "key": true,
  }
}
```

### Integer (64-bit)

```javascript
{
  "field": {
      "type": "Edm.Int64",
      "name": "id",
      "nullable": true,
      "key": false
  }
}
```

### String / Varchar (utf-8)

```javascript
{
  "field": {
      "type": "Edm.String",
      "name": "Name",
      "nullable": true,
      "key": false,
      "maxLength": "255",
      "fixedLength": false
  }
}
```

### String / Varchar (with default value)

```javascript
{
  "field": {
      "type": "Edm.String",
      "name": "Document",
      "nullable": true,
      "key": false,
      "maxLength": "255",
      "fixedLength": false,
      "defaultValue": "Untitled"
  }
}
```

### String / Varchar (fixed length)

```javascript
{
  "field": {
      "type": "Edm.String",
      "name": "Color",
      "nullable": true,
      "key": false,
      "maxLength": "6",
      "fixedLength": true
  }
}
```

### String / Varchar (ascii with non-stardard collation)

```javascript
{
  "field": {
      "type": "Edm.String",
      "name": "AsciiArt",
      "nullable": true,
      "key": false,
      "maxLength": "5",
      "fixedLength": true,
      "unicode": false,
      "collation": "1252LATIN1"
  }
}
```

### Boolean

```javascript
{
  "field": {
      "type": "Edm.Boolean",
      "name": "Active",
      "nullable": true,
      "key": false
  }
}
```

### DateTime (millisecond precision)

```javascript
{
  "field": {
      "type": "Edm.DateTime",
      "name": "Edited",
      "nullable": true,
      "key": false,
      "precision": 3
  }
}
```

### Float (double precision)

```javascript
{
  "field": {
      "type": "Edm.Double",
      "name": "Price",
      "nullable": true,
      "key": false
  }
}
```

### Float (single precision)

```javascript
{
  "field": {
      "type": "Edm.Single",
      "name": "Price",
      "nullable": true,
      "key": false
  }
}
```

### Float (fixed scale and precision)

```javascript
{
  "field": {
      "type": "Edm.Decimal",
      "name": "Price",
      "nullable": true,
      "key": false,
      "precision": 3,
      "scale": 3
  }
}
```

### Binary

```javascript
{
  "field": {
      "type": "Edm.Binary",
      "name": "File",
      "nullable": true,
      "key": false,
      "maxLength": "1024",
      "fixedLength": false
  }
}
```

### Binary (fixed length)

```javascript
{
  "field": {
      "type": "Edm.Binary",
      "name": "Flags",
      "nullable": true,
      "key": false,
      "maxLength": "16",
      "fixedLength": true
  }
}
```

### Time

```javascript
{
  "field": {
      "type": "Edm.Time",
      "name": "AlarmTime",
      "nullable": true,
      "key": false
  }
}
```

### DateTimeOffset

```javascript
{
  "field": {
      "type": "Edm.DateTimeOffset",
      "name": "ETA",
      "nullable": true,
      "key": false
  }
}
```

### Integer (8-bit unsigned)

```javascript
{
  "field": {
      "type": "Edm.Byte",
      "name": "Order",
      "nullable": true,
      "key": false
  }
}
```

### Integer (8-bit signed)

```javascript
{
  "field": {
      "type": "Edm.SByte",
      "name": "Offset",
      "nullable": true,
      "key": false
  }
}
```

### Integer (16-bit)

```javascript
{
  "field": {
      "type": "Edm.Int16",
      "name": "Population",
      "nullable": true,
      "key": false
  }
}
```

### Global Unique Identifier

```javascript
{
  "field": {
      "type": "Edm.Guid",
      "name": "id",
      "nullable": true,
      "key": false
  }
}
```

### Optional Documentation Properties (sample & description)

```javascript
{
  "field": {
      "type": "Edm.String",
      "name": "Name",
      "nullable": true,
      "key": false,
      "sample": "John Doe",
      "description": "This is the person's name"
  }
}
```
