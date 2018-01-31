# btc-sms-notifier

The system was initially planned to notify incoming Bitcoin transactions via SMS, linking a Bitcoin Address to a phone number

There are 5 interdependant modules (modular design instead of a single app):
-datacontroller stores and manages DB related tasks
-morse sends SMS using a commercial API gateway
-hubble listens to BlockCypher's Bitcoin address webhooks and after receiving a Tx notification it sends the needed info to octopus
-octopus acts as an orchestra director between every module. Receives Tx notifications from hubble, sends datacontroller info to store, asks morse to send an SMS to user, etc
-windshield should handle every web GUI related task and communicates with octopus exclusively and directly

Each one runs as an independent program and communicates with other modules via API commands.

System is far from perfect, dev was abandoned in early stage but it was successfully notifying about incoming Bitcoin Tx's via SMS.
ETA of SMS after Bitcoin Tx was about 10 to 30 seconds (Venezuelan SMS and phone networks are pretty slow and prone to failure)


PD: I'm a noob on RoR
