<h1>Toast-Catcher-Game</h1>
<P>My name is Aman Kumar, and I have developed an exciting and interactive game called Toast-Catcher-Game using HTML, CSS, and JavaScript. This simple yet addictive game challenges players to catch falling toast slices using a moving plate, earning points for each successful catch while avoiding burnt toast.</P>

<h1>Concept and Gameplay</h1>
<P>The idea behind the game is straightforward—toast slices fall from the top of the screen, and the player must move the plate left or right to catch them. The game gets progressively harder, with increasing speed and random obstacles such as burnt toast, which deducts points if caught.</P>

<h1>Key Features</h1>
<P>Dynamic Toast Falling: Slices of toast fall at random positions with varying speeds.

Player-Controlled Plate: Users can move the plate left and right using keyboard keys.

Score System: Points are awarded for catching good toast and deducted for catching burnt toast.

Difficulty Scaling: As the game progresses, toast falls faster and more frequently.

Fun Animations: Toast flipping, bouncing effects, and sizzling burnt toast add an engaging visual element.</P>

<h1>Game Mechanics</h1>
<P>Start the game: Click the start button to begin.

Move the plate: Use arrow keys or mouse movement to position the plate under falling toast.

Catch toast: Successfully catching toast increases score.

Avoid burnt toast: If caught, it reduces points or triggers a penalty animation.

Progressive difficulty: Toast falls faster as time passes, making the game more challenging.</P>

<img src = "https://github.com/Amansinha110/Toast-Catcher-Game/blob/master/Screenshot%202025-06-01%20064941.png">
<a href = "https://amansinha110.github.io/Toast-Catcher-Game/"><img src = "https://github.com/Amansinha110/Toast-Catcher-Game/blob/master/OIP.jpeg"></a>

<h1>Click Blue Button For Play</h1>

```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Toast Catcher Game</title>
    <style>
        body { text-align: center; font-family: Arial, sans-serif; background-color: #f5e1a0; }
        #game-container { position: relative; width: 400px; height: 500px; margin: auto; border: 2px solid #333; background-color: #fff; overflow: hidden; }
        #plate { width: 100px; height: 20px; position: absolute; bottom: 10px; left: 150px; background-color: brown; border-radius: 10px; }
        .toast { width: 50px; height: 50px; position: absolute; top: 0; background: url('toast.png') no-repeat center/cover; }
    </style>
</head>
<body>

<h1>Toast Catcher Game</h1>
<p>Move the plate to catch toast!</p>
<div id="game-container">
    <div id="plate"></div>
</div>
<p>Score: <span id="score">0</span></p>
<button onclick="startGame()">Start Game</button>

<script>
    let score = 0;
    let plate = document.getElementById("plate");
    let gameContainer = document.getElementById("game-container");

    document.addEventListener("keydown", (event) => {
        if (event.key === "ArrowLeft" && plate.offsetLeft > 10) {
            plate.style.left = plate.offsetLeft - 20 + "px";
        }
        if (event.key === "ArrowRight" && plate.offsetLeft < 290) {
            plate.style.left = plate.offsetLeft + 20 + "px";
        }
    });

    function spawnToast() {
        let toast = document.createElement("div");
        toast.classList.add("toast");
        toast.style.left = Math.random() * 350 + "px";
        gameContainer.appendChild(toast);

        let fallInterval = setInterval(() => {
            toast.style.top = toast.offsetTop + 5 + "px";
            if (toast.offsetTop >= 450) {
                if (toast.offsetLeft > plate.offsetLeft - 50 && toast.offsetLeft < plate.offsetLeft + 100) {
                    score++;
                    document.getElementById("score").innerText = score;
                }
                gameContainer.removeChild(toast);
                clearInterval(fallInterval);
            }
        }, 50);
    }

    function startGame() {
        score = 0;
        document.getElementById("score").innerText = score;
        setInterval(spawnToast, 1500);
    }
</script>

</body>
</html>
```

<h1>Final Thoughts</h1>
<p>The Toast-Catcher-Game is designed to be fun, simple, and engaging with smooth animations and increasing difficulty. You can enhance the game further by tweaking AI logic, animations, and player interactions! 🚀 Let me know if you need help improving it.</p>
