---
title: Pianificare riunioni di grandi dimensioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: "Riepilogo: leggere questo argomento per informazioni sulle procedure consigliate per l'implementazione e la gestione di riunioni di grandi dimensioni in Skype for Business Server."
ms.openlocfilehash: 136896a45be36508af419d84bc5bd684c9d8a429
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "36195876"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Pianificare riunioni di grandi dimensioni in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulle procedure consigliate per l'implementazione e la gestione di riunioni di grandi dimensioni in Skype for Business Server.
  
Le dimensioni delle riunioni supportate da Skype for Business Server variano a seconda che i servizi di conferenza siano ospitati in un pool condiviso o dedicato: da 250 partecipanti in un pool condiviso a 1000 partecipanti in un pool dedicato. 
  
> [!NOTE]
> Questo argomento è dedicato alle procedure consigliate per le riunioni di grandi dimensioni supportate da Skype for Business Server. Se l'organizzazione richiede funzionalità di riunione più ampie, è consigliabile implementare un ambiente ibrido che sfrutta Skype meeting broadcast, un nuovo servizio online che fa parte di Office 365. 

> [!NOTE]
> Skype meeting Broadcast consente agli utenti di ospitare e trasmettere riunioni a un pubblico online di grandi dimensioni fino a 10.000 partecipanti. L'uso di Skype meeting broadcast richiede che Skype for Business Server sia già configurato in una configurazione ibrida con un tenant di Office 365 di produzione. Tutti gli utenti devono avere un tenant online stabilito come prerequisito. Se si è interessati alla distribuzione di una soluzione ibrida che può trarre vantaggio da Skype meeting broadcast, vedere [cos'è un Skype meeting broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e [configurare la distribuzione locale per Skype meeting broadcast](../../deploy/configure-skype-meeting-broadcast.md). 
  
Le riunioni di grandi dimensioni in genere presentano le caratteristiche seguenti:
  
- Il formato della riunione è una presentazione uno-a-molti.
    
- Uno o più utenti sono relatori e tutti gli altri membri partecipano solo come partecipanti.
    
- La condivisione delle presentazioni di PowerPoint è l'attività di collaborazione dati principale.
    
- L'audio è obbligatorio e può essere usato anche il video.
    
- Una persona dedicata, in genere l'organizzatore della riunione o un assistente dell'organizzatore, configura bene la riunione in anticipo.
    
- Il personale dedicato (non i relatori) esegue la riunione, inclusa la connessione a una riunione online, verificando che l'audio, il video e la condivisione delle diapositive funzionino, gestiscono i ruoli di lobby e utenti, riattivano e riattivano i partecipanti, le domande e la gestione delle registrazioni, come appropriato.
    
Quando un utente pianifica una riunione, Skype for Business Server crea un record nel database dei servizi di conferenza, che archivia i dati di conferenza, ma non riserva le risorse hardware per la riunione pianificata prima del tempo. Skype for Business Server ha invece la logica di bilanciamento del carico predefinita per allocare dinamicamente le risorse di conferenza nei server front-end in modo da distribuire i carichi equamente in tutti i server front-end del pool. In questo modo vengono effettivamente rilevate e usate risorse hardware, ma è importante pianificare in modo appropriato il supporto di riunioni molto grandi. 
  
Ad esempio, quando un pool di Skype for Business Server sta per essere eseguito vicino alla sua capacità superiore, ogni server front-end può ospitare circa 125 riunioni di media dimensione. L'aggiunta di un'altra piccola riunione non è un problema, ma l'aggiunta di una riunione per gli utenti di 1000 sarebbe un problema, perché i server front-end probabilmente non sarebbero in grado di supportare una riunione di grandi dimensioni contemporaneamente alle altre riunioni di 125.
  
Per supportare riunioni di grandi dimensioni fino a 1000 partecipanti, è necessario risolvere i problemi relativi al modello hardware condiviso e al modello senza prenotazione. In generale, è necessario pianificare un pool dedicato e seguire le procedure consigliate descritte nelle sezioni seguenti. 
  
## <a name="plan-for-a-dedicated-pool"></a>Pianificare un pool dedicato

