# Idea

Pomysł na projekt zrodził się z prozaicznego powodu: mieszkam w Krakowie :) Stan powietrza jest jaki jest, a mieszkanie trzeba jakoś wietrzyć. Problem polega na tym, że w czasie kiedy powietrze jest w najlepszym stanie (ok. 12:00-15:00), nie ma w domu nikogo, kto mógłby to zrobić. 

Rozwiązaniem może być połączenie trzech składników, z którymi miałem do czynienia osobno, ale nigdy razem:
* [Airly](https://airly.eu/pl)
* [ThingSpeak](https://thingspeak.com)
* [ESP8266](https://en.wikipedia.org/wiki/ESP8266)

Połączenie tych technologii umożliwi mi automatyczne załączanie wentylacji tylko wtedy, gdy stan powietrza będzie się do tego nadawał.

## Airly

Ponieważ sam nie posiadam czujnika powietrza, użyję danych Airly udostępnianych przez ich [API](https://airly.eu/pl/api/). Po zarejestrowaniu się na [plaformie deweloperskiej](https://developer.airly.eu/), otrzymujemy klucz dzięki któremu będziemy mogli pobrać aktualny stan powietrza dla wybranej pozycji geograficznej. Funkcja, z której będziemy korzystać, to **/v1/mapPoint/measurements**. W sekcji [dokumentacji](https://developer.airly.eu/docs) możemy teraz przetestować działanie funkcji:

> "currentMeasurements": {
>     "airQualityIndex": 78.75600471978652,
>     "pm1": 61.6078431372549,
>     "pm25": 63.18804117647057,
>     "pm10": 92.45425050666988,
>     "pressure": 102384.14627450977,
>     "humidity": 83.5,
>     "temperature": 2.1626960784313725,
>     "pollutionLevel": 4
>   },

Po sprawdzeniu że wszystko działa jak trzeba, przenosimy się do platformy ThingSpeak.
