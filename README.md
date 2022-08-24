
# Radiosignaler
##Steg 0 @showdialog
Dette eksempelet viser hvordan du sender signaler fra en micro:bit til en annen.
Pass på at begge micro:bitene er stilt inn på samme kanal ("group"), og at ingen andre i rommet bruker samme tall.
```blocks
radio.setGroup(1)
```
##Steg 1 - forklaring
Les koden under. 
Ved Start bestemmer vi hvilken radiokanal micro:biten skal sende signaler på.
Når Knapp B trykkes, sender micro:biten beskjeden "Hello world!"
Trykk på knapp B på simulatoren til venstre og se hva som skjer.


##Steg 2 -  enda mer forklaring 
Antennen i simulatoren gløder for å vise at et signal sendes, og det dukker opp enda en micro:bit i simulatoren.
Begge micro:bitene har det samme programmet.
For øyeblikket skjer det skuffende lite hos mottakeren.

##Steg 3 - 
Finn "on radio received receivedString"-blokken, og legg den til et sted i programmet.
Denne blokken ligner veldig på "Når knapp B trykkes"-blokken, men i stedet for å kjøre kode når du trykker på en knapp, kjører den kode når den mottar en tekstmelding.

##Steg 4 -
Hent en "vis tekst" blokk, og putt den inni "receivedNumber"-blokken. 
Prøv å trykke på knapp B i simulatoren. Hva skjer med mottakeren?
##Steg 5 - @showdialog
Klikk og dra den runde "receivedString"-variabelen ned i vis tekst slik:
```blocks
radio.onReceivedString(function (receivedString) {
    basic.showString(receivedString)
})
```
##steg 6 - 
Ser du noen forskjell når du trykker på knappen nå?
##Steg 7 @showdialog
Godt jobbet! 
I den neste radio-veiledningen får du se eksempler på hvordan du kan bruke bluetooth-signaler for å fjernstyre motorer.
##Steg 8 
Trykk på Finish for å forlate veiledningen.

```template
input.onButtonPressed(Button.B, function () {
    radio.sendString("Hello world!")
})
radio.setGroup(1)
```
```ghost
radio.onReceivedString(function (receivedString) {
    basic.showString("Hello!")
    radio.sendNumber(0)
    basic.showNumber(0)
})
input.onButtonPressed(Button.B, function () {
    radio.sendString("Hello world!")
})
radio.setGroup(1)

```
