---

copyright:
 years: 2015, 2016

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Configurazione delle credenziali per il browser web Safari
{: #configure-credential-for-safari}
Ultimo aggiornamento: 06 dicembre 2016
{: .last-updated}

Il servizio IBM {{site.data.keyword.mobilepushshort}} ora estende le funzionalità per inviare le notifiche al tuo browser Safari. La versione supportata è Safari 10.0.

## Generazione di un certificato
  {: #certificate-generation}

Assicurati di disporre in un account Apple Developer. Hai bisogno di registrare un ID push sito web e generare un certificato per configurare il tuo browser Safari per ricevere le notifiche. La seguente procedura ti aiuterà ad iniziare.

1. Nel Apple Developer Member center, fai clic su **Certificates, ID & Profiles**. 
2. Fai clic su **Identifiers** e quindi su **Website Push IDs**.
3. Scegli di creare una nuova voce selezionando l'icona più.
  ![Dashboard Push](images/safari_1.jpg)

4. Nel pannello Register Website Push ID, fornisci un ID identificativo e una descrizione Website Push ID appropriati. Ti raccomandiamo che sia nel formato del nome a dominio inverso, e che inizi con 'web'. Ad esempio: web.com.example.dailyweatherreports.
5. Registra l'ID push sito web. Ora hai un ID push sito web. 
6. Seleziona **Edit** per creare un certificato da utilizzare per l'ID push sito web.
7. Nella finestra Certificate Assistant per Certificate Information, fornisci il tuo indirizzo email e un nome comune. Lascia l'indirizzo email Certificate Authority vuoto.
8. Fai clic su **Save to disk** e seleziona **Continue**.
9. Scegli di salvare il certificato in una cartella appropriata.
10. Scegli il `.certSigningRequest` creato sul disco quando ti viene richiesto nella procedura guidata di creazione del certificato. Assicurati di scaricare il certificato di push sito web creato nel formato `.cer`.
11. Apri il certificato nello strumento KeyChain Access. Fai clic con il tasto destro del mouse ed esportalo come certificato p12. Annota la password fornita durante la generazione del certificato p12.


## Configurazione per le notifiche
  {: #configuration-notification}
 
Dopo aver generato il certificato, puoi configurare il servizio per l'invio di notifiche a Safari. 

Completa la procedura:

1. Nel dashboard del servizio Push Notifications, fai clic su **Configure**. 
2. Seleziona la scheda Web. 
3. Nella sezione Safari Push, aggiorna il modulo con le informazioni richieste. 
	- **Website Name**: il nome che hai fornito nel centro di notifica.
	- **Website Push ID**: aggiorna con la stringa reverse-domain per il tuo ID push sito web. Ad esempio, web.com.example.www.
	- **Website URL**: fornisci l'URL del sito web da sottoscrivere alle notifiche di push. Ad esempio, https://www.example.com.
	- **Allowed Domains**: parametro facoltativo. Indica l'elenco di siti web che richiedono l'autorizzazione dall'utente. Assicurati che gli URL siano valori separati da virgola. Se non si fornisce questo valore, verrà utilizzato quello specificato in Website URL. 
	- **URL Format String**: l'URL da risolvere quando si fa clic sulla notifica. Ad esempio, ["https://www.example.com"]. Assicurati che l'URL utilizzi lo schema http o https.
	- **Safari web push certificate**: carica il certificato .p12 e fornisci la password.
4. Fai clic su **Save**.	

![Dashboard Push](images/push_configure_safari.jpg)	

Il servizio è ora configurato per l'invio di notifiche di push al browser Safari.

	
