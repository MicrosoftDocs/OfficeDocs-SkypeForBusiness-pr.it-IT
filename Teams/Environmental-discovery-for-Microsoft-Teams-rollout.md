---
title: Compatibilità con l'ambiente - Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Come eseguire una dettagliata individuazione ambientale mentre si pianifica il viaggio da Skype for Business a Microsoft Teams.
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
ms.openlocfilehash: 00173fe35d41241fb35a69f88785fa84b8bdf378
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790398"
---
<a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Individuazione ambientale per l'implementazione di Microsoft Teams
===================================================

L'individuazione è uno dei primi passi chiave da eseguire durante la pianificazione del viaggio in Microsoft Teams.

È possibile eseguire una dettagliata individuazione dell'ambiente per comprenderne meglio lo stato corrente e per rivelare eventuali difficoltà o, ulteriormente, bloccare l'esecuzione dell'implementazione di Teams.

## <a name="discovery-questionnaire"></a>Questionario di individuazione

Il questionario di esempio seguente illustra una serie di domande per verificare che l'organizzazione sia pronta per l'implementazione corretta delle audioconferenze e del sistema telefonico con funzionalità Piani per chiamate in Teams.

Tutti gli aspetti relativi all'infrastruttura di collaborazione esistente e all'organizzazione di Microsoft 365 o Office 365, alla rete, agli endpoint, alle operazioni, all'adozione e alla preparazione sono inclusi nel questionario per l'individuazione dell'ambiente.

Il questionario è suddiviso in più sezioni per verificare la conformità dell'organizzazione alla distribuzione di Teams in diverse aree principali. Collaborare con il team di progetto per fornire il maggior numero possibile di dettagli alle informazioni richieste per agevolare le attività di pianificazione.

> [!TIP]
> Per iniziare, copiare il questionario in un documento di Microsoft Word. Prova a rispondere a tutte le domande e acquisisci tutti i dettagli mentre ti sposti.

<a name="project-team"></a>Team di progetto
---

Acquisire informazioni dettagliate sulle principali parti interessate del progetto di implementazione di Teams. Si noti che una persona può avere diversi ruoli nell'intero progetto.

> | Ruolo | Nome, indirizzo di posta elettronica, numero di telefono | Posizione, fuso orario | Commenti |
> |---|---|---|---|
> | Executive Sponsor | | | |
> | Cliente potenziale del progetto | | | |
> | Lead/Architect per la collaborazione | | | |
> | Consulente | | | |
> | Project Manager | | | |
> | Esperto nella gestione delle modifiche e nell'adozione | | | |
> | Cliente potenziale rete | | | |
> | Cliente potenziale della sicurezza | | | |
> | Cliente potenziale telefonia | | | |
> | Cliente potenziale desktop | | | |
> | Cliente potenziale del supporto tecnico/help desk | | | |
> | Cliente potenziale distribuzione | | | |
> | Proprietario del servizio | | | |
> | Cliente potenziale struttura | | | |
> | Video Team Lead | | | |
> | Clienti potenziali business unit | | | |

<a name="microsoft-365-or-office-365-organization-details"></a>Dettagli dell'organizzazione di Microsoft 365 o Office 365
---

È consigliabile avere un'organizzazione di Microsoft 365 o Office 365 attiva mentre si lavora con questo questionario. Se non è ancora stata attivata o configurata un'organizzazione di Microsoft 365 o Office 365, vedere Pianificare la configurazione di [Microsoft 365 per le aziende.](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645)

