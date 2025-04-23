# php-notes

## Databse connection and queries

$eid = 501;
$ename = "Rajesh Sharma";
$esal= 70000;
$edpet = "it";

$mycon = mysqli_connect("ipAddress of the database","username","password","mynewdata"); // returns a connection object

echo "connection established" 
$sql = "insert into emp values(?,?,?,?)"; // ? represents number of variables
$ps = $mycon -> prepare($sql); // prepares sql query and 
returns prepared statement object
// prepared statements are used for parameterized query
$ps->bind_param("isis",$eid,$ename,$esal,$edept) // "isis" bcus my table has column : integer,string,interger,string
$ps->execute();
echo "Data inserted successfully"


// fetching data :


<?php

$mycon = mysqli_connect("local host","root","pass","database-name")

echo "connection success";
$sql = "select * from employee"; // bcus no parameterized query, so no prepared statements
$record = $mycon->query($sql); // executes the query
$n = mysqli_num_rows($record); // counts the number of rows
echo "Total Record".$n;









?>


