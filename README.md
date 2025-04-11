<script>
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = Math.random() * 3 + 3 + 's';
      heartsContainer.appendChild(heart);
      
      setTimeout(() => {
        heart.remove();
      }, 6000);
    }

    function playAudio() {
      if (audio.paused) {
        audio.play();
        document.querySelector('.audio button').textContent = 'Пауза';
        setInterval(createHeart, 300);
      } else {
        audio.pause();
        document.querySelector('.audio button').textContent = 'Відтворити пісню';
      }
    }

    // Генерация сердечек при загрузке
    for (let i = 0; i < 15; i++) {
      setTimeout(createHeart, i * 200);
    }
  </script>
</body>
</html>
