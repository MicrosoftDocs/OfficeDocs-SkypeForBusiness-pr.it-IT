---
title: Pianificare riunioni di grandi dimensioni in Skype for Business Server
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
ms.assetid: 21507e18-bd79-4019-9c3a-0867fccaa3b4
description: "Riepilogo: leggere questo argomento per informazioni sulle procedure consigliate per l'implementazione e la gestione di riunioni di grandi dimensioni in Skype for Business Server."
ms.openlocfilehash: 8e982f08b1ff65ac6a4ea6f47a15e57f1eded163
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813976"
---
# <a name="plan-for-large-meetings-in-skype-for-business-server"></a>Pianificare riunioni di grandi dimensioni in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulle procedure consigliate per l'implementazione e la gestione di riunioni di grandi dimensioni in Skype for Business Server.
  
Le dimensioni delle riunioni supportate da Skype for Business Server dipendono dal fatto che i servizi di conferenza siano ospitati in un pool condiviso o dedicato: dovunque da 250 partecipanti in un pool condiviso a 1000 partecipanti in un pool dedicato. 
  
> [!NOTE]
> Questo argomento è dedicato alle procedure consigliate per le riunioni di grandi dimensioni supportate da Skype for Business Server. Se l'organizzazione richiede funzionalità di riunione più estese, è consigliabile implementare un ambiente ibrido che si avvale di Skype meeting broadcast, un nuovo servizio online che fa parte di Microsoft 365 e Office 365. 

