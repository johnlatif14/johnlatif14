<script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.1/p5.min.js"></script>
<canvas width="500" height="500"></canvas>
function setup() {
  createCanvas(500, 500);
  // Create the snake.
  snake = new Snake();
}
function draw() {
  // Clear the canvas.
  background(255);
  // Draw the snake.
  snake.draw();
}
class Snake {
  constructor() {
    // Create the snake's body.
    this.body = [];
    // Create the snake's head.
    this.head = new Point(width / 2, height / 2);
    // Add the head to the snake's body.
    this.body.push(this.head);
  }

  // This function moves the snake.
  move() {
    // Get the direction of the snake's movement.
    var direction = this.direction;
    // Move the snake's head in the direction of its movement.
    this.head.x += direction.x;
    this.head.y += direction.y;
    // Check if the snake has hit a wall.
    if (this.head.x < 0 || this.head.x > width || this.head.y < 0 || this.head.y
