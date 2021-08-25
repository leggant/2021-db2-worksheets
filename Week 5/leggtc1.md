# SQL Worksheet Assignment

This worksheet is worth 10% of your course. Submit a single text document (readable either by MS‐Word or notepad) named YOURUSERNAME  to your IN605 Git repository by September 10th 11:59pm with the statements to do the tasks listed below.

## Book Rating Database

You've started a new book‐rating website. You've been collecting data on reviewers' ratings of various books. There's not much data yet, but you can still try out some interesting queries. The scripts to create this database in SQLite are on the I: drive. A printout of the data is on the last page

### Schema:

**Book:** ( bID, title, published, author, genre ) Explanation: There is a book with ID number bID, a title, a first published year, a director and a genre.

**Reviewer:** ( rID, name ) Explanation: The reviewer with ID number rID has a certain name.

**Rating:** ( rID, bID, ratings, ratingDate ) Explanation: The reviewer rID gave the book bID a number of ratings (1‐5) on a certain ratingDate.

## Tasks

**Create SQL statements to achieve the following:**
*Use the techniques taught in class - zero marks for using a NATURAL JOIN or USING instead of ON*

### Queries

1. Find the titles and the genre of all books written by Harper Lee.
```sql
SELECT title, genre
FROM Book
WHERE author like "harper lee";
```
2. Find all years that have a book that received a rating of 4 or 5, and sort them in increasing order.
```sql
SELECT ratingDate
FROM Rating
WHERE ratings BETWEEN 4 and 5
and ratingDate IS NOT NULL
ORDER BY ratingDate;
```
3. Find the names of all reviewers who rated To Kill a Mocking Bird.
```sql
SELECT DISTINCT rev.name
FROM Reviewer rev
JOIN Rating ra
on rev.rID = ra.rID
Join Book bk
on ra.bID = bk.bID
where bk.title like "To Kill a Mocking Bird";
```
4. Some reviewers didn't provide a date with their rating. Find the names of all reviewers who have ratings with a NULL value for the date
```sql
SELECT DISTINCT rev.name
FROM Reviewer rev
JOIN Rating ra
on rev.rID = ra.rID
where ra.ratingDate is NULL;
```
5. for any rating where the reviewer is the same as the author of any book, return the reviewer name, book, title, and the ratings
```sql

```
6. rite a query to return the rating data in a more readable format (usings titles): reviewer name, book title, ratings, and ratingDate. Also, sort the data, first by reviewer name, then by book title, and lastly by ratings.
```sql

```
7. For all cases where the same reviewer rated the same book twice and gave it a higher rating the second time, return the reviewer's name and the title of the book.
```sql

```
8. For each book that has at least one rating, find the highest rating that book received. Return the book title and the rating. Sort by book title.
```sql

```
9. For each book, return the title and the 'rating spread', that is, the difference between highest and lowest ratings given to that book. Sort by rating spread from highest to lowest, then by book title.
```sql

```
10. Find the difference between the average rating of books released before 1970 and the average rating of books released after 1970. (Make sure to calculate the average rating for each book, then the average of those averages for books before 1970 and books after. Don't just calculate the overall average rating before and after 1970.)
```sql

```
## Modification 

11. Add the reviewer John Green to your database, with an rID of 209.
```sql

```
12. Insert 5‐star ratings by Daniel Lewis for all books in the database. Leave the review date as NULL. Do Not write five insert statements.
```sql

```
13. For all books that have an average rating of 4 or higher, add 25 to the published year. (Update the existing Rows; don't insert new Rows.)
```sql

```
14. Remove all ratings where the book year is before 1970 or after 2000, and the rating is fewer than 4.
```sql

```