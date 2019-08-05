---
title: Prendere decisioni del servizio di audioconferenza-Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Informazioni sulle riunioni, le licenze e la disponibilità, la configurazione delle impostazioni del Bridge di conferenza, l'acquisizione o il trasferimento di numeri di telefono e la scelta dei piani di chiamata tenant.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f7c36904aadf19802511979fa5e069b3c91035e
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2019
ms.locfileid: "36182740"
---
# <a name="make-my-service-decisions"></a>Prendere le decisioni del servizio

Per pianificare l'implementazione tecnica di servizi di audioconferenza, è necessario effettuare prima di tutto una serie di decisioni di servizio per preparare meglio l'organizzazione a implementare una soluzione che soddisfi i requisiti aziendali definiti.

## <a name="audio-conferencing-in-teams"></a>Servizi di conferenza audio in teams

Come parte della definizione delle funzionalità di conferenza audio richieste in Microsoft teams, uno dei primi passaggi consiste nel valutare l'ultima Roadmap pubblica per determinare:

-   Quali funzionalità di conferenza audio in teams verranno distribuite per gli utenti nell'ambito.

-   Requisiti di funzionalità utente previsti per i servizi di audioconferenza in teams.

-   Conferma che le caratteristiche dei servizi di audioconferenza in teams descritte nella roadmap pubblica più recente soddisfano i requisiti dell'utente, della funzionalità e dell'ambito, nella sequenza temporale della distribuzione.

> [!NOTE]
> La roadmap per i team più recenti per identificare le caratteristiche dei servizi di audioconferenza in ambito per la <https://aka.ms/O365Roadmap>distribuzione può essere trovata in.

## <a name="meetings-in-teams"></a>Riunioni in teams

Teams offre agli utenti la possibilità di pianificare e partecipare a riunioni online tramite video HD, Voice over IP (VoIP) e opzioni per i servizi di conferenza telefonica con accesso esterno PSTN.

Le riunioni possono essere programmate come riunioni private (solo le parti invitate possono partecipare) o le riunioni di canale (aperte per tutti gli utenti che hanno accesso al canale) e gli utenti possono anche avviare riunioni improvvisate all'interno dei canali.

