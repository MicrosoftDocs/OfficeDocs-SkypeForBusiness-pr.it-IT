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
  
Le dimensioni delle riunioni supportate da Skype for Business Server dipendono dal fatto che le conferenze siano ospitate in un pool condiviso o dedicato: da 250 partecipanti in un pool condiviso a 1000 partecipanti in un pool dedicato. 
  
> [!NOTE]
> In questo argomento vengono trattate le procedure consigliate per le riunioni di grandi dimensioni supportate da Skype for Business Server. Se l'organizzazione richiede funzionalità di riunione più grandi, è consigliabile implementare un ambiente ibrido che sfrutta Skype Meeting Broadcast, un nuovo servizio online che fa parte di Microsoft 365 e Office 365. 

> [!NOTE]
> Skype Meeting Broadcast consente agli utenti di ospitare e trasmettere riunioni a grandi gruppi di destinatari online fino a 10.000 partecipanti. L'uso di Skype Meeting Broadcast richiede che Skype for Business Server sia già configurato in una configurazione ibrida con un'organizzazione di Produzione di Microsoft 365 o Office 365. Tutti gli utenti devono disporre di un tenant online stabilito come prerequisito. Se si è interessati alla distribuzione di una soluzione ibrida in grado di sfruttare Skype Meeting Broadcast, vedere Che cos'è [Skype Meeting Broadcast e](https://go.microsoft.com/fwlink/?LinkId=617071) Configurare la distribuzione locale per Skype Meeting [Broadcast.](../../deploy/configure-skype-meeting-broadcast.md) 
  
Le riunioni di grandi dimensioni hanno in genere le caratteristiche seguenti:
  
- La riunione è una presentazione uno a molti.
    
- Pochi utenti hanno il ruolo di relatori o il relatore è uno solo e gli altri utenti sono solo partecipanti.
    
- La principale attività di collaborazione dati è la condivisione di presentazioni di PowerPoint.
    
- L'audio è indispensabile e possono essere usate anche le funzionalità video.
    
- Una persona dedicata, in genere l'organizzatore della riunione o un assistente dell'organizzatore, configura la riunione con largo anticipo.
    
- Uno staff dedicato (non i relatori) si occupa di aspetti della riunione quali la connessione alla riunione online, la verifica del funzionamento di audio, video e condivisione delle diapositive, la gestione della sala di attesa e dei ruoli utente, la disattivazione e la riattivazione dell'audio dei partecipanti, la raccolta delle domande e la gestione delle registrazione, come più opportuno.
    
Quando un utente pianifica una riunione, Skype for Business Server crea un record nel database delle conferenze, in cui vengono archiviati i dati delle conferenze, ma non riserva alcuna risorsa hardware per la riunione pianificata in anticipo. Skype for Business Server dispone invece di una logica di bilanciamento del carico incorporata per allocare dinamicamente le risorse di conferenza nei Front End Server in modo da distribuire equamente i carichi in tutti i Front End Server del pool. Ciò consente di eseguire in modo efficace il provisioning e l'utilizzo di risorse hardware, ma è importante pianificare in modo appropriato per supportare riunioni di grandi dimensioni. 
  
Ad esempio, quando un pool di Skype for Business Server è in esecuzione vicino alla capacità massima, ogni Front End Server potrebbe ospitare circa 125 riunioni di medie dimensioni. L'aggiunta di un'altra riunione di piccole dimensioni non sarebbe un problema, ma l'aggiunta di una riunione per 1000 utenti sarebbe un problema perché i Front End Server probabilmente non sarebbero in grado di supportare una riunione così grande contemporaneamente alle altre 125 riunioni.
  
Per supportare riunioni di grandi dimensioni con un massimo di 1000 partecipanti, è necessario risolvere i problemi relativi sia al modello hardware condiviso che al modello senza prenotazione. In generale, è necessario pianificare un pool dedicato e seguire le procedure consigliate descritte nelle sezioni seguenti. 
  
