---
title: Pianificare Skype for business in ambienti VDI
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Questo argomento illustra le considerazioni sulla pianificazione per l'uso di Skype for business durante la connessione a un desktop virtuale remoto.
ms.openlocfilehash: c6bf1cea2a18920231ea4d347b8b0471cfebbba3
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36195893"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Pianificare Skype for business in ambienti VDI
 
Questo argomento illustra le considerazioni sulla pianificazione per l'uso di Skype for business durante la connessione a un desktop virtuale remoto. 
  
In alcune organizzazioni viene usato un ambiente VDI (Virtual Desktop Infrastructure) in cui i problemi di sicurezza e conformità sono particolarmente sensibili. Gli utenti eseguono il loro lavoro su un desktop virtuale con tutte le applicazioni desktop e i file che usano servizi desktop remoto o una connessione remota simile. L'uso di Skype for business con l'audio e il video completo su una connessione come quella richiede pesanti carichi di elaborazione audio e video nel client ospitato su un desktop virtuale. È disponibile un ulteriore software di plug-in VDI che consente di scaricare l'elaborazione nel computer locale dell'utente finale e di ridurre il carico sul desktop virtuale.
  
Sono disponibili tre soluzioni per il componente plug-in VDI, offerto da Microsoft, Citrix o VMWare. Per le nuove distribuzioni, Microsoft consiglia di usare la soluzione Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. Il plug-in originale di Lync VDI è ancora supportato per il resto del ciclo di vita.
  
- Il **plug-in Lync VDI** è stato sviluppato per Lync 2013 ed è compatibile con il client Lync 2013 o Skype for business 2015 eseguito su un desktop virtuale. Si tratta di un'applicazione autonoma che viene installata nel computer locale e consente l'uso di dispositivi audio e video locali con un client su un desktop virtuale. Il plug-in non richiede l'installazione di un client Skype for business nel computer locale o nel thin client, che deve eseguire sistemi operativi Windows 7, Windows 8 o Windows Server 2008. I dispositivi thin client che usano questi sistemi operativi e supportati da Microsoft includono: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 e HP t5740e. Questo plug-in è ancora supportato, ma non sono previsti aggiornamenti futuri. Per gli ambienti virtuali basati su Citrix, è consigliabile il pacchetto Citrix RealTime Optimization.
    
