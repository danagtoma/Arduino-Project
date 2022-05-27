  static const int RED = 17;
  static const int BLUE = 18;
  static const int GREEN = 16;
  static const int YELLOW = 19;
  static const int WRONG = 15;
  static const int RIGHT = 14;
  
  static const int RBUTTON = 3;
  static const int BBUTTON = 2;
  static const int GBUTTON = 4;
  static const int YBUTTON = 1;
  static const int START_BUTTON = 0;
  
  static const int RED_TONE = 200;
  static const int BLUE_TONE = 400;
  static const int GREEN_TONE = 600;
  static const int YELLOW_TONE = 800;
  static const int GAMEOVER_TONE = 1000;
  static const int BUZZER = 13;

  static const int APIN = 11;
  static const int BPIN = 12;
  static const int CPIN = 7;
  static const int DPIN = 6;
  static const int EPIN = 5;
  static const int FPIN = 9;
  static const int GPIN = 10;
  static const int DPPIN = 8;
   

const int MAX_LEVEL = 100;
int sequence[MAX_LEVEL];
int input_sequence[MAX_LEVEL];
int level = 1;
int speed = 1000;
  
void setup() {
  //led
  pinMode(RED, OUTPUT); 
  pinMode(BLUE, OUTPUT); 
  pinMode(GREEN, OUTPUT); 
  pinMode(YELLOW, OUTPUT); 
  pinMode(WRONG, OUTPUT); 
  pinMode(RIGHT, OUTPUT); 

  //button
  pinMode(RBUTTON, INPUT_PULLUP);
  pinMode(BBUTTON, INPUT_PULLUP);
  pinMode(GBUTTON, INPUT_PULLUP);
  pinMode(YBUTTON, INPUT_PULLUP);
  pinMode(START_BUTTON, INPUT_PULLUP);

  //buzzer
  pinMode(BUZZER, OUTPUT);

  //7display
  pinMode(APIN, OUTPUT);
  pinMode(BPIN, OUTPUT);
  pinMode(CPIN, OUTPUT);
  pinMode(DPIN, OUTPUT);
  pinMode(EPIN, OUTPUT);
  pinMode(FPIN, OUTPUT);
  pinMode(GPIN, OUTPUT);
  pinMode(DPPIN, OUTPUT);
  
}

void loop() {
  if (level == 1)
    generate_sequence();   

  if (digitalRead(START_BUTTON)== LOW || level != 1){  
    delay(200);
    difficulty();
    show_sequence();    
    get_sequence();    
  }
}

void generate_sequence(){
  randomSeed(millis()); 

  for (int i = 0; i < MAX_LEVEL; i++){
    sequence[i] = random(16,20);
  }
}

void show_sequence(){
  digitalWrite(RED, LOW);
  digitalWrite(BLUE, LOW);
  digitalWrite(GREEN, LOW);
  digitalWrite(YELLOW, LOW);

  for (int i = 0; i < level; i++){  
    if(sequence[i] == 17) tone(BUZZER,800);
    if(sequence[i] == 18) tone(BUZZER,600);
    if(sequence[i] == 16) tone(BUZZER,1000);
    if(sequence[i] == 19) tone(BUZZER,400);
    digitalWrite(sequence[i], HIGH);
    delay(speed);
    digitalWrite(sequence[i], LOW);
    noTone(BUZZER);
    delay(300);
  }
}

void get_sequence(){
  int flag = 0; 

  for (int i = 0; i < level; i++){
    flag = 0;
    while(flag == 0){
      if (digitalRead(RBUTTON) == LOW){
        digitalWrite(RED, HIGH);
        tone(BUZZER,800);
        input_sequence[i] = RED;
        flag = 1;
        delay(400);
        noTone(BUZZER);
        digitalWrite(RED, LOW);
        if (input_sequence[i] != sequence[i]){
          wrong_sequence();
          return;
        }
      }

      if (digitalRead(BBUTTON) == LOW){
        digitalWrite(BLUE, HIGH);
        tone(BUZZER,600);
        input_sequence[i] = BLUE;
        flag = 1;
        delay(400);
        noTone(BUZZER);
        digitalWrite(BLUE, LOW);
        if (input_sequence[i] != sequence[i]){
          wrong_sequence();
          return;
        }
      }

      if (digitalRead(GBUTTON) == LOW){
        digitalWrite(GREEN, HIGH);
        tone(BUZZER,1000);
        input_sequence[i] = GREEN;
        flag = 1;
        delay(400);
        noTone(BUZZER);
        digitalWrite(GREEN, LOW);        
        if (input_sequence[i] != sequence[i]){
          wrong_sequence();
          return;
        }
      }

      if (digitalRead(YBUTTON) == LOW){
        digitalWrite(YELLOW, HIGH);
        tone(BUZZER,400);
        input_sequence[i] = YELLOW;
        flag = 1;
        delay(400);
        noTone(BUZZER);
        digitalWrite(YELLOW, LOW);
        if (input_sequence[i] != sequence[i]){
          wrong_sequence();
          return;
        }
      }   
    }
  }
  right_sequence();
}