Usare la tabella seguente per acquisire informazioni sull'organizzazione Microsoft 365 o Office 365.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Si noti la produzione di Microsoft 365<br/>o l'ID e il nome dell'organizzazione di Office 365<br/>nella colonna Rispondi. Se hai più<br/>più tenant associati<br/>l'organizzazione, prendere nota di tutti gli ID. | Nome tenant: <br/>ID tenant:| |
> | In quali aree geografiche vengono distribuiti i tenant?| | |
> | Prendere nota del tipo di questi prodotti Microsoft 365 o <br/>Tenant di Office 365. Sono multitenant <br/>o Dedicated? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> Dedicato | |
> | Quali prodotti Microsoft Online sono attualmente in uso? <br/>Annota il numero di utenti abilitati per ogni <br/>nella colonna Commenti. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox"> Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox"> Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox"> OneDrive for Business <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Altro| |
> | Quale livello di licenza è abilitato per Skype per <br/>Utenti di Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Il numero di utenti <br/>per ogni SKU: |
> | Qual è la foresta di Active Directory corrente <br/>livello funzionale nell'ambiente? <br/>Se sono presenti più foreste, prendere nota dei dettagli <br/>nella colonna Commenti. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox"> Windows Server 2012 <br/> <input type="checkbox"> Windows Server 2012 R2 <br/> <input type="checkbox"> Windows Server 2016| |
> | Cosa si usa per la directory <br/>sincronizzazione oggi stesso? |<input type="checkbox"> Nessuna sincronizzazione (solo cloud) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Connetti <br/> <input type="checkbox"> Altro (specifica nella casella <br/>&nbsp;&nbsp; &nbsp; Colonna Commenti).| |
> | Le identità federate sono attualmente distribuite? <br/>(Active Directory Federation Services o <br/>di terze parti) | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Se si usano le identità federate, che cos'è <br/>infrastruttura federativa? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Adfs di Windows 2012 <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Adfs di Windows 2016 <br/> <input type="checkbox"> Federazione di terze parti <br/>&nbsp;&nbsp; &nbsp; gateway (prendere nota dei dettagli <br/>&nbsp;&nbsp; &nbsp; nella colonna Commenti. | |
> | Se attualmente si mantiene un account Microsoft 365 attivo<br/>o tenant di Office 365, è il dominio SMTP/SIP di <br/>gli utenti mirati associati al tenant? | <input type="checkbox"> N/D- Nessun Microsoft 365 o<br/>&nbsp;&nbsp; &nbsp; Tenant di Office 365 sul posto <br/> <input type="checkbox"> No, SMTP/SIP degli utenti <br/>&nbsp;&nbsp; &nbsp; dominio non è associato <br/>&nbsp;&nbsp; &nbsp; con tutti i tenant in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365<br/> <input type="checkbox"> Sì, SMTP/SIP degli utenti <br/>&nbsp;&nbsp; &nbsp; dominio è associato <br/>&nbsp;&nbsp; &nbsp; con un tenant esistente in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365 | |
> | Gli UPN degli utenti corrispondono al loro indirizzo SMTP principale? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No <br/> <input type="checkbox"> Incoerente | |

<a name="existing-collaboration-platform-summary"></a>Riepilogo piattaforma di collaborazione esistente
---

Usare la tabella seguente per acquisire informazioni sulla distribuzione della piattaforma di collaborazione esistente.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Microsoft Teams è distribuito? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Skype for Business è distribuito? <br/>Per le distribuzioni locali e ibride, assicurati che <br/>si annota la versione e l'aggiornamento cumulativo <br/>nella colonna Commenti. | <input type="checkbox"> Sì, Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365 <br/> <input type="checkbox"> Sì, ibrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sì, locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sì, ospitato, dedicato <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> Sì, ospitato, condiviso <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> No, altro | |
> | Exchange è distribuito? <br/>Per le distribuzioni locali e ibride, assicurati che <br/>si annota la versione e i dettagli dell'cu nei commenti <br/>. | <input type="checkbox"> Sì, Microsoft 365 <br/> <input type="checkbox"> Sì, ibrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sì, locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sì, ospitato, dedicato <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> Sì, ospitato, condiviso <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> No, altro | |
> | SharePoint è distribuito? <br/>Per le distribuzioni locali e ibride, assicurati che <br/>si annota la versione e i dettagli dell'cu nei commenti <br/>. | <input type="checkbox"> Sì, Microsoft 365 <br/> <input type="checkbox"> Sì, ibrido (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp; Office 365) <br/> <input type="checkbox"> Sì, locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp; (Microsoft) <br/> <input type="checkbox"> Sì, ospitato, dedicato <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> Sì, ospitato, condiviso <br/>&nbsp;&nbsp; &nbsp; (terze parti) <br/> <input type="checkbox"> No, altro | |
> | OneDrive for Business è distribuito? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Sono state distribuite altre piattaforme di terze parti? <br/>e in uso oggi? In tal caso, annota il numero di utenti di <br/>queste piattaforme e i dettagli di utilizzo nella <br/>Colonna Commenti. | <input type="checkbox"> Cisco WebEx <br/> <input type="checkbox"> Margine di flessibilità <br/> <input type="checkbox"> Altro (specifica nella casella <br/>&nbsp;&nbsp; &nbsp; Colonna Commenti). | Numero di utenti: <br/>Dettagli:|
> | Stai pianificando di spostare gli utenti da queste terze parti <br/>piattaforme a Teams? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Qual è la soluzione di telefonia e conferenza attuale? <br/>degli utenti nell'ambito di questa iniziativa? | | |
> | Si dispone di [SBC che supportano il routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) distribuito <br/>per i tuoi uffici che hanno ambito per questa iniziativa? In caso affermativa,<br/>prendere nota dei dettagli nella colonna Commenti.| <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||