## <a name="plan-for-a-dedicated-pool"></a>Pianificare un pool dedicato

Se l'organizzazione richiede riunioni con più di 250 partecipanti, è necessario pianificare un pool dedicato per supportare il carico. 
  
Per disporre di risorse di CPU e memoria sufficienti per riunioni con un massimo di 1000 utenti, i Front End Server di hosting non devono ospitare altri carichi di lavoro di messaggistica istantanea, presenza o VoIP aziendale. I server non devono inoltre ospitare altre riunioni, indipendentemente dalle dimensioni delle altre riunioni. Per ospitare riunioni con un massimo di 1000 utenti, è necessario configurare un pool Skype for Business Server separato dedicato all'hosting di riunioni di grandi dimensioni.
  
Un pool di Skype for Business Server dedicato all'hosting di riunioni di grandi dimensioni deve ospitare una e una sola riunione con un massimo di 1000 utenti contemporaneamente, pertanto gli orari delle riunioni devono essere riservati in anticipo tramite un processo di pianificazione fuori banda per garantire il supporto dedicato dai Front End Server. Per supportare più riunioni di grandi dimensioni contemporaneamente, è consigliabile configurare più pool dedicati per le riunioni di grandi dimensioni.
  
Per ulteriori informazioni sui requisiti hardware e software e sulla pianificazione di una topologia che supporti riunioni di grandi dimensioni, vedere Requisiti hardware e software per le conferenze [in Skype for Business Server](hardware-and-software-requirements.md) e Pianificare la topologia di conferenza per Skype for Business [Server.](conferencing-topology.md)
  
## <a name="implement-best-practices-for-large-meetings"></a>Implementare le procedure consigliate per le riunioni di grandi dimensioni

Dopo aver impostato un pool dedicato per le riunioni di grandi dimensioni, è possibile eseguire le operazioni necessarie per garantire che le riunioni di grandi dimensioni ospitate nel pool forniranno la migliore esperienza utente. Nelle sezioni seguenti vengono fornite linee guida per la gestione di riunioni di grandi dimensioni:
  
- Creare organizzatori di riunioni dedicati
    
- Creare moderatori dedicati
    
- Gestire un calendario separato di riunioni di grandi dimensioni
    
- Implementare un processo di pianificazione delle riunioni di grandi dimensioni
    
- Specificare i dettagli di pianificazione appropriati
    
- Creare criteri di conferenza per riunioni di grandi dimensioni
    
### <a name="create-dedicated-meeting-organizers"></a>Creare organizzatori di riunioni dedicati

Per ridurre al minimo il traffico di comunicazioni in tempo reale nel pool di riunioni di grandi dimensioni, Microsoft non consiglia di ospitare gli utenti che a loro volta a un accesso con regolarità utilizzano i client Skype for Business e partecipano a sessioni di messaggistica istantanea, presenza, conferenze e vocali. Eseguire invece una delle operazioni seguenti:
  
- Creare uno o più account utente dedicati solo per la pianificazione di riunioni di grandi dimensioni
    
- Ospitare gli account utente del personale responsabile della pianificazione di riunioni di grandi dimensioni in un pool di riunioni di grandi dimensioni
    
### <a name="create-dedicated-moderators"></a>Creare moderatori dedicati

Con diverse centinaia o migliaia di utenti in una riunione, è consigliabile che una persona dedicata moderi la sessione online di una riunione di grandi dimensioni. Questa persona dedicata può essere un delegato dell'organizzatore della riunione o un membro del personale di supporto per le riunioni di grandi dimensioni dell'organizzazione. È importante aggiungere il moderatore dedicato di una riunione come relatore al momento della pianificazione della riunione, sebbene sia possibile alzare di livello un partecipante della riunione online al ruolo di relatore nel corso della riunione.
  
