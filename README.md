# Library-DB-Model
Basic library DB model for book booking.

# What is this?
Very basic DB model for library book booking subsystem.

# Explanation
![Model](https://i.gyazo.com/c5d6249b4da4c8530ba6f2c73ba53bb4.png)

### Tables:
#### Book takeout table
Provides information on every booking/takeout made.

#### Reader
Data describing every registered library user.

#### Worker
Someone has to work.

#### Book
Info about the book itself.

------------------------------------------------------------------------

### Relationship:
The main goal of a library is to share books and provide everyone access to cheap or free knowledge. Therefore, three entities of Users (`Readers`), `Workers` and `Books` are present. And `Book Takeout` is a process that connects every entity together. There are many takeouts, but only a few books, a few readers and a few workers. Therefore the relationship of `Book Takeouts` is `many...one` with other tables.

------------------------------------------------------------------------

### Key information gathering
There is a need to gather the 3 most important pieces of information from data:
1. Book takeouts (what book, who took it, who gave it);
2. Book takeout and return history (when taken, when returned);
3. Late return managing (time spent over the limit, how big the fine is, who registered the return and when).

Using queries it is not difficult to collect desired information. Problems 1 and 2 are straight forward. However, the third is a little trickier. In order to calculate the time spent over the limit, there must be a limit in the first place. The formula for time spent over the limit is simple: `DaysOverLimit = ReturnDate(days) - TakeoutDate(days) - Limit(days)`.

To calculate how big the fine is, multiply `DaysOverLimit` with the 1 day over limit fee.

Who registered the return of the book and when is present in the table straight forward.

# Have a great day!
Seriously, have a great day!
