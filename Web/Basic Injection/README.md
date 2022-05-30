## Basic Injection from [CTFLearn.com](https://www.ctflearn.com/challenge/88)

### This is a great basic example for a simple SQL Injection.
#### Upon arriving, we are greeted with this Website:
![image](https://user-images.githubusercontent.com/106492307/170979221-e8c5c98c-2a54-4407-9132-e70f914e0edb.png)

#### As like in every other Web-Challenge, i first looked through the source code, as it often contains hints aaand... BINGO:
![image](https://user-images.githubusercontent.com/106492307/170979555-6aa509ef-0b08-443f-ba00-32782c355748.png)

#### Just to see what output looks like, we're gonna try each of them and notice that 'Luke' will actually give us a result:
![image](https://user-images.githubusercontent.com/106492307/170979861-94bce9c8-a90f-4393-a4a6-230de3b07a59.png)

#### Although this knowledge isn't really neccessary to solve this challenge, sometimes it's good to know how many columns the output will contain.
#### Let's quickly look at the Syntax of the SQL-Query to get a better understanding of what we need to do:
![image](https://user-images.githubusercontent.com/106492307/170981141-25ef23fa-f7db-44b1-ae37-9d793aea6302.png)

#### The question to ask here is: How do we get the query to return ALL the columns in our table?
#### WHERE initiates a simple string comparison, which means we can also compare 2 strings of our own, by closing the name='' comparison and ORing another statement, where the result is known to be true in any case. One very simple example would be '1' = '1', as 1 will always and inevitably be equal to 1. This works with any other string though, so 'Alpaca' = 'Alpaca' would do the same! So our solution input could look like this:
```sql
' OR 'Alpaca' = 'Alpaca
```

#### Now let's test this query:
![image](https://user-images.githubusercontent.com/106492307/170982547-e1898154-13e7-448b-bcd5-7dc5b8e3256e.png)

#### Awesome, we just solved our first SQL-Injection Challenge :)
