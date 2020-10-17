<html>
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
    <header>
      <h1>SampleQRCodeJS</h1>
    </header>
    <main>
      <article>
        <section>
          <h2></h2>
          <p></p>
        </section>
      </article>
    </main>
    <footer>
      <b/>
      <p class="copyright">
        Copyright&copy; 2015-2019 <a href="mailto:ArdeshirV@protonmail.com" alt="email">ArdeshirV(at)protonmail.com</a>, Licensed under GPL<sup>v3+</sup>
      <p/>
    </footer>
  
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
</html>
