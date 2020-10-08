<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Калькулятор</title>
    <link
      rel="stylesheet"
      href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css"
      integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh"
      crossorigin="anonymous"
    />
    <link
      href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap"
      rel="stylesheet"
    />
    <link rel="stylesheet" href="style.css" type="text/css" />
  </head>
  <body>
  <style>.calc-row {
    height: 100vh;
    font-family: 'Share Tech Mono', monospace;
}
.input-window {
    text-align: left;
    font-size: x-large;
}
.card-body{
    background-color: black;
}</style>
    <div class="container">
      <div class="row calc-row align-items-center">
        <div class="col col-md-4 offset-md-4">
          <div class="form-group">
            <div class="card" id="calc">
              <div class="card-body">
                <input
                  class="form-control input-window"
                  id="inputWindow"
                  value=""
                  placeholder="0"
                />
                <div class="row no-gutters">
                  <div class="col">
                    <button
                      class="btn btn-outline-danger form-control"
                      id="btn_clr"
                    >
                      C
                    </button>
                  </div>
                </div>
                <div class="row no-gutters">
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_1"
                    >
                      1
                    </button>
                  </div>
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_2"
                    >
                      2
                    </button>
                  </div>
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_3"
                    >
                      3
                    </button>
                  </div>
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_sum"
                    >
                      +
                    </button>
                  </div>
                </div>
                <div class="row no-gutters">
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_4"
                    >
                      4
                    </button>
                  </div>
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_5"
                    >
                      5
                    </button>
                  </div>
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_6"
                    >
                      6
                    </button>
                  </div>
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_def"
                    >
                      -
                    </button>
                  </div>
                </div>
                <div class="row no-gutters">
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_7"
                    >
                      7
                    </button>
                  </div>
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_8"
                    >
                      8
                    </button>
                  </div>
                  <div class="col">
                    <button
                      class="btn btn-outline-primary form-control"
                      id="btn_9"
                    >
                      9
                    </button>
                  </div>
                    <div class="col">
                      <button
                        class="btn btn-outline-primary form-control"
                        id="btn_mult"
                      >
                        *
                      </button>
                 </div>
                </div>
                <div class="row no-gutters">
                    <div class="col">
                      <button
                        class="btn btn-outline-primary form-control"
                        id="btn_0"
                      >
                        0
                      </button>
                    </div>
                    <div class="col">
                        <button
                          class="btn btn-outline-primary form-control"
                          id="btn_sqrt"
                        >
                        √
                        </button>
                      </div>
                      <div class="col">
                        <button
                          class="btn btn-outline-primary form-control"
                          id="btn_div"
                        >
                        /
                        </button>
                      </div>
                      <div class="col">
                        <button
                          class="btn btn-outline-primary form-control"
                          id="btn_pow"
                        >
                        x<sup>y</sup>
                        </button>
                      </div>
                </div>
                <div class="row no-gutters">
                 <div class="col">
                    <button
                      class="btn btn-outline-success form-control"
                      id="btn_calc"
                    >
                      =
                    </button>
                  </div>
                  </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <script src="script.js"></script>
   <script>let lastOperand = 0;
let operation = null;
const inputWindow = document.getElementById("inputWindow");
document.getElementById("btn_clr").addEventListener("click", function () {
    lastOperand = 0;
    operation = null;
    inputWindow.value = "";
  });
document.getElementById("btn_0").addEventListener("click", function () {
  inputWindow.value +=0 ;
});
document.getElementById("btn_1").addEventListener("click", function () {
  inputWindow.value += 1;
});
document.getElementById("btn_2").addEventListener("click", function () {
  inputWindow.value += 2;
});
document.getElementById("btn_3").addEventListener("click", function () {
  inputWindow.value += 3;
});
document.getElementById("btn_4").addEventListener("click", function () {
  inputWindow.value += 4;
});
document.getElementById("btn_5").addEventListener("click", function () {
  inputWindow.value += 5;
});
document.getElementById("btn_6").addEventListener("click", function () {
  inputWindow.value += 6;
});
document.getElementById("btn_7").addEventListener("click", function () {
  inputWindow.value += 7;
});
document.getElementById("btn_8").addEventListener("click", function () {
  inputWindow.value += 8;
});
document.getElementById("btn_9").addEventListener("click", function () {
  inputWindow.value += 9;
});
document.getElementById("btn_sum").addEventListener("click", function () {
  lastOperand = parseInt(inputWindow.value);
  operation = "sum";
  inputWindow.value = "";
});
document.getElementById("btn_def").addEventListener("click", function () {
  lastOperand = parseInt(inputWindow.value);
  operation = "def";
  inputWindow.value = "-";
});
document.getElementById("btn_mult").addEventListener("click", function () {
    lastOperand = parseInt(inputWindow.value);
    operation = "mult";
    inputWindow.value = "";
  });
  document.getElementById("btn_sqrt").addEventListener("click", function () {
    lastOperand = parseInt(inputWindow.value);
    operation = "sqrt";
    inputWindow.value = "";
  });
  document.getElementById("btn_div").addEventListener("click", function () {
    lastOperand = parseInt(inputWindow.value);
    operation = "div";
    inputWindow.value = "";
  });
  document.getElementById("btn_pow").addEventListener("click", function () {
    lastOperand = parseInt(inputWindow.value);
    operation = "pow";
    inputWindow.value = "";
  });
document.getElementById("btn_calc").addEventListener("click", function () {
  if (operation === "sum") {
    const result = lastOperand + parseInt(inputWindow.value);
    operation = null;
    lastOperand = 0;
    inputWindow.value = result;
  }
  if (operation === "def") {
    const result = lastOperand - parseInt(inputWindow.value);
    operation = null;
    lastOperand = 0;
    inputWindow.value = result;
  }
  if (operation === "mult") {
    const result = lastOperand * parseInt(inputWindow.value);
    operation = null;
    lastOperand = 0;
    inputWindow.value = result;
  }
  if (operation === "sqrt") {
    const result = Math.sqrt(parseInt(inputWindow.value));
    operation = null;
    lastOperand = 0;
    inputWindow.value = result;
  }
  if (operation === "div") {
    const result = lastOperand / parseInt(inputWindow.value);;
    operation = null;
    lastOperand = 0;
    inputWindow.value = result;
}
if (operation === "pow") {
    const result = Math.pow(lastOperand, parseInt(inputWindow.value));
    operation = null;
    lastOperand = 0;
    inputWindow.value = result;
}
});</script>
  </body>
</html>
