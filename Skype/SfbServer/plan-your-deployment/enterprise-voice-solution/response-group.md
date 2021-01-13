---
title: Pianificare l'applicazione Response Group in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: Pianificazione dei Response Group in Skype for Business Server VoIP aziendale, che consente di configurare il routing delle chiamate a gruppi di utenti. Include i requisiti dei file audio.
ms.openlocfilehash: 5abf043531079e8eef707b8cdfc4efe70f8be4bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813476"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Pianificare l'applicazione Response Group in Skype for Business Server

Pianificazione dei Response Group in Skype for Business Server VoIP aziendale, che consente di configurare il routing delle chiamate a gruppi di utenti. Include i requisiti dei file audio.

Se l'organizzazione dispone di gruppi di utenti che rispondono e gestiscono determinati tipi di chiamate, ad esempio per il servizio clienti, per un supporto tecnico interno o per un reparto telefonico generale, è possibile distribuire l'applicazione Response Group per gestire questi tipi di chiamate. L'applicazione Response Group consente di instradare e accodare le chiamate in arrivo alle persone designate, che sono note come agenti. È possibile aumentare l'utilizzo dei servizi di supporto telefonico e ridurre l'overhead prodotto dall'esecuzione di questi servizi tramite Response Group.

Quando un chiamante chiama un Response Group, viene eseguito il routing della chiamata a un agente in base a un gruppo di risposta o alle risposte del chiamante alle domande di un sistema IVR (Interactive Voice Response). L'applicazione Response Group utilizza metodi di routing di Response Group standard per instradare la chiamata al successivo agente disponibile. I metodi di routing delle chiamate supportate includono la serie, la più lunga inattività, la parallela, la Round Robin e il routing degli operatori (ovvero, tutti gli agenti vengono chiamati contemporaneamente per ogni chiamata in arrivo, indipendentemente dalla loro presenza corrente).

Se non è disponibile alcun agente, la chiamata viene mantenuta in una coda fino a quando non è disponibile un agente. Mentre la chiamata è nella coda, il chiamante ascolta un brano musicale fino a quando un agente disponibile non accetta la chiamata. Se la coda è piena o se la chiamata viene interrotta durante la coda, il chiamante potrebbe udire un messaggio e quindi essere disconnesso o trasferito in una destinazione diversa, ad esempio un numero di telefono o una segreteria telefonica diversa. Quando un agente accetta la chiamata, il chiamante può o meno visualizzare l'identità dell'agente, a seconda del modo in cui l'amministratore ha configurato Response Group. Gli agenti possono essere agenti formali, ovvero devono accedere al gruppo prima di poter accettare le chiamate di cui viene eseguito il routing al gruppo, oppure agenti informali, ovvero non accedono al gruppo né si disconnettono per accettare le chiamate.

> [!NOTE]
> Solo gli utenti che si trovano in locale possono essere agenti. Se un agente viene spostato da in locale a online, le chiamate del Response Group non gli verranno instradate.

> [!NOTE]
> L'applicazione Response Group utilizza un servizio interno, denominato match making, per accodare le chiamate e trovare gli agenti disponibili. Ogni computer che esegue l'applicazione Response Group esegue il servizio di corrispondenza, ma solo una corrispondenza che effettua il servizio per pool è attiva alla volta, mentre le altre sono passive. Se il servizio di ricerca corrispondenze diventa non disponibile durante un guasto non pianificato, viene attivato uno dei servizi di ricerca corrispondenze passivi. L'applicazione Response Group consente di fare in modo che il routing delle chiamate e l'accodamento continuino senza interruzioni. Quando si verifica una transizione a un servizio di ricerca corrispondenze, tutte le chiamate in trasferimento durante la transizione vengono perdute. Ad esempio, se la transizione è dovuta alla fine del server front-end, vengono perse anche tutte le chiamate attualmente gestite dal servizio di corrispondenza attivo in quel front end server.

## <a name="response-group-workflows"></a>Flussi di lavoro di Response Group

Un flusso di lavoro definisce il comportamento di una chiamata dal momento in cui il telefono squilla al momento in cui un qualcuno risponde. Il flusso di lavoro specifica la coda da utilizzare per lasciare in attesa la chiamata e il metodo di routing da utilizzare per i gruppi di risposta oppure le domande e le risposte da utilizzare per i Response Group interattivi. Un flusso di lavoro inoltre definisce impostazioni quali il messaggio di benvenuto, la musica di attesa, l'orario di ufficio e le festività.

