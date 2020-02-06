---
title: Pianificare i servizi di conferenza in Skype for Business Server
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
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Riepilogo: leggere questo argomento per informazioni sulle funzionalità e le funzionalità dei servizi di conferenza in Skype for Business Server.'
ms.openlocfilehash: f91c815cf0b5d0b69ad5815157cba7a56bb28307
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816004"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Pianificare i servizi di conferenza in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulle funzionalità e le funzionalità dei servizi di conferenza in Skype for Business Server.
  
I servizi di conferenza in Skype for Business Server consentono agli utenti di partecipare a conferenze online usando il loro client Skype for business invece di essere tutti insieme nella stessa stanza. I partecipanti alla riunione possono connettersi a una riunione con il client Skype for business per un'esperienza audio e video completa oppure effettuare una chiamata a una conferenza tramite telefono. Le conferenze supportano anche la messaggistica istantanea, la condivisione di desktop e applicazioni e lavagne interattive.
  
Questo argomento include le sezioni seguenti:
  
- Funzionalità e funzionalità per i servizi di conferenza
    
- Componenti di conferenza
    
- Criteri conferenza
    
- Supporto per le riunioni di grandi dimensioni
    
- Determinare le esigenze dell'organizzazione
    
## <a name="conferencing-features-and-capabilities"></a>Funzionalità e funzionalità per i servizi di conferenza

In Skype for Business Server sono disponibili quattro tipi di servizi di conferenza: Servizi di conferenza Web, conferenze audio e video (A/V), conferenze telefoniche con accesso esterno e conferenze di messaggistica istantanea. 
  
Puoi scegliere di abilitare tutti i tipi di conferenza o di usare un solo tipo, a seconda delle tue esigenze. Ad esempio, puoi abilitare tutti i tipi, inclusi i servizi di conferenza telefonica con accesso esterno, per consentire agli utenti che non sono in grado di partecipare a una conferenza con un client Skype for business di chiamare e partecipare all'audio della riunione da un telefono. Quando si distribuisce Skype for Business Server, le funzionalità di conferenza di messaggistica istantanea vengono distribuite automaticamente; Puoi specificare se distribuire web, A/V e servizi di conferenza telefonica con accesso esterno usando il generatore di topologie. Per altre informazioni, vedere [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
Le sottosezioni seguenti descrivono le caratteristiche e le funzionalità di ogni tipo di conferenza.
  
### <a name="web-conferencing"></a>Conferenza Web

Le conferenze Web consentono ai partecipanti alla riunione di collaborare ai documenti condivisi durante la riunione e al relatore della riunione di condividere le applicazioni tramite il client Skype for business. Web Conferencing offre le caratteristiche seguenti: 
  
- **Lavagna e annotazioni.** Una lavagna è un'area di disegno vuota che può essere usata per la collaborazione, con testo, input penna, disegni e immagini. Le annotazioni effettuate sulle lavagne possono essere visualizzate da tutti i partecipanti alla riunione. La funzionalità Lavagna migliora la collaborazione consentendo ai partecipanti alla riunione di discutere idee, brainstorming, appunti e così via.
    
- **Polling.** La funzionalità di polling migliora la collaborazione consentendo ai relatori di determinare rapidamente le preferenze dei partecipanti. Durante le riunioni e le conversazioni online, i relatori possono usare il polling per raccogliere risposte anonime dai partecipanti. Tutti i relatori possono visualizzare i risultati e possono nascondere i risultati o visualizzarli in tutti i partecipanti.
    
- **Condivisione di applicazioni e condivisione desktop.** Durante una conferenza, il relatore della riunione può condividere l'intero desktop, una singola applicazione o singoli monitor in un ambiente con più monitor. Oltre a visualizzare solo il contenuto, gli altri partecipanti alla conferenza possono richiedere il controllo dello schermo del relatore e, con l'autorizzazione, interagire con il contenuto (incluso lo scorrimento e la modifica). I partecipanti alla riunione possono anche subentrare come relatore e iniziare a condividere il contenuto durante la riunione.
    