<a name="collaboration-platform-deployment-details"></a>Dettagli sulla distribuzione della piattaforma di collaborazione
---

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione di Teams usando la tabella di esempio seguente. Se Teams non è stato ancora distribuito, ignorare questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quali tipi di utenti sono abilitati per Teams? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/> <input type="checkbox"> Utenti/gruppi di utenti specifici <br/>&nbsp;&nbsp; &nbsp; Specificare nella colonna Commenti. ||
> | Quali caratteristiche e modalità di Teams sono in uso? | <input type="checkbox"> Conversazioni basate su canale <br/> <input type="checkbox"> Chat privata <br/> <input type="checkbox"> Accesso guest <br/> <input type="checkbox"> Riunioni del canale <br/> <input type="checkbox"> Riunioni private <br/> <input type="checkbox"> Chiamate private <br/> <input type="checkbox"> Meetup canale ad-hoc <br/> <input type="checkbox"> Video nelle riunioni <br/> <input type="checkbox"> Condivisione dello schermo nelle riunioni <br/> <input type="checkbox"> Audioconferenza <br/><input type="checkbox"> Applicazioni (app)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Schede<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bot <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Connettori<br/><input type="checkbox"> Integrazione di archiviazione cloud personalizzata <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Unità, Egnyte <br/> <input type="checkbox"> Integrazione della posta elettronica del canale <br/> <input type="checkbox"> Altro (specificare nella colonna Commenti). | |
> | Quali applicazioni sono state distribuite in Teams? | | |
> | Hai bloccato specificamente le funzionalità di Teams? <br/>In caso affermativa, prendere nota dei dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||
> | Quali client di Teams sono in uso? | <input type="checkbox"> Web <br/> <input type="checkbox"> Windows <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Chi ha le autorizzazioni per creare team? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/>&nbsp;&nbsp; &nbsp; Questa è l'impostazione predefinita. <br/> <input type="checkbox"> Utenti specifici <br/>&nbsp;&nbsp; &nbsp; Specificare nella colonna Commenti. | |
> | Stai usando le funzionalità di sicurezza e conformità in Teams? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business online (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione di Skype for Business online utilizzando la tabella di esempio seguente. Se non hai ancora distribuito la distribuzione di Skype for Business online, ignora questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quali tipi di utenti sono abilitati per Skype? <br/>per Business Online? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/> <input type="checkbox"> Utenti/gruppi di utenti specifici <br/>&nbsp;&nbsp; &nbsp; Specificare nella colonna Commenti. | |
> | Quali sono le modali e le funzionalità attualmente disponibili <br/>in uso oggi? | <input type="checkbox"> Messaggistica istantanea e presenza (IM/P)<br/> <input type="checkbox"> Conferenze <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Registrazione riunione <br/> <input type="checkbox"> Audioconferenza Microsoft <br/> <input type="checkbox"> Servizi di audioconferenza di terze parti (nota)<br/>&nbsp;&nbsp; &nbsp; i dettagli nella colonna Commenti). <br/> <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) <br/> <input type="checkbox"> Operatori automatici organizzazione <br/> <input type="checkbox"> Code di chiamata | |
> | Hai bloccato specificamente qualsiasi Skype per <br/>Funzionalità di Business Online? <br/>In caso affermativa, prendere nota dei dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Quale metodo si usa o si prevede di usare per <br/>connetti sistema telefonico (in precedenza Cloud PBX) a <br/>pstN? <br/>Selezionare tutte le opzioni applicabili. | <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) <br/> <input type="checkbox"> Connettività PSTN locale <br/>&nbsp;&nbsp; &nbsp; (sfruttando skype esistente per <br/>&nbsp;&nbsp; &nbsp; Business 2015 o Lync Server <br/>&nbsp;&nbsp; &nbsp; Distribuzione 2013) <br/> <input type="checkbox"> Connettività PSTN locale <br/>&nbsp;&nbsp; &nbsp; (con Cloud Connector) | |
> | Hai portato numeri di telefono a Microsoft? <br/>Questa impostazione è applicabile ai Piani per chiamate e audio <br/>Funzionalità di conferenza. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business locale (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione di Skype for Business utilizzando la tabella di esempio seguente. Se non hai ancora distribuito Skype for Business in locale, ignora questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quali versioni di Lync o Skype for Business <br/> attualmente sono distribuite in locale? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype for Business Server 2015 <br/> <input type="checkbox"> Skype for Business Server 2019 <br/><input type="checkbox"> Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edizione | |
> | La distribuzione ibrida con Skype for Business online è configurata? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Questo ambiente è ospitato e gestito da un terzo <br/>festa? In caso affermativa, annota i dettagli nella casella <br/>Colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Quali modali e funzionalità sono attualmente in uso? <br/>oggi? | <input type="checkbox"> Messaggistica istantanea e presenza (IM/P) <br/> <input type="checkbox"> Conferenze <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Registrazione riunione <br/> <input type="checkbox"> Chat persistente/Group Chat <br/> <input type="checkbox"> Audioconferenza Microsoft <br/>&nbsp;&nbsp; &nbsp; (in precedenza Conferenza telefonica con accesso esterno) sul <br/>&nbsp;&nbsp; &nbsp; lync server locale o <br/>&nbsp;&nbsp; &nbsp; Distribuzione di Skype for Business <br/> <input type="checkbox"> Audioconferenza di terze parti <br/>&nbsp;&nbsp; &nbsp; Si notino i dettagli nel riquadro Commenti <br/>&nbsp;&nbsp; &nbsp; ). <br/> <input type="checkbox"> VoIP aziendale usa la distribuzione locale <br/>&nbsp; &nbsp; &nbsp;Connettività PSTN <br/> <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) tramite <br/>&nbsp;&nbsp; &nbsp; Ibrida con Skype for Business online | |
> | Quali versioni di Edge Server sono state distribuite? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox"> Skype for Business Server 2015 <br/> <input type="checkbox"> Skype for Business Server 2019| |
> | Si dispone di Lync o Skype for Business Edge <br/>distribuito in più data center? <br/>In caso affermativa, prendere nota dei dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Seleziona i servizi forniti oggi dal tuo ruolo Edge. | <input type="checkbox"> Accesso a utenti esterni (utenti aziendali) <br/> <input type="checkbox"> Accesso remoto degli utenti (anonimo) <br/>&nbsp;&nbsp; &nbsp; partecipanti a riunioni esterne) <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Media Relay | |
> | Quali delle seguenti funzionalità per le chiamate vocali sei tu <br/>attualmente hanno dipendenze? <br/>Annotare eventuali dipendenze aggiuntive nei commenti <br/>. | <input type="checkbox"> Opzioni occupato <br/> <input type="checkbox"> Parco delle chiamate <br/> <input type="checkbox"> Ritiro chiamata o ritiro chiamata di gruppo <br/> <input type="checkbox"> Telefoni dell'area comune, o "hot desking" <br/> <input type="checkbox"> Response Group o gruppi di risposta <br/> <input type="checkbox"> Aspetto delle linee condivise <br/> <input type="checkbox"> Riga privata <br/> <input type="checkbox"> Segreteria telefonica <br/> <input type="checkbox"> Chiama tramite lavoro <br/> <input type="checkbox"> Numeri di emergenza o informazioni <br/>&nbsp;&nbsp; &nbsp; (911, 811, 411) <br/> <input type="checkbox"> Composizione dell'interno <br/> <input type="checkbox"> Operatore automatico <br/> <input type="checkbox"> Accesso sottoscrittore <br/> <input type="checkbox"> Dispositivi analogici <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Maschera o modifica dell'ID chiamante <br/> <input type="checkbox"> Routing basato sulla posizione <br/> <input type="checkbox"> Routing con costi minimo <br/> <input type="checkbox"> Telefoni per cellulari | |

