Wrapper for the PDO Class. Easy SQl query.

For each user is created only one connection for each database. 

Install
=======
```
composer require pyataks/sinlgularpdo
```

Documentation
=============

###Create connection
```
$db = DBConnect::connect('mysql:dbname=db_name;host=localhost','root','');
```
###Create new query
```
$query = new DBQuery($db);
```
####Examples of queries

```
$selectAll = $query->queryAll('SELECT * FROM users');

$selectColumn = $query->queryColumn('SELECT email FROM users');

$data = [
    'email' => 'user1@example.com',
    'password' => password_hash('q1234')
];
$rowCount = $query->execute("INSERT INTO `users` (`email`, `password`) VALUES (:email, :password)", $data);
```
