---
title: Pianificare i client di riunioni (app per le riunioni e le app Web)
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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: "Riepilogo: i professionisti IT devono esaminare i requisiti di supporto per l'app Skype for Business Web App e Skype Meetings durante la pianificazione di Skype for Business Server. Questo articolo non è destinato agli utenti di queste app."
ms.openlocfilehash: 4956a11c0ed163cbe50c49233e9aa05a0fbbd872
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826016"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Pianificare i client di riunioni (app per le riunioni e le app Web)
 
**Riepilogo:** I professionisti IT devono esaminare i requisiti di supporto per l'app Skype for Business Web App e Skype Meetings durante la pianificazione di Skype for Business Server. Questo articolo non è destinato agli utenti di queste app.
  
Dopo aver implementato Skype for Business Server, gli utenti dell'organizzazione avranno presumibilmente installato il client Skype for business come parte del processo di distribuzione. 
  
Successivamente, gli utenti possono creare riunioni e invitare utenti esterni all'organizzazione e gli invitati alla riunione potrebbero non avere alcuna versione del client Skype for business. Quando gli utenti fanno clic sull'URL dell'invito alla riunione, viene rilevata la mancanza di un client e viene richiesto all'utente senza un client Skype for business di scaricare e installare un client Lightweight, solo riunioni, in modo che possano partecipare alla riunione.
  
