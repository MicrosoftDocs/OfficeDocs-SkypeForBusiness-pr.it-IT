---
title: Cosa sono gli operatori automatici cloud?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.autoattendants.overview
ms.custom:
- Phone System
description: Scopri quali sono gli operatori automatici di cloud e come usarli.
ms.openlocfilehash: b3541ad88f29727d07043cba46503d040e6434c0
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2019
ms.locfileid: "36184669"
---
# <a name="what-are-cloud-auto-attendants"></a>Cosa sono gli operatori automatici cloud?

Sistema telefonico in Office 365 fornisce gli operatori automatici, che possono essere usati per consentire ai chiamanti esterni e interni di spostarsi in un sistema di menu per individuare e inserire o trasferire le chiamate agli utenti o ai reparti aziendali dell'organizzazione.
  
Un operatore automatico è una serie di richieste vocali o di file audio che i chiamanti sentono al posto di un operatore umano quando chiamano un'organizzazione. Quando gli utenti chiamano un numero associato a un operatore automatico, le loro scelte possono reindirizzare la chiamata a un utente o individuare qualcuno nell'organizzazione e quindi connettersi a tale utente. Possono esprimere le proprie scelte e interagire con il sistema di menu usando la tastiera del telefono (DTMF) o il riconoscimento vocale.
  
Per configurare un operatore automatico per il sistema telefonico in Office 365, vedere [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).
  
Un operatore automatico cloud ha le caratteristiche seguenti:
  
- Può fornire messaggi di saluto informativi o aziendali.
- Può offrire menu aziendali personalizzati. Puoi personalizzare questi menu per disporre di più di un livello.
- Fornisce la ricerca nella directory che consente alle persone che chiamano per cercare un nome nella directory dell'organizzazione.
- Consente a un utente che chiama di raggiungere o di uscire da un messaggio per una persona dell'organizzazione.
- Supporta più lingue per le richieste, la sintesi vocale e il riconoscimento vocale.
- Supporta l'impostazione di festività e orari di ufficio.
- Supporta il trasferimento della chiamata a un operatore, ad altri utenti, alle code di chiamata e agli operatori automatici.

> [!NOTE]
> Questo articolo si applica sia a Microsoft teams che a Skype for business online.

## <a name="getting-started"></a>Introduzione

Per iniziare a utilizzare gli operatori automatici, è importante ricordare quanto segue.

- Per avere un account di risorse associato, è necessario un operatore automatico. Per informazioni dettagliate sugli account delle risorse, vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) .
- Se si sta assegnando un numero di telefono a un account di risorse, è ora possibile usare la licenza per gli utenti virtuali del sistema telefonico senza costi. In questo modo le funzionalità del sistema telefonico sono disponibili per i numeri di telefono a livello di organizzazione e consentono di creare funzionalità di operatore automatico e coda di chiamata.

