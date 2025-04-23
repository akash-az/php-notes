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
$record = $mycon->query($sql); // query function is used to execute the queries 
$n = mysqli_num_rows($record); // counts the number of rows
<!-- echo "Total Record".$n; -->

if($n>0){

echo "<table border =1>";
echo "<tr><th>Emp Id</th><th>Emp Name</th><th>Emp Salary</th><th>Emp Department</th></tr>";
while($row = mysqli_fetch_row($record)) // fetches row one by one , saves in $row

<!-- // if we use :  
   while($row = mysqli_fetch_assoc($record))

   {
    echo  echo $row['eid']. " " .$row['ename']. " ".$row['esal']." ".$row['edept'];//we have to use column names.
   } -->

{   
    // for representing data in a table
    echo "<tr>";
    echo "<td>.$row[0]</td>";
    echo "<td>.$row[1]</td>";
    echo "<td>.$row[2]</td>";
    echo "<td>.$row[3]</td>";

    <!-- echo $row[0]. " " .$row[1]. " ".$row[2]." ".$row[3];// displays each collumn of every row
    echo "<br>"; 
    echo "</tr>"; -->

}

 else {
    echo "<font color=red size=5>Record not found</font>"
 }

}


?>