> [!NOTE]
> L'app Skype for Business Web App e Skype Meetings è disponibile solo quando si tenta di accedere a una riunione senza Skype for business. La guida dell'utente per queste app è at [https://aka.ms/smahelp](https://aka.ms/smahelp) . 
  
> [!NOTE]
> Non è possibile preinstallare l'app Skype for Business Web App o Skype meetings, ma gli utenti di [Smart Phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) e [Tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) potrebbero essere in grado di installare client mobili economici che possono utilizzare per partecipare alle riunioni.
  
Per impostazione predefinita, il server che ospita la riunione consentirà all'utente di scaricare e installare Skype for Business Web App per partecipare alla riunione. Skype for Business Web App è memorizzato nel front end server e viene inviato al partecipante alla riunione. 
  
Per Skype for Business Server, le app per riunioni Skype (su Windows) e Skype for business per Mac (su Mac) sono disponibili come sostituzioni per Skype for Business Web App a partire da CU5, ma fornire le app di sostituzione richiede la configurazione aggiuntiva descritta in [Enable Skype Meetings app to replace Skype for Business Web App (facoltativo)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Se le riunioni Skype app e Skype for business per Mac sono abilitate, gli utenti scaricheranno la versione più recente delle app da Microsoft 365 o Office 365 Content Delivery Network (CDN) anziché da Skype for Business Server. Per Skype for Business Server 2019, l'utilizzo dell'app Skype Meetings e di Skype for business per Mac è l'unica opzione.
  
Skype Meetings app offre un'esperienza browser semplificata per il download e l'installazione dell'app e la partecipazione alle riunioni, inclusa la join con un clic per gli utenti di Internet Explorer. L'app Skype Meetings offre anche numerosi miglioramenti rispetto a Skype for Business Web App per l'affidabilità e l'esperienza di riunione. 
  
> [!NOTE]
> A seguito di Skype for Business Server 2015 CU5 o versione successiva, le riunioni che utilizzano Skype for business online non invieranno più un utente senza client Skype for Business Web App, verranno invece inviate le app per riunioni Skype (su Windows) o Skype for business per Mac (su Mac). Come in Skype for Business Server 2015 CU5 o versione successiva, se si [Abilita l'app per le riunioni Skype per sostituire Skype for Business Web App (facoltativo)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), gli utenti non consentiti verranno inviati all'app Skype meetings o Skype for business per Mac anziché in Skype for Business Web App. 
  
## <a name="software-requirements"></a>Requisiti software
<a name="OS-Browser"> </a>

Per utilizzare l'app Web di Skype for business, un utente deve disporre di una delle seguenti combinazioni di browser e sistema operativo supportate. 
  
**Sistema operativo e supporto dei browser minimo per Skype for Business Web App**

| Sistema operativo | Edge | 32-e 64-bit Internet Explorer 11 o versioni successive | 32-e 64-bit Internet Explorer 10 o versioni successive | 32-e 64-bit Internet Explorer 9 o versioni successive | Versione 32-e 64 bit di Safari 6.2.8-11. X | Versione 32 e 64 bit di Chrome 18. X o versioni successive |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sì &#x2778; <br/> |
|&#x2776; di Windows 8,1 <br/> |N/D  <br/> |Sì  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sì &#x2778; <br/> |
|&#x2776; di Windows 8 (basato su Intel) <br/> |N/D  <br/> |N/D  <br/> |Sì  <br/> |N/D <br/> |N/D  <br/> |Sì &#x2778; <br/> |
|&#x2777; di Windows 7 con SP1 <br/> |N/D  <br/> |Sì  <br/> |No  <br/> |No  <br/> |N/D <br/>|Sì &#x2778; <br/> |
|Windows Server 2008 R2 con SP1 &#x2777; <br/> |N/D  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |N/D <br/>|Sì &#x2778; <br/> |
|&#x2777; macOS 10,8 e versioni successive (basate su Intel) <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sì  <br/> |Sì <br/> |
   
&#x2776; il plug-in del browser di Skype for Business Web App richiede un plug-in di condivisione specifico per l'utilizzo di funzionalità vocali, video, condivisione e visualizzazione della condivisione dello schermo in continuo e altre caratteristiche. A un partecipante alla riunione viene data la possibilità di installare il plug-in di condivisione quando partecipano alla riunione o quando avviano una di queste funzionalità. In Windows 8 e Windows 8,1, è possibile installare il plug-in di condivisione solo se è in esecuzione Internet Explorer 10 o Internet Explorer 11 per il desktop. Queste funzionalità non sono disponibili con le versioni non desktop di Internet Explorer 10 e 11. Si noti che Firefox e Safari versione 12,0 e versioni successive non sono più supportati.
  
&#x2777; sui sistemi operativi Windows 7, Windows Server 2008 R2 e Macintosh supportati, sono disponibili tutte le funzionalità, tra cui voce, video, visualizzazione applicazioni, condivisione applicazioni, visualizzazione desktop e condivisione desktop. Per utilizzare queste funzionalità, è necessario installare un plug-in quando richiesto. Si noti che Mac OS X versione 10,7 non è più supportato.  Si noti inoltre che l'applicazione Web non verrà installata su OS X 10,15 o versioni successive.  È consigliabile utilizzare la versione più recente di Skype for business per Mac, che supporta gli scenari di join anonimi in avanti.
  
&#x2778; l'accesso all'app Web da Chrome su Windows lancerà un piccolo programma che carica l'app Web in un frame Internet Explorer incorporato. Questo programma richiede la corretta installazione di una delle versioni supportate di Internet Explorer per l'applicazione Web.
  
> [!NOTE]
> Gli utenti di Microsoft 365 e Office 365 possono utilizzare Internet Explorer 10 o versioni successive con Skype for business. 
  
### <a name="skype-meetings-app"></a>App Riunioni Skype

L'app riunioni Skype viene eseguita come un'app nei computer che utilizzano Windows 10, Windows 8,1, Windows 8, Windows 7, con 32 e 64 bit Internet Explorer 11 o versione successiva installata. 
  
Per eventuali altre dipendenze, fare riferimento a [piattaforme supportate per l'app riunioni Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for Business per Mac

Skype for business per Mac viene eseguito su computer che utilizzano macOS versione 10,8 o successiva. 

## <a name="hardware-requirements"></a>Requisiti hardware
<a name="OS-Browser"> </a>

I requisiti hardware del computer sono determinati dal sistema operativo e dal browser. Le funzionalità vocali e di telefonia richiedono un microfono e altoparlanti, auricolare con microfono o dispositivo equivalente compatibile con il computer. Le funzionalità video richiedono un dispositivo video compatibile con il computer. Per informazioni dettagliate sul supporto hardware video e sulla qualità video prevista, vedere [risoluzioni video client Skype for business](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisiti di rete
<a name="Network"> </a>

Se un utente di Skype for Business Web App o Skype Meetings app incontra problemi di connessione, è probabile che l'infrastruttura di rete dell'organizzazione non sia configurata per il supporto di Office 365 come descritto in [office 365 URLs and IP address ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). Questo è il caso se la riunione è stata creata da un utente di Skype for business online o Skype for Business Server. 
  
Se l'utente si trova in una rete non configurata come descritto, molte funzionalità dell'app potrebbero funzionare o meno e potrebbero non essere in grado di connettersi alla riunione.
  
## <a name="supported-meetings-features"></a>Funzionalità di riunioni supportate
<a name="BKMK_Conferencing"> </a>

In questa tabella sono confrontate le funzionalità di riunioni disponibili per gli utenti del client Skype for business, Skype for Business Web App, Skype Meetings app e Lync Web App. Lync Web App è elencato per le funzionalità di confronto delle caratteristiche: un utente può scaricare e usare Lync Web App solo se la riunione è stata ospitata su un server Lync 2013.

| Caratteristica/funzionalità | Client Skype for business 2016 o 2019 | Client Skype for business su Mac | App Riunioni Skype | Skype for Business Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Aggiungere la funzionalità audio al computer  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |
|Aggiungere la funzionalità video  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |
|Passare l'audio a un telefono per i partecipanti autenticati  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Passare l'audio a un telefono per i partecipanti all'ospite  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Visualizzazione del video in più parti (visualizzazione raccolta)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condivisione dello schermo basato su video  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (solo visualizzazione)  <br/> |||
|Utilizzare controlli di relatore nell'ambito delle riunioni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accedere all'elenco dettagliato delle riunioni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a conversazioni istantanee tra più utenti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Impostare i messaggi di messaggistica istantanea come priorità alta  <br/> |&#x2714;|||||
|Condividere il desktop (se consentito)  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |&#x2714; (richiede plug-in)  <br/> |
|Condividere un programma (se consentito)  <br/> |&#x2714;||&#x2714; (solo su Windows, richiede plug-in)  <br/> |&#x2714; (solo su Windows, richiede plug-in)  <br/> |&#x2714; (solo su Windows, richiede plug-in)  <br/> |
|Assumere il controllo del desktop o del programma condiviso di un altro utente  <br/> |&#x2714;||&#x2714; (solo &#x2776; in Windows, richiede il plug-in)  <br/> |&#x2714; (solo &#x2776; in Windows, richiede il plug-in)  <br/> |&#x2714; (solo &#x2776; in Windows, richiede il plug-in)  <br/> |
|Consentire a un altro utente di assumere il controllo del desktop o del programma condiviso  <br/> |&#x2714;|||||
|Aggiungere partecipanti anonimi (se consentito)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitare i partecipanti per nome  <br/> |&#x2714;|&#x2714;||||
|Invitare i partecipanti in base al numero di telefono  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitare i partecipanti tramite posta elettronica  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Utilizzo di riunioni audio con accesso esterno  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Avviare una riunione adesso  <br/> |&#x2714;|&#x2714;||||
|Registrare una riunione  <br/> |&#x2714;|||||
|Aggiungere e scaricare allegati  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Aggiungere e presentare file di Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Passare ai file di Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere e modificare le note della riunione di OneNote  <br/> |&#x2714;||Modifica solo (non aggiungere)  <br/> |Modifica solo (non aggiungere)  <br/> |Modifica solo (non aggiungere)  <br/> |
|Utilizzare una lavagna  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Effettuare sondaggi  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Caricare file da condividere con altri utenti  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Pianificare una riunione o una conferenza  <br/> |Outlook o Skype for Business Web Scheduler  <br/> |Outlook o Skype for Business Web Scheduler  <br/> |Utilità di pianificazione Web di Skype for business  <br/> |Utilità di pianificazione Web di Skype for business  <br/> |Utilità di pianificazione Web di Skype for business  <br/> |
|Q &amp; un Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Disattiva video partecipante  <br/> |&#x2714;|||||
|Disattiva messaggistica istantanea riunione  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Disattiva gruppo di destinatari  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Rendere tutti un partecipante  <br/> |&#x2714;|||||
|Produrre Skype meeting broadcast  <br/> |&#x2714;|||||
   
 &#x2776; i partecipanti non possono controllare i desktop condivisi da Skype for business per Mac, Lync per Mac 2011 o Communicator per gli utenti di Mac 2011. Questo non funzionerà anche per Skype for Business Web App su Max OSX.
  
 &#x2777; per Skype for business online, questa funzionalità richiede servizi di conferenza PSTN Microsoft, messaggistica unificata di Exchange o un provider di audioconferenza di terze parti.
  
 &#x2778; il client Lync per Mac 2011 non è in grado di visualizzare le presentazioni di Microsoft Office 2013 PowerPoint quando sono state condivise in una conferenza da Skype for Business Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problemi noti e risoluzione dei problemi
<a name="BKMK_Conferencing"> </a>

Per gli utenti finali, la [Guida in linea](https://aka.ms/smahelp) per queste app è prontamente disponibile. I professionisti IT devono essere a conoscenza dei problemi seguenti:
  
- Se l'utente si trova in una rete non configurata per soddisfare i [requisiti di rete](meetings-clients.md#Network), molte funzionalità dell'app potrebbero funzionare o meno e potrebbero non essere in grado di connettersi alla riunione.
    
- Alcuni utenti possono disporre di computer amministrati dall'organizzazione con autorizzazioni disabilitate per installare le app. per gli utenti, l'app non è un'opzione, ma gli utenti di [Smart Phone](https://products.office.com/skype-for-business/download-app?tab=tabs-1) e [Tablet](https://products.office.com/skype-for-business/download-app?tab=tabs-2) potrebbero essere in grado di installare client mobili economici che possono utilizzare per partecipare alle riunioni.
    
    Altri problemi di installazione sono descritti anche negli [argomenti della Guida](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Gli utenti possono visualizzare un avviso del firewall per la prima volta che eseguono l'app riunioni. Potrebbe essere richiesto di aprire le porte per ottimizzare l'esperienza e potrebbe essere necessario disporre di privilegi di amministratore per il computer che potrebbe non avere. L'app deve comunque funzionare e l'utente può rifiutare in modo sicuro l'apertura delle porte richieste. 
    
- È necessario che [ActiveX sia abilitato senza filtraggio](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) in Internet Explorer, anche se IE non è il browser predefinito. In Skype for Business Web App, un controllo ActiveX, ovvero un modulo di piccole dimensioni che aggiunge altre funzionalità a un'app Web o a un altro programma, è necessario per la condivisione di audio, video e schermo.
    
- Affinché le funzionalità di Skype for Business Web App funzionino correttamente, è necessario consentire al browser di [salvare i cookie](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) nel computer o nel dispositivo.
    
- Potrebbe essere necessario abilitare il supporto [JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) nel browser per alcune caratteristiche di Skype for Business Web App per funzionare come previsto.
    
### <a name="aes-support"></a>Supporto AES 

A partire da Skype for Business Server 2015 CU5, AES non è supportato per ASP.NET 4,6 e potrebbe non essere possibile avviare l'app riunioni Skype. I [requisiti di crittografia a causa di ASP .net 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) hanno maggiori dettagli.
  
## <a name="see-also"></a>Vedere anche
<a name="BKMK_Conferencing"> </a>

[Distribuire i client scaricabili Web in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Piattaforme supportate per l'app incontri Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
