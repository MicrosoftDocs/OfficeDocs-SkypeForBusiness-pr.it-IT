---
title: Microsoft Teams |  Valuta ambiente | Adozione, individuazione
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: Come eseguire una scoperta ambientale dettagliata quando si pianifica il viaggio da Skype for business a Microsoft teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 68bd92067bffc2ed88e8a9d44e228ce442021b29
ms.sourcegitcommit: 73518a589db1a9883fc97827f0ddb9132995fbfa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42236676"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Individuazione ambientale per l'implementazione di Microsoft Teams
===================================================

L'individuazione è uno dei primi passaggi principali da eseguire durante la pianificazione del viaggio a Microsoft teams.

Si esegue una scoperta dettagliata dell'ambiente per comprendere meglio lo stato corrente e per rivelare eventuali difficoltà o, ancora di più, possibili bloccanti per l'esecuzione dell'implementazione del team.

## <a name="discovery-questionnaire"></a>Questionario di individuazione

Il questionario di esempio seguente illustra una serie di domande per verificare che l'organizzazione sia pronta per l'implementazione corretta di servizi di audioconferenza e telefono con funzionalità per i piani di chiamata in teams.

Tutte le questioni relative all'infrastruttura di collaborazione esistente e al tenant di Office 365, alla rete, agli endpoint, alle operazioni e all'adozione e alla disponibilità sono incluse nell'ambito del questionario sull'individuazione ambientale.

Il questionario è suddiviso in più sezioni per confermare la disponibilità dell'organizzazione per la distribuzione di team in più aree principali. Collaborare con il team di progetto per specificare le informazioni richieste con il maggior dettaglio possibile per facilitare le attività di pianificazione.

> [!TIP]
> È possibile iniziare copiando il questionario in un documento di Microsoft Word. Provare a rispondere a tutte le domande e acquisire tutti i dettagli man mano che ci si sposta.

<a name="project-team"></a>Team di progetto
---

Acquisire informazioni dettagliate sui principali stakeholder del progetto di implementazione del team. Tieni presente che una persona può svolgere diversi ruoli in tutto il progetto.

> | Ruolo | Nome, indirizzo di posta elettronica, numero di telefono | Posizione, fuso orario | Commenti |
> |---|---|---|---|
> | Sponsor esecutivo | | | |
> | Lead progetto | | | |
> | Lead di collaborazione/architetto | | | |
> | Consulente | | | |
> | Project Manager | | | |
> | Specialista per la gestione/adozione delle modifiche | | | |
> | Cavo di rete | | | |
> | Lead di sicurezza | | | |
> | Lead per la telefonia | | | |
> | Lead desktop | | | |
> | Supporto/help desk lead | | | |
> | Lead di distribuzione | | | |
> | Proprietario del servizio | | | |
> | Strutture lead | | | |
> | Video Team Lead | | | |
> | Lead della business unit | | | |

<a name="office-365-tenant-details"></a>Dettagli del tenant di Office 365
---

È consigliabile disporre di un tenant di Office 365 attivo durante l'utilizzo di questo questionario. Se non è ancora stato attivato o configurato un tenant di Office 365, vedere [pianificare la configurazione di office 365 per le aziende](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Usare la tabella seguente per acquisire informazioni sul tenant di Office 365.

