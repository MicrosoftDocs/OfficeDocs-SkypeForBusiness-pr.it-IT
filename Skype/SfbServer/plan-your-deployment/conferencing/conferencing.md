---
title: Pianificare le conferenze in Skype for Business Server
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
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Riepilogo: leggere questo argomento per informazioni sulle funzionalità e le funzionalità di conferenza in Skype for Business Server.'
ms.openlocfilehash: 187da0c45724140295ba28285a33d8d57d422e4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814056"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Pianificare le conferenze in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulle funzionalità e le funzionalità di conferenza in Skype for Business Server.
  
La conferenza in Skype for Business Server consente agli utenti di incontrare e tenere conferenze online usando il proprio client Skype for business invece di essere tutti insieme nella stessa stanza. I partecipanti alla riunione possono connettersi a una riunione con il client Skype for business per un'esperienza audio e video completa o accedere a una conferenza tramite un telefono. Le conferenze supportano anche la messaggistica istantanea, la condivisione di desktop e applicazioni e tavole bianche interattive.
  
In questo argomento sono incluse le sezioni seguenti:
  
- Funzionalità e funzionalità di conferenza
    
- Componenti per conferenze
    
- Criteri conferenza
    
- Supporto per riunioni di grandi dimensioni
    
- Determinare le esigenze dell'organizzazione
    
## <a name="conferencing-features-and-capabilities"></a>Funzionalità e funzionalità di conferenza

In Skype for Business Server sono disponibili quattro tipi di servizi di conferenza: Web Conferencing, audio and video (A/V), conferenze telefoniche con accesso esterno e servizi di messaggistica istantanea. 
  
È possibile scegliere di abilitare tutti i tipi di conferenza o di utilizzare un solo tipo, a seconda delle proprie esigenze. Ad esempio, è possibile abilitare tutti i tipi, inclusi i servizi di conferenza telefonica con accesso esterno, per consentire agli utenti che non sono in grado di partecipare a una conferenza con un client Skype for business di effettuare chiamate e partecipare all'audio della riunione da un telefono. Quando si distribuisce Skype for Business Server, le funzionalità di conferenza di messaggistica istantanea vengono distribuite automaticamente. specificare se si desidera distribuire web, A/V e le conferenze telefoniche con accesso esterno utilizzando il generatore di topologie. Per ulteriori informazioni, vedere [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
Nelle sottosezioni seguenti vengono descritte le caratteristiche e le funzionalità di ogni tipo di conferenza.
  
### <a name="web-conferencing"></a>Web Conferencing

Web Conferencing consente ai partecipanti alla riunione di collaborare ai documenti condivisi durante la riunione e al relatore della riunione di condividere le applicazioni tramite il client Skype for business. Web Conferencing offre le funzionalità seguenti: 
  
- **Lavagna e annotazioni.** La lavagna è una schermata vuota che può essere utilizzata per la collaborazione con l'aiuto di strumenti come testo, inchiostro, disegni e immagini. Le annotazioni effettuate sulle lavagne verranno visualizzate da tutti i partecipanti. Tale funzionalità facilita la collaborazione, consentendo ai partecipanti alle riunioni di discutere, mettere insieme idee, prendere appunti e così via.
    
- **Polling.** La funzionalità di polling migliora la collaborazione, consentendo ai relatori di determinare rapidamente le preferenze dei partecipanti. Durante le riunioni e le conversazioni online, i relatori possono utilizzare i sondaggi per raccogliere risposte anonime dai partecipanti. Tutti i relatori possono vedere i risultati e decidere se nasconderli o mostrarli a tutti i partecipanti.
    
- **Condivisione di applicazioni e condivisione del desktop.** Durante una conferenza, il relatore della riunione può condividere l'intero desktop, un'applicazione individuale o singoli monitor in un ambiente con più monitor. Oltre a visualizzare solo il contenuto, gli altri partecipanti alla conferenza possono richiedere il controllo dello schermo del relatore e, con l'autorizzazione, interagire con il contenuto (incluso lo scorrimento e la modifica). I partecipanti alla riunione possono anche prendere il sopravvento come relatore e iniziare a condividere il contenuto durante la riunione.
    
- **Condivisione di PowerPoint.** Consente agli utenti di condividere le presentazioni di PowerPoint nella riunione tramite un server Office Web Apps, che consente di:
    
  - Visualizzazioni ad alta risoluzione e supporto per le funzionalità di PowerPoint, ad esempio animazioni, transizioni di diapositive e video incorporati.
    
  - I dispositivi mobili possono accedere a queste presentazioni.
    
  - Gli utenti che dispongono delle autorizzazioni appropriate possono scorrere una presentazione di PowerPoint indipendentemente dalla presentazione stessa. Ad esempio, mentre Ken presenta la sua presentazione, Heidi può guardare qualsiasi diapositiva che vuole senza influire sulla presentazione di Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferenze audio e video

Le conferenze audio e video consentono l'audio e il video nella riunione. L'audio consente ai partecipanti di comunicare tra loro come se si trovassero nella stessa stanza. Video consente di visualizzare video nel client Skype for business di tutti i partecipanti o relatori che partecipano alla riunione con una Web Cam o un dispositivo per conferenze che supporta il video.
  
 Skype for Business Server offre diverse funzionalità che gli utenti possono utilizzare per configurare l'esperienza di audioconferenza per l'utente, incluse le seguenti:
  
- **Disattivazione del gruppo di destinatari.** Il relatore può utilizzare questa impostazione per disattivare l'audio di tutti i partecipanti alla conferenza e inserire la conferenza in uno stato in cui non è possibile riattivare gli stessi.
    
- **Annunci di entrata/uscita per le conferenze.** Se sono state abilitate le conferenze telefoniche con accesso esterno, i relatori possono utilizzare questa impostazione per attivare o disattivare gli annunci di entrata e uscita per ridurre al minimo le distrazioni mentre è in corso una conferenza.
    
- **Aggiunta di un utente tramite chiamata in uscita.** I relatori e i partecipanti a cui è stata assegnata l'autorizzazione, possono aggiungere numeri PSTN alle conferenze e fare in modo che la conferenza sia in uscita per i numeri.
    
  In Skype for Business Server sono disponibili diverse funzionalità che possono essere utilizzate dagli utenti per configurare l'esperienza di audioconferenza per l'utente, incluse le operazioni seguenti:
  
- **Visualizzazione raccolta.** Nelle conferenze video con più di due persone, gli utenti visualizzano automaticamente tutti i partecipanti alla conferenza. Se la conferenza ha più di cinque partecipanti, il video dei partecipanti più attivi viene visualizzato nella riga superiore e viene visualizzata solo la foto per gli altri partecipanti. Il video a più parti è attivato per impostazione predefinita.
    
- **Video panoramico.** Se nella sala conferenze è installato un dispositivo di videoconferenza RoundTable, questa funzionalità fornisce una visualizzazione completa di 360 gradi della sala riunioni. La striscia panoramica video è disponibile solo con i dispositivi RoundTable.
    
- **Solo modalità video del relatore.** I relatori possono configurare la riunione in modo che venga visualizzato solo il video. In questo modo si evitano le distrazioni nelle riunioni di grandi dimensioni quando sono disponibili più flussi video e si bloccano su origini diverse. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable.
    
- **Video Spotlight.** I relatori possono configurare la riunione in modo che solo il video di un partecipante selezionato che è un'origine video venga visualizzato dagli altri partecipanti alla conferenza. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable per il video panoramico.
    
### <a name="dial-in-conferencing"></a>Audioconferenza telefonica

Le conferenze telefoniche con accesso esterno consentono ai partecipanti alla riunione di partecipare alla parte audio di una riunione chiamando la riunione da un telefono. Le conferenze telefoniche con accesso esterno sono un sottoinsieme delle funzionalità di audioconferenza e richiedono interventi di configurazione aggiuntive. Per ulteriori informazioni sulle conferenze telefoniche con accesso esterno, vedere Pianificare le conferenze telefoniche [con accesso esterno in Skype for Business Server](dial-in-conferencing.md) e [configurare le conferenze telefoniche con accesso esterno in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Servizi di conferenza di messaggistica istantanea

Le conferenze di messaggistica istantanea consentono a più di due parti di comunicare in una singola sessione di messaggistica immediata. Per informazioni dettagliate sulle conferenze di messaggistica istantanea, vedere [pianificare la messaggistica immediata e la presenza in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componenti per conferenze

Di seguito sono riportati i componenti che supportano le funzionalità di conferenza:
  
- **Servizio applicazione.** Il servizio applicazione fornisce una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni di Unified Communications (UC). Per le conferenze telefoniche con accesso esterno vengono utilizzate due applicazioni UC che richiedono il servizio applicazione: Operatore Conferenza e Annuncio conferenza. Il servizio applicazione viene installato e attivato per impostazione predefinita in tutti i front end server in un pool Front end. Viene inoltre installato in ogni server Standard Edition per abilitare e configurare le conferenze telefoniche con accesso esterno.
    
- **Applicazione Operatore Conferenza.** L'applicazione Operatore Conferenza è un'applicazione di comunicazione unificata che accetta le chiamate PSTN (Public Switched Telephone Network), riproduce le richieste e aggiunge le chiamate a una conferenza a/V. L'applicazione Operatore Conferenza è installata e attivata per impostazione predefinita quando si abilitano le conferenze telefoniche con accesso esterno.
    
- **Applicazione Annuncio conferenza.** L'applicazione annuncio per conferenze è un'applicazione di comunicazione unificata che riproduce i toni e richiede ai partecipanti PSTN su determinate azioni, ad esempio quando i partecipanti si uniscono o lasciano una conferenza, i partecipanti sono disattivati o non sono in sordina, qualcuno entra nella sala riunioni o la conferenza è bloccata o sbloccata. L'applicazione Annuncio conferenza supporta anche i comandi DTMF (Dual-Tone Multi-Frequency) dalla tastiera del telefono. L'applicazione Annuncio conferenza viene automaticamente installata e attivata per impostazione predefinita quando si abilitano le conferenze telefoniche con accesso esterno.
    
- **Pagina Impostazioni conferenza telefonica con accesso esterno.** La pagina Impostazioni conferenza telefonica con accesso esterno consente di visualizzare i numeri di chiamata in conferenza con le lingue disponibili, le informazioni di conferenza assegnate (ovvero per le riunioni che non devono essere pianificate) e i controlli DTMF in-Conference e supporta la gestione del PIN (Personal Identification Number) e le informazioni di conferenza assegnate. La pagina Impostazioni conferenza telefonica con accesso esterno viene automaticamente installata come parte dei servizi Web.
    
- **Mediation Server e gateway PSTN.** Per le conferenze telefoniche con accesso esterno è necessario che un Mediation Server converta la segnalazione (e il supporto in alcune configurazioni) tra Skype for Business Server e il gateway PSTN e un gateway PSTN per tradurre la segnalazione e i supporti tra il Mediation Server e il gateway PSTN. Per le conferenze telefoniche con accesso esterno, è necessario distribuire almeno un server Mediation Server e almeno uno dei componenti seguenti:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - SBC (Session Border Controller), per un provider di servizi di telefonia Internet a cui viene eseguita la connessione tramite la configurazione di un trunk SIP
    
  > [!NOTE]
  > Se si sta distribuendo anche VoIP aziendale, Mediation Server e gateway PSTN fanno parte della distribuzione di VoIP aziendale. Se non si distribuisce VoIP aziendale, è necessario distribuire almeno un server Mediation Server e un gateway PSTN, un sistema IP-PBX o un servizio SBC per le conferenze telefoniche con accesso esterno. 
  
- **Archivio file.** L'archivio file viene utilizzato per i file audio dei nomi registrati. Si tratta di un componente standard di ogni distribuzione Enterprise Edition o Standard Edition.
    
- **Archivio utente.** L'archivio utente viene utilizzato per archiviare i pin degli utenti di Skype for Business Server. I PIN vengono sottoposti a hashing. Si tratta di un componente standard di ogni distribuzione Enterprise Edition o Standard Edition.
    
- **Server Office Web Apps.** Per poter utilizzare le funzionalità di Web Conferencing, gli amministratori devono installare il server Office Web Apps e devono configurare Skype for Business Server per comunicare con il server Office Web Apps.
    
## <a name="conferencing-policies"></a>Criteri conferenza

Per applicare i criteri dell'organizzazione e controllare l'utilizzo della larghezza di banda, è possibile impostare criteri per i tipi di riunioni che gli utenti possono organizzare. È possibile definire una vasta gamma di criteri di conferenza e assegnarli a singoli utenti e gruppi di utenti. È inoltre possibile impostare criteri che controllano le conversazioni peer-to-peer. Per informazioni dettagliate sull'impostazione dei criteri di conferenza, vedere [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Per informazioni dettagliate sulla gestione della larghezza di banda, vedere [Plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Supporto per riunioni di grandi dimensioni

Le dimensioni delle riunioni supportate da Skype for Business Server dipendono dal fatto che i servizi di conferenza siano ospitati in un pool condiviso o dedicato:
  
- In un pool condiviso, Skype for Business Server può ospitare riunioni con un massimo di 250 utenti. Un pool condiviso è un pool che ospita tutti i carichi di lavoro di Skype for Business Server, tra cui la messaggistica istantanea e la presenza, le conferenze e la VoIP aziendale. 
    
- In un pool dedicato, Skype for Business Server è in grado di supportare riunioni con un massimo di 1000 partecipanti tramite conferenze Web e audio/video (A/V), tra cui la condivisione di presentazioni di PowerPoint. Ciò richiede un pool dedicato per supportare riunioni di grandi dimensioni e gestito in modo da assicurare l'hosting di una sola riunione di grandi dimensioni alla volta. 
    
Per ulteriori informazioni sulla gestione di riunioni di grandi dimensioni, vedere [pianificare riunioni di grandi dimensioni in Skype for Business Server](large-meetings.md).
  
Se l'organizzazione richiede una maggiore capacità di riunione, è consigliabile implementare un ambiente ibrido che si avvale di Skype meeting broadcast, un servizio online che fa parte di Microsoft 365 e Office 365. Skype meeting Broadcast consente agli utenti di ospitare e trasmettere riunioni a grandi gruppi di destinatari online fino a 10.000 partecipanti. L'uso di Skype meeting broadcast richiede che Skype for Business Server sia già configurato in una configurazione ibrida con un'organizzazione di produzione Microsoft 365 o Office 365. Tutti gli utenti devono disporre di un tenant online definito come prerequisito. Se si è interessati alla distribuzione di una soluzione ibrida che può usufruire di Skype meeting broadcast, vedere [Configure your on-premises Deployment for Skype meeting broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinare le esigenze delle organizzazioni

Per determinare le funzionalità di conferenza da distribuire, è necessario considerare le funzionalità che si desidera rendere disponibili agli utenti e le caratteristiche di larghezza di banda della rete. Nell'elenco seguente viene illustrato il processo di pianificazione delle conferenze per determinare le funzionalità di conferenza da distribuire, in base ai requisiti dell'organizzazione.
  
> [!NOTE]
> Quando si Abilita la conferenza alla distribuzione, si abilitano automaticamente sia le conferenze Web che A/V. Tuttavia, è possibile disabilitare le funzionalità specifiche configurando i criteri di conferenza come descritto in precedenza in questo argomento. 
  
- **Si desiderano abilitare le conferenze Web, che includono funzionalità di collaborazione sui documenti e condivisione di applicazioni?**
    
    In caso affermativo, è necessario abilitare le conferenze per il pool Front end utilizzando lo strumento di pianificazione o utilizzando Generatore di topologie. Per ulteriori informazioni, vedere [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Per la condivisione di applicazioni è richiesta e viene utilizzata più larghezza di banda di rete rispetto alla collaborazione sui documenti. Skype for Business Server fornisce un meccanismo di limitazione per controllare ogni sessione di condivisione delle applicazioni. Per impostazione predefinita, il limite è impostato su 1,5 Kb/secondo per ogni sessione. Se non si desidera abilitare la condivisione di applicazioni, ma si desidera consentire la collaborazione con i documenti, è possibile abilitare i servizi di conferenza e utilizzare i criteri di conferenza per disabilitare la condivisione delle applicazioni. Per informazioni dettagliate sulla configurazione dei criteri di conferenza, vedere [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Per consentire agli utenti di condividere le presentazioni di PowerPoint, è necessario configurare il server Office Web Apps. Per informazioni dettagliate sulla configurazione del server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Si desidera abilitare le conferenze audio e video?**
    
    In caso affermativo, è necessario abilitare le conferenze per il pool Front end utilizzando lo strumento di pianificazione o utilizzando Generatore di topologie. Per ulteriori informazioni, vedere [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Le conferenze audio e video richiedono e utilizzano una maggiore larghezza di banda di rete rispetto alle Web Conferencing (che include la collaborazione tra documenti e condivisione applicazioni). Se non si desidera abilitare le conferenze audio e video, ma si desidera abilitare le conferenze Web, è possibile abilitare i servizi di conferenza e utilizzare i criteri di conferenza per disabilitare le conferenze A/V.
    
    Se si desidera abilitare le conferenze audio ma non le conferenze video, è possibile abilitare A/V Conferencing e utilizzare i criteri di conferenza per impedire le conferenze video. In alternativa, è possibile abilitare le conferenze audio/video e consentire solo a particolari utenti audio di avviare o partecipare a conferenze audio/video. 
    
    Per ulteriori informazioni sulla configurazione dei criteri di conferenza, vedere [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > VoIP aziendale non è necessario per l'utilizzo di A/V Conferencing. Se si abilitano le conferenze audio/video, gli utenti possono aggiungere l'audio alle conferenze nel caso dispongano di dispositivi audio, anche se si utilizza una soluzione telefonica PBX. 
  
- **Si desidera consentire agli utenti di partecipare alla parte audio delle conferenze quando si utilizza un telefono PSTN?**
    
    In caso affermativo, distribuire e abilitare le conferenze telefoniche con accesso esterno. Gli utenti invitati, sia all'interno che all'esterno dell'organizzazione, potranno quindi partecipare alla parte audio delle conferenze tramite un telefono PSTN.
    
    Le conferenze telefoniche con accesso esterno sono una funzionalità facoltativa che è possibile configurare quando si distribuiscono le conferenze di Skype for Business Server. Anche se la conferenza telefonica con accesso esterno utilizza alcuni degli stessi componenti utilizzati da VoIP aziendale, è possibile distribuire le conferenze telefoniche con accesso esterno anche se non si distribuisce VoIP aziendale. Le conferenze telefoniche con accesso esterno supportano utenti sia aziendali sia anonimi. Per ulteriori informazioni sulla configurazione delle conferenze telefoniche con accesso esterno per l'organizzazione e per gli utenti anonimi, vedere [deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) e [Configure Dial-in Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Si desidera consentire agli utenti esterni con client Skype for business di partecipare a conferenze?**
    
    Consentendo la partecipazione esterna alle riunioni, è possibile massimizzare gli investimenti in Skype for Business Server. Gli utenti esterni possono essere:
    
  - **Utenti remoti.** Gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e utilizzano i propri laptop o altri dispositivi Skype for Business Server.
    
  - **Utenti federati.** Utenti provenienti da aziende con cui si lavora anche per l'esecuzione di Skype for Business Server. Per consentire agli utenti di mettersi facilmente in contatto con questi utenti, si creano relazioni federate con le relative società.
    
  - **Utenti anonimi.** Qualsiasi altro utente esterno invitato in modo specifico da uno degli utenti interni a partecipare a una conferenza specifica. L'organizzatore di una riunione può inviare un invito tramite posta elettronica per una conferenza a un utente esterno. Il messaggio di posta elettronica include un collegamento su cui l'utente esterno può fare clic per partecipare alla conferenza.
    
    Se si desidera consentire agli utenti esterni, è necessario distribuire server perimetrali. Inoltre, con i server perimetrali distribuiti è possibile creare relazioni federate con altre organizzazioni, ad esempio clienti o fornitori, e gli utenti di tali organizzazioni possono collaborare più facilmente con gli utenti.
    
    Per informazioni dettagliate sulla distribuzione di server perimetrali, vedere Pianificare i server perimetrali e distribuire server perimetrali. Per informazioni dettagliate sull'abilitazione dell'accesso esterno per il server Office Web Apps, vedere [configurazione dell'integrazione con Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Si desidera controllare i client che possono partecipare alle riunioni di Skype for Business Server?**
    
    In caso affermativo, è necessario configurare la pagina di partecipazione alle riunioni in modo che siano disponibili solo le opzioni client che si desidera supportare. Ogni volta che un utente fa clic su un collegamento per partecipare a una riunione pianificata, Skype for Business Server rileva se un client è già installato nel computer. Viene quindi avviato il client predefinito e viene aperta la pagina di partecipazione alla riunione, che contiene i collegamenti per i client alternativi. La pagina di partecipazione alle riunioni contiene sempre la possibilità di utilizzare Skype for Business Web App. Oltre a questa opzione, è possibile decidere se includere i collegamenti per il partecipante e le versioni precedenti di Communicator. 
    

