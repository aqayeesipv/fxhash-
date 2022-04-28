# fxhash-
const canvas = Math.min(innerWidth, innerHeight)  function setup() {   rectMode(CENTER)   angleMode(DEGREES)   createCanvas(canvas, canvas)   noLoop() }  function draw() {   const grid = int(random(3,canvas/50))   const margin = canvas/10   const space = random([0,0,canvas/200])   const m = ((canvas-(2*margin))-((grid-1)*space))/grid   const style = floor(random(0,4))   const diagonal = 0      clr = random([[0,255,255],[255,0,0],[50,200,200],                 [[random(150,255),random(150,255),random(150,255)],0,0],                 [[random(0,100),random(0,100),random(0,100)],255,255]])      background(clr[0])   stroke(clr[1])   strokeWeight(random(1,canvas/500))   translate(m/2+margin,m/2+margin)   for (let x=0; x&lt;grid; x++) {     push()     for (let y=0; y&lt;grid; y++) {       push()       pickerStyle(style)       pickerDraw(m, diagonal)       pop()       translate(0,m+space)     }      pop()     translate(m+space,0)   } }  function nBox(m) {   rotate(pickerRotation())   rect(0,0,m,m/2) }  function nCross(m) {   beginShape()   vertex(-m/4, -m/2)  //1   vertex(m/4, -m/2)  //2   vertex(m/4, -m/4)  //3   vertex(m/2, -m/4)  //4   vertex(m/2, m/4)  //5   vertex(m/4, m/4)  //6   vertex(m/4, m/2)  //7   vertex(-m/4, m/2)  //8   vertex(-m/4, m/4)  //9   vertex(-m/2, m/4)  //10   vertex(-m/2, -m/4)  //11   vertex(-m/4, -m/4)  //12   vertex(-m/4, -m/2)  //1   endShape() }  function nTshape(m) {   rotate(pickerRotation())   beginShape()   vertex(-m/4, -m/2)  //1   vertex(m/4, -m/2)  //2   vertex(m/4, -m/4)  //3   vertex(m/2, -m/4)  //4   vertex(m/2, m/4)  //5   vertex(-m/2, m/4)  //10   vertex(-m/2, -m/4)  //11   vertex(-m/4, -m/4)  //12   vertex(-m/4, -m/2)  //1   endShape() }  function nLshape(m) {   rotate(pickerRotation())   beginShape()   vertex(-m/4, -m/2)  //1   vertex(m/4, -m/2)  //2   vertex(m/4, m/4)  //6   vertex(-m/2, m/4)  //10   vertex(-m/2, -m/4)  //11   vertex(-m/4, -m/4)  //12   vertex(-m/4, -m/2)  //1   endShape() }  function dBox(m) {   rotate(pickerRotation())   beginShape()   vertex(-m/4, -m/2) //1   vertex(m/4, -m/2) //2   vertex(m/4, -3*m/8) //3   vertex(m/8, -m/4) //4   vertex(m/8, m/4) //5   vertex(m/4, 3*m/8) //6   vertex(m/4, m/2) //7   vertex(-m/4, m/2) //8   vertex(-m/4, 3*m/8) //9   vertex(-m/8, m/4) //10   vertex(-m/8, -m/4) //11   vertex(-m/4, -3*m/8) //12   vertex(-m/4, -m/2) //1   endShape()  }  function dBox2(m) {   rotate(pickerRotation())   beginShape()   vertex(-m/4, -m/2) //1   vertex(m/4, -m/2) //2   vertex(m/4, -3*m/8) //3   vertex(3*m/8, -m/4) //4   vertex(3*m/8, m/4) //5   vertex(m/4, 3*m/8) //6   vertex(m/4, m/2) //7   vertex(-m/4, m/2) //8   vertex(-m/4, 3*m/8) //9   vertex(-3*m/8, m/4) //10   vertex(-3*m/8, -m/4) //11   vertex(-m/4, -3*m/8) //12   vertex(-m/4, -m/2) //1   endShape()  }  function dCross(m) {   beginShape()   vertex(-m/4, -m/2) //1   vertex(m/4, -m/2) //2   vertex(m/4, -3*m/8) //3   vertex(3*m/8, -m/4) //4   vertex(m/2, -m/4) //5   vertex(m/2, m/4) //6   vertex(3*m/8, m/4) //7   vertex(m/4, 3*m/8) //8   vertex(m/4, m/2) //9   vertex(-m/4, m/2) //10   vertex(-m/4, 3*m/8) //11   vertex(-3*m/8, m/4) //12   vertex(-m/2, m/4) //13   vertex(-m/2, -m/4) //14   vertex(-3*m/8, -m/4) //15   vertex(-m/4, -3*m/8) //16   vertex(-m/4, -m/2) //1   endShape() }  function dLshape(m) {   rotate(pickerRotation())   beginShape()   vertex(-m/4, -m/2) //1   vertex(m/4, -m/2) //2   vertex(m/4, -m/4) //3   vertex(m/8, -m/8) //4   vertex(m/8, 0) //5   vertex(0, m/8) //6   vertex(-m/8, m/8) //7   vertex(-m/4, m/4) //8   vertex(-m/2, m/4) //9   vertex(-m/2, -m/4) //10   vertex(-3*m/8, -m/4) //11   vertex(-m/4, -3*m/8) //12   vertex(-m/4, -m/2) //1   endShape() }  function dTshape(m) {   rotate(pickerRotation())   beginShape()   vertex(-m/4, -m/2) //1   vertex(m/4, -m/2) //2   vertex(m/4, -3*m/8) //3   vertex(3*m/8, -m/4) //4   vertex(m/2, -m/4) //5   vertex(m/2, m/4) //6   vertex(3*m/8, m/4) //7   vertex(m/4, m/8) //8   vertex(-m/4, m/8) //9   vertex(-3*m/8, m/4) //10   vertex(-m/2, m/4) //11   vertex(-m/2, -m/4) //12   vertex(-3*m/8, -m/4) //13   vertex(-m/4, -3*m/8) //14   vertex(-m/4, -m/2) //1   endShape() }  function pickerRotation() {   var angle = random([0,90,180,270])   return angle }  function pickerDraw(m, diagonal) {   if (diagonal == 0) {   rand = floor(random(0,4))   let draw = (rand == 0) ? nBox(m) :              (rand == 1) ? nCross(m) :              (rand == 2) ? nLshape(m) :              nTshape(m)   } else if (diagonal == 1) {   rand = floor(random(0,4))   let draw = (rand == 0) ? dBox(m) :              (rand == 1) ? dCross(m) :              (rand == 2) ? dLshape(m) :              dTshape(m)    } }  function pickerStyle(style) {   rand = floor(random(0,2))   if (style == 0) {    noFill()   } else if (style == 1) {   let style = (rand == 0) ? noFill() :                             fill(clr[2],random(255))     } else if (style == 2) {   let style = (rand == 0) ? noFill() :                             fill(clr[2])    } else {   fill(clr[2])     } }  function mouseClicked() {   setup()   draw() }
