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
    <!-- just a personal example of how to comment-->

</body>
</html>

<css>
    #workskin .window {
  text-align: justify;
  margin-left: auto;
  margin-right: auto;
  margin-top: 0;
  margin-bottom: 0;
}

#workskin .topbar {
  background-color: #404040;
  color: #FFFFFF;
  border-color: #404040;
  border-style: solid;
  border-width: 1px;
  margin-top: 0;
  margin-bottom: 0;
  width: 66%;
  padding: 2px;
height: 1.5em;
overflow: hidden;
  text-overflow: clip;
}

#workskin .topbar:before {
  content: 'Email';
  display: inline-block;
  position: relative;
  float: left;
  font-weight: bold;
  padding: 0 3px;
width: 85%;
}

#workskin .topbar:after {
  content: ' _ X';
  display: inline-block;
  position: relative;
  font-weight: bold;
  padding-right: 5px;
  float: right;
  color: #cfcfcf;
  -webkit-transform: scale(1.5, 1.0);
  -moz-transform: scale(1.5, 1.0);
  -ms-transform: scale(1.5, 1.0);
  -o-transform: scale(1.5, 1.0);
  transform: scale(1.5,1.0);
  cursor: pointer;
}

#workskin .textfield {
  border-color: #cfcfcf;
  border-style: solid;
  border-width: 1px;
  border-bottom: none;
  margin-top: 0;
  margin-bottom: 0;
  width: 66%;
  padding: 2px;
  color: #000000;
  background-color: #FFFFFF;
}

#workskin .ebody {
  width: 66%;
  padding-top: 0;
  padding-bottom: 0;
  padding-left: 2px;
  padding-right: 2px;
  text-align: justify;
  color: #000000;
  background-color: #FFFFFF;
  margin-left: auto;
  margin-right: auto;
  overflow: auto;
  display: block;
  height: 250px;
  border-color: #cfcfcf;
  border-style: solid;
  border-width: 1px;
}

#workskin .ebody::-webkit-scrollbar {
  -webkit-appearance: none;
}

#workskin .ebody::-webkit-scrollbar:vertical {
  width: 12px;
}

#workskin .ebody::-webkit-scrollbar:horizontal {
  height: 12px;
}

#workskin .ebody::-webkit-scrollbar-thumb {
  background-color: rgba(0, 0, 0, .5);
  border-radius: 10px;
  border: 2px solid #ffffff;
}

#workskin .ebody::-webkit-scrollbar-track {
  border-radius: 10px;
  background-color: #ffffff;
}

#workskin .buttonbar {
  border-color: #cfcfcf;
  background-color: #f5f5f5;
  color: #000000;
  border-style: solid;
  border-width: 1px;
  border-top: none;
  margin-top: 0;
  margin-bottom: 0;
  width: 66%;
  padding: 2px;
height: 1.5em;
overflow: hidden;
  text-overflow: clip;
}

#workskin .buttonbar:after {
  content: 'Reply | Forward | Delete';
  display: inline-block;
  position: relative;
  float: left;
  padding: 0 3px;
  cursor: pointer;
}
