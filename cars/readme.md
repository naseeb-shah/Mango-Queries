# CARS QUERIES

### Men who own a Pink car

```bash
db.car_collections.find({$and: [{gender: "Male"},{car_color: "Pink"}]})
```

### Women who own a Red or a Blue Car

```bash
db.car_collections.find({$and: [{gender: "Female"},{$or: [{car_color: "Red"},{car_color: "Blue"}]}]})
```

### Men who purchased the car in the year 1998

```bash
db.car_collections.find({$and: [{gender: "Male"},{purchase_year:"1998"}]})
```

### Women who purchased a Yellow car in the year 1985

```bash
db.car_collections.find({$and: [{gender: "Female"},{car_color: "Yellow"},{purchase_year:"1985"}]})
```

### Men who either have a Red or Green car and either live in Germany or Kenya

```bash
db.car_collections.find({$and: [{gender: "Male"},{$or: [{car_color: "Green"},{car_color: "Red"}]},{$or: [{country: "Germany"},{country: "Kenya"}]}]})
```

### People from India who purchased cars in the year 2001

```bash
db.car_collections.find({$and: [{country: "India"},{purchase_year:"2001"}]})
```

### People from Germany or Egypt who purchased cars in the year 1998 or 1992

```bash
db.car_collections.find({$and: [{$or: [{purchase_year: "1998"},{purchase_year: "1992"}]},{$or: [{country: "Germany"},{country: "Egypt"}]}]})
```

### Women from India who own a Blue car

```bash
db.car_collections.find({$and: [{gender: "Female"},{country: "India"},{car_color:"Blue"}]})
```

### Men from Germany who purchased cars in 1998 and Men from Egypt who purchased cars in 1992

```bash
db.car_collections.find({$or: [{$and: [{country: "Germany"},{purchase_year: "1998"}]},{$and: [{country: "Egypt"},{purchase_year: "1992"}]}]})
```

### Women who own a Green car and are not from Pakistan

```bash
db.car_collections.find({$and: [{gender: "Female"},{car_color: "Green"},{country: {$nin: ["Pakistan"]}}]})
```
