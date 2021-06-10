---
title: Compatibilità ambientale - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Come eseguire una scoperta ambientale dettagliata durante la pianificazione del viaggio da Skype for Business a Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 50c6845eabb56ea270e6eafa699fbba57d0639e3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105252"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Individuazione dell'ambiente per un'implementazione Microsoft Teams ambiente
===================================================

L'individuazione è uno dei primi passaggi chiave da eseguire durante la pianificazione del viaggio verso Microsoft Teams.

È possibile eseguire un'individuazione dettagliata dell'ambiente per comprenderne meglio lo stato corrente e per rivelare eventuali difficoltà o, ancora di più, possibili blocchi all'esecuzione dell'Teams aziendale.

## <a name="discovery-questionnaire"></a>Questionario di individuazione

Il questionario di esempio seguente illustra una serie di domande per confermare che l'organizzazione è pronta per l'implementazione di audioconferenza e Sistema telefonico con funzionalità Piani per chiamate in Teams.

Tutte le questioni relative all'infrastruttura di collaborazione esistente e all'organizzazione di Microsoft 365 o Office 365, alla rete, agli endpoint, alle operazioni e all'adozione e alla preparazione sono incluse nel questionario sulla scoperta dell'ambiente.

Il questionario è suddiviso in più sezioni per confermare la conformità dell'organizzazione per la distribuzione Teams in diverse aree principali. Collaborare con il team di progetto per fornire le informazioni richieste con il maggior numero di dettagli possibile per facilitare le attività di pianificazione.

> [!TIP]
> È possibile iniziare copiando il questionario in un Microsoft Word documento. Prova a rispondere a tutte le domande e acquisisci tutti i dettagli mentre ti sposti.

<a name="project-team"></a>Project team
---

Acquisire informazioni dettagliate sui principali stakeholder del Teams di implementazione. Si noti che una persona può svolgere diversi ruoli in tutto il progetto.

> | Ruolo | Nome, indirizzo di posta elettronica, numero di telefono | Luogo, fuso orario | Commenti |
> |---|---|---|---|
> | Executive Sponsor | | | |
> | Project Cliente potenziale | | | |
> | Cliente potenziale/architetto della collaborazione | | | |
> | Consulente | | | |
> | Project Responsabile | | | |
> | Change Management/Adoption Specialist | | | |
> | Cliente potenziale della rete | | | |
> | Cliente potenziale della sicurezza | | | |
> | Cliente potenziale di telefonia | | | |
> | Cliente potenziale del desktop | | | |
> | Lead del supporto tecnico/help desk | | | |
> | Cliente potenziale di distribuzione | | | |
> | Proprietario del servizio | | | |
> | Cliente potenziale strutture | | | |
> | Video Team Lead | | | |
> | Clienti potenziali di Business Unit | | | |

<a name="microsoft-365-or-office-365-organization-details"></a>Microsoft 365 o Office 365'organizzazione
---