<a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Rete e accesso ai servizi di Microsoft 365 e Office 365
---

Usare la tabella seguente per acquisire i dettagli di rete dell'organizzazione e il modo in cui gli utenti sono (o saranno) connessi ai servizi di Microsoft 365 e Office 365.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Come (o come) gli utenti nell'ambito della migrazione <br/>accedere a Teams quando sono in ufficio? <br/>Selezionare tutte le opzioni applicabili. | <input type="checkbox"> Connessione NAT instradata <br/> <input type="checkbox"> Server proxy <br/> <input type="checkbox"> Servizi Wi-Fi <br/> <input type="checkbox"> Tipi di dati gestiti (non Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp; (peering Microsoft) ||
> | Se l'accesso a Microsoft 365 o Office 365 è tramite un<br/>server proxy, esiste un modo per ignorare il proxy? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | ExpressRoute è attualmente in uso? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No <br/> <input type="checkbox"> No, ma è in fase di pianificazione | |
> | Hai eseguito una valutazione di conformità della rete? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Gli utenti sono tenuti a usare una VPN quando si connettono a <br/>risorse aziendali in remoto? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Se si usa una VPN, il traffico di Teams può essere escluso da <br/>la VPN per accedere direttamente a Microsoft 365 e Ai servizi di Office 365? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | La tua rete supporta la QoS? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | È possibile assegnare priorità al traffico audio e video di Teams <br/>per guidare un'esperienza di alta qualità? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Tutte le posizioni all'interno di un'area geografica hanno un punto di uscita Internet, <br/>oppure il uscita Internet è centralizzato per l'intera area geografica? | <input type="checkbox"> Accesso locale a Internet <br/> <input type="checkbox"> Accesso centralizzato alla <br/>&nbsp;&nbsp; &nbsp; internet | |

<a name="endpoints"></a>Endpoint
---

Usare la tabella seguente per acquisire i dettagli dei client e degli endpoint in uso.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quale sistema operativo desktop usano gli utenti? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox"> Windows 8 <br/> <input type="checkbox"> Windows 10 <br/> <input type="checkbox"> Mac (Specifica la versione nella colonna Commenti). <br/> <input type="checkbox"> Linux (Specifica la distribuzione nella colonna Commenti).) <br/><input type="checkbox"> Altro (notare i dettagli nella colonna Commenti). | |
> | Quale versione di Microsoft Office distribuita <br/>a questi dispositivi? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox"> Office per Mac 2011 <br/> <input type="checkbox"> Office per Mac 2016 <br/> <input type="checkbox"> Altro (notare i dettagli nella colonna Commenti). | |
> | Tecnologia di distribuzione di Office in uso <br/>nell'organizzazione? | <input type="checkbox"> MSI <br/> <input type="checkbox"> A run-to-run | |
> | Quali sono i dispositivi mobili consentiti e supportati? <br/>piattaforme in uso? <br/>Selezionare tutte le opzioni applicabili. | <input type="checkbox"> Windows <br/> <input type="checkbox"> Dispositivi mobili <br/> <input type="checkbox"> iOS <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Altro (notare i dettagli nella colonna Commenti). | |
> | Come vengono forniti i dispositivi mobili? <br/>Selezionare tutte le opzioni applicabili. | <input type="checkbox"> Dispositivi aziendali <br/> <input type="checkbox"> Porta il tuo dispositivo | |
> | Quali dispositivi attualmente usano gli utenti per accedere <br/>servizi vocali e di conferenza <br/>(ricevitori, cuffie, telefoni, video)? | | |

<a name="operations"></a>Operazioni
---

Usare la tabella seguente per acquisire i dettagli degli aspetti operativi dell'ambiente.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Qual è il modello di operazioni per Lync Server, <br/>Skype for Business Server, distribuzione di Microsoft 365, <br/>o la distribuzione di Office 365 oggi? | | |
> | È possibile delineare la disposizione del supporto corrente per <br/>Lync Server, Skype for Business Server, Microsoft 365, <br/>o Office 365? | | |
> | Se stai distribuendo in più paesi o aree geografiche, <br/>fa in modo che ogni paese/area geografica abbia un proprio IT/telefonia <br/>personale a collaborare o verranno gestiti centralmente? | <input type="checkbox"> Operazioni e supporto regionale <br/> <input type="checkbox"> Operazioni centralizzate e supporto | |
> | Stai seguendo la metodologia per la qualità delle chiamate? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Hai assegnato un singolo o un team al <br/>Ruolo di campione della qualità per la piattaforma di collaborazione <br/>in uso? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||
> | Come monitorare Lync Server, Skype per <br/>Business Server, distribuzione di Microsoft 365 o <br/>Distribuzione di Office 365 | | |
> | Si verificano problemi di qualità delle chiamate? | <input type="checkbox"> Sì<br/> <input type="checkbox"> No | |
> | Come e quando fornire formazione ai <br/>supporto tecnico su nuovi servizi e funzionalità? | | |

<a name="adoption-and-readiness"></a>Adozione e preparazione
---

Usare la tabella seguente per acquisire lo stato di adozione e conformità corrente dell'organizzazione.

>
> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Qual è l'utilizzo attivo corrente di <br/>Skype for Business? | **__** % totale utenti attivi rispetto a utenti abilitati | |
> | Come viene utilizzato l'organizzazione? <br/>Skype for Business? | Conversazioni 1:1 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Messaggistica istantanea <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chiamate <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Condivisione<br/> Riunioni <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferenze<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Condivisione<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chiamate | |
> | L'organizzazione ha un'adozione da parte degli utenti <br/>e il team di gestione delle modifiche? | <input type="checkbox"> Sì<br/> <input type="checkbox"> No | |
> | Come misurare il successo per la tecnologia <br/>implementazioni come Skype for Business? | | |
> | Quale percentuale della base di utenti potresti dire che ha <br/>ha adottato Skype for Business? | | |
> | Qual è il valutazione degli utenti su Skype for Business? | <input type="checkbox"> Buono <br/> <input type="checkbox"> Neutrale <br/> <input type="checkbox"> Non è possibile | |
> | Quale delle seguenti descrive meglio l'implementazione <br/>strategia utilizzata per Skype for Business <br/>distribuzione? | <input type="checkbox"> Ampia portata: campagna di posta elettronica con <br/>&nbsp;&nbsp; &nbsp; collegamenti alla formazione <br/> <input type="checkbox"> Esteso: Ampio punto di raggiungere oltre a una varietà <br/>&nbsp;&nbsp; &nbsp; campagne di consapevolezza (poster, <br/>&nbsp;&nbsp; &nbsp; eventi, campioni) e formazione <br/>&nbsp;&nbsp; &nbsp; (video, guide per l'utente, di persona) <br/> <input type="checkbox"> Su misura: Espansa, più mirata <br/>&nbsp;&nbsp; &nbsp; Messaggistica e formazione per utente tipo <br/> <input type="checkbox"> Altro <br/>&nbsp;&nbsp; &nbsp; Si notino i dettagli nella colonna Commenti. | |
