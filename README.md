<!DOCTYPE html><html lang="km">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>សារភាពស្នេហ៍</title>
<style>
body {
  font-family: 'Arial', sans-serif;
  text-align: center;
  background: linear-gradient(135deg,#ff9a9e,#fad0c4);
  height: 100vh;
  overflow: hidden;
  margin: 0;
  position: relative;
}h1 { margin-top: 120px; font-size: 42px; color: white; text-shadow: 2px 2px 5px rgba(0,0,0,0.3); position: relative; }

button { padding: 15px 35px; font-size: 20px; border: none; border-radius: 12px; cursor: pointer; position: absolute; }

#yes { background: #28a745; color: white; top: 50%; left: 45%; transform: translate(-50%, -50%); }

#no { background: #dc3545; color: white; top: 50%; left: 55%; transform: translate(-50%, -50%); }

#byline { color: black; font-size: 20px; position: absolute; top: 60%; left: 50%; transform: translateX(-50%); font-weight: bold; white-space: nowrap; } </style>

</head>
<body><h1 id="question">អូនព្រមធ្វើជាសង្សារបងអត់❤️</h1><button id="yes">Yes</button> <button id="no">No</button>

<div id="byline">BY: Matin❤️</div><script>
const yesBtn = document.getElementById('yes');
const noBtn = document.getElementById('no');

// Yes button click -> go to YouTube
yesBtn.addEventListener('click', ()=>{
    window.location.href = "https://youtu.be/-__W6u7gjGg?si=H0YUGIbrVcTu2aHm";
});

// No button click -> moves randomly in screen, keeping ~3cm gap from Yes
noBtn.addEventListener('click', ()=>{
    const maxX = window.innerWidth - noBtn.offsetWidth;
    const maxY = window.innerHeight - noBtn.offsetHeight;

    const yesRect = yesBtn.getBoundingClientRect();
    const minGap = 30; // approx 3cm

    let newX, newY;
    do {
        newX = Math.random() * maxX;
        newY = Math.random() * maxY;
    } while(Math.abs(newX - yesRect.left) < minGap || Math.abs(newY - yesRect.top) < minGap);

    noBtn.style.left = newX + 'px';
    noBtn.style.top = newY + 'px';
});

// Keep buttons and BY: Matin centered
function positionButtons(){
    const rect = document.getElementById('question').getBoundingClientRect();
    yesBtn.style.top = rect.bottom + 50 + 'px';
    noBtn.style.top = rect.bottom + 50 + 'px';
    yesBtn.style.left = '45%';
    noBtn.style.left = '55%';
    document.getElementById('byline').style.top = rect.bottom + 100 + 'px';
}
window.addEventListener('resize', positionButtons);
positionButtons();
</script></body>
</html>
