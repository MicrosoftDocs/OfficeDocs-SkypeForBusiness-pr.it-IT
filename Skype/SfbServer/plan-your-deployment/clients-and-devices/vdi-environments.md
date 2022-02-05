---
title: Pianificare la Skype for Business in ambienti VDI
author: SerdarSoysal
ms.author: serdars
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - Strat_SB_Admin
ms.custom: null
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: In questo argomento vengono illustrate considerazioni sulla pianificazione per l'Skype for Business durante la connessione a un desktop virtuale remoto.
---

# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Pianificare la Skype for Business in ambienti VDI
 
In questo argomento vengono illustrate considerazioni sulla pianificazione per l'Skype for Business durante la connessione a un desktop virtuale remoto. 
  
Un Virtual Desktop Infrastructure (VDI) viene utilizzato in alcune organizzazioni in cui i problemi di sicurezza e conformità sono particolarmente sensibili. Gli utenti lavorano su un desktop virtuale con tutte le applicazioni desktop e i file utilizzando Servizi Desktop remoto o una connessione remota simile. L Skype for Business con audio e video completi su una connessione come questa richiede un carico intenso di elaborazione audio e video nel client che si ospita su un desktop virtuale. È disponibile un software aggiuntivo per i plug-in VDI che scarica l'elaborazione nel computer locale dell'utente finale e riduce il carico sul desktop virtuale.
  
Sono disponibili tre soluzioni per il componente plug-in VDI, offerte da Microsoft, Citrix o VMWare. Per le nuove distribuzioni, Microsoft consiglia di usare la soluzione Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. Il plug-in VDI di Lync originale è ancora supportato per il resto del ciclo di vita.
  
- Il **plug-in VDI di Lync** è stato sviluppato per Lync 2013 ed è compatibile con il client Lync 2013 o Skype for Business 2015 in esecuzione su un desktop virtuale. Si tratta di un'applicazione autonoma che viene installata nel computer locale e consente l'utilizzo di dispositivi audio e video locali con un client su un desktop virtuale. Il plug-in non richiede l'installazione di un client Skype for Business nel computer locale o nel thin client, che deve eseguire i sistemi operativi Windows 7, Windows 8 o Windows Server 2008. I dispositivi thin client che utilizzano questi sistemi operativi e supportati da Microsoft includono: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP t610 e HP t5740e. Questo plug-in è ancora supportato, ma non sono pianificati aggiornamenti futuri. Per gli ambienti virtuali basati su Citrix, è consigliato Citrix RealTime Optimization Pack.
    
