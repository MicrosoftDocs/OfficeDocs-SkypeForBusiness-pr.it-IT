---
title: Pianificare l'applicazione Response Group in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Pianificazione dei gruppi di risposta in Skype for Business Server VoIP aziendale, che consente di configurare il routing delle chiamate a gruppi di utenti. Include i requisiti per i file audio.
ms.openlocfilehash: ec0bbe0e02fd7b4f027f8c2e57784c402aa0f039
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802486"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>Pianificare l'applicazione Response Group in Skype for Business Server

Pianificazione dei gruppi di risposta in Skype for Business Server VoIP aziendale, che consente di configurare il routing delle chiamate a gruppi di utenti. Include i requisiti per i file audio.

Se l'organizzazione dispone di gruppi di persone che rispondono e gestiscono determinati tipi di chiamate, ad esempio per il servizio clienti, un help desk interno o il supporto telefonico generale per un reparto, è possibile distribuire l'applicazione Response Group per gestire questi tipi di chiamate. L'applicazione Response Group instrada e accoda le chiamate in arrivo alle persone designate, note come agenti. È possibile aumentare l'uso dei servizi di supporto telefonico e ridurre il sovraccarico di eseguire questi servizi utilizzando Response Groups.

Quando un chiamante chiama un gruppo di risposte, la chiamata viene instradata a un agente in base a un gruppo di risposta o alle domande del chiamante per rispondere alla risposta vocale interattiva (IVR). L'applicazione Response Group USA i metodi di routing dei gruppi di risposta standard per instradare la chiamata al successivo agente disponibile. I metodi di routing delle chiamate supportati includono il routing seriale, più lungo, quello parallelo, quello rotondo e quello del supervisore (ovvero tutti gli agenti vengono chiamati contemporaneamente per ogni chiamata in arrivo, indipendentemente dalla presenza corrente).

Se non sono disponibili agenti, la chiamata viene mantenuta in una coda finché non è disponibile un agente. Mentre si è in coda, il chiamante sente la musica finché un agente disponibile non accetta la chiamata. Se la coda è piena o se la chiamata viene interrotta durante la coda, il chiamante potrebbe udire un messaggio e quindi essere disconnesso o trasferito in una destinazione diversa, ad esempio un numero di telefono o un messaggio di posta vocale diverso. Quando un agente accetta la chiamata, il chiamante potrebbe non essere in grado di visualizzare l'identità dell'agente, a seconda del modo in cui l'amministratore configura il gruppo di risposte. Gli agenti possono essere formali, quindi devono accedere al gruppo prima di poter accettare le chiamate instradate al gruppo o informale, il che significa che non accedono al gruppo per accettare le chiamate.

> [!NOTE]
> Solo gli utenti locali possono essere agenti. Se un agente viene spostato da locale a online, le chiamate di Response Group non verranno indirizzate a tale agente.

> [!NOTE]
> L'applicazione Response Group usa un servizio interno, denominato match making, per accodare le chiamate e trovare gli agenti disponibili. Ogni computer che esegue l'applicazione Response Group esegue il servizio di match making, ma solo un servizio per ogni pool è attivo alla volta, mentre gli altri sono passivi. Se il servizio di corrispondenza attiva diventa non disponibile durante un'interruzione non pianificata, uno dei servizi di corrispondenza passiva diventa attivo. L'applicazione Response Group fa del suo meglio per assicurarsi che il routing delle chiamate e l'accodamento continuino senza interruzioni. Tuttavia, quando si verifica una transizione del servizio di corrispondenza, le chiamate in fase di trasferimento vengono perse. Ad esempio, se la transizione è dovuta al fatto che il server front-end si abbassa, vengono perse anche le chiamate attualmente gestite dal servizio Active match making del server front-end.

## <a name="response-group-workflows"></a>Flussi di lavoro di Response Group

