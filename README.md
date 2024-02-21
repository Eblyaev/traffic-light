# traffic-light

```с++
#define RED 6
#define YEL 7
#define GRE 8

unsigned long t0 = 0;
unsigned long t1 = 0;

inst state = 0;


void setup()
{
  pinMode (RED, OUTPUT);
  pinMode (YEL, OUTPUT);
  pinMode (GRE, OUTPUT);
}

void loop()
{
  t1 = millis();
  switch(state) {
    case 0: 
  	 state = 1;
     break;
    
    case 1: 
  	 digitalWrite (RED, HIGH);
     digitalWrite (GRE, LOW);
     if (t0 - t1 > 30) [
       state = 2;
       t0 = t1;
     break;
    
    case 2: 
  	 digitalWrite (YEL, HIGH);
     digitalWrite (RED, LOW);
       if (t0 - t1 > 3 && state == 2) {
       state = 3;
       t0 = t1;
       }
       else if (t0 - t1 > 3 && state == 3) {
         staet = 1;
         t0 = t1;
       }
        break;
    
    case 3: 
  	 digitalWrite (GRE, HIGH);
     digitalWrite (YEL, LOW);
     if (t0 - t1 > 30) [
       state = 2;
       t0 = t1;
     break;
}
```c++