- **Condivisione di PowerPoint.** Consente agli utenti di condividere presentazioni di PowerPoint nella riunione tramite un server di Office Web Apps, che consente di:
    
  - Schermi ad alta risoluzione e supporto per le funzionalità di PowerPoint, ad esempio animazioni, transizioni diapositiva e video incorporato.
    
  - I dispositivi mobili possono accedere a queste presentazioni.
    
  - Gli utenti con le autorizzazioni appropriate possono scorrere una presentazione di PowerPoint indipendentemente dalla presentazione stessa. Ad esempio, mentre Ken sta presentando la sua presentazione, Heidi può vedere le diapositive che vuole senza influire sulle presentazioni di Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferenze audio e video

Le conferenze audio e video consentono l'audio e il video nella riunione. L'audio consente ai partecipanti di comunicare tra loro come se fossero nella stessa stanza. Video consente la visualizzazione video nel client Skype for business di eventuali partecipanti o relatori che partecipano alla riunione con una Web Cam o un dispositivo di conferenza che supporta il video.
  
 Skype for Business Server offre diverse funzionalità che gli utenti possono usare per configurare l'esperienza di audioconferenza per l'utente, inclusi i seguenti:
  
- **Disattivazione del pubblico.** Il relatore può usare questa impostazione per disattivare l'audio di tutti i partecipanti alla conferenza e inserire la conferenza in uno stato in cui non è possibile riattivare i presentatori.
    
- **Annunci di entrata/uscita per conferenze.** Se è stata abilitata la conferenza telefonica con accesso esterno, i relatori possono usare questa impostazione per attivare o disattivare gli annunci di entrata e uscita per ridurre al minimo le distrazioni mentre è in corso una conferenza.
    
- **Aggiunta di un utente tramite chiamata in uscita.** Relatori e partecipanti a cui è stata assegnata l'autorizzazione, è possibile aggiungere numeri PSTN alle conferenze e effettuare la chiamata in uscita per i numeri.
    
  Skype for Business Server offre diverse funzionalità che gli utenti possono usare per configurare l'esperienza di videoconferenza per l'utente, inclusi i seguenti:
  
- **Visualizzazione raccolta.** Nelle videoconferenze che hanno più di due persone, gli utenti vedranno automaticamente tutti i partecipanti alla conferenza. Se la conferenza include più di cinque partecipanti, il video dei partecipanti più attivi viene visualizzato nella riga superiore e viene visualizzata solo la foto per gli altri partecipanti. Il video a più parti è attivato per impostazione predefinita.
    
- **Video panoramico.** Se un dispositivo di videoconferenza RoundTable è installato nella sala conferenze, questa caratteristica offre una vista completa di 360 gradi della sala riunioni. La striscia video panoramica è disponibile solo con i dispositivi RoundTable.
    
- **Solo modalità video del relatore.** I relatori possono configurare la riunione in modo che venga visualizzata solo la visualizzazione del video. In questo modo si evitano le distrazioni nelle riunioni di grandi dimensioni quando sono disponibili più flussi video e si bloccano in origini diverse. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable.
    
- **Video in evidenza.** I relatori possono configurare la riunione in modo che solo il video di un partecipante selezionato che è un'origine video sia visibile dagli altri partecipanti alla conferenza. Questa modalità si applica anche ai video acquisiti e forniti dai dispositivi RoundTable per il video panoramico.
    
### <a name="dial-in-conferencing"></a>Chiamate in conferenza

