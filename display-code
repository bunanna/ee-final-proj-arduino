#include "SPI.h"
#include "Adafruit_GFX.h"
#include "Adafruit_ILI9341.h"

#define TFT_DC 9
#define TFT_CS 10

Adafruit_ILI9341 tft = Adafruit_ILI9341(TFT_CS, TFT_DC);

int player1InputPin = 3;
int player2InputPin = 2; 

int player1OutputPin = 7; 
int player2OutputPin = 6;

int player1InputState;
int player2InputState;

int player1Score = 0;
int player2Score = 0;

void setup() {
 tft.begin();
 tft.setRotation(3); //landscape
 tft.fillScreen(ILI9341_BLACK);
 tft.setCursor(0, 0);
 tft.setTextColor(ILI9341_WHITE);
 
 pinMode(player1InputPin, INPUT);
 pinMode(player2InputPin, INPUT);
 
 pinMode(player1OutputPin, OUTPUT); 
 pinMode(player2OutputPin, OUTPUT);
}

void loop() {
 player1InputState = digitalRead(player1InputPin);
 player2InputState = digitalRead(player2InputPin);
 
 if (player1InputState == HIGH) {
   tft.setTextSize(3);
   tft.fillScreen(ILI9341_BLACK);
   tft.setCursor(0, 0);
   digitalWrite(player1OutputPin, HIGH);
   player1Score++;
   delay(2000);
 
 } else { 
   tft.setTextSize(3);
   digitalWrite(player1OutputPin, LOW);

   tft.setCursor(0, 0);
   tft.println("Player 1 Score:");
   tft.println(player1Score);
   tft.println("Player 2 Score:");
   tft.println(player2Score);
 }

 if (player2InputState == HIGH) {
   tft.setTextSize(3);
   tft.fillScreen(ILI9341_BLACK);
   tft.setCursor(0, 0);
   digitalWrite(player2OutputPin, HIGH);
   player2Score++;
   delay(2000);
 } else {
   tft.setTextSize(3);
   digitalWrite(player2OutputPin, LOW);

   tft.setCursor(0, 0);
   tft.println("Player 1 Score:");
   tft.println(player1Score);
   tft.println("Player 2 Score:");
   tft.println(player2Score);
 }
} 
