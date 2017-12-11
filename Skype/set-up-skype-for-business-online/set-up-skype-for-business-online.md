---
title: "Configurare Skype for Business online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/16/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.prod: office-online-server
localization_priority: Priority
ms.collection:
- Adm_O365_CommTopIssues
- Adm_O365_Setup
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom:
- Adm_O365_FullSet
- Alchemy
- DianeF_Adm_Simplified
- DianeF_Setup_HappyPath
- LeftNav_Adm_O365
- LIL_Placement
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e

description: "Learn to set up your domain, users, IM and presense for your organization to install Skype for Business. Also See how to set up dial-in conferencing, Cloud PBX and PSTN calling, and Skype Meeting broadcast. "
---

# Configurare Skype for Business online

Contributori: [![Diane Faigel](../images/e4ec7084-196e-4e04-bccc-e241da509abf.png)
  
](https://go.microsoft.com/fwlink/?linkid=847124)
  
Per impostare Skype for Business devi disporre delle autorizzazioni di amministratore globale di Office 365. Se il tuo firewall o server proxy limitano l'accesso a parti del Web, puoi incaricare un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) di eseguire per te la configurazione di Skype for Business.
  
## Configurazione di Skype

Sembra che tu abbia bisogno di aiuto per la configurazione di Skype con il tuo abbonamento Office 365. Puoi seguire la procedura descritta in [questo articolo](https://support.office.com/article/https://support.office.com/en-us/article/Set-up-Skype-for-Business-Online-40296968-e779-4259-980b-c2de1c044c6e.aspx#bkmk_more) per completare la configurazione.
  
## 1. Piano per Skype for Business

Se disponi di **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** o di **Business Essentials**, puoi usare Skype for Business per chiamare online altre persone della tua azienda con il medesimo abbonamento. Ad esempio, se nell'azienda lavorano 10 persone, queste possono comunicare tra loro[Iniziare a utilizzare Skype for Business per la messaggistica istantanea e le riunioni online](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) e[Meetings with Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) con Skype for Business dopo aver eseguito le operazioni ai punti 2-6 riportate qui sotto. E potranno anche[Configurare una riunione Skype for Business in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) alle riunioni online!
  
Se vuoi usare Skype for Business per effettuare e ricevere **chiamate** da persone *esterne*  all'azienda:
  
- **Opzione 1: puoi usare l'[app Skype](https://www.skype.com/)** gratuita. Se hai un'azienda molto piccola (composta, ad esempio, da 1 o 2 persone) l'utilizzo dell'app Skype è la soluzione migliore. È l'opzione più conveniente per effettuare le chiamate nazionali e internazionali. Puoi comunque partecipare alle conferenze telefoniche, effettuare videochiamate e condividere il desktop per mostrare le presentazioni.[Controlla le tariffe e le opzioni di pagamento](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).
    
- **Opzione 2: esegui l'aggiornamento del piano e acquista il Sistema telefonico Office 365 e il Piano per chiamate Office 365**. Il modo più semplice per conoscere i costi ed effettuare il cambio è[Contattare il supporto di Office 365 per le aziende - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) e lasciar fare a loro.
    
Per ulteriori informazioni, consulta [Pianificare la configurazione di Office 365 per le aziende](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype)
  
## 2. Accedere a Office 365
<a name="bkmk_signin"> </a>

Skype for Business online fa parte della famiglia di servizi Office 365. Per configurare Skype for Business online devi accedere a Office 365. Procedi come indicato di seguito:
  
1. Individua il tuo ID utente di Office 365 (ad esempio,  *rob@fourthcoffee.com*  ). Il team dei Microsoft Online Services ti ha inviato un'e-mail con il tuo ID utente di Office 365 che hai creato al momento dell'acquisto di Skype for Business online. Il messaggio ha un aspetto simile al seguente:
    
    ![Esempio del messaggio di posta elettronica di benvenuto che si riceve dopo essersi iscritti a Skype for Business Online. Contiene l'ID utente di Office 365.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)
  
2. Vai all'indirizzo [https://portal.office.com/](https://go.microsoft.com/fwlink/p/?linkid=402333) e inserisci ID utente e password di Office 365. Dopo l'accesso, viene visualizzata l'Interfaccia di amministrazione di Office 365:
    
    ![Esempio dell'aspetto dell'interfaccia di amministrazione di Office 365 quando si ha un piano di Skype for Business Online.](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)
  
## 3. Configurare il dominio e gli utenti
<a name="bkmk_users"> </a>

Ora che hai effettuato l'accesso a Office 365, puoi configurare il tuo dominio e consentire alle persone all'interno dell'organizzazione di usare Skype for Business online.
  
1. [Aggiungere utenti e domini in Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): Usa la procedura guidata di Office 365 per configurare il tuo dominio personalizzato (ad esempio  *fourthcoffee.com*  ) con Office 365. **Per impostazione predefinita, la procedura guidata di Office 365 include la configurazione di Skype for Business online e la creazione dei tuoi ID utente di Skype for Business.** Se hai già usato la procedura guidata per configurare il tuo dominio per Office 365, hai completato questo passaggio.
    
2. [Testare il dominio e le connessioni DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0 .aspx): Usa il nostro strumento per la risoluzione dei problemi relativi ai domini e verifica che le impostazioni DNS e del tuo dominio siano corrette. Utilizzando questo strumento avrai la possibilità di capire in anticipo gli eventuali problemi di configurazione che possono verificarsi, perché sarai in grado di escludere le impostazioni DNS che potrebbero causare problemi in futuro. 
    
3. [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): questo passaggio non è necessario per la maggior parte delle aziende di piccole dimensioni. **Se hai un firewall o un server proxy che limita l'accesso a parti del Web**, devi creare regole per consentire l'accesso agli endpoint di Skype for Business online. Questo è un passaggio avanzato che viene eseguito al meglio da qualcuno che abbia esperienza con la configurazione dei firewall e dei server proxy. Se non lo hai fatto prima, prendi in considerazione l'intervento di un[partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) che esegua per te la configurazione di Skype for Business.
    
## 4. Configurare le funzionalità di messaggistica istantanea e presenza all'interno dell'organizzazione
<a name="bkmk_IM"> </a>

Messaggistica istantanea (IM) e presenza ([Controllo dell'accesso alle informazioni sulla presenza in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c#bkmk_presence)) sono funzionalità di base incluse in Skype for Business. Per impostazione predefinita le persone della tua azienda possono comunicare tra loro utilizzando Skype e i messaggi istantanei.
  
1. **Scegliere con quali altri utenti possono comunicare gli utenti Skype for Business:**
    
  - [Consentire agli utenti di contattare utenti Skype for Business esterni](allow-users-to-contact-external-skype-for-business-users.md) Sia tu *che*  l'altra azienda dovrete configurare i vostri sistemi.
    
    **IMPORTANTE**: se nell'azienda ci sono due domini, per esempio rob@contosowest.com e ina@contosoeast.com, è necessario procedere con questa operazione in modo che tutti gli utenti possano comunicare tra loro.
    
  - [Consenti agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) esterni alla tua azienda
    
2. **Scegliere chi può vedere se i colleghi sono online:** La funzionalità presenza mostra chi è online e fornisce una descrizione della sua disponibilità, ad esempio, disponibile, non disponibile, non al computer, o presentazione in corso.
    
    ![An example of a person's online status with a personal message.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)
  
    Puoi scegliere le impostazioni predefinite per tutte le persone della tua azienda:
    
  - Mostra automaticamente la presenza online di una persona a tutti gli utenti dell'organizzazione
    
  - Mostra la presenza online di una persona solo ai suoi contatti
    
Per le istruzioni, vedi [Configurare la presenza in Skype for Business online](configure-presence-in-skype-for-business-online.md).
  
## 5. Scaricare e installare Skype for Business
<a name="bkmk_download"> </a>

Per utilizzare Skype for Business sul PC, sul Mac o su un dispositivo mobile, tu e altre persone nella tua azienda dovrete prima di tutto installare il download di Skype for Business sui dispositivi. 
  
- [Installare Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Istruzioni su come scaricare l'app dal portale di Office 365 e installarla sul PC o Mac. 
    
- [Distribuire il client Skype for Business in Office 365](deploy-the-skype-for-business-client-in-office-365.md) : Istruzioni per distribuire l'app in un'azienda di grandi dimensioni.
    
- [Installare Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Scaricare, installare e accedere a Skype for Business su dispositivi Android, dispositivi iOS e telefoni Windows Phone.
    
- [Attivare o disattivare le notifiche su cellulare](turn-on-or-off-mobile-phone-notifications.md) : Quando Skype for Business viene installato su un dispositivo mobile, tu e altre persone nella tua azienda potete ricevere avvisi sui messaggi istantanei in arrivo e quelli persi.
    
## 6. Eseguire il test per accertarsi che tutto funzioni correttamente
<a name="bkmk_test"> </a>

Prima di tutto, verifica che tu e gli altri utenti nell'azienda possiate [Video: Effettuare l'accesso e disconnettersi da Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451). Verifica che tu e l'altro utente possiate scambiarvi messaggi istantanei e visualizzare le informazioni sulla rispettiva presenza, quindi prova ad avviare una riunione rapida.
  
In caso di problemi, procedi come segue:
  
- [Occorrono indicazioni per l'accesso a Skype for Business?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) di comuni problemi di accesso.
    
- [Contattare il supporto di Office 365 per le aziende - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Siamo qui per aiutarti! 
    
## Desideri configurare altre funzionalità disponibili?
<a name="bkmk_more"> </a>

Prima di configurare altre funzionalità, accertati di avere le licenze necessarie. [Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
### Configurare l'audioconferenza

Talvolta le persone all'interno dell'organizzazione dovranno usare un telefono per accedere a una riunione. Skype for Business offre la funzione di audioconferenza proprio per queste evenienze! Le persone possono accedere alle riunioni di Skype for Business usando un telefono, al posto di usare la app di Skype for Business su un dispositivo mobile o PC.
  
Per le istruzioni dettagliate, consulta [Configurare le audioconferenze per Skype for Business e Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md) in Office 365.
  
### Configurare il Sistema telefonico e il Piano per chiamate in Office 365

Con il Sistema telefonico Office 365, si ha a disposizione un sistema telefonico per l'azienda. Le chiamate verso altri contatti di Skype for Business all'interno dell'organizzazione sono gratuite e i dipendenti possono ricevere i messaggi vocali tra loro e da chiamanti esterni. Ecco cosa offre il Sistema telefonico.
  
Aggiungendo il servizio di Piano per chiamate, i dipendenti ricevono un numero di telefono primario in Skype for Business. Possono fare e ricevere chiamate telefoniche al di fuori dell'azienda. Possono effettuare chiamate vocali su telefoni VoIP, PC e dispositivi mobili. E, in caso di emergenza, possono chiamare il 911.
  
Per le istruzioni dettagliate, consulta Configurare i Piani per chiamate.
  
### Configurare Skype Meeting Broadcast

Skype Meeting Broadcast è una funzionalità che consente di pianificare, produrre, ospitare e trasmettere riunioni a cui possono partecipare fino a 10.000 persone. **Per maggiori informazioni su come funziona, vedi [Informazioni su Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**
  
Ecco una panoramica dei passaggi per la configurazione di Skype Meeting Broadcast:
  
1. [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): Assegna le licenze per **Skype for Business Online** o per il **piano Enterprise** a tutti gli utenti che intendono **ospitare** una riunione Broadcast.
    
2. [Abilitare Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md) : Per impostazione predefinita, questa funzionalità non è abilitata. Dopo che l'avrai abilitata, i tuoi utenti saranno in grado di ospitare riunioni broadcast con altre persone dell'organizzazione.
    
3. [Configurare la rete per Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md) : se desideri ospitare webinar e altre broadcast con partecipanti esterni all'organizzazione, devi configurare la rete.
    
4. [Pianificazione di un evento Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) e fare in modo che[Partecipare a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): verifica che le riunioni broadcast vadano a buon fine pianificando una Skype Meeting Broadcast sul sito  *https://portal.broadcast.skype.com*  e facendo in modo che un utente tenti di partecipare alla riunione.
    
## Maggiori informazioni sui requisiti di connettività di rete
<a name="bkmk_more"> </a>

La qualità della connettività di rete end-to-end influisce notevolmente sulla qualità delle condivisioni audio, video e di applicazioni in Skype for Business. Per un'esperienza ottimale, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype for Business Online. Per informazioni relative alla rete e all'ottimizzazione, vedi la sezione [Ottimizzare le prestazioni di Skype for Business Online](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).
  
## La configurazione è stata eseguita? Introduzione all'utilizzo di Skype for Business
<a name="bkmk_more"> </a>

[Alla scoperta di Skype for Business](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): consulta questo elenco di argomenti di formazione per iniziare subito!
  
[Avviare una conferenza telefonica Skype for Business](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)
  
[Impostare le opzioni dei dispositivi video in Skype for Business](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)
  
[Effettuare e ricevere videochiamate con Skype for Business](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)
  
## 
<a name="bkmk_more"> </a>

||
|:-----|
|![Icona breve di LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Nuovi utenti di Office 365?**         Vedere i corsi video gratuiti per **amministratori di Office 365 e professionisti IT**, offerti da LinkedIn Learning. |
   
## Argomenti correlati
<a name="bkmk_more"> </a>

[Pianificare connettività ibrida tra Skype for Business Server e Skype for Business Online](https://go.microsoft.com/fwlink/p/?linkid=400791)
  

