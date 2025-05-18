# Final Lab Task 6: MongoDB Practice

## Query Statements

```sql
use mongo_practice
```
### Create Database

![Sample Output](images/1.PNG)

### Insert Documents

![Sample Output](images/docs1.PNG)

![Sample Output](images/doc2.PNG)

### Query Find
```sql
db.movies.find()
```
![Sample Output](images/2.PNG)

![Sample Output](images/3.PNG)

```sql
db.movies.find({writer:”Quentin Tarantino”})
```
![Sample Output](images/Q.PNG)

```sql
db.movies.find({actors:”Brad Pitt”})
```
![Sample Output](images/B.PNG)

```sql
db.movies.find({franchise:”The Hobbit”})
```
![Sample Output](images/H.PNG)

```sql
db.movies.find({year:{$gt:”1990”, $lt:”2000”}})
```
![Sample Output](images/1990.PNG)

```sql
db.movies.find({$or:[{year:{$gt:”2010”}},{year: {$lt:”2000”}}]})
```
![Sample Output](images/2010.PNG)

### Update Documents

![Sample Output](images/update.PNG)

### Text Search

![Sample Output](images/search.PNG)

### Delete Documents

![Sample Output](images/delete.PNG)


