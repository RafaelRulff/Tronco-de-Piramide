Piramide e Prisma

from OpenGL.GLUT import *

from OpenGL.GLU import *

from OpenGL.GL import *

import math

def pentagono():
     
     raio = 1
     
     N = 5
     
     angulo = (2*math.pi)/N
     
     glColor3f(1.0,1.0,1.0)
     
     glBegin(GL_POLYGON)
     
     for(i in rage(0,N):
     
         x = raio * math.cos{1*angulo)
         
         y = raio * math.sin{1*angulo)
         
         glVertex3f(x,y,0,0)
         
         printf(x,y)
         
     glEnd()
     
glBegin(GL_TRIANGLE)

for i in rage (0,N):

    glVertex3f(0,0,0,H)
    
    glVertex3f(pontosBase[i][0],pontosBase[i][1], 0 ,0)
    
    glVertex3f(pontosBase[i+1][0],pontosBase[i+1][i],0,0)
    
    glEnd
    
    x = raio * math * cos(i * angulo)

def desenha():

      glClear(GL_COLOR_BUFFER_BIT || GL_DEPTH_BUFFER_BIT)
      
      pentagono()
      
      glSwapBuffers()
    

def f(x,y):

    return x**2-y**2
    

M, N = 100, 100

x0, y0 = -2, -2

xf, yf = 2, 2

dx, dy = (xf - x0)/M, (yf - y0)/N

a = 0


def mesh():

   glPushMatrix()
   
    glTranslate(0.0,0.0,az)
    
    glRotatef(ax,1.0,0.0,0.0)
    
    glRotatef(ay,0.0,1.0,0.0)

    
    for i in range(0, N):
    
        y = y0 + i*dy      
        
        glColor3f(1-(i/N), 0, i/N)
        
        glBegin(GL_QUAD_STRIP)
        
        for j in range(0,M):
        
            x = x0 + j*dx
            
            glVertex3f(x, y, f(x,y))
            
            glVertex3f(x, y+dy, f(x, y+dy))
            
        glEnd()
    
    glPopMatrix()

    
    for i in range(0, N):
    
        y = y0 + i*dy
        
        for j in range(0,M):
        
            x = x0 + j*dx
            
            z = f(x,y)
            
            glVertex3f(x,y,z)
    
    glEnd()
    
    glPopMatrix()


def desenha():

    global a
    
    glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT)
    
    glPushMatrix()
    
    glRotatef(a,1.0,0.0,0.0)
    
    glBegin(GL_POINTS)
    
    glPopMatrix()
    
    glPushMatrix()
    
    glTranslatef(0,2,0)
    
    desenhandoDoisCubos()
    
    glPopMatrix()
    
    glutSwapBuffers()

glutInit(sys.argv)

glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGBA | GLUT_DEPTH | GLUT_MULTISAMPLE)

glutInitWindowSize(1024,1024)

glutCreateWindow("Tronco de Piramide")

glutDisplayFunc(desenha)

glEnable(GL_MULTISAMPLE)

glEnable(GL_DEPTH_TEST)

glClearColor(0,0,0,1)

gluPerspective(45,800.0/600.0,0.1,100.0)

glTranslatef(0.0,0.0,-10)

glutTimerFunc(10,timer,1)

glutMainLoop()

def f(x,y):

    return sqrt(abs(-x**2 - y**2 - 1.5**2))

M, N = 100, 100

x0, y0 = -2, -2

xf, yf = 2, 2

dx, dy = (xf - x0)/M, (yf - y0)/N

ax, ay, az = 0, 0, 0


def mesh():

    glPushMatrix()
    
    glTranslate(0.0,0.0,az)
    
    glRotatef(ax,1.0,0.0,0.0)
    
    glRotatef(ay,0.0,1.0,0.0)

       for i in range(0, N):
       
        y = y0 + i*dy      
        
        glColor3f(1-(i/N), 0, i/N)
        
        glBegin(GL_QUAD_STRIP)
        
        for j in range(0,M):
        
            x = x0 + j*dx
            
            glVertex3f(x, y, f(x,y))
            
            glVertex3f(x, y+dy, f(x, y+dy))
            
        glEnd()
    
    glPopMatrix()


def desenha():

    glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT)
    
    mesh()
    
    glutSwapBuffers()


 
#
def keyPressed(tecla, x, y):

    global az
    
    if tecla == b'\033':
    
        glutLeaveMainLoop()
        
        elif tecla == b'+':
        
        az += 1
        
    elif tecla == b'-':
    
        az -= 1
        
    glutPostRedisplay()
    
 
def teclaEspecialPressionada(tecla, x, y):

    global ax, ay
    
    if tecla == GLUT_KEY_LEFT:
    
        ax -= 1                 
        
    elif tecla == GLUT_KEY_RIGHT:
    
        ax += 1            
    
    elif tecla == GLUT_KEY_UP:
    
        ay += 1
        
    elif tecla == GLUT_KEY_DOWN:
    
        ay -= 1
        
    glutPostRedisplay()
    
# PROGRAMA PRINCIPAL

glutInit(sys.argv)

glutInitDisplayMode((GLUT_DOUBLE | GLUT_RGBA | GLUT_DEPTH | GLUT_MULTISAMPLE)

glutInitWindowSize(1024,1024)

glutCreateWindow("Poligono de pontos")

glutDisplayFunc(desenha)

glutKeyboardFunc(keyPressed)

glutSpecialFunc(teclaEspecialPressionada)

glEnable(GL_MULTISAMPLE)

glEnable(GL_DEPTH_TEST)

glClearColor(0,0,0,1)

gluPerspective(45,800.0/600.0,0.1,100.0)

glTranslatef(0.0,0.0,-20)

glutMainLoop()