> | Domanda | Answer | Commenti |
> |---|---|---|
> | Nota il tenant di Office 365 di produzione <br>nome e ID nella colonna risposta <br/>Se si ha più di un tenant <br>associato all'organizzazione <br>Nota tutti gli ID. | Nome tenant: <br/>ID tenant:| |
> | In quali aree geografiche sono distribuiti i tenant?| | |
> | Questi tenant sono Office 365 multitenant o <br>Dedicato? | <input type="checkbox">Multitenant<br/> <input type="checkbox">Dedicato | |
> | Quali prodotti Microsoft online sono in uso oggi? <br/>Nota il numero di utenti abilitati per ogni <br>servizio nella colonna comments. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for business <br>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox">Altri| |
> | Quale livello di licenza è abilitato per Skype for <br>Utenti business online | <input type="checkbox">E1/G1 <br/> <input type="checkbox">E2/G2 <br/> <input type="checkbox">E3/G3 <br/> <input type="checkbox">E4/G4 E5 | Numero di utenti <br>per ogni SKU: |
> | Che cos'è l'insieme di strutture Active Directory corrente <br>livello di funzionalità nell'ambiente? <br/>Se sono presenti più insiemi di strutture, tenere presente che i dettagli <br>nella colonna comments. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Cosa si usa per la directory <br>sincronizzazione oggi? |<input type="checkbox">Nessuna sincronizzazione (solo cloud) <br/> <input type="checkbox">Azure Active Directory <br>&nbsp;&nbsp; &nbsp;Connettersi <br/> <input type="checkbox">Altro (specificare il <br>&nbsp;&nbsp; &nbsp;| |
> | L'identità federata è attualmente distribuita? <br/>(Active Directory Federation Services o <br>terze parti) | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Se si usa l'identità federata, qual è la <br>infrastruttura federativa? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox">Federazione di terze parti <br>&nbsp;&nbsp; &nbsp;gateway <br>&nbsp;&nbsp; (Prendere nota dei &nbsp;dettagli nel <br>&nbsp;&nbsp; &nbsp; | |
> | Se attualmente si gestisce un Office 365 attivo <br>tenant, è il dominio SMTP/SIP della propria <br>utenti mirati associati al tenant? | <input type="checkbox">N/d: nessun Office 365 <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">No, SMTP/SIP degli utenti <br>&nbsp;&nbsp; &nbsp;è associato <br>&nbsp;&nbsp; &nbsp;tenant in <br>&nbsp;&nbsp; &nbsp;Office 365 <br/> <input type="checkbox">Sì, SMTP/SIP degli utenti <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp; | |
> | Gli utenti di UPN corrispondono all'indirizzo SMTP principale? | <input type="checkbox">Sì <br/> <input type="checkbox">Non <br/> <input type="checkbox">Incoerente | |

<a name="existing-collaboration-platform-summary"></a>Riepilogo della piattaforma di collaborazione esistente
---

Usare la tabella seguente per acquisire informazioni sulla distribuzione della piattaforma di collaborazione esistente.

> | Domanda | Answer | Commenti |
> |---|---|---|
> | Microsoft teams è distribuito? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Skype for business è distribuito? <br/>Per le distribuzioni locali e ibride, verificare che <br>si nota la versione e l'aggiornamento cumulativo (CU) <br>Dettagli nella colonna comments. | <input type="checkbox">Sì, Office 365 <br/> <input type="checkbox">Sì, ibrido (con Office 365) <br/> <input type="checkbox">Sì, locale <br/> <input type="checkbox">Sì, online, dedicato <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sì, ospitati, dedicati <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sì, ospitata, condivisa (terza parte) <br/> <input type="checkbox">No, altro | |
> | Exchange è distribuito? <br/>Per le distribuzioni locali e ibride, verificare che <br>si notano i dettagli della versione e della CU nei commenti <br>colonna. | <input type="checkbox">Sì, Office 365 <br/> <input type="checkbox">Sì, ibrido (con Office 365) <br/> <input type="checkbox">Sì, locale <br/> <input type="checkbox">Sì, online, dedicato <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sì, ospitati, dedicati <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sì, ospitati, condivisi <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">No, altro | |
> | SharePoint è distribuito? <br/>Per le distribuzioni locali e ibride, verificare che <br>si notano i dettagli della versione e della CU nei commenti <br>colonna. | <input type="checkbox">Sì, Office 365 <br/> <input type="checkbox">Sì, ibrido (con Office 365) <br/> <input type="checkbox">Sì, locale <br/> <input type="checkbox">Sì, online, dedicato <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sì, ospitati, dedicati <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Sì, ospitati, condivisi <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">No, altro | |
> | Office 365 OneDrive for business è distribuito? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Esistono altre piattaforme di terze parti distribuite <br>e in uso oggi? In caso affermativo, prendere nota del numero di utenti di <br>queste piattaforme e i dettagli sull'utilizzo nei commenti <br>colonna. | <input type="checkbox">Cisco WebEx <br/> <input type="checkbox">Flessibilità <br/> <input type="checkbox">Altro (specificare nei commenti <br>&nbsp;&nbsp; &nbsp; | Numero di utenti: <br/>Dettagli|
> | Si prevede di trasferire gli utenti da queste terze parti <br>piattaforme a teams? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Qual è la soluzione per la telefonia e i servizi di conferenza corrente <br>degli utenti che hanno un ambito per questa iniziativa? | | |
> | [Gli SBC supportano il routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) distribuito per gli uffici che si trovano nell'ambito di questa iniziativa? <br>In caso affermativo, prendere nota dei dettagli nella colonna commenti.| <input type="checkbox">Sì <br/> <input type="checkbox">Non ||