void wrong_sequence(){
  delay(200);
  digitalWrite(WRONG, HIGH);
  tone(BUZZER, 200);
  delay(1000);
  digitalWrite(WRONG, LOW);
  noTone(BUZZER);
  
  level = 1;
  speed = 1000;

  delay(200);
}

void right_sequence(){
  delay(200);
  digitalWrite(RIGHT, HIGH);
  tone(BUZZER, 1200);
  delay(500);
  digitalWrite(RIGHT, LOW);
  noTone(BUZZER);

  if (level < MAX_LEVEL);
    level++;

  if(level == 11 || level == 21 || level == 31 || level == 41 || level == 51 || level == 61 || level == 71 || level == 81 || level == 91 )
    speed -= 100; 

  delay(200);  
}

void difficulty(){
  for(int i=5;i<13;i++){
    digitalWrite(i,LOW);
  }
  if(level >= 1 and level <= 10){
    digitalWrite(APIN,HIGH);  //zero
    digitalWrite(BPIN,HIGH);
    digitalWrite(FPIN,HIGH);
    digitalWrite(EPIN,HIGH);
    digitalWrite(DPIN,HIGH);
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  }
  if(level >= 11 and level <= 20){
    digitalWrite(BPIN,HIGH);  //one
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPPIN,HIGH);
  }
  if(level >= 21 and level <= 30){
    digitalWrite(APIN,HIGH);  //two
    digitalWrite(BPIN,HIGH);
    digitalWrite(GPIN,HIGH);
    digitalWrite(EPIN,HIGH);
    digitalWrite(DPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  }
  if(level >= 31 and level <= 40){
    digitalWrite(APIN,HIGH); // three
    digitalWrite(BPIN,HIGH);
    digitalWrite(GPIN,HIGH);
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  } 
  if(level >= 41 and level <= 50){
    digitalWrite(FPIN,HIGH); //four
    digitalWrite(BPIN,HIGH);
    digitalWrite(GPIN,HIGH);
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  }
  if(level >= 51 and level <= 60){
    digitalWrite(APIN,HIGH); //five
    digitalWrite(FPIN,HIGH);
    digitalWrite(GPIN,HIGH);
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  }
  if(level >= 61 and level <= 70){
    digitalWrite(APIN,HIGH); //six
    digitalWrite(FPIN,HIGH);
    digitalWrite(GPIN,HIGH);
    digitalWrite(EPIN,HIGH);
    digitalWrite(DPIN,HIGH);
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  }
  if(level >= 71 and level <= 80){
    digitalWrite(APIN,HIGH);  //seven
    digitalWrite(BPIN,HIGH);
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  }
  if(level >= 81 and level <= 00){
    digitalWrite(APIN,HIGH);  //eight
    digitalWrite(BPIN,HIGH);
    digitalWrite(FPIN,HIGH);
    digitalWrite(GPIN,HIGH);
    digitalWrite(EPIN,HIGH);
    digitalWrite(DPIN,HIGH);
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  }
  if(level >= 91 and level <= 100){
    digitalWrite(APIN,HIGH);  //nine
    digitalWrite(BPIN,HIGH);
    digitalWrite(FPIN,HIGH);
    digitalWrite(GPIN,HIGH);
    digitalWrite(DPIN,HIGH);
    digitalWrite(CPIN,HIGH);
    digitalWrite(DPPIN,HIGH); 
  }
  
}