- **Citrix RealTime Optimization Pack** si basa sul plug-in VDI lync e funziona con i client Lync 2013 o Skype for Business 2016 su un desktop virtuale. È stato sviluppato da Citrix e Microsoft per migliorare il plug-in VDI originale. Può essere installato nei client con Windows e non Windows (inclusi Windows 10, Mac e Linux). È costituito da due componenti: RealTime Connector (installato sul desktop virtuale) e RealTime Media Engine (installato nel computer locale dell'utente finale). Questi due componenti consentono al computer locale dell'utente di utilizzare il client Skype for Business in esecuzione sul desktop virtuale con l'elaborazione A/V spostata nel computer locale. Per gli ambienti desktop virtuali basati su Citrix, è consigliato Citrix RealTime Optimization Pack e viene pianificato un ulteriore supporto.
    
- **VmWare Horizon Virtualization Pack** per Skype for Business, sviluppato in collaborazione con VMWare, consente di distribuire Skype for Business in un desktop virtuale offrendo al contempo un'esperienza utente ottimale. La soluzione funziona sfruttando un motore multimediale nel client per creare una soluzione ottimizzata, con l'endpoint client che fornisce funzionalità di offload multimediale per le chiamate audio e video. Questa soluzione in grado di fornire audio e video direttamente tra gli endpoint per la collaborazione uno-a-uno o di scaricarla in una MCU (Multipoint Control Unit) centrale per conferenze telefoniche o riunioni tra più partecipanti.
    
> [!NOTE]
> I Skype for Business Basic non sono supportati con Citrix HDX RealTime Optimization Pack o VMWare Horizon Virtualization Pack. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

Il plug-in dell'ambiente VDI di Citrix (una funzionalità di XenApp e XenDesktop) è compatibile con i client Lync 2013 e Skype for Business 2015 e 2016 (client completi che usano qualsiasi clic per eseguire il programma di installazione o programmi di installazione MSI rilasciati dopo gennaio 2017) installati su un desktop virtuale. Il suo funzionamento complessivo si basa sul plug-in VDI di Microsoft Lync, ma funziona su una più ampia gamma di sistemi operativi client, tra cui Windows 10, Macintosh e Linux.
  
Un elenco completo delle funzionalità e delle tecnologie supportate è disponibile nel sito Web Citrix [all'indirizzo Delivering Microsoft Skype for Business to XenApp and XenDesktop Users](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Per ulteriori informazioni, vedere i collegamenti seguenti:
  
- Citrix [HDX RealTime Optimization Pack 2.1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Panoramica tecnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Supporto delle funzionalità Skype for Business CTX200279](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>VMWare Horizon Virtualization Pack
<a name="Citrix_RT"> </a>

La soluzione di ambiente VDI di VMWare è compatibile con i client Skype for Business 2015 e 2016 completi installati in un desktop virtuale. Il suo funzionamento complessivo si basa sul plug-in VDI di Microsoft Lync, ma funziona su una più ampia gamma di sistemi operativi client, tra cui Windows 10, Macintosh e Linux. 
  
Una descrizione completa delle funzionalità e delle tecnologie supportate è disponibile nel sito Web VMWare nei collegamenti seguenti:
  
- [Novità di VMware Horizon 7.4 &amp; Horizon Client 4.7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Horizon Virtualization Pack per Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business con VMWare Horizon](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in VDI Lync di Microsoft
<a name="Citrix_RT"> </a>

Con la soluzione plug-in VDI di Microsoft Lync, l'utente deve essere in un computer Windows o un thin client e avere installato il plug-in VDI Lync di Microsoft per gestire i flussi audio/video dal client sul desktop virtuale. Un utente:
  
1. Connessione un dispositivo audio/video (ad esempio una cuffia o una fotocamera) a un computer locale.
    
2. Connessione a un desktop virtuale remoto con un client Lync 2013 o Skype for Business 2015.
    
3. Immettere le credenziali per Skype for Business sul desktop virtuale.
    
4. Immettere di nuovo le credenziali utente per stabilire una connessione con il plug-in VDI di Lync nel computer Windows locale o nel thin client.
    
Dopo aver stabilito una connessione, l'utente è pronto per effettuare e ricevere chiamate audio e video. Il traffico sulla rete e il carico sul desktop virtuale vengono ridotti al minimo, poiché il computer locale gestisce l'elaborazione audio/video.
  
Il plug-in VDI Lync di Microsoft è supportato solo in alcuni sistemi operativi Windows e supporta solo i client Lync 2013 o Skype for Business 2015. Vedi [Tecnologie di virtualizzazione supportate e limitazioni note](vdi-environments.md#Supported_virt) per ulteriori dettagli sulle tecnologie e le limitazioni supportate.
  
Per ulteriori informazioni, vedere i collegamenti seguenti:
  
- [Tecnologie di virtualizzazione supportate e limitazioni note](vdi-environments.md#Supported_virt)
    
- [Prerequisiti del plug-in VDI di Lync](vdi-environments.md#VDI_prereq)
    
- [Distribuire il plug-in VDI di Lync con Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Articolo del Centro informazioni Citrix [CTX138408](https://support.citrix.com/article/CTX138408)
    
Il plug-in Microsoft VDI è disponibile nel [plug-in Microsoft Lync VDI 2013 (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) o nel [plug-in Microsoft Lync VDI 2013 (64 bit).](https://www.microsoft.com/download/details.aspx?id=35454) Questo plug-in è supportato con il client Skype for Business 2015, nonostante il nome.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologie di virtualizzazione supportate e limitazioni note
<a name="Supported_virt"> </a>

Il plug-in VDI di Lync consente chiamate audio e video per le tecnologie di virtualizzazione supportate. In conformità alle normative telefoniche standard, è incluso anche il supporto per E911. Nelle sezioni seguenti vengono descritte le tecnologie di virtualizzazione supportate dal plug-in VDI di Lync e le limitazioni note delle funzionalità.
  
#### <a name="support-for-virtualization-technologies"></a>Supporto per tecnologie di virtualizzazione

Il plug-in VDI di Lync supporta sessioni remote desktop complete nello scenario desktop virtuale personale, ma non nello scenario di sessione desktop remoto. Questi scenari possono essere descritti come segue:
  
- **Supportato: desktop virtuali personalizzati o Virtual Desktop Infrastructure (VDI).** In questo scenario, ogni utente accede a un desktop virtuale personalizzabile ed è in grado di salvare i file sul desktop che vengono mantenuti tra le sessioni. Desktop remoto Microsoft Services e VMware Horizon View sono implementazioni di esempio testate per l'utilizzo con Skype for Business 2015. Altre implementazioni in fase di convalida includono Citrix XenDesktop. Per informazioni sugli ambienti VDI specifici del fornitore e sull'hardware client testato da Microsoft, vedere [Infrastructure qualified for Microsoft Lync](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md).
    
- **Non supportato: Sessioni Desktop remoto.** In questo scenario, ogni utente accede a una sessione desktop virtuale generica che non può essere personalizzata. Alcuni esempi includono Desktop remoto Microsoft sessioni (RDSH) e Citrix XenApp in combinazione con Citrix Receiver.
    
Il plug-in VDI di Lync non supporta altre tecnologie di virtualizzazione, ad esempio la virtualizzazione delle applicazioni, che consente l'utilizzo di un'applicazione senza richiedere l'installazione dell'applicazione completa in locale. Le implementazioni di esempio includono Citrix XenApp e Microsoft Application Virtualization (App-V). Il flusso delle applicazioni, la comunicazione remota delle applicazioni e le modalità di virtualizzazione mista (ad esempio, la comunicazione remota delle applicazioni in servizi remoti desktop completi) non sono supportati.
  
Il plug-in VDI di Lync è stato progettato per l'utilizzo di API indipendenti dalla piattaforma denominate DVC (Dynamic Virtual Channels). Per gli scenari non esplicitamente supportati, fare riferimento alle istruzioni di supporto del provider di soluzioni VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Prerequisiti del plug-in VDI di Lync
<a name="VDI_prereq"> </a>

In un ambiente VDI, le macchine virtuali e il computer locale dell'utente devono soddisfare i requisiti descritti in questa sezione.
  
> [!NOTE]
>  Il provider di soluzioni di virtualizzazione può fornire dettagli su come installare e distribuire l'ambiente. Per informazioni generali sulla distribuzione di un ambiente virtualizzato basato su Hyper-V e Servizi Desktop remoto, vedere gli articoli seguenti nella libreria Microsoft: [Hyper-V](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753637(v=ws.10)), [Servizi Desktop remoto in Windows Server 2008 R2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd736539(v=ws.10)) 
  
Le macchine virtuali devono essere configurate con Windows 8, Windows 7 o Windows Server 2008 R2 con i Service Pack più recenti.
  
Il computer locale dell'utente deve soddisfare i requisiti seguenti:
  
- L'utente deve essere in Skype for Business Server o Lync Server 2013.
    
- Il computer locale deve eseguire Windows Embedded Standard 7 con SP1, Windows 7 con SP1 o Windows 8.
    
- Se si utilizza Servizi Desktop remoto, scegliere il plug-in VDI Lync a 32 bit o a 64 bit in modo che corrisponda al sistema operativo del computer locale. Non è necessario che il computer locale e la macchina virtuale abbia sistemi operativi a 32 bit o a 64 bit. Se si usa un'altra soluzione o piattaforma di virtualizzazione, fare riferimento ai requisiti del provider.
    
- Nel computer locale deve essere in esecuzione la [versione più recente del client desktop remoto](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients). Installare gli aggiornamenti più recenti del client Servizi Desktop remoto da Microsoft o il software client desktop remoto più recente dal provider di soluzioni di virtualizzazione. 
    
- Nel computer locale, le impostazioni del client desktop remoto devono essere configurate in modo che l'audio sia riprodotto nel computer locale e la registrazione remota sia disabilitata. Per configurare queste impostazioni per Connessione Desktop remoto in Windows, vedere la sezione successiva "Per configurare le impostazioni di Connessione Desktop remoto". 
    
Il plug-in Microsoft VDI è disponibile nel [plug-in Microsoft Lync VDI 2013 (32 bit)](https://www.microsoft.com/download/details.aspx?id=35457) o nel [plug-in Microsoft Lync VDI 2013 (64 bit).](https://www.microsoft.com/download/details.aspx?id=35454)
  
#### <a name="known-feature-limitations"></a>Limitazioni delle funzionalità note
<a name="VDI_prereq"> </a>

Di seguito sono riportate alcune limitazioni note quando si utilizza il client Skype for Business 2015 in un ambiente VDI:
  
Il supporto per la delega delle chiamate e le funzionalità di anonimizzazione degli agenti di Response Group è limitato.
  
Non è previsto supporto per le seguenti caratteristiche:
  
- Pagine di regolazione dispositivi audio e video integrati.
    
- Video con più visualizzazione.
    
- Registrazione delle conversazioni.
    
- Partecipare alle riunioni in modo anonimo, ovvero partecipare Skype for Business riunioni ospitate da un'organizzazione che non si federata con l'organizzazione.
    
- Utilizzo del plug-in VDI lync insieme a un dispositivo Lync Telefono Edition.
    
- Continuità di chiamata in caso di problemi di rete.
    
- Suonerie personalizzate e funzionalità di musica di attesa.
    
Il plug-in VDI di Lync non è supportato in Microsoft 365 o Office 365 virtuali.
  
> [!NOTE]
> Citrix RealTime Optimization Pack supporta Microsoft 365 e Office 365. Per gli ambienti virtuali basati su Citrix, consultare la documentazione di [](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) Panoramica tecnica di Citrix per l'elenco delle funzionalità e delle versioni supportate.
  
## <a name="see-also"></a>Vedere anche
<a name="Citrix_RT"> </a>

[Distribuire il plug-in VDI di Lync con Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)