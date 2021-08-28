---
title: Pianificare i client riunioni (App Web e app Riunioni)
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: "Riepilogo: i professionisti IT devono esaminare i requisiti di supporto per l'app riunioni Skype for Business Web App e Skype durante la pianificazione di Skype for Business Server. Questo articolo non è destinato agli utenti di queste app."
ms.openlocfilehash: 29464c7dffbeee1a8ae6eed33764453bed948c58
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608023"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Pianificare i client riunioni (App Web e app Riunioni)
 
**Riepilogo:** I professionisti IT devono esaminare i requisiti di supporto per l'app riunioni Skype for Business Web App e Skype durante la pianificazione di Skype for Business Server. Questo articolo non è destinato agli utenti di queste app.
  
Dopo aver implementato Skype for Business Server, gli utenti dell'organizzazione probabilmente avranno installato il client Skype for Business come parte del processo di distribuzione. 
  
In seguito, tali utenti possono creare riunioni e invitare utenti esterni all'organizzazione e gli invitati alle riunioni potrebbero non avere alcuna versione del client Skype for Business. Quando gli utenti fanno clic sull'URL per l'invito alla riunione, viene rilevata la mancanza di un client e all'invitato senza un client Skype for Business verrà richiesto di scaricare e installare un client leggero solo per le riunioni in modo che possa partecipare alla riunione.
  