<a name="collaboration-platform-deployment-details"></a>Dettagli sulla distribuzione della piattaforma di collaborazione
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione dei team usando la tabella di esempio seguente. Se non sono stati distribuiti team, saltare questa sezione.

> | Domanda | Answer | Commenti |
> |---|---|---|
> | Quali tipi di utenti sono abilitati per i team? | <input type="checkbox">Tutti gli utenti dell'organizzazione <br/> <input type="checkbox">Utenti/gruppi utente specifici <br>&nbsp;&nbsp; (Specificare nella colonna &nbsp;comments) ||
> | Quali caratteristiche e modalità di teams sono in uso? | <input type="checkbox">Conversazioni basate su canale <br/> <input type="checkbox">Chat privata <br/> <input type="checkbox">Accesso Guest <br/> <input type="checkbox">Riunioni di canale <br/> <input type="checkbox">Riunioni private <br/> <input type="checkbox">Chiamate private <br/> <input type="checkbox">Meetup del canale ad-hoc <br/> <input type="checkbox">Video nelle riunioni <br/> <input type="checkbox">Condivisione dello schermo nelle riunioni <br/> <input type="checkbox">Audioconferenza <br/><input type="checkbox">Applicazioni (app)<br> &nbsp;&nbsp; Schede &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; Bot &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; Connettori &nbsp; <input type="checkbox"><br><input type="checkbox">Integrazione di archiviazione cloud personalizzata <br>&nbsp;&nbsp; (Box, Dropbox, ShareFile, Google &nbsp; Drive) <br/> <input type="checkbox">Integrazione tramite posta elettronica del canale <br/> <input type="checkbox">Altro (specificare nella colonna Comments). | |
> | Quali applicazioni sono state distribuite in teams? | | |
> | Sono state bloccate in modo specifico eventuali funzionalità Teams? <br/>In caso affermativo, prendere nota dei dettagli nella colonna commenti. | <input type="checkbox">Sì <br/> <input type="checkbox">Non ||
> | Quali client di team sono in uso? | <input type="checkbox">Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox">Mac <br/> <input type="checkbox">Linux <br/>  <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Windows Mobile | |
> | Chi ha le autorizzazioni per creare team? | <input type="checkbox">Tutti gli utenti dell'organizzazione <br>&nbsp;&nbsp; (Questa è l'impostazione &nbsp;predefinita) <br/> <input type="checkbox">Persone specifiche <br>&nbsp;&nbsp; &nbsp;comments. | |
> | Si usano le caratteristiche di sicurezza e conformità in teams? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for business online (se applicabile)

Se applicabile, Acquisisci i dettagli della distribuzione di Skype for business online usando la tabella di esempio seguente. Se non è stata distribuita la distribuzione di Skype for business online, saltare questa sezione.