> [!NOTE]
> È necessario creare i gruppi di agenti e le code prima di creare il flusso di lavoro che li utilizza.

## <a name="management-of-response-groups"></a>Gestione dei Response Group

In Skype for Business Server, sono disponibili due ruoli di gestione per la gestione dei Response Group: il responsabile del gruppo di risposta e l'amministratore di Response Group. Gli amministratori di Response Group possono gestire qualsiasi aspetto di qualsiasi Response Group. I responsabili dei Response Group possono gestire solo alcuni aspetti e solo per i Response Group di cui sono proprietari. Il ruolo di gestione consente di ridurre i costi amministrativi, in quanto è possibile delegare responsabilità limitate per gruppi di risposta specifici a qualsiasi utente abilitato per VoIP aziendale. Si noti che un utente può essere un responsabile di Response Group e un amministratore di Response Group.

Per soddisfare il ruolo di Manager, l'applicazione Response Group utilizza un **tipo di flusso di lavoro** gestito o non gestito. Nella tabella riportata di seguito vengono descritti i Response Group gestiti e non gestiti.

**Response Group gestiti e non gestiti**

|**Tipo di Response Group**|**Descrizione**|
|:-----|:-----|
|Gestito  <br/> | Ai Response Group non gestiti non è assegnato alcun Gestore. Solo l'amministratore del gruppo di risposta può configurare questi Response Group. <br/>  Response group multipli non gestiti possono condividere una coda o gruppo di agenti. <br/>  Quando si esegue la migrazione dei Response Group da una versione precedente a Skype for Business Server, il tipo è impostato su non gestito. <br/> |
|Gestione  <br/> | Gli amministratori di Response Group possono configurare qualsiasi aspetto dei gruppi di risposta gestiti. <br/>  I responsabili dei Response Group non sono in grado di visualizzare o modificare gruppi di risposta non assegnati in modo esplicito. <br/>  I responsabili dei Response Group possono configurare solo alcune impostazioni per i Response Group a loro assegnati in modo esplicito. <br/>  I Response group gestiti non possono condividere code o gruppi di agenti con altri Response group gestiti o non gestiti. <br/> |

Nella tabella seguente vengono descritte le azioni che possono essere eseguite dai responsabili dei Response Group e che non è possibile eseguire per i Response Group a loro assegnati.

**Capacità del manager del Response group**

|**Possono configurare:**|**Possono creare, eliminare o configurare:**|**Possibile**|
|:-----|:-----|:-----|
| Agents <br/>  Messaggio di benvenuto <br/>  Nome del gruppo di risposta <br/>  Descrizione <br/>  Numero visualizzato <br/>  Ore lavorative <br/>  Musica di attesa <br/>  Stato (attivo/inattivo) <br/>  Workflow del gruppo di risposta o Interactive voice response (IVR) <br/> | Gestione di gruppi di agenti <br/>  Code <br/>  Insiemi di festività <br/> | Creare o eliminare qualsiasi tipo di workflow <br/>  Modificare le impostazioni fondamentali dei Response Group, quali: **URI SIP**, **Numero di telefono** o **Tipo di workflow**.  <br/> |

I responsabili dei Response Group possono utilizzare gli strumenti seguenti per gestire i Response Group designati.

- Pannello di controllo di Skype for Business Server

    > [!NOTE]
    > I responsabili dei Response Group possono gestire solo le impostazioni di Response Group con questo strumento. Altre impostazioni di Skype for Business Server non sono disponibili per i responsabili.

- Strumento di configurazione di Response Group

- Skype for Business Server Management Shell