> [!NOTE]
> Per altre informazioni sulle caratteristiche delle riunioni in teams, vedere la Guida di [orientamento di Microsoft 365](https://aka.ms/O365Roadmap).

I partecipanti alla riunione possono partecipare alle riunioni del team componendo i numeri di telefono di Bridge per conferenze telefoniche con accesso esterno a pedaggio o a pedaggio gratuito tramite telefoni fissi o cellulari. Inoltre, gli utenti possono consentire al servizio di audioconferenza di avviare la funzione "Chiamami" in modo che possano partecipare a una riunione facendo chiamare il Bridge di conferenza i loro telefoni (utile quando la connessione dati non è affidabile) o consentire agli organizzatori della riunione di invitare la riunione partecipanti tramite chiamata esterna ai loro telefoni.

> [!IMPORTANT]
> Le conferenze audio in teams non supportano i provider di servizi di audioconferenza di terze parti (ACPs).

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>Disponibilità di servizi di conferenza audio

Prima di pianificare l'implementazione di servizi di audioconferenza in teams, è necessario esaminare la disponibilità del servizio di audioconferenza come descritto in dettaglio nella [disponibilità per i programmi di audioconferenza e per le chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

> [!IMPORTANT]
> A causa di vincoli legali, per consentire ai servizi di audioconferenza di essere disponibili per le organizzazioni multinazionali, il contratto per gli abbonamenti a Office 365 deve essere proveniente da paesi e aree geografiche in cui il servizio di audioconferenza è disponibile commercialmente.

Dopo aver confermato che l'organizzazione è idonea a ottenere il servizio di audioconferenza, compilare l'elenco delle posizioni o degli uffici degli utenti in cui verrà implementato il servizio di audioconferenza, in base all'elenco dei paesi e delle aree geografiche disponibili.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere quali posizioni utente o uffici implementeranno il servizio di audioconferenza.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare le posizioni degli utenti o gli uffici da abilitare per il servizio di audioconferenza.</li></ul>|

> [!TIP]
> Di seguito è riportato un esempio di modello di elenco di abilitazione sito di audioconferenza:
> 
> |Ufficio   |Posizione |Servizio di conferenza PSTN  |
> |---------|---------|---------|
> |Una strada di Epping|Australia|Audioconferenza|
> |100 Cyberport Road|Hong Kong SAR (香港特別行政區)|Servizi di conferenza PSTN legacy|
> |Una Marina Boulevard|Singapore|Audioconferenza|
> |32 London Bridge Street|Regno Unito|Audioconferenza|
> |39 Quai du Président Roosevelt|Francia|Audioconferenza|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>Licenze per i servizi di audioconferenza

Una [licenza](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) per i servizi di audioconferenza è disponibile come parte dei piani di abbonamento a Office 365 E5 oppure come servizio componente aggiuntivo per i piani di abbonamento a Office 365 E1 o Office 365 E3.

> [!NOTE]
> Le conferenze telefoniche PSTN o con accesso esterno in teams non supportano i provider di servizi di audioconferenza di terze parti (ACPs).
> <br>Se usi già i servizi di conferenza PSTN di Skype for business online, puoi subito sfruttare le funzionalità di audioconferenza in teams.

Per ottenere numeri di telefono a ponte per conferenze senza pedaggio e per supportare l'accesso esterno ai numeri di telefono internazionali, è necessario configurare i crediti per le [comunicazioni](what-are-communications-credits.md) per l'organizzazione.

> [!IMPORTANT]
> Alcuni paesi sono serviti solo per i numeri di telefono del Bridge di conferenza senza pedaggio. Per supportare l'accesso esterno in questi paesi, è necessario usare i crediti per le comunicazioni.

La prima considerazione quando si implementano i crediti per le comunicazioni consiste nel decidere l'importo iniziale dei fondi che si desidera acquistare. Se l'organizzazione sceglie di usare la ricarica automatica, è necessario decidere l'importo del trigger (importo minimo dei fondi) e l'importo della ricarica automatica. L'utilizzo effettivo determinerà l'importo della ricarica automatica. Dovresti monitorare l'uso dei crediti di comunicazione nel tempo e regolare l'importo della ricarica se necessario.

Per altre informazioni sui crediti per le comunicazioni, vedere [qui](what-are-communications-credits.md).

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Se l'organizzazione non ha già acquistato le licenze per i servizi di audioconferenza necessarie, decidere se acquisire le licenze per i servizi di audioconferenza eseguendo l'accesso agli attuali abbonamenti a Office 365 o acquisendo licenze per i componenti aggiuntivi per i servizi di audioconferenza.</li><li>Decidere se i crediti per le comunicazioni sono necessari per l'implementazione di audioconferenza. In caso affermativo, decidere l'importo iniziale dei fondi da acquistare. Se applicabile, decidere l'importo del trigger e l'importo della ricarica automatica.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare gli utenti a cui saranno assegnate licenze per i servizi di audioconferenza.</li><li>Documentare il piano di crediti per le comunicazioni (importo iniziale, importo del trigger, importo della ricarica automatica)</li></ul>|

> [!TIP]
> Puoi documentare l'elenco delle assegnazioni di licenze per gli utenti di servizi di audioconferenza usando l'esempio seguente.
> 
> |Utente  |Ufficio  |Licenza di Office 365  |
> |---------|---------|---------|
> |Adele Vance|Una strada di Epping|Office 365 E5|
> |Alex Wilber|Una strada di Epping|Office 365 E3, componente aggiuntivo per la conferenza audio|
> |Ben Walters|Una strada di Epping|Office 365 E3, componente aggiuntivo per la conferenza audio|
> |Christie Cline|Una Marina Boulevard|Office 365 E3, componente aggiuntivo per la conferenza audio|
> |Debra Berger|Una Marina Boulevard|Office 365 E5|
> |Lee GU|Una Marina Boulevard|Office 365 E5|
> |Emily Braun|32 London Bridge Street|Office 365 E5|
> |Lidia Holloway|32 London Bridge Street|Office 365 E5|
> |Luigi Lahr|32 London Bridge Street|Office 365 E5|
> |Marcel Beauchamp|39 Quai du Président Roosevelt|Office 365 E3, componente aggiuntivo per la conferenza audio|
> |Rachelle Cormier|39 Quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 Quai du Président Roosevelt|Office 365 E3, componente aggiuntivo per la conferenza audio|

<br>

> [!TIP]
> I numeri di pianificazione per i crediti di comunicazione possono essere documentati come segue:
>
> |         |         |
> |---------|---------|
> |Importo iniziale|$1.000|
> |Importo trigger|$400|
> |Importo di ricarica automatica|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>Numeri di telefono per Bridge di conferenza

Il servizio di audioconferenza in Office 365 include:

-   Più tipi di numeri di telefono per Bridge di conferenza (numero verde e numero verde)

-   Più categorie di numeri di telefono per Bridge di conferenza (dedicati e condivisi)

-   Supporto per più lingue per il Bridge di conferenza (primario e secondario)

-   Numero di telefono predefinito per il tenant

> [!NOTE]
> I numeri di telefono di Bridge conferenza dedicati contano sul limite dei numeri di telefono che possono essere acquisiti per ogni tenant, in base al numero di licenze applicabili. I numeri di telefono per i ponti conferenza gratuiti richiedono crediti per comunicazioni.

Se è necessario trasferire i numeri di telefono di Bridge conferenza esistenti al servizio di audioconferenza, supponendo che soddisfino i requisiti specifici per il paese, è possibile trasferire questi numeri di telefono di Bridge conferenza esistenti a Microsoft.

> [!NOTE]
> La complessità del trasferimento di numeri di telefono a Microsoft varia notevolmente a seconda del paese o dell'area geografica, del vettore, del numero di circuiti coinvolti e di molti altri fattori che contribuiscono. Collaborare con il provider corrente per verificare quanto tempo è probabile che sia necessario per assicurarsi di avviare il processo abbastanza presto per soddisfare le sequenze temporali.

Per altre informazioni sui numeri di telefono di Bridge per conferenze, vedere gli articoli seguenti:

-   [Configurare servizi di audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

-   [Numeri di telefono per i servizi di audioconferenza](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [Recupero di numeri di telefono del servizio](getting-service-phone-numbers.md)

-   [Trasferire numeri di telefono in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se l'organizzazione ha bisogno di numeri di telefono di Bridge Conference dedicati.</li><li>Decidere in che modo verranno ottenuti i numeri di telefono di Bridge conferenza dedicati per le posizioni degli utenti o gli uffici nell'ambito dell'implementazione di servizi di audioconferenza, ovvero ottenere da Microsoft o trasferire i numeri di telefono esistenti.</li><li>Se si sceglie di ottenerle da Microsoft, decidere il metodo da usare (invio modulo o automatizzato) per le posizioni degli utenti o gli uffici nell'ambito dell'implementazione di servizi di audioconferenza.</li><li>Decidere le preferenze della lingua da configurare per ogni numero di telefono di Bridge conferenza dedicato.</li><li>Decidere il numero di telefono del Bridge di conferenza predefinito del tenant.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare il piano master per l'acquisizione di numeri di telefono, specificando il modo in cui verranno ottenuti i numero di telefono per ogni posizione utente o Office in ambito per l'implementazione di audioconferenza.</li><li>Se applicabile, completare il modulo di richiesta nuovo numero di telefono, ovvero un modulo per ogni posizione o ufficio.</li><li>Documentare le configurazioni dettagliate del numero di telefono di Bridge Conference (numeri di telefono di Bridge di conferenza condivisi e dedicati, preferenze della lingua per ogni numero di telefono di Bridge Conference dedicato, numero di telefono del Bridge Conference predefinito del tenant).</li></ul>|

Di seguito è riportato un esempio di modello che è possibile usare per acquisire i dettagli del Bridge di conferenza.

> [!TIP]
> Di seguito è riportato un esempio di modello per acquisire i dettagli del Bridge di conferenza:
> 
> |Ufficio   |Acquisizione di Bridge Number e Bridge Type |Numero di Bridge  |Lingua Bridge|
> |---------|---------|---------|---------|
> |Una strada di Epping|Acquisire nuove, dedicate|TBA|Inglese (Australia)|
> |Una Marina Boulevard|Acquisire nuove condivisioni|TBA|Inglese (Stati Uniti), cinese (semplificato, RPC)|
> |32 London Bridge Street|Porta esistente, dedicata|+ 44 20 7946 0001|Inglese (Regno Unito)|
> |39 Quai du Président Roosevelt|Acquisire nuove, dedicate|TBA|Francese (Francia), inglese (Regno Unito)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>Impostazioni del Bridge di conferenza

Per personalizzare ulteriormente l'esperienza utente, è possibile configurare le opzioni a livello di organizzazione per partecipare a riunioni di audioconferenza (riunione e notifica di uscita e registrazione del nome del chiamante), la lunghezza del PIN dell'organizzatore della riunione e la notifica tramite posta elettronica:

-   Le notifiche di entrata e di uscita della riunione sono disponibili sotto forma di nome registrato, numero di telefono e toni.

-   La lunghezza del PIN è configurabile da 4 a 12 cifre, con un PIN di 5 cifre come predefinito.

-   I messaggi di notifica inviati all'abilitazione della licenza di audioconferenza o qualsiasi altra modifica guidata dall'amministratore sono abilitati per impostazione predefinita. Puoi disabilitare questa funzionalità e prendere il controllo delle comunicazioni degli utenti dell'organizzazione.

Per gli utenti a cui è assegnata una licenza di audioconferenza, i numeri a pedaggio/numero verde predefiniti, visualizzati nelle coordinate di audioconferenza, possono essere configurati in modo da usare:

-   Impostazione predefinita a livello di tenant.

-   I numeri di telefono di Bridge conferenza assegnati automaticamente.

-   Numeri di telefono di Bridge Conference configurati manualmente per ogni utente.

I numeri di telefono di Bridge conferenza specifici per gli utenti sono in genere utili nelle organizzazioni globali o a livello nazionale in cui gli utenti sono distribuiti e devono specificare i numeri locali come numeri di telefono di Bridge conferenza predefiniti negli inviti alle riunioni.

I partecipanti che partecipano da diverse città o oltremare possono cercare numeri aggiuntivi configurati a livello di tenant, ma questi numeri non vengono visualizzati direttamente negli inviti alla riunione. Gli inviti alla riunione includono un collegamento che porta i partecipanti alla pagina numeri di telefono per le **conferenze telefoniche con accesso** esterno per cercare il numero di cellulare Bridge Conference più vicino alla propria posizione.

È anche possibile configurare il modo in cui i chiamanti non autenticati vengono gestiti da ogni singolo organizzatore di una riunione, se richiedere all'organizzatore della riunione di avviare la riunione prima che i chiamanti non autenticati possano essere ammessi o consentire ai chiamanti non autenticati di avviare una riunione .

È anche possibile applicare configurazioni aggiuntive per ogni utente per controllare l'uso dei numeri di telefono per le conferenze senza pedaggio e la chiamata in uscita da una conferenza.

> [!NOTE]
> Questi controlli correlati ai costi sono attualmente disponibili solo per i clienti in anteprima. È possibile iscrivere l'organizzazione nel programma di anteprima https://www.skypepreview.comda.

Con questi controlli, è possibile decidere se gli organizzatori della riunione possono ottenere numeri di telefono per le riunioni organizzate da un numero verde e se i partecipanti possono effettuare chiamate in uscita dalle riunioni organizzate. Il livello di controllo della chiamata in uscita consente di impedire completamente la chiamata in uscita, per consentire la chiamata esterna ai numeri nazionali, per consentire la chiamata esterna ai numeri nazionali e internazionali.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se l'organizzazione richiede notifiche di entrata e di uscita e, in caso affermativo, il tipo di notifica da implementare (toni, numero di telefono o nome registrato).</li><li>Decidi la lunghezza del PIN per i servizi di audioconferenza che soddisfa i requisiti di sicurezza dell'organizzazione.</li><li>Decidere se l'organizzazione vuole assumere il controllo delle comunicazioni degli utenti relative al servizio di audioconferenza.</li><li>Decidere i numeri di telefono del Bridge di conferenza da assegnare a ogni organizzatore della riunione.</li><li>Decidere se alcuni organizzatori della riunione devono usare numeri di telefono per le riunioni senza pedaggio.</li><li>Decidere se alcuni organizzatori della riunione devono consentire ai chiamanti non autenticati di avviare una riunione.</li><li>Decidere se alcuni organizzatori della riunione richiedono la chiamata in uscita per la conferenza per essere controllati.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare le impostazioni dettagliate per il Bridge delle conferenze (notifiche di entrata e uscita, lunghezza del PIN, notifica della modifica della configurazione della posta elettronica)</li><li>Documentare i numeri di telefono del Bridge di conferenza da assegnare a ogni organizzatore della riunione e l'impostazione corrispondente per controllare i criteri per i chiamanti non autenticati e i controlli per il numero verde e la chiamata in uscita.</li></ul>|

> [!TIP]
> Le impostazioni del Bridge di conferenza possono essere documentate come nell'esempio seguente.
> 
> |         |         |
> |---------|---------|
> |Abilitare le notifiche di entrata e uscita delle riunioni|Abilitata|
> |Tipo di annuncio di entrata/uscita|Toni|
> |Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione|Disabilitata|
> |Lunghezza del PIN|5|
> |Inviare automaticamente messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di accesso esterno|Disabilitata|

<br>

> [!TIP]
> È possibile documentare l'elenco delle assegnazioni delle impostazioni del Bridge di conferenza per gli utenti di servizi di audioconferenza usando l'esempio seguente.
>
> |Utente  |Ufficio  |Numero di pedaggio predefinito  |Numero verde predefinito  |Consenti numero verde  |Sala di attesa per i chiamanti non autenticati  |Conferenza telefonica in uscita  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|Una strada di Epping|TBA|TBA|Sì|Abilitata|Internazionali e nazionali|
> |Alex Wilber|Una strada di Epping|TBA|TBA|No|Disabilitata|Non consentito|
> |Ben Walters|Una strada di Epping|TBA|TBA|No|Disabilitata|Non consentito|
> |Christie Cline|Una Marina Boulevard|TBA|TBA|Sì|Disabilitata|Nazionali|
> |Debra Berger|Una Marina Boulevard|TBA|TBA|Sì|Abilitata|Nazionali|
> |Lee GU|Una Marina Boulevard|TBA|TBA|Sì|Abilitata|Nazionali|
> |Emily Braun|32 London Bridge Street|+ 44 20 7946 0001|TBA|Sì|Abilitata|Non consentito|
> |Lidia Holloway|32 London Bridge Street|+ 44 20 7946 0001|TBA|Sì|Disabilitata|Non consentito|
> |Luigi Lahr|32 London Bridge Street|+ 44 20 7946 0001|TBA|Sì|Disabilitata|Non consentito|
> |Marcel Beauchamp|39 Quai du Président Roosevelt|TBA|TBA|No|Disabilitata|Nazionali|
> |Rachelle Cormier|39 Quai du Président Roosevelt|TBA|TBA|Sì|Abilitata|Internazionali e nazionali|
> |Isabell Potvin|39 Quai du Président Roosevelt|TBA|TBA|No|Disabilitata|Nazionali|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>Gestire i numeri di telefono Cloud Voice

Per l'implementazione di servizi di audioconferenza, è possibile scegliere di acquisire nuovi numeri di telefono o trasferire/portare i numeri di telefono esistenti.

Per consentire agli utenti di effettuare il dial-up di numeri di telefono nel modo in cui sono abituati, ad esempio omettendo i codici di area per le chiamate locali, omettendo il codice paese per le chiamate nazionali o anche usando la chiamata a cifre brevi durante l'esecuzione di una conferenza telefonica, è possibile configurare un dial plan personalizzato e assegnarla agli utenti.

## <a name="acquire-new-telephone-numbers"></a>Acquisire nuovi numeri di telefono

I due tipi di numeri di telefono nelle soluzioni Microsoft Cloud Voice sono i seguenti:

-   Numeri di abbonato (utente), che possono essere assegnati agli utenti dell'organizzazione.

-   Numeri di servizio, disponibili come numeri di servizio a pagamento e a pagamento, che hanno una maggiore capacità di chiamata simultanea rispetto ai numeri di abbonato e possono essere assegnati a servizi come audioconferenza, operatori automatici o code di chiamata.

Per altre informazioni su questi tipi di numeri di telefono, vedere [diversi tipi di numeri di telefono usati per chiamare i piani](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans).

Il numero totale di numeri di telefono che è possibile ottenere dipende dai tipi di numero di telefono e dalle licenze acquistate e assegnate agli utenti.

Quando si tratta di numeri di servizio, è necessario pianificare con attenzione l'implementazione di servizi di audioconferenza. Valutare se l'azienda richiede numeri di telefono di Bridge conferenza dedicati; in caso contrario, l'organizzazione può scegliere di usare i numeri di telefono di Bridge conferenza condivisi.

Per altre informazioni sul numero totale di numeri di telefono ottenibili, vedere [quanti numeri di telefono si possono ottenere?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere le posizioni o gli uffici degli utenti in cui verranno acquisiti nuovi numeri di telefono da Microsoft.</li><li>Decidere il tipo di numeri di telefono da acquisire da Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare le posizioni degli utenti o gli uffici in cui verranno acquisiti nuovi numeri di telefono da Microsoft.</li><li>Documentare il tipo di numeri di telefono da acquisire da Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Trasferire i numeri di telefono esistenti

Se l'organizzazione vuole trasferire (o portare) i numeri di telefono esistenti a Microsoft, è possibile inviare una richiesta di ordine di trasferimento a Microsoft.

È possibile trasferire tutti i numeri di telefono esistenti contemporaneamente (porta completa) e, in alcuni mercati, è possibile trasferire un sottoinsieme dei numeri di telefono esistenti (porta parziale). Una porta parziale può essere utile nei casi in cui si vuole semplicemente trasferire il Bridge di conferenza telefonica con accesso esterno a un servizio di audioconferenza.

Un singolo ordine di porta può solo trasferire i numeri di telefono a un singolo tipo di numero di telefono. Se è necessario trasferire alcuni numeri di telefono come numeri di abbonato e alcuni come numeri di servizio, è consigliabile completare prima il trasferimento a Microsoft e quindi eseguire la conversione non appena i numeri si trovano all'interno del controllo di Microsoft.

In alternativa, se è supportata la porta parziale, è possibile inviare più richieste di porta, una richiesta di porta alla volta. Questo approccio alternativo prolungherà tuttavia il contratto con il provider di servizi di telecomunicazioni esistente.

La conversione di numeri di telefono è un argomento complesso e richiede pianificazione, coordinamento e gestione adeguati delle aspettative delle parti interessate. Per altre informazioni, vedere gli articoli seguenti:

-   [Trasferimento di numeri di telefono in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [Domande comuni sul trasferimento dei numeri di telefono](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere le posizioni o gli uffici degli utenti in cui i numeri di telefono esistenti verranno trasferiti a Microsoft.</li><li>Decidere il tipo di numeri di telefono da trasferire a Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare le posizioni o gli uffici degli utenti in cui i numeri di telefono esistenti verranno trasferiti a Microsoft.</li><li>Documentare il tipo di numeri di telefono da trasferire a Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>Dial plan

Un dial plan nella caratteristica sistema telefonico di Office 365 è un set di regole di normalizzazione che converte i numeri di telefono composti in un formato alternativo (in genere formato E. 164) per l'autorizzazione di chiamata e il routing delle chiamate. Il servizio di audioconferenza sfrutta le stesse funzionalità usate dal sistema telefonico per tradurre i numeri di telefono compilati in scenari di chiamata in uscita per conferenze, ad esempio invitare i partecipanti tramite PSTN e effettuare la chiamata, "Chiamami".

Nella caratteristica sistema telefonico di Office 365 sono disponibili due tipi di dial plan:

-   **Dial plan di servizio:** Questo è il dial plan predefinito applicato agli utenti in base alla posizione di utilizzo di Office 365 e non può essere modificato.

-   **Dial plan tenant:** Si tratta di un dial plan personalizzabile all'interno di un tenant, che viene ulteriormente suddiviso in due tipi:

    -   **Tenant-dial plan globale:** Il dial plan che si applica a tutti gli utenti del tenant.

    -   **Tenant-dial plan per utenti:** Il dial plan che si applica solo a utenti specifici.

Il dial plan effettivo assegnato agli utenti è la combinazione del piano di chiamata di servizio (in base alla posizione di utilizzo di Office 365 dell'utente) e del dial plan tenant (può essere tenant-dial plan globale o tenant-dial plan utente).

![Tabella mostra tre combinazioni di piani di servizio e di dial tenant.] (media/audio_conferencing_image8.png "Tabella mostra tre combinazioni di piani di servizio e di dial tenant.")

> [!Important]
> In ogni dial plan del tenant può essere previsto un massimo di 25 regole di normalizzazione; per questo motivo, è importante evitare di duplicare le regole di normalizzazione già disponibili nell'ambito del piano di servizi di chiamata.

Per altre informazioni sui dial plan, vedere [cosa sono i dial plan?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Punti decisionali|<ul><li>Decidere se l'organizzazione richiede piani di dial personalizzati (requisiti aziendali, requisiti di adozione e così via).</li><li>Se applicabile, decidere l'ambito del dial plan tenant (tenant-Global o tenant-User) per supportare i requisiti per i dial plan personalizzati.</li><li>Se applicabile, decidere i piani di chiamata del tenant che verranno creati per supportare le posizioni degli utenti o gli uffici in ambito per l'implementazione di cloud Voice.</li><li>Se applicabile, decidere quali utenti richiedono un piano di chiamata personalizzato e il piano di chiamata del tenant da assegnare per ogni utente.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Passaggi successivi|<ul><li>Documentare i piani di chiamata personalizzati e le regole di normalizzazione associate da configurare nell'ambito dell'implementazione vocale cloud.</li><li>Documento a cui gli utenti devono assegnare un dial plan personalizzato e il piano di chiamata del tenant da assegnare per ogni utente.</li></ul>|

> [!TIP]
> Se è applicabile al progetto, è possibile usare il modello seguente per documentare le configurazioni di dial plan del tenant.
> 
> |Nome del piano di chiamata tenant<br>_Descrizione_  |Nome regole di normalizzazione<br>_Descrizione_  |Modello<br>Conversione<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_One Epping Road North Ryde, NSW, AU dial plan_|**AU-NSW-NorthRyde-OER-interno**<br>_Numero interno (X7000-x7999) per un ufficio stradale di Epping, North Ryde, NSW, Australia_|^ (7 \ d{3}) $<br>+ 6125550 $1<br>True|
> ||**AU-NSW-local**<br>_Normalizzazione dei numeri locali per NSW, Australia_|^ ([2-9] \d{7}) $<br>+ 612 $1<br>False|
> ||**AU-TollFree**<br>_Normalizzazione numeri verdi per l'Australia_|^ (1 [38] \d{4,8}) \d * $<br>+ 61 $1<br>False|
> ||**AU-Service**<br>_Normalizzazione dei numeri di servizio per l'Australia_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>False|
> |**SG-Singapore-OMB**<br>_OMB Singapore, SG dial plan_|**SG-OMB-interno**<br>_Numero interno (X8000 â € "x8999) per OMB Office, Singapore_|^ (8 \ d{3}) $<br>+ 656888 $1<br>True|
> ||**SG-TollFree**<br>_Normalizzazione numeri verdi per Singapore_|^ (1? 800 \ d{7}) \d * $<br>+ 65 $1<br>False|
> ||**SG-Service**<br>_Normalizzazione dei numeri di servizio per Singapore_|^ (1 \ d{3,4}\|9 \ d{2}) $<br>$1<br>False|
> |**FR-Parigi-Issy-39qdPR**<br>_39 Quai du Président Roosevelt Issy-les-Moulineaux, Francia dial plan_|**FR-39qdPR-Internal**<br>_Numero interno (X7000 â € "x7999) per 39 Quai du Président Roosevelt Office, Issy-les-Moulineaux, Francia_|^ (7 \ d{3}) $<br>+ 3319999 $1<br>True|
> ||**FR-TollFree**<br>_Normalizzazione numeri verdi per la Francia_|^ 0? (80 \ d{7}) \d * $<br>+ 33 $1<br>False|
> ||**FR-Service**<br>_Normalizzazione dei numeri di servizio per la Francia_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>False|

<br>

> [!TIP]
> Il modello di esempio seguente può essere sfruttato per le assegnazioni di dial plan per documenti per supportare il progetto:
>
> |Utente  |Ufficio  |Tipo di dial plan  |Nome del dial plan  |
> |---------|---------|---------|---------|
> |Adele Vance|Una strada di Epping|Dial plan tenant|AU-NSW-NorthRyde-OER|
> |Alex Wilber|Una strada di Epping|Dial plan tenant|AU-NSW-NorthRyde-OER|
> |Ben Walters|Una strada di Epping|Dial plan tenant|AU-NSW-NorthRyde-OER|
> |Christie Cline|Una Marina Boulevard|Dial plan tenant|SG-Singapore-OMB|
> |Debra Berger|Una Marina Boulevard|Dial plan tenant|SG-Singapore-OMB|
> |Lee GU|Una Marina Boulevard|Dial plan tenant|SG-Singapore-OMB|
> |Emily Braun|32 London Bridge Street|Dial plan di servizio|N/D|
> |Lidia Holloway|32 London Bridge Street|Dial plan di servizio|N/D|
> |Luigi Lahr|32 London Bridge Street|Dial plan di servizio|N/D|
> |Marcel Beauchamp|39 Quai du Président Roosevelt|Dial plan tenant|FR-Parigi-Issy-30qdPR|
> |Rachelle Cormier|39 Quai du Président Roosevelt|Dial plan tenant|FR-Parigi-Issy-30qdPR|
> |Isabell Potvin|39 Quai du Président Roosevelt|Dial plan tenant|FR-Parigi-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Decisioni del servizio documenti 

Usare le informazioni delle sezioni precedenti di questo articolo per documentare le decisioni del servizio. In generale, questa documentazione conterrà le sezioni principali seguenti:

-   Elenco di abilitazione del sito del servizio di audioconferenza

-   Elenco delle assegnazioni di licenze per gli organizzatori della riunione di audioconferenza

-   Numeri di pianificazione per i crediti comunicazioni

-   Dettagli del Bridge di conferenza

-   Impostazioni del Bridge di conferenza

-   Assegnazioni delle impostazioni del Bridge di conferenza

-   Piani di acquisizione di numeri di telefono

-   Piani di dial tenant

-   Assegnazioni di dial plan

<!--ENDOFSECTION-->