> | Domanda | Answer | Commenti |
> |---|---|---|
> | Tipi di utenti abilitati per Skype <br>for business online? | <input type="checkbox">Tutti gli utenti dell'organizzazione <br/> <input type="checkbox">Utenti/gruppi utente specifici <br>&nbsp;&nbsp; (Specificare nella colonna &nbsp;comments) | |
> | Quali sono le modalità e le caratteristiche attualmente disponibili <br>in uso oggi? | <input type="checkbox">Messaggistica istantanea e presenza (IM/P)<br/> <input type="checkbox">Conferenza telefonica <br/> <input type="checkbox">Federazione <br/> <input type="checkbox">Registrazione delle riunioni <br/> <input type="checkbox">Servizi di audioconferenza Microsoft <br/> <input type="checkbox">Audioconferenza di terze parti <br>&nbsp;&nbsp; (Prendere nota dei dettagli nella colonna Comments &nbsp;). <br/> <input type="checkbox">Piani chiamante (in precedenza chiamate PSTN) <br/> <input type="checkbox">Operatori automatici dell'organizzazione <br/> <input type="checkbox">Code di chiamata | |
> | Hai bloccato in modo specifico qualsiasi Skype for <br>Funzionalità business online <br>In caso affermativo, prendere nota dei dettagli nella colonna commenti. | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Quale metodo si usa o si prevede di usare per <br>connettere il sistema telefonico (in precedenza cloud PBX) a <br>la rete PSTN? <br/>Selezionare tutto ciò che si applica. | <input type="checkbox">Piani chiamante (in precedenza chiamate PSTN) <br/> <input type="checkbox">Connettività PSTN locale (sfruttando le esistenti <br>&nbsp;&nbsp; Skype for business 2015 o Lync &nbsp;Server 2013 <br>&nbsp;&nbsp; &nbsp;distribuzione) <br/> <input type="checkbox">Connettività PSTN locale (tramite il connettore Cloud) | |
> | È stato convertito qualsiasi numero di telefono in Microsoft? <br/>Questo si applica ai piani di chiamata e all'audio <br>Funzionalità di conferenza. | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for business locale (se applicabile)

Se applicabile, Acquisisci i dettagli della distribuzione di Skype for business usando la tabella di esempio seguente. Se non è stata distribuita in locale Skype for business, saltare questa sezione.

> | Domanda | Answer | Commenti |
> |---|---|---|
> | Quali versioni di Lync o Skype for business sono attualmente <br>vengono distribuiti in locale? | <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Skype for Business Cloud Connector Edition | |
> | È configurata l'Hybrid con Skype for business online? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Questo ambiente è ospitato e gestito da terze parti? <br/>In caso affermativo, prendere nota dei dettagli nella colonna commenti. | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Quali modalità e funzionalità sono attualmente in uso <br>oggi? | <input type="checkbox">Messaggistica istantanea e presenza (IM/P) <br/> <input type="checkbox">Conferenza telefonica <br/> <input type="checkbox">Federazione <br/> <input type="checkbox">Registrazione delle riunioni <br/> <input type="checkbox">Chat persistente/Chat di gruppo <br/> <input type="checkbox">Servizi di audioconferenza Microsoft <br>&nbsp;&nbsp; (già chiamata in conferenza &nbsp;telefonica) <br>&nbsp;&nbsp; &nbsp; <br>&nbsp;&nbsp; &nbsp;for business <br/> <input type="checkbox">Audioconferenza di terze parti <br>&nbsp;&nbsp; (Prendere nota dei dettagli nella colonna &nbsp;comments) <br/> <input type="checkbox">VoIP aziendale con PSTN locale <br>&nbsp;&nbsp; &nbsp;connettività <br/> <input type="checkbox">Piani di chiamata (in precedenza chiamate PSTN) tramite <br>&nbsp;&nbsp; Ibrido con Skype for &nbsp;business online | |
> | Quale versione di Edge Server è stata distribuita? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox">Lync Server 2010 <br/> <input type="checkbox">Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Si dispone di Lync o Skype for Business Edge distribuito <br>in più di un Data Center? <br/>In caso affermativo, prendere nota dei dettagli nella colonna commenti. | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Selezionare i servizi che il ruolo di Edge offre oggi. | <input type="checkbox">Accesso utenti esterni (utenti aziendali) <br/> <input type="checkbox">Accesso remoto agli utenti (Anonymous External <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Federazione <br/> <input type="checkbox">Inoltro multimediale | |
> | Quale delle seguenti funzionalità per le chiamate vocali <br>Attualmente sono presenti dipendenze? <br/>Notare eventuali dipendenze aggiuntive nei commenti <br>colonna. | <input type="checkbox">Opzioni di occupato <br/> <input type="checkbox">Parcheggio delle chiamate <br/> <input type="checkbox">Raccolta chiamate o ritiro chiamate di gruppo <br/> <input type="checkbox">Telefoni per area comune o "Hot desking" <br/> <input type="checkbox">Response Groups o Hunt Groups <br/> <input type="checkbox">Aspetto della linea condivisa <br/> <input type="checkbox">Linea privata <br/> <input type="checkbox">Segreteria telefonica <br/> <input type="checkbox">Chiamata tramite lavoro <br/> <input type="checkbox">Numeri di informazioni o di emergenza <br>&nbsp;&nbsp; (911, 811, &nbsp;411) <br/> <input type="checkbox">Chiamata di estensione <br/> <input type="checkbox">Operatore automatico <br/> <input type="checkbox">Accesso sottoscrittore <br/> <input type="checkbox">Dispositivi analogici <br/> <input type="checkbox">Fax <br/> <input type="checkbox">ID chiamante che maschera o altera <br/> <input type="checkbox">Routing basato sulla posizione <br/> <input type="checkbox">Routing con costi minimi <br/> <input type="checkbox">Telefoni per l'ascensore | |

