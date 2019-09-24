---

title: Welcome to my website
layout: page
feature_image: /carlo_carracc80_funerali-dell-anarchico-galli_futurismo_riassunto_due-minuti-di-arte1.jpg
excerpt: "Welcome to the Marco Piangerelli website"
aside: false 

---

Computer Science Division & Math Division <br>
Polo 'Carla Lodovici' <br>
via Madonna delle Carceri 7 <br>
marco[dot]piangerelli[at]unicam[dot]it

{% include button.html text="Github" icon="github" link="https://github.com/MPiangerelli/" color="#0366d6" %} {% include button.html text="Twitter" icon="twitter" link="https://twitter.com/MPiangerelli" color="#0d94e7" %} {% include button.html text="LinkedIn" icon="linkedin" link="https://www.linkedin.com/in/marco-piangerelli-08392768/" color="#0d94e7" %} {% include button.html text="RG" icon="ResearchGate" link="https://www.researchgate.net/profile/Marco_Piangerelli/research" color="#48d1cc" %}


<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-148503736-1"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'UA-148503736-1');
</script>

# Count-down for FuturenTech Week 2019 Virtual Workshop 
<!DOCTYPE HTML>
<html>
<body>
<script>
// Set the date we're counting down to
var countDownDate = new Date("Jan 5, 2021 15:37:25").getTime();

// Update the count down every 1 second
var x = setInterval(function() {

  // Get today's date and time
  var now = new Date().getTime();
    
  // Find the distance between now and the count down date
  var distance = countDownDate - now;
    
  // Time calculations for days, hours, minutes and seconds
  var days = Math.floor(distance / (1000 * 60 * 60 * 24));
  var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  var seconds = Math.floor((distance % (1000 * 60)) / 1000);
    
  // Output the result in an element with id="demo"
  document.getElementById("demo").innerHTML = days + "d " + hours + "h "
  + minutes + "m " + seconds + "s ";
    
  // If the count down is over, write some text 
  if (distance < 0) {
    clearInterval(x);
    document.getElementById("demo").innerHTML = "EXPIRED";
  }
}, 1000);
</script>

</body>
</html>

