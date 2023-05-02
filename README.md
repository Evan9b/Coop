<!-- Lines 2-7 are just to create the base webpage, classifying it as html and giving the tab a title-->
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>Text Cypher</title>
<!-- Lines 9-16 are the style comments they change the backround colour and make the title font bigger-->
</head>
<style> 
*{
  color: white;
}
button{
  color: black;
}
textarea{
  color: black;
}
p {
    font-size: 20px;
}
p1{
  font-size: 70px;
}
h4{
  font-size: 20px;

}
h3{
  font-size: 20px;
}
h5{
  font-size: 20px;
}
input{
  color: black;
}
a{
  color: black;
}
</style>
<!-- Lign 18 aligns all the textboxs and labels to the center of the window-->
<body style="background-image: url('Backround.jpg');">
 
<!-- Lines 20-25 are the tittle on the window and then the textarea with its name and charecter restriction-->

<p1> Text Cypher & Un-Cypher</p1>
<div style="width:500px;height: 100px; overflow:hidden;"></div>
<div style="width: 1200px;height: 400px; overflow: hidden;">
<div style="width:800px;height: 100px; float:left;">
  <form>
  <p>Insert your word to be Cyphered!:</p>
 <br>
  <textarea id="txts" maxlength="8" rows="10" cols="30">
</textarea>
 <!-- lines 27-34 are all of the lables and buttons that appear on my window and their respective ids to store the texts and numbers that are typed on them-->
 <button type="button" onclick="paste();this.onclick=null;"> Cypher...</button>
</form>
<div style="width:300px;height: 1px; float: left;">
<h3 id="empty-space">The First value is: </h3>
<h4 id="emptyspace">The Second value is: </h4>
</div>
</div>
<div style="width:450px;height:400px; float: right;">
  <div style="width: 400px;height: 400px;">
  <p> Insert your numbers to be Un Cyphered!:</p>
  <br>
  <label for="a">Numerator:</label>
<input type="text" id="a" name="a">
<br>
  <label for="b">Denominator:</label>
  <input type="text" id="b" name="b">
  <button type="button" onclick="fix()"> Un-Cypher...</button>
  <h5 id="emptyspace1">Your decoded message is: </h5>
</div>
</div>
</div>
<!-- Openning the script so we can insert our java script code-->
<!-- Lines 38-42 get the text from the text area and store it into a variable which is then run through a for loop that switches out the letter to its corresponding number defined in the cypher variable -->
<script>
  function paste(){
   let txt = document.getElementById("txts").value;
   //var cypher = {" ":"99","a":"01","b":"03","c":"04","d":"05","e":"06","f":"07","g":"08","h":"09","i":"11","j":"12","k":"13","l":"14","m":"15","n":"16","o":"17","p":"18","q":"19","r":"22","s":"23","t":"24","u":"25","v":"26","w":"27","x":"28","y":"29","z":"33","A":"34","B":"35","C":"36","D":"37","E":"38","F":"39","G":"44","H":"45","I":"46","J":"47","K":"48","L":"49","M":"55","N":"56","O":"57","P":"58","Q":"59","R":"66","S":"67","T":"68","U":"69","V":"77","W":"78","X":"79","Y":"88","Z":"89","?":"02"}
   let characters = ["A","B","C",  "D",  "E",  "F",  "G",  "H",  "I",  "J",  "K",  "L",  "M",  "N",  "O",  "P",  "Q",  "R",  "S",  "T",  "U",  "V",  "W",  "X",  "Y",  "Z"," "]

    let numbers = ["00", "01", "02", "03", "04", "05", "06", "07", "08", "09", "10", "11", "12", "13", "14", "15", "16", "17", "18", "19", "20", "21", "22", "23", "24", "25","26"]
    for(let i=0; i<characters.length; i++){
      txt = txt.replaceAll(characters[i], numbers[i]+"");
      console.log(txt, "in the cypher")
    }
    
// The decial variable is used to change the number we get from the txt to a decimal number by adding 0. to the number and var b is fixed to 150
var decimal = parseFloat("0." + txt)
var b= 150;
// calculates a by mulitplying the other 2 numbers otgether and then prints them to the console, with a limitation of the texts length of charecters
 var a = b * decimal
 //var d = BigInt
 console.log("a", (a))
 console.log("b", (b))
 console.log("a/b",(a / b))
 console.log(txt.length)
 console.log(decimal)
 //console.log(d)
 document.getElementById("empty-space").innerHTML += a
 document.getElementById("emptyspace").innerHTML += b
}

// This function takes the inputs from the denominator and numerator text boxes and turns c into a text instead of numbers by adding "" to it
function fix(){
    var ay = document.getElementById("a").value
    var be = document.getElementById("b").value
    var ce = (ay/be) + ""
    console.log(ce)
//var cypher1 = {"99":" ", "01":"a","03":"b","04":"c","05":"d","06":"e","07":"f","08":"g","09":"h","11":"i","12":"j","13":"k","14":"l","15":"m","16":"n","17":"o","18":"p","19":"q","22":"r","23":"s","24":"t","25":"u","26":"v","27":"w","28":"x","29":"y","33":"z", "34":"A","35":"B","36":"C","37":"D","38":"E","39":"F","44":"G","45":"H","46":"I","47":"J","48":"K","49":"L","55":"M","56":"N","57":"O","58":"P","59":"Q","66":"R","67":"S","68":"T","69":"U","77":"V","78":"W","79":"X","88":"Y","89":"Z","02":"?" }
let characters = ["A","B","C",  "D",  "E",  "F",  "G",  "H",  "I",  "J",  "K",  "L",  "M",  "N",  "O",  "P",  "Q",  "R",  "S",  "T",  "U",  "V",  "W",  "X",  "Y",  "Z", " "]

    let numbers = ["00", "01", "02", "03", "04", "05", "06", "07", "08", "09", "10", "11", "12", "13", "14", "15", "16", "17", "18", "19", "20", "21", "22", "23", "24", "25","26"]
    for(let i=0; i<characters.length; i++){
    //console.log(`replacing ${Object.keys(cypher1)[i]} with ${cypher1[Object.keys(cypher1)[i]]}`)
    //ce = ce.replaceAll(Object.keys(cypher1)[i], cypher1[Object.keys(cypher1)[i]]);
    ce = ce.replaceAll(numbers[i]+"", characters[i]);
    //console.log("=>",ce);
}
console.log(ce.substring(2))
document.getElementById("emptyspace1").innerHTML += ce.substring(2)
}


</script>
</body>
</html>