Un flusso di lavoro definisce il comportamento di una chiamata dall'ora in cui il telefono squilla per l'ora in cui qualcuno risponde alla chiamata. Il flusso di lavoro specifica la coda da usare per la chiamata e specifica il metodo di routing da usare per i gruppi di ricerca o le domande e le risposte da usare per i gruppi di risposta interattivi. Un flusso di lavoro definisce anche le impostazioni, ad esempio un messaggio di benvenuto, la musica in attesa, le ore lavorative e le festività.

> [!NOTE]
> È necessario creare gruppi di agenti e code prima di creare un flusso di lavoro che li usa.

## <a name="management-of-response-groups"></a>Gestione dei gruppi di risposta

In Skype for Business Server sono disponibili due ruoli di gestione per la gestione dei gruppi di risposta: Response Group Manager e Response Group Administrator. Gli amministratori del gruppo di risposte possono gestire qualsiasi aspetto di un gruppo di risposte. I responsabili dei gruppi di risposte possono gestire solo determinati aspetti e solo per i gruppi di risposta di cui sono proprietari. Il ruolo di Manager può aiutare a ridurre i costi amministrativi, perché è possibile delegare responsabilità limitate per specifici gruppi di risposta a qualsiasi utente abilitato per VoIP aziendale. Tieni presente che un utente può essere sia un Manager di Response Group che un amministratore del gruppo di risposte.

Per gestire il ruolo di Manager, l'applicazione Response Group usa un **tipo di flusso di lavoro** gestito o non gestito. La tabella seguente descrive i gruppi di risposta gestiti e non Managed.

**Gruppi di risposte gestite e non gestiti**

|**Tipo di gruppo di risposta**|**Descrizione**|
|:-----|:-----|
|Non gestite  <br/> | I gruppi di risposte non gestiti non hanno gestori assegnati. Solo l'amministratore del gruppo di risposte può configurare questi gruppi di risposta. <br/>  Più gruppi di risposte non gestiti possono condividere una coda o un gruppo di agenti. <br/>  Quando si esegue la migrazione di Response Groups da una versione precedente a Skype for Business Server, il tipo è impostato su non gestito. <br/> |
|Gestito  <br/> | Gli amministratori del gruppo di risposte possono configurare qualsiasi aspetto dei gruppi di risposta gestiti. <br/>  I responsabili del gruppo di risposte non possono visualizzare o modificare i gruppi di risposta che non sono assegnati esplicitamente. <br/>  I responsabili del gruppo di risposte possono configurare solo alcune impostazioni per i gruppi di risposta assegnati esplicitamente. <br/>  I gruppi di risposta gestiti non possono condividere le code o i gruppi di agenti con qualsiasi altro gruppo di risposte, gestito o non gestito. <br/> |

La tabella seguente descrive le azioni che i responsabili dei gruppi di risposta possono e non possono eseguire per i gruppi di risposte assegnati.

**Funzionalità di gestione gruppi di risposte**

|**Può configurare:**|**Può creare, eliminare o configurare:**|**Non**|
|:-----|:-----|:-----|
| Agenti <br/>  Messaggio di benvenuto <br/>  Nome del gruppo di risposte <br/>  Descrizione <br/>  Numero di visualizzazione <br/>  Orari di ufficio <br/>  Musica in attesa <br/>  Stato (attivo/inattivo) <br/>  Cercare flussi di lavoro di gruppo o flussi di lavoro IVR (Interactive Voice Response) <br/> | Gruppi di agenti <br/>  Code <br/>  Set di festività <br/> | Creare o eliminare qualsiasi tipo di flusso di lavoro <br/>  Modificare le impostazioni del gruppo di risposte di base, ad esempio: **URI SIP**, **numero di telefono**o **tipo di flusso di lavoro**.  <br/> |

I responsabili del gruppo di risposte possono usare gli strumenti seguenti per gestire i gruppi di risposta designati.

- Pannello di controllo di Skype for Business Server

    > [!NOTE]
    > I responsabili dei gruppi di risposte possono gestire solo le impostazioni di Response Group con questo strumento. Altre impostazioni di Skype for Business Server non sono disponibili per i responsabili.

- Strumento di configurazione di Response Group

- Skype for Business Server Management Shell

