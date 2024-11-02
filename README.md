<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>প্রোফাইল পেজ</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            text-align: center;
            padding: 20px;
        }
        .profile-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            display: inline-block;
        }
        img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            display: none; /* Initially hidden */
        }
    </style>
</head>
<body>
    <div class="profile-container">
        <h1>প্রোফাইল</h1>
        <form>
            <label for="profile-pic">প্রোফাইল ছবি আপলোড করুন:</label>
            <input type="file" id="profile-pic" accept="image/*" onchange="previewImage()">
            <img id="profile-image" src="#" alt="প্রোফাইল ছবি" />
            <h2>নাম: <span id="username">আপনার নাম</span></h2>
            <button type="submit">আপলোড করুন</button>
        </form>
    </div>

    <script>
        function previewImage() {
            const file = document.getElementById('profile-pic').files[0];
            const reader = new FileReader();

            reader.onload = function(e) {
                const img = document.getElementById('profile-image');
                img.src = e.target.result;
                img.style.display = 'block'; // Show the image
            }

            if (file) {
                reader.readAsDataURL(file);
            }
        }
    </script>
</body>
</html>


