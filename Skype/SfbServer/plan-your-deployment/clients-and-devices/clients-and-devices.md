---
title: Pianificare client e dispositivi
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 95f0852e-391d-4345-985f-0a2da50491fa
description: 'Riepilogo: esaminare i client e le app supportati per Skype for Business.'
ms.openlocfilehash: 5bf793c052d665c579294529b78a5fd69c81be3c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598760"
---
# <a name="plan-for-clients-and-devices"></a>Pianificare client e dispositivi

**Riepilogo:** Esaminare i client e le app supportati per Skype for Business.

La forza lavoro di oggi è costantemente in movimento. I dipendenti devono comunicare e collaborare sia che si lavori dall'ufficio aziendale, nelle sedi regionali, negli uffici nazionali o in viaggio. Skype for Business Server queste esigenze tramite una raccolta di interfacce client che è possibile distribuire agli utenti dell'organizzazione. Una pianificazione attenta garantisce ai dipendenti di ottenere ciò di cui hanno bisogno e Skype for Business che siano disponibili ovunque si trovano.

## <a name="available-clients"></a>Client disponibili

Skype for Business Server supporta diversi tipi di client, tra cui software client installato dal computer, client basati sul Web e client per dispositivi mobili. I client principali sono stati introdotti in questa sezione, per un elenco dettagliato di tutti i client supportati, vedere Confronto delle funzionalità client desktop per [Skype for Business Server 2015](desktop-feature-comparison.md) o Confronto delle funzionalità client desktop per [Skype for Business Server 2019.](../../../SfBServer2019/plan/feature-comparison.md) Se in precedenza è stata utilizzata una combinazione di client Lync, tenere presente che esistono client [legacy](clients-and-devices.md#Legacy) non supportati incompatibili con Skype for Business Server 2019. Gli aggiornamenti vengono evasi regolarmente, quindi controllare periodicamente questo argomento per le informazioni più recenti sul client.

### <a name="skype-for-business-2019"></a>Skype for Business (2019)

Skype for Business (2019) è il client completo consigliato per Skype for Business Server 2015 e 2019. Per [una descrizione delle nuove funzionalità, vedere Follow the latest updates in Skype for Business.](https://support.office.com/article/What-s-new-in-Skype-for-Business-2016-cece9f93-add1-4d93-9a38-56cc598e5781) Il supporto delle funzionalità client è descritto in dettaglio nel confronto delle funzionalità [client desktop](desktop-feature-comparison.md)per Skype for Business e la documentazione dell'utente è disponibile Skype for Business [guida.](https://support.office.com/Skype-for-business) Questo client viene incluso quando un utente installa Microsoft 365 o Office 365.

È disponibile anche un client di base gratuito che supporta meno funzionalità. Entrambe le versioni sono disponibili per il download in [Download Skype for Business su tutti i dispositivi.](https://products.office.com/skype-for-business/download-app?tab=tabs-3) Le differenze tra client completi e di base sono descritte nella [sezione Limitazioni client di](desktop-feature-comparison.md#Full-Basic) base.

### <a name="skype-for-business-2016"></a>Skype for Business 2016

Skype for Business 2016 è un client completo per Skype for Business Server 2015 o 2019. Per [una descrizione delle nuove funzionalità, Skype for Business 2016,](https://support.office.com/article/What-s-new-in-Skype-for-Business-2016-cece9f93-add1-4d93-9a38-56cc598e5781) vedere Novità di Skype for Business 2016. Il supporto delle funzionalità client è descritto in dettaglio nel confronto delle funzionalità [client desktop](desktop-feature-comparison.md)per Skype for Business e la documentazione dell'utente è disponibile Skype for Business [guida.](https://support.office.com/Skype-for-business) Questo client viene incluso quando un utente installa Office 365.

È disponibile anche un client di base gratuito che supporta meno funzionalità. Entrambe le versioni sono disponibili per il download in [Download Skype for Business su tutti i dispositivi.](https://products.office.com/skype-for-business/download-app?tab=tabs-3) Le differenze tra client completi e di base sono descritte nella [sezione Limitazioni client di](desktop-feature-comparison.md#Full-Basic) base.

### <a name="skype-for-business-2015"></a>Skype for Business 2015

Skype for Business 2015 è un client completo per Skype for Business Server 2015 o 2019. L Skype for Business'interfaccia utente è stata completamente riprogettata e include nuove funzionalità integrate, ad esempio Monitoraggio chiamate, Skype integrazione della directory, emoticon e altro ancora. Per un riepilogo delle modifiche, vedere [Lync is now Skype for Business — see what's new](https://support.office.com/en-in/article/aba02d7e-c801-4a82-bccd-e7207240f612). Il supporto delle funzionalità client è descritto in dettaglio nel confronto delle funzionalità [client desktop](desktop-feature-comparison.md)per Skype for Business e la documentazione dell'utente è disponibile Skype for Business [guida.](https://support.office.com/Skype-for-business) Questo client viene incluso quando un utente installa Office 365.

### <a name="skype-for-business-on-mac"></a>Skype for Business nel Mac

Il [Skype for Business sul](https://www.microsoft.com/download/details.aspx?id=54108) client Mac è disponibile per il download. Vedi [Skype for Business sui requisiti del client Mac](mac-requirements.md) per esaminare i prerequisiti.

### <a name="skype-for-business-for-mobile-devices"></a>Skype for Business per dispositivi mobili

I client sono disponibili Windows Phone, iPhone/iPad e Android. Gli utenti possono scaricarli in [Download Skype for Business su tutti i dispositivi.](https://products.office.com/skype-for-business/download-app?tab=tabs-3) Il supporto delle funzionalità per questi client è descritto in [Confronto delle funzionalità dei client mobili per Skype for Business](mobile-feature-comparison.md).

> [!NOTE]
> Il supporto MCX (Mobility Service) per i client mobili legacy non è più disponibile Skype for Business Server 2019. Tutti i client Skype for Business mobili utilizzano già UNIFIED Communications Web API (UCWA) per supportare la messaggistica istantanea, la presenza e i contatti. Gli utenti con client legacy che usano MCX dovranno eseguire l'aggiornamento a un client corrente.

### <a name="online-meeting-add-in-for-skype-for-business"></a>Componente aggiuntivo per riunioni online per Skype for Business

Il componente aggiuntivo per riunioni online per Skype for Business supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Microsoft Outlook in Windows. Il componente aggiuntivo per riunioni online per Skype for Business viene installato automaticamente con Skype for Business.

### <a name="skype-for-business-web-app-and-skype-meetings-app"></a>Skype for Business Web App e Skype riunioni

Se Skype for Business non è installato nel computer di un utente e l'utente fa clic su un collegamento a una riunione in una convocazione di riunione in un computer Windows, l'app riunioni di Skype o Skype for Business Web App verrà installata e aperta.  Skype L'app Riunioni è il client preferito per i partecipanti esterni all'organizzazione. Tieni presente che in un Mac, Skype for Business su Mac verrà installato e aperto. Vedere [Plan for Meetings clients (Web App and Meetings App)](meetings-clients.md) per i requisiti per l'uso di questi client.


### <a name="skype-for-business-web-scheduler"></a>Skype for Business Web Scheduler

[Skype for Business Web Scheduler](https://sched.lync.com) è uno strumento di pianificazione e gestione delle riunioni basato sul Web per gli utenti di Skype for Business Online che non hanno accesso a Microsoft Outlook o che si basano su un sistema operativo non basato su Windows. Con Skype for Business Web Scheduler, gli utenti possono creare nuove riunioni, modificare le riunioni esistenti e inviare inviti utilizzando il programma di posta elettronica preferito. Skype for Business Web Scheduler documentazione [fornisce](https://support.office.com/article/Skype-for-Business-Web-Scheduler-3b24a211-6470-4a2d-81b7-22d9399d0fec?ui=en-US&amp;rs=en-US&amp;ad=US) ulteriori dettagli.

### <a name="vdi-plugins"></a>Plug-in VDI

Un Virtual Desktop Infrastructure (VDI) viene utilizzato in alcune organizzazioni in cui i problemi di sicurezza e conformità sono particolarmente sensibili. L Skype for Business con audio e video completi su una connessione come questa richiede carichi elevati di elaborazione audio e video nel client che si ospita su un desktop virtuale. È disponibile un software aggiuntivo per i plug-in VDI che scarica l'elaborazione nel computer locale dell'utente finale e riduce il carico sul desktop virtuale. Per [informazioni dettagliate sull'uso di questi plug-in, vedere Plan for Skype for Business in VDI environments.](vdi-environments.md)

### <a name="microsoft-teams-rooms"></a>Microsoft Teams Rooms

Microsoft Teams Rooms è la soluzione di conferenza più recente di Microsoft che usa un'interfaccia familiare ed è facilmente distribuita e gestita, sfruttando attrezzature esistenti come i pannelli LCD per semplificare l'installazione. Microsoft Teams Rooms usa un'app UWP appositamente creata in esecuzione su un Surface Pro 4 o un Surface Pro in modalità console (una volta distribuita l'app UWP è l'unica app che verrà eseguita nel dispositivo) e richiede il proprio account del dispositivo nell'implementazione. Il software viene aggiornato tramite Windows Store e Windows Update. Vedi https://aka.ms/MTRDocs per informazioni dettagliate sull'uso di queste console sala nella distribuzione. 

### <a name="skype-for-business-on-surface-hub"></a>Skype for Business in Surface Hub

Microsoft Surface Hub è un dispositivo di produttività all-in-one destinato a brainstorming, collaborazione e presentazioni. Ha una propria iterazione del client Skype for Business, documentata nella guida Microsoft Surface Hub [admin guide](/surface-hub/).

## <a name="choosing-your-organizations-preferred-client"></a>Scelta del client preferito dell'organizzazione
<a name="BK_client_choose"> </a>

Se l'organizzazione ha acquistato le licenze appropriate, scegliere il client completo, altrimenti scegliere il client di base.

Gli utenti possono installare il client da [Download Skype for Business su tutti i dispositivi.](https://products.office.com/skype-for-business/download-app?tab=tabs-3) Il client viene installato anche quando gli utenti installano Microsoft 365 o Office 365 in Windows. Se alcuni utenti dispongono di Mac, questi utenti avranno un set di funzionalità diverso, come descritto nelle sezioni precedenti.

Alcune funzionalità disponibili con Skype for Business Server 2015 non sono disponibili in Skype for Business Online o Skype for Business Server 2019, vedere Limitazioni degli account utente online o ibridi per [il 2015](desktop-feature-comparison.md#Online-Hybrid) o Limitazioni degli account utente online o ibridi per [il 2019](desktop-feature-comparison.md#Online-Hybrid) per specifiche. Skype for Business Gli amministratori online potrebbero voler fare riferimento Skype for Business [Descrizione del](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description) servizio online per informazioni sui diversi piani disponibili.

 Prima di distribuire o eseguire l'aggiornamento a Skype for Business, verificare quali client sono già in uso nell'organizzazione. Utilizzare il [confronto delle funzionalità del client](desktop-feature-comparison.md) desktop per Skype for Business per comprendere l'impatto del supporto delle funzionalità su tali client. In questo modo è possibile comunicare modifiche agli utenti, implementare il processo di implementazione e comprendere appieno i vantaggi dell'aggiornamento al client più recente.

## <a name="ways-to-deploy-the-client-to-your-users"></a>Modalità di distribuzione del client agli utenti
<a name="BK_User_Deploy"> </a>

I programmi di installazione client sono disponibili sia per i programmi di installazione MSI che per i programmi di installazione dei tipi a scelta. La Skype for Business di sostegno del client può influire sulle scelte, pertanto è consigliabile comprendere i punti seguenti:

- In generale Skype for Business non aggiunge nuove funzionalità ai client rilasciati in precedenza

- In generale Skype for Business non prevede la spedizione di nuove funzionalità nel Skype for Business MSI dopo il rilascio iniziale. I miglioramenti MSI tra le versioni saranno principalmente di natura qualità/sicurezza.

- L'esperienza client Skype for Business più recente e più recente si trova nel programma di Skype for Business 2019 a clic.

È possibile eseguire una distribuzione personalizzata del client come descritto in [Customize Windows client installation in Skype for Business Server](../../deploy/deploy-clients/customize-windows-client-installation.md). I metodi di installazione sono descritti in maggiore dettaglio in [Deploy clients for Skype for Business Server](../../deploy/deploy-clients/deploy-clients.md)

### <a name="click-to-run"></a>A click-to-run

A scelta è una tecnologia di streaming e virtualizzazione Microsoft che puoi usare per installare e aggiornare i prodotti Office inclusi Skype for Business. Queste funzionalità di streaming e virtualizzazione si basano sulle tecnologie di Microsoft Application Virtualization (App-V). La a esecuzione a clic presenta i vantaggi seguenti:

- Installazione in streaming di Office suite che si traduce in breve tempo di installazione

- Aggiornamenti e patch integrata

- Occupa meno spazio su disco

- Licenze di base per gli utenti: 5 installazioni per utente

- Personalizzabile tramite l'editor XML per l'installazione di programmi indipendenti

È possibile utilizzare lo strumento di [Office per](https://www.microsoft.com/download/details.aspx?id=49117) questo tipo di programma di installazione.

Entrambe le versioni client di base e completa (con la scelta di versioni a 32 e 64 bit) sono disponibili con un programma di installazione a clic per eseguire, gli utenti possono scaricare in [Download Skype for Business](https://products.office.com/skype-for-business/download-app?tab=tabs-3)su tutti i dispositivi.

### <a name="msi"></a>MSI

MSI è un metodo di installazione più tradizionale, utilizzato nei client Skype for Business 2015 e 2016. Consente di installare manualmente aggiornamenti e patch, utilizzare contratti multilicenza e attivazione ed è personalizzabile tramite lo Office [Customization Tool.](https://www.microsoft.com/download/details.aspx?id=49030) È possibile distribuire i client applicando Criteri di gruppo, utilizzando Microsoft Endpoint Configuration Manager o uno strumento di terze parti.



## <a name="legacy-clients"></a>Client legacy
<a name="Legacy"> </a>

Skype for Business Server 2019 e Skype for Business Online supportano i seguenti client rilasciati in precedenza: Skype for Business 2016, Skype for Business 2015, Lync 2013.

Skype for Business Server 2015 supporta i seguenti client rilasciati in precedenza: Lync 2013, Lync 2010, Lync 2010 Mobile, Lync Telefono Edition e Lync 2010 Attendant. Per informazioni su questi client se utilizzati con altri server, vedere Le tabelle di confronto dei client per [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-desktop-client-comparison-tables) e Tabelle di confronto client [per Lync Server 2010.](/previous-versions/office/skype-server-2010/gg425836(v=ocs.14))


## <a name="client-system-requirements"></a>Requisiti di sistema client
<a name="Legacy"> </a>

Vedere gli articoli seguenti per comprendere le funzionalità, le piattaforme, i sistemi operativi, i browser e l'integrazione supportati per Skype for Business client.

- [Pianificare l'Skype for Business client per gli utenti](user-experience.md)

- [Confronto delle funzionalità client desktop per Skype for Business](desktop-feature-comparison.md)

- [Confronto delle funzionalità dei client mobili per Skype for Business](mobile-feature-comparison.md)

- [Windows client e supporto software](windows-requirements.md)

- [Skype for Business compatibilità con Office app](compatibility-with-office.md)

- [Skype for Business video client](video-resolutions.md)

- [Pianificare i client riunioni (App Web e app Riunioni)](meetings-clients.md)

- [Requisiti di sistema per Skype for Business per Windows Phone](requirements-for-windows-phone.md)

- [Skype for Business sui requisiti del client Mac](mac-requirements.md)

- [Pianificare la Microsoft Teams Rooms](/MicrosoftTeams/rooms/rooms-plan)

- [Pianificare la Skype for Business in ambienti VDI](vdi-environments.md)

- Fare riferimento ai [requisiti di sistema](https://products.office.com/office-system-requirements) per l'hardware necessario.


## <a name="see-also"></a>Vedere anche

[Aggiornamenti più recenti per le versioni di Skype for Business che utilizzano Windows Installer (MSI)](../../sfb-client-updates.md)