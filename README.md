<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Naruto Inspiration</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <div class="card">
    <img 
      src="https://i.postimg.cc/kMc82yZw/Naruto-Et-Ses-Amis.jpg" 
      alt="Naruto and Friends" 
      id="characterImage"
    />
    <div class="dialogue" id="dialogue">Believe it!</div>
  </div>

  <script>
    const dialogues = [
      "Believe it! – Naruto Uzumaki",
      "Hard work is worthless for those that don’t believe in themselves.",
      "When you give up, your dreams and everything else, they're gone.",
      "A smile is the best way to get away with trouble.",
      "Power comes in response to a need, not a desire.",
      "A hero always arrives late – but he never gives up!",
      "In this world, wherever there is light – there are also shadows.",
      "It's not the face that makes someone a monster; it's the choices they make."
    ];

    const dialogueElement = document.getElementById('dialogue');
    const image = document.getElementById('characterImage');

    image.addEventListener('click', () => {
      const randomIndex = Math.floor(Math.random() * dialogues.length);
      
      // Trigger animation class
      image.classList.add('image-clicked');
      dialogueElement.classList.remove('fade-up');
      void dialogueElement.offsetWidth; // force reflow to restart animation
      dialogueElement.classList.add('fade-up');

      // Update text
      dialogueElement.textContent = dialogues[randomIndex];

      // Remove animation class after it runs
      setTimeout(() => {
        image.classList.remove('image-clicked');
      }, 400);
    });
  </script>

</body>
</html>
