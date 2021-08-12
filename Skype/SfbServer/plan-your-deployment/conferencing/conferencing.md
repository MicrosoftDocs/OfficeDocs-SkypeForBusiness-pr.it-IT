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
ms.openlocfilehash: 67956a20727747d83889a88d359e145bc99775ffc2243fc3449f282875701820
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334857"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Pianificare le conferenze in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulle funzionalità e le funzionalità di conferenza in Skype for Business Server.
  
Le conferenze in Skype for Business Server consentono agli utenti di riunirsi e tenere conferenze online usando il proprio client Skype for Business anziché tutti gli utenti che si riunino nella stessa sala. I partecipanti alla riunione possono connettersi a una riunione con il client Skype for Business per un'esperienza audio e video completa o accedere a una conferenza tramite telefono. Le conferenze supportano anche la messaggistica istantanea, la condivisione di desktop e applicazioni e le lavagna interattive.
  
In questo argomento sono incluse le sezioni seguenti:
  
- Funzionalità e funzionalità di conferenza
    
- Componenti per conferenze
    
- Criteri conferenza
    
- Supporto per riunioni di grandi dimensioni
    
- Determinare le esigenze dell'organizzazione
    
## <a name="conferencing-features-and-capabilities"></a>Funzionalità e funzionalità di conferenza

In Skype for Business Server sono disponibili quattro tipi di conferenze: conferenze Web, conferenze audio e video (A/V), conferenze telefoniche con accesso esterno e conferenze di messaggistica istantanea. 
  
È possibile scegliere di abilitare tutti i tipi di conferenza o di utilizzare un solo tipo, a seconda delle proprie esigenze. Ad esempio, è possibile abilitare tutti i tipi, incluse le conferenze telefoniche con accesso esterno, per consentire agli utenti che non sono in grado di partecipare a una conferenza con un client Skype for Business di chiamare e partecipare all'audio della riunione da un telefono. Quando si distribuisce Skype for Business Server, le funzionalità di conferenza di messaggistica istantanea vengono distribuite automaticamente. è possibile specificare se distribuire conferenze Web, A/V e con accesso esterno utilizzando Generatore di topologie. Per ulteriori informazioni, vedere [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
Nelle sottosezioni seguenti vengono descritte le funzionalità e le funzionalità di ogni tipo di conferenza.
  
### <a name="web-conferencing"></a>Web Conferencing

Le conferenze Web consentono ai partecipanti alla riunione di collaborare ai documenti condivisi durante la riunione e di condividere le applicazioni tramite il client Skype for Business riunione. Le conferenze Web forniscono le funzionalità seguenti: 
  
- **Lavagna e annotazioni.** La lavagna è una schermata vuota che può essere utilizzata per la collaborazione con l'aiuto di strumenti come testo, inchiostro, disegni e immagini. Le annotazioni effettuate sulle lavagne verranno visualizzate da tutti i partecipanti. Tale funzionalità facilita la collaborazione, consentendo ai partecipanti alle riunioni di discutere, mettere insieme idee, prendere appunti e così via.
    
- **Polling.** La funzionalità di polling migliora la collaborazione consentendo ai relatori di determinare rapidamente le preferenze dei partecipanti. Durante le riunioni e le conversazioni online, i relatori possono utilizzare i sondaggi per raccogliere risposte anonime dai partecipanti. Tutti i relatori possono vedere i risultati e decidere se nasconderli o mostrarli a tutti i partecipanti.
    
- **Condivisione applicazioni e condivisione desktop.** Durante una conferenza, il relatore della riunione può condividere l'intero desktop, una singola applicazione o singoli monitor in un ambiente multi-monitor. Oltre a visualizzare solo il contenuto, altri partecipanti alla conferenza possono richiedere il controllo dello schermo del relatore e, con l'autorizzazione, interagire con il contenuto (incluso lo scorrimento e la modifica). I partecipanti alla riunione possono anche assumere il controllo del relatore e iniziare a condividere il contenuto durante la riunione.
    