<a name="networking-and-access-to-office-365-services"></a>Networking e accesso ai servizi di Office 365
---

Usare la tabella seguente per acquisire i dettagli di rete dell'organizzazione e la modalità di connessione degli utenti ai servizi di Office 365.

> | Domanda | Answer | Commenti |
> |---|---|---|
> | Come fare (o come faranno) gli utenti nell'ambito della migrazione <br>accedere ai team quando si trova in ufficio? <br/>Selezionare tutto ciò che si applica. | <input type="checkbox">Connessione NAT instradata <br/> <input type="checkbox">Server proxy <br/> <input type="checkbox">Wi-Fi pubblico <br/> <input type="checkbox">Wi-Fi gestito (non pubblico) <br/> <input type="checkbox">ExpressRoute (peering Microsoft) ||
> | Se l'accesso a Office 365 avviene tramite un server proxy, esiste <br>un modo per aggirare il proxy? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | ExpressRoute viene usato oggi? | <input type="checkbox">Sì <br/> <input type="checkbox">Non <br/> <input type="checkbox">No, ma è in fase di progettazione | |
> | È stata eseguita una valutazione della conformità della rete? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Gli utenti devono usare una VPN per la connessione a <br>risorse aziendali in remoto? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Se si usa una rete VPN, è possibile escludere il traffico dei team da <br>la VPN per accedere direttamente ai servizi di Office 365? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | La rete supporta QoS? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | È possibile assegnare priorità al traffico audio e video di Teams <br>per guidare un'esperienza di alta qualità? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | Tutte le posizioni all'interno di un'area geografica hanno l'uscita Internet <br>oppure l'uscita Internet è centralizzata per l'intera area geografica? | <input type="checkbox">Accesso locale a Internet <br/> <input type="checkbox">Accesso centralizzato a Internet | |

<a name="endpoints"></a>Endpoint
---

Usare la tabella seguente per acquisire i dettagli dei client e degli endpoint in uso.

> | Domanda | Answer | Commenti |
> |---|---|---|
> | Quali sistemi operativi desktop sono utilizzati dagli utenti? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox">Mac (specificare la versione nella colonna Comments). <br/> <input type="checkbox">Linux (specificare la distribuzione nella colonna Comments) <br/><input type="checkbox">Altro (prendere nota dei dettagli nella colonna Comments). | |
> | Quale versione di Microsoft Office viene distribuita <br>a questi dispositivi? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office per Mac 2011 <br/> <input type="checkbox">Office per Mac 2016 <br/> <input type="checkbox">Altro (prendere nota dei dettagli nella colonna Comments). | |
> | Quale tecnologia di distribuzione di Office è in uso <br>nell'organizzazione? | <input type="checkbox">MSI <br/> <input type="checkbox">A portata di clic | |
> | Quali sono i dispositivi mobili consentiti e supportati <br>piattaforme in uso? <br/>Selezionare tutto ciò che si applica. | <input type="checkbox">Windows <br/> <input type="checkbox">Mobile <br/> <input type="checkbox">iOS <br/> <input type="checkbox">Android <br/> <input type="checkbox">Altro (prendere nota dei dettagli nella colonna Comments). | |
> | Come vengono forniti i dispositivi mobili? <br/>Selezionare tutto ciò che si applica. | <input type="checkbox">Dispositivi aziendali <br/> <input type="checkbox">Creare un dispositivo personalizzato | |
> | Quali dispositivi usano attualmente gli utenti per accedere <br>Servizi di conferenza telefonica <br>(cornetti, auricolari, telefoni, video)? | | |

