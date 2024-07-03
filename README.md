
# Main Screen

This is the code for the main screen of your web application.

## HTML (index.html)

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Main Screen</title>
    <style>
        body {
            margin: 0;
            height: 100vh;
            background-image: url('https://lh5.googleusercontent.com/p/AF1QipO8PJUggV7QXNFUlRnKiTDKRtw9jSZf7JcyvTGt=w750-h348-p-k-no');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        .floating-window {
            width: 500px;
            height: 400px;
            overflow: hidden;
            background: rgba(255, 255, 255, 0.8);
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            transform: translateY(50px); /* Adjust the value to move the window downwards */
            position: relative;
        }

        .scroll-container {
            display: flex;
            flex-direction: column;
            animation: scroll 100s linear infinite;
        }

        .scroll-container img {
            width: 100%;
            height: auto;
            border-radius: 10px;
            cursor: pointer;
        }

        @keyframes scroll {
            0% { transform: translateY(0); }
            100% { transform: translateY(calc(-99%)); }
        }

        .button-container {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            transform: translateY(-10%);
        }

        .button-container a {
            text-decoration: none;
        }

        .button-container button {
            width: 120px; /* Fixed width for buttons */
            height: 50px; /* Fixed height for buttons */
            padding: 15px 25px;
            border: none;
            border-radius: 15px; /* Rounded corners */
            background-color: #007BFF;
            color: white;
            cursor: pointer;
            font-size: 19px; /* Adjust font size to fit the buttons */
            margin: 0 290px; /* Margin to provide some space from the floating window */
            animation: blink 1s infinite;
        }

        .button-container button:hover {
            animation: none; /* Stop blinking */
            background-color: black; /* Change background color to black on hover */
        }

        @keyframes blink {
            0% { background-color: #007BFF; }
            50% { background-color: #FF6347; }
            100% { background-color: #007BFF; }
        }

        .enlarged-image-container {
            display: none;
            flex-direction: column;
            align-items: center;
            margin-top: 20px;
            text-align: center;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: rgba(255, 255, 255, 1); /* Fully opaque background */
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
            z-index: 100; /* Ensure it's above other elements */
        }

        .enlarged-image-container img {
            max-width: 80vw; /* Ensure it's responsive and not larger than viewport width */
            max-height: 80vh; /* Ensure it's responsive and not larger than viewport height */
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        }

        .image-details {
            margin-top: 10px;
            background: rgba(255, 255, 255, 0.8);
            padding: 10px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
        }
    </style>
</head>
<body>
    <div class="button-container">
        <a href="{{ url_for('register') }}">
            <button>Register</button>
        </a>
        <a href="{{ url_for('login') }}">
            <button>Login</button>
        </a>
    </div>
    <div class="floating-window">
        <div class="scroll-container">
            <!-- Placeholder images with updated details in data-details attribute -->
            <img src="https://www.yuvamind.com/colleges/images/college/ideal-institute-of-technology-kakinada-campus.png" alt="Image 1" data-details="Ideal Institute of Technology, Kakinada Campus">
            <img src="https://www.idealtech.edu.in/website/assets/images/home/2.jpg" alt="Image 2" data-details="Ideal Institute of Technology Accredited by NACC A+">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Administrative%20Officer.jpg" alt="Image 3" data-details="Administrative Officer, Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Director.jpg" alt="Image 4" data-details="Director of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Principal.jpg" alt="Image 5" data-details="Principal of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Vice%20Principal.jpg" alt="Image 6" data-details="Vice Principal of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/hod/csehod.jpg" alt="Image 7" data-details="Head of Department, Computer Science Engineering, Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/ideal_logo.jpg" alt="Image 8" data-details="Ideal Institute of Technology Logo">
            <!-- Duplicate images for continuous scrolling effect -->
            <img src="https://www.yuvamind.com/colleges/images/college/ideal-institute-of-technology-kakinada-campus.png" alt="Image 1" data-details="Ideal Institute of Technology, Kakinada Campus">
            <img src="https://www.idealtech.edu.in/website/assets/images/home/2.jpg" alt="Image 2" data-details="Ideal Institute of Technology Accredited by NACC A+">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Administrative%20Officer.jpg" alt="Image 3" data-details="Administrative Officer, Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Director.jpg" alt="Image 4" data-details="Director of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Principal.jpg" alt="Image 5" data-details="Principal of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Vice%20Principal.jpg" alt="Image 6" data-details="Vice Principal of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/hod/csehod.jpg" alt="Image 7" data-details="Head of Department, Computer Science Engineering, Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/ideal_logo.jpg" alt="Image 8" data-details="Ideal Institute of Technology Logo">
            <!-- Duplicate images for continuous scrolling effect -->
            <img src="https://www.yuvamind.com/colleges/images/college/ideal-institute-of-technology-kakinada-campus.png" alt="Image 1" data-details="Ideal Institute of Technology, Kakinada Campus">
            <img src="https://www.idealtech.edu.in/website/assets/images/home/2.jpg" alt="Image 2" data-details="Ideal Institute of Technology Accredited by NACC A+">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Administrative%20Officer.jpg" alt="Image 3" data-details="Administrative Officer, Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Director.jpg" alt="Image 4" data-details="Director of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Principal.jpg" alt="Image 5" data-details="Principal of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/Faculty/Vice%20Principal.jpg" alt="Image 6" data-details="Vice Principal of Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/hod/csehod.jpg" alt="Image 7" data-details="Head of Department, Computer Science Engineering, Ideal Institute of Technology">
            <img src="https://www.idealtech.edu.in/website/assets/images/ideal_logo.jpg" alt="Image 8" data-details="Ideal Institute of Technology Logo">
        </div>
    </div>

    <div class="enlarged-image-container" id="enlargedImageContainer">
        <img src="" alt="Enlarged Image" id="enlargedImage">
        <div class="image-details" id="imageDetails"></div>
    </div>

    <script>
        const container = document.querySelector('.scroll-container');
        const images = document.querySelectorAll('.scroll-container img');
        const enlargedImageContainer = document.getElementById('enlargedImageContainer');
        const enlargedImage = document.getElementById('enlargedImage');
        const imageDetails = document.getElementById('imageDetails');

        images.forEach(image => {
            let isHovering = false;

            image.addEventListener('mouseenter', () => {
                isHovering = true;
                // Stop the scrolling animation
                container.style.animationPlayState = 'paused';
                // Display the enlarged image and details
                enlargedImage.src = image.src;
                imageDetails.innerText = image.getAttribute('data-details');
                enlargedImageContainer.style.display = 'flex';
            });

            image.addEventListener('mouseleave', () => {
                isHovering = false;
                // Resume the scrolling animation after a short delay
                setTimeout(() => {
                    if (!isHovering) {
                        container.style.animationPlayState = 'running';
                        enlargedImageContainer.style.display = 'none';
                    }
                }, 200);
            });
        });

        enlargedImageContainer.addEventListener('mouseenter', () => {
            // Stop the scrolling animation when mouse is over the enlarged image
            container.style.animationPlayState = 'paused';
        });

        enlargedImageContainer.addEventListener('mouseleave', () => {
            // Resume the scrolling animation when mouse leaves the enlarged image
            container.style.animationPlayState = 'running';
        });
    </script>
</body>
</html>

Explanation
HTML Structure:

The <head> section includes meta tags and styles.
The <body> contains two main parts:
The button container with links to the register and login pages.
The floating window that contains the scrollable images.
The enlarged image container for displaying images on hover.
CSS:

Styles for the body, floating window, scroll container, buttons, and enlarged image container.
Keyframe animations for scrolling images and button blinking.
JavaScript:

Event listeners for image hover to pause scrolling and display the enlarged image.
Event listeners for the enlarged image container to pause/resume scrolling on hover.
