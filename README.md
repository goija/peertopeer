# peertopeer

Om de WebRTC PDF Downloader direct te kunnen maken en testen zonder dat je ingewikkelde servers (zoals Node.js) hoeft te installeren, heb ik een "Serverless" prototype voor je geschreven.

In deze versie speel jij zelf voor "server" door de verbindingscodes (de zogenaamde Offer en Answer) te kopiëren en te plakken tussen twee tabbladen. Dit is de snelste manier om een werkende P2P-app te zien.

Instructies

    Maak een nieuw bestand op je computer genaamd index.html.

    Plak onderstaande code erin en sla op.

    Open dit bestand in twee aparte browser-tabbladen (of twee verschillende browsers).

    Tabblad 1 (Verzender): Kies 'Ik wil verzenden', selecteer een PDF en klik op 'Maak Verbinding'. Kopieer de code die verschijnt.

    Tabblad 2 (Ontvanger): Kies 'Ik wil ontvangen', plak de code van Tab 1 erin en klik op 'Verbinden'. Kopieer de 'Antwoord-code'.

    Tabblad 1: Plak de 'Antwoord-code' terug en rond af. De bestandsoverdracht begint direct!

    Hoe werkt dit?

In plaats van een centrale server die de twee gebruikers aan elkaar koppelt (wat normaal via websockets gaat), doe je die handdruk nu handmatig via de tekstvakken (Copy/Paste). Zodra die handdruk klaar is (peer.onicecandidate), maakt de browser een directe tunnel naar de andere browser. Het PDF-bestand vliegt daarna rechtstreeks door die tunnel, zonder dat het ooit een server raakt.
