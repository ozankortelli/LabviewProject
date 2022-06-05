# LabviewProject
# Greenhouse

## **The main task of greenhouses is to provide the most suitable environmental conditions for the development of plants. Meeting these demands of plants must be under economic conditions. For this, the yield should be higher, the product quality should be better, and the development and maturation period of the product should be shorter in the greenhouse. In order to create these conditions in the greenhouse, the greenhouse planner must know the wishes of the plants. In greenhouse planning, besides the primary environmental factors such as light, temperature, humidity and ventilation, in addition to these, the amount of carbon dioxide in the air, which determines the growing environment, soil water, drainage, soil plant nutrients, and disease factors can be counted.**
![Provide better yields for your crop with Smart greenhouse monitoring  solution](https://www.softwebsolutions.com/wp-content/uploads/2019/12/Greenhouse-monitoring.jpg)

#   Importance of temperature for greenhouse
## In order for plants to complete their normal development, they must spend a certain period of time at the most suitable temperature. It is difficult to define the optimum or optimum temperature. Because the optimum temperature for plants is closely related to factors such as air humidity and lighting. Due to the lack of lighting, the temperature inside the greenhouse should be 5-8 °C lower than the daytime. In fact, the limits of the optimum temperature for each plant species are different. However, it is desirable that the interior of the greenhouse should not be lower than 15 °C on cold days and not higher than 30 °C on sunny and hot days.
 
# GREENHOUSE PROJECT

## In this project, I aimed to create an alarm system by controlling the temperature. Under 30-35 degrees, the 1st led will light, while when 30-35 degrees is reached, the 2nd led will start to light. In this way, when it reaches 30-35 degrees, it will be understood that the greenhouse should be cooled, since it is known that this temperature is harmful to the greenhouse, by the second led on.

# Used materials:

**1-Arduino Uno
 2-LM35 
3-2 LEDs 
4-2 resistor 
5-Jumper Cables**



## The LM35 temperature sensor is a semiconductor analog temperature sensor with an accuracy of 0.5 degrees.



# LM35 Sensor Operation and Features

## **The output voltages of LM35 temperature sensors vary in proportion to the temperature. The measuring range is between -55 and 150 degrees. It provides 0.5 degree sensitivity with a supply voltage in the range of 4-30 V and a current of less than 60 micro A. The output voltage increases by 10mV for each degree. With this value, the required ratio is established and the temperature of the external environment is converted from analog to digital, that is, to values ​​that we can see digitally.**

## ARDUINO CONNECTION
![1](https://user-images.githubusercontent.com/97398192/172064416-c9279c6f-0775-4b50-945d-d52c132d1a5c.jpeg)

![2](https://user-images.githubusercontent.com/97398192/172064434-30f02751-3213-4f62-be1e-1e5c57a3b78f.jpeg)


## Arduino Code of The System

int kirmizi_led=2;             //2 numaralı pine kırmızı led bağladık

int mavi_led=3;             // 3 numaralı pine mavi led bağladık 

int lm_35=A0;                  // A0 numaralı pine sensörün base ucunu bağladık

void setup(){

pinMode(kirmizi_led,OUTPUT);            //  kırmızı led çıkış olarak seçildi

pinMode(mavi_led,OUTPUT);           // mavi led çıkış olarak seçildi

pinMode(lm_35,INPUT);       

Serial.begin(9600);// sensörden bilgi alınacağı için giriş olarak şeçildi
}

void loop(){

float lm35_okunan_deger= analogRead(lm_35);     //analog değeri değişkene atadık

float analog_sicaklik=(lm35_okunan_deger/1023)*5000;  //okunan değeri analog sıcaklık bilgisine atadık

float digital_sicaklik= analog_sicaklik/10.0;     //analog sıcaklığı Digital sıcak çevirdik

if(digital_sicaklik>35){

Serial.println(digital_sicaklik);

digitalWrite(kirmizi_led,HIGH);

digitalWrite(mavi_led,LOW);}          //sıcaklık 30 derece üstünde ise kırmızı led yansın

else{

Serial.println(digital_sicaklik);

digitalWrite(mavi_led,HIGH);          // diğer durumda mavi led yansın kırmızı led sönsün

digitalWrite(kirmizi_led,LOW);}
}***
## 

## BLOCK DIAGRAM DESIGN BY LABVIEW

![Ekran-G-r-nt-s-244](https://i.ibb.co/WF48rNM/Ekran-G-r-nt-s-244.png)


#  FRONT PANEL DESIGN BY LABVIEW
![Ekran-G-r-nt-s-235](https://i.ibb.co/9YK2qMZ/Ekran-G-r-nt-s-235.png)

![Ekran-G-r-nt-s-236](https://i.ibb.co/fQ9xFGW/Ekran-G-r-nt-s-236.png)
