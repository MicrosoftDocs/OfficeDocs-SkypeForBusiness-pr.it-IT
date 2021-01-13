---
title: Pianificare i client e i dispositivi
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/20/2018
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
ms.assetid: 95f0852e-391d-4345-985f-0a2da50491fa
description: 'Riepilogo: revisione dei client e delle app supportate per Skype for business.'
ms.openlocfilehash: 1c88786680699c81c9dd06dc8156bff333ae98ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802756"
---
# <a name="plan-for-clients-and-devices"></a>Pianificare i client e i dispositivi

**Riepilogo:** Revisione dei client e delle app supportate per Skype for business.

La forza lavoro di oggi è costantemente in movimento. Gli impiegati devono comunicare e collaborare se si lavora dall'ufficio aziendale, nelle sedi regionali, negli uffici domestici o in viaggio. Skype for Business Server supporta queste esigenze tramite una raccolta di interfacce client che è possibile distribuire agli utenti dell'organizzazione. La pianificazione premurosa garantisce che i dipendenti possano ottenere ciò di cui hanno bisogno e che Skype for business sia disponibile ovunque si trovino.

## <a name="available-clients"></a>Client disponibili

Skype for Business Server supporta diversi tipi di client, tra cui il software client installato nel computer, i client basati sul Web e i client per i dispositivi mobili. I client primari sono stati introdotti in questa sezione, per un elenco dettagliato di tutti i client supportati, vedere confronto delle caratteristiche dei client desktop per il confronto delle funzionalità di [Skype for Business server 2015](desktop-feature-comparison.md) o [desktop client per Skype for Business Server 2019](../../../SfBServer2019/plan/feature-comparison.md). Se in precedenza è stata utilizzata una combinazione di client Lync, tenere presente che esistono [client legacy](clients-and-devices.md#Legacy) non supportati che non sono compatibili con Skype for Business Server 2019. Gli aggiornamenti hanno luogo regolarmente, quindi controllare periodicamente questo argomento per le informazioni più recenti sul client.

### <a name="skype-for-business-2019"></a>Skype for business (2019)

Skype for business (2019) è il client completo consigliato per Skype for Business Server 2015 e 2019. Per una descrizione delle nuove funzionalità, vedere [seguire gli aggiornamenti più recenti in Skype for business](https://support.office.com/article/What-s-new-in-Skype-for-Business-2016-cece9f93-add1-4d93-9a38-56cc598e5781) . Il supporto per le funzionalità client è dettagliato nel [confronto delle funzionalità client desktop per Skype for business](desktop-feature-comparison.md)e la documentazione dell'utente è relativa alla [Guida di Skype for business](https://support.office.com/Skype-for-business). Questo client è incluso quando un utente installa Microsoft 365 o Office 365.

È disponibile anche un client di base gratuito che supporta meno funzionalità. Entrambe le versioni sono disponibili per il download nel [download di Skype for business in tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3). Le differenze tra i client completi e di base sono descritte nella sezione [limitazioni client di base](desktop-feature-comparison.md#Full-Basic) .

### <a name="skype-for-business-2016"></a>Skype for Business 2016

Skype for business 2016 è un client full-optional per Skype for Business Server 2015 o 2019. Per una descrizione delle nuove funzionalità, vedere [What ' s New in Skype for Business 2016](https://support.office.com/article/What-s-new-in-Skype-for-Business-2016-cece9f93-add1-4d93-9a38-56cc598e5781) . Il supporto per le funzionalità client è dettagliato nel [confronto delle funzionalità client desktop per Skype for business](desktop-feature-comparison.md)e la documentazione dell'utente è relativa alla [Guida di Skype for business](https://support.office.com/Skype-for-business). Questo client è incluso quando un utente installa Office 365.

È disponibile anche un client di base gratuito che supporta meno funzionalità. Entrambe le versioni sono disponibili per il download nel [download di Skype for business in tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3). Le differenze tra i client completi e di base sono descritte nella sezione [limitazioni client di base](desktop-feature-comparison.md#Full-Basic) .

### <a name="skype-for-business-2015"></a>Skype for Business 2015

Skype for business 2015 è un client full-optional per Skype for Business Server 2015 o 2019. L'interfaccia utente di Skype for business è stata completamente riprogettata e include nuove funzionalità integrate, ad esempio Monitor chiamata, integrazione directory Skype, emoticon e altro ancora. Per un riepilogo delle modifiche, vedere [Lync è ora Skype for business, vedere What ' s New](https://support.office.com/en-in/article/aba02d7e-c801-4a82-bccd-e7207240f612). Il supporto per le funzionalità client è dettagliato nel [confronto delle funzionalità client desktop per Skype for business](desktop-feature-comparison.md)e la documentazione dell'utente è relativa alla [Guida di Skype for business](https://support.office.com/Skype-for-business). Questo client è incluso quando un utente installa Office 365.

### <a name="skype-for-business-on-mac"></a>Skype for Business nel Mac

Il client [Skype for business su Mac](https://www.microsoft.com/download/details.aspx?id=54108) è disponibile per il download. Consultare [i requisiti client Skype for business su Mac](mac-requirements.md) per esaminare i prerequisiti.

### <a name="skype-for-business-for-mobile-devices"></a>Skype for business per dispositivi mobili

I client sono disponibili per Windows Phone, iPhone/iPad e Android. Gli utenti possono [scaricarli su Skype for business in tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3). Il supporto delle funzionalità per questi client è dettagliato nel [confronto delle funzionalità dei client per dispositivi mobili per Skype for business](mobile-feature-comparison.md).

> [!NOTE]
> Il supporto di MCX (Mobility Service) per i client mobili legacy non è più disponibile in Skype for Business Server 2019. Tutti i client per dispositivi mobili Skype for business corrente utilizzano già Unified Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che utilizzano MCX dovranno eseguire l'aggiornamento a un client corrente.

### <a name="online-meeting-add-in-for-skype-for-business"></a>Componente aggiuntivo per riunioni online per Skype for business

Il componente aggiuntivo per riunioni online per Skype for business supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Microsoft Outlook su Windows. Il componente aggiuntivo per riunioni online per Skype for business software si installa automaticamente con Skype for business.

### <a name="skype-for-business-web-app-and-skype-meetings-app"></a>App Skype for Business Web App e Skype Meetings

Se Skype for business non è installato nel computer di un utente e l'utente fa clic su un collegamento a una riunione in una convocazione di riunione su un computer Windows, l'app Skype meetings o Skype for Business Web App verrà installata e aperta.  Skype Meetings app è il client preferito per i partecipanti all'esterno dell'organizzazione. (Si noti che su un Mac, Skype for business su Mac verrà installato e aperto). Per i requisiti per l'utilizzo di questi client, vedere [Plan for meetings clients (Web App and Meetings app)](meetings-clients.md) .


### <a name="skype-for-business-web-scheduler"></a>Utilità di pianificazione Web di Skype for business

[Skype for Business Web Scheduler](https://sched.lync.com) è uno strumento di gestione e pianificazione delle riunioni basato sul Web per gli utenti di Skype for business online che non dispongono dell'accesso a Microsoft Outlook o che si trovano in un sistema operativo non basato su Windows. Con Skype for Business Web Scheduler, gli utenti possono creare nuove riunioni, modificare le riunioni esistenti e inviare inviti usando il programma di posta elettronica preferito. La [documentazione](https://support.office.com/article/Skype-for-Business-Web-Scheduler-3b24a211-6470-4a2d-81b7-22d9399d0fec?ui=en-US&amp;rs=en-US&amp;ad=US)  di Skype for Business Web Scheduler fornisce ulteriori dettagli.

### <a name="vdi-plugins"></a>Plug-in VDI

Un ambiente VDI (Virtual Desktop Infrastructure) viene utilizzato in alcune organizzazioni in cui i problemi di sicurezza e conformità sono particolarmente sensibili. L'utilizzo di Skype for business con audio e video completi su una connessione di questo tipo richiede pesanti carichi di elaborazione audio e video sul client ospitato su un desktop virtuale. È disponibile un ulteriore software plug-in VDI che consente di scaricare l'elaborazione nel computer locale dell'utente finale e di ridurre il carico sul desktop virtuale. Per informazioni dettagliate sull'utilizzo di questi plug-in, vedere [Plan for Skype for business in VDI Environments](vdi-environments.md) .

### <a name="microsoft-teams-rooms"></a>Microsoft Teams Rooms

Microsoft teams Rooms è la soluzione di conferenza più recente di Microsoft che utilizza un'interfaccia familiare e può essere facilmente distribuita e gestita, sfruttando gli strumenti esistenti come i pannelli LCD per semplificare l'installazione. Microsoft teams Rooms utilizza un'app UWP costruita appositamente in esecuzione su Surface Pro 4 o Surface Pro in una modalità console (dopo la distribuzione dell'app UWP è l'unica applicazione che verrà eseguita sul dispositivo) e richiederà un account dispositivo personalizzato per l'implementazione. Il software viene aggiornato tramite Windows Store e Windows Update. https://aka.ms/MTRDocsPer informazioni dettagliate sull'utilizzo di queste console sala nella distribuzione, vedere. 

### <a name="skype-for-business-on-surface-hub"></a>Skype for business su Surface Hub

Microsoft Surface Hub è un dispositivo di produttività all-in-One che è stato progettato per il brainstorming, la collaborazione e le presentazioni. Ha una propria iterazione del client Skype for business, documentato nella [Guida di amministrazione di Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).

## <a name="choosing-your-organizations-preferred-client"></a>Scelta del client preferito dell'organizzazione
<a name="BK_client_choose"> </a>

Se nell'organizzazione sono state acquistate le licenze appropriate, scegliere il client completo, altrimenti scegliere il client di base.

Gli utenti possono installare il client per se stessi da [scaricare Skype for business su tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3). Il client viene installato anche quando gli utenti installino Microsoft 365 o Office 365 su Windows. Se alcuni utenti dispongono di Mac, gli utenti avranno un set di caratteristiche diverso, come descritto nelle sezioni precedenti.

Alcune funzionalità disponibili con Skype for Business Server 2015 non sono disponibili in Skype for business online o in Skype for Business Server 2019, vedere [online o Hybrid account utente limitazioni per 2015](desktop-feature-comparison.md#Online-Hybrid) o [online o ibrida limitazioni dell'account utente per 2019](desktop-feature-comparison.md#Online-Hybrid) per specifiche. Gli amministratori di Skype for business online possono fare riferimento alla [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) per informazioni sui diversi piani disponibili.

 Prima di eseguire la distribuzione o l'aggiornamento a Skype for business, verificare quali client sono già in uso nell'organizzazione. Utilizzare il [confronto delle funzionalità client desktop per Skype for business](desktop-feature-comparison.md) per comprendere l'impatto del supporto delle caratteristiche su tali client. In questo modo è possibile comunicare le modifiche apportate agli utenti, passare al processo di implementazione e comprendere appieno i vantaggi dell'aggiornamento al client più recente.

## <a name="ways-to-deploy-the-client-to-your-users"></a>Modalità di distribuzione del client agli utenti
<a name="BK_User_Deploy"> </a>

I programmi di installazione client sono disponibili per i programmi di installazione di tipo MSI e a portata di clic. La strategia di Sustaining client Skype for business può influire sulle scelte, pertanto è necessario comprendere i seguenti punti:

- In generale, Skype for business non aggiunge nuove funzionalità ai client rilasciati in precedenza

- In generale, Skype for business non pianifica di inviare nuove funzionalità nel MSI di Skype for business dopo la sua versione iniziale. I miglioramenti di MSI tra i rilasci saranno principalmente qualità/sicurezza in natura.

- L'esperienza più recente e la più grande client Skype for business si troverà nel programma di installazione a portata di clic su Skype for business 2019.

È possibile eseguire una distribuzione personalizzata del client come descritto in [Customize Windows Client Installation in Skype for Business Server](../../deploy/deploy-clients/customize-windows-client-installation.md). I metodi di installazione sono descritti in maggiore dettaglio in [deploy clients for Skype for Business Server](../../deploy/deploy-clients/deploy-clients.md)

### <a name="click-to-run"></a>A portata di clic

A portata di clic è presente una tecnologia di Microsoft streaming e di virtualizzazione che è possibile utilizzare per installare e aggiornare i prodotti di Office, tra cui Skype for business. Queste funzionalità di flusso e virtualizzazione si basano sulle tecnologie di Microsoft Application Virtualization (App-V). A portata di clic è possibile utilizzare i vantaggi seguenti:

- Installazione in streaming di una famiglia di prodotti Office che risulta in tempi di installazione brevi

- Aggiornamenti e patch integrati

- Occupa meno spazio su disco

- Licenze base utente: 5 installazioni per utente

- Personalizzabile tramite editor XML per l'installazione di programmi indipendenti

È possibile utilizzare lo strumento di [distribuzione di Office](https://www.microsoft.com/download/details.aspx?id=49117) per questo tipo di programma di installazione.

Sia le versioni di base che quelle client complete (con scelta tra le versioni a 32 e 64 bit) sono disponibili utilizzando un programma di installazione a portata di clic, gli utenti possono scaricare scaricando [Skype for business su tutti i dispositivi](https://products.office.com/skype-for-business/download-app?tab=tabs-3).

### <a name="msi"></a>MSI

MSI è un metodo di installazione più tradizionale, utilizzato nei client Skype for business 2015 e 2016. Consente di installare manualmente gli aggiornamenti e le patch, utilizzare contratti multilicenza e attivazione ed è personalizzabile tramite lo [strumento di personalizzazione di Office](https://www.microsoft.com/download/details.aspx?id=49030). È possibile distribuire i client applicando criteri di gruppo tramite Microsoft endpoint Configuration Manager o utilizzando uno strumento di terze parti.



## <a name="legacy-clients"></a>Client legacy
<a name="Legacy"> </a>

Skype for Business Server 2019 e Skype for business online supportano i seguenti client rilasciati in precedenza: Skype for business 2016, Skype for business 2015, Lync 2013.

Skype for Business Server 2015 supporta i client rilasciati in precedenza seguenti: Lync 2013, Lync 2010, Lync 2010 mobile, Lync Phone Edition e Lync 2010 Attendant. Per informazioni su questi client se utilizzati con altri server, vedere le [tabelle di confronto dei client per Lync server 2013](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx) e le [tabelle di confronto dei client per Lync Server 2010](https://technet.microsoft.com/library/gg425836%28v=ocs.14%29.aspx).


## <a name="client-system-requirements"></a>Requisiti di sistema client
<a name="Legacy"> </a>

Vedere gli articoli seguenti per comprendere le funzionalità supportate, le piattaforme, i sistemi operativi, i browser e l'integrazione necessari per i client Skype for business.

- [Pianificare l'esperienza client di Skype for business per gli utenti](user-experience.md)

- [Confronto delle funzionalità dei client desktop per Skype for business](desktop-feature-comparison.md)

- [Confronto delle funzionalità dei client per dispositivi mobili per Skype for business](mobile-feature-comparison.md)

- [Requisiti del client Windows e supporto software](windows-requirements.md)

- [Compatibilità di Skype for business con le app di Office](compatibility-with-office.md)

- [Risoluzione video client Skype for business](video-resolutions.md)

- [Pianificare i client di riunioni (app per le riunioni e le app Web)](meetings-clients.md)

- [Requisiti di sistema per Skype for business per Windows Phone](requirements-for-windows-phone.md)

- [Requisiti client Skype for business su Mac](mac-requirements.md)

- [Pianificare le sale di Microsoft Teams](skype-room-systems-v2-0.md)

- [Pianificare Skype for business in ambienti VDI](vdi-environments.md)

- Fare riferimento ai [requisiti di sistema](https://products.office.com/office-system-requirements) per l'hardware necessario.


## <a name="see-also"></a>Vedere anche

[Aggiornamenti più recenti per le versioni di Skype for business che utilizzano Windows Installer (MSI)](../../sfb-client-updates.md)
