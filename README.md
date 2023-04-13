# Evan9b.github.io
My coop projects
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>Text Cypher</title>
<!-- Lines 9-16 are the style comments they change the backround colour and make the title font bigger-->
</head>
<style> body {
  background-color: lightblue;
}
p1{
  font-size: 100px;
}
</style>
<!-- Lign 18 aligns all the textboxs and labels to the center of the window-->
<body align = "center">
<!-- Lines 20-25 are the tittle on the window and then the textarea with its name and charecter restriction-->
  <p1> Text Cypher & Un-Cypher</p1>
  <form>
  Text Cypher!
 <textarea id="txts" maxlength="50">

 </textarea>
 <!-- lines 27-34 are all of the lables and buttons that appear on my window and their respective ids to store the texts and numbers that are typed on them-->
 <button type="button" onclick="paste();this.onclick=null;"> Cypher...</button>
</form>
<label for="a">Numerator:</label>
<input type="text" id="a" name="a">
<br>
<label for="b">Denominator:</label>
<input type="text" id="b" name="b">
<button type="button" onclick="fix()"> Un-Cypher</button>
<h3 id="empty-space">The Numerator is: </h3>
<h4 id="emptyspace">The Denominator is: </h4>
<h5 id="emptyspace1">Your decoded message is: </h5>
<!-- Openning the script so we can insert our java script code-->
<!-- Lines 38-42 get the text from the text area and store it into a variable which is then run through a for loop that switches out the letter to its corresponding number defined in the cypher variable -->
<script>
 
  var txt = document.getElementById("txts").value
  
  function paste(){
   let txt = document.getElementById("txts").value;
  var cypher = {"a":"1", "d":"4", " ":"2"}

  
for(let i=0; i<Object.keys(cypher).length; i++){
    txt = txt.replaceAll(Object.keys(cypher)[i], cypher[Object.keys(cypher)[i]]);

}
    
// The decial variable is used to change the number we get from the txt to a decimal number by adding 0. to the number and var b is fixed to 150
var decimal = parseFloat("0." + txt)
var b= 150;
// calculates a by mulitplying the other 2 numbers otgether and then prints them to the console, with a limitation of the texts length of charecters
 var a = b * decimal
 console.log("a", (a).toPrecision(txts.length))
 console.log("b", (b).toPrecision(txts.length))
 console.log("a/b",(a / b).toPrecision(txts.length))
 document.getElementById("empty-space").innerHTML += a
 document.getElementById("emptyspace").innerHTML += b
}

// This function takes the inputs from the denominator and numerator text boxes and turns c into a text instead of numbers by adding "" to it
function fix(){
    var ay = document.getElementById("a").value
    var be = document.getElementById("b").value
    var c = ay/be + ""
    
   var cypher1 = {"1":"a", "4":"d","2":" "}
// a forloop to cycle through the numbers to change them back to letters
   for(let i=0; i<Object.keys(cypher1).length; i++){
    c = c.replaceAll(Object.keys(cypher1)[i], cypher1[Object.keys(cypher1)[i]]);
}
console.log(c.substring(2))
document.getElementById("emptyspace1").innerHTML += c.substring(2)
}


</script>
</body>
</html>
Footer
© 2023 GitHub, Inc.
