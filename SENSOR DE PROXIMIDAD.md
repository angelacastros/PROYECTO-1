# Sensor de proximidad.

**Descripción**

El montaje trabajado en la clase consiste en determinar la distancia cercana al sensor por medio del sensor ultrasónico instalado en el protoboard y programado. Luego de esto instalamos los leds y los conectamos con el sensor, estos se encenderán o apagarán deacuerdo a la distancia calcuclado por el sensor de ultrasonido.

**¿Para qué funciona?**

Con este proyecto buscamos darlle utilidad al sensor ultrasonido instalado en el prtoboard, este determina la proximidad de algún obejeto de acuerdo a lo que esté en frente de la ráfaga y el eco.Por ejemplo estos se usan en los autos cuando se están parqueando, el sonido que produce inidca la proximidad del obejto.

**Materiales**

- Leds
- Sensor ultrasónico HC-SR04
- Placa arduino
- Resistencias
- Protoboard 
- Jumpers 


**Diagrama esquemático**
![Diagrama esquemático ](https://github.com/angelacastros/PROYECTO-1/blob/master/images/Diagrama%20esquematico.png?raw=true)


**Diagrama picórico**
![Foto diagrama pictorico  ](https://github.com/angelacastros/PROYECTO-1/blob/master/images/Diagrama%20Pictorico.png?raw=true)


**Fotos**

![Foto](https://github.com/angelacastros/PROYECTO-1/blob/master/images/20190214_161130.jpg?raw=true)

![Foto](https://github.com/angelacastros/PROYECTO-1/blob/master/images/20190214_161151.jpg?raw=true)


**Código**
![CODIGO ](https://github.com/angelacastros/PROYECTO-1/blob/master/codes/sensor%20de%20proximidad/sensor%20de%20proximidad.ino)


Inline `code` has
 `const int trigPin =3;
  const int echoPin =2;

int duration;
int distance;

void setup() 
{
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  
  for (int i = 4 ; i < 9; i++) 
  {

pinMode(i,OUTPUT);
    
  }
  
}

void loop() 
{
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

duration = pulseIn(echoPin, HIGH);

distance = 0.034 * duration / 2;

if (distance < 5) 
 {
  for(int i = 4; i < 9; i++)
   {
digitalWrite(i,HIGH);

   }  
 }
  
  else if (distance > 5 && distance < 10) 
  {
digitalWrite(8,LOW);
    for(int i = 4; i < 8; i++)
    {
digitalWrite(i,HIGH);   
  
    }
  }
  else if (distance > 10 && distance < 15) 
  {
digitalWrite(8,LOW);
digitalWrite(7,LOW);
    for(int i = 4; i < 7 ; i++)
    {
digitalWrite(i,HIGH);
    }
 }
}






