```
//Replace SSID, PASSWORD and BOT-Token with your data


#include <ESP8266WiFi.h>
#include <WiFiClientSecure.h>
#include <UniversalTelegramBot.h>

// Wifi network station credentials
#define WIFI_SSID "XXXXX"
#define WIFI_PASSWORD "XXXXXX"
// Telegram BOT Token (Get from Botfather)
#define BOT_TOKEN "XXXXXXXX:XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX"

const unsigned long BOT_MTBS = 1000; // mean time between scan messages

X509List cert(TELEGRAM_CERTIFICATE_ROOT);
WiFiClientSecure secured_client;
UniversalTelegramBot bot(BOT_TOKEN, secured_client);
unsigned long bot_lasttime; // last time messages' scan has been done

int sensor=0; //Sensor input ar Analog pin A0
int Out=16;  //D0 pin for motor Signal
int value=0;

void handleNewMessages(int numNewMessages)
{
  
  Serial.print("handleNewMessages ");
  Serial.println(numNewMessages);

  for (int i = 0; i < numNewMessages; i++)
  {
    String chat_id = bot.messages[i].chat_id;
    String text = bot.messages[i].text;

    String from_name = bot.messages[i].from_name;
    if (from_name == "")
      from_name = "Guest";

    if (text == "/start")
    {
      bot.sendMessage(chat_id, "Welcome to aquabot \xF0\x9F\x8C\xB2 \n/status: To know the status \xE2\x9D\x93 \n/mon: To start motor \xF0\x9F\x94\xB5 \n/moff: To off motor \xF0\x9F\x94\xB4 ");
    }
    if (text == "/mon")
    {
      digitalWrite(Out,HIGH); // turn the LED on (HIGH is the voltage level)
      bot.sendMessage(chat_id, " \xF0\x9F\x9A\xBF ", "");
      bot.sendMessage(chat_id, " Motor is ON ", "");
    }

    if (text == "/moff") 
    {
      digitalWrite(Out, LOW); // turn the Motor off (LOW is the voltage level)
      bot.sendMessage(chat_id, "\xF0\x9F\x9A\xAB", "");
      bot.sendMessage(chat_id, " Motor is OFF ", "");
    }

    if (text == "/status")
    {
      value=analogRead(sensor);
      value=value/10;
      if (value<50)
      {
        bot.sendMessage(chat_id, " \xF0\x9F\x98\x81 ", "");
        bot.sendMessage(chat_id, "Plants are Happy!!", "");
        
      }
      else
      {
        bot.sendMessage(chat_id, " \xF0\x9F\x98\xA5 ", "");
        bot.sendMessage(chat_id, "Plants are thirsty :", "");
      }
    }
  }
}


void setup()
{
  Serial.begin(115200);
  Serial.println();

  pinMode(Out, OUTPUT); // initialize digital(D0) motor as an output.
  delay(10);
  digitalWrite(Out, LOW); // initialize pin as off (active LOW)

  // attempt to connect to Wifi network:
  configTime(0, 0, "pool.ntp.org");      // get UTC time via NTP
  secured_client.setTrustAnchors(&cert); // Add root certificate for api.telegram.org
  Serial.print("Connecting to Wifi SSID ");
  Serial.print(WIFI_SSID);
  WiFi.begin(WIFI_SSID, WIFI_PASSWORD);
  while (WiFi.status() != WL_CONNECTED)
  {
    Serial.print(".");
    delay(500);
  }
  Serial.print("\nWiFi connected. IP address: ");
  Serial.println(WiFi.localIP());

  // Check NTP/Time, usually it is instantaneous and you can delete the code below.
  Serial.print("Retrieving time: ");
  time_t now = time(nullptr);
  while (now < 24 * 3600)
  {
    Serial.print(".");
    delay(100);
    now = time(nullptr);
  }
  Serial.println(now);
}

void loop()
{
  if (millis() - bot_lasttime > BOT_MTBS)
  {
    int numNewMessages = bot.getUpdates(bot.last_message_received + 1);

    while (numNewMessages)
    {
      Serial.println("got response");
      handleNewMessages(numNewMessages);
      numNewMessages = bot.getUpdates(bot.last_message_received + 1);
    }

    bot_lasttime = millis();
  }
}

```
