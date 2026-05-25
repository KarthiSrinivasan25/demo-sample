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




https://gramentheme.com/html/addina/index.html


From:
ரவி குமார்
12, அண்ணா நகர்,
தாம்பரம்,
சென்னை – 600045.
மொபைல்: 9876543210

To:
கிளை மேலாளர்,
Indian Bank
தாம்பரம் கிளை,
சென்னை – 600045.

தேதி: 25/05/2026

பொருள்: ATM கார்டு காணாமல் போனது குறித்து

மதிப்பிற்குரிய அய்யா / அம்மா,

நான் உங்கள் வங்கியின் வாடிக்கையாளர் ஆவேன். எனது சேமிப்பு வங்கி கணக்கு எண் 1234567890 ஆகும். எனது ATM / Debit Card காணாமல் போயுள்ளது. பல இடங்களில் தேடியும் கிடைக்கவில்லை.

எனவே, பாதுகாப்பு காரணங்களுக்காக எனது ATM கார்டை உடனடியாக Block செய்யுமாறு கேட்டுக் கொள்கிறேன். மேலும், எனக்கு புதிய ATM / Debit Card வழங்க தேவையான நடவடிக்கைகளை மேற்கொள்ளவும் தங்களை அன்புடன் கேட்டுக் கொள்கிறேன்.

நன்றி.

இப்படிக்கு,
ரவி குமார்

கையொப்பம்
(Ravi Kumar)