> [!NOTE]
> Skype meeting Broadcast consente agli utenti di ospitare e trasmettere riunioni a grandi gruppi di destinatari online fino a 10.000 partecipanti. L'uso di Skype meeting broadcast richiede che Skype for Business Server sia già configurato in una configurazione ibrida con un'organizzazione di produzione Microsoft 365 o Office 365. Tutti gli utenti devono disporre di un tenant online definito come prerequisito. Se si è interessati alla distribuzione di una soluzione ibrida che può usufruire di Skype meeting broadcast, vedere [che cos'è un Skype meeting broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e [configurare la distribuzione locale per Skype meeting broadcast](../../deploy/configure-skype-meeting-broadcast.md). 
  
Le riunioni di grandi dimensioni presentano in genere le caratteristiche seguenti:
  
- La riunione è una presentazione uno a molti.
    
- Pochi utenti hanno il ruolo di relatori o il relatore è uno solo e gli altri utenti sono solo partecipanti.
    
- La principale attività di collaborazione dati è la condivisione di presentazioni di PowerPoint.
    
- L'audio è indispensabile e possono essere usate anche le funzionalità video.
    
- Una persona dedicata, generalmente l'organizzatore della riunione o un assistente all'organizzatore, configura bene la riunione in anticipo.
    
- Uno staff dedicato (non i relatori) si occupa di aspetti della riunione quali la connessione alla riunione online, la verifica del funzionamento di audio, video e condivisione delle diapositive, la gestione della sala di attesa e dei ruoli utente, la disattivazione e la riattivazione dell'audio dei partecipanti, la raccolta delle domande e la gestione delle registrazione, come più opportuno.
    
Quando un utente pianifica una riunione, in Skype for Business Server viene creato un record nel database delle conferenze, in cui sono archiviati i dati per le conferenze, ma non vengono riservate risorse hardware per la riunione pianificata prima del tempo. Invece, Skype for Business Server dispone di una logica di bilanciamento del carico incorporata per allocare dinamicamente le risorse di conferenza nei front end server in modo da distribuire i carichi equamente in tutti i Front End Server nel pool. In questo modo, vengono riportate e utilizzate risorse hardware, ma è importante pianificare adeguatamente le riunioni di grandi dimensioni. 
  
Ad esempio, quando un pool di Skype for Business Server è in esecuzione vicino alla sua capacità superiore, ogni Front End Server potrebbe ospitare circa 125 riunioni di medie dimensioni. L'aggiunta di un'altra riunione di piccole dimensioni non è un problema, ma l'aggiunta di una riunione per gli utenti di 1000 potrebbe essere un problema perché i front end server probabilmente non sarebbero in grado di supportare una riunione di grandi dimensioni contemporaneamente alle altre riunioni di 125.
  
Il supporto di riunioni di grandi dimensioni con un massimo di 1000 partecipanti richiede la risoluzione dei problemi relativi al modello hardware condiviso e al modello senza prenotazione. In generale, è necessario pianificare un pool dedicato e seguire le procedure consigliate descritte nelle sezioni seguenti. 
  
## <a name="plan-for-a-dedicated-pool"></a>Pianificare un pool dedicato

Se l'organizzazione richiede riunioni con più di 250 partecipanti, è necessario pianificare un pool dedicato per supportare il carico. 
  
Per disporre di risorse di memoria e CPU sufficienti per riunioni fino a 1000 utenti, i front end server host non devono ospitare altri carichi di lavoro per la messaggistica istantanea e la presenza o VoIP aziendale. Anche i server non devono ospitare altre riunioni, indipendentemente dalle dimensioni delle altre riunioni. Per ospitare riunioni con un massimo di 1000 utenti, è necessario configurare un pool di Skype for Business Server separato dedicato all'hosting di riunioni di grandi dimensioni.
  
Un pool di Skype for Business Server dedicato all'hosting di riunioni di grandi dimensioni deve ospitare una sola riunione fino a 1000 utenti contemporaneamente, quindi è necessario che i tempi di riunione siano prenotati in anticipo tramite un processo di pianificazione fuori banda per garantire un supporto dedicato dai Front End Server. Per supportare più di una riunione di grandi dimensioni contemporaneamente, è necessario configurare più pool di riunioni di grandi dimensioni dedicati.
  
Per ulteriori informazioni sui requisiti hardware e software e sulla pianificazione di una topologia che supporta riunioni di grandi dimensioni, vedere [hardware and software requirements for Conferencing in Skype for Business Server](hardware-and-software-requirements.md) e [plan your Conferencing topologie for Skype for Business Server](conferencing-topology.md).
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementare le procedure consigliate per le riunioni di grandi dimensioni

Dopo aver configurato un pool dedicato per riunioni di grandi dimensioni, è possibile eseguire le operazioni necessarie per garantire che le riunioni di grandi dimensioni ospitate nel pool offrano la migliore esperienza utente. Nelle sezioni seguenti vengono fornite linee guida per la gestione delle riunioni di grandi dimensioni:
  
- Creare organizzatori di riunioni dedicati
    
- Creare moderatori dedicati
    
- Mantenere un calendario separato di riunioni di grandi dimensioni
    
- Implementare un processo di pianificazione delle riunioni di grandi dimensioni
    
- Specificare i dettagli di pianificazione corretti
    
- Creare criteri di conferenza per riunioni di grandi dimensioni
    
### <a name="create-dedicated-meeting-organizers"></a>Creare organizzatori di riunioni dedicati

Per ridurre al minimo il traffico di comunicazione in tempo reale nel pool di riunioni di grandi dimensioni, Microsoft non consiglia l'hosting degli utenti che effettuano regolarmente l'accesso utilizzando client Skype for business e partecipano a sessioni di messaggistica istantanea, presenza, conferenza e vocali. Eseguire invece una delle operazioni seguenti:
  
- Creare uno o più account utente dedicati solo per la pianificazione di riunioni di grandi dimensioni
    
- Home gli account utente del personale responsabile della pianificazione di riunioni di grandi dimensioni in un pool di riunioni di grandi dimensioni
    
### <a name="create-dedicated-moderators"></a>Creare moderatori dedicati

Con diverse centinaia di migliaia di utenti in una riunione, è consigliabile avere una persona dedicata a moderare la sessione online di una riunione di grandi dimensioni. Questa persona dedicata può essere un delegato dell'organizzatore della riunione o un membro del personale di supporto per le riunioni di grandi dimensioni dell'organizzazione. È importante aggiungere il moderatore dedicato di una riunione come relatore al momento della pianificazione della riunione, sebbene sia possibile alzare di livello un partecipante della riunione online al ruolo di relatore nel corso della riunione.
  
Il moderatore della riunione può utilizzare tutte le funzionalità di Presenter dei client Skype for business per gestire la riunione di grandi dimensioni. Tra queste funzionalità sono incluse le seguenti:
  
- Monitoraggio della lobby e ammissione o rifiuto degli utenti nella sala di attesa
    
- Rimozione di tutti gli utenti dalla riunione che non devono essere presenti nella riunione
    
- Modifica di tipi di accesso alle riunioni
    
- Modifica dei ruoli dei partecipanti
    
- Invitare altri partecipanti durante la riunione utilizzando la funzionalità di trascinamento della selezione, la chiamata esterna o la posta elettronica
    
- Muting e riattivazione del gruppo di destinatari o di singoli utenti
    
- Gestione del contenuto delle riunioni, incluso il caricamento del contenuto, l'eliminazione del contenuto e il passaggio di contenuto attivo

    
### <a name="maintain-a-separate-calendar"></a>Mantenere un calendario separato

Per ogni pool di riunioni di grandi dimensioni, è necessario mantenere un calendario distinto di riunioni di grandi dimensioni pianificate in tale pool. Ad esempio, è possibile ospitare un singolo account utente nel pool di riunioni di grandi dimensioni e utilizzare Outlook con il componente aggiuntivo meeting di Exchange e online per Skype for business per mantenere un calendario distinto. Se si utilizzano più account utente per consentire a un team di supporto di creare riunioni di grandi dimensioni, è possibile configurare un calendario distinto che aggrega tutte le riunioni di grandi dimensioni create dai membri del personale di supporto. 
  
La gestione di un calendario di riunioni di grandi dimensioni separato contribuisce a impedire conflitti e a garantire che sia attiva solo una riunione di grandi dimensioni in qualsiasi momento.
  
### <a name="implement-a-scheduling-process"></a>Implementazione di un processo di pianificazione

Poiché solo una riunione di grandi dimensioni alla volta è supportata nel pool di riunioni di grandi dimensioni dedicato, è necessario implementare un processo di pianificazione delle riunioni di grandi dimensioni per facilitare la configurazione di riunioni di grandi dimensioni e impedire conflitti. Tale funzionalità non viene fornita direttamente dai client Skype for Business Server o Skype for business. Un modo per implementare un processo di questo tipo consiste nell'utilizzare il sistema di ticketing del team di supporto dell'organizzazione, se disponibile.
  
La pianificazione di una riunione di grandi dimensioni comporta il completamento dei passaggi seguenti:
  
- L'organizzatore della riunione o il delegato stabilisce data e ora, durata e dimensioni di una riunione prossima, oltre all'elenco dei relatori. Se le dimensioni previste per la riunione superano i 250 utenti oppure per assicurare un'esperienza utente ottimale per una riunione con meno di 250 utenti, l'organizzatore o il delegato invia una richiesta per una riunione di grandi dimensioni.
    
- Il personale addetto della pianificazione verifica se la data e l'ora richieste sono disponibili. Dato che nel pool dedicato è supportata una sola riunione di grandi dimensioni alla volta, il personale addetto alla pianificazione deve controllare il calendario di questo tipo di riunioni per stabilire se ne è già presente un'altra pianificata per la data e l'ora richieste. Se l'intervallo di tempo richiesto risulta disponibile, la richiesta di riunione viene approvata.
    
- Se la richiesta è stata approvata, il personale di pianificazione (utilizzando le credenziali nel pool dedicato) utilizza il componente aggiuntivo per riunioni online per Skype for business con Outlook per impostare una riunione nel pool di riunioni di grandi dimensioni dedicato. L'URL da utilizzare per partecipare alla riunione viene fornito al richiedente nell'ambito della notifica dell'approvazione.
    
- L'organizzatore della riunione o il delegato utilizza Outlook per pianificare la riunione imminente, aggiungendo l'URL per la partecipazione alla riunione all'invito alla riunione. L'organizzatore della riunione o il delegato specifica quindi gli utenti da invitare e invia l'invito alla riunione.
    
### <a name="specify-appropriate-scheduling-details"></a>Specificare i dettagli di pianificazione corretti

Dopo avere verificato che nel periodo di tempo richiesto non sono pianificate altre riunioni, il personale di supporto delle riunioni di grandi dimensioni che gestisce le richieste pianifica la riunione nel pool di riunioni di grandi dimensioni. 
  
Per garantire la migliore esperienza utente, è importante pianificare la riunione di grandi dimensioni con i livelli di accesso giusti e le impostazioni di riunione appropriate per le esigenze dell'organizzatore della riunione. Si consideri le seguenti impostazioni di pianificazione configurate nelle opzioni di riunioni di Skype for business:
  
- Usare una nuova area riunioni per ciascuna riunione di grandi dimensioni anziché riutilizzare l'area riunione dedicata. 
    
- Specificare il livello di accesso alla riunione come segue:
    
  - Se almeno un invitato è esterno all'organizzazione, impostare il tipo di accesso alla riunione su **tutti gli utenti (nessuna restrizione)**. Ciò consente di evitare di dover gestire una sala d'attesa di dimensioni potenzialmente grandi quando la riunione è in corso.
    
  - Se la riunione prevede solo partecipanti interni, impostare il tipo di accesso su **Tutti gli utenti dell'organizzazione**.
    
    > [!NOTE]
    > Evitare di impostare il tipo di accesso alla riunione su **Persone invitate appartenenti alla società** perché questa impostazione costringe gli organizzatori ad aggiungere all'elenco degli invitati tutti gli indirizzi di posta elettronica degli utenti e non è possibile invitare un gruppo di distribuzione. Evitare di impostare il tipo di accesso alla riunione su **Solo io, l'organizzatore della riunione** perché questa impostazione richiede che ciascun partecipante, inclusi i relatori, stiano in sala d'attesa durante l'esecuzione della riunione. La persona responsabile della riunione di grandi dimensioni deve quindi costantemente monitorare l'elenco della sala d'attesa e ammettere i nuovi utenti che si trovano in sala d'attesa.
  
- Selezionare l'opzione **Consenti ai chiamanti di entrare direttamente** per consentire agli utenti che accedono dall'esterno mediante chiamata telefonica di accedere alla riunione automaticamente.
    
- Invitare esplicitamente gli utenti seguenti:
    
  - Organizzatore della riunione e delegato (richiedente)
    
  - L'elenco dei relatori fornito da un richiedente della riunione
    
    > [!NOTE]
    > Se il tipo di accesso alla riunione è impostato su **Persone scelte dall'utente**, è necessario aggiungere esplicitamente come invitato ciascun partecipante di una riunione di grandi dimensioni. 
  
- Gestire esplicitamente i relatori anziché impostare l'opzione su uno dei valori di promozione automatica. Assicurarsi di aggiungere gli utenti seguenti come relatori:
    
  - Organizzatore della riunione e delegato (richiedente)
    
  - L'elenco dei relatori fornito dai richiedenti di riunioni di grandi dimensioni
    
    Tramite la gestione esplicita dei relatori, è possibile limitare i relatori a un numero sufficientemente piccolo per rendere possibile una riunione di grandi dimensioni efficace. Se la maggioranza dei partecipanti alla riunione dispone del ruolo di partecipante, si riducono le probabilità che i partecipanti assumano per errore il controllo della presentazione, eliminino una presentazione di PowerPoint, disattivino/attivino l'audio dei relatori o siano causa di altre interruzioni della riunione. 
    
- Selezionare l'impostazione **Disattiva l'audio di tutti i partecipanti** per fare in modo che durante la riunione venga trasmesso solo l'audio dei relatori.
    
- Controllare l'impostazione **video dei partecipanti del blocco** per assicurarsi che solo i relatori possano trasmettere video alla riunione.
    
### <a name="create-a-conferencing-policy"></a>Creazione di un criterio di conferenza

Creare un nuovo criterio conferenza in modo specifico per riunioni di grandi dimensioni e quindi assegnare i criteri di conferenza agli utenti che si trovano nel pool di riunioni di grandi dimensioni dedicato. Configurare il criterio per conferenze con le impostazioni seguenti:
  
- Impostare l'opzione **MaxMeetingSize** su 1000. Il valore predefinito è 250.
    
- Impostare l'opzione **AllowLargeMeetings** su **True**. 
    
- Impostare l'opzione **EnableAppDesktopSharing** su **None**.
    
- Impostare l'opzione **AllowUserToScheduleMeetingsWithAppSharing** su **False**.
    
- Impostare l'opzione **AllowSharedNotes** su **False**.
    
- Impostare l'opzione **AllowAnnotations** su **False**.
    
- Impostare l'opzione **DisablePowerPointAnnotations** su **True**.
    
- Impostare l'opzione **AllowMultiview** su **False**.
    
- Impostare l'opzione **EnableMultiviewJoin** su **False**.
    
> [!NOTE]
> Il supporto per le riunioni di grandi dimensioni in Skype for Business Server richiede che l'impostazione **AllowLargeMeetings** sia impostata su true. Quando questa impostazione è impostata su true, l'esperienza Skype for business sarà ottimizzata per le riunioni di grandi dimensioni quando gli utenti partecipano alla riunione. In particolare, in una riunione di grandi dimensioni, Skype for business non mostrerà l'iniziale o l'aggiornamento dell'elenco dei partecipanti alla riunione completo, che è un collo di bottiglia delle prestazioni sia per il client che per il server Skype for business. Invece, Skype for Business mostrerà solo informazioni sull'utente e l'elenco dei relatori della riunione. Skype for Business mostrerà ancora il numero totale di partecipanti disponibili nelle riunioni di grandi dimensioni.

L'impostazione di **$true di AllowLargeMeetings** determina quanto segue:

- Nasconde l'elenco dei partecipanti. 

- Disattiva gli errori nella finestra di messaggistica istantanea.

- Disattiva la funzionalità video a più parti.

- Disattiva la possibilità di promuovere un partecipante al relatore. Prima della riunione è necessario pianificare in anticipo e dichiarare tutti i relatori.

- Disattiva la possibilità di riattivare i singoli partecipanti.

- Disattiva la possibilità di applicare la funzionalità blocca video Spotlight ai partecipanti.

- La connessione PSTN negli utenti non sarà in grado di riattivarsi usando 6 perché manca l'assistenza virtuale personale responsabile dei comandi DTMF nelle riunioni di grandi dimensioni attive.

- Se il relatore/organizzatore pianifica una riunione in cui tutti gli utenti devono essere disattivati per primo ("Disattiva tutto"), i clienti PSTN vengono disattivati durante la chiamata e non saranno in grado di riattivarsi.

Ad eccezione dell'impostazione **Dimensione massima riunione**, tutti gli altri criteri di conferenza specificati qui sono necessari per disabilitare le funzionalità di conferenza non necessarie in riunioni di grandi dimensioni.
  
Inoltre, è necessario configurare il pool di riunioni di grandi dimensioni dedicato in modo che ogni utente di Skype for Business Server ospitato nel pool e responsabile della gestione della pianificazione delle riunioni disponga delle autorizzazioni appropriate. A tale scopo, procedere come segue:
  
- Impostare l'opzione **Designa come relatore** a **Nessuno**. In genere, uno o pochi altri utenti tra tutti i partecipanti a una riunione di grandi dimensioni sono relatori, pertanto i partecipanti non devono essere automaticamente ammessi a riunioni di grandi dimensioni come relatori. I relatori dovrebbero invece essere designati in modo esplicito al momento di pianificare la riunione oppure durante la riunione stessa.
    
- Accertarsi che la casella di controllo **Tipo di conferenza assegnato per impostazione predefinita** non sia selezionata. Questa impostazione consente di controllare se il componente aggiuntivo per riunioni online per Skype for business Pianifica sempre le conferenze utilizzando la conferenza assegnata dall'organizzatore, il che significa che le riunioni pianificate hanno lo stesso URL di join e le informazioni audio. In scenari di collaborazione di piccoli gruppi, l'assegnazione di un tipo di conferenza funziona bene perché ognuno dispone di una conferenza individuale assegnata e l'URL di accesso e le informazioni audio consentono di agevolare un più rapido accesso alla riunione. Tuttavia, in scenari con riunioni di grandi dimensioni, il personale di queste ultime pianifica le riunioni più grandi con un singolo set di credenziali utente, e quindi offre URL di accesso e informazioni sull'audio al richiedente il meeting. In questo caso, l'uso di un URL diverso per accedere a ogni riunione funziona bene.
    
- Accettarsi che la casella di controllo **Consenti utenti anonimi per impostazione predefinita** non è selezionata a meno che non sia necessario. Questa impostazione influisce sul tipo di accesso alle riunioni predefinito programmato dal componente aggiuntivo per riunioni online per Skype for business quando non si utilizza una conferenza assegnata. L'opzione appropriata per questa impostazione dipende dalle esigenze dell'organizzazione. Se la maggior parte delle riunioni di grandi dimensioni nell'organizzazione è interna, non selezionare questa opzione. Se per la maggior parte delle riunioni di grandi dimensioni è prevista la partecipazione di  utenti esterni, selezionare questa opzione.
    
Per ulteriori informazioni sulla creazione di un criterio di conferenza, vedere [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  

