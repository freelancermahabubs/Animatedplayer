# Animated Video Player Component

![Animated player](./image/Screenshot_4.png)

This repository contains a React component that creates an animated video player card. When the user clicks the play button, the animation is triggered, and the video starts playing.

## Usage

To use the animated video player component in your React application, follow these steps:

1. Install the required dependencies by running:

   ```bash
   npm install


## Component Details
- The VideoCard component consists of the following parts:

- The play button with an animated border and background.
- The button is initially clickable, and the animation starts when it's clicked.
- You can add your video player component inside the card container.

## CSS Animation Details
### The animation for the play button involves:

- A pulsating border that grows and fades out.
- Changing background colors on hover to provide a visual feedback to users.
- The CSS animations are defined in the style.css file.

```jsx import React, { useState } from 'react';
import "./style.css"; // Import your CSS file

function VideoCard() {
  const [isVideoPlaying, setIsVideoPlaying] = useState(false);

  const handleVideoClick = () => {
    setIsVideoPlaying(true);
    // Add your logic for playing the video here
  };

  return (
    <div className="card">
      <button
        id="play-video"
        className="video-play-button"
        onClick={handleVideoClick}
        disabled={isVideoPlaying} // Disable the button while the video is playing
      >
        <span></span>
      </button>
      {/* You can add your video player component here */}
    </div>
  );
}

export default VideoCard;
```

```css


.card .video-play-button {
    position: absolute;
    z-index: 10;
    inset: 0;
    margin: auto;
    box-sizing: content-box;
    display: block;
    cursor: pointer;
    width: 32px;
    height: 44px;
    border: none;
    border-radius: 50%;
    padding: 18px 20px 18px 28px;
  }
  .card .video-play-button:before {
    content: "";
    position: absolute;
    z-index: 0;
    inset: 0;
    margin: auto;
    display: block;
    width: 80px;
    height: 80px;
    background: linear-gradient(45deg, rgba(253, 78, 11, 0.9) 15%, rgba(255, 0, 0, 0.95) 70%);
    border-radius: 50%;
    animation: pulse-border 1500ms ease-out infinite;
  }
  .card .video-play-button:after {
    content: "";
    position: absolute;
    z-index: 1;
    inset: 0;
    margin: auto;
    display: block;
    width: 80px;
    height: 80px;
    background: linear-gradient(45deg, rgb(253, 78, 11) 15%, rgb(255, 0, 0) 70%);
    border-radius: 50%;
    transition: all 200ms;
    box-shadow: 0 2px 7px #131b49;
  }
  .card .video-play-button:hover:after {
    background-color: #da0528;
  }
  .card .video-play-button span {
    display: block;
    position: relative;
    z-index: 3;
    width: 0;
    height: 0;
    border-left: 30px solid #fff;
    border-top: 18px solid transparent;
    border-bottom: 18px solid transparent;
    border-radius: 4px;
  }
  @keyframes pulse-border {
    0% {
      transform: scale(1);
      opacity: 1;
    }
    100% {
      transform: scale(1.75);
      opacity: 0;
    }
  }
  
  @keyframes fadeInUp {
    from {
      transform: translate3d(0, 30px, 0);
    }
    to {
      transform: translate3d(0, 0, 0);
      opacity: 1;
    }
  }
  
```
