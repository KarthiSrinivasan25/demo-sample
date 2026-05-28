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




✔ Verified badge
✔ Company + logo
✔ Rating (not always 5)
✔ Result metric badge
✔ Tags (SaaS / Web / Ecom)
✔ Clean professional SaaS UI
✔ Your existing auto-changing system kept intact





<section class="testimonials-pro">
  <div class="container">

    <div class="testimonials-header text-center mb-5">
      <span class="badge">Testimonials</span>
      <h2>Trusted by global clients</h2>
      <p>Real results from real projects</p>
    </div>

    <div class="row g-4">

      <!-- MAIN -->
      <div class="col-lg-7">
        <div class="main-card" id="mainCard"></div>
      </div>

      <!-- SIDE -->
      <div class="col-lg-5">
        <div class="side-list" id="sideList"></div>
      </div>

    </div>
  </div>
</section>



.testimonials-pro {
  padding: 100px 0;
  background: #ffffff;
}

.testimonials-header .badge {
  background: #eef2ff;
  color: #4361ee;
  padding: 6px 14px;
  border-radius: 999px;
  font-size: 12px;
  font-weight: 600;
}

.testimonials-header h2 {
  font-size: 34px;
  font-weight: 800;
  margin-top: 10px;
}

.testimonials-header p {
  color: #64748b;
}

/* MAIN CARD */
.main-card {
  border: 1px solid #e2e8f0;
  border-radius: 18px;
  padding: 28px;
  background: #fff;
  transition: 0.3s ease;
  height: 100%;
}

.main-card.fade {
  opacity: 0;
  transform: translateY(10px);
}

/* TOP BAR */
.main-topbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.rating {
  color: #f59e0b;
  font-size: 14px;
}

/* VERIFIED */
.verified {
  font-size: 11px;
  background: #ecfdf5;
  color: #059669;
  padding: 3px 8px;
  border-radius: 20px;
  margin-left: 8px;
}

/* TITLE */
.main-card h3 {
  font-size: 22px;
  font-weight: 700;
  color: #1e293b;
}

/* TEXT */
.main-card p {
  color: #475569;
  margin-top: 12px;
  line-height: 1.7;
}

/* TAGS */
.tags {
  margin-top: 12px;
}

.tag {
  display: inline-block;
  font-size: 11px;
  padding: 4px 10px;
  border-radius: 20px;
  background: #f1f5f9;
  color: #334155;
  margin-right: 5px;
}

/* RESULT */
.result {
  margin-top: 12px;
  font-size: 12px;
  font-weight: 600;
  color: #4361ee;
}

/* USER */
.main-user {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-top: 20px;
}

.main-user img {
  width: 48px;
  height: 48px;
  border-radius: 50%;
}

.main-user strong {
  display: block;
}

.main-user span {
  font-size: 12px;
  color: #64748b;
}

/* SIDE */
.side-item {
  border: 1px solid #e2e8f0;
  border-radius: 14px;
  padding: 14px;
  margin-bottom: 12px;
  cursor: pointer;
  transition: 0.25s;
  background: #fff;
}

.side-item:hover {
  border-color: #4361ee;
  transform: translateY(-3px);
}

.side-item.active {
  border-color: #4361ee;
  box-shadow: 0 12px 25px rgba(67,97,238,0.12);
}

.side-item p {
  font-size: 13px;
  color: #334155;
}

.side-item span {
  font-size: 12px;
  color: #64748b;
}




<script>
const data = [
  {
    title: "A reliable development partner we trust.",
    text: "CodeStack built a scalable SaaS platform with clean architecture and fast performance.",
    name: "Arjun Mehta",
    role: "CEO, SaaS Analytics Platform",
    img: "https://randomuser.me/api/portraits/men/32.jpg",
    rating: 4.5,
    verified: true,
    result: "🚀 40% Faster Performance",
    tags: ["SaaS", "Backend", "Scalable"]
  },
  {
    title: "Excellent UI and backend execution.",
    text: "They delivered ahead of schedule with smooth UX and modern UI system.",
    name: "Sarah Johnson",
    role: "Founder, E-commerce Brand",
    img: "https://randomuser.me/api/portraits/women/44.jpg",
    rating: 5,
    verified: true,
    result: "📈 2x Conversion Rate",
    tags: ["E-commerce", "UI/UX", "Frontend"]
  },
  {
    title: "Highly professional engineering team.",
    text: "Strong communication and scalable backend system delivered perfectly.",
    name: "Michael Lee",
    role: "CTO, FinTech Company",
    img: "https://randomuser.me/api/portraits/men/76.jpg",
    rating: 4,
    verified: true,
    result: "⚡ 60% Faster API Response",
    tags: ["FinTech", "API", "Backend"]
  }
];

let current = 0;
let autoPlay = true;
let interval;

const mainCard = document.getElementById("mainCard");
const sideList = document.getElementById("sideList");

/* MAIN */
function renderMain(i) {
  const d = data[i];

  mainCard.classList.add("fade");

  setTimeout(() => {
    mainCard.innerHTML = `
      <div class="main-topbar">
        <div class="rating">
          ${"★".repeat(Math.floor(d.rating))}
          ${d.verified ? '<span class="verified">✔ Verified</span>' : ''}
        </div>
      </div>

      <h3>“${d.title}”</h3>
      <p>${d.text}</p>

      <div class="result">${d.result}</div>

      <div class="tags">
        ${d.tags.map(t => `<span class="tag">${t}</span>`).join("")}
      </div>

      <div class="main-user">
        <img src="${d.img}">
        <div>
          <strong>${d.name}</strong>
          <span>${d.role}</span>
        </div>
      </div>
    `;

    mainCard.classList.remove("fade");
  }, 200);
}

/* SIDE */
function renderSide() {
  sideList.innerHTML = "";

  data.forEach((d, i) => {
    sideList.innerHTML += `
      <div class="side-item ${i === current ? "active" : ""}" onclick="selectTestimonial(${i})">
        <p>${d.title}</p>
        <span>${d.name}</span>
      </div>
    `;
  });
}

/* SWITCH */
function selectTestimonial(i) {
  current = i;
  renderMain(current);
  renderSide();
  resetAuto();
}

/* AUTO */
function next() {
  current = (current + 1) % data.length;
  renderMain(current);
  renderSide();
}

function startAuto() {
  stopAuto();
  interval = setInterval(next, 5000);
}

function stopAuto() {
  if (interval) clearInterval(interval);
  interval = null;
}

function resetAuto() {
  stopAuto();
  if (autoPlay) startAuto();
}

/* INIT */
renderMain(current);
renderSide();
startAuto();

/* PAUSE ON HOVER */
mainCard.addEventListener("mouseenter", stopAuto);
mainCard.addEventListener("mouseleave", () => {
  if (autoPlay) startAuto();
});
</script>