<a name="operations"></a>Operazioni
---

Usare la tabella seguente per acquisire i dettagli degli aspetti operativi dell'ambiente.

> | Domanda | Answer | Commenti |
> |---|---|---|
> | Qual è il modello di operazioni per il server Lync <br>Skype for Business Server o distribuzione di Office 365 <br>oggi? | | |
> | È possibile delineare la disposizione di supporto corrente per <br>Lync Server, Skype for Business Server o Office 365? | | |
> | Se si sta distribuendo in più paesi o aree geografiche, <br>ogni paese/area geografica ha il proprio IT/telefonia <br>il personale con cui collaborare o verrà gestito in modo centralizzato? | <input type="checkbox">Operazioni e supporto regionali <br/> <input type="checkbox">Operazioni e supporto centralizzato | |
> | Si segue la metodologia di qualità delle chiamate? | <input type="checkbox">Sì <br/> <input type="checkbox">Non | |
> | È stato assegnato un singolo utente o un team al <br>Ruolo di campione di qualità per la piattaforma di collaborazione <br>in uso? | <input type="checkbox">Sì <br/> <input type="checkbox">Non ||
> | Come si monitora il server Lync, Skype for <br>Server aziendale o distribuzione di Office 365? | | |
> | Si verificano problemi di qualità delle chiamate? | <input type="checkbox">Sì<br/> <input type="checkbox">Non | |
> | Come e quando si offre formazione alla propria <br>helpdesk su nuovi servizi e funzionalità? | | |

<a name="adoption-and-readiness"></a>Adozione e disponibilità
---

Usare la tabella seguente per acquisire lo stato di approvazione e preparazione corrente dell'organizzazione.

>
> | Domanda | Answer | Commenti |
> |---|---|---|
> | Qual è l'uso attivo corrente di <br>Skype for business? | **** totale di utenti attivi e utenti abilitati | |
> | Modalità di utilizzo dell'organizzazione <br>Skype for business? | conversazioni di 1:1 <br>&nbsp;&nbsp; &nbsp; Messaggistica <input type="checkbox"> istantanea <br>&nbsp;&nbsp; Chiamata &nbsp; <input type="checkbox"> <br>&nbsp;&nbsp; Condivisione &nbsp; <input type="checkbox"><br> Riunioni <br>&nbsp;&nbsp; &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; Condivisione &nbsp; <input type="checkbox"><br>&nbsp;&nbsp; Chiamata &nbsp; <input type="checkbox"> | |
> | L'organizzazione ha un'adozione da parte dell'utente <br>e cambiare il team di gestione? | <input type="checkbox">Sì<br/> <input type="checkbox">Non | |
> | Come si fa a misurare il successo della tecnologia attualmente <br>Rollout come Skype for business? | | |
> | Qual è la percentuale della base utente che si vuole dire <br>adottato Skype for business? | | |
> | Che cos'è il sentimento degli utenti in Skype for business? | <input type="checkbox">Buona <br/> <input type="checkbox">Neutro <br/> <input type="checkbox">Male | |
> | Quale delle seguenti descrive meglio l'implementazione <br>strategia usata per Skype for business <br>distribuzione? | <input type="checkbox">Ampia portata: campagna di posta elettronica con <br>&nbsp;&nbsp; &nbsp; <br/> <input type="checkbox">Espansa: ampia portata e una varietà <br>&nbsp;&nbsp; di campagne di sensibilizzazione ( &nbsp;poster, <br>&nbsp;&nbsp; eventi, campioni) &nbsp;e formazione <br>&nbsp;&nbsp; (video, guide utente, in &nbsp;persona) <br/> <input type="checkbox">Personalizzata: espansa, più mirata <br>&nbsp;&nbsp; &nbsp;per persona <br/> <input type="checkbox">Altri <br>&nbsp;&nbsp; (Prendere nota dei dettagli nella colonna Comments &nbsp;). | |
