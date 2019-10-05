

<html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
	<title>Mon to Unicode</title>
	
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
	<script src="./Mon to Unicode_files/rabbit.js.download"></script>
	<link rel="stylesheet" href="./Mon to Unicode_files/style.css">
    <link rel="stylesheet" href="./Mon to Unicode_files/saved_resource">
    <link rel="stylesheet" href="./Mon to Unicode_files/saved_resource(1)">
    <script type="text/javascript">
      function clearText() {
        document.getElementById("unicode").value = "";
        document.getElementById("zawgyi").value = ""
      }

  </script>
</head>
<body>
<div id="container">
	<header>
		<a href="https://web.facebook.com/themonproduction/"><img src="./Mon to Unicode_files/logo.gif"></a>
		<h2>A Chark</h2>
	</header>
  <br>
  
    <div id="textContainer">

        <section id="Unicode">
            <h3>Unicode</h3>
            <textarea id="unicode" onfocus="handleOnFocus(this)" onblur="handleOnBlur()">နာဲသုၚ်စောဲ Unicode ဟာ သုၚ်စောဲ Mon ဟာ ဟွံပြေပြံၚ်တှေ်စမ်ရံၚ်အဏံ တက်သီုၜါဘာသာဂွံ</textarea>
        </section>
        
        <section id="Zawgyi">
            <h3>Mon</h3>
            <textarea id="zawgyi" onfocus="handleOnFocus(this)" onblur="handleOnBlur()">နာဲသုင္ေစာဲ Unicode ဟာ သုင္ေစာဲ Mon ဟာ ဟြံေျပျပံင္ေတွ္စမ္ရံင္အဏံ တက္သီုၐါဘာသာဂြံ </textarea>
        </section>
    </div>
    <div id="textContainer">
    <section id="buttons">
        <input type="button" value="Clear Text" onclick="clearText()">
        <input type="button" value="Copy Mon" onclick="copyZawgyi()">
        <input type="button" value="Copy Unicode" onclick="copyUnicode()">
    </section>
  </div>
	<footer>
		Found a bug ? Please , open <a href="https://web.facebook.com/themonproduction/">new issue</a>.
	</footer>
</div>

<script>


var textFieldInFocus;
function handleOnFocus(form_element)
{
   textFieldInFocus = form_element;
}
function handleOnBlur()
{
   textFieldInFocus = null;
}

var unicode = document.getElementById("unicode");
var zawgyi = document.getElementById("zawgyi");

onchangeHandler(unicode,zawgyi,"uni2zg");
onchangeHandler(zawgyi,unicode,"zg2uni");

function converter(textField,tochangeField,toconv) {
    if(tochangeField != textFieldInFocus) {
        if(toconv == "uni2zg") {
              tochangeField.value = Rabbit.uni2zg(textField.value);
        }
        else {
             tochangeField.value = Rabbit.zg2uni(textField.value);
        }
    }
}

function onchangeHandler(textField,tochangeField,toconv) {
    
    if (textField.addEventListener) {
      textField.addEventListener('input', function() {
          converter(textField,tochangeField,toconv);
      }, false);
    } else if (textField.attachEvent) {
      textField.attachEvent('onpropertychange', function() {
        // IE
          converter(textField,tochangeField,toconv);
      });
    }
    
}

function copyZawgyi() {
  /* Get the text field */
  var copyText = document.getElementById("zawgyi");

  /* Select the text field */
  copyText.select(); 
  copyText.setSelectionRange(0, 99999); /*For mobile devices*/

  /* Copy the text inside the text field */
  document.execCommand("copy");
}

function copyUnicode() {
  /* Get the text field */
  var copyText = document.getElementById("unicode");

  /* Select the text field */
  copyText.select(); 
  copyText.setSelectionRange(0, 99999); /*For mobile devices*/

  /* Copy the text inside the text field */
  document.execCommand("copy");
}


</script>


</body></html>
