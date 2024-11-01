- <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Screen Mirroring Demo</title>
</head>
<body>
    <button id="start">Start Screen Sharing</button>
    <video id="screenVideo" autoplay></video>
    
    <script>
        document.getElementById('start').addEventListener('click', async () => {
            try {
                const stream = await navigator.mediaDevices.getDisplayMedia({ video: true });
                document.getElementById('screenVideo').srcObject = stream;
            } catch (error) {
                console.error("Error accessing screen share", error);
            }
        });
    </script>
</body>
</html>