Il gruppo di risposte si adatta bene agli ambienti dipartimentali o gruppi di lavoro (per informazioni dettagliate, Vedi [pianificazione della capacità per Response Group](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)) e può essere distribuito in installazioni di telefonia completamente nuove. Supporta le chiamate in arrivo dalla distribuzione VoIP aziendale e dalla rete di vettori locali. Gli agenti possono usare Skype for business, Lync 2013, Lync 2010, Lync 2010 Attendant o Lync Phone Edition per eseguire le chiamate instradate.

## <a name="deployment-and-requirements"></a>Distribuzione e requisiti

L'applicazione Response Group viene abilitata automaticamente quando si distribuisce VoIP aziendale.

### <a name="hardware-and-software-requirements"></a>Requisiti hardware e software

L'applicazione Response Group offre gli stessi requisiti hardware, i requisiti del sistema operativo e i prerequisiti software come front end server.

Se si usano file di Windows Media Audio (con estensione WMA) per la musica e gli annunci di Response Group, tutti i server front-end o le edizioni standard che eseguono l'applicazione Response Group devono avere installato Windows Media Format Runtime per i server che eseguono Windows Server 2008 R2 o Microsoft Media Foundation per server che utilizzano Windows Server 2012 o Windows Server 2012 R2. Per Windows Server 2008 R2, Windows Media Format Runtime viene installato come parte dell'esperienza desktop di Windows.

Il gruppo di risposte usa i **Language Pack** per supportare il riconoscimento vocale e del testo. Queste tecnologie vocali vengono usate quando si configurano i messaggi, ad esempio il messaggio di benvenuto e altre richieste, e le domande e le risposte di risposta vocale interattiva (IVR). Per impostazione predefinita, i 26 Language Pack supportati vengono installati quando si distribuisce Skype for Business Server.

### <a name="port-requirements"></a>Requisiti della porta

L'applicazione Response Group usa le porte seguenti:

- **Porta 5071** per le richieste di ascolto SIP

- **Porta 8404** per le comunicazioni interserver

    > [!NOTE]
    > Questa porta viene usata per il servizio di creazione delle corrispondenze ed è necessaria quando l'applicazione Response Group viene distribuita in un pool che ha più di un server front-end.

   > [!NOTE]
   > Queste porte sono impostazioni predefinite che è possibile modificare usando il cmdlet **Set-CsApplicationServer** . Per informazioni dettagliate su questo cmdlet, vedere la documentazione di Skype for Business Server Management Shell.

### <a name="audio-file-requirements"></a>Requisiti per i file audio

L'applicazione Response Group supporta il formato di file Wave (con estensione wav) e il formato di file di Windows Media Audio (con estensione WMA) per i messaggi di Response Group, la musica in attesa o le domande di risposta vocale interattiva (IVR).

Il formato di file audio Windows Media richiede che Windows Media Format Runtime sia installato nei server front-end in cui è in esecuzione Windows Server 2008 R2 e Windows Server 2008. Per altri dettagli, vedere "requisiti software" in questa sezione.

#### <a name="supported-wave-file-formats"></a>Formati di file Wave supportati

Tutti i file Wave devono soddisfare i requisiti seguenti:

- file a 8 bit o a 16 bit

- Modulazione del codice pulsazione lineare (LPCM), A-Law o mu-Law Format

- Mono o stereo

- 4 MB o meno

Per ottenere prestazioni ottimali, è consigliabile un file Wave da 16 kHz, mono e a 16 bit.

#### <a name="supported-windows-media-audio-file-formats"></a>Formati di file audio Windows Media supportati

Se si usa un file audio Windows Media, valutare l'uso di velocità in bit bassi e verificare le prestazioni del sistema in Load.

Puoi usare Microsoft Expression Encoder 4 per convertire un file nel formato audio di Windows Media. Per scaricare Expression Encoder 4, vedere [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843).

### <a name="response-group-configuration-tool-requirements"></a>Requisiti dello strumento di configurazione dei gruppi di risposta

Lo strumento di configurazione Response Group supporta le combinazioni di sistemi operativi e browser Web descritti nella tabella seguente.

> [!NOTE]
> sono supportate le versioni a 32 bit o a bit 64 dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.

**Sistemi operativi e browser Web supportati**

|**Sistema operativo**|**Web browser**|
|:-----|:-----|
|Windows Vista con Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows 7  <br/> Windows 7 con Service Pack 1  <br/> |Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows Server 2008 con Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 con Service Pack 1  <br/> |Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>Console agente di Response Group

La console agente supporta le combinazioni di sistemi operativi e browser Web descritti nella tabella seguente.

> [!NOTE]
> sono supportate le versioni a 32 bit o a bit 64 dei sistemi operativi. Sono supportate solo le versioni a 32 bit di Internet Explorer.

**Sistemi operativi e browser Web supportati**

|**Sistema operativo**|**Web browser**|
|:-----|:-----|
|Windows Vista con Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows 7  <br/> Windows 7 con Service Pack 1  <br/> |Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> Firefox 10,0  <br/> Chrome 18,0  <br/> |
|Windows Server 2008 con Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 con Service Pack 1  <br/> |Internet Explorer 8 (modalità nativa)  <br/> Internet Explorer 9 (modalità nativa)  <br/> Firefox 10,0  <br/> Chrome 18,0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>Supporto client

L'applicazione Response Group supporta i client seguenti:

- Client desktop Skype for business

- Client desktop Lync 2013

- Client desktop Lync 2010

- Assistente di Lync 2010

- Assistente di Office Communications Server 2007 R2

- Lync Phone Edition

> [!NOTE]
> L'applicazione Response Group non è supportata nei client di Lync mobile.

Il client specifico che puoi usare dipende dal tipo di utente di Response Group che sei:

- I **chiamanti** possono chiamare un Response Group usando uno dei client elencati in precedenza e usando un telefono standard sulla rete PSTN (Public Switched Telephone Network).

- Gli **agenti informali** (gli agenti che non accedono ai loro gruppi per accettare le chiamate) possono accettare le chiamate tramite Attendant, Lync o Lync Phone Edition. Gli agenti informali vengono automaticamente registrati nei loro gruppi quando accedono a Skype for Business Server usando uno di questi client.

- Gli **agenti formali** (gli agenti che devono accedere e disconnettersi dai loro gruppi per accettare le chiamate) possono accettare le chiamate usando Skype for business e accedendo alla console dell'agente dalla voce di menu oppure usando Attendant e accedendo alla console dell'agente direttamente da Internet Explorer.

## <a name="capacity-planning"></a>Pianificazione della capacità

La tabella seguente descrive il modello di Response Group User che puoi usare come base per i requisiti di pianificazione della capacità.

> [!NOTE]
> I numeri nella tabella seguente presuppongono l'uso di file wave 16 kHz, mono, a 16 bit (WAV) per tutti i file audio del gruppo di risposte. Se si usano altri formati di file, ad esempio Windows Media Audio (WMA), i numeri possono variare.

> [!IMPORTANT]
> Tieni presente che per la pianificazione della capacità di ripristino di emergenza, ogni pool di un pool associato dovrebbe essere in grado di gestire i carichi di lavoro per tutti i gruppi di risposta in entrambi i pool.

**Modello di Response Group User**

|**Metrica**|**Per pool <br/> Enterprise Edition (con 8 server front-end)**|**Per server Standard Edition**|
|:-----|:-----|:-----|
|Chiamate in arrivo al secondo  <br/> |16  <br/> |2  <br/> |
|Chiamate simultanee connesse a IVR o MoH  <br/> |480  <br/> |60  <br/> |
|Sessioni anonime simultanee (senza messaggi istantanei)  <br/> |224  <br/> |28  <br/> |
|Sessioni anonime simultanee (con messaggistica istantanea)  <br/> |64  <br/> |8  <br/> |
|Agenti attivi (formali e informali)  <br/> |2400  <br/> |2400  <br/> |
|Numero di gruppi di ricerca  <br/> |800  <br/> |800  <br/> |
|Numero di gruppi IVR (usare il riconoscimento vocale)  <br/> |400  <br/> |400  <br/> |


