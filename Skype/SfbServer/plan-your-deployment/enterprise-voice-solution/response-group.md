---
title: Pianificare l'applicazione Response Group in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
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
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Pianificazione dei Response Group in Skype for Business Server VoIP aziendale, che consente di configurare il routing delle chiamate a gruppi di utenti. Include i requisiti per i file audio.
ms.openlocfilehash: 3b208b5f18b4b14a35985144b2b96cbabbf39dfe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859883"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Pianificare l'applicazione Response Group in Skype for Business Server

Pianificazione dei Response Group in Skype for Business Server VoIP aziendale, che consente di configurare il routing delle chiamate a gruppi di utenti. Include i requisiti per i file audio.

Se nell'organizzazione sono disponibili gruppi di persone che rispondono e gestiscono determinati tipi di chiamate, ad esempio per il servizio clienti, un help desk interno o un supporto telefonico generale per un reparto, è possibile distribuire l'applicazione Response Group per gestire questi tipi di chiamate. L'applicazione Response Group instrada e accoda le chiamate in arrivo a persone designate, note come agenti. È possibile aumentare l'utilizzo dei servizi di supporto telefonico e ridurre l'overhead prodotto dall'esecuzione di questi servizi tramite Response Group.

Quando un chiamante chiama un Response Group, viene eseguito il routing della chiamata a un agente in base a un gruppo di risposta o alle risposte del chiamante alle domande di un sistema IVR (Interactive Voice Response). L'applicazione Response Group utilizza metodi di routing standard di Response Group per instradare la chiamata al successivo agente disponibile. I metodi di routing delle chiamate supportati includono il routing seriale, inattivo più lungo, parallelo, round robin e operatore, ovvero tutti gli agenti vengono chiamati contemporaneamente per ogni chiamata in arrivo, indipendentemente dalla presenza corrente.

Se non è disponibile alcun agente, la chiamata viene mantenuta in una coda fino a quando non è disponibile un agente. Mentre la chiamata è nella coda, il chiamante ascolta un brano musicale fino a quando un agente disponibile non accetta la chiamata. Se la coda è piena o se si verifica il timeout della chiamata durante la coda, il chiamante potrebbe ascoltare un messaggio e quindi essere disconnesso o trasferito a una destinazione diversa, ad esempio un numero di telefono o una segreteria telefonica diversa. Quando un agente accetta la chiamata, il chiamante può o meno visualizzare l'identità dell'agente, a seconda del modo in cui l'amministratore ha configurato Response Group. Gli agenti possono essere agenti formali, ovvero devono accedere al gruppo prima di poter accettare le chiamate di cui viene eseguito il routing al gruppo, oppure agenti informali, ovvero non accedono al gruppo né si disconnettono per accettare le chiamate.

> [!NOTE]
> Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.

> [!NOTE]
> L'applicazione Response Group utilizza un servizio interno, denominato Match Making, per accodare le chiamate e trovare gli agenti disponibili. Ogni computer che esegue l'applicazione Response Group esegue il servizio Match Making, ma è attivo un solo servizio match making per pool, mentre gli altri sono passivi. Se il servizio di ricerca corrispondenze diventa non disponibile durante un guasto non pianificato, viene attivato uno dei servizi di ricerca corrispondenze passivi. L'applicazione Response Group fa del suo meglio per assicurarsi che il routing delle chiamate e l'accodamento continuino ininterrottamente. Quando si verifica una transizione a un servizio di ricerca corrispondenze, tutte le chiamate in trasferimento durante la transizione vengono perdute. Ad esempio, se la transizione è dovuta al calo del Front End Server, anche tutte le chiamate attualmente gestite dal servizio match making attivo su tale Front End Server andranno perse.

## <a name="response-group-workflows"></a>Flussi di lavoro di Response Group

Un flusso di lavoro definisce il comportamento di una chiamata dal momento in cui il telefono squilla al momento in cui un qualcuno risponde. Il flusso di lavoro specifica la coda da utilizzare per lasciare in attesa la chiamata e il metodo di routing da utilizzare per i gruppi di risposta oppure le domande e le risposte da utilizzare per i Response Group interattivi. Un flusso di lavoro inoltre definisce impostazioni quali il messaggio di benvenuto, la musica di attesa, l'orario di ufficio e le festività.

> [!NOTE]
> È necessario creare i gruppi di agenti e le code prima di creare il flusso di lavoro che li utilizza.

## <a name="management-of-response-groups"></a>Gestione dei Response Group

In Skype for Business Server sono disponibili due ruoli di gestione per la gestione dei Response Group: Response Group Manager e Response Group Administrator. Gli amministratori di Response Group possono gestire qualsiasi aspetto di qualsiasi Response Group. I responsabili di Response Group possono gestire solo determinati aspetti e solo per i Response Group di cui sono proprietari. Il ruolo Manager consente di ridurre i costi di amministrazione, poiché è possibile delegare responsabilità limitate per response group specifici a qualsiasi utente abilitato per VoIP aziendale. Si noti che un utente può essere sia un responsabile di Response Group che un amministratore di Response Group.

