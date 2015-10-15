# PartyTimevar swimmersMaster;
var swimmersCut;
var canvas;
var partyState = 0;
var hat1;
var hat2;
var hat3;
var hat4;
var hat5;
var hats = [];
var pixCheck = [];
var origPos = [];
var hatPositions = [242, 50, 449, 0, 607, 59, 554, 216, 311, 100]
var a = 0;

var colorz = ["red", "orange", "yellow", "green", "blue", "purple"];
var initText;
var doneText;

var textCheck;

var onHat;

var blarg = 0;

function setup() {
  canvas = createCanvas(617, 600);
  swimmersMaster = createImg('Swimmers2.png');
  swimmersCut = createImg('SwimmersClr.png');
    canvas.position(150,0);
    swimmersCut.position(150, 0);
 

  for (var i=0; i<5; i++) {
    hats[i] = createImg('hat.png');
    hats[i].position(46, (i * 125 + 50));
    hats[i].mousePressed(hatBlast);
  }

/*
  hat1 = createImg('hat.png');
  hat1.position(44, 50);
  hat2 = createImg('hat.png');
  hat2.position(44, 175);
  hat3 = createImg('hat.png');
  hat3.position(44, 300);
  hat4 = createImg('hat.png');
  hat4.position(44, 425);
  hat5 = createImg('hat.png');
  hat5.position(44, 550); */
  //hat6 = createImg('hat.png');
  //hat6.position(44, 50);
  
    /*hat1.mousePressed(hatBlast);
    hat2.mousePressed(hatBlast);
    hat3.mousePressed(hatBlast);
    hat4.mousePressed(hatBlast);
    hat5.mousePressed(hatBlast);*/
    //hat6.mousePressed(hatBlast);
    //hat7.mousePressed(hatBlast);

initText = createP("GET THIS PARTY STARTED.");
initText.position(200, 450);
initText.style("color:#FFFFFF; font-size:30pt")

doneText = createP("PARTY!!!");
doneText.position(250, 300);
doneText.style("color:#0000FF; font-size:72pt; font-weight:bold");


}

function draw() {
  print(blarg);
  
  swimmersMaster.position(150, 0);

  if (partyState === 0) {
    canvas.hide();
    swimmersCut.hide();
    doneText.hide();
  }

if (blarg >0) {
  initText.hide();
}   
if (blarg > 4) {
  partyState = 1;
}

if (partyState > 0) {
  if (a < 25) {doneText.show();}
  else {doneText.hide();}
  
  swimmersMaster.hide();
  canvas.show();
  background (255);
for (var i = 0; i < 6; i++) {
  noStroke();
  fill(colorz[i]);
  rect(0, i * 100, 617, 100);
}
a += 5;
if (a >= 50) {
  a = 0;
  colorz[6] = colorz[0];
  for (var j = 0; j<6; j++) {
    colorz[j] = colorz[j+1];
  }
  

}
  
swimmersCut.show();
}

}

/*function mousePressed() {
  pixCheck = get(mouseX, mouseY);
  for (i = 0; i<4; i++) {
    console.log(pixCheck[i]);
  }
}*/

function hatBlast() {
  this.position(hatPositions[0], hatPositions[1]);
  hatPositions.splice(0, 2);
  blarg++;
  
}

function yesHat() {
  onHat = true;
}
function noHat() {
  onHat = false;
}

/*function mouseDragged() {
  for (i = 0; i<5; i++) {
  if (onHat === true) {
    hats[i].position(mouseX+30, mouseY+35);
  }
    
  }
  }*/

/*function moveHat() {
 this.position(mouseX, mouseY);
}*/