Se l'organizzazione richiede riunioni con più di 250 partecipanti, è necessario pianificare un pool dedicato per supportare il caricamento. 
  
Per avere sufficienti risorse di memoria e CPU per riunioni fino a 1000 utenti, i server front-end ospitanti non devono ospitare altri carichi di lavoro istantanei e di presenza o di Enterprise Voice. Anche i server non devono ospitare altre riunioni, indipendentemente dalle dimensioni delle altre riunioni. Per ospitare riunioni con un massimo di 1000 utenti, è necessario configurare un pool di Skype for Business Server distinto dedicato all'hosting di riunioni di grandi dimensioni.
  
Un pool di Skype for Business Server dedicato all'hosting di riunioni di grandi dimensioni dovrebbe ospitare una sola riunione di un massimo di 1000 utenti contemporaneamente, quindi è necessario prenotare i tempi di riunione in anticipo tramite un processo di pianificazione fuori banda per garantire un supporto dedicato dall' Server front-end. Per supportare più di una riunione di grandi dimensioni contemporaneamente, è necessario configurare più pool di riunioni di grandi dimensioni dedicati.
  
Per altre informazioni sui requisiti hardware e software e la pianificazione di una topologia che supporta riunioni di grandi dimensioni, vedere [requisiti hardware e software per i servizi di conferenza in Skype for Business Server](hardware-and-software-requirements.md) e [pianificare la topologia di conferenza per Skype for Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementare le procedure consigliate per riunioni di grandi dimensioni

Dopo aver configurato un pool dedicato per riunioni di grandi dimensioni, è possibile eseguire le operazioni necessarie per garantire che le riunioni di grandi dimensioni ospitate nel pool offrano la migliore esperienza utente. Le sezioni seguenti includono linee guida per la gestione di riunioni di grandi dimensioni:
  
- Creare organizzatori di riunioni dedicati
    
- Creare moderatori dedicati
    
- Gestire un calendario distinto di riunioni di grandi dimensioni
    
- Implementare un processo di pianificazione delle riunioni di grandi dimensioni
    
- Specificare i dettagli di pianificazione appropriati
    
- Creare criteri di conferenza per riunioni di grandi dimensioni
    
### <a name="create-dedicated-meeting-organizers"></a>Creare organizzatori di riunioni dedicati

Per ridurre al minimo il traffico delle comunicazioni in tempo reale nel pool di grandi riunioni, Microsoft non consiglia di ospitare gli utenti che accedono regolarmente tramite client Skype for business e partecipano a messaggistica istantanea, presenza, conferenza e sessioni vocali. Eseguire invece una delle operazioni seguenti:
  
- Creare uno o più account utente dedicati solo per la pianificazione di riunioni di grandi dimensioni
    
- Home gli account utente del personale responsabile per la pianificazione di riunioni di grandi dimensioni in un pool di grandi riunioni
    
### <a name="create-dedicated-moderators"></a>Creare moderatori dedicati

Con diverse centinaia di migliaia di utenti in una riunione, è buona norma avere una persona dedicata che modera la sessione online di una riunione di grandi dimensioni. Questa persona dedicata può essere un delegato dell'organizzatore della riunione o un membro del personale di supporto per la riunione di grandi dimensioni dell'organizzazione. È importante aggiungere il moderatore della riunione dedicato come relatore al momento della pianificazione della riunione, anche se è possibile promuovere un partecipante alla riunione online per il ruolo di relatore mentre la riunione è in corso.
  
Il moderatore della riunione può usare tutte le funzionalità di relatore dei client Skype for business per gestire la riunione di grandi dimensioni. Queste funzionalità includono:
  
- Monitorare la sala d'attesa e ammettere o rifiutare gli utenti nella sala di attesa
    
- Rimozione di tutti gli utenti dalla riunione che non devono partecipare alla riunione
    
- Modifica di tipi di accesso alle riunioni
    
- Modifica dei ruoli dei partecipanti
    
- Invitare altri partecipanti durante la riunione con funzionalità di trascinamento della selezione, chiamata telefonica esterna o posta elettronica
    
- Disattivare e riattivare il pubblico o i singoli utenti
    
- Gestione del contenuto della riunione, inclusi il caricamento del contenuto, l'eliminazione di contenuto e il passaggio di contenuto attivo

    
### <a name="maintain-a-separate-calendar"></a>Gestire un calendario separato

Per ogni pool di riunioni di grandi dimensioni, è necessario mantenere un calendario distinto delle riunioni di grandi dimensioni pianificate in tale pool. Ad esempio, è possibile inserire un singolo account utente nel pool di grandi riunioni e usare Outlook con il componente aggiuntivo riunioni di Exchange e online per Skype for business per mantenere un calendario distinto. Se si usano più account utente per consentire a un personale di supporto di creare riunioni di grandi dimensioni, è possibile configurare un calendario distinto che aggrega tutte le riunioni di grandi dimensioni create dai membri del personale di supporto. 
  
Il mantenimento di un calendario di riunioni di grandi dimensioni separato consente di evitare conflitti e di garantire che solo una riunione di grandi dimensioni sia attiva in qualsiasi momento.
  
### <a name="implement-a-scheduling-process"></a>Implementare un processo di pianificazione

Poiché è supportata solo una riunione di grandi dimensioni alla volta nel pool di riunioni di grandi dimensioni dedicato, è necessario implementare un processo di pianificazione delle riunioni di grandi dimensioni per facilitare la configurazione di riunioni di grandi dimensioni e impedire conflitti. Tale funzionalità non viene fornita direttamente da Skype for Business Server o da client Skype for business. Un modo per implementare un processo di questo tipo consiste nell'usare il sistema di ticketing del team di supporto dell'organizzazione, se disponibile.
  
La pianificazione di una riunione di grandi dimensioni prevede il completamento dei passaggi seguenti:
  
- L'organizzatore o il delegato della riunione determina l'ora, la durata e le dimensioni di una riunione imminente, oltre all'elenco di relatori. Se la dimensione prevista della riunione supera gli utenti di 250 o per garantire la migliore esperienza utente per una riunione con meno di 250 utenti, l'organizzatore o il delegato invia una richiesta per una riunione di grandi dimensioni.
    
- Il personale di pianificazione controlla se la data e l'ora richieste sono disponibili. Poiché supportiamo solo una singola riunione di grandi dimensioni nel pool dedicato alla volta, il personale di pianificazione deve controllare il calendario della riunione di grandi dimensioni per determinare se è prevista un'altra riunione per la data e l'ora richieste. Se il tempo richiesto è disponibile, il personale approva la convocazione di riunione.
    
- Se la richiesta è approvata, il personale di pianificazione (usando le credenziali nel pool dedicato) usa il componente aggiuntivo riunione online per Skype for business con Outlook per configurare una riunione nel pool di grandi riunioni dedicato. L'URL da usare per partecipare alla riunione viene fornito al richiedente come parte della notifica di approvazione.
    
- L'organizzatore o il delegato della riunione usa Outlook per pianificare la riunione imminente, aggiungendo l'URL per partecipare alla riunione all'invito alla riunione. L'organizzatore della riunione o il delegato specifica quindi agli utenti di essere invitati e invia l'invito alla riunione.
    
### <a name="specify-appropriate-scheduling-details"></a>Specificare i dettagli di pianificazione appropriati

Dopo aver verificato che non sia prevista nessun'altra riunione al momento richiesto, il personale di supporto per le riunioni di grandi dimensioni che gestisce la richiesta pianifica la riunione nel pool di grandi riunioni. 
  
Per garantire la migliore esperienza utente, è importante pianificare la riunione di grandi dimensioni con i livelli di accesso corretti e le impostazioni delle riunioni appropriate per le esigenze dell'organizzatore della riunione. Considerare le impostazioni di pianificazione seguenti configurate nelle opzioni delle riunioni Skype for business:
  
- Usare un nuovo spazio per riunioni per ogni riunione di grandi dimensioni invece di riutilizzare lo spazio dedicato per le riunioni. 
    
- Specificare il livello di accesso alla riunione come indicato di seguito:
    
  - Se almeno un invitato è esterno all'organizzazione, imposta il tipo di accesso alla riunione a **chiunque (nessuna restrizione)**. In questo modo è possibile evitare di dover gestire una sala di attesa potenzialmente grande quando la riunione è in corso.
    
  - Se la riunione è una riunione interna, impostare il tipo di accesso alla riunione per **tutti gli utenti dell'organizzazione**.
    
    > [!NOTE]
    > Evitare di impostare il tipo di accesso alla riunione per le **persone che invito dalla mia società** perché quando si usa questa impostazione, gli organizzatori devono aggiungere tutti gli indirizzi di posta elettronica dell'utente all'elenco di invitati e non è possibile invitare un gruppo di distribuzione. Evitare di impostare il tipo di accesso alla riunione **solo a me, l'organizzatore della riunione** perché questa impostazione richiede che ogni partecipante alla riunione, inclusi i relatori, debba essere inserito nella sala di attesa in fase di esecuzione della riunione. La persona responsabile dell'uso della riunione di grandi dimensioni deve quindi monitorare costantemente il roster della sala di attesa e ammettere nuovi utenti che si trovano nell'atrio.
  
- Consentire agli utenti che accedono tramite telefono di accedere automaticamente alla riunione controllando che i **chiamanti entrino direttamente nell'** impostazione.
    
- Invitare esplicitamente gli utenti seguenti:
    
  - Organizzatore della riunione e delegato (richiedente)
    
  - Elenco di relatori forniti da un richiedente di una riunione
    
    > [!NOTE]
    > Se il tipo di accesso alla riunione è impostato per gli **utenti scelti**, è necessario aggiungere esplicitamente ogni partecipante di una riunione di grandi dimensioni come invito della riunione. 
  
- Gestisci esplicitamente i relatori, invece di impostare l'opzione Presenter su uno dei valori di promozione automatica. Assicurarsi di aggiungere gli utenti seguenti come relatori:
    
  - Organizzatore della riunione e delegato (richiedente)
    
  - Elenco di relatori forniti da convocazione di riunione di grandi dimensioni
    
    Con la gestione esplicita dei relatori, puoi limitare i relatori a un numero abbastanza piccolo per poter avere una riunione di grandi dimensioni effettiva. Se la maggior parte dei partecipanti alla riunione ha il ruolo di partecipante, consente di ridurre la probabilità che le persone prendano accidentalmente il controllo della presentazione, eliminando una presentazione di PowerPoint, riattivando o disattivando i relatori e altre interruzioni alla riunione. 
    
- Selezionare l'impostazione **Disattiva tutti i partecipanti** per verificare che solo i relatori possano trasmettere l'audio alla riunione.
    
- Controlla l'impostazione del **video dei partecipanti al blocco** per verificare che solo i relatori possano trasmettere video alla riunione.
    
### <a name="create-a-conferencing-policy"></a>Creare un criterio di conferenza

Creare un nuovo criterio di conferenza in modo specifico per riunioni di grandi dimensioni e quindi assegnare i criteri per i servizi di conferenza agli utenti residenti nel pool di grandi riunioni dedicato. Configurare i criteri di conferenza con le impostazioni seguenti:
  
- Impostare l'opzione **MaxMeetingSize** su 1000. (Il valore predefinito è 250).
    
- Imposta l'opzione **AllowLargeMeetings** su **true**. 
    
- Impostare l'opzione **EnableAppDesktopSharing** su **None**.
    
- Imposta l'opzione **AllowUserToScheduleMeetingsWithAppSharing** su **false**.
    
- Imposta l'opzione **AllowSharedNotes** su **false**.
    
- Imposta l'opzione **AllowAnnotations** su **false**.
    
- Imposta l'opzione **DisablePowerPointAnnotations** su **true**.
    
- Imposta l'opzione **AllowMultiview** su **false**.
    
- Imposta l'opzione **EnableMultiviewJoin** su **false**.
    
> [!NOTE]
> Il supporto per riunioni di grandi dimensioni in Skype for Business Server richiede che l'impostazione **AllowLargeMeetings** sia impostata su true. Quando questa impostazione è impostata su true, l'esperienza di Skype for business verrà ottimizzata per riunioni extra-large quando gli utenti partecipano alla riunione. In particolare, in una riunione di grandi dimensioni, Skype for business non visualizzerà l'iniziale o l'aggiornamento dell'elenco dei partecipanti alla riunione completa, che è un collo di bottiglia delle prestazioni sia per il client che per Skype for Business Server. Skype for business visualizzerà invece solo le informazioni sull'utente e l'elenco dei relatori della riunione. Skype for Business mostrerà ancora il numero totale di partecipanti disponibili nelle riunioni di grandi dimensioni.

L'impostazione di **$true AllowLargeMeetings** causa le operazioni seguenti:

- Nasconde l'elenco dei partecipanti. 

- Disabilita gli errori nella finestra di messaggistica istantanea.

- Disabilita il video a più parti.

- Disabilita la possibilità di promuovere un partecipante a relatore. È necessario pianificare in anticipo e dichiarare tutti i relatori prima della riunione.

- Disabilita la possibilità di riattivare l'audio dei singoli partecipanti.

- Disabilita la possibilità di applicare la funzionalità blocca video Spotlight ai partecipanti.

- La chiamata PSTN in utenti non sarà in grado di riattivare l'audio con 6, perché manca l'assistenza virtuale personale responsabile dei comandi DTMF in riunioni di grandi dimensioni attive.

- Se il relatore/organizzatore pianifica una riunione in cui tutti devono essere disattivati prima di tutto ("Disattiva tutto"), gli utenti PSTN verranno disattivati durante la chiamata e non saranno in grado di riattivare l'audio.

Fatta eccezione per le **dimensioni massime della riunione** , tutte le altre impostazioni dei criteri di conferenza specificate in questo articolo sono necessarie per disabilitare le funzionalità di conferenza che non sono necessarie in riunioni di grandi dimensioni.
  
Inoltre, è necessario configurare il pool di grandi riunioni dedicato in modo che ogni utente di Skype for Business Server ospitato nel pool e responsabile della gestione della pianificazione delle riunioni disponga delle autorizzazioni appropriate. Per eseguire questa operazione, eseguire le operazioni seguenti:
  
- Impostare l'opzione **designa come** relatore su **nessuno**. In genere, uno o pochi utenti di tutti i partecipanti a una riunione di grandi dimensioni sono relatori, quindi i partecipanti non devono essere ammessi automaticamente alle riunioni di grandi dimensioni come relatori. Al contrario, i relatori devono essere designati in modo esplicito al momento della riunione o essere promossi esplicitamente durante la riunione di grandi dimensioni.
    
- Verificare che la casella **di controllo tipo di conferenza assegnata per impostazione predefinita** non sia selezionata. Questa impostazione controlla se il componente aggiuntivo riunione online per Skype for business Pianifica sempre le conferenze con la conferenza assegnata dell'organizzatore, in modo che le riunioni pianificate abbiano lo stesso URL di join e le informazioni audio. Negli scenari di collaborazione in piccoli gruppi, il tipo di conferenza assegnata funziona bene perché ognuno ha una propria conferenza assegnata individualmente e l'URL di join costante e le informazioni audio contribuiscono a facilitare l'Unione delle riunioni. Nello scenario della riunione di grandi dimensioni, tuttavia, il personale di supporto per le riunioni di grandi dimensioni pianifica le riunioni di grandi dimensioni con un singolo set di credenziali utente e quindi fornisce URL di join e informazioni audio ai richiedenti della riunione. In questo caso, l'uso di un URL diverso per partecipare a una riunione funziona meglio.
    
- Verificare che la casella **di controllo Ammetti gli utenti anonimi per impostazione predefinita** non sia selezionata, a meno che non sia obbligatoria. Questa impostazione ha effetto sul tipo di accesso alle riunioni predefinito programmato dal componente aggiuntivo riunione online per Skype for business quando non si usa una conferenza assegnata. L'opzione appropriata per questa impostazione dipende dalle esigenze dell'organizzazione. Se la maggior parte delle riunioni di grandi dimensioni per l'organizzazione è riunioni interne, non selezionare questa opzione. Se la maggior parte delle riunioni di grandi dimensioni richiede che gli utenti esterni possano partecipare, selezionare questa opzione.
    
Per altre informazioni sulla creazione di criteri di conferenza, vedere [gestire i criteri di conferenza in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

