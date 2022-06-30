---
title: Compatibilità ambientale - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: Come eseguire una scoperta ambientale dettagliata durante la pianificazione del viaggio da Skype for Business a Microsoft Teams.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 348a0e615f5ef876bfdd62b71adb30f6bf242dd6
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562605"
---
# <a name="environmental-discovery-for-a-microsoft-teams-rollout"></a>Individuazione ambientale per un'implementazione di Microsoft Teams

La scoperta è uno dei primi passi chiave da intraprendere durante la pianificazione del viaggio verso Microsoft Teams.

Si esegue un'individuazione dettagliata dell'ambiente per comprenderne meglio lo stato corrente e per rivelare eventuali difficoltà o, ancora, possibili bloccanti per l'esecuzione dell'implementazione di Teams.

## <a name="discovery-questionnaire"></a>Questionario di individuazione

Il questionario di esempio riportato di seguito illustra una serie di domande per confermare che l'organizzazione è pronta per l'implementazione di audioconferenze e sistema telefonico con funzionalità Piani per chiamate in Teams.

Tutte le questioni relative all'infrastruttura di collaborazione esistente e a Microsoft 365 o Office 365 organizzazione, rete, endpoint, operazioni, adozione e conformità sono incluse nel questionario di individuazione ambientale.

Il questionario è diviso in più sezioni per confermare la conformità dell'organizzazione alla distribuzione di Teams in diverse aree principali. Collaborare con il team di progetto per fornire le informazioni richieste con il maggior livello di dettaglio possibile per facilitare le attività di pianificazione.

> [!TIP]
> Per iniziare, copiare il questionario in un documento di Microsoft Word. Prova a rispondere a tutte le domande e acquisisci tutti i dettagli mentre ti sposti.

### <a name="project-team"></a>Team di progetto

Acquisire informazioni dettagliate sui principali stakeholder del progetto di implementazione di Teams. Si noti che una persona può svolgere diversi ruoli nell'intero progetto.

> | Ruolo | Nome, indirizzo e-mail, numero di telefono | Luogo, fuso orario | Commenti |
> |---|---|---|---|
> | Sponsor esecutivo | | | |
> | Project Lead | | | |
> | Responsabile/Architetto della collaborazione | | | |
> | Consulente | | | |
> | Project Manager | | | |
> | Change Management/Adoption Specialist | | | |
> | Cliente potenziale di rete | | | |
> | Cliente potenziale per la sicurezza | | | |
> | Lead telefonia | | | |
> | Cliente potenziale del desktop | | | |
> | Supporto/Help Desk Lead | | | |
> | Cliente potenziale della distribuzione | | | |
> | Proprietario del servizio | | | |
> | Facilities Lead | | | |
> | Video Responsabile del team | | | |
> | Clienti potenziali di Business Unit | | | |

## <a name="microsoft-365-or-office-365-organization-details"></a>Dettagli dell'organizzazione di Microsoft 365 o Office 365

