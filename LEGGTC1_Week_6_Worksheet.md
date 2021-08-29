# Exercise 6-1 Nulls and Data Modification

## Sakila Database

You don’t have modification rights to sakila (or shouldn’t! Please tell me if you find that you  do). So these queries are all working with nulls

### Queries

1. Which staff member does not have a picture? (answer: Jon Stephens)
```sql

```
2. Which customers paid for something that was not a video rental?
```sql

```
3. Which cities do not appear in the address table? There are six. Create two queries to provide this answer: 
   - Use a subselect
   - Use a left join.
```sql

```
## SQLite 

Using the pizza database from Week 4. With all modifications you should check the records affected  with a select statement before performing the modification. 

### Insert

1. Insert a new customer Alice who is 23 years old
```sql

```

2. Alice likes the same pizza’s as Amy. Insert records into Eats based on Amy’s food choice
```sql

```

3. Alice goes to all pizzerias which serves mushroom pizza’s – insert these records into Frequents
```sql

```
### Update

4. It turns out that Cal is female – update her record
```sql

```
5. New York Pizza has been purchased by ‘Kiwi Pizza Company’. Change the name of all
references in both Serves and Frequents tables
```sql

```
6. The price of cheese increases by 10%. Increase the cost of all cheese pizza’s by 10% (added challenge – make sure the price is rounded to two decimal places)
```sql

```

### Delete 

7. Ben decides he no longer likes cheese pizza’s. Remove cheese from the list of pizza’s he eats
```sql

```
8. Delete from ‘Frequents’ any pizzeria which does not serve a pizza which Ben now eats.
```sql

```
9. Alice stops going to any pizzeria where mushroom pizza’s are over $10. Delete records based on that price
```sql

```