Il moderatore della riunione può usare tutte le funzionalità del relatore dei client Skype for Business per gestire la riunione di grandi dimensioni. Queste funzionalità includono:
  
- Monitoraggio della sala di attesa e ammissione o rifiuto degli utenti nella sala di attesa
    
- Rimozione degli utenti dalla riunione che non dovrebbero essere presenti alla riunione
    
- Modifica dei tipi di accesso alle riunioni
    
- Modifica dei ruoli dei partecipanti
    
- Invitare altri partecipanti durante la riunione utilizzando la funzionalità di trascinamento della selezione, una chiamata in uscita telefonica o un messaggio di posta elettronica
    
- Disattivazione e riattivazione dell'audio del gruppo di destinatari o dei singoli utenti
    
- Gestione del contenuto delle riunioni, incluso il caricamento del contenuto, l'eliminazione del contenuto e il cambio di contenuto attivo

    
### <a name="maintain-a-separate-calendar"></a>Gestire un calendario separato

Per ogni pool di riunioni di grandi dimensioni, è consigliabile mantenere un calendario separato delle riunioni di grandi dimensioni pianificate in tale pool. Ad esempio, è possibile ospitare un singolo account utente nel pool di riunioni di grandi dimensioni e usare Outlook con exchange e il componente aggiuntivo per riunioni online per Skype for Business per mantenere un calendario separato. Se si utilizzano più account utente per consentire a un personale di supporto di creare riunioni di grandi dimensioni, è possibile configurare un calendario separato che aggrega tutte le riunioni di grandi dimensioni create dai membri del personale di supporto. 
  
La gestione di un calendario delle riunioni di grandi dimensioni separato consente di evitare conflitti e garantire che sia attiva una sola riunione di grandi dimensioni alla volta.
  
### <a name="implement-a-scheduling-process"></a>Implementare un processo di pianificazione

Poiché nel pool di riunioni di grandi dimensioni dedicato è supportata una sola riunione alla volta, è consigliabile implementare un processo di pianificazione delle riunioni di grandi dimensioni per facilitare la configurazione di riunioni di grandi dimensioni e prevenire conflitti. Tale funzionalità non viene fornita direttamente dai client Skype for Business Server o Skype for Business. Un modo per implementare tale processo è usare il sistema di ticket del team di supporto dell'organizzazione, se disponibile.
  
Per pianificare una riunione di grandi dimensioni è necessario completare i passaggi seguenti:
  
- L'organizzatore della riunione o il delegato stabilisce data e ora, durata e dimensioni di una riunione prossima, oltre all'elenco dei relatori. Se le dimensioni previste per la riunione superano i 250 utenti oppure per assicurare un'esperienza utente ottimale per una riunione con meno di 250 utenti, l'organizzatore o il delegato invia una richiesta per una riunione di grandi dimensioni.
    
- Il personale addetto della pianificazione verifica se la data e l'ora richieste sono disponibili. Dato che nel pool dedicato è supportata una sola riunione di grandi dimensioni alla volta, il personale addetto alla pianificazione deve controllare il calendario di questo tipo di riunioni per stabilire se ne è già presente un'altra pianificata per la data e l'ora richieste. Se l'intervallo di tempo richiesto risulta disponibile, la richiesta di riunione viene approvata.
    
- Se la richiesta viene approvata, il personale di pianificazione (utilizzando le credenziali nel pool dedicato) utilizza il componente aggiuntivo per riunioni online per Skype for Business con Outlook per configurare una riunione nel pool dedicato alle riunioni di grandi dimensioni. L'URL da utilizzare per partecipare alla riunione viene fornito al richiedente nell'ambito della notifica dell'approvazione.
    
- L'organizzatore o il delegato della riunione utilizza Outlook per pianificare la riunione imminente, aggiungendo l'URL per partecipare alla riunione all'invito alla riunione. L'organizzatore della riunione o il delegato specifica quindi gli utenti da invitare e invia l'invito alla riunione.
    