> [!NOTE]
> I numeri di servizio di routing diretto per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti e gli agenti di Microsoft teams.
  
   > [!TIP]
   > Per reindirizzare le chiamate a un operatore o a un'opzione di menu che è un utente online con una licenza di **sistema telefonico** , sarà necessario abilitarle per VoIP aziendale o assegnare loro piani di chiamata. Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md). Puoi anche utilizzare Windows PowerShell. Ad esempio, esegui:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ottenere e usare i numeri di servizio gratuiti per gli operatori automatici, è necessario configurare i crediti per le comunicazioni. Per eseguire questa operazione, vedere informazioni sui crediti per le [comunicazioni](what-are-communications-credits.md) e [configurare i crediti per le comunicazioni per l'organizzazione](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati agli operatori automatici, ma solo numeri di telefono di servizio a pagamento o numeri verdi.

- Un sistema di operatore automatico completo coinvolgerà in genere più operatori automatici e può richiedere solo un singolo numero di telefono assegnato per l'operatore automatico di primo livello o di entrata. Gli altri operatori automatici o le code di chiamata nel sistema completo necessitano solo di un numero di telefono se si vuole specificare più punti di ingresso nel sistema.
- È possibile applicare più di un numero di telefono a un operatore automatico associando più account di risorse a un operatore automatico.
  
## <a name="feature-overview"></a>Panoramica delle funzionalità

### <a name="dial-by-name"></a>Chiamata per nome

Chiamata per nome è una caratteristica di un operatore automatico noto anche come ricerca directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte del tastierino telefonico (DTMF) per immettere un nome completo o parziale nella directory della società, individuare la persona e quindi fare in modo che venga trasferita la chiamata. Gli utenti che desiderano avere individuato e raggiunto tramite chiamata per nome **non devono avere un numero di telefono o avere piani di chiamata assegnati, ma devono avere una licenza di sistema telefonico se sono utenti online o EV abilitato per gli utenti di onlocale**. Il comando componi per nome sarà anche in grado di trovare e trasferire le chiamate agli utenti di Microsoft teams ospitati in paesi o aree geografiche diverse per organizzazioni multinazionali.

### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Non esiste alcun limite per le dimensioni di Active Directory per cui è supportata la chiamata in base al nome quando si usa la tastiera del telefono per cercare l'immissione di nomi parziali o completi (nome + cognome e anche cognome + nome). Tuttavia, le dimensioni massime degli elenchi di nomi che un singolo operatore automatico può supportare usando il riconoscimento dei nomi con la parola sono gli utenti di 80.000.
  
|Tipo di ingresso|Formato di ricerca|Numero massimo di utenti di un'organizzazione|
|:-----|:-----|:-----|
|DTMF (immissione con tastiera) |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome |Nessun limite  |
|Voce (ingresso vocale) |FirstName  <br/> LastName  <br/> Nome + Cognome  <br/> Cognome + Nome  | utenti di 80.000 |

> [!NOTE]
> Se si usa dial by Name con il riconoscimento vocale, ma Active Directory dell'organizzazione è maggiore di 80.000 utenti e non è stato limitato l'ambito della chiamata per nome tramite la caratteristica ambito di chiamata, il comando componi per nome continuerà a funzionare per i chiamanti tramite una tastiera del telefono e gli input vocali saranno disponibili per tutti gli altri scenari. È possibile utilizzare la funzione Ambito di chiamata per limitare i nomi raggiungibili modificando l'ambito di Chiamata per nome per un particolare operatore automatico.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Chiamata per nome - Immissione con tastiera (DTMF)

Le persone che chiamano in può usare la chiamata in base al nome per raggiungere gli utenti specificando il nome completo o parziale della persona che sta cercando di raggiungere. Sono disponibili vari formati che possono essere usati quando viene immesso il nome.

Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando si immette il nome, verrà chiesto di terminare l'immissione del tastierino numerico con il tasto #. Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Le persone possono cercare nomi nell'organizzazione utilizzando i seguenti formati di ricerca sulla tastiera del telefono.
  
|Formato del nome|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa  |Amos0Marble# |Amos Marble |
|Cognome + Nome |Completa |Marble0Amos#  |Amos Marble |
|FirstName  |Completa   |Amos#   |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|LastName |Completa |Marble#  |Premere 1 per Amos Marble  <br/> Premere 2 per Mary Marble |
|Nome o Cognome |Parziale |Mar# |Premere 1 per Mary Marble  <br/> Premere 2 per Mary Jones  <br/> Premere 3 per Amos Marcus |
|Nome + Cognome |Parziale |Mar0Amos# |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|Cognome + Nome |Parziale |Mar0Am# |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |

Ci sono diversi caratteri speciali che vengono utilizzati per la ricerca di persone con la tastiera del telefono. Ad esempio, alla persona verrà richiesto di usare il tasto cancelletto (#), mentre il tasto zero (0) viene usato per uno spazio tra i nomi. Premendo il tasto asterisco (*) verrà ripetuto l'elenco dei nomi corrispondenti.
  
|Carattere speciale della tastiera del telefono|Cosa significa|
|:-----|:-----|
|#   |Carattere terminale quando si immette un nome. |
|0   |Spazio tra i nomi. |
|*    |Ripete l'elenco dei nomi corrispondenti. |

### <a name="dial-by-name---name-recognition-with-speech"></a>Chiamata per nome - Riconoscimento vocale del nome

Gli utenti possono cercare altri utenti nella propria organizzazione usando la voce (riconoscimento vocale). Possono anche raggiungere chiunque nell'Active Directory della società dicendo il nome della persona che sta tentando di individuare. L'uso di input vocali può riconoscere i nomi in diversi formati, tra cui nome, cognome, nome + cognome o cognome + nome.
  
Quando si Abilita il riconoscimento vocale per un operatore automatico, la voce del tastierino telefonico (DTMF) non verrà disabilitata, pertanto è possibile usare entrambi i tipi di input. La voce della tastiera del telefono non può essere disabilitata e può essere usata in qualsiasi momento, anche se il riconoscimento vocale è abilitato nell'operatore automatico.
  
Come avviene per l'immissione da tastiera, se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Il chiamante può pronunciare i nomi nei seguenti formati.
  
|Nome con il riconoscimento vocale|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa |Amos Marble |Amos Marble |
|Cognome + Nome |Completa  |Marble Amos |Amos Marble |
|FirstName |Completa |Amos |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones |
|LastName |Completa |Marble |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble |

> [!NOTE]
> Per un nuovo utente possono essere necessarie fino a 36 ore per avere il nome elencato nella directory per il nome della chiamata tramite il riconoscimento vocale a causa del ritardo di replica di Active Directory.
  
### <a name="language-support"></a>Lingue supportate

Sono disponibili le seguenti lingue per il sintetizzatore vocale.
  
||||
|:-----|:-----|:-----|
|Arabo (EG)  |Inglese (NZ)  |Coreano (KO)  |
|Cinese (HK)  |Inglese (UK) |Norvegese (NO)  |
|Cinese (TW) |Inglese (US) |Polacco (PL)  |
|Cinese (ZH) |Finlandese (FI) |Portoghese (BR) |
|Danese (DA)  |Francese (CA)  |Portoghese (PT) |
|Olandese (NL)   |Francese (FR)  |Russo (RU) |
|Inglese (AU)  |Tedesco (DE) |Spagnolo (ES)  |
|Inglese (CA)  |Italiano (IT) |Spagnolo (MX)|
|Inglese (IN)  |Giapponese (JP) |Svedese (SV)|

Il riconoscimento vocale per gli operatori automatici è disponibile nelle seguenti lingue.
  
|||
|:-----|:-----|
|Cinese (ZH)  |Francese (FR)  |
|Inglese (AU)  |Tedesco (DE)  |
|Inglese (CA)  |Italiano (IT)  |
|Inglese (IN)  |Giapponese (JP)  |
|Inglese (UK)  |Portoghese (BR)  |
|Inglese (US)  |Spagnolo (ES)  |
|Francese (CA)   |Spagnolo (MX)  |

I seguenti comandi vocali sono disponibili nelle quattordici (14) lingue supportate per il riconoscimento vocale.
  
|Comando vocale| Corrisponde a |
|:-----|:-----|
|Sì |Sì - corrisponde a premere 1 per Sì. |
|No |No - corrisponde a premere 2 per No. |
|Ripeti |Ripete l'elenco di opzioni - corrisponde a premere * per ripetere l'elenco di opzioni. |
|Operatore |Chiama operatore - corrisponde a premere 0 per "Operatore". |
|Menu principale  |Porta il chiamante al menu principale dell'operatore automatico. |
|Zero |Corrisponde a premere 0 (per impostazione predefinita, ha la stessa funzione di "Operatore").|
|Uno |Corrisponde a premere 1. |
|Due |Corrisponde a premere 2. |
|Tre|Corrisponde a premere 3.|
|Quattro |Corrisponde a premere 4. |
|Cinque |Corrisponde a premere 5. |
|Sei  |Corrisponde a premere 6. |
|Sette |Corrisponde a premere 7.|
|Otto |Corrisponde a premere 8.|
|Nove  |Corrisponde a premere 9.|

### <a name="using-the-operator-option"></a>Uso dell'opzione operatore

L'uso dell'operatore per un operatore automatico è un'impostazione facoltativa che fornisce al chiamante l'opzione di parlare con un operatore umano.
  
Il tasto 0 e il comando vocale "operator" indirizzano la chiamata all'operatore designato per impostazione predefinita. Questo è il caso di tutte le lingue supportate per il riconoscimento vocale. È anche possibile usare le **Opzioni di menu** per impostare un valore personalizzato per l'operatore.
  
L'operatore può essere impostato su:
  
- Un utente di Microsoft teams o un utente di Skype for business in cui è abilitata la funzionalità VoIP aziendale.
  
- Un altro operatore automatico configurato per l'organizzazione.
- Una coda di chiamata in corso configurata nell'organizzazione. Per altre informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Orario di ufficio e gestione delle chiamate

L'orario di ufficio è impostato su tutti gli operatori automatici. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. Gli orari di ufficio possono essere impostati con interruzioni nel tempo durante il giorno e tutte le ore che non sono impostate come orari di ufficio sono considerate after-hours. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto diversi (facoltativi) ed entrambi possono essere impostati per le ore lavorative e le ore successive.
  
Ogni operatore automatico ha le opzioni di gestione delle chiamate che possono essere impostate:
  
- È possibile far scollegare la chiamata dopo il saluto.
- È possibile anche:
  - Reindirizza la chiamata a un utente di Microsoft teams che dispone di una licenza per il **sistema telefonico** con funzionalità VoIP aziendale o con piani di chiamata assegnati. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per farlo, scegli una **Persona nell'azienda** che riceverà le chiamate inoltrate direttamente alla segreteria telefonica.

  - Reindirizzare la chiamata a una coda di chiamata. Per altre informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Reindirizzare la chiamata a un altro operatore automatico configurato.
  - Creare opzioni di menu e riprodurre un messaggio menu per il chiamante. Ad esempio: "Premere 1 per i servizi commerciali, premere 2 per l'assistenza. Per parlare con l'operatore, premere 0 in qualsiasi momento".

### <a name="menu-options"></a>Opzioni di menu

Gli operatori automatici del cloud consentono di creare prompt dei menu ("premere 1 per le vendite, premere 2 per i servizi") e configurare le opzioni del menu per instradare le chiamate in base all'opzione selezionata dall'utente. L'impostazione di opzioni di menu per un operatore automatico consente a un'organizzazione di fornire una guida interattiva per portare la persona a destinazione più velocemente, senza dover ricorrere a un operatore umano per gestire le chiamate in arrivo. Le richieste di menu possono essere create usando la sintesi vocale (prompt generati dal sistema) o caricando un file audio registrato. Il riconoscimento vocale utilizza i comandi vocali per la navigazione in vivavoce, ma il chiamante può anche usare la tastiera del telefono per navigare nei menu.
  
I tasti da 0 a 9 possono essere assegnati alle **Opzioni di menu** in un operatore automatico con l'interfaccia di amministrazione di Skype for business. Possono essere create serie di opzioni di menu diverse per l'orario di ufficio e l'orario di chiusura, e si può attivare o disattivare Chiamata per nome nelle **Opzioni di menu**. I tasti possono essere mappati per trasferire le chiamate a:
  
- Un operatore, mappato al tasto 0 per impostazione predefinita. Tuttavia, può essere riassegnato a qualsiasi altro tasto o rimosso dal menu.
- Una coda di chiamata.
- Un altro operatore automatico. I menu multilivello possono essere configurati puntando un' **opzione di menu** in un operatore automatico a un altro operatore automatico con il proprio set di opzioni di menu, che si chiama operatore automatico "annidato".
- Un utente di Microsoft teams che dispone di una licenza di **sistema telefonico** con VoIP aziendale o con piani di chiamata assegnati. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per farlo, scegli una **Persona nell'azienda** che riceverà le chiamate inoltrate direttamente alla segreteria telefonica.
  
Il nome di ogni opzione del menu diventa una parola chiave per il riconoscimento vocale se il riconoscimento vocale è stato abilitato. Ad esempio, i chiamanti possono pronunciare "uno" per selezionare l'opzione di menu mappata con il tasto 1 oppure possono semplicemente dire "vendite" per selezionare la stessa opzione di menu denominata "Sales".
  
Per configurare un operatore automatico e le opzioni di menu, [impostare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Assegnazione di numeri di telefono per un operatore automatico

È possibile assegnare un numero di servizio Microsoft, un numero di routing diretto o un numero ibrido all'operatore automatico. Vedere [pianificare il routing diretto](direct-routing-plan.md) per i dettagli.

Per assegnare un numero di servizio, è necessario ottenere o trasferire i numeri di servizio a pagamento o a pedaggio esistenti. Una volta ottenuto il pedaggio o i numeri di telefono del servizio gratuito, verranno visualizzati nella finestra di dialogo <!-- validate nav path --> **** > I**numeri di telefono****vocali** > dell'interfaccia di amministrazione di Skype for business e il **tipo di numero** elencato saranno elencati come **servizio a pagamento gratuito**. Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono per Skype for business e Microsoft teams](/microsoftteams/getting-service-phone-numbers) oppure, se si vuole trasferire e numero di servizio esistente, vedere trasferire i [numeri di telefono in Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio. È invece necessario [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per vedere come eseguire questa operazione.
  
## <a name="related-topics"></a>Argomenti correlati

[Ecco cosa offre il Sistema telefonico in Office 365](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Esempio per piccole imprese - Impostare un operatore automatico](/microsoftteams/tutorial-org-aa)