Le conferenze telefoniche con accesso esterno consentono ai partecipanti alla riunione di partecipare alla parte audio di una riunione chiamando la riunione da un telefono. Le conferenze telefoniche con accesso esterno sono un sottoinsieme di servizi di audioconferenza e richiedono una configurazione aggiuntiva. Per altre informazioni sui servizi di conferenza telefonica con accesso esterno, vedere Pianificare i servizi di conferenza telefonica con accesso esterno [in Skype for Business Server](dial-in-conferencing.md) e [configurare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferenza di messaggistica istantanea

I servizi di conferenza di messaggistica istantanea (IM) consentono a più di due parti di comunicare in una singola sessione di messaggistica istantanea. Per informazioni dettagliate sulle conferenze [istantanee, vedere Pianificare la messaggistica istantanea e la presenza in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componenti di conferenza

I componenti che supportano le funzionalità di conferenza includono i seguenti:
  
- **Servizio applicazione.** Il servizio applicazione offre una piattaforma per la distribuzione, l'hosting e la gestione delle applicazioni UC (Unified Communications). I servizi di conferenza telefonica con accesso esterno usano due applicazioni UC che richiedono il servizio applicazione: operatore di conferenza e annuncio di conferenza. Il servizio applicazione viene installato e attivato per impostazione predefinita in ogni server front-end in un pool Front-end. Viene installato anche in ogni server standard per abilitare e configurare i servizi di conferenza telefonica con accesso esterno.
    
- **Applicazione Supervisore conferenza.** L'applicazione Supervisore conferenza è un'applicazione di comunicazioni unificate che accetta chiamate PSTN (Public Switched Telephone Network), riproduce le richieste e partecipa alle chiamate a una conferenza a/V. L'applicazione Operatore Conferenza viene installata e attivata per impostazione predefinita quando si abilitano i servizi di conferenza telefonica con accesso esterno.
    
- **Applicazione per l'annuncio di conferenza.** L'applicazione per gli annunci per conferenze è un'applicazione di comunicazioni unificata che riproduce i toni e chiede ai partecipanti PSTN di eseguire alcune azioni, ad esempio quando i partecipanti partecipano o abbandonano una conferenza, i partecipanti vengono disattivati o disabilitati, qualcuno immette il sala riunioni o conferenza è bloccata o sbloccata. L'applicazione di annunci conferenza supporta anche i comandi DTMF (Dual-Tone Multi-Frequency) dalla tastiera del telefono. L'applicazione per l'annuncio di conferenza viene automaticamente installata e attivata per impostazione predefinita quando si abilitano i servizi di conferenza telefonica con accesso esterno.
    
- **Pagina delle impostazioni di conferenza telefonica con accesso esterno.** La pagina delle impostazioni dei servizi di conferenza telefonica con accesso esterno consente di visualizzare i numeri di chiamata in conferenza con le lingue disponibili, le informazioni sulla conferenza assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in conferenza e supporta la gestione dei PIN (Personal Identification Number) e informazioni di conferenza assegnate. La pagina Impostazioni conferenza telefonica con accesso esterno viene installata automaticamente come parte dei servizi Web.
    
- **Mediation Server e gateway PSTN.** I servizi di conferenza telefonica con accesso esterno richiedono un Mediation Server per tradurre i segnali (e gli elementi multimediali in alcune configurazioni) tra Skype for Business Server e il gateway PSTN e un gateway PSTN per tradurre segnali e elementi multimediali tra il Mediation Server e il gateway PSTN . Per i servizi di conferenza telefonica con accesso esterno, è necessario distribuire almeno un Mediation Server e almeno una delle opzioni seguenti:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Session Border Controller (SBC) (per un provider di servizi di telefonia Internet a cui ci si connette configurando un trunk SIP)
    
  > [!NOTE]
  > Se si sta distribuendo anche VoIP aziendale, Mediation Server e gateway PSTN fanno parte della distribuzione VoIP aziendale. Se non si sta distribuendo VoIP aziendale, è necessario distribuire almeno un Mediation Server e almeno un gateway PSTN, IP-PBX o SBC per i servizi di conferenza telefonica con accesso esterno. 
  
- **Archivio file.** Il file Store viene usato per i file audio dei nomi registrati. File Store è un componente standard in tutte le distribuzioni Enterprise Edition o Standard Edition.
    
- **Archivio utenti.** L'archivio degli utenti viene usato per archiviare i pin di Skype for Business Server. Vengono hashati i pin. L'archivio utenti è un componente standard in tutte le distribuzioni Enterprise Edition o Standard Edition.
    
- **Server di Office Web Apps.** Per usare le funzionalità di conferenza Web, gli amministratori devono installare Office Web Apps Server e devono configurare Skype for Business Server per comunicare con Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Criteri conferenza

Per applicare i criteri dell'organizzazione e controllare l'utilizzo della larghezza di banda, è possibile impostare i criteri per i tipi di riunioni che gli utenti possono organizzare. Puoi definire una vasta gamma di criteri di conferenza e assegnarli a singoli utenti e gruppi di utenti. È anche possibile impostare i criteri che governano le conversazioni peer-to-peer. Per informazioni dettagliate sull'impostazione dei criteri di conferenza, vedere [gestire i criteri di conferenza in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Per informazioni dettagliate sulla gestione della larghezza di banda, vedere [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Supporto per le riunioni di grandi dimensioni

Le dimensioni delle riunioni supportate da Skype for Business Server variano a seconda che i servizi di conferenza siano ospitati in un pool condiviso o dedicato:
  
- In un pool condiviso, Skype for Business Server può ospitare riunioni con un massimo di 250 utenti. Un pool condiviso è un pool che ospita tutti i carichi di lavoro di Skype for Business Server, tra cui messaggistica istantanea e presenza, conferenza e VoIP aziendale. 
    
- In un pool dedicato, Skype for Business Server può supportare riunioni con un massimo di 1000 partecipanti che usano conferenze Web e audio/video (A/V), tra cui la condivisione di presentazioni di PowerPoint. Questo supporto richiede un pool dedicato configurato per supportare riunioni di grandi dimensioni e gestito in modo da garantire l'hosting di una sola riunione di grandi dimensioni alla volta. 
    
Per altre informazioni sulla gestione di riunioni di grandi dimensioni, vedere [pianificare le riunioni di grandi dimensioni in Skype for Business Server](large-meetings.md).
  
Se l'organizzazione richiede funzionalità di riunione più ampie, è consigliabile implementare un ambiente ibrido che sfrutta Skype meeting broadcast, un servizio online che fa parte di Office 365. Skype meeting Broadcast consente agli utenti di ospitare e trasmettere riunioni a un pubblico online di grandi dimensioni fino a 10.000 partecipanti. L'uso di Skype meeting broadcast richiede che Skype for Business Server sia già configurato in una configurazione ibrida con un tenant di Office 365 di produzione. Tutti gli utenti devono avere un tenant online stabilito come prerequisito. Se si è interessati alla distribuzione di una soluzione ibrida che può trarre vantaggio da Skype meeting broadcast, vedere [configurare la distribuzione locale per Skype meeting broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinare le esigenze delle organizzazioni

Quando si determina quali funzionalità di conferenza distribuire, è necessario prendere in considerazione le funzionalità che si desidera siano disponibili per gli utenti e le funzionalità di larghezza di banda della rete. Nell'elenco seguente viene illustrata la procedura di pianificazione dei servizi di conferenza per determinare quali funzionalità di conferenza è necessario distribuire, in base ai requisiti dell'organizzazione.
  
> [!NOTE]
> Quando si abilitano i servizi di conferenza alla distribuzione, si abilitano automaticamente sia Web che A/V Conferencing. È tuttavia possibile disabilitare le caratteristiche specifiche configurando i criteri di conferenza come descritto in precedenza in questo argomento. 
  
- **Si desidera abilitare le conferenze Web, che includono la collaborazione tra documenti e la condivisione di applicazioni?**
    
    In questo caso, è necessario abilitare i servizi di conferenza per il pool Front-end usando lo strumento pianificazione oppure usando generatore di topologie. Per altre informazioni, vedere [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    La condivisione delle applicazioni richiede e usa più larghezza di banda della collaborazione tra documenti. Skype for Business Server offre un meccanismo di limitazione per controllare ogni sessione di condivisione delle applicazioni. Per impostazione predefinita, questa opzione è impostata su 1,5 KB/secondo per ogni sessione. Se non si vuole abilitare la condivisione delle applicazioni ma si vuole collaborare con i documenti, è possibile abilitare le conferenze e usare i criteri di conferenza per disabilitare la condivisione delle applicazioni. Per informazioni dettagliate sulla configurazione dei criteri di conferenza, vedere [gestire i criteri di conferenza in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Per consentire agli utenti di condividere presentazioni di PowerPoint, è necessario configurare Office Web Apps Server. Per informazioni dettagliate sulla configurazione di Office Web Apps Server, vedere [configurare l'integrazione con Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Si desidera abilitare le conferenze audio e video?**
    
    In questo caso, è necessario abilitare i servizi di conferenza per il pool Front-end usando lo strumento pianificazione oppure usando generatore di topologie. Per altre informazioni, vedere [distribuire servizi di conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    Le conferenze audio e video richiedono e usano più larghezza di banda della rete rispetto alle conferenze Web (che includono la collaborazione tra documenti e la condivisione delle applicazioni). Se non si vogliono abilitare le conferenze audio e video, ma si vuole abilitare i servizi di conferenza Web, è possibile abilitare la conferenza e usare i criteri di conferenza per disabilitare riunioni A/V.
    
    Se si vuole abilitare le conferenze audio ma non le conferenze video, è possibile abilitare servizi di conferenza a/V e usare i criteri di conferenza per evitare videoconferenze. In alternativa, puoi abilitare i servizi di conferenza A/V e consentire solo a determinati utenti di avviare o partecipare a conferenze A/V. 
    
    Per altre informazioni sulla configurazione dei criteri di conferenza, vedere [gestire i criteri di conferenza in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Enterprise Voice non è necessaria per l'uso di servizi di conferenza A/V. Se si abilita una conferenza telefonica A/V, gli utenti possono aggiungere audio alle loro conferenze se hanno dispositivi audio, anche se si usa un PBX per la soluzione telefono. 
  
- **Si vuole consentire agli utenti di partecipare alla parte audio delle conferenze quando si usa un telefono PSTN?**
    
    In caso affermativo, distribuire e abilitare i servizi di conferenza telefonica con accesso esterno. Gli utenti invitati, sia all'interno che all'esterno dell'organizzazione, possono quindi partecipare alla parte audio delle conferenze usando un telefono PSTN.
    
    I servizi di conferenza telefonica con accesso esterno sono una funzionalità facoltativa che è possibile configurare quando si distribuiscono le conferenze di Skype for Business Server. Anche se i servizi di conferenza telefonica con accesso esterno usano alcuni degli stessi componenti usati da Enterprise Voice, è possibile distribuire i servizi di conferenza telefonica con accesso esterno anche se non si distribuisce VoIP aziendale. I servizi di conferenza telefonica con accesso esterno supportano utenti Enterprise e Anonymous. Per altre informazioni sulla configurazione dei servizi di conferenza telefonica con accesso esterno per le aziende e gli utenti anonimi, vedere distribuire servizi di [conferenza in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) e configurare i servizi di [conferenza telefonica con accesso esterno in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Si desidera consentire agli utenti esterni con client Skype for business di partecipare a conferenze?**
    
    Consentendo la partecipazione esterna alle riunioni, è possibile massimizzare l'investimento in Skype for Business Server. Gli utenti esterni possono includere:
    
  - **Utenti remoti.** Gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e usano i loro portatili o altri dispositivi Skype for Business Server.
    
  - **Utenti federati.** Gli utenti di aziende con cui si lavora e che eseguono anche Skype for Business Server. Per consentire agli utenti di contattare facilmente questi utenti, è possibile creare relazioni federate con queste società.
    
  - **Utenti anonimi.** Tutti gli altri utenti esterni invitati in modo specifico dagli utenti a partecipare a conferenze specifiche. Un organizzatore della riunione nella tua azienda può inviare un invito di posta elettronica per una conferenza a un utente esterno. Il messaggio di posta elettronica include un collegamento a cui l'utente esterno può fare clic per partecipare alla conferenza.
    
    Se si vuole consentire agli utenti esterni, è necessario distribuire Edge Server. Inoltre, con i server perimetrali distribuiti è possibile creare relazioni federate con altre organizzazioni, ad esempio i clienti o i fornitori, e gli utenti di tali organizzazioni possono collaborare più facilmente con gli utenti.
    
    Per informazioni dettagliate sulla distribuzione di Edge Server, vedere Pianificare Edge Server e distribuire Edge Server. Per informazioni dettagliate sull'abilitazione dell'accesso esterno per il server Office Web Apps, vedere [configurare l'integrazione con Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Si desidera controllare i client che possono partecipare alle riunioni di Skype for Business Server?**
    
    In questo caso, devi configurare la pagina di partecipazione alla riunione in modo che siano disponibili solo le opzioni client che vuoi supportare. Ogni volta che un utente fa clic su un collegamento per partecipare a una riunione pianificata, Skype for Business Server rileva se un client è già installato nel computer. Avvia quindi il client predefinito e apre la pagina di partecipazione alla riunione, che contiene i collegamenti per i client alternativi. La pagina di partecipazione alla riunione contiene sempre l'opzione per l'uso di Skype for Business Web App. Oltre a questa opzione, è possibile decidere se includere i collegamenti per il partecipante e le versioni precedenti di Communicator. 
    

