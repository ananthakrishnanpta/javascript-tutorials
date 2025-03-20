```javascript
 const ball = document.getElementById('ball');
        let x = 0, y = 0;

        document.addEventListener('keydown', (event) => {
            if (event.key === 'ArrowUp') y -= 10;
            if (event.key === 'ArrowDown') y += 10;
            if (event.key === 'ArrowLeft') x -= 10;
            if (event.key === 'ArrowRight') x += 10;

            // Set new position
            ball.style.transform = `translate(${x}px, ${y}px)`;
        });


```
