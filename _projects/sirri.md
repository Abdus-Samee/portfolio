---
title: JS Sirri
---
I built this following a tutorial on youtube. On starting the project, the user clicks the button and permission is wanted to access the microphone. The user starts speaking and
when he stops, his voice is converted to text and displayed on the screen. Moreover, a voice reiterates what the user told. Cool, isn't it?

<!--more-->

## Views

<div style="text-align:center;" class="text-div"></div>
<button type="button" name="talk" id="talk" class="btn btn-primary">Talk!</button>
<hr>

## More

For the time being, I haven't made a GitHub repository for this demo project. If I can broaden the idea more, then I will definitely give an update here.

<script>
    const SpeechRecognition = window.SpeechRecognition || window.webkitSpeechRecognition;
    const recognition = new SpeechRecognition();
    recognition.onstart = function(){
      console.log('voice activated...');
    }
    recognition.onresult = function(event){
      const current = event.resultIndex;
      const transcript = event.results[current][0].transcript;
      $('.text-div').empty();
      $('.text-div').append('<h1>' + transcript + '</h1>');
      readOutLoud(transcript);
    }
    $('#talk').on('click', function(){
      recognition.start();
    });

    function readOutLoud(message){
      const speech = new SpeechSynthesisUtterance();
      speech.text = message;
      speech.volume = 1;
      speech.rate = 1;
      speech.pitch = 1;
      window.speechSynthesis.speak(speech);
    }
</script>
