```javascript
const ball = document.getElementById('ball');
    const box = document.querySelector('.box');

    let ballPosition = {
      x: box.clientWidth / 2 - ball.offsetWidth / 2,
      y: box.clientHeight / 2 - ball.offsetHeight / 2
    };

    const ballSpeed = 10;

    document.addEventListener('keydown', (event) => {
      const boxRect = box.getBoundingClientRect();
      const ballRect = ball.getBoundingClientRect();

      switch (event.key) {
        case 'ArrowUp':
          if (ballRect.top > boxRect.top) {
            ballPosition.y -= ballSpeed;
          }
          break;
        case 'ArrowDown':
          if (ballRect.bottom < boxRect.bottom) {
            ballPosition.y += ballSpeed;
          }
          break;
        case 'ArrowLeft':
          if (ballRect.left > boxRect.left) {
            ballPosition.x -= ballSpeed;
          }
          break;
        case 'ArrowRight':
          if (ballRect.right < boxRect.right) {
            ballPosition.x += ballSpeed;
          }
          break;
      }

      ball.style.transform = `translate(${ballPosition.x}px, ${ballPosition.y}px)`;
    });


```
