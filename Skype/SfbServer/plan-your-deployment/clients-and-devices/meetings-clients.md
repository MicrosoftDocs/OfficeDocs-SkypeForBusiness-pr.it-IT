---
title: Pianificare i client delle riunioni (app Web e riunioni)
ms.author: v-lanac
author: lanachin
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
description: "Riepilogo: i professionisti IT devono rivedere i requisiti di supporto per l'app Skype for Business Web App e riunioni Skype durante la pianificazione di Skype for Business Server. Questo articolo non è destinato agli utenti di queste app."
ms.openlocfilehash: 126d8ffc71a2ff1a0bcbf26c744301736d2b47b2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803556"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Pianificare i client delle riunioni (app Web e riunioni)
 
**Riepilogo:** I professionisti IT devono rivedere i requisiti di supporto per l'app Skype for Business Web App e riunioni Skype durante la pianificazione per Skype for Business Server. Questo articolo non è destinato agli utenti di queste app.
  
Dopo aver implementato Skype for Business Server, gli utenti dell'organizzazione avranno presumibilmente il client Skype for business installato come parte del processo di distribuzione. 
  
In seguito, gli utenti possono creare riunioni e invitare utenti esterni all'organizzazione e gli invitati alla riunione potrebbero non avere una versione del client Skype for business. Quando gli utenti fanno clic sull'URL dell'invito alla riunione, viene rilevata la mancanza di un client e viene richiesto l'invito senza un client Skype for business per scaricare e installare un client leggero e solo riunioni in modo che possano partecipare alla riunione.
  
> [!NOTE]
> L'app Skype for Business Web App e le riunioni Skype sono disponibili solo quando si prova ad accedere a una riunione senza avere Skype for business. La guida dell'utente per queste app [https://aka.ms/smahelp](https://aka.ms/smahelp)è at. 
  
> [!NOTE]
> Non è possibile pre-installare l'app Skype for Business Web App o riunioni Skype, ma gli utenti di [Smart Phone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) e [Tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) possono installare client mobili poco costosi che possono usare per partecipare alle riunioni.
  
Per impostazione predefinita, il server che ospita la riunione indirizza l'utente a scaricare e installare Skype for Business Web App per partecipare alla riunione. L'app web Skype for business è archiviata nel server front-end e viene inviata al partecipante alla riunione. 
  
Per Skype for Business Server, l'app riunioni Skype (su Windows) e Skype for business per Mac (su Mac) sono disponibili come sostituzioni per Skype for Business Web App che iniziano con CU5, ma le app di sostituzione richiedono la configurazione aggiuntiva descritta in [abilitare l'app riunioni Skype per sostituire Skype for Business Web App (facoltativo)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Se le app riunioni Skype e Skype for business per Mac sono abilitate, gli utenti scaricheranno la versione più recente delle app dalla rete di distribuzione dei contenuti di Office 365 invece che da Skype for Business Server. Per Skype for Business Server 2019, l'uso dell'app riunioni Skype e Skype for business per Mac è l'unica opzione.
  
L'app riunioni Skype offre un'esperienza di browser semplificata per il download e l'installazione dell'app e l'Unione delle riunioni, incluso il join con un clic per gli utenti di Internet Explorer. L'app riunioni Skype offre anche numerosi miglioramenti rispetto all'app web Skype for business per l'affidabilità e l'esperienza di riunione. 
  
> [!NOTE]
> A partire da Skype for Business Server 2015 CU5 o versioni successive, le riunioni svolte con Skype for business online non invieranno più un utente senza client Skype for Business Web App, ma verranno inviate all'app riunioni Skype (in Windows) o Skype for business per Mac (per Mac). A partire da Skype for Business Server 2015 CU5 o versioni successive, se si [Abilita l'app riunioni Skype per sostituire Skype for Business Web App (facoltativo)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), gli utenti non client saranno inviati all'app riunioni Skype o Skype for business per Mac invece di Skype for Business Web App. 
  
## <a name="software-requirements"></a>Requisiti software
<a name="OS-Browser"> </a>

