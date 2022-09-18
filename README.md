<html>
<head>
<script async src="https://www.googletagmanager.com/gtag/js?id=G-FS3WN7E3DE"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-FS3WN7E3DE');
</script>
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<style>
input[type=checkbox] {
    width: 50px;
    height: 50px;
    vertical-align: middle;
}
.start{
    width: 200px;
    padding: 25px;
    box-sizing: border-box;
    border: 1px solid #68779a;
    background: #cbe8fa;
    cursor: pointer;
}
.ana{
    width: 100px;
    padding: 30px;
}
.ana2{
    width: 100px;
    padding: 15px;
    font-size: 20px;
}
.start {
  text-decoration: none;
  display: block;
  background: gray;
  color: #fff;
  height: 50px;
  border-radius: 20px;
  line-height: 40px;
  align-items: center;
  padding: 10px 0;
  line-height: 1;
  font-size: 25px;
  margin-top: 350px;
  box-shadow: 0 5px 0 rgba(0, 0, 0, 0.2);
  width: 200px;
}
</style>
<script>
window.onload = function() {
	var startTime;
	var time;

	function start() {
		for (var i = 0; i < document.moguratataki.ana.length; ++i) {
			document.moguratataki.ana[i].disabled = true;
			document.moguratataki.ana[i].checked = false;
		}
		startTime = Date.now();
		document.moguratataki.point.value = 0;
		document.moguratataki.start.disabled = true;
		tokei();
		mogura();
	}

	function tokei() {
		time = Math.floor((30 - (Date.now() - startTime)) / 1000);
		if (time <= 0) {
			for (var i = 0; i < document.moguratataki.ana.length; ++i) {
				document.moguratataki.ana[i].disabled = true;
			}
			document.moguratataki.time.value = 30;
			alert('ざっこww ' + document.moguratataki.point.value + '匹WWWWW');
			document.moguratataki.start.disabled = false;
			return;
		}
		document.moguratataki.time.value = time;
		setTimeout(tokei, 300);
	}

	function mogura() {
		if (time < 30) {
			document.moguratataki.time.value = time;
			for (var i = 0; i < document.moguratataki.ana.length; ++i) {
				document.moguratataki.ana[i].disabled = true;
				document.moguratataki.ana[i].checked = false;
			}
			for (var i = 0; i < 4; ++i) {
				var j = Math.floor(document.moguratataki.ana.length * Math.random());
				document.moguratataki.ana[j].disabled = false;
				document.moguratataki.ana[j].checked = true;
			}
			setTimeout(mogura, 900);
		}
	}

	function tataku(e) {
		if (!e.target.disabled) {
			e.target.disabled = true;
			document.moguratataki.point.value = +document.moguratataki.point.value + 1;
		}
	}

	document.moguratataki.start.addEventListener('click', start);
	for (var i = 0; i < document.moguratataki.ana.length; ++i) {
		document.moguratataki.ana[i].addEventListener('click', tataku);
	}
}
</script>
</head>
<body>
<center>
	<form name="moguratataki">
		<input type="button" name="start" value="start" class="start">
		<br>
		<br>
		<input type="text" name="time" value="Time" size="4" class="ana2" readonly>
		<input type="text" name="point" value="Score" size="4" class="ana2" readonly>
		<div style="margin:50px;">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<br>
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
                        <br>
                        <input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
                        <br> 
                        <input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
			<input type="checkbox" name="ana">
		</div>
	</form>
</center>
</body>
</html>
