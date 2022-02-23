    #define botaoGreen 8
    #define botaoRed 12
    #define greenLed 7
    #define redLed 2
    int x = 0;

    void setup ()
     {
    pinMode(botaoGreen, INPUT_PULLUP);
    pinMode(botaoRed, INPUT_PULLUP);
    pinMode(greenLed, OUTPUT);
    pinMode(redLed, OUTPUT);
    }

    void loop()
    {
    if(!digitalRead(botaoRed)) {
    
    x++;
    if(x==1){
    digitalWrite(redLed, HIGH);
    delay(5000);
    digitalWrite(redLed, LOW);
    x=0;
    }
    delay(400);
    }

    if(!digitalRead(botaoGreen)) {
    
    x++;
    if(x==1){
    digitalWrite(greenLed, HIGH);
    delay(5000);
    digitalWrite(greenLed, LOW);
    x=0;
    }
    delay(400);
    }
    }
