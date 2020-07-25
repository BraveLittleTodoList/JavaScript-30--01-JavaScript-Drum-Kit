# Project Goal
- The Goal of this project is to create a Javascript Keyboard.

## Theory 
- My theory on how to accomplish this is to use an event listener 'onkeypress' to play the corresponding sound when a keyboard key is pressed.
- The same event listener might also be used for the styling.

## Final result

The main take aways from this project are these lines of code

window.addEventListener('keydown', function (e) {
const audio = document.querySelector(`audio[data-key="${e.keyCode}"]`);
audio.currentTime = 0
audio.play();
});

What this says is put an event listener on a keypress with e as the event object. Then the event object selects the audio element with the matching keyCode.

const key = document.querySelector(`div[data-key="${e.keyCode}"]`)
key.classList.add('playing')

What is is saying when the event object selects the audio element with the matching KeyCode add the class playing
to the key classes. This will then apply the transition stylings in the css.

Finally to smooth out the the transitions. We have to remove the playing class when the transitions are done.

function removeTransition(e) {

if  (e.propertyName ! = 'transform') return;

e.target.classList.remove('playing')

}

const keys = document.querySelectorAll(".key")

keys.forEach(key => key.addEventListener('transitionend', removeTransition)

## Take Aways 
This Project was a great exercise on 
