# Finding-The-Date-of-Birth-Using-NIC-No-and-The-Logic-Behind-The-NIC-No
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.m
<title>Easy Code Stuff - NIC Birth Day Finder</title>
<script>
$(document).ready(function () {
$("#find").click(function () {
//Clear Existing Details
$("#error").html("");
$("#gender").html("");
$("#year").html("");
$("#month").html("");
$("#day").html("");
var NICNo = $("#nic").val();
var dayText = 0;
var year = "";
var month = "";
var day = "";
var gender = "";
if (NICNo.length != 10 && NICNo.length != 12) {
$("#error").html("Invalid NIC NO");
} else if (NICNo.length == 10 && !$.isNumeric(NICNo.substr(0
$("#error").html("Invalid NIC NO");
}e
lse {
// Year
if (NICNo.length == 10) {
year = "19" + NICNo.substr(0, 2);
dayText = parseInt(NICNo.substr(2, 3));
} else {
year = NICNo.substr(0, 4);
dayText = parseInt(NICNo.substr(4, 3));
} /
/ Gender
if (dayText > 500) {
gender = "Female";
dayText = dayText - 500;
} else {
gender = "Male";
} /
/ Day Digit Validation
if (dayText < 1 && dayText > 366) {
$("#error").html("Invalid NIC NO");
} else {
//Month
if (dayText > 335) {
day = dayText - 335;
month = "December";
}e
lse if (dayText > 305) {
day = dayText - 305;
month = "November";
}e
lse if (dayText > 274) {
day = dayText - 274;
month = "October";
}e
lse if (dayText > 244) {
day = dayText - 244;
month = "September";
}e
lse if (dayText > 213) {
day = dayText - 213;
month = "Auguest";
}e
lse if (dayText > 182) {
day = dayText - 182;
month = "July";
}e
lse if (dayText > 152) {
day = dayText - 152;
month = "June";
}e
lse if (dayText > 121) {
day = dayText - 121;
month = "May";
}e
lse if (dayText > 91) {
day = dayText - 91;
month = "April";
}e
lse if (dayText > 60) {
day = dayText - 60;
month = "March";
}e
lse if (dayText < 32) {
month = "January";
day = dayText;
}e
lse if (dayText > 31) {
day = dayText - 31;
month = "Febuary";
} /
/ Show Details
$("#gender").html("Gender : " + gender);
$("#year").html("Year : " + year);
$("#month").html("Month : " + month);
$("#day").html("Day :" + day);
}
}
});
});
</script>
</head>
<body>
<center>
<p style="color: #000;">NIC Birth Day Finder</p>
<p style="color: #000;">Both New & Old Format</p>
<input type="text" id="nic" />
<button id="find">Find</button>
<br/>
<br/>
<p id="error" style="color: red;"></p>
<p id="gender" style="color: #000;"></p>
<p id="year" style="color: #000;"></p>
<p id="month" style="color: #000;"></p>
<p id="day" style="color: #000;"></p>
</center>
</body>
</html>
