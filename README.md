<?php
$servername = "localhost";
$username = "root";
$password = "";
$databasename = "sample";

$conn = new mysqli($servername, $username, $password, $databasename);

if($conn -> connect_errno){
    die("connection failed");
}else{
    echo "connection success";
}

?>




<?php
include 'db.php';

// $name = $_POST['full_name'];
// $email = $_POST['email'];
// $password = $_POST['pass'];

// $sql = "insert into user(full_name, email, pass) values ('$name', '$email', '$password')";

// if($conn->query($sql) === true){
//     echo "data inserted successfully";
// }else{
//     echo "error: ", $conn->error;
// }

// $conn->close();

if($_SERVER["REQUEST_METHOD"] == "POST"){
    $name = trim($_POST['full_name']);
    $email = trim($_POST['email']);
    $password = $_POST['pass'];

    if($name == "" || $email=="" || $password==""){
        die("please fill the values...");
    }

    $stmt = $conn->prepare("insert into user(full_name, email, pass) values(?,?,?)");
    $stmt->bind_param("sss", $name, $email, $password);

    if($stmt->execute()){
        header("location: index.html?success=1");
        exit;
    }else{
                echo "Error: " . $conn->error;
    }
    $stmt->close();
}
$conn->close();
?>
