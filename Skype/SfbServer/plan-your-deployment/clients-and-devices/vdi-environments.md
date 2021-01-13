---
title: Pianificare Skype for business in ambienti VDI
author: cichur
ms.author: v-cichur
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: In questo argomento vengono illustrate le considerazioni relative alla pianificazione per l'utilizzo di Skype for business durante la connessione a un desktop virtuale remoto.
ms.openlocfilehash: 66fe9dd0be2dd079597837b8d25c29b3f047b0c6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816106"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Pianificare Skype for business in ambienti VDI
 
In questo argomento vengono illustrate le considerazioni relative alla pianificazione per l'utilizzo di Skype for business durante la connessione a un desktop virtuale remoto. 
  
Un ambiente VDI (Virtual Desktop Infrastructure) viene utilizzato in alcune organizzazioni in cui i problemi di sicurezza e conformità sono particolarmente sensibili. Gli utenti eseguono il proprio lavoro su un desktop virtuale con tutte le applicazioni e i file desktop utilizzando Servizi Desktop remoto o una connessione remota analoga. L'utilizzo di Skype for business con audio e video completi su una connessione di questo tipo richiede pesanti carichi di elaborazione audio e video sul client ospitato su un desktop virtuale. È disponibile un ulteriore software plug-in VDI che consente di scaricare l'elaborazione nel computer locale dell'utente finale e di ridurre il carico sul desktop virtuale.
  
Esistono tre soluzioni disponibili per il componente plug-in VDI, offerte da Microsoft, Citrix o VMWare. Per le nuove distribuzioni, Microsoft consiglia di utilizzare la soluzione Citrix HDX RealTime Optimize Pack o VMWare Horizon Virtualization Pack. Il plug-in VDI originale di Lync è ancora supportato per il resto del ciclo di vita.
  
- Il **plug-in VDI di Lync** è stato sviluppato per Lync 2013 ed è compatibile con il client Lync 2013 o Skype for business 2015 in esecuzione su un desktop virtuale. Si tratta di un'applicazione autonoma che viene installata nel computer locale e che consente l'utilizzo di dispositivi audio e video locali con un client su un desktop virtuale. Il plug-in non richiede l'installazione di un client Skype for business nel computer locale o nel thin client, che deve eseguire sistemi operativi Windows 7, Windows 8 o Windows Server 2008. I dispositivi thin client che utilizzano questi sistemi operativi e supportati da Microsoft sono: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 e HP t5740e. Questo plug-in è ancora supportato, ma non sono previsti aggiornamenti futuri. Per gli ambienti virtuali basati su Citrix, è consigliabile utilizzare il pacchetto di ottimizzazione Citrix RealTime.
    