### <a name="specify-appropriate-scheduling-details"></a>Specificare i dettagli di pianificazione appropriati

Dopo avere verificato che nel periodo di tempo richiesto non sono pianificate altre riunioni, il personale di supporto delle riunioni di grandi dimensioni che gestisce le richieste pianifica la riunione nel pool di riunioni di grandi dimensioni. 
  
Per garantire la migliore esperienza utente, è importante pianificare la riunione di grandi dimensioni con i livelli di accesso e le impostazioni delle riunioni appropriati per le esigenze dell'organizzatore della riunione. Considera le seguenti impostazioni di pianificazione configurate nelle opzioni riunione Skype for Business:
  
- Usare una nuova area riunioni per ciascuna riunione di grandi dimensioni anziché riutilizzare l'area riunione dedicata. 
    
- Specificare il livello di accesso alla riunione come segue:
    
  - Se almeno un invitato è esterno all'organizzazione, impostare il tipo di accesso alla riunione su **Chiunque (senza restrizioni).** Ciò consente di evitare di dover gestire una sala d'attesa di dimensioni potenzialmente grandi quando la riunione è in corso.
    
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
    
    Gestendo esplicitamente i relatori, è possibile limitare i relatori a un numero sufficientemente piccolo da rendere possibile una riunione di grandi dimensioni efficace. Se la maggioranza dei partecipanti alla riunione dispone del ruolo di partecipante, si riducono le probabilità che i partecipanti assumano per errore il controllo della presentazione, eliminino una presentazione di PowerPoint, disattivino/attivino l'audio dei relatori o siano causa di altre interruzioni della riunione. 
    
- Selezionare l'impostazione **Disattiva l'audio di tutti i partecipanti** per fare in modo che durante la riunione venga trasmesso solo l'audio dei relatori.
    
- Controllare **l'impostazione Blocca video dei** partecipanti per assicurarsi che solo i relatori possano trasmettere video nella riunione.
    
### <a name="create-a-conferencing-policy"></a>Creare un criterio di conferenza

Creare un nuovo criterio di conferenza specifico per le riunioni di grandi dimensioni e quindi assegnarlo agli utenti ospitati nel pool dedicato alle riunioni di grandi dimensioni. Configurare il criterio per conferenze con le impostazioni seguenti:
  
- Imposta **l'opzione MaxMeetingSize** su 1000. Il valore predefinito è 250.
    
- Impostare l'opzione **AllowLargeMeetings** su **True**. 
    
- Impostare l'opzione **EnableAppDesktopSharing** su **None**.
    
- Impostare l'opzione **AllowUserToScheduleMeetingsWithAppSharing** su **False**.
    
- Impostare l'opzione **AllowSharedNotes** su **False**.
    
- Impostare l'opzione **AllowAnnotations** su **False**.
    
- Impostare l'opzione **DisablePowerPointAnnotations** su **True**.
    
- Impostare l'opzione **AllowMultiview** su **False**.
    
- Impostare l'opzione **EnableMultiviewJoin** su **False**.
    
> [!NOTE]
> Il supporto per le riunioni di grandi dimensioni in Skype for Business Server richiede che **l'impostazione AllowLargeMeetings** sia impostata su true. Quando questa impostazione è impostata su true, l'esperienza di Skype for Business sarà ottimizzata per le riunioni di dimensioni molto grandi quando gli utenti aderiscono alla riunione. In particolare, in una riunione di grandi dimensioni, Skype for Business non mostrerà l'elenco iniziale o l'aggiornamento dell'elenco completo dei partecipanti alla riunione, che rappresenta un collo di bottiglia delle prestazioni sia per il client che per Skype for Business Server. Al contrario, Skype for Business mostrerà solo le informazioni sull'utente e l'elenco dei relatori della riunione. Skype for Business mostrerà comunque il numero totale di partecipanti disponibili nelle riunioni di grandi dimensioni.

