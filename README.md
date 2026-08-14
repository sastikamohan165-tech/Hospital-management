<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>PurpleCare Hospital</title>
<style>
*{box-sizing:border-box}
body{margin:0;font-family:Arial,sans-serif;background:#f3e8ff;color:#3b0764}
header{background:#6d28d9;color:white;text-align:center;padding:20px}
header h1{margin:0}
nav{background:#3b0764;text-align:center;padding:12px}
nav a{color:white;text-decoration:none;margin:12px;font-weight:bold}
nav a:hover{color:#d8b4fe}
.container{width:90%;max-width:1000px;margin:20px auto}
.welcome{background:white;padding:20px;text-align:center;border-radius:10px;box-shadow:0 3px 10px #0002}
.welcome h2{color:#6d28d9}
.details{display:flex;gap:15px;margin:20px 0}
.box{flex:1;background:white;padding:18px;text-align:center;border-radius:10px;box-shadow:0 3px 10px #0002}
.box h3{color:#7e22ce}
h2{text-align:center;color:#6d28d9}
.services{display:flex;gap:15px;margin:20px 0}
.service{flex:1;background:white;padding:18px;text-align:center;border-radius:10px;box-shadow:0 3px 10px #0002;cursor:pointer;transition:.3s}
.service:hover{transform:translateY(-5px);background:#faf5ff}
.service h3{color:#7e22ce}
.doctors{display:flex;gap:15px;margin:20px 0}
.doctor{flex:1;background:white;padding:20px;text-align:center;border-radius:10px;box-shadow:0 3px 10px #0002;cursor:pointer;transition:.3s}
.doctor:hover{transform:translateY(-5px);background:#faf5ff}
.doctor h3{color:#7e22ce}
.icon{font-size:40px}
#doctorSection,#profileSection{display:none}
.profile{background:white;padding:25px;margin-top:20px;text-align:center;border-radius:10px;box-shadow:0 3px 10px #0002}
.profile h3{font-size:25px;color:#6d28d9}
.rating{font-size:22px;color:#eab308;font-weight:bold}
.review{background:#f5f3ff;padding:15px;margin:15px;border-radius:8px}
.bookBtn{width:80%;padding:12px;background:#6d28d9;color:white;border:0;border-radius:6px;cursor:pointer}
.bookBtn:hover{background:#4c1d95}
.card{background:white;padding:20px;border-radius:10px;box-shadow:0 3px 10px #0002}
.time{display:flex;justify-content:space-between;padding:10px;border-bottom:1px solid #ddd}
.form-box{background:white;padding:20px;border-radius:10px;box-shadow:0 3px 10px #0002}
.row{display:flex;gap:15px}
.group{flex:1;margin-bottom:15px}
label{display:block;font-weight:bold;margin-bottom:5px}
input,select,textarea{width:100%;padding:10px;border:1px solid #c4b5fd;border-radius:6px}
textarea{height:70px;resize:none}
button{width:100%;padding:12px;border:0;background:#6d28d9;color:white;border-radius:6px;cursor:pointer;font-weight:bold}
button:hover{background:#4c1d95}
.reset{background:#9333ea;margin-top:8px}
.error{display:none;color:red;font-size:12px;margin-top:4px}
.success{display:none;background:#dcfce7;color:#166534;padding:15px;margin-top:15px;border-radius:8px}
footer{margin-top:25px;background:#3b0764;color:white;text-align:center;padding:18px}
@media(max-width:700px){.details,.services,.doctors,.row{flex-direction:column}}
</style>
</head>
<body>
<header>
<h1>💜 PurpleCare Hospital</h1>
<p>Advanced Healthcare & Trusted Doctors</p>
</header>
<nav>
<a href="#home">Home</a>
<a href="#services">Departments</a>
<a href="#doctors">Doctors</a>
<a href="#timings">Timings</a>
<a href="#appointment">Appointment</a>
</nav>
<div class="container">
<section id="home" class="welcome">
<h2>👋 Welcome, Sastika!</h2>
<p>You are visiting PurpleCare Hospital.</p>
<p><b>Patient:</b> Sastika M</p>
<p><b>Role:</b> Patient</p>
</section>
<div class="details">
<div class="box">
<h3>🏥 Hospital</h3>
<p>PurpleCare Multispeciality Hospital</p>
</div>
<div class="box">
<h3>📍 Location</h3>
<p>Tamil Nadu</p>
</div>
<div class="box">
<h3>🚑 Emergency</h3>
<p>24 × 7 Available</p>
</div>
</div>
<h2 id="services">🩺 Our Departments</h2>
<section class="services">
<div class="service" onclick="showDoctors('cardiology')">
<h3>❤️ Cardiology</h3>
<p>Heart Care</p>
<small>👆 Touch to view doctors</small>
</div>
<div class="service" onclick="showDoctors('neurology')">
<h3>🧠 Neurology</h3>
<p>Brain Care</p>
<small>👆 Touch to view doctors</small>
</div>
<div class="service" onclick="showDoctors('dermatology')">
<h3>🧴 Dermatology</h3>
<p>Skin Care</p>
<small>👆 Touch to view doctors</small>
</div>
<div class="service" onclick="showDoctors('general')">
<h3>🩺 General Medicine</h3>
<p>Health Checkup</p>
<small>👆 Touch to view doctors</small>
</div>
</section>
<section id="doctorSection">
<h2 id="doctorTitle">Doctors</h2>
<div id="doctorList" class="doctors"></div>
</section>
<section id="profileSection" class="profile">
<div class="icon">👨‍⚕️</div>
<h3 id="profileName"></h3>
<p id="profileSpeciality"></p>
<p id="profileExperience"></p>
<p id="profileRating" class="rating"></p>
<div class="review">
<b>💬 Patient Message</b>
<p id="profileReview"></p>
</div>
<button class="bookBtn" onclick="goToAppointment()">
📅 Book With This Doctor
</button>
</section>
<h2 id="timings">🕐 Hospital Timings</h2>
<section class="card">
<div class="time">
<b>Monday</b>
<span>9 AM - 5 PM</span>
</div>
<div class="time">
<b>Tuesday</b>
<span>9 AM - 5 PM</span>
</div>
<div class="time">
<b>Wednesday</b>
<span>10 AM - 6 PM</span>
</div>
<div class="time">
<b>Thursday</b>
<span>9 AM - 5 PM</span>
</div>
<div class="time">
<b>Friday</b>
<span>9 AM - 4 PM</span>
</div>
<div class="time">
<b>Saturday</b>
<span>10 AM - 2 PM</span>
</div>
<div class="time">
<b>Sunday</b>
<span>Emergency Only</span>
</div>
</section>
<h2 id="appointment">📅 Book Appointment</h2>
<section class="form-box">
<form id="appointmentForm">
<div class="row">
<div class="group">
<label>Patient Name *</label>
<input type="text" id="name" placeholder="Enter name">
<div class="error" id="nameError">Enter name.</div>
</div>
<div class="group">
<label>Age *</label>
<input type="number" id="age" placeholder="Enter age">
<div class="error" id="ageError">Enter valid age.</div>
</div>
</div>
<div class="row">
<div class="group">
<label>Phone *</label>
<input type="text" id="phone" placeholder="10 digit number">
<div class="error" id="phoneError">Enter valid phone.</div>
</div>
<div class="group">
<label>Email *</label>
<input type="email" id="email" placeholder="Enter email">
<div class="error" id="emailError">Enter valid email.</div>
</div>
</div>
<div class="row">
<div class="group">
<label>Department *</label>
<select id="department">
<option value="">Select Department</option>
<option value="Cardiology">Cardiology</option>
<option value="Neurology">Neurology</option>
<option value="Dermatology">Dermatology</option>
<option value="General Medicine">General Medicine</option>
</select>
<div class="error" id="departmentError">
Select department.
</div>
</div>
<div class="group">
<label>Doctor *</label>
<select id="doctor">
<option value="">Select Doctor</option>
<option>Dr. Ananya</option>
<option>Dr. Rajesh</option>
<option>Dr. Arjun</option>
<option>Dr. Kumar</option>
<option>Dr. Priya</option>
<option>Dr. Meena</option>
<option>Dr. Suresh</option>
<option>Dr. Kavya</option>
</select>
<div class="error" id="doctorError">
Select doctor.
</div>
</div>
</div>
<div class="row">
<div class="group">
<label>Appointment Date *</label>
<input type="date" id="date">
<div class="error" id="dateError">Select date.</div>
</div>
<div class="group">
<label>Appointment Time *</label>
<select id="time">
<option value="">Select Time</option>
<option>09:00 AM</option>
<option>10:00 AM</option>
<option>11:00 AM</option>
<option>02:00 PM</option>
<option>03:00 PM</option>
<option>04:00 PM</option>
</select>
<div class="error" id="timeError">
Select time.
</div>
</div>
</div>
<div class="group">
<label>Symptoms</label>
<textarea id="symptoms" placeholder="Enter symptoms"></textarea>
</div>
<button type="submit">
💜 Confirm Appointment
</button>
<button type="button" id="resetBtn" class="reset">
🔄 Reset
</button>
<div class="success" id="successBox">
<h3>✅ Appointment Confirmed</h3>
<p id="result"></p>
</div>
</form>
</section>
</div>
<footer>
<p>💜 PurpleCare Multispeciality Hospital</p>
<p>Quality Care | Trusted Doctors | 24 × 7 Emergency</p>
<p>© 2026 PurpleCare Hospital</p>
</footer>
<script>
const doctors = {
cardiology: [
{
name:"Dr. Ananya",
speciality:"Cardiologist",
experience:"12 Years Experience",
rating:"⭐ 4.9 / 5",
review:"Very caring doctor. Explained the treatment clearly and patiently."
},
{
name:"Dr. Rajesh",
speciality:"Cardiologist",
experience:"10 Years Experience",
rating:"⭐ 4.8 / 5",
review:"Excellent doctor with friendly and professional care."
}
],

neurology: [
{
name:"Dr. Arjun",
speciality:"Neurologist",
experience:"10 Years Experience",
rating:"⭐ 4.8 / 5",
review:"Very experienced and explains every medical issue clearly."
},
{
name:"Dr. Kumar",
speciality:"Neurologist",
experience:"8 Years Experience",
rating:"⭐ 4.7 / 5",
review:"Good treatment and very supportive with patients."
}
],

dermatology: [
{
name:"Dr. Priya",
speciality:"Dermatologist",
experience:"8 Years Experience",
rating:"⭐ 4.7 / 5",
review:"My skin problem improved a lot after the treatment."
},
{
name:"Dr. Meena",
speciality:"Dermatologist",
experience:"6 Years Experience",
rating:"⭐ 4.6 / 5",
review:"Friendly doctor and gives simple treatment advice."
}
],
general: [
{
name:"Dr. Suresh",
speciality:"General Physician",
experience:"15 Years Experience",
rating:"⭐ 4.9 / 5",
review:"Very experienced doctor with excellent patient care."
},
{
name:"Dr. Kavya",
speciality:"General Physician",
experience:"7 Years Experience",
rating:"⭐ 4.7 / 5",
review:"Kind doctor and gives proper health guidance."
}
]

};
function showDoctors(department) {
try {
const section =
document.getElementById("doctorSection");
const list =
document.getElementById("doctorList");
const title =
document.getElementById("doctorTitle");
list.innerHTML = "";
const selected =
doctors[department];
if (!selected) {
throw new Error("Department not found");
}
title.innerHTML =
"👨‍⚕️ " +
department.charAt(0).toUpperCase() +
department.slice(1) +
" Doctors";
selected.forEach(function(doctor,index) {
const card =
document.createElement("div");
card.className = "doctor";
card.onclick = function() {
showProfile(department,index);
};
card.innerHTML =
"<div class='icon'>👨‍⚕️</div>" +
"<h3>" + doctor.name + "</h3>" +
"<p>🩺 " + doctor.speciality + "</p>" +
"<small>👆 Touch to view profile</small>";
list.appendChild(card);
});
section.style.display = "block";
section.scrollIntoView({
behavior:"smooth"
});
}
catch(error) {
alert("Unable to load doctors.");
console.log(error);
}
}
function showProfile(department,index) {
try {
const doctor =
doctors[department][index];
document.getElementById("profileName")
.innerText = doctor.name;
document.getElementById("profileSpeciality")
.innerText =
"🩺 " + doctor.speciality;
document.getElementById("profileExperience")
.innerText =
"🕐 " + doctor.experience;
document.getElementById("profileRating")
.innerText =
doctor.rating;
document.getElementById("profileReview")
.innerText =
doctor.review;
document.getElementById("profileSection")
.style.display = "block";
document.getElementById("profileSection")
.scrollIntoView({
behavior:"smooth"
});
document.getElementById("doctor")
.value =
doctor.name;
let departmentName =
department.charAt(0).toUpperCase() +
department.slice(1);
if (department === "general") {
departmentName = "General Medicine";
}
document.getElementById("department")
.value =
departmentName;
}
catch(error) {
alert("Unable to load doctor profile.");
console.log(error);
}
}
function goToAppointment() {
document.getElementById("appointment")
.scrollIntoView({
behavior:"smooth"
});
}
const form =
document.getElementById("appointmentForm");
const name =
document.getElementById("name");
const age =
document.getElementById("age");
const phone =
document.getElementById("phone");
const email =
document.getElementById("email");
const department =
document.getElementById("department");
const doctor =
document.getElementById("doctor");
const date =
document.getElementById("date");
const time =
document.getElementById("time");
const successBox =
document.getElementById("successBox");
const result =
document.getElementById("result");
const resetBtn =
document.getElementById("resetBtn");
date.min =
new Date().toISOString().split("T")[0];
phone.addEventListener("input",function() {
if (phone.value.length > 10) {
phone.value =
phone.value.slice(0,10);
}
});
name.addEventListener("focus",function() {
name.style.background =
"#faf5ff";
});
name.addEventListener("blur",function() {
name.style.background =
"white";
});
department.addEventListener("change",function() {
if (department.value !== "") {
department.style.borderColor =
"green";
}
});
doctor.addEventListener("change",function() {
if (doctor.value !== "") {
doctor.style.borderColor =
"green";
}
});
resetBtn.addEventListener("click",function() {
form.reset();
successBox.style.display =
"none";
document.querySelectorAll(".error")
.forEach(function(error) {
error.style.display =
"none";
});
});
form.addEventListener("submit",function(event) {
event.preventDefault();
try {
let valid = true;
document.querySelectorAll(".error")
.forEach(function(error) {
error.style.display =
"none";
});
if (name.value.trim() === "") {
document.getElementById("nameError")
.style.display = "block";
valid = false;
}
if (
age.value === "" ||
age.value < 1 ||
age.value > 120
) {
document.getElementById("ageError")
.style.display = "block";
valid = false;
}
if (!/^[0-9]{10}$/.test(phone.value)) {
document.getElementById("phoneError")
.style.display = "block";
valid = false;
}
if (
!/^[^ ]+@[^ ]+\.[a-z]{2,3}$/
.test(email.value)
) {
document.getElementById("emailError")
.style.display = "block";
valid = false;
}
if (department.value === "") {
document.getElementById("departmentError")
.style.display = "block";
valid = false;
}
if (doctor.value === "") {
document.getElementById("doctorError")
.style.display = "block";
valid = false;
}
if (date.value === "") {
document.getElementById("dateError")
.style.display = "block";
valid = false;
}
if (time.value === "") {
document.getElementById("timeError")
.style.display = "block";
valid = false;
}
if (!valid) {
alert("Please fill all required fields.");
return;
}
result.innerHTML =
"Dear <b>" +
name.value +
"</b>, your appointment with <b>" +
doctor.value +
"</b> is confirmed on <b>" +
date.value +
"</b> at <b>" +
time.value +
"</b>.";
successBox.style.display =
"block";
successBox.scrollIntoView({
behavior:"smooth"
});
alert("Appointment booked successfully!");
}
catch(error) {
alert("Something went wrong!");
console.log(error);
}
});
</script>
</body>
</html>
