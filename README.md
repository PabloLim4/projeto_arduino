# projeto_arduino

#define botaoGreen 12
#define botaoRed 13
#define greenLed 2
#define redLed 3

int numero = 2;
int number = 2;
bool botaoAnt = false;
bool botaoAtu = false;

void setup()
{
	pinMode(botaoGreen, INPUT);
    pinMode(botaoRed, INPUT);
	pinMode(greenLed, OUTPUT);
	pinMode(redLed, OUTPUT);
}

void loop()
{
  
  botaoAtu = digitalRead(botaoRed);
  if (botaoAtu && !botaoAnt) {
    number++;
    
      if (number>1){
       number = 0;
      }
    }
  
   botaoAtu = digitalRead(botaoGreen);
   if (botaoAtu && !botaoAnt) {
      numero--;
      
      if (numero<0) {
        numero = 1;
      }
    }
  
  botaoAnt = botaoAtu;
  
  switch (number, numero){
    case 0:
    digitalWrite(2, HIGH);
    digitalWrite(3, LOW);
    break;
    
    case 1:
    digitalWrite(3, HIGH);
    digitalWrite(2, LOW);
    break;
  }
}
