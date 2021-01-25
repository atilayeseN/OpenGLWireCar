
#include <GL/glut.h>
#include <cmath>
#define pi 3.14159265359
//Function initialization
void display();
void init();
void reshape(int, int);
void timer(int);
//Frontwheels radius
static int fwheel_radius = 1;
//Backwheels radius
static float bwheel_radius = 0.8;
// Angle for movement stick
float angle = 0;
//Steering wheel stick's initial angles 
float direction_angle1 = 30;
float direction_angle2 = 120;
//Rotation angle for front wheel direction
float circle_angle = 0;
//For up,bottom,left,right,front and back vision specifications;t's for Translate r's for rotate.
float tx = 1.5, ty = -2, tz = -10;
int ra = 90, rx = 0,ry = 1;
void init() {
	glClearColor(0.0, 0.0, 0.0, 0.0);

}
//Degree to radian function
float functheta(int angle) {
	return angle *pi / 180;
}
//Draw points
void skeleton() {
	glBegin(GL_LINES);
	glVertex3f(0.0, 0.0, 0.0);
	glVertex3f(0, 0, -3.0);
	glVertex3f(0, 0, -0.5);
	glVertex3f(8, 0, -0.5);
	glVertex3f(8.0, 0.0, 0.0);
	glVertex3f(8.0, 0.0, -3.0);
	glVertex3f(0, 0, -2.5);
	glVertex3f(8, 0, -2.5);
	glVertex3f(0, 3, -1.5);
	glVertex3f(2, 6, -1.5);
	glVertex3f(0.0, 0, -0.5);
	glVertex3f(0.0, 3, -0.5);
	glVertex3f(0.0, 0.0, -2.5);
	glVertex3f(0.0, 3, -2.5);
	glVertex3f(0.0, 3, -0.5);
	glVertex3f(8.0, 3, -0.5);
	glVertex3f(0.0, 3, -2.5);
	glVertex3f(8.0, 3, -2.5);
	glVertex3f(8.0, 3, -0.5);
	glVertex3f(8.0, 0, -0.5);
	glVertex3f(8.0, 3, -2.5);
	glVertex3f(8.0, 0, -2.5);
	glVertex3f(0, 3, -0.5);
	glVertex3f(0, 3, -2.5);
	glVertex3f(8.0, 3, -0.5);
	glVertex3f(8.0, 3, -2.5);


	glEnd();
}
//Draw frontwheels
void frontwheels(){
	//Processing for specific shape
	glPushMatrix();
	//Move wheel to center
	glTranslatef(0, 0, 0);
	//Rotate wheels to left or right
	glRotatef(circle_angle, 0, 1, 0);
	//Draw first
	glBegin(GL_POINTS);
	for (int i = 1; i <= 360; i++) {
		glVertex3f(cos(functheta(i)) * fwheel_radius, sin(functheta(i)) * fwheel_radius, 0.0);
	}
	glEnd();

	//Draw sticks
	//They moves according to points determined by the angle
	glBegin(GL_LINES);
	glVertex3f(cos(functheta(angle)) * fwheel_radius, sin(functheta(angle)) * fwheel_radius, 0.0);
	glVertex3f(cos(functheta(angle + 180)) * fwheel_radius, sin(functheta(angle + 180)) * fwheel_radius, 0.0);
	glEnd();
	glPopMatrix();

	glPushMatrix();
	//Move to top left corner to wheels with the help of translation
	glTranslatef(0, 0, -3);
	glRotatef(circle_angle, 0, 1, 0);
	
	glBegin(GL_POINTS);
	for (int i = 1; i <= 360; i++) {
		glVertex3f(cos(functheta(i)) * fwheel_radius, sin(functheta(i)) * fwheel_radius, 0.0);
	}
	glEnd();


	glBegin(GL_LINES);
	glVertex3f(cos(functheta(angle)) * fwheel_radius, sin(functheta(angle)) * fwheel_radius, 0.0);
	glVertex3f(cos(functheta(angle + 180)) * fwheel_radius, sin(functheta(angle + 180)) * fwheel_radius, 0.0);
	
	glEnd();
	glPopMatrix();
	
}
void backwheels() {
	glBegin(GL_POINTS);
	for (int i = 1; i <= 360; i++) {

		glVertex3f(cos(functheta(i)) * bwheel_radius + 8.0, sin(functheta(i)) * bwheel_radius, 0.0);
	}

	glEnd();
	glBegin(GL_LINES);
	glVertex3f(cos(functheta(angle)) * bwheel_radius + 8.0, sin(functheta(angle)) * bwheel_radius, 0.0);
	glVertex3f(cos(functheta(angle + 180)) * bwheel_radius + 8.0, sin(functheta(angle + 180)) * bwheel_radius, 0.0);
	glEnd();



	glBegin(GL_POINTS);
	for (int i = 1; i <= 360; i++) {

		glVertex3f(cos(functheta(i)) * bwheel_radius + 8.0, sin(functheta(i)) * bwheel_radius, -3.0);
	}



	glEnd();
	glBegin(GL_LINES);
	glVertex3f(cos(functheta(angle)) * bwheel_radius + 8.0, sin(functheta(angle)) * bwheel_radius , -3.0);
	glVertex3f(cos(functheta(angle + 180)) * bwheel_radius + 8.0, sin(functheta(angle + 180)) * bwheel_radius, -3.0);
	glEnd();
}
void steering_wheel() {
	
	glPushMatrix();
	//Putting to steering whell chamber
	glTranslatef(2.0, 6.0, -1.5);
	//Rotation for steering wheel illusion
	glRotatef(90, 1, 0, 0);
	glRotatef(30, 0, -1, 0);
	glBegin(GL_POINTS);
	for (int i = 1; i <= 360; i++) {
		glVertex3f(cos(functheta(i)) * bwheel_radius, sin(functheta(i)) * bwheel_radius, 0);
	}
	glEnd();
	glBegin(GL_LINES);
	glVertex3f(cos(functheta(direction_angle1)) * bwheel_radius, sin(functheta(direction_angle1)) * bwheel_radius, 0);
	glVertex3f(cos(functheta(direction_angle1 + 180)) * bwheel_radius, sin(functheta(direction_angle1 + 180)) * bwheel_radius, 0);
	glEnd();
	glBegin(GL_LINES);
	glVertex3f(cos(functheta(direction_angle2)) * bwheel_radius, sin(functheta(direction_angle2)) * bwheel_radius, 0);
	glVertex3f(cos(functheta(direction_angle2 + 180)) * bwheel_radius, sin(functheta(direction_angle2 + 180)) * bwheel_radius, 0);
	glEnd();
	glPopMatrix();
}


