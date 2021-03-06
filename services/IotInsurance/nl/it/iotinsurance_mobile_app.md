---

copyright:
  years: 2016
lastupdated: "2016-10-26"
---

<!-- Common attributes used in the template are defined as follows: -->
{:new_window: target="\_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}


<!-- {{site.data.keyword.iotinsurance_full}}  {{site.data.keyword.iotinsurance_short}}  -->


# Installazione e collegamento dell'applicazione mobile di esempio
{: #iot4i_gettingstarted}

L'applicazione mobile di esempio {{site.data.keyword.iotinsurance_full}} è un'implementazione di riferimento per un client mobile di {{site.data.keyword.iotinsurance_short}}. Puoi utilizzare l'applicazione per registrare nuovi dispositivi nel sistema e per ricevere avvisi per i dispositivi.
{:shortdesc}

**Prerequisiti:** prima di iniziare, assicurati che siano implementati i seguenti prerequisiti:
  - Un ambiente di sviluppo integrato Apple Xcode 8 o superiore.
  - Un dispositivo mobile iPhone iOS 9.0 o superiore.
  - CocoaPods installato sul tuo computer. Consulta il [sito web CocoaPods](https://guides.cocoapods.org/using/getting-started.html).
  - I [parametri](#iot4i_mobileParam) necessari per collegare l'applicazione mobile di esempio alla tua istanza del servizio.

## Creazione dell'applicazione mobile di esempio
{: #building_mobile}
Per provare l'applicazione mobile di esempio, completa la seguente procedura:

1. Clona [il repository del codice di origine per l'applicazione mobile di esempio](https://github.com/ibm-watson-iot/ioti-mobile) in un computer su cui è installato Xcode 7.3 o superiore.
2. Installa i pacchetti richiesti e genera il file IoT4I.xcworkspace eseguendo un comando CocoaPods pod install nel tuo progetto. CocoaPods deve essere installato per completare questa azione.
3. Apri il progetto in Xcode facendo doppio clic sul file IoT4I.xcworkspace.
4. Collega il tuo iPhone al tuo computer e selezionalo come una destinazione integrata.
5. Seleziona il file IoT4I nell'elenco dei file per visualizzare la casella di dialogo dell'identità.
6. Nella casella di dialogo dell'identità in Xcode, effettua le seguenti modifiche:
  - Modifica l'**Identificativo bundle** con un identificativo univoco, ad esempio: **myIoT4Ibundle**.
  - Imposta **Team** con il nome del tuo team personale e quindi fai clic su **Risolvi problema**.
7. Per collegare la tua applicazione alla tua istanza di {{site.data.keyword.iotinsurance_short}}, imposta i seguenti parametri nel file **constants.swift**:  
    - [applicationRoute](#iot4i_mobileParam) = L'URL della tua istanza di {{site.data.keyword.iotinsurance_short}}
    - [applicationId](#iot4i_mobileParam) = L'URL della tua istanza di {{site.data.keyword.amashort}}
8. Nel tuo computer, fai clic sulla freccia per creare ed eseguire lo schema corrente. L'applicazione mobile di esempio è installata sul tuo telefono. Per ulteriori informazioni, consulta [Apple developer instructions for running apps on devices from Xcode](https://developer.apple.com/library/mac/documentation/IDEs/Conceptual/AppDistributionGuide/LaunchingYourApponDevices/LaunchingYourApponDevices.html).

  **Nota:** se viene visualizzato un errore quando tenti la creazione con il testo *Impossibile avviare IoT4I perché non hai ancora verificato che il tuo certificato Developer App è sicuro sul tuo dispositivo*, selezionati come sviluppatore sicuro nel seguente modo:  
    1. Nel tuo telefono, vai a **Impostazioni > Generale > Gestione dispositivo > tuoIDsviluppatore**.
    2. Digita il tuo nome dell'account ID da sviluppatore per stabilire la sicurezza del tuo ID da sviluppatore.
    3. Quando richiesto, conferma che il tuo ID da sviluppatore è sicuro.

## Abilitazione delle notifiche push per l'applicazione mobile.
{: #iot4i_pushNotification}

Esegui le seguenti attività per abilitare le notifiche push per il tuo dispositivo mobile. Devi disporre di un'appartenenza a un account da sviluppatore Apple valido per utilizzare il servizio di notifica push.

1. Accedi al tuo account da sviluppatore Apple all'indirizzo https://developer.apple.com/account.

2. Crea un file certificato.
  1. Seleziona **Certificates, Identifiers & Profiles**.
  2. Seleziona identificativi: ID applicazione.
  3. Fai clic sul pulsante (+) per creare un nuovo ID applicazione.
  4. Immetti una descrizione per l'applicazione in **Description**.
  5. Seleziona **Explicit App ID** e immetti un ID bundle, ad esempio com.YourOrganizationName.iot4i.mobileApp).
  6. Seleziona (V) in **Push Notifications** e fai clic su **Continue > Register > Done**.

3. Crea un certificato di notifica push.
  1. Seleziona **Certificates: All**.
  2. Fai clic sul pulsante (+) per creare un nuovo certificato APN.
  3. Nella pagina Add iOS Certificate, seleziona **Apple Push Notification service SSL (Sandbox)** e fai clic su **Continue**.
  4. Seleziona l'ID applicazione che hai creato nel passo precedente e fai clic su **Continue**.
  5. Crea un file CSR utilizzando le istruzioni nella pagina e fai clic su **Continue**.
  6. Seleziona il file CSR che hai creato e fai clic su **Continue**.
  7. Scarica ed esegui il file certificato.

4. Crea un profilo.
  1. Seleziona **Provisioning profile: Development**.
  2. Fai clic sul pulsante (+) per creare un nuovo profilo di sviluppo.
  3. Seleziona **iOS App Development** e fai clic su **Continue**.
  4. Seleziona l'ID applicazione che hai precedentemente creato.
  5. Seleziona **Developer Certificates: All** e fai clic su **Continue**.
  5. Seleziona **All development devices (testing devices)** e fai clic su **Continue**.
  6. Specifica un nome profilo e fai clic su **Continue**.
  7. Scarica ed esegui il profilo generato.

5. Crea un file Public Key Cryptography Standards (PKCS) 12 e aggiungilo al servizio {{site.data.keyword.mobilepushshort}}.
  1. Apri Keychain Access e seleziona **My Certificates**.
  2. Fai clic con il tasto destro su **Apple Development IOS Push Service: (bundleID)** e quindi esporta, salva e immetti una password per il file. 
  3. Nella tua console {{site.data.keyword.Bluemix_notm}}, apri il servizio {{site.data.keyword.mobilepushshort}}.
  4. Fai clic su **Configura**.
  5. Nella sezione Apple Push Notifications Certificate, carica il file PKCS 12 e immetti la password password.
  6. In Xcode, modifica l'identificativo bundle con uno di quelli creati precedentemente.
  7. Esegui l'applicazione e concedi le autorizzazioni per il servizio Push Notification.

# Link correlati
{: #rellinks}

## Riferimento API
{: #api}
* [{{site.data.keyword.iotinsurance_short}} API](https://iot4i-api-docs.mybluemix.net/){:new_window}
* [{{site.data.keyword.iotinsurance_short}} API Examples](https://github.com/IBM-Bluemix/iot4i-api-examples-nodejs/#iot-for-insurance-api-examples){:new_window}

## Link correlati
{: #general}
* [Documentazione {{site.data.keyword.iot_full}}](https://console.ng.bluemix.net/docs/services/IoT/index.html)
* [Developer support forum](https://developer.ibm.com/answers/search.html?f=&type=question&redirect=search%2Fsearch&sort=relevance&q=%2B[iot]%20%2B[bluemix])
* [Stack overflow support forum](http://stackoverflow.com/questions/tagged/ibm-bluemix)
