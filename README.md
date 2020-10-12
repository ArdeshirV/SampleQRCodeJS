<head>
  <title>SampleQRCodeJS</title>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no" />
  <!--<link rel="stylesheet" href="https://raw.githubusercontent.com/ArdeshirV/ardeshirv.github.io/master/css/av-darklee.css">-->
  <link rel="stylesheet" href="./css/av-darklee.css">
  <link rel="stylesheet" href="./css/style.css">
  <link rel="icon" href="img/tech-supp.png">
  <script src="https://cdn.freecodecamp.org/testable-projects-fcc/v1/bundle.js"></script>
  <script type="text/javascript" src="./js/qrcodejs/jquery.min.js"></script>
  <script type="text/javascript" src="./js/qrcodejs/qrcode.js"></script>
</head>

<body>
  <div class="div-main-flex" id="main-div">
    <nav id="navbar">
      <header>
        <h1>SampleQRCodeJS</h1>
      </header>
      <div class="links">
        <a class="nav-link" href="https://github.com/ArdeshirV/SampleQRCodeJS">Code on Github</a>
      </div>
      <br />
      <h5 class="h5-description">Description</h5>
      <p class="p-description">
        Demonstrates using qrcodejs library on a dynamic web page
      </p>
    </nav>

    <main id="main-doc">
      <section id="Simple_Examples" class="main-section">
        <header name="header">
          <h2>Simple examples</h2>
        </header>
        <p>
          <input id="text_v" type="text" value="https://github.com/ArdeshirV" style="width:80%" />
          <br/><br/>
          <svg style="border-color: white; width: 10em; height: 10em; border-style: solid; border-width: 0.5em;"
            xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
            <g id="qrcode"/>
          </svg>
        </p>
        <hr>
      </section>

      <footer>
        <p class="footer-p" target="_blank">All the documentation in this page is taken from <a
            href="https://github.com/davidshimjs/qrcodejs">davidshimjs</a></p>
        <p class="footer-p">
          Copyright&copy; 2020 <a href="mailto:ArdeshirV@protonmail.com" alt="email">ArdeshirV@protonmail.com</a>,
          Licensed under GPL<sup>v3+</sup>
        </p>
      </footer>
    </main>
  </div>
  <script type="text/javascript">
var qrcode = new QRCode(document.getElementById("qrcode"), {
    width : 100,
    height : 100,
    useSVG: true
});

function makeCode () {
  var elText = document.getElementById("text_v");
  if (!elText.value) {
    alert("Input a text");
    elText.focus();
    return;
  }
  qrcode.makeCode(elText.value);
}

makeCode();

$("#text_v").
  on("blur", function () {
      makeCode();
  }).
  on("keydown", function (e) {
      if (e.keyCode == 13) {
          makeCode();
      }
  });
  </script>
</body>