void display() {
	glClear(GL_COLOR_BUFFER_BIT);

	glLoadIdentity();

	
    //Define color
	glColor3d(1, 1, 1);
	//Translate shape for visibility
	glTranslatef(-4, 0, -15);
	glRotatef(30, 1,0, 0);
	
	//Rendering shapes
	skeleton();
	
	steering_wheel();


	glEnd();
	
	backwheels();
	frontwheels();
	
	//For animations and keybord function;changing to second buffer for animation
	glutSwapBuffers();
}


//For my rotational window
void displaynew() {
	glClear(GL_COLOR_BUFFER_BIT);

	glLoadIdentity();


	//Define color
	glColor3d(1, 1, 1);
	//Translate  for visibility
	glTranslatef(tx, ty, tz);
	glRotatef(ra, rx, ry, 0);
	//Rendering shapes
	skeleton();

	steering_wheel();


	glEnd();

	backwheels();
	frontwheels();

	//For animations and keybord function;changing to second buffer for animation
	glutSwapBuffers();
}
//Define my perspective of window
void reshape(int w, int h) {
	glViewport(0, 0, (GLsizei)w, (GLsizei)h);
	glMatrixMode(GL_PROJECTION);
	gluPerspective(60, 1, 2.0f, 50.0f);
	glMatrixMode(GL_MODELVIEW);

}
//Timer function for move of sticks on the wheels
void timer(int) {
	glutPostRedisplay();
	glutTimerFunc(1000/600, timer, 0);
	angle++;

}
//My keyboard function for rotating wheels and steering wheel
void keyboard(unsigned char key,int x,int y) {
	if (key == 'a') {
		circle_angle+=2;
		direction_angle1--;
		direction_angle2--;
	}
	if (key == 's') {
		circle_angle-=2;
		direction_angle1++;
		direction_angle2++;
	}
	
}
//My second keyboard function for my rotational window;f=front,b=back,y=up,h=down,g=left,j=right.
void rotations(unsigned char key, int x, int y) {
	if (key == 'f') {
		tx = 1.5, ty = -2, tz = -10;
		ra = 90, rx = 0, ry = 1;
	}
	if (key == 'b') {
		tx = -1.5, ty = -2, tz = -15;
		ra = 90, rx = 0, ry = -1;
	}
	switch (key) {
	case 'y':
		
		tx = -4, ty = -1, tz = -12;
		ra = 90, rx = 1, ry = 0;
		break;
	case 'h':
		tx = -4, ty = 2, tz = -12;
		ra = 270, rx = 1, ry = 0;
		break;
	case 'j':
		tx = 4, ty = -2, tz = -12;
		ra = 180, rx = 0, ry = 1;
		break;
	case 'g':
		tx = 4, ty = -2, tz = -12;
		ra = 180, rx = 0, ry = -1;
		break;
	}


}


int main(int argc, char** argv) {
	glutInit(&argc, argv);
	glutInitDisplayMode(GLUT_RGB );

	glutInitWindowPosition(200, 100);
	glutInitWindowSize(500, 500);

	
	//Initializing my main windows
	glutCreateWindow("Window");
	glutReshapeFunc(reshape);
	glutDisplayFunc(display);
	glutKeyboardFunc(keyboard);
	glutTimerFunc(0, timer, 0);
	init();

	glutInitWindowPosition(700, 100);
	glutCreateWindow("Parts");
	glutReshapeFunc(reshape);
	glutDisplayFunc(displaynew);
	glutKeyboardFunc(rotations);
	glutTimerFunc(0, timer, 0);
	init();


	glutMainLoop();
}