La scala dei Response Group è adatta agli ambienti dipartimentali o gruppi di lavoro (per informazioni dettagliate, vedere [Capacity Planning for Response Group](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) e può essere distribuita in installazioni di telefonia completamente nuove. Supporta le chiamate in arrivo dalla distribuzione di VoIP aziendale e dalla rete di vettori locali. Gli agenti possono utilizzare Skype for business, Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Phone Edition per eseguire le chiamate instradate.

## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

L'applicazione Response Group viene abilitata automaticamente quando si distribuisce VoIP aziendale.

### <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

L'applicazione Response Group ha gli stessi requisiti hardware, i requisiti del sistema operativo e i prerequisiti software dei Front End Server.

Se si utilizzano file di Windows Media Audio (WMA) per gli annunci e la musica di Response Group, tutti i Front End Server o i server Standard Edition che eseguono l'applicazione Response Group devono disporre del Runtime formato Windows Media per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per i server che eseguono Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime è installato come parte dell'esperienza desktop di Windows.

Response Group utilizza i **Language Pack** per il supporto del riconoscimento vocale e del testo. Queste tecnologie vocali vengono usate quando si configurano messaggi, ad esempio messaggi di benvenuto o di altro tipo, nonché domande e risposte IVR (Interactive Voice Response). Per impostazione predefinita, i 26 Language Pack supportati vengono installati quando si distribuisce Skype for Business Server.

### <a name="port-requirements"></a>Requisiti delle porte

L'applicazione Response Group utilizza le porte seguenti:

- **Porta 5071**   per le richieste di attesa SIP

- **Porta 8404**   per le comunicazioni tra server

    > [!NOTE]
    > Questa porta viene utilizzata per il servizio di ricerca delle corrispondenze ed è necessaria quando l'applicazione Response Group viene distribuita in un pool con più server front-end.

   > [!NOTE]
   > Tali porte vengono utilizzate per impostazione predefinita e possono essere cambiate mediante il cmdlet **Set-CsApplicationServer**. Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Skype for Business Server Management Shell.

### <a name="audio-file-requirements"></a>Requisiti dei file audio

L'applicazione Response Group supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (. WMA) per i messaggi di Response Group, la musica di attesa o le domande del sistema IVR (Interactive Voice Response).

Il formato di file Windows Media Audio richiede che il runtime del formato Windows Media sia installato nei front end server che eseguono Windows Server 2008 R2 e Windows Server 2008. Per ulteriori dettagli, vedere i "Requisiti software" presi già in esame in questa sezione.

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

Lo strumento di configurazione di Response Group supporta le combinazioni di sistemi operativi e Web browser descritte nella tabella seguente.

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

- Client desktop Skype for business

- Client desktop Lync 2013

- Client desktop Lync 2010

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> L'applicazione Response Group non è supportata nei client mobili di Lync.

Il client specifico che è possibile utilizzare dipende dal tipo di utente di Response Group che si è:

- **Chiamanti**: possono chiamare un Response Group utilizzando uno qualsiasi dei client elencati in precedenza e utilizzando un telefono standard nella rete PSTN (Public Switched Telephone Network).

- Gli **agenti informali** (gli agenti che non effettuano l'accesso e i loro gruppi per accettare le chiamate) possono accettare le chiamate tramite Attendant, Lync o Lync Phone Edition. Gli agenti informali vengono automaticamente firmati nei rispettivi gruppi quando eseguono l'accesso a Skype for Business Server mediante uno di questi client.

- Gli **agenti formali** (gli agenti che devono accedere e uscire dai propri gruppi per accettare le chiamate) possono accettare le chiamate utilizzando Skype for business e accedendo alla console dell'agente dalla voce di menu oppure utilizzando Attendant e accedendo alla console dell'agente direttamente da Internet Explorer.

## <a name="capacity-planning"></a>Pianificazione della capacità

Nella tabella seguente viene descritto il modello utente di Response Group che è possibile utilizzare come base per i requisiti di pianificazione della capacità.

> [!NOTE]
> I numeri nella tabella seguente presuppongono l'utilizzo di file Wave (con estensione wav) a 16 bit, 16 kHz, mono per tutti i file audio Response Group. Se si utilizzano altri formati, ad esempio Windows Media Audio ( con estensione wma), i numeri possono variare.

> [!IMPORTANT]
> Tenere presente che, per la pianificazione della capacità per il ripristino di emergenza, ogni pool di un pool accoppiato deve poter gestire i carichi di lavoro per tutti i Response Group in entrambi i pool.

**Modello utente Response Group**

|**Metrica**|**Per pool Enterprise Edition  <br/> (con 8 Front End Server)**|**Per server Standard Edition**|
|:-----|:-----|:-----|
|Chiamate in entrata al secondo  <br/> |16   <br/> |2   <br/> |
|Chiamate simultanee connesse a IVR o MoH  <br/> |480  <br/> |60  <br/> |
|Sessioni anonime simultanee (senza messaggistica istantanea)  <br/> |224  <br/> |28  <br/> |
|Sessioni anonime simultanee (con messaggistica istantanea)  <br/> |64  <br/> |8   <br/> |
|Agenti attivi (formali e informali)  <br/> |2400  <br/> |2400  <br/> |
|Numero di gruppi di risposta  <br/> |800  <br/> |800  <br/> |
|Numero di gruppi IVR (utilizzo del riconoscimento vocale)  <br/> |400  <br/> |400  <br/> |


