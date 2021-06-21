<!--
<html>
<body style="background-color:powderblue;">
    
    <p>
    <h1>Hello!</h1>
    </p>
    <p>
        Did you know there are 6 levels of headline types? <h1>one,</h1> <h2>two,</h2> <h3>three,</h3> <h4>four,</h4> <h5>five,</h5> <h6>and six!</h6>
    </p>
    <p>
    This is the default text. But it can be <b>bold</b> or <i>italic</i>. Did you know there are two types of bold and italic? Though they look the same on your screen, this is <strong>bold text that is intended to convey importance</strong> and this is <em>italic text meant to be emphasized.</em>
    </p>
    In html, you can create ordered and unordered lists.
    <ol>
        <li>an</li>
        <li>ordered</li>
        <li>list</li>
    </ol>
    <ul>
        <li>an</li>
        <li>unordered</li>
        <li>list</li>
    </ul>
    <p>
    I can also add an image to my website! <img src="https://theknow.denverpost.com/wp-content/uploads/2020/04/GettyImages-1089392442.jpg" alt="stack of books">
    </p>
    <p>
    I can also embed a video! 
    </p>
  <iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    <p>
    <a href="https://www.tumblr.com/blog_auth/public-library">Here's a link to my project :)</a> 
    </p>
    <!-- just a personal example of how to comment

</body>
</html>

-->
<div class="imgLoader"></div>

<div class="container">

  <h1 class="title">
    Turning pages<br>with css
  </h1>

  <div class="credit">
    * Images loaded randomly from Picsum.photos
  </div>

  <div class="book">
    <div class="gap"></div>
    <div class="pages">
      <div class="page"></div>
      <div class="page"></div>
      <div class="page"></div>
      <div class="page"></div>
      <div class="page"></div>
      <div class="page"></div>
    </div>
    <div class="flips">
      <div class="flip flip1">
        <div class="flip flip2">
          <div class="flip flip3">
            <div class="flip flip4">
              <div class="flip flip5">
                <div class="flip flip6">
                  <div class="flip flip7"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<a href="https://twitter.com/amit_sheen" class="twitterLink" target="_top">
   <img src="https://assets.codepen.io/1948355/twitterLogo2.png" />
</a>
@import url('https://fonts.googleapis.com/css2?family=Indie+Flower&display=swap');

* {
    padding: 0;
    margin: 0 auto;
    box-sizing: border-box;
}

body {
    font-family: 'Indie Flower', cursive;
    background-color: #eee;
    color: #555;
    text-align: center;
    padding: 4em 0;
}

$bookAngle: 60deg;
$speed: 5s;
$borderColor: #555;

$images:
    url('https://picsum.photos/420/300?random=1'),
    url('https://picsum.photos/420/300?random=2'),
    url('https://picsum.photos/420/300?random=3'),
    url('https://picsum.photos/420/300?random=4'),
    url('https://picsum.photos/420/300?random=5'), 
    url('https://picsum.photos/420/300?random=1');

// Preload to images
.imgLoader {
    position: fixed;
    animation: preLoad 1s steps(1);
    width: 1px;
    height: 1px;

    @keyframes preLoad {
        @for $i from 0 through 4 {
            #{$i * 10}% { background-image: nth($images, ($i + 1)); }
        }
        100% { display: none; }
    }
}

.container {
    position: relative;
    width: 420px;
    border: #fff solid 2px;
    border-radius: 4px;
    height: 420px;
}

.title {
    position: absolute;
    top: 45px; left: 0;
    width: 100%;
    font-size: 2em;
    font-weight: normal;
    line-height: 1;
}

.credit {
    position: absolute;
    top: 100%; left: 0;
    font-size: 0.9em;
    text-align: left;

}

.book {
    position: relative;
    perspective: 630px;
    perspective-origin: center 50px; 
    transform: scale(1.2);
    filter: drop-shadow(0px 10px 5px rgba(0,0,0,0.25));
}

