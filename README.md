int PINA0 = 0;
int lectura = 0;
int Ve = 5; 
float VR = 0;
float R1 = 10000;
float R2 = 0;
float A = 0;
float relacion = 0;

void setup()
{
Serial.begin(9600);
}

void loop()
{
lectura = analogRead(PINA0);
if(lectura) 
{
relacion = lectura * Ve;
VR = (relacion)/1024.0;
relacion = (Ve/VR) -1;
R2= R1 * relacion;
A = Ve / (R1 + R2) * 1000;
Serial.print("R2: ");
Serial.println(R2);

delay(1000);
}
}