**L'impostazione allowLargeMeetings $true** causa quanto segue:

- Nasconde l'elenco partecipanti. 

- Disabilita gli errori nella finestra di messaggistica istantanea.

- Disabilita il video tra più parti.

- Disabilita la possibilità di alzare di livello un partecipante a relatore. È necessario pianificare in anticipo e dichiarare tutti i relatori prima della riunione.

- Disabilita la possibilità di riattivare l'audio dei singoli partecipanti.

- Disabilita la possibilità di applicare la funzionalità Blocca contenuti in evidenza video ai partecipanti.

- Gli utenti con accesso remoto PSTN non saranno in grado di riattivare l'audio utilizzando 6 perché l'assistenza virtuale personale responsabile dei comandi DTMF nelle riunioni di grandi dimensioni attive non è presente.

- Se il relatore/organizzatore pianifica una riunione in cui tutti devono essere disattivati per primi ("Disattiva tutto"), gli utenti PSTN verranno disattivati per tutta la chiamata e non potranno riattivare l'audio.

Ad eccezione dell'impostazione **Dimensione massima riunione**, tutti gli altri criteri di conferenza specificati qui sono necessari per disabilitare le funzionalità di conferenza non necessarie in riunioni di grandi dimensioni.
  
Inoltre, è necessario configurare il pool dedicato per le riunioni di grandi dimensioni in modo che ogni utente di Skype for Business Server che si trova nel pool e responsabile della gestione della pianificazione della riunione abbia le autorizzazioni appropriate. A tale scopo, procedere come segue:
  
- Impostare l'opzione **Designa come relatore** a **Nessuno**. In genere, uno o pochi altri utenti tra tutti i partecipanti a una riunione di grandi dimensioni sono relatori, pertanto i partecipanti non devono essere automaticamente ammessi a riunioni di grandi dimensioni come relatori. I relatori dovrebbero invece essere designati in modo esplicito al momento di pianificare la riunione oppure durante la riunione stessa.
    
- Accertarsi che la casella di controllo **Tipo di conferenza assegnato per impostazione predefinita** non sia selezionata. Questa impostazione controlla se il componente aggiuntivo per riunioni online per Skype for Business pianifica sempre le conferenze utilizzando la conferenza assegnata dall'organizzatore, il che significa che le riunioni pianificate hanno lo stesso URL di partecipazione e le stesse informazioni audio. In scenari di collaborazione di piccoli gruppi, l'assegnazione di un tipo di conferenza funziona bene perché ognuno dispone di una conferenza individuale assegnata e l'URL di accesso e le informazioni audio consentono di agevolare un più rapido accesso alla riunione. Tuttavia, in scenari con riunioni di grandi dimensioni, il personale di queste ultime pianifica le riunioni più grandi con un singolo set di credenziali utente, e quindi offre URL di accesso e informazioni sull'audio al richiedente il meeting. In questo caso, l'uso di un URL diverso per accedere a ogni riunione funziona bene.
    
- Accettarsi che la casella di controllo **Consenti utenti anonimi per impostazione predefinita** non è selezionata a meno che non sia necessario. Questa impostazione influisce sul tipo di accesso alle riunioni predefinito pianificato dal componente aggiuntivo per riunioni online per Skype for Business quando non si utilizza una conferenza assegnata. L'opzione appropriata per questa impostazione dipende dalle esigenze dell'organizzazione. Se la maggior parte delle riunioni di grandi dimensioni nell'organizzazione è interna, non selezionare questa opzione. Se per la maggior parte delle riunioni di grandi dimensioni è prevista la partecipazione di  utenti esterni, selezionare questa opzione.
    
Per ulteriori informazioni sulla creazione di criteri di conferenza, vedere [Gestire i criteri di conferenza in Skype for Business Server.](../../manage/conferencing/conferencing-policies.md)
  