.page {
    width: 210px;
    height: 300px;
    background-color: #bbb;
    position: absolute;
    top: 0px; right: 50%;
    transform-origin: 100% 100%;
    border: solid $borderColor 2px;
    background-size: 420px 300px;
    background-position: center;

    &:nth-child(1) {transform: rotateX($bookAngle) rotateY(3deg); }
    &:nth-child(2) { transform: rotateX($bookAngle) rotateY(4.5deg); }
    &:nth-child(3) {
        transform: rotateX($bookAngle) rotateY(6deg);
        animation: nextPage $speed*5 infinite $speed*-4.8 steps(1);
        background-size: 420px 300px;
        background-position: -2px -2px;
    }

    &:nth-child(4) { transform: rotateX($bookAngle) rotateY(177deg); }
    &:nth-child(5) { transform: rotateX($bookAngle) rotateY(175.5deg); }
    &:nth-child(6) {
        transform: rotateX($bookAngle) rotateY(174deg);
        overflow: hidden;

        &::after {
            content: '';
            width: 210px;
            height: 300px;
            position: absolute;
            top: 0px; right: 0%;
            transform-origin: center;
            transform: rotateY(180deg);
            animation: nextPage $speed*5 $speed*-4 infinite steps(1);
            background-size: 420px 300px;
            background-position: 100% -2px;
        }
    }

    @keyframes nextPage {
        @for $i from 0 through 4 {
            #{$i * 20}% { background-image: nth($images, ($i + 1)); }
        }
    }
}

.gap {
    width: 10px;
    height: 300px;
    background: none;
    transform: rotateX($bookAngle);
    transform-origin: bottom;
    position: absolute;
    top: 0px; left: calc(50% - 5px);

    &::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 50%;
        transform: translate(-50%, 50%);
        background-color: $borderColor;
        width: 10px;
        height: 5px;
        border-radius: 50%;
    }
}

.flip {
    width: 32px;
    height: 300px;
    position: absolute;
    top: 0px;
    transform-origin: 100% 100%;
    right: 100%;
    border: solid $borderColor;
    border-width: 2px 0px;
    perspective: 4200px;
    perspective-origin: center; 
    transform-style: preserve-3d;
    background-size: 420px 300px;

    &::after {
        content: '';
        position: absolute;
        top: 0px; right: 0%;
        width: 100%; height: 100%;
        transform-origin: center;
        background-size: 420px 300px;
    }

    &.flip1 {
        right: 50%;
        animation: flip1 $speed infinite ease-in-out;
        border-width: 2px 2px 2px 0;

        &::after {
            animation: nextFlip1 $speed*5 $speed*-4 infinite steps(1);
        }
    }

    &:not(.flip1) {
        right: calc(100% - 2px);
        top: -2px;
        transform-origin: right;
        animation: flip2 $speed ease-in-out infinite;
    }

    @for $i from 2 through 7 {
        &.flip#{$i}::after { animation: nextFlip#{$i} $speed*5 $speed*-4 infinite steps(1); }
    }
    
    &.flip7 {
        width: 30px;
        border-width: 2px 0px 2px 2px;
        &::after { animation: nextFlip7 $speed*5 $speed*-4 infinite steps(1); }
    }

    @keyframes flip1 {
        0%, 20% { transform: rotateX($bookAngle) rotateY(6deg); }
        80%, 100% { transform: rotateX($bookAngle) rotateY(174deg); }
    }

    @keyframes flip2 {
        0%, 20% { transform: rotateY(0deg) translateY(0px); }
        50% { transform: rotateY(-15deg) translateY(0px); }
    }
}

@keyframes nextFlip1 {
    @for $i from 0 through 4 {
        #{$i * 20}% { background-image: nth($images, ($i + 1)); background-position: -178px -2px; transform: rotateY(0deg); }
        #{10 + ($i * 20)}% { background-image: nth($images, ($i + 2)); background-position: -210px -2px; transform: rotateY(180deg); }
    }
}

@for $i from 2 through 6 {
    @keyframes nextFlip#{$i} {
        @for $j from 0 through 4 {
            #{$j * 20}% { background-image: nth($images, ($j + 1)); background-position: #{-148 + (($i - 2) * 30)}px -2px; transform: rotateY(0deg); }
            #{((10 + ($j * 20)) + (($i - 1) * 0.5))}% { background-image: nth($images, ($j + 2)); background-position: #{-238 - (($i - 2) * 30)}px -2px; transform: rotateY(180deg); }
        }
    }
}

@keyframes nextFlip7 {
    @for $i from 0 through 4 {
        #{$i * 20}% { background-image: nth($images, ($i + 1)); background-position: -2px -2px; transform: rotateY(0deg); }
        #{13 + ($i * 20)}% { background-image: nth($images, ($i + 2)); background-position: -388px -2px; transform: rotateY(180deg); }
    }
}

.twitterLink {
  position: fixed;
  bottom: 0.5em; right: 0.5em;
  & img {
    width: 2em;
    filter: grayscale(100%);
    transition: filter 0.25s;
    &:hover {
      filter: grayscale(0%);
    }
  }
}
