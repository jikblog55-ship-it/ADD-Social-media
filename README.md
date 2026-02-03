<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Text to Speech</title>

<style>
  body{
    font-family: Arial, sans-serif;
    background:#f2f2f2;
    padding:20px;
  }

  .box{
    background:#fff;
    padding:15px;
    border-radius:8px;
    max-width:300px;
  }

  textarea{
    width:100%;
    height:100px;
  
    font-size:16px;
    padding:8px;
  }

  button{
    margin-top:10px;
    padding:10px;
    width:100%;
    font-size:16px;
    cursor:pointer;
  }
</style>
</head>

<body>

<h2>Text to Speech </h2>

<div class="box">
  <textarea id="text" placeholder="Yaha text likho..."></textarea>
  <button onclick="speakText()">Speak</button>
  <button onclick="stopSpeech()">Stop</button>
</div>

<script>
  let speech = new SpeechSynthesisUtterance();

  function speakText(){
    let text = document.getElementById("text").value;

    if(text === ""){
      alert("Pehle text likho");
      return;
    }

    speech.text = text;          // Text jo bolna hai
    speech.lang = "hi-IN";       // Hindi voice (en-US for English)
    speech.rate = 1;             // Speed
    speech.pitch = 1;            // Voice tone
    speech.volume = 1;           // Volume

    window.speechSynthesis.speak(speech);
  }

  function stopSpeech(){
    window.speechSynthesis.cancel();
  }
</script>

</body>
</html>
