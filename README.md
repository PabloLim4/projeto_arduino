# projeto_arduino

	#define botaoGreen 12
	#define botaoRed 13
	#define greenLed 2
	#define redLed 3

	int valorA = 2;
	int valorB = 2;
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
    		valorA++;
    
      		if (valorA>1) {
        		valorA = 0;
      		}
    	}
  
    		botaoAtu = digitalRead(botaoGreen);
    		if (botaoAtu && !botaoAnt) {
      		valorB--;
      
      		if (valorB<0) {
        	valorB = 1;
      		}
    	}
  
    		botaoAnt = botaoAtu;
  
    		switch (valorA, valorB) {
  
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