> [!NOTE]
> L Skype for Business Web App e Skype riunioni sono disponibili solo quando si tenta di accedere a una riunione senza dover Skype for Business. La Guida dell'utente per queste app è disponibile all'indirizzo [https://aka.ms/smahelp](https://aka.ms/smahelp) . 
  
> [!NOTE]
> Non è possibile preinstallare l'app riunioni Skype for Business Web App o Skype, ma gli utenti di [smartphone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) e [tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) potrebbero essere in grado di installare client mobili poco costosi che possono usare per partecipare alle riunioni.
  
Per impostazione predefinita, il server che ospita la riunione invierà l'utente a scaricare e installare Skype for Business Web App per partecipare alla riunione. Il Skype for Business Web App viene archiviato nel Front End Server e viene inviato al partecipante alla riunione. 
  
Per Skype for Business Server, Skype Meetings App (su Windows) e Skype for Business per Mac (su Mac) sono disponibili come sostituzioni per Skype for Business Web App a partire da CU5, ma per fornire le app sostitutive è necessaria la configurazione aggiuntiva descritta in [Enable Skype Meetings App to replace Skype for Business Web App (Optional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Se Skype Meetings App e Skype for Business per Mac sono abilitati, gli utenti scaricano la versione più recente delle app da Microsoft 365 o Office 365 rete per la distribuzione di contenuti (rete CDN) anziché dal server Skype for Business. Per Skype for Business Server 2019, l'Skype Meeting App e Skype for Business per Mac è l'unica opzione.
  
Skype L'app Riunioni offre un'esperienza browser semplificata per scaricare e installare l'app e partecipare alle riunioni, inclusa la partecipazione con un solo clic per gli utenti di Internet Explorer. Skype L'app Riunioni presenta anche molti miglioramenti rispetto al Skype for Business Web App per l'affidabilità e l'esperienza delle riunioni. 
  
> [!NOTE]
> A Skype for Business Server 2015 CU5 o versioni successive, le riunioni tenute con Skype for Business Online non invieranno più a un utente senza client il Skype for Business Web App, ma verranno inviate Skype Meetings App (su Windows) o Skype for Business per Mac (su Mac). A Skype for Business Server 2015 CU5 o versioni successive, se abiliti l'app Riunioni di Skype per sostituire [Skype for Business Web App (facoltativo),](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable)gli utenti senza client verranno inviati Skype Meetings App o Skype for Business per Mac anziché Skype for Business Web App. 
  
## <a name="software-requirements"></a>Requisiti software
<a name="OS-Browser"> </a>

Per usare il Skype for Business Web App, un utente deve disporre di una delle combinazioni di browser e sistema operativo supportate seguenti. 
  
**Sistema operativo e supporto minimo dei browser per Skype for Business Web App**

| Sistema operativo | Edge | Internet Explorer 11 a 32 e 64 bit o versione successiva | 32 e 64 bit Internet Explorer 10 o versioni successive | Internet Explorer 9 a 32 e 64 bit o versione successiva | Versione a 32 e 64 bit di Safari 6.2.8 - 11.X | Versione a 32 e 64 bit di Chrome 18.X o versione successiva |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sì &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |N/D  <br/> |Sì  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sì &#x2778; <br/> |
|Windows 8 (basato su Intel) &#x2776; <br/> |N/D  <br/> |N/D  <br/> |Sì  <br/> |N/D <br/> |N/D  <br/> |Sì &#x2778; <br/> |
|Windows 7 con SP1 &#x2777; <br/> |N/D  <br/> |Sì  <br/> |No  <br/> |No  <br/> |N/D <br/>|Sì &#x2778; <br/> |
|Windows Server 2008 R2 con SP1 &#x2777; <br/> |N/D  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |N/D <br/>|Sì &#x2778; <br/> |
|macOS 10.8 e versioni successive (basato su Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sì  <br/> |Sì <br/> |
   
&#x2776; Il plug-in del browser Skype for Business Web App richiede un plug-in di condivisione specifico per usare funzionalità vocali, video, condivisione e visualizzazione dello schermo in corso. A un partecipante alla riunione viene data la possibilità di installare il plug-in di condivisione quando partecipa alla riunione o quando avvia una di queste funzionalità. In Windows 8 e Windows 8.1, il plug-in di condivisione può essere installato solo se si esegue Internet Explorer 10 o Internet Explorer 11 per il desktop. Queste funzionalità non sono disponibili con le versioni non desktop di Internet Explorer 10 e 11. Si noti che Firefox e Safari versione 12.0 e successive non sono più supportati.
  
&#x2777; Nei sistemi operativi Windows 7, Windows Server 2008 R2 e Macintosh supportati sono disponibili tutte le funzionalità, tra cui voce basata su computer, video, visualizzazione applicazioni, condivisione applicazioni, visualizzazione desktop e condivisione desktop. Per usare queste funzionalità, è necessario installare un plug-in quando richiesto. Mac OS X versione 10.7 non è più supportato.  Nota anche che l'app Web non verrà installata in OS X 10.15 o versione successiva.  È consigliabile usare la versione più recente di Skype for Business per Mac che supporta scenari di join anonimi in futuro.
  
&#x2778;'accesso all'app Web da Chrome in Windows verrà avviato un piccolo programma che carica l'app Web in un frame incorporato di Internet Explorer. Per il corretto caricamento dell'app Web, è necessario che sia installata una delle versioni supportate di Internet Explorer.
  
> [!NOTE]
> Microsoft 365 e Office 365 utenti possono usare Internet Explorer 10 o versioni successive con Skype for Business. 
  
### <a name="skype-meetings-app"></a>App Riunioni Skype

Skype L'app Riunioni viene eseguita come app nei computer che usano Windows 10, Windows 8.1, Windows 8, Windows 7, con Installato Internet Explorer 11 a 32 e 64 bit o versione successiva. 
  
Per altre dipendenze, fai riferimento [a Piattaforme supportate per Skype Riunioni App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business per Mac

Skype for Business per Mac viene eseguito nei computer che usano macOS versione 10.8 o successiva. 

## <a name="hardware-requirements"></a>Requisiti hardware
<a name="OS-Browser"> </a>

I requisiti hardware del computer sono determinati dal sistema operativo e dal browser. Le funzionalità vocali e telefoniche richiedono un microfono e altoparlanti, un auricolare con microfono o un dispositivo equivalente compatibile con il computer. Le funzionalità video richiedono un dispositivo video compatibile con il computer. Per informazioni dettagliate sul supporto dell'hardware video e sulla qualità video prevista, Skype for Business [risoluzioni video client.](video-resolutions.md)
  
## <a name="network-requirements"></a>Requisiti di rete
<a name="Network"> </a>

Se un utente di Skype for Business Web App o Skype Meetings App verifica problemi di connessione, è probabile che l'infrastruttura di rete dell'organizzazione non sia configurata per supportare Office 365, come descritto in URL e intervalli di indirizzi [IP di Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Questo è il caso se la riunione è stata creata da un utente di Skype for Business Online o Skype for Business Server. 
  
Se l'utente si trova in una rete non configurata come descritto, molte funzionalità dell'app potrebbero non funzionare e potrebbero non essere affatto in grado di connettersi alla riunione.
  
## <a name="supported-meetings-features"></a>Funzionalità riunioni supportate
<a name="BKMK_Conferencing"> </a>

In questa tabella vengono confrontate le funzionalità riunioni disponibili per gli utenti del client Skype for Business, Skype for Business Web App, Skype'app Riunioni e Lync Web App. Lync Web App è elencato a scopo di confronto delle funzionalità: un utente sta scaricando e usando Lync Web App solo se la riunione è stata ospitata su un server Lync 2013.

| Funzionalità/funzionalità | Skype for Business 2016 o 2019 | Skype for Business sul client Mac | App Riunioni Skype | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Aggiungere la funzionalità audio al computer  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |
|Aggiungere la funzionalità video  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |
|Passare dall'audio a un telefono per i partecipanti autenticati  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Passare dall'audio a un telefono per i partecipanti guest  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Visualizzare video con più parti (visualizzazione Raccolta)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condivisione dello schermo basato su video  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(sola visualizzazione)  <br/> |||
|Utilizzare controlli di relatore nell'ambito delle riunioni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accedere all'elenco dettagliato delle riunioni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a conversazioni istantanee tra più utenti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Impostare i messaggi di messaggistica istantanea come priorità elevata  <br/> |&#x2714;|||||
|Condividere il desktop (se consentito)  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |
|Condividere un programma (se consentito)  <br/> |&#x2714;||&#x2714;(Solo Windows e richiede plug-in)  <br/> |&#x2714;(Solo Windows e richiede plug-in)  <br/> |&#x2714;(Solo Windows e richiede plug-in)  <br/> |
|Assumere il controllo del desktop o del programma condiviso di un altro utente  <br/> |&#x2714;||&#x2714; (&#x2776; solo Windows e richiede plug-in)  <br/> |&#x2714; (&#x2776; solo Windows e richiede plug-in)  <br/> |&#x2714; (&#x2776; solo Windows e richiede plug-in)  <br/> |
|Consentire a un altro utente di assumere il controllo del desktop o del programma condiviso  <br/> |&#x2714;|||||
|Aggiungere partecipanti anonimi (se consentito)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitare partecipanti per nome  <br/> |&#x2714;|&#x2714;||||
|Invitare partecipanti per numero di telefono  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitare partecipanti tramite posta elettronica  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usare riunioni audio con accesso remoto  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Avviare una riunione riunione  <br/> |&#x2714;|&#x2714;||||
|Registrare una riunione  <br/> |&#x2714;|||||
|Aggiungere e scaricare allegati  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Aggiungere e presentare file di Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Esplorare i file PowerPoint Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere e modificare note OneNote riunione  <br/> |&#x2714;||Solo modifica (non aggiunta)  <br/> |Solo modifica (non aggiunta)  <br/> |Solo modifica (non aggiunta)  <br/> |
|Utilizzare una lavagna  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Effettuare sondaggi  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Upload file da condividere con altri utenti  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Pianificare una riunione o una conferenza  <br/> |Outlook o Skype for Business Web Scheduler  <br/> |Outlook o Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |Skype for Business Web Scheduler  <br/> |
|D &amp; A Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Disabilitare il video dei partecipanti  <br/> |&#x2714;|||||
|Disabilitare la messaggistica istantanea riunione  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Disattiva gruppo di destinatari  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Rendi tutti i partecipanti  <br/> |&#x2714;|||||
|Produrre Riunione Skype Broadcast  <br/> |&#x2714;|||||
   
 &#x2776; i partecipanti non possono controllare i desktop condivisi dagli utenti di Skype for Business per Mac, Lync per Mac 2011 o Communicator per Mac 2011. Questo non funziona anche per i Skype for Business Web App su Max OSX.
  
 &#x2777; Per Skype for Business Online, questa funzionalità richiede Servizi di conferenza PSTN Microsoft, Exchange messaggistica unificata o un provider di servizi di audioconferenza di terze parti.
  
 &#x2778; Il client Lync per Mac 2011 non può visualizzare le presentazioni di Microsoft Office 2013 PowerPoint quando sono state condivise in una conferenza dal Skype for Business Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problemi noti e risoluzione dei problemi
<a name="BKMK_Conferencing"> </a>

Per gli utenti finali, la [Guida online](https://aka.ms/smahelp) per queste app è immediatamente disponibile. I professionisti IT devono essere a conoscenza dei seguenti problemi:
  
- Se l'utente si trova in una rete non configurata per soddisfare i requisiti di [rete,](meetings-clients.md#Network)molte funzionalità dell'app potrebbero non funzionare e potrebbero non essere affatto in grado di connettersi alla riunione.
    
- Alcuni utenti potrebbero avere computer amministrati dall'azienda con l'autorizzazione disabilitata per installare le app. per questi utenti, nessuna delle due app è un'opzione, ma gli utenti di [smartphone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) e [tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) potrebbero essere in grado di installare client mobili economici che possono usare per partecipare alle riunioni.
    
    Altri problemi di installazione sono trattati anche negli argomenti [della Guida.](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US) 
    
- Gli utenti potrebbero visualizzare un avviso del firewall la prima volta che eseguono l'app riunioni. Potrebbe essere richiesto loro di aprire le porte per ottimizzare l'esperienza e ciò potrebbe richiedere privilegi di amministratore sul computer che potrebbero non avere. L'app dovrebbe comunque funzionare e l'utente può tranquillamente rifiutare di aprire le porte richieste. 
    
- Devi avere abilitato [ActiveX senza filtro](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) in Internet Explorer, anche se Internet Explorer non è il browser predefinito. In Skype for Business Web App è necessario un controllo ActiveX, un piccolo modulo che aggiunge funzionalità aggiuntive a un'app Web o a un altro programma, per la condivisione di audio, video e schermo.
    
- Per il corretto funzionamento di alcune Skype for Business Web App, è necessario consentire al browser di salvare i [cookie](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) nel computer o nel dispositivo.
    
- Potrebbe essere necessario [attivare il supporto JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) nel browser perché alcune funzionalità Skype for Business Web App funzionino come previsto.
    
### <a name="aes-support"></a>Supporto AES 

A partire da Skype for Business Server 2015 CU5, AES non è supportato per ASP.NET 4.6 e ciò potrebbe causare l'avvio dell'app Riunioni Skype. [I requisiti di crittografia dovuti a ASP.NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) hanno altri dettagli.
  
## <a name="see-also"></a>Vedere anche
<a name="BKMK_Conferencing"> </a>

[Distribuire client scaricabili Web in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Piattaforme supportate per l'app Skype riunioni](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