- **Citrix realtime Optimization Pack** si basa sul plug-in di Lync VDI e funziona con i client Lync 2013 o Skype for business 2016 su un desktop virtuale. È stato sviluppato in collaborazione da Citrix e Microsoft per migliorare il plug-in VDI originale. Può essere installato nei client con sistemi operativi Windows e non Windows (inclusi Windows 10, Mac e Linux). È costituito da due componenti: il connettore RealTime (installato sul desktop virtuale) e il motore multimediale in RealTime (installato nel computer locale dell'utente finale). Questi due componenti consentono al computer locale dell'utente di usare il client Skype for business in esecuzione sul desktop virtuale con l'elaborazione A/V spostata nel computer locale. Per gli ambienti desktop virtuali basati su Citrix, è consigliabile il Citrix RealTime Optimization Pack e è previsto un ulteriore supporto.
    
- **VMware Horizon Virtualization Pack** per Skype for business, sviluppato in collaborazione con VMware, consente di offrire Skype for business in un desktop virtuale offrendo un'esperienza utente ottimale. La soluzione funziona sfruttando un motore multimediale presso il client per creare una soluzione ottimizzata, con l'endpoint client che offre funzionalità di offload multimediali per le chiamate audio e video. Questa soluzione in grado di fornire audio e video direttamente tra endpoint per la collaborazione uno-a-uno o di scaricarla in un'unità di controllo multipunto centrale (MCU) per le conferenze o le riunioni multiparte.
    
> [!NOTE]
> I client Skype for Business Basic non sono supportati con Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Il plug-in per l'ambiente VDI di Citrix (una caratteristica di XenApp e XenDesktop) è compatibile con Lync 2013 e Skype for business 2015 e 2016 (i client completi che usano qualsiasi programma di installazione o programmi di installazione MSI rilasciati dopo il gennaio 2017 PU) installati su un client virtuale desktop. Il suo funzionamento complessivo si basa sul plug-in Microsoft Lync VDI, ma funziona su una vasta gamma di sistemi operativi client, tra cui Windows 10, Macintosh e Linux.
  
Un elenco completo delle caratteristiche e delle tecnologie supportate è disponibile nel sito Web Citrix per la [distribuzione di Microsoft Skype for business agli utenti di XenApp e XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Per altre informazioni, vedere i collegamenti seguenti:
  
- Citrix [HDX Realtime Optimization Pack 2,1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Panoramica tecnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Supporto delle funzionalità di Skype for business CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

La soluzione ambiente VDI di VMWare è compatibile con i client completi Skype for business 2015 e 2016 installati in un desktop virtuale. Il suo funzionamento complessivo si basa sul plug-in Microsoft Lync VDI, ma funziona su una vasta gamma di sistemi operativi client, tra cui Windows 10, Macintosh e Linux. 
  
Una discussione completa sulle caratteristiche e sulle tecnologie supportate può essere trovata nel sito Web VMWare con i collegamenti seguenti:
  
- [Novità di VMware Horizon 7,4 &amp; horizon client 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualization Pack per Skype for business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for business con VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in di Lync VDI di Microsoft
<a name="Citrix_RT"> </a>

Con la soluzione plug-in Microsoft Lync VDI, l'utente deve essere installato in un computer Windows o un thin client e avere il plug-in di Lync VDI di Microsoft per gestire i flussi audio/video dal client sul desktop virtuale. Un utente dovrà:
  
1. Connettere un dispositivo audio/video (ad esempio un auricolare o una fotocamera) a un computer locale.
    
2. Connettersi a un desktop virtuale remoto con un client Lync 2013 o Skype for business 2015.
    
3. Immettere le credenziali per Skype for business sul desktop virtuale.
    
4. Immettere di nuovo le credenziali utente per stabilire una connessione con il plug-in Lync VDI nel computer Windows locale o nel thin client.
    
Dopo aver stabilito una connessione, l'utente è pronto per effettuare e ricevere chiamate audio e video. Il traffico sulla rete e il carico sul desktop virtuale sono minimizzati, poiché il computer locale gestisce l'elaborazione audio/video.
  
Il plug-in Lync VDI di Microsoft è supportato solo in determinati sistemi operativi Windows e supporta solo i client Lync 2013 o Skype for business 2015. Per altre informazioni sulle tecnologie e sulle limitazioni supportate, vedere [tecnologie di virtualizzazione supportate e limitazioni note](vdi-environments.md#Supported_virt) .
  
Per altre informazioni, vedere i collegamenti seguenti:
  
- [Tecnologie di virtualizzazione supportate e limitazioni note](vdi-environments.md#Supported_virt)
    
- [Prerequisiti del plug-in VDI di Lync](vdi-environments.md#VDI_prereq)
    
- [Distribuire il plug-in di Lync VDI con Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Articolo del centro informazioni [CTX138408](https://support.citrix.com/article/CTX138408)
    
Il plug-in Microsoft VDI è disponibile presso il plug-in [Microsoft Lync vdi 2013 (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) o il plug-in [microsoft Lync vdi 2013 (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Questo plug-in è supportato con il client Skype for business 2015, nonostante il nome.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologie di virtualizzazione supportate e limitazioni note
<a name="Supported_virt"> </a>

Il plug-in Lync VDI consente le chiamate audio e video per le tecnologie di virtualizzazione supportate. In conformità con le normative telefoniche standard, è incluso anche il supporto per E911. Le sezioni seguenti descrivono le tecnologie di virtualizzazione supportate dal plug-in di Lync VDI e dalle limitazioni note delle funzionalità.
  
#### <a name="support-for-virtualization-technologies"></a>Supporto per le tecnologie di virtualizzazione

Il plug-in Lync VDI supporta sessioni remote desktop complete nello scenario desktop virtuale personale, ma non nello scenario di sessione Desktop remoto. Questi scenari possono essere descritti come segue:
  
- **Supportati: desktop virtuali personalizzati o Virtual Desktop Infrastructure (VDI). ** In questo scenario, ogni utente esegue l'accesso a un desktop virtuale personalizzabile ed è in grado di salvare i file sul desktop che persiste tra le sessioni. I Servizi Desktop remoto Microsoft e la visualizzazione orizzonte VMware sono implementazioni di esempio testate per l'uso con Skype for business 2015. Altre implementazioni in corso di convalida includono Citrix XenDesktop. Per informazioni sugli ambienti VDI specifici del fornitore e sull'hardware client testati da Microsoft, vedere [infrastruttura qualificata per Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Non supportati: sessioni desktop remoto. ** In questo scenario ogni utente accede a una sessione desktop virtuale generica che non può essere personalizzata. Gli esempi includono Microsoft Remote Desktop Sessions (RDSH) e Citrix XenApp combinati con Citrix Receiver.
    
Il plug-in di Lync VDI non supporta altre tecnologie di virtualizzazione, come la virtualizzazione delle applicazioni, che consente l'uso di un'applicazione senza richiedere l'installazione dell'applicazione completa localmente. Le implementazioni di esempio includono Citrix XenApp e Microsoft Application Virtualization (App-V). Lo streaming di applicazioni, la comunicazione remota applicazioni e le modalità miste di virtualizzazione (ad esempio, la comunicazione remota applicazioni in una comunicazione remota desktop completa) non sono supportati.
  
Il plug-in di Lync VDI è stato progettato per usare API indipendenti dalla piattaforma, denominate Dynamic Virtual Channels (DVCs). Per gli scenari non esplicitamente supportati, fare riferimento alle istruzioni del supporto del provider di soluzioni VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Prerequisiti del plug-in VDI di Lync
<a name="VDI_prereq"> </a>

In un ambiente VDI le macchine virtuali e il computer locale dell'utente devono soddisfare i requisiti descritti in questa sezione.
  
> [!NOTE]
>  Il provider di soluzioni di virtualizzazione può fornire informazioni dettagliate su come installare e distribuire l'ambiente. Per informazioni generali sulla distribuzione di un ambiente virtualizzato basato su Hyper-V e Servizi Desktop remoto, vedere gli articoli seguenti nella raccolta Microsoft: [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [Servizi Desktop remoto in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Le macchine virtuali devono essere configurate con Windows 8, Windows 7 o Windows Server 2008 R2 con i Service Pack più recenti.
  
Il computer locale dell'utente deve soddisfare i requisiti seguenti:
  
- L'utente deve essere ospitato in Skype for Business Server o Lync Server 2013.
    
- Il computer locale deve eseguire Windows Embedded Standard 7 con SP1, Windows 7 con SP1 o Windows 8.
    
- Se si usano servizi desktop remoto, scegliere il plug-in Lync VDI a 32 o 64 bit in base al sistema operativo del computer locale. Non è necessario che sia il computer locale che la macchina virtuale abbiano sistemi operativi a 32 bit o a 64 bit. Se si usa un'altra soluzione di virtualizzazione o una piattaforma, vedere i requisiti del provider.
    
- Il computer locale deve eseguire la [versione più recente del client desktop remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032). Installare gli aggiornamenti più recenti del client di Servizi Desktop remoto da Microsoft o dal software client desktop remoto più recente del provider di soluzioni di virtualizzazione. 
    
- Nel computer locale le impostazioni client desktop remoto devono essere configurate in modo che le riproduzioni audio nel computer locale e la registrazione remota siano disattivate. Per configurare queste impostazioni per la connessione Desktop remoto in Windows, vedere la sezione successiva "per configurare le impostazioni di connessione Desktop remoto". 
    
Il plug-in Microsoft VDI è disponibile presso il plug-in [Microsoft Lync vdi 2013 (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) o il plug-in [microsoft Lync vdi 2013 (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitazioni note delle funzionalità
<a name="VDI_prereq"> </a>

Di seguito sono riportate le limitazioni note quando si usa il client Skype for business 2015 in un ambiente VDI:
  
È disponibile un supporto limitato per le funzionalità di delega delle chiamate e dell'agente di Response Group anonimato dell'.
  
Non è previsto supporto per le seguenti caratteristiche:
  
- Pagine di regolazione dispositivi audio e video integrati.
    
- Video con visualizzazioni multiple.
    
- Registrazione delle conversazioni.
    
- Partecipare a riunioni in forma anonima, ossia partecipare a riunioni Skype for business ospitate da un'organizzazione che non si associa alla propria organizzazione.
    
- Usare il plug-in di Lync VDI insieme a un dispositivo Lync Phone Edition.
    
- Continuità di chiamata in caso di problemi di rete.
    
- Suonerie personalizzate e musica di attesa.
    
Il plug-in Lync VDI non è supportato in un ambiente di Office 365.
  
> [!NOTE]
> Citrix RealTime Optimization Pack supporta Office 365. Per gli ambienti virtuali basati su Citrix, esaminare la documentazione [Panoramica tecnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) di Citrix per l'elenco delle caratteristiche e delle versioni supportate.
  
## <a name="see-also"></a>Vedere anche
<a name="Citrix_RT"> </a>

[Distribuire il plug-in di Lync VDI con Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