Per supportare il ruolo Manager, l'applicazione Response Group utilizza un tipo **di flusso di lavoro** gestito o non gestito. Nella tabella riportata di seguito vengono descritti i Response Group gestiti e non gestiti.

**Response Group gestiti e non gestiti**

|**Tipo di Response Group**|**Descrizione**|
|:-----|:-----|
|Non gestito  <br/> | Ai Response Group non gestiti non è assegnato alcun Gestore. Solo l'amministratore di Response Group può configurare questi Response Group. <br/>  Response group multipli non gestiti possono condividere una coda o gruppo di agenti. <br/>  Quando si esegue la migrazione di Response Group da una versione precedente a Skype for Business Server, il tipo è impostato su Non gestito. <br/> |
|Gestione  <br/> | Gli amministratori di Response Group possono configurare qualsiasi aspetto dei Response Group gestiti. <br/>  I responsabili di Response Group non possono visualizzare o modificare i Response Group non assegnati in modo esplicito. <br/>  I responsabili di Response Group possono configurare solo alcune impostazioni per i Response Group assegnati in modo esplicito. <br/>  I Response group gestiti non possono condividere code o gruppi di agenti con altri Response group gestiti o non gestiti. <br/> |

Nella tabella seguente vengono descritte le azioni che i responsabili di Response Group possono eseguire e non possono eseguire per i Response Group a loro assegnati.

**Capacità del manager del Response group**

|**Possono configurare:**|**Possono creare, eliminare o configurare:**|**Impossibile:**|
|:-----|:-----|:-----|
| Agents <br/>  Messaggio di benvenuto <br/>  Nome Response Group <br/>  Descrizione <br/>  Numero visualizzato <br/>  Ore lavorative <br/>  Musica di attesa <br/>  Stato (attivo/inattivo) <br/>  Workflow del gruppo di risposta o Interactive voice response (IVR) <br/> | Gestione di gruppi di agenti <br/>  Code <br/>  Insiemi di festività <br/> | Creare o eliminare qualsiasi tipo di workflow <br/>  Modificare le impostazioni fondamentali dei Response Group, quali: **URI SIP**, **Numero di telefono** o **Tipo di workflow**.  <br/> |

I responsabili di Response Group possono utilizzare gli strumenti seguenti per gestire i Response Group designati.

- Pannello di controllo di Skype for Business Server

    > [!NOTE]
    > I responsabili di Response Group possono gestire solo le impostazioni di Response Group con questo strumento. Altre Skype for Business Server non sono disponibili per i manager.

- Strumento di configurazione di Response Group

- Skype for Business Server Management Shell

Response Group si adatta bene agli ambienti di reparto o di gruppo di lavoro (per informazioni dettagliate, vedere [Capacity Planning for Response Group)](/previous-versions/office/lync-server-2013/lync-server-2013-capacity-planning-for-response-group)e può essere distribuito in installazioni di telefonia completamente nuove. Supporta le chiamate in arrivo dalla distribuzione VoIP aziendale e dalla rete del gestore locale. Gli agenti possono utilizzare Skype for Business, Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Telefono Edition per effettuare le chiamate instradati.

## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

L'applicazione Response Group viene abilitata automaticamente quando si distribuisce VoIP aziendale.

### <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

L'applicazione Response Group ha gli stessi requisiti hardware, i requisiti del sistema operativo e i prerequisiti software dei Front End Server.

Se si utilizzano file Windows Media Audio (wma) per la musica e gli annunci di Response Group, in tutti i Front End Server o nei server Standard Edition che eseguono l'applicazione Response Group deve essere installato Runtime formato multimediale Windows per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte di Windows Desktop Experience.

Response Group usa **Language Pack** per supportare la sintesi vocale e il riconoscimento vocale. Queste tecnologie vocali vengono usate quando si configurano messaggi, ad esempio messaggi di benvenuto o di altro tipo, nonché domande e risposte IVR (Interactive Voice Response). Per impostazione predefinita, i 26 Language Pack supportati vengono installati quando si distribuisce Skype for Business Server.

### <a name="port-requirements"></a>Requisiti delle porte

L'applicazione Response Group utilizza le porte seguenti:

- **Porta 5071 per**   le richieste di attesa SIP

- **Porta 8404 per**   le comunicazioni tra server

    > [!NOTE]
    > Questa porta viene utilizzata per il servizio Match Making ed è necessaria quando l'applicazione Response Group viene distribuita in un pool con più Front End Server.

   > [!NOTE]
   > Tali porte vengono utilizzate per impostazione predefinita e possono essere cambiate mediante il cmdlet **Set-CsApplicationServer**. Per informazioni dettagliate su questo cmdlet, vedere la documentazione Skype for Business Server Management Shell.

### <a name="audio-file-requirements"></a>Requisiti dei file audio

L'applicazione Response Group supporta il formato di file wave (wav) e il formato di file Windows Media Audio (wma) per i messaggi di Response Group, la musica di attesa o le domande IVR (Interactive Voice Response).