È consigliabile avere un'organizzazione Microsoft 365 o Office 365 mentre si lavora a questo questionario. Se non è ancora stata attivata o configurata un'organizzazione Microsoft 365 o Office 365, vedere Pianificare la configurazione di [Microsoft 365 per le aziende.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

Usare la tabella seguente per acquisire informazioni sulla Microsoft 365 o Office 365 organizzazione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Annotare le informazioni di Microsoft 365<br/>o Office 365 e ID dell'organizzazione<br/>nella colonna Risposta. Se hai più<br/>più di un tenant associato a<br/>annotare tutti gli ID dell'organizzazione. | Nome tenant: <br/>ID tenant:| |
> | In quali aree sono distribuiti i tenant?| | |
> | Prendere nota del tipo di Microsoft 365 o <br/>Office 365 tenant. Sono multitenant <br/>o Dedicato? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> Dedicato | |
> | Quali prodotti Microsoft Online sono attualmente in uso? <br/>Annotare il numero di utenti abilitati per ogni <br/>nella colonna Commenti. | <input type="checkbox">Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox">SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox">Yammer <br/> <input type="checkbox"> Altro| |
> | Livello di licenza abilitato per Skype per <br/>Utenti di Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Il numero di utenti <br/>per ogni SKU: |
> | Qual è la foresta di Active Directory corrente <br/>livello di funzionalità nell'ambiente? <br/>Se sono presenti più foreste, prendere nota dei dettagli <br/>nella colonna Commenti. | <input type="checkbox">Windows Server 2000 <br/> <input type="checkbox">Windows Server 2003 <br/> <input type="checkbox">Windows Server 2008<br/> <input type="checkbox">Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Cosa si usa per la directory <br/>sincronizzazione oggi? |<input type="checkbox"> Nessuna sincronizzazione (solo cloud) <br/> <input type="checkbox">Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Connessione <br/> <input type="checkbox"> Altro (specificare nella casella <br/>&nbsp;&nbsp; &nbsp; Colonna Commenti.)| |
> | L'identità federata è attualmente distribuita? <br/>(Active Directory Federation Services o <br/>di terze parti) | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Se si usa l'identità federata, qual è il <br/>infrastruttura federativa? | <input type="checkbox">Windows 2008 R2 AD FS <br/> <input type="checkbox">Windows 2012 AD FS <br/> <input type="checkbox">Windows 2012 R2 AD FS <br/> <input type="checkbox">Windows 2016 AD FS <br/> <input type="checkbox"> Federazione di terze parti <br/>&nbsp;&nbsp; &nbsp; gateway (Prendere nota dei dettagli <br/>&nbsp;&nbsp; &nbsp; nella colonna Commenti. | |
> | Se attualmente si mantiene un'Microsoft 365<br/>o Office 365 tenant, è il dominio SMTP/SIP di <br/>gli utenti mirati associati al tenant? | <input type="checkbox">N/D - Nessuna Microsoft 365 o<br/>&nbsp;&nbsp; &nbsp; Office 365 tenant in posizione <br/> <input type="checkbox"> No, SMTP/SIP degli utenti <br/>&nbsp;&nbsp; &nbsp; il dominio non è associato <br/>&nbsp;&nbsp; &nbsp; con i tenant in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365<br/> <input type="checkbox"> Sì, SMTP/SIP degli utenti <br/>&nbsp;&nbsp; &nbsp; il dominio è associato <br/>&nbsp;&nbsp; &nbsp; con un tenant esistente in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365 | |
> | Gli UPN degli utenti corrispondono all'indirizzo SMTP principale? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No <br/> <input type="checkbox"> Incoerente | |

<a name="existing-collaboration-platform-summary"></a>Riepilogo della piattaforma di collaborazione esistente
---

Usare la tabella seguente per acquisire informazioni sulla distribuzione della piattaforma di collaborazione esistente.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | È Microsoft Teams distribuito? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Le Skype for Business distribuite? <br/>Per le distribuzioni locali e ibride, verificare che <br/>annotare la versione e l'aggiornamento cumulativo (CU) <br/>dettagli nella colonna Commenti. | <input type="checkbox">Sì, Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365 <br/> <input type="checkbox"> Sì, ibrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sì, locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sì, ospitata, dedicata <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> Sì, ospitato, condiviso <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> No, altro | |
> | È Exchange distribuito? <br/>Per le distribuzioni locali e ibride, verificare che <br/>annotare la versione e i dettagli dell'cu nei commenti <br/>colonna. | <input type="checkbox">Sì, Microsoft 365 <br/> <input type="checkbox"> Sì, ibrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sì, locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sì, ospitata, dedicata <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> Sì, ospitato, condiviso <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> No, altro | |
> | È SharePoint distribuito? <br/>Per le distribuzioni locali e ibride, verificare che <br/>annotare la versione e i dettagli dell'cu nei commenti <br/>colonna. | <input type="checkbox">Sì, Microsoft 365 <br/> <input type="checkbox"> Sì, ibrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sì, locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sì, ospitata, dedicata <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> Sì, ospitato, condiviso <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> No, altro | |
> | È OneDrive for Business distribuito? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Sono state distribuite altre piattaforme di terze parti <br/>e in uso oggi? In tal caso, prendere nota del numero di utenti di <br/>queste piattaforme e i dettagli sull'utilizzo nel <br/>Colonna Commenti. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Margine di flessibilità <br/> <input type="checkbox"> Altro (specificare nella casella <br/>&nbsp;&nbsp; &nbsp; Colonna Commenti.) | Numero di utenti: <br/>Dettagli:|
> | Stai pianificando di spostare gli utenti da queste terze parti <br/>piattaforme da Teams? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Qual è l'attuale soluzione di telefonia e conferenza <br/>degli utenti che hanno l'ambito di questa iniziativa? | | |
> | Sono state distribuite [le SBC che supportano il routing](./direct-routing-plan.md#supported-session-border-controllers-sbcs) diretto <br/>per gli uffici che hanno l'ambito di questa iniziativa? Se sì,<br/>Prendere nota dei dettagli nella colonna Commenti.| <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||

<a name="collaboration-platform-deployment-details"></a>Dettagli sulla distribuzione della piattaforma di collaborazione
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione Teams usando la tabella di esempio seguente. Se non è stato ancora distribuito Teams, ignorare questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quali tipi di utenti sono abilitati per Teams? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/> <input type="checkbox"> Utenti/gruppi di utenti specifici <br/>&nbsp;&nbsp; &nbsp; Specificare nella colonna Commenti. ||
> | Quali Teams caratteristiche e modalità sono in uso? | <input type="checkbox"> Conversazioni basate sul canale <br/> <input type="checkbox"> Chat privata <br/> <input type="checkbox"> Accesso guest <br/> <input type="checkbox"> Riunioni del canale <br/> <input type="checkbox"> Riunioni private <br/> <input type="checkbox"> Chiamate private <br/> <input type="checkbox"> Riunione di canale ad hoc <br/> <input type="checkbox"> Video nelle riunioni <br/> <input type="checkbox"> Condivisione dello schermo nelle riunioni <br/> <input type="checkbox"> Audioconferenza <br/><input type="checkbox"> Applicazioni (app)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Schede<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bot <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Connettori<br/><input type="checkbox"> Integrazione di archiviazione cloud personalizzata <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Drive, Egnyte <br/> <input type="checkbox"> Integrazione della posta elettronica del canale <br/> <input type="checkbox"> Altro (specificare nella colonna Commenti). | |
> | Quali applicazioni sono state distribuite in Teams? | | |
> | Sono state bloccate in modo specifico Teams funzionalità? <br/>Se sì, annotare i dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||
> | Quali Teams client sono in uso? | <input type="checkbox"> Web <br/> <input type="checkbox">Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox">Windows Dispositivo mobile | |
> | Who autorizzazioni per creare team? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/>&nbsp;&nbsp; &nbsp; (Questa è l'impostazione predefinita) <br/> <input type="checkbox"> Persone specifiche <br/>&nbsp;&nbsp; &nbsp; Specificare nella colonna Commenti. | |
> | Si usano le caratteristiche di sicurezza e conformità in Teams? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione Skype for Business Online usando la tabella di esempio seguente. Se la distribuzione online non è stata Skype for Business, ignorare questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quali tipi di utenti sono abilitati per Skype <br/>per Business Online? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/> <input type="checkbox"> Utenti/gruppi di utenti specifici <br/>&nbsp;&nbsp; &nbsp; Specificare nella colonna Commenti. | |
> | Modalità e caratteristiche attualmente disponibili <br/>in uso oggi? | <input type="checkbox"> Messaggistica istantanea e presenza (IM/P)<br/> <input type="checkbox"> Servizi di conferenza <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Registrazione riunione <br/> <input type="checkbox"> Audioconferenza Microsoft <br/> <input type="checkbox"> Audioconferenze di terze parti (Nota<br/>&nbsp;&nbsp; &nbsp; i dettagli nella colonna Commenti. <br/> <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) <br/> <input type="checkbox"> Operatori automatici dell'organizzazione <br/> <input type="checkbox"> Code di chiamata | |
> | Hai bloccato in modo specifico qualsiasi Skype per <br/>Funzionalità di Business Online? <br/>Se sì, annotare i dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Quale metodo si sta usando o si prevede di usare per <br/>connettersi Sistema telefonico (in precedenza Cloud PBX) a <br/>la rete PSTN? <br/>Selezionare tutte le opzioni applicabili. | <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) <br/> <input type="checkbox"> Connettività PSTN locale <br/>&nbsp;&nbsp; &nbsp; (sfruttando le Skype esistenti per <br/>&nbsp;&nbsp; &nbsp; Business 2015 o Lync Server <br/>&nbsp;&nbsp; &nbsp; Distribuzione 2013) <br/> <input type="checkbox"> Connettività PSTN locale <br/>&nbsp;&nbsp; &nbsp; (usando Cloud Connector) | |
> | Sono stati esportati numeri di telefono in Microsoft? <br/>Questa opzione è applicabile ai piani per chiamate e all'audio <br/>Funzionalità di conferenza. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business locale (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione Skype for Business usando la tabella di esempio seguente. Se non è stata distribuita una Skype for Business locale, ignorare questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quali versioni di Lync o Skype for Business <br/> attualmente sono distribuite in locale? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edizione | |
> | L'ambiente ibrido con Skype for Business Online è configurato? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Questo ambiente è ospitato e gestito da un terzo <br/>festa? In caso affermativa, prendere nota dei dettagli nella casella <br/>Colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Modalità e caratteristiche attualmente in uso <br/>oggi? | <input type="checkbox"> Messaggistica istantanea e presenza (IM/P) <br/> <input type="checkbox"> Servizi di conferenza <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Registrazione riunione <br/> <input type="checkbox"> Chat persistente /Chat di gruppo <br/> <input type="checkbox"> Audioconferenza Microsoft <br/>&nbsp;&nbsp; &nbsp; (in precedenza Conferenza telefonica con accesso esterno) sul tuo <br/>&nbsp;lync server locale &nbsp; &nbsp; o <br/>&nbsp;&nbsp; &nbsp; Skype for Business distribuzione <br/> <input type="checkbox"> Audioconferenze di terze parti <br/>&nbsp;&nbsp; &nbsp; Si notino i dettagli nella sezione Commenti <br/>&nbsp;&nbsp; &nbsp; colonna.) <br/> <input type="checkbox">VoIP aziendale l'uso locale <br/>&nbsp; &nbsp; &nbsp;Connettività PSTN <br/> <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) tramite <br/>&nbsp;&nbsp; &nbsp; Ibrida con Skype for Business Online | |
> | Quali versioni del server perimetrale sono state distribuite? | <input type="checkbox">Office Communications Server 2007 "R1" <br/> <input type="checkbox">Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Si dispone di Lync o Skype for Business Edge <br/>distribuito in più data center? <br/>Se sì, annotare i dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Selezionare i servizi forniti oggi dal ruolo Edge. | <input type="checkbox"> Accesso degli utenti esterni (utenti aziendali) <br/> <input type="checkbox"> Accesso utente remoto (anonimo <br/>&nbsp;&nbsp; &nbsp; partecipanti a riunioni esterne) <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Media relay | |
> | Quali delle seguenti funzionalità per le chiamate vocali <br/>attualmente hanno dipendenze? <br/>Prendere nota di eventuali dipendenze aggiuntive nei commenti <br/>colonna. | <input type="checkbox"> Opzioni occupato <br/> <input type="checkbox"> Parcheggio di chiamata <br/> <input type="checkbox"> Ritiro chiamata o ritiro chiamata di gruppo <br/> <input type="checkbox"> Telefoni dell'area comune o "hot desking" <br/> <input type="checkbox"> Response group o gruppi di risposta <br/> <input type="checkbox"> Aspetto della linea condivisa <br/> <input type="checkbox"> Linea privata <br/> <input type="checkbox"> Segreteria telefonica <br/> <input type="checkbox"> Chiama tramite lavoro <br/> <input type="checkbox"> Numeri di emergenza o informazioni <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Composizione dell'interno <br/> <input type="checkbox"> Operatore automatico <br/> <input type="checkbox"> Accesso sottoscrittore <br/> <input type="checkbox"> Dispositivi analogici <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Mascheramento o modifica dell'ID chiamante <br/> <input type="checkbox"> Routing basato sulla posizione <br/> <input type="checkbox"> Routing a costi più basso <br/> <input type="checkbox"> Telefoni con ascensori | |

<a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Rete e accesso a Microsoft 365 e Office 365 servizi
---

Usare la tabella seguente per acquisire i dettagli di rete dell'organizzazione e il modo in cui gli utenti sono (o saranno) connessi a Microsoft 365 e Office 365 servizi.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Come (o come) gli utenti nell'ambito della migrazione <br/>accedere Teams quando sono in ufficio? <br/>Selezionare tutte le opzioni applicabili. | <input type="checkbox"> Connessione NAT instradata <br/> <input type="checkbox"> Server proxy <br/> <input type="checkbox"> Informazioni Wi-Fi <br/> <input type="checkbox"> Gestione (non pubblica) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (peering Microsoft) ||
> | Se l'accesso Microsoft 365 o Office 365 tramite un<br/>server proxy, esiste un modo per ignorare il proxy? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | ExpressRoute viene usato oggi? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No <br/> <input type="checkbox"> No, ma è in fase di pianificazione | |
> | È stata eseguita una valutazione della conformità alla rete? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | È necessario che gli utenti usino una VPN per la connessione <br/>risorse aziendali in remoto? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Se si usa una VPN, Teams il traffico può essere escluso da <br/>la VPN per accedere direttamente Microsoft 365 e Office 365 servizi? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | La rete supporta QoS? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | È possibile assegnare priorità Teams traffico audio e video <br/>per guidare un'esperienza di alta qualità? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Tutte le località all'interno di un'area geografica sono in uscita da Internet, <br/>o l'uscita internet è centralizzata per l'intera area geografica? | <input type="checkbox"> Accesso locale a Internet <br/> <input type="checkbox"> Accesso centralizzato al <br/>&nbsp;&nbsp; &nbsp; internet | |

<a name="endpoints"></a>Endpoint
---

Usare la tabella seguente per acquisire i dettagli dei client e degli endpoint in uso.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quale sistema operativo desktop usano gli utenti? | <input type="checkbox">Windows XP <br/> <input type="checkbox">Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Specificare la versione nella colonna Commenti). <br/> <input type="checkbox"> Linux (Specificare la distribuzione nella colonna Commenti). <br/><input type="checkbox"> Altro (si notino i dettagli nella colonna Commenti). | |
> | Quale versione di Microsoft Office distribuita <br/>a questi dispositivi? | <input type="checkbox">Office 2003 <br/> <input type="checkbox">Office 2007 <br/> <input type="checkbox">Office 2010 <br/> <input type="checkbox">Office 2013 <br/> <input type="checkbox">Office 2016 <br/> <input type="checkbox">Office per Mac 2011 <br/> <input type="checkbox">Office per Mac 2016 <br/> <input type="checkbox"> Altro (si notino i dettagli nella colonna Commenti). | |
> | Quale Office di distribuzione è in uso <br/>all'interno dell'organizzazione? | <input type="checkbox"> MSI <br/> <input type="checkbox"> A click-to-Run | |
> | Quali sono i dispositivi mobili consentiti e supportati <br/>piattaforme in uso? <br/>Selezionare tutte le opzioni applicabili. | <input type="checkbox">Windows <br/> <input type="checkbox"> Dispositivo mobile <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Altro (si notino i dettagli nella colonna Commenti). | |
> | Come vengono forniti i dispositivi mobili? <br/>Selezionare tutte le opzioni applicabili. | <input type="checkbox"> Dispositivi aziendali <br/> <input type="checkbox"> Porta il tuo dispositivo | |
> | Quali dispositivi usano attualmente gli utenti per accedere <br/>servizi vocali e di conferenza <br/>(telefoni, cuffie, telefoni, video)? | | |

<a name="operations"></a>Operazioni
---

Usare la tabella seguente per acquisire i dettagli degli aspetti operativi dell'ambiente.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Qual è il modello operativo per Lync Server, <br/>Skype for Business Server, Microsoft 365 distribuzione, <br/>o Office 365 distribuzione oggi? | | |
> | È possibile delineare la disposizione del supporto corrente per <br/>Lync Server, Skype for Business Server, Microsoft 365, <br/>o Office 365? | | |
> | Se si esegue la distribuzione in più paesi o aree geografiche, <br/>ogni paese/area geografica ha un proprio IT/telefonia <br/>personale con cui lavorare o verrà gestito in modo centralizzato? | <input type="checkbox"> Operazioni e supporto regionale <br/> <input type="checkbox"> Operazioni e supporto centralizzati | |
> | Stai seguendo la metodologia call quality? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Hai assegnato un singolo o un team al <br/>Ruolo di campione qualitativo per la piattaforma di collaborazione <br/>in uso? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||
> | Come si esegue il monitoraggio di Lync Server, Skype per <br/>Business Server, Microsoft 365 distribuzione o <br/>Office 365 distribuzione? | | |
> | Si verificano problemi di qualità delle chiamate? | <input type="checkbox"> Sì<br/> <input type="checkbox"> No | |
> | Come e quando fornisci formazione al tuo <br/>helpdesk su nuovi servizi e funzionalità? | | |

<a name="adoption-and-readiness"></a>Adozione e conformità
---

Usare la tabella seguente e acquisire lo stato di adozione e conformità corrente dell'organizzazione.

>
> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Qual è l'uso attivo corrente di <br/>Skype for Business? | **__** % totale utenti attivi rispetto agli utenti abilitati | |
> | Come viene utilizzato l'organizzazione <br/>Skype for Business? | Conversazioni 1:1 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Messaggistica istantanea <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chiamate <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Condivisione<br/> Riunioni <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Servizi di conferenza<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Condivisione<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chiamate | |
> | L'organizzazione ha un'adozione degli utenti <br/>e team di gestione delle modifiche? | <input type="checkbox"> Sì<br/> <input type="checkbox"> No | |
> | Come si misura attualmente il successo per la tecnologia <br/>implementazioni come Skype for Business? | | |
> | Qual è la percentuale della base di utenti <br/>adottato Skype for Business? | | |
> | Che cos'è il clima di Skype for Business? | <input type="checkbox"> Buono <br/> <input type="checkbox"> Neutro <br/> <input type="checkbox"> Non è un valore | |
> | Quale delle opzioni seguenti descrive meglio l'implementazione <br/>strategia usata per la Skype for Business <br/>distribuzione? | <input type="checkbox"> Ampia portata: campagna di posta elettronica con <br/>&nbsp;&nbsp; &nbsp; collegamenti alla formazione <br/> <input type="checkbox"> Espanso: Ampia portata più una varietà <br/>&nbsp;&nbsp; &nbsp; campagne di sensibilizzazione (poster, <br/>&nbsp;&nbsp; &nbsp; eventi, campioni) e formazione <br/>&nbsp;&nbsp; &nbsp; (video, guide utente, di persona) <br/> <input type="checkbox"> Su misura: espanso, più mirato <br/>&nbsp;&nbsp; &nbsp; messaggistica e formazione per persona <br/> <input type="checkbox"> Altro <br/>&nbsp;&nbsp; &nbsp; Si notino i dettagli nella colonna Commenti. | |