È consigliabile avere un'organizzazione di Microsoft 365 o Office 365 attiva mentre si lavora con questo questionario. Se non è ancora stata attivata o configurata un'organizzazione di Microsoft 365 o Office 365, vedere [Pianificare la configurazione di Microsoft 365 per le aziende](https://support.office.com/article/plan-your-setup-of-office-365-for-business-eb926624-018b-4486-bf11-5fba6ee4d645).

Usare la tabella seguente per acquisire informazioni su Microsoft 365 o Office 365 organizzazione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Prendere nota della versione di produzione di Microsoft 365<br/>o Office 365 nome e ID dell'organizzazione<br/>nella colonna Risposta. Se hai più<br/>di un tenant associato a<br/>la tua organizzazione, prendi nota di tutti gli ID. | Nome tenant: <br/>ID tenant:| |
> | In quali aree geografiche vengono distribuiti i tenant?| | |
> | Prendi nota del tipo di microsoft 365 o <br/>Office 365 tenant. Sono Multitenant <br/>o Dedicated? | <input type="checkbox"> Multitenant<br/> <input type="checkbox"> Dedicato | |
> | Quali prodotti Microsoft Online sono attualmente in uso? <br/>Si noti il numero di utenti abilitati per ogni <br/>nella colonna Commenti. | <input type="checkbox"> Microsoft Teams <br/> <input type="checkbox">Skype for Business <br/>&nbsp; &nbsp; &nbsp;Online <br/> <input type="checkbox">Exchange Online <br/> <input type="checkbox"> SharePoint Online <br/> <input type="checkbox">OneDrive for Business <br/> <input type="checkbox"> Yammer <br/> <input type="checkbox"> Altro| |
> | Quale livello di licenza è abilitato per Skype per <br/>Utenti di Business Online? | <input type="checkbox"> E1/G1 <br/> <input type="checkbox"> E2/G2 <br/> <input type="checkbox"> E3/G3 <br/> <input type="checkbox"> E4/G4 E5 | Il numero di utenti <br/>per ogni SKU: |
> | Cos'è l'attuale foresta di Active Directory <br/>livello funzionale nell'ambiente? <br/>Se c'è più di una foresta, prendi nota dei dettagli <br/>nella colonna Commenti. | <input type="checkbox"> Windows Server 2000 <br/> <input type="checkbox"> Windows Server 2003 <br/> <input type="checkbox"> Windows Server 2008<br/> <input type="checkbox"> Windows Server 2008 R2 <br/> <input type="checkbox">Windows Server 2012 <br/> <input type="checkbox">Windows Server 2012 R2 <br/> <input type="checkbox">Windows Server 2016| |
> | Cosa stai usando per la directory <br/>sincronizzazione oggi? |<input type="checkbox"> Nessuna sincronizzazione (solo cloud) <br/> <input type="checkbox"> Azure Active Directory <br/>&nbsp;&nbsp; &nbsp; Connettersi <br/> <input type="checkbox"> Altro (specifica nella casella di <br/>&nbsp;&nbsp; &nbsp; Colonna Commenti.| |
> | L'identità federativa è attualmente distribuita? <br/>(Active Directory Federation Services o <br/>terze parti) | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Se si usa l'identità federativa, che cos'è <br/>dell'infrastruttura federativa? | <input type="checkbox"> Windows 2008 R2 AD FS <br/> <input type="checkbox"> Windows 2012 AD FS <br/> <input type="checkbox"> Windows 2012 R2 AD FS <br/> <input type="checkbox"> Windows 2016 AD FS <br/> <input type="checkbox"> Federazione di terze parti <br/>&nbsp;&nbsp; &nbsp;gateway (Nota i dettagli <br/>&nbsp;&nbsp; &nbsp;nella colonna Commenti. | |
> | Se attualmente si mantiene un account Microsoft 365 attivo<br/>o Office 365 tenant, è il dominio SMTP/SIP di <br/>gli utenti assegnati associati al tenant? | <input type="checkbox"> N/D- Nessun microsoft 365 o<br/>&nbsp;&nbsp; &nbsp;Office 365 tenant <br/> <input type="checkbox"> No, SMTP/SIP degli utenti <br/>&nbsp;&nbsp; &nbsp;dominio non è associato <br/>&nbsp;&nbsp; &nbsp;con qualsiasi tenant in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365<br/> <input type="checkbox"> Sì, SMTP/SIP degli utenti <br/>&nbsp;&nbsp; &nbsp;dominio è associato <br/>&nbsp;&nbsp; &nbsp;con un tenant esistente in <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o Office 365 | |
> | Gli UPN utente corrispondono all'indirizzo SMTP principale? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No <br/> <input type="checkbox"> Incoerente | |

## <a name="existing-collaboration-platform-summary"></a>Riepilogo della piattaforma di collaborazione esistente

Usare la tabella seguente per acquisire informazioni sulla distribuzione della piattaforma di collaborazione esistente.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Microsoft Teams viene distribuito? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Viene distribuita Skype for Business? <br/>Per le distribuzioni locali e ibride, assicurarsi che <br/>prendi nota della versione e dell'aggiornamento cumulativo <br/>nella colonna Commenti. | <input type="checkbox"> Sì, Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp;Office 365 <br/> <input type="checkbox"> Sì, ibrida (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sì, in locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sì, ospitata, dedicata <br/>&nbsp;&nbsp; &nbsp;(terze parti) <br/> <input type="checkbox"> Sì, ospitata, condivisa <br/>&nbsp;&nbsp; &nbsp;(terze parti) <br/> <input type="checkbox"> No, altro | |
> | Exchange viene distribuito? <br/>Per le distribuzioni locali e ibride, assicurarsi che <br/>si annotano i dettagli della versione e dell'cu nei commenti <br/>Colonna. | <input type="checkbox"> Sì, Microsoft 365 <br/> <input type="checkbox"> Sì, ibrida (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sì, in locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sì, ospitata, dedicata <br/>&nbsp;&nbsp; &nbsp;(terze parti) <br/> <input type="checkbox"> Sì, ospitata, condivisa <br/>&nbsp;&nbsp; &nbsp;(terze parti) <br/> <input type="checkbox"> No, altro | |
> | SharePoint viene distribuito? <br/>Per le distribuzioni locali e ibride, assicurarsi che <br/>si annotano i dettagli della versione e dell'cu nei commenti <br/>Colonna. | <input type="checkbox"> Sì, Microsoft 365 <br/> <input type="checkbox"> Sì, ibrida (con <br/>&nbsp;&nbsp; &nbsp; Microsoft 365 o <br/>&nbsp;&nbsp; &nbsp;Office 365) <br/> <input type="checkbox"> Sì, in locale <br/> <input type="checkbox"> Sì, online, dedicato <br/>&nbsp;&nbsp; &nbsp;(Microsoft) <br/> <input type="checkbox"> Sì, ospitata, dedicata <br/>&nbsp;&nbsp; &nbsp;(terze parti) <br/> <input type="checkbox"> Sì, ospitata, condivisa <br/>&nbsp;&nbsp; &nbsp;(terze parti) <br/> <input type="checkbox"> No, altro | |
> | Viene distribuita OneDrive for Business? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Hai altre piattaforme di terze parti distribuite? <br/>e in uso oggi? In tal caso, prendi nota del numero di utenti di <br/>queste piattaforme e i dettagli sull'utilizzo nel <br/>Colonna Commenti. | <input type="checkbox"> Cisco Webex <br/> <input type="checkbox"> Slack <br/> <input type="checkbox"> Altro (specifica nella casella di <br/>&nbsp;&nbsp; &nbsp; Colonna Commenti. | Numero di utenti: <br/>Dettagli:|
> | Si prevede di spostare gli utenti da queste terze parti? <br/>piattaforme a Teams? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Qual è l'attuale soluzione di telefonia e conferenza <br/>degli utenti che rientrano nell'ambito di questa iniziativa? | | |
> | Hai [SBC che supportano Direct Routing](./direct-routing-plan.md#supported-session-border-controllers-sbcs) distribuito <br/>per i vostri uffici che rientrano nell'ambito di questa iniziativa? In caso affermativo,<br/>prendere nota dei dettagli nella colonna Commenti.| <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||

## <a name="collaboration-platform-deployment-details"></a>Dettagli sulla distribuzione della piattaforma di collaborazione

### <a name="microsoft-teams-if-applicable"></a>Microsoft Teams (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione di Teams usando la tabella di esempio seguente. Se Teams non è ancora stato distribuito, ignorare questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quali tipi di utenti sono abilitati per Teams? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/> <input type="checkbox"> Utenti/gruppi di utenti specifici <br/>&nbsp;&nbsp; &nbsp;Specificare nella colonna Commenti. ||
> | Quali caratteristiche e modalità di Teams sono in uso? | <input type="checkbox"> Conversazioni basate sul canale <br/> <input type="checkbox"> Chat privata <br/> <input type="checkbox"> Accesso guest <br/> <input type="checkbox"> Riunioni di canale <br/> <input type="checkbox"> Riunioni private <br/> <input type="checkbox"> Chiamate private <br/> <input type="checkbox"> Riunione canale ad-hoc <br/> <input type="checkbox"> Video nelle riunioni <br/> <input type="checkbox"> Condivisione dello schermo nelle riunioni <br/> <input type="checkbox"> Audioconferenza <br/><input type="checkbox"> Applicazioni (app)<br/> &nbsp;&nbsp; &nbsp;<input type="checkbox"> Schede<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Bot <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Connettori<br/><input type="checkbox"> Integrazione di archiviazione cloud personalizzata <br/>&nbsp;&nbsp; &nbsp; Dropbox, Box, ShareFile, Google <br/>&nbsp;&nbsp; &nbsp; Drive, Egnyte <br/> <input type="checkbox"> Integrazione della posta elettronica del canale <br/> <input type="checkbox"> Altro (Specificare nella colonna Commenti). | |
> | Quali applicazioni sono state distribuite in Teams? | | |
> | Hai bloccato in modo specifico le funzionalità di Teams? <br/>Se sì, prendere nota dei dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||
> | Quali client di Teams sono in uso? | <input type="checkbox"> Web <br/> <input type="checkbox"> Finestre <br/> <input type="checkbox"> Mac <br/> <input type="checkbox"> Linux <br/>  <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Windows Mobile | |
> | Chi ha le autorizzazioni per creare team? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/>&nbsp;&nbsp; &nbsp;(Questa è l'impostazione predefinita) <br/> <input type="checkbox"> Persone specifiche <br/>&nbsp;&nbsp; &nbsp;Specificare nella colonna Commenti. | |
> | Stai usando le funzionalità di sicurezza e conformità in Teams? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-online-if-applicable"></a>Skype for Business Online (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione online di Skype for Business usando la tabella di esempio seguente. Se non è stata ancora distribuita Skype for Business distribuzione online, ignorare questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Tipi di utenti abilitati per Skype <br/>for Business Online? | <input type="checkbox"> Tutti gli utenti dell'organizzazione <br/> <input type="checkbox"> Utenti/gruppi di utenti specifici <br/>&nbsp;&nbsp; &nbsp;Specificare nella colonna Commenti. | |
> | Quali modalità e funzionalità sono attualmente disponibili <br/>in uso oggi? | <input type="checkbox"> Messaggistica istantanea e presenza (IM/P)<br/> <input type="checkbox"> Conferenza <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Registrazione riunione <br/> <input type="checkbox"> Audioconferenza Microsoft <br/> <input type="checkbox"> Audioconferenza di terze parti (nota<br/>&nbsp;&nbsp; &nbsp;i dettagli nella colonna Commenti). <br/> <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) <br/> <input type="checkbox"> Operatori automatici dell'organizzazione <br/> <input type="checkbox"> Code di chiamata | |
> | Hai bloccato specificamente qualsiasi skype per <br/>Funzionalità di Business Online? <br/>Se sì, prendere nota dei dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Quale metodo si sta utilizzando o si prevede di utilizzare per <br/>connect Phone System (in precedenza Cloud PBX) a <br/>pstn? <br/>Selezionare tutte le risposte pertinenti. | <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) <br/> <input type="checkbox"> Connettività PSTN locale <br/>&nbsp;&nbsp; &nbsp;(sfruttando l'attuale Skype per <br/>&nbsp;&nbsp; &nbsp; Business 2015 o Lync Server <br/>&nbsp;&nbsp; &nbsp;distribuzione 2013) <br/> <input type="checkbox"> Connettività PSTN locale <br/>&nbsp;&nbsp; &nbsp;(tramite Cloud Connector) | |
> | Hai convertito numeri di telefono in Microsoft? <br/>Si applica ai Piani per chiamate e all'audio <br/>Funzionalità di conferenza. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |

### <a name="skype-for-business-on-premises-if-applicable"></a>Skype for Business locale (se applicabile)

Se applicabile, acquisire i dettagli della distribuzione Skype for Business usando la tabella di esempio seguente. Se non è stato ancora distribuito Skype for Business locale, ignorare questa sezione.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quali versioni di Lync o di Skype for Business <br/> sono attualmente distribuiti in locale? | <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019 <br/><input type="checkbox">Skype for Business Cloud Connector <br/>&nbsp;&nbsp; &nbsp; Edizione | |
> | È configurato un ambiente ibrido con Skype for Business Online? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Questo ambiente è ospitato e gestito da un terzo <br/>Partito? In caso affermativo, prendi nota dei dettagli nella scheda <br/>Colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Quali modalità e funzionalità sono attualmente in uso <br/>Oggi? | <input type="checkbox"> Messaggistica istantanea e presenza (IM/P) <br/> <input type="checkbox"> Conferenza <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Registrazione riunione <br/> <input type="checkbox"> Chat persistente/ Chat di gruppo <br/> <input type="checkbox"> Audioconferenza Microsoft <br/>&nbsp;&nbsp; &nbsp;(in precedenza Chiamata in conferenza) sul tuo <br/>&nbsp;&nbsp; &nbsp;locale Di Lync Server o <br/>&nbsp;&nbsp; &nbsp;distribuzione Skype for Business <br/> <input type="checkbox"> Audioconferenza di terze parti <br/>&nbsp;&nbsp; &nbsp;(Nota i dettagli nei commenti <br/>&nbsp;&nbsp; &nbsp;).) <br/> <input type="checkbox">VoIP aziendale uso locale <br/>&nbsp; &nbsp; &nbsp;Connettività PSTN <br/> <input type="checkbox"> Piani per chiamate (in precedenza chiamate PSTN) tramite <br/>&nbsp;&nbsp; &nbsp; Ibrida con Skype for Business Online | |
> | Quali versioni di Edge Server sono state distribuite? | <input type="checkbox"> Office Communications Server 2007 "R1" <br/> <input type="checkbox"> Office Communications Server 2007 R2 <br/> <input type="checkbox"> Lync Server 2010 <br/> <input type="checkbox"> Lync Server 2013 <br/> <input type="checkbox">Skype for Business Server 2015 <br/> <input type="checkbox">Skype for Business Server 2019| |
> | Si ha Lync o Skype for Business Edge? <br/>distribuito in più data center? <br/>Se sì, prendere nota dei dettagli nella colonna Commenti. | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Seleziona i servizi forniti oggi dal tuo ruolo Edge. | <input type="checkbox"> Accesso degli utenti esterni (utenti aziendali) <br/> <input type="checkbox"> Accesso remoto degli utenti (utenti anonimi) <br/>&nbsp;&nbsp; &nbsp;partecipanti alla riunione esterna) <br/> <input type="checkbox"> Federazione <br/> <input type="checkbox"> Media Relay | |
> | Quali delle seguenti funzionalità di chiamata vocale ti serve <br/>attualmente hanno dipendenze da? <br/>Prendere nota di eventuali altre dipendenze nei commenti <br/>Colonna. | <input type="checkbox"> Opzioni occupato <br/> <input type="checkbox"> Parcheggio di chiamata <br/> <input type="checkbox"> Ritiro chiamate o ritiro chiamate di gruppo <br/> <input type="checkbox"> Telefoni dell'area comune o "hot desking" <br/> <input type="checkbox"> Response Group o gruppi di risposta <br/> <input type="checkbox"> Aspetto linea condivisa <br/> <input type="checkbox"> Riga privata <br/> <input type="checkbox"> Segreteria telefonica <br/> <input type="checkbox"> Chiamare tramite ufficio <br/> <input type="checkbox"> Numeri di emergenza o informazioni <br/>&nbsp;&nbsp; &nbsp;(911, 811, 411) <br/> <input type="checkbox"> Composizione delle estensioni <br/> <input type="checkbox"> Operatore automatico <br/> <input type="checkbox"> Accesso sottoscrittore <br/> <input type="checkbox"> Dispositivi analogici <br/> <input type="checkbox"> Fax <br/> <input type="checkbox"> Mascheramento o modifica dell'ID chiamante <br/> <input type="checkbox"> Routing basato sulla posizione <br/> <input type="checkbox"> Routing con costi minimi <br/> <input type="checkbox"> Telefoni elevatori | |

## <a name="networking-and-access-to-microsoft-365-and-office-365-services"></a>Rete e accesso a Microsoft 365 e servizi di Office 365

Usare la tabella seguente per acquisire i dettagli di rete dell'organizzazione e il modo in cui gli utenti sono (o saranno) connessi a Microsoft 365 e ai servizi di Office 365.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Come (o come) gli utenti nell'ambito della migrazione <br/>accedere a Teams quando è in ufficio? <br/>Selezionare tutte le risposte pertinenti. | <input type="checkbox"> Connessione NAT instradata <br/> <input type="checkbox"> Server proxy <br/> <input type="checkbox"> Wi-Fi pubblica <br/> <input type="checkbox"> Gestito (non pubblico) Wi-Fi <br/> <input type="checkbox"> ExpressRoute <br/>&nbsp;&nbsp; &nbsp;(peering Microsoft) ||
> | Se l'accesso a Microsoft 365 o a Office 365 avviene tramite un<br/>proxy, esiste un modo per bypassare il proxy? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | ExpressRoute viene usato oggi? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No <br/> <input type="checkbox"> No, ma è in corso di pianificazione | |
> | È stata eseguita una valutazione di conformità alla rete? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Gli utenti devono utilizzare una VPN quando si connettono a <br/>le risorse aziendali in remoto? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Se viene usata una VPN, il traffico di Teams può essere escluso <br/>la VPN per accedere direttamente a Microsoft 365 e ai servizi di Office 365? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | La tua rete supporta QoS? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | È possibile assegnare priorità al traffico audio e video di Teams <br/>per guidare un'esperienza di alta qualità? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Tutte le località all'interno di un'area geografica hanno un uscita Internet, <br/>o internet in uscita è centralizzato per l'intera area geografica? | <input type="checkbox"> Accesso regionale a Internet <br/> <input type="checkbox"> Accesso centralizzato all'app <br/>&nbsp;&nbsp; &nbsp;Internet | |

## <a name="endpoints"></a>Endpoint

Usare la tabella seguente per acquisire i dettagli dei client e degli endpoint in uso.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Quale sistema operativo desktop usano gli utenti? | <input type="checkbox"> Windows XP <br/> <input type="checkbox"> Windows 7 <br/> <input type="checkbox">Windows 8 <br/> <input type="checkbox">Windows 10 <br/> <input type="checkbox"> Mac (Specificare la versione nella colonna Commenti). <br/> <input type="checkbox"> Linux (specificare la distribuzione nella colonna Commenti). <br/><input type="checkbox"> Altro (si noti i dettagli nella colonna Commenti). | |
> | Quale versione di Microsoft Office è distribuita <br/>a questi dispositivi? | <input type="checkbox"> Office 2003 <br/> <input type="checkbox"> Office 2007 <br/> <input type="checkbox"> Office 2010 <br/> <input type="checkbox"> Office 2013 <br/> <input type="checkbox"> Office 2016 <br/> <input type="checkbox">Office per Mac 2011 <br/> <input type="checkbox">Office per Mac 2016 <br/> <input type="checkbox"> Altro (si noti i dettagli nella colonna Commenti). | |
> | Tecnologia di distribuzione di Office in uso <br/>nella tua organizzazione? | <input type="checkbox"> MSI <br/> <input type="checkbox"> A portata di clic | |
> | Quali sono i dispositivi mobili consentiti e supportati <br/>piattaforme in uso? <br/>Selezionare tutte le risposte pertinenti. | <input type="checkbox"> Finestre <br/> <input type="checkbox"> Mobile <br/> <input type="checkbox"> Ios <br/> <input type="checkbox"> Android <br/> <input type="checkbox"> Altro (si noti i dettagli nella colonna Commenti). | |
> | Come vengono forniti i dispositivi mobili? <br/>Selezionare tutte le risposte pertinenti. | <input type="checkbox"> Dispositivi aziendali <br/> <input type="checkbox"> Porta il tuo dispositivo | |
> | Quali dispositivi usano attualmente gli utenti per accedere <br/>servizi di audioconferenza <br/>(telefoni, cuffie, telefoni, video)? | | |

## <a name="operations"></a>Operazioni

Usare la tabella seguente per acquisire i dettagli degli aspetti operativi dell'ambiente.

> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Qual è il modello operativo per Lync Server, <br/>Skype for Business Server, distribuzione di Microsoft 365, <br/>o Office 365 distribuzione oggi? | | |
> | È possibile delineare la disposizione del supporto corrente per <br/>Lync Server, Skype for Business Server, Microsoft 365 <br/>o Office 365? | | |
> | Se stai distribuendo in più paesi o aree geografiche, <br/>ciascun paese/area geografica dispone di un proprio <br/>il personale a lavorare con, o sarà gestito centralmente? | <input type="checkbox"> Operazioni regionali e sostegno <br/> <input type="checkbox"> Operazioni centralizzate e supporto | |
> | Stai seguendo la metodologia per la qualità delle chiamate? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No | |
> | Hai assegnato una persona o un team all'elenco <br/>Ruolo di Quality Champion per la piattaforma di collaborazione <br/>in uso? | <input type="checkbox"> Sì <br/> <input type="checkbox"> No ||
> | Come monitorare Lync Server, Skype for <br/>Business Server, distribuzione di Microsoft 365 o <br/>Office 365 distribuzione? | | |
> | Si verificano problemi di qualità delle chiamate? | <input type="checkbox"> Sì<br/> <input type="checkbox"> No | |
> | Come e quando fornisci formazione al tuo <br/>helpdesk su nuovi servizi e funzionalità? | | |

## <a name="adoption-and-readiness"></a>Adozione e preparazione

Usare la tabella seguente per acquisire lo stato di adozione e conformità corrente dell'organizzazione.

>
> | Domanda | Risposta | Commenti |
> |---|---|---|
> | Qual è il tuo attuale utilizzo attivo di <br/>Skype for Business? | **__** % utenti attivi totali e utenti abilitati | |
> | Come viene usato l'organizzazione <br/>Skype for Business? | Conversazioni 1:1 <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> IM <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chiamata <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Condivisione<br/> Riunioni <br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Conferenza<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Condivisione<br/>&nbsp;&nbsp; &nbsp;<input type="checkbox"> Chiamata | |
> | L'organizzazione ha un'adozione da parte degli utenti <br/>e il team di gestione delle modifiche? | <input type="checkbox"> Sì<br/> <input type="checkbox"> No | |
> | Come misurare attualmente il successo della tecnologia <br/>ad esempio Skype for Business? | | |
> | Quale percentuale della tua base di utenti diresti che ha <br/>adottato Skype for Business? | | |
> | Che cos'è la valutazione degli utenti in merito a Skype for Business? | <input type="checkbox"> Buono <br/> <input type="checkbox"> Neutro <br/> <input type="checkbox"> Male | |
> | Quale delle seguenti affermazioni descrive meglio l'implementazione <br/>strategia usata per la Skype for Business <br/>Distribuzione? | <input type="checkbox"> Portata generale: campagna di posta elettronica con <br/>&nbsp;&nbsp; &nbsp;collegamenti alla formazione <br/> <input type="checkbox"> Espanso: portata estesa più una varietà <br/>&nbsp;&nbsp; &nbsp;campagne di sensibilizzazione (poster, <br/>&nbsp;&nbsp; &nbsp;eventi, campioni) e formazione <br/>&nbsp;&nbsp; &nbsp;(video, manuali dell'utente, di persona) <br/> <input type="checkbox"> Su misura: Espanso, più mirato <br/>&nbsp;&nbsp; &nbsp;messaggistica e formazione per persona <br/> <input type="checkbox"> Altro <br/>&nbsp;&nbsp; &nbsp;Si noti i dettagli nella colonna Commenti. | |