Il formato di file audio Windows Media richiede che runtime formato multimediale di Windows sia installato nei Front End Server che eseguono Windows Server 2008 R2 e Windows Server 2008. Per ulteriori dettagli, vedere i "Requisiti software" presi già in esame in questa sezione.

#### <a name="supported-wave-file-formats"></a>Formati di file wave supportati

Tutti i file wave devono soddisfare i requisiti seguenti:

- File a 8 bit o a 16 bit

- LPCM (Linear Pulse Code Modulation), formato A-Law o mu-Law

- Mono o stereo

- Massimo 4 MB

Per ottenere prestazioni ottimali con i file wave, è consigliabile utilizzare un file wave mono a 16 bit e 16 kHz.

#### <a name="supported-windows-media-audio-file-formats"></a>Formati di file Windows Media Audio supportati

Se si utilizza un file Windows Media Audio, è consigliabile utilizzare velocità in bit basse e verificare le prestazioni del sistema sotto carico.

Per convertire un file nel formato Windows Media Audio, è possibile utilizzare Microsoft Expression Encoder 4. Per scaricare Expression Encoder 4, vedere [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) .

### <a name="response-group-configuration-tool-requirements"></a>Requisiti dello Strumento di configurazione Response Group

Lo strumento di configurazione di Response Group supporta le combinazioni di sistemi operativi e Web browser descritti nella tabella seguente.

> [!NOTE]
> Sono supportate sia le versioni a 32 bit che a 64 bit dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.

**Sistemi operativi e Web browser supportati**

|**Sistema operativo**|**Web browser**|
|:-----|:-----|
|Windows Vista con Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows 7  <br/> Windows 7 con Service Pack 1  <br/> |Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows Server 2008 con Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 con Service Pack 1  <br/> |Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Console degli agenti di Response Group

La console degli agenti supporta le combinazioni di sistemi operativi e Web browser descritte nella tabella seguente.

> [!NOTE]
> Sono supportate sia le versioni a 32 bit che a 64 bit dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.

**Sistemi operativi e Web browser supportati**

|**Sistema operativo**|**Web browser**|
|:-----|:-----|
|Windows Vista con Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows 7  <br/> Windows 7 con Service Pack 1  <br/> |Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 con Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 con Service Pack 1  <br/> |Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Supporto client

L'applicazione Response Group supporta i client seguenti:

- Skype for Business client desktop

- Client desktop Lync 2013

- Client desktop Lync 2010

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> L'applicazione Response Group non è supportata nei client mobili Lync.

Il client specifico che è possibile utilizzare dipende dal tipo di utente di Response Group in uso:

- **Chiamanti**: possono chiamare un Response Group utilizzando uno qualsiasi dei client elencati in precedenza e utilizzando un telefono standard nella rete PSTN (Public Switched Telephone Network).

- **Gli agenti informali** ,ovvero gli agenti che non eseguono l'accesso e la disconnessione dai propri gruppi per accettare chiamate, possono accettare chiamate utilizzando Attendant, Lync o Lync Telefono Edition. Gli agenti informali vengono automaticamente connessi ai propri gruppi quando a Skype for Business Server tramite uno di questi client.

- Gli agenti formali **(gli** agenti che devono accedere e uscire dai propri gruppi per accettare le chiamate) possono accettare le chiamate utilizzando Skype for Business e accedendo alla console degli agenti dalla voce di menu oppure utilizzando Operatore e accedendo alla console dell'agente direttamente da Internet Explorer.

## <a name="capacity-planning"></a>Pianificazione della capacità

Nella tabella seguente viene descritto il modello utente di Response Group che è possibile utilizzare come base per i requisiti di pianificazione della capacità.

> [!NOTE]
> I numeri nella tabella seguente presuppongono l'utilizzo di file Wave (con estensione wav) a 16 bit, 16 kHz, mono per tutti i file audio Response Group. Se si utilizzano altri formati, ad esempio Windows Media Audio ( con estensione wma), i numeri possono variare.

> [!IMPORTANT]
> Tenere presente che, per la pianificazione della capacità per il ripristino di emergenza, ogni pool di un pool accoppiato deve poter gestire i carichi di lavoro per tutti i Response Group in entrambi i pool.

**Modello utente Response Group**

|**Metrica**|**Per edizione Enterprise pool <br/> (con 8 Front End Server)**|**Per server Standard Edition**|
|:-----|:-----|:-----|
|Chiamate in entrata al secondo  <br/> |16   <br/> |2  <br/> |
|Chiamate simultanee connesse a IVR o MoH  <br/> |480  <br/> |60  <br/> |
|Sessioni anonime simultanee (senza messaggistica istantanea)  <br/> |224  <br/> |28  <br/> |
|Sessioni anonime simultanee (con messaggistica istantanea)  <br/> |64  <br/> |8   <br/> |
|Agenti attivi (formali e informali)  <br/> |2400  <br/> |2400  <br/> |
|Numero di gruppi di risposta  <br/> |800  <br/> |800  <br/> |
|Numero di gruppi IVR (utilizzo del riconoscimento vocale)  <br/> |400  <br/> |400  <br/> |