- **PowerPoint Condivisione.** Consente agli utenti di condividere PowerPoint presentazioni nella riunione tramite un server Office Web Apps, che consente di:
    
  - Display ad alta risoluzione e supporto per PowerPoint, ad esempio animazioni, transizioni di diapositive e video incorporati.
    
  - I dispositivi mobili possono accedere a queste presentazioni.
    
  - Gli utenti con le autorizzazioni appropriate possono scorrere una presentazione PowerPoint indipendentemente dalla presentazione stessa. Ad esempio, mentre Davide presenta la presentazione, Heidi può esaminare qualsiasi diapositiva che desidera senza influire sulla presentazione di Ken.
    
### <a name="audio-and-video-conferencing"></a>Audio e videoconferenze

Le conferenze audio e video consentono audio e video nella riunione. L'audio consente ai partecipanti di parlare tra loro come se si trovavano nella stessa sala. Il video consente la visualizzazione video nel client Skype for Business di tutti i partecipanti o relatori che aderiscono alla riunione con una web cam o un dispositivo di conferenza che supporta il video.
  
 Skype for Business Server offre diverse funzionalità che gli utenti possono utilizzare per configurare l'esperienza di audioconferenza per l'utente, tra cui:
  
- **Disattivazione dell'audio del gruppo di destinatari.** Il relatore può utilizzare questa impostazione per disattivare l'audio di tutti i partecipanti alla conferenza e impostare la conferenza in uno stato in cui i non relatori non possono riattivare l'audio.
    
- **Annunci di ingresso/uscita conferenza.** Se sono state abilitate le conferenze telefoniche con accesso esterno, i relatori possono utilizzare questa impostazione per attivare o disattivare gli annunci di ingresso e uscita per ridurre al minimo le distrazioni durante l'esecuzione di una conferenza.
    
- **Aggiunta di un utente tramite chiamata in uscita.** I relatori e i partecipanti a cui è stata concessa l'autorizzazione possono aggiungere numeri PSTN alle conferenze e disporre della chiamata in uscita per la conferenza a tali numeri.
    
  Skype for Business Server offre diverse funzionalità che gli utenti possono utilizzare per configurare l'esperienza di videoconferenza per l'utente, tra cui:
  
- **Visualizzazione Raccolta.** Nelle conferenze video con più di due persone, gli utenti visualizzano automaticamente tutti gli utenti della conferenza. Se alla conferenza sono presenti più di cinque partecipanti, il video dei partecipanti più attivi viene visualizzato nella riga superiore e solo la foto viene visualizzata per gli altri partecipanti. Il video con più parti è attivato per impostazione predefinita.
    
- **Panoramic Video.** Se nella sala conferenze è installato un dispositivo di videoconferenza RoundTable, questa funzionalità offre una visualizzazione completa a 360 gradi della sala riunioni. La striscia video panoramica è disponibile solo con dispositivi RoundTable.
    
- **Modalità video solo relatore.** I relatori possono configurare la riunione in modo che sia visualizzato solo il video del relatore. In questo modo si evitano distrazioni nelle riunioni di grandi dimensioni quando sono disponibili più flussi video e si bloccano su origini diverse. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable.
    
- **Contenuti in evidenza video.** I relatori possono configurare la riunione in modo che solo il video di un partecipante selezionato che è un'origine video sia visualizzato dagli altri partecipanti alla conferenza. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable per i video panoramici.
    
### <a name="dial-in-conferencing"></a>Audioconferenza telefonica

Le conferenze telefoniche con accesso esterno consentono ai partecipanti alla riunione di partecipare alla parte audio di una riunione chiamandoli da un telefono. Le conferenze telefoniche con accesso esterno sono un sottoinsieme delle funzionalità di audioconferenza e richiedono interventi di configurazione aggiuntive. Per ulteriori informazioni sulle conferenze telefoniche con accesso esterno, vedere [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md) e Configure [dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Servizi di conferenza di messaggistica istantanea

Le conferenze di messaggistica istantanea consentono a più di due parti di comunicare in una singola sessione di messaggistica istantanea. Per informazioni dettagliate sulle conferenze di messaggistica istantanea, vedere [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componenti per conferenze

Di seguito sono riportati i componenti che supportano le funzionalità di conferenza:
  
- **Servizio dell'applicazione.** Il servizio applicazione offre una piattaforma per la distribuzione, l'hosting e la gestione di applicazioni per comunicazioni unificate. Le conferenze telefoniche con accesso esterno utilizzano due applicazioni per le comunicazioni unificate che richiedono il servizio applicazione: Operatore conferenza e Annuncio conferenza. Il servizio applicazione viene installato e attivato per impostazione predefinita in ogni Front End Server di un pool Front End. Viene inoltre installato in ogni server edizione Standard per abilitare e configurare le conferenze telefoniche con accesso esterno.
    
- **applicazione Operatore conferenza.** Il applicazione Operatore conferenza è un'applicazione di comunicazione unificata che accetta chiamate PSTN (Public Switched Telephone Network), riproduce le richieste e partecipa alle chiamate a una conferenza audio/video. Il applicazione Operatore conferenza viene installato e attivato per impostazione predefinita quando si abilitano le conferenze telefoniche con accesso esterno.
    
- **applicazione Annuncio conferenza.** Il applicazione Annuncio conferenza è un'applicazione di comunicazione unificata che riproduce toni e istruzioni ai partecipanti PSTN su determinate azioni, ad esempio quando i partecipanti a partecipare o uscire da una conferenza, i partecipanti vengono disattivati o disattivati, qualcuno entra nella sala di attesa della conferenza o la conferenza è bloccata o sbloccata. applicazione Annuncio conferenza supporta anche comandi DTMF (Dual Tone Multi-Frequency) dalla tastiera del telefono. Il applicazione Annuncio conferenza viene installato e attivato automaticamente per impostazione predefinita quando si abilitano le conferenze telefoniche con accesso esterno.
    
- **Pagina Servizi di conferenza telefonica Impostazioni accesso esterno.** Nella pagina Impostazioni conferenza telefonica con accesso esterno vengono visualizzati i numeri di accesso esterno per conferenze con le lingue disponibili, le informazioni sulla conferenza assegnate (ovvero per le riunioni che non devono essere pianificate) e i controlli DTMF in conferenza e supporta la gestione del PIN (Personal Identification Number) e delle informazioni di conferenza assegnate. La pagina Servizi di Impostazioni accesso esterno viene installata automaticamente come parte dei servizi Web.
    
- **Mediation Server e gateway PSTN.** Per le conferenze telefoniche con accesso esterno è necessario un Mediation Server per tradurre la segnalazione (e i supporti in alcune configurazioni) tra Skype for Business Server e il gateway PSTN e un gateway PSTN per tradurre la segnalazione e i supporti tra il Mediation Server e il gateway PSTN. Per le conferenze telefoniche con accesso esterno, è necessario distribuire almeno un server Mediation Server e almeno uno dei componenti seguenti:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - SBC (Session Border Controller), per un provider di servizi di telefonia Internet a cui viene eseguita la connessione tramite la configurazione di un trunk SIP
    
  > [!NOTE]
  > Se si distribuiscono anche VoIP aziendale, Mediation Server e gateway PSTN fanno parte della VoIP aziendale distribuzione. Se non si distribuisce VoIP aziendale, è necessario distribuire almeno un server Mediation Server e un gateway PSTN, un sistema IP-PBX o un servizio SBC per le conferenze telefoniche con accesso esterno. 
  
- **Archivio file.** L'archivio file viene utilizzato per i file audio dei nomi registrati. Si tratta di un componente standard di ogni distribuzione Enterprise Edition o Standard Edition.
    
- **Archivio utente.** L'archivio utente viene usato per archiviare i PIN Skype for Business Server utente. I PIN vengono sottoposti a hashing. Si tratta di un componente standard di ogni distribuzione Enterprise Edition o Standard Edition.
    
- **Office Server Web Apps.** Per utilizzare le funzionalità di conferenza Web, gli amministratori devono installare Office Web Apps Server e devono configurare Skype for Business Server per comunicare con Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Criteri conferenza

Per applicare i criteri dell'organizzazione e controllare l'utilizzo della larghezza di banda, è possibile impostare criteri per i tipi di riunioni che gli utenti possono organizzare. È possibile definire un'ampia gamma di criteri di conferenza e assegnarli a singoli utenti e gruppi di utenti. È inoltre possibile impostare criteri che controllano le conversazioni peer-to-peer. Per informazioni dettagliate sull'impostazione dei criteri di conferenza, vedere [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Per informazioni dettagliate sulla gestione della larghezza di banda, vedere [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Supporto per riunioni di grandi dimensioni

La dimensione delle riunioni che Skype for Business Server può supportare dipende dal fatto che le conferenze siano ospitate in un pool condiviso o dedicato:
  
- In un pool condiviso, Skype for Business Server può ospitare riunioni con un massimo di 250 utenti. Un pool condiviso è un pool che ospita tutti Skype for Business Server di lavoro, tra cui messaggistica istantanea e presenza, conferenze e VoIP aziendale. 
    
- In un pool dedicato, Skype for Business Server può supportare le riunioni con un massimo di 1000 partecipanti che utilizzano conferenze Web e audio/video (A/V), inclusa la condivisione di presentazioni PowerPoint video. Ciò richiede un pool dedicato per supportare riunioni di grandi dimensioni e gestito in modo da assicurare l'hosting di una sola riunione di grandi dimensioni alla volta. 
    
Per ulteriori informazioni sulla gestione di riunioni di grandi dimensioni, vedere [Plan for large meetings in Skype for Business Server](large-meetings.md).
  
Se l'organizzazione richiede funzionalità di riunione più grandi, è consigliabile implementare un ambiente ibrido che si avvale di Riunione Skype Broadcast, un servizio online che fa parte di Microsoft 365 e Office 365. Riunione Skype La trasmissione consente agli utenti di ospitare e trasmettere riunioni a un pubblico online di grandi dimensioni fino a 10.000 partecipanti. L'utilizzo di Riunione Skype Broadcast richiede che Skype for Business Server sia già configurato in una configurazione ibrida con un'organizzazione Microsoft 365 o Office 365 di produzione. Tutti gli utenti devono disporre di un tenant online definito come prerequisito. Se si desidera distribuire una soluzione ibrida in grado di sfruttare Riunione Skype Broadcast, vedere [Configure your on-premises deployment for Riunione Skype Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinare le esigenze delle organizzazioni

Per determinare le funzionalità di conferenza da distribuire, è necessario considerare le funzionalità che si desidera rendere disponibili agli utenti e le caratteristiche di larghezza di banda della rete. L'elenco seguente illustra il processo di pianificazione delle conferenze per determinare quali funzionalità di conferenza distribuire, in base ai requisiti dell'organizzazione.
  
> [!NOTE]
> Quando si abilitano le conferenze durante la distribuzione, si abilitano automaticamente sia le conferenze Web che le conferenze audio/video. È tuttavia possibile disabilitare funzionalità specifiche configurando i criteri di conferenza come descritto in precedenza in questo argomento. 
  
- **Si desiderano abilitare le conferenze Web, che includono funzionalità di collaborazione sui documenti e condivisione di applicazioni?**
    
    In tal caso, è necessario abilitare le conferenze per il pool Front End utilizzando lo Strumento di pianificazione o generatore di topologie. Per ulteriori informazioni, vedere [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Per la condivisione di applicazioni è richiesta e viene utilizzata più larghezza di banda di rete rispetto alla collaborazione sui documenti. Skype for Business Server fornisce un meccanismo di limitazione per controllare ogni sessione di condivisione delle applicazioni. Per impostazione predefinita, il limite è impostato su 1,5 Kb/secondo per ogni sessione. Se non si desidera abilitare la condivisione delle applicazioni ma si desidera collaborare ai documenti, è possibile abilitare le conferenze e utilizzare i criteri di conferenza per disabilitare la condivisione delle applicazioni. Per informazioni dettagliate sulla configurazione dei criteri di conferenza, vedere [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Per consentire agli utenti di condividere PowerPoint presentazioni, è necessario configurare Office Web Apps Server. Per informazioni dettagliate sulla configurazione di Office Web Apps Server, vedere [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Si desidera abilitare le conferenze audio e video?**
    
    In tal caso, è necessario abilitare le conferenze per il pool Front End utilizzando lo Strumento di pianificazione o generatore di topologie. Per ulteriori informazioni, vedere [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Le conferenze audio e video richiedono e utilizzano più larghezza di banda di rete rispetto alle conferenze Web (che includono la collaborazione di documenti e la condivisione di applicazioni). Se non si desidera abilitare le conferenze audio e video ma si desidera abilitare le conferenze Web, è possibile abilitare le conferenze e utilizzare i criteri di conferenza per disabilitare le conferenze audio/video.
    
    Se si desidera abilitare audioconferenze ma non videoconferenze, è possibile abilitare le conferenze audio/video e utilizzare i criteri di conferenza per impedire le conferenze video. In alternativa, è possibile abilitare le conferenze audio/video e consentire solo a particolari utenti audio di avviare o partecipare a conferenze audio/video. 
    
    Per ulteriori informazioni sulla configurazione dei criteri di conferenza, vedere [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > VoIP aziendale non è necessario per l'uso delle conferenze audio/video. Se si abilitano le conferenze audio/video, gli utenti possono aggiungere l'audio alle conferenze nel caso dispongano di dispositivi audio, anche se si utilizza una soluzione telefonica PBX. 
  
- **Si desidera consentire agli utenti di partecipare alla parte audio delle conferenze quando si utilizza un telefono PSTN?**
    
    In caso affermativo, distribuire e abilitare le conferenze telefoniche con accesso esterno. Gli utenti invitati, sia all'interno che all'esterno dell'organizzazione, potranno quindi partecipare alla parte audio delle conferenze tramite un telefono PSTN.
    
    Le conferenze telefoniche con accesso esterno sono una funzionalità facoltativa che è possibile configurare quando si distribuiscono Skype for Business Server conferenza telefonica. Sebbene le conferenze telefoniche con accesso esterno utilizzino alcuni degli stessi componenti utilizzati da VoIP aziendale, è possibile distribuire le conferenze telefoniche con accesso esterno anche se non si distribuiscono VoIP aziendale. Le conferenze telefoniche con accesso esterno supportano utenti sia aziendali sia anonimi. Per ulteriori informazioni sulla configurazione delle conferenze telefoniche con accesso esterno per utenti aziendali e anonimi, vedere [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) e Configure [dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Si desidera consentire agli utenti esterni con Skype for Business di partecipare alle conferenze?**
    
    Consentendo la partecipazione esterna alle riunioni, è possibile ottimizzare l'investimento in Skype for Business Server. Gli utenti esterni possono essere:
    
  - **Utenti remoti.** Gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e utilizzano i portatili o altri dispositivi Skype for Business Server.
    
  - **Utenti federati.** Utenti di società con cui si lavora che eseguono anche Skype for Business Server. Per consentire agli utenti di mettersi facilmente in contatto con questi utenti, si creano relazioni federate con le relative società.
    
  - **Utenti anonimi.** Qualsiasi altro utente esterno invitato in modo specifico da uno degli utenti interni a partecipare a una conferenza specifica. L'organizzatore di una riunione può inviare un invito tramite posta elettronica per una conferenza a un utente esterno. Il messaggio di posta elettronica include un collegamento su cui l'utente esterno può fare clic per partecipare alla conferenza.
    
    Se si desidera consentire agli utenti esterni, è necessario distribuire i server perimetrali. Inoltre, con i server perimetrali distribuiti è possibile creare relazioni federate con altre organizzazioni, ad esempio clienti o fornitori, e gli utenti di tali organizzazioni possono collaborare più facilmente con gli utenti.
    
    Per informazioni dettagliate sulla distribuzione dei server perimetrali, vedere Plan for Edge Servers e Deploy Edge Servers. Per informazioni dettagliate sull'abilitazione dell'accesso esterno per Office Web Apps Server, vedere [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Si desidera controllare i client che possono partecipare Skype for Business Server riunioni?**
    
    In tal caso, è consigliabile configurare la pagina di partecipazione alla riunione in modo che siano disponibili solo le opzioni client che si desidera supportare. Ogni volta che un utente fa clic su un collegamento per partecipare a una riunione pianificata, Skype for Business Server rileva se un client è già installato nel computer. Viene quindi avviato il client predefinito e viene aperta la pagina di partecipazione alla riunione, che contiene i collegamenti per i client alternativi. La pagina di partecipazione alle riunioni contiene sempre l'opzione per l'Skype for Business Web App. Oltre a questa opzione, puoi decidere se includere i collegamenti per Attendee e le versioni precedenti di Communicator. 
    