Per usare l'app web Skype for business, un utente deve avere una delle seguenti combinazioni di browser e sistemi operativi supportati. 
  
**Sistema operativo e supporto per i browser minimi per Skype for Business Web App**

| Sistema operativo | Bordo | 32-e 64 bit Internet Explorer 11 o versioni successive | 32-e 64 bit Internet Explorer 10 o versioni successive | 32-e 64 bit Internet Explorer 9 o versioni successive | 32-e 64 bit versione di Safari 6.2.8-11. X | 32 e 64 bit di Chrome 18. X o versioni successive |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Sì  <br/> |Sì  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sì &#x2778; <br/> |
|Windows 8,1 &#x2776; <br/> |N/D  <br/> |Sì  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Sì &#x2778; <br/> |
|&#x2776; di Windows 8 (basato su Intel) <br/> |N/D  <br/> |N/D  <br/> |Sì  <br/> |N/D <br/> |N/D  <br/> |Sì &#x2778; <br/> |
|Windows 7 con SP1 &#x2777; <br/> |N/D  <br/> |No  <br/> |No  <br/> |No  <br/> |N/D <br/>|Sì &#x2778; <br/> |
|Windows Server 2008 R2 con SP1 &#x2777; <br/> |N/D  <br/> |Sì  <br/> |Sì  <br/> |Sì  <br/> |N/D <br/>|Sì &#x2778; <br/> |
|Mac OS 10,8 e versioni successive (basato su Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Sì  <br/> |Sì <br/> |
   
&#x2776; il plug-in del browser per Skype for Business Web App richiede un plug-in di condivisione specifico per usare la voce, il video, la condivisione e la visualizzazione basati su computer della condivisione dello schermo in corso e altre caratteristiche. A un partecipante alla riunione viene assegnata l'opzione di installare il plug-in di condivisione quando partecipano alla riunione o quando avviano una di queste funzionalità. In Windows 8 e Windows 8,1 il plug-in di condivisione può essere installato solo se si sta usando Internet Explorer 10 o Internet Explorer 11 per il desktop. Queste funzionalità non sono disponibili con le versioni non desktop di Internet Explorer 10 e 11. Tieni presente che Firefox e Safari versione 12,0 e successive non sono più supportati.
  
&#x2777; nei sistemi operativi Windows 7, Windows Server 2008 R2 e Macintosh supportati, tutte le funzionalità sono disponibili, tra cui la voce, il video, la visualizzazione delle applicazioni, la condivisione delle applicazioni, la visualizzazione desktop e la condivisione del desktop. Per usare queste funzionalità, è necessario installare un plug-in quando richiesto. Tieni presente che Mac OS X versione 10,7 non è più supportato.
  
&#x2778; l'accesso all'app Web da Chrome in Windows lancerà un piccolo programma che carica l'app Web in un frame di Internet Explorer incorporato. Questo programma richiede che una delle versioni supportate di Internet Explorer sia installata affinché l'app Web venga caricata correttamente.
  
> [!NOTE]
> Gli utenti di Office 365 possono usare Internet Explorer 10 o versioni successive con Skype for business. 
  
### <a name="skype-meetings-app"></a>App riunioni Skype

L'app riunioni Skype viene eseguita come app nei computer che usano Windows 10, Windows 8,1, Windows 8, Windows 7, con 32 e 64-bit Internet Explorer 11 o versione successiva installata. 
  
Per altre dipendenze, vedere [piattaforme supportate per l'app riunioni Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype for business per Mac

Skype for business per Mac viene eseguito su computer che usano macOS versione 10,8 o successiva. 

## <a name="hardware-requirements"></a>Requisiti hardware
<a name="OS-Browser"> </a>

I requisiti hardware per i computer sono determinati dal sistema operativo e dal browser. Le funzionalità vocali e telefoniche richiedono un microfono e altoparlanti, auricolare con microfono o un dispositivo equivalente compatibile con il computer. Le caratteristiche video richiedono un dispositivo video compatibile con il computer. Per informazioni dettagliate sul supporto hardware video e la qualità video prevista, Vedi [risoluzioni video client Skype for business](video-resolutions.md).
  
## <a name="network-requirements"></a>Requisiti di rete
<a name="Network"> </a>

Se un utente dell'app Skype for Business Web App o delle riunioni Skype incontra problemi di connessione, è probabile che l'infrastruttura di rete dell'organizzazione non sia configurata per supportare Office 365 come descritto in [URL e intervalli di indirizzi IP di office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). In questo caso, se la riunione è stata creata da un utente di Skype for business online o Skype for Business Server. 
  
Se l'utente si trova in una rete non configurata come descritto, molte caratteristiche dell'app potrebbero non funzionare e potrebbero non essere in grado di connettersi alla riunione.
  
## <a name="supported-meetings-features"></a>Caratteristiche delle riunioni supportate
<a name="BKMK_Conferencing"> </a>

Questa tabella confronta le caratteristiche delle riunioni disponibili per gli utenti di Skype for Business client, Skype for Business Web App, app riunioni Skype e Lync Web App. Lync Web App è elencata per scopi di confronto delle caratteristiche: un utente dovrebbe scaricare e usare Lync Web App solo se la riunione è stata ospitata in un server Lync 2013.

| Funzionalità/funzionalità | Client Skype for business 2016 o 2019 | Client Skype for business per Mac | App riunioni Skype | App web Skype for business | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Aggiungere l'audio del computer  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede il plug-in)  <br/> |&#x2714; (richiede il plug-in)  <br/> |&#x2714; (richiede il plug-in)  <br/> |
|Aggiungere un video  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede il plug-in)  <br/> |&#x2714; (richiede il plug-in)  <br/> |&#x2714; (richiede il plug-in)  <br/> |
|Passare l'audio a un telefono per i partecipanti autenticati  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Passare l'audio a un telefono per i partecipanti Guest  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Visualizzare il video in più parti (visualizzazione raccolta)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Condivisione dello schermo basata su video  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (solo visualizzazione)  <br/> |||
|Usare i controlli relatore in-meeting  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accedere a un elenco dettagliato delle riunioni  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partecipare a un messaggio istantaneo a più parti  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Impostare messaggi di messaggistica istantanea come priorità alta  <br/> |&#x2714;|||||
|Condividere il desktop (se abilitato)  <br/> |&#x2714;|&#x2714;|&#x2714; (richiede il plug-in)  <br/> |&#x2714; (richiede il plug-in)  <br/> |&#x2714; (richiede il plug-in)  <br/> |
|Condividere un programma (se abilitato)  <br/> |&#x2714;||&#x2714; (solo in Windows; richiede il plug-in)  <br/> |&#x2714; (solo in Windows; richiede il plug-in)  <br/> |&#x2714; (solo in Windows; richiede il plug-in)  <br/> |
|Assumere il controllo del desktop o del programma condiviso di un altro utente  <br/> |&#x2714;||&#x2714; (&#x2776; solo in Windows; richiede il plug-in)  <br/> |&#x2714; (&#x2776; solo in Windows; richiede il plug-in)  <br/> |&#x2714; (&#x2776; solo in Windows; richiede il plug-in)  <br/> |
|Consentire a un altro utente di assumere il controllo del desktop o del programma condiviso  <br/> |&#x2714;|||||
|Aggiungere partecipanti anonimi (se abilitati)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitare i partecipanti per nome  <br/> |&#x2714;|&#x2714;||||
|Invitare i partecipanti per numero di telefono  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Invitare i partecipanti tramite posta elettronica  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Usare le riunioni audio con accesso esterno  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Avviare una riunione meeting Now  <br/> |&#x2714;|&#x2714;||||
|Registrare una riunione  <br/> |&#x2714;|||||
|Aggiungere e scaricare allegati  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Aggiungere e presentare file di Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Spostarsi tra i file di Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Aggiungere e modificare le note della riunione di OneNote  <br/> |&#x2714;||Modifica solo (non aggiungere)  <br/> |Modifica solo (non aggiungere)  <br/> |Modifica solo (non aggiungere)  <br/> |
|Usare una lavagna  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Eseguire sondaggi  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Caricare file da condividere con altri  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Pianificare una riunione o una conferenza  <br/> |Outlook o Skype for Business Web Scheduler  <br/> |Outlook o Skype for Business Web Scheduler  <br/> |Programmatore web Skype for business  <br/> |Programmatore web Skype for business  <br/> |Programmatore web Skype for business  <br/> |
|Responsabile&amp;di Q A  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Disabilitare il video dei partecipanti  <br/> |&#x2714;|||||
|Disabilitare la messaggistica istantanea della riunione  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Disattivare l'audio del pubblico  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Rendere tutti partecipanti un partecipante  <br/> |&#x2714;|||||
|Produrre Skype meeting broadcast  <br/> |&#x2714;|||||
   
 &#x2776; i partecipanti non possono controllare i desktop condivisi da Skype for business per Mac, Lync per Mac 2011 o Communicator per Mac 2011 utenti. Questo non funzionerà anche per Skype for Business Web App su Max OSX.
  
 &#x2777; per Skype for business online, questa funzionalità richiede conferenze PSTN Microsoft, messaggistica unificata di Exchange o un provider di servizi di audioconferenza di terze parti.
  
 &#x2778; il client Lync per Mac 2011 non può visualizzare le presentazioni di PowerPoint di Microsoft Office 2013 quando è stato condiviso in una conferenza da Skype for Business Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problemi noti e risoluzione dei problemi
<a name="BKMK_Conferencing"> </a>

Per gli utenti finali, la [Guida online](https://aka.ms/smahelp) per queste app è prontamente disponibile. I professionisti IT devono tenere presente i problemi seguenti:
  
- Se l'utente si trova in una rete non configurata in modo da soddisfare i [requisiti di rete](meetings-clients.md#Network), molte delle funzionalità dell'app potrebbero non funzionare e potrebbero non essere in grado di connettersi alla riunione.
    
- Alcuni utenti possono avere computer gestiti da una società con autorizzazioni disabilitate per installare le app. per gli utenti, nessuna delle due app è un'opzione, ma gli utenti di [Smart Phone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) e [Tablet](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) potrebbero essere in grado di installare client mobili economici che possono usare per partecipare alle riunioni.
    
    Altri problemi di installazione sono descritti anche negli [argomenti della Guida](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Gli utenti possono visualizzare un avviso del firewall la prima volta che eseguono l'app riunioni. Potrebbe essere richiesto di aprire le porte per ottimizzare l'esperienza e questo potrebbe richiedere privilegi di amministratore nel computer che potrebbe non avere. L'app deve comunque funzionare e l'utente può rifiutare in modo sicuro l'apertura delle porte richieste. 
    
- È necessario avere [ActiveX abilitato senza filtrare](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) in Internet Explorer, anche se IE non è il browser predefinito. In Skype for Business Web App, un controllo ActiveX, un piccolo modulo che aggiunge funzionalità aggiuntive a un'app Web o a un altro programma, è necessario per la condivisione di audio, video e schermo.
    
- Per alcune funzionalità di Skype for Business Web App in modo che funzioni correttamente, devi consentire al browser di [salvare i cookie](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) nel computer o nel dispositivo.
    
- Potrebbe essere necessario [attivare il supporto JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) nel browser per alcune funzionalità di Skype for Business Web App in modo che funzionino come previsto.
    
### <a name="aes-support"></a>Supporto AES 

A partire da Skype for Business Server 2015 CU5, AES non è supportato per ASP.NET 4,6 e potrebbe non essere possibile avviare l'app riunioni Skype. I [requisiti crittografici a causa di ASP .net 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) sono più dettagli.
  
## <a name="see-also"></a>Vedere anche
<a name="BKMK_Conferencing"> </a>

[Distribuire client scaricabili Web in Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Piattaforme supportate per l'app riunioni Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