- Il **pacchetto di ottimizzazione Citrix realtime** si basa sul plug-in VDI di Lync ed è compatibile con i client Lync 2013 o Skype for business 2016 su un desktop virtuale. È stato sviluppato in collaborazione da Citrix e Microsoft per migliorare il plug-in VDI originale. Può essere installato nei client con sistemi operativi Windows e non Windows, tra cui Windows 10, Mac e Linux. È costituito da due componenti: il connettore in tempo reale (installato sul desktop virtuale) e il motore multimediale in tempo reale (installato nel computer locale dell'utente finale). Questi due componenti consentono al computer locale dell'utente di utilizzare il client Skype for business in esecuzione sul desktop virtuale con l'elaborazione A/V spostata nel computer locale. Per gli ambienti desktop virtuali basati su Citrix, è consigliabile eseguire il pacchetto di ottimizzazione Citrix in tempo reale e è previsto un ulteriore supporto.
    
- **VMware Horizon Virtualization Pack** per Skype for business, sviluppato in collaborazione con VMware, consente di recapitare Skype for business in un desktop virtuale e di offrire un'esperienza utente ottimale. La soluzione funziona sfruttando un motore multimediale nel client per creare una soluzione ottimizzata, con l'endpoint client che fornisce le funzionalità di offload multimediale per le chiamate audio e video. Questa soluzione in grado di fornire audio e video direttamente tra gli endpoint per la collaborazione uno-a-uno o di scaricarla in un'unità di controllo multipunto centrale (MCU) per le conferenze o le riunioni a più parti.
    
> [!NOTE]
> I client Skype for Business Basic non sono supportati con Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX ottimizzazione in tempo reale
<a name="Citrix_RT"> </a>

Il plug-in dell'ambiente VDI di Citrix (caratteristica di XenApp e XenDesktop) è compatibile con Lync 2013 e Skype for business 2015 e 2016 (client completi che utilizzano qualsiasi programma di installazione di clic per eseguire o programmi di installazione MSI rilasciati dopo il gennaio 2017 PU) installati su un desktop virtuale. Il suo funzionamento generale si basa sul plug-in Microsoft Lync VDI, ma è compatibile con una vasta gamma di sistemi operativi client, tra cui Windows 10, Macintosh e Linux.
  
Un elenco completo delle funzionalità e delle tecnologie supportate può essere trovato nel sito Web di Citrix per la [distribuzione di Microsoft Skype for business agli utenti di XenApp e XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Per ulteriori informazioni, vedere i collegamenti seguenti:
  
- Citrix [HDX Realtime Optimization Pack 2,1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Panoramica tecnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Supporto delle funzionalità di Skype for business di CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

La soluzione ambiente VDI di VMWare è compatibile con i client di Skype for business 2015 e 2016 Full installati su un desktop virtuale. Il suo funzionamento generale si basa sul plug-in Microsoft Lync VDI, ma è compatibile con una vasta gamma di sistemi operativi client, tra cui Windows 10, Macintosh e Linux. 
  
È possibile trovare una descrizione completa delle funzionalità e delle tecnologie supportate nel sito Web VMWare nei collegamenti seguenti:
  
- [What ' s New in VMware Horizon 7,4 &amp; Horizon Client 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pacchetto di virtualizzazione di Horizon per Skype for business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for business con VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in di Lync VDI di Microsoft
<a name="Citrix_RT"> </a>

Con la soluzione plug-in Microsoft Lync VDI, l'utente deve trovarsi su un computer Windows o thin client e avere installato il plug-in Lync VDI di Microsoft per gestire i flussi audio/video dal client sul desktop virtuale. Un utente eseguirà le operazioni seguenti:
  
1. Connettere un dispositivo audio/video (come una cuffia o una telecamera) a un computer locale.
    
2. Connettersi a un desktop remoto virtuale con un client Lync 2013 o Skype for business 2015.
    
3. Immettere le credenziali per Skype for business sul desktop virtuale.
    
4. Immettere di nuovo le credenziali utente per stabilire una connessione con il plug-in VDI di Lync nel computer Windows locale o thin client.
    
Una volta stabilita la connessione, l'utente è pronto per effettuare e ricevere chiamate audio e video. Il traffico sulla rete e il carico sul desktop virtuale sono minimizzati, poiché il computer locale gestisce l'elaborazione audio/video.
  
Il plug-in di Lync VDI di Microsoft è supportato solo in alcuni sistemi operativi Windows e supporta solo i client Lync 2013 o Skype for business 2015. Per ulteriori informazioni sulle tecnologie e le limitazioni supportate, vedere [tecnologie di virtualizzazione supportate e limitazioni note](vdi-environments.md#Supported_virt) .
  
Per ulteriori informazioni, vedere i collegamenti seguenti:
  
- [Tecnologie di virtualizzazione supportate e limitazioni note](vdi-environments.md#Supported_virt)
    
- [Prerequisiti del plug-in VDI di Lync](vdi-environments.md#VDI_prereq)
    
- [Distribuire il plug-in VDI di Lync con Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Articolo del centro informazioni di Citrix [CTX138408](https://support.citrix.com/article/CTX138408)
    
Il plug-in Microsoft VDI è disponibile in [Microsoft Lync vdi 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) o [microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454). Questo plugin è supportato con il client Skype for business 2015, nonostante il nome.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologie di virtualizzazione supportate e limitazioni note
<a name="Supported_virt"> </a>

Il plug-in VDI di Lync consente la chiamata audio e video per le tecnologie di virtualizzazione supportate. In conformità con le normative telefoniche standard, è incluso anche il supporto per E911. Nelle sezioni seguenti vengono descritte le tecnologie di virtualizzazione supportate dal plug-in VDI di Lync e le limitazioni note delle funzionalità.
  
#### <a name="support-for-virtualization-technologies"></a>Supporto per le tecnologie di virtualizzazione

Il plug-in VDI di Lync supporta sessioni remote desktop complete nello scenario di desktop virtuale personale, ma non nello scenario di sessione Desktop remoto. Questi scenari possono essere descritti nel modo seguente:
  
- **Supportato: desktop virtuali personalizzati o VDI (Virtual Desktop Infrastructure).** In questo scenario, ogni utente esegue l'accesso a un desktop virtuale personalizzabile ed è in grado di salvare i file sul desktop che persistono tra le sessioni. Microsoft Remote Desktop Services e VMware Horizon View sono implementazioni di esempio che sono state testate per l'utilizzo con Skype for business 2015. Altre implementazioni in seguito alla convalida includono Citrix XenDesktop. Per informazioni sugli ambienti VDI specifici del fornitore e sull'hardware client che sono stati testati da Microsoft, vedere [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Non supportata: sessioni di desktop remoto.** In questo scenario, ogni utente esegue l'accesso a una sessione desktop virtuale generica che non può essere personalizzata. Tra gli esempi sono inclusi Microsoft Remote Desktop Sessions (RDSH) e Citrix XenApp in combinazione con Citrix Receiver.
    
Il plug-in VDI di Lync non supporta altre tecnologie di virtualizzazione, ad esempio la virtualizzazione dell'applicazione, che consente l'utilizzo di un'applicazione senza richiedere l'installazione dell'applicazione completa localmente. Le implementazioni di esempio includono Citrix XenApp e Microsoft Application Virtualization (App-V). Le modalità di flusso applicazioni, comunicazione remota applicazioni e virtualizzazione mista, ad esempio la comunicazione remota applicazioni in Desktop remoto completo, non sono supportate.
  
Il plug-in VDI di Lync è stato creato per l'utilizzo di API indipendenti dalla piattaforma denominate Dynamic Virtual Channels (dinamici). Per gli scenari non supportati in modo esplicito, fare riferimento alle istruzioni di supporto del provider di soluzioni VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Prerequisiti del plug-in VDI di Lync
<a name="VDI_prereq"> </a>

In un ambiente VDI, le macchine virtuali e il computer locale dell'utente devono soddisfare i requisiti descritti in questa sezione.
  
> [!NOTE]
>  Il provider di soluzioni di virtualizzazione può fornire informazioni dettagliate su come installare e distribuire il proprio ambiente. Per informazioni di carattere generale sulla distribuzione di un ambiente virtualizzato basato su Hyper-V e Servizi Desktop remoto, vedere gli articoli seguenti in Microsoft Library: [Hyper-V](https://go.microsoft.com/fwlink/p/?linkid=247514), [Remote Desktop Services in Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Le macchine virtuali devono essere configurate con Windows 8, Windows 7 o Windows Server 2008 R2 con i Service Pack più recenti.
  
Il computer locale dell'utente deve soddisfare i requisiti seguenti:
  
- L'utente deve essere ospitato in Skype for Business Server o Lync Server 2013.
    
- È necessario che il computer locale esegua Windows Embedded Standard 7 con SP1, Windows 7 con SP1 o Windows 8.
    
- Se si utilizzano Servizi Desktop remoto, scegliere il plug-in di Lync VDI a 32 bit o 64 in modo che corrisponda al sistema operativo del computer locale. Non è necessario che il computer locale e la macchina virtuale siano dotati di sistemi operativi a 32 bit o a 64 bit. Se si utilizza un'altra soluzione o piattaforma di virtualizzazione, fare riferimento ai requisiti del provider.
    
- È necessario che il computer locale esegua la [versione più recente del client desktop remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032). Installare gli aggiornamenti più recenti del client dei Servizi Desktop remoto da Microsoft o dall'ultimo software client desktop remoto dal provider di soluzioni di virtualizzazione. 
    
- Nel computer locale, è necessario configurare le impostazioni del client desktop remoto in modo che le riproduzioni audio sul computer locale e sulla registrazione remota siano disabilitate. Per configurare queste impostazioni per la connessione Desktop remoto in Windows, vedere la sezione successiva "per configurare le impostazioni di connessione Desktop remoto". 
    
Il plug-in Microsoft VDI è disponibile in [Microsoft Lync vdi 2013 plugin (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) o [microsoft Lync VDI 2013 plugin (64 bit)](https://www.microsoft.com/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitazioni note delle funzionalità
<a name="VDI_prereq"> </a>

Di seguito sono riportate limitazioni note quando si utilizza il client Skype for business 2015 in un ambiente VDI:
  
È disponibile un supporto limitato per le funzionalità di delega chiamata e agente di Response Group Anonymization.
  
Non è previsto supporto per le seguenti caratteristiche:
  
- Pagine di regolazione dispositivi audio e video integrati.
    
- Video con più visualizzazioni.
    
- Registrazione delle conversazioni.
    
- Partecipare a riunioni in forma anonima, ovvero partecipare alle riunioni di Skype for business ospitate da un'organizzazione non federata con la propria organizzazione.
    
- Utilizzo del plug-in VDI di Lync insieme a un dispositivo Lync Phone Edition.
    
- Continuità di chiamata in caso di problemi di rete.
    
- Suonerie personalizzate e funzionalità di musica in attesa.
    
Il plug-in VDI di Lync non è supportato negli ambienti Microsoft 365 o Office 365.
  
> [!NOTE]
> Il pacchetto di ottimizzazione Citrix RealTime supporta Microsoft 365 e Office 365. Per gli ambienti virtuali basati su Citrix, consultare la documentazione relativa alla [Panoramica tecnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) di Citrix per l'elenco delle caratteristiche e delle versioni supportate.
  
## <a name="see-also"></a>Vedere anche
<a name="Citrix_RT"> </a>

[Distribuire il plug-in VDI di Lync con Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

