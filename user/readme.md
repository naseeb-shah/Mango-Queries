# Collection - users

### Find all the female users

```bash
db.users.find({gender: "Female"})
```

### Find all the female users who speak one of the two languages Kannada, Hindi

```bash
db.users.find({$and: [{gender: "Female"},{$or: [{language: "Hindi"},{language: "Kannada"}]}]})
```

### Find all the male users who can speak Hindi and female users who can speak Kannada

```bash
db.users.find({$or: [{$and: [{gender: "Male"},{language: "Hindi"}]},{$and: [{gender: "Female"},{language: "Kannada"}]}]})
```

### Find all the users who wear the shirt size S

```bash
db.users.find({shirt_size: "S"})
```

### Find all the female users who wear the shirt size XL

```bash
db.users.find({$and:[{gender: "Female"},{shirt_size: "XL"}]})
```

### Find all the English speaking male users and Hindi speaking female users

```bash
db.users.find({$or: [{$and: [{gender: "Male"},{language: "English"}]},{$and: [{gender: "Female"},{language: "Hindi"}]}]})
```

### Find all the male users who can speak Hindi or English and female users who can speak Kannada or German

```bash
db.users.find({$or: [{$and: [{gender: "Male"},{$or: [{language: "English"}, {language: "Hindi"}]}]},{$and: [{gender: "Female"},{$or: [{language: "Kannada"},{language: "German"}]}]}]})
```

### Find all the female users who can speak Bengali who wear shirt size XL and male users who speak German and wear shirt size either L or M

```bash
db.users.find({$or: [{$and: [{gender: "Male"}, {language: "German"},{$or: [{shirt_size: "L"}, {shirt_size: "M"}]}]},{$and: [{gender: "Female"}, {language: "Bengali"}, {shirt_size: "XL"}]}]})
```

### Find all the female users who speak any of the Indian languages (Hindi, Punjabi, Bengali, Gujarati, Tamil, Malayalam)

```bash
db.users.find({$and: [{gender: "Female"}, {language: {$in: ["Hindi", "Punjabi", "Bengali", "Gujarati", "Tamil", "Malayalam"]}}]})
```

### Men who can speak Korean

```bash
db.users.find({$and: [{gender: "Male"}, {language: "Korean"}]})
```
