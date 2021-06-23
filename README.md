var wall,thickness;
var bullet,speed, weight;

function setup() {
  createCanvas(1600,400);
  createSprite(400, 200, 50, 50);
  background(255,255,255);
  //background('yellow');
  
  speed=random(55, 90);
  weight= random(400, 1500);
  bullet= createSprite(50, 200,  50, 50);
  wall= createSprite(1300, 200, 60, height/2);   
  bullet.velocityX=speed;
  wall.shapeColor='lightblue'; 
  bullet.shapeColor='pink';
  deformation=0;

}
function draw(){
 if(hasCollided(bullet,wall))
 {
   bullet.velocityX=0;
   var damage=0.5 * weight * speed * speed/(thickness * thickness * thickness);

  if(damage>10)
  {
         wall.shapeColor=color(255,0,0);

  }





  if(damage<10)
  {
        wall.shapeColor=color(0,255,0);
  }
 }
   drawSprties()
}
function hasCollided(lbullet, lwall);
{
    bulletRightEdge=lbullet.x +lbullet.width;
    wallLeftEdge=lwall.x;
    if  (bulletRightEdge>=wallLeftEdge)
   {
     return true
   }
   return fale;

}
