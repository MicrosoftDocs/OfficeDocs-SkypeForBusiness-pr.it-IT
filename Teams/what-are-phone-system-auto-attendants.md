---
title: Cosa sono gli operatori automatici cloud?
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: makolomi
ms.date: 4/2/2019
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sugli operatori automatici Cloud e su come usarli per consentire ai chiamanti di spostarsi attraverso un sistema di menu per individuare ed effettuare o trasferire chiamate a utenti o reparti.
ms.openlocfilehash: 862272ffe0cb42edc092c513823f421ab1c5bd95
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918942"
---
# <a name="what-are-cloud-auto-attendants"></a>Cosa sono gli operatori automatici cloud?

Sistema telefonico fornisce operatori automatici, che possono essere usati per consentire ai chiamanti esterni e interni di spostarsi attraverso un sistema di menu per individuare ed effettuare o trasferire chiamate a utenti o reparti dell'organizzazione.
  
Un operatore automatico è spesso un nodo di un sistema, dando al chiamante una serie di comandi vocali o file audio che sente invece di un operatore umano. Quando le persone chiamano un numero associato a un operatore automatico, le loro scelte possono reindirizzare la chiamata a un utente o individuare qualcuno nell'organizzazione e quindi connettersi a quell'utente. Possono esprimere le proprie scelte e interagire con il sistema di menu usando la tastiera del telefono (DTMF) o il riconoscimento vocale. Le scelte effettuate possono anche reindirizzare la chiamata a un altro operatore automatico o a una coda di chiamata.
  
Per impostare un operatore automatico per Sistema telefonico, vai [a Imposta un operatore automatico Cloud.](create-a-phone-system-auto-attendant.md)
  
Un operatore automatico Cloud ha le seguenti funzionalità:
  
- Può fornire messaggi di saluto informativi o aziendali.
- Può offrire menu aziendali personalizzati. Puoi personalizzare questi menu per disporre di più di un livello.
- Fornisce una ricerca in elenco che consente alle persone che chiamano di cercare un nome nella directory dell'organizzazione.
- Consente a un utente che chiama di raggiungere o lasciare un messaggio a una persona dell'organizzazione.
- Supporta più lingue per prompt, sintesi vocale e riconoscimento vocale.
- Supporta l'impostazione di festività e orari di ufficio.
- Supporta il trasferimento delle chiamate a un operatore, ad altri utenti, code di chiamata e operatori automatici.
- Supporta la segreteria telefonica condivisa per consentire ai chiamanti di lasciare un messaggio per un'organizzazione.

> [!NOTE]
> Questo articolo si applica sia a Microsoft Teams che a Skype for Business Online.

## <a name="getting-started"></a>Introduzione

Per iniziare a utilizzare gli operatori automatici, è importante ricordare quanto segue.

- Per avere un account delle risorse associato, è necessario un operatore automatico. Per [informazioni dettagliate sugli account delle risorse, vedere](manage-resource-accounts.md) Gestire gli account delle risorse in Teams. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Quando assegni un numero di telefono a un operatore automatico, lo stai assegnando all'account delle risorse associato a quell'operatore automatico. In questo modo è possibile avere più numeri di telefono per accedere a un operatore automatico. Nella maggior parte dei casi, un account delle risorse usa la licenza utente virtuale Sistema telefonico senza costi. Questa licenza fornisce funzionalità Sistema telefonico ai numeri di telefono a livello organizzativo e consente di creare operatori automatici e code di chiamata.

> [!NOTE]
> I numeri di servizio di instradamento diretto per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti di Microsoft Teams e gli agenti di chiamata.

   > [!TIP]
   > Per reindirizzare le chiamate a un operatore  o a un'opzione di menu che rappresenta un utente online con licenza Sistema telefonico, devi abilitare il suo account per VoIP aziendale o assegnargli Piani per chiamate. Vedi [Assegnare le licenze per i componenti aggiuntivi di Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md) Puoi anche utilizzare Windows PowerShell. Ad esempio, esegui:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ottenere e utilizzare numeri di servizio a numero verde per gli operatori automatici, devi impostare i Crediti comunicazioni. Per farlo, consulta [Cosa sono i Crediti comunicazioni?](what-are-communications-credits.md) e Imposta i Crediti comunicazioni per la tua [organizzazione.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati agli operatori automatici, ma solo numeri di telefono di servizio a pagamento o numeri verdi.

- Un sistema completo di operatore automatico comporta in genere più operatori automatici.
- È possibile applicare più numeri di telefono agli operatori automatici entry-level.
- Gli operatori automatici o le code di chiamata non entry level nel sistema completo avranno bisogno di un numero di telefono solo se effettuano chiamate PSTN in uscita.
  
## <a name="feature-overview"></a>Panoramica delle caratteristiche

### <a name="searching-for-users"></a>Ricerca di utenti

Chiamata per nome è una funzione di un operatore automatico, nota anche come ricerca in elenco. Consente alle persone che chiamano l'operatore automatico di usare le risposte vocali (riconoscimento vocale) o la tastiera del telefono (DTMF) per immettere un nome completo o parziale per cercare nell'elenco aziendale, individuare la persona e poi trasferirla a quella persona. Gli utenti che si desidera trovare e raggiungere utilizzando Chiamata per nome non sono tenuti ad avere un numero di telefono o disporre di Piani per chiamate assegnati, ma devono avere una licenza Sistema telefonico se sono utenti online o VoIP aziendale abilitati per gli utenti **di Skype for Business Server.** Chiamata per nome sarà anche in grado di trovare e trasferire le chiamate a utenti di Microsoft Teams ospitati in paesi o aree geografiche diverse per organizzazioni internazionali. Considerando i prerequisiti necessari, abiliti esplicitamente Chiamata per nome in un operatore automatico.

Chiamata per interno è una caratteristica di un operatore automatico che fa anche parte della ricerca in elenco. Consente alle persone che chiamano l'operatore automatico di usare le risposte vocali (riconoscimento vocale) o la tastiera del telefono (DTMF) per immettere l'interno del telefono dell'utente che sta cercando di raggiungere e quindi far trasferire la chiamata a quel utente. Gli utenti che desideri trovare e raggiungere utilizzando Chiamata per interno non sono tenuti ad avere un numero di telefono o avere piani per chiamate assegnati, ma devono avere una licenza Sistema telefonico se sono utenti online o VoIP aziendale abilitati per gli utenti **di Skype for Business Server.** Devi inoltre avere un piano di chiamata configurato in modo appropriato per i tuoi utenti. Chiamata per interno sarà anche in grado di trovare e trasferire le chiamate a utenti di Microsoft Teams ospitati in paesi o aree geografiche diverse per organizzazioni multi-nazionali. Considerando i prerequisiti necessari, abiliti esplicitamente Chiamata per interno in un operatore automatico.

#### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Non ci sono limiti al numero di utenti Active Directory che Chiamata per nome e Chiamata per interno possono supportare quando un chiamante cerca una persona specifica. Un chiamante può immettere nomi parziali o completi (Nome + Cognome e anche Cognome + Nome), ma richiede il numero di interno completo. La dimensione massima dell'elenco nomi che un operatore automatico può supportare utilizzando il riconoscimento vocale è di 80.000 utenti.
  
|Tipo di ingresso|Formato di ricerca|Numero massimo di utenti di un'organizzazione|
|:-----|:-----|:-----|
|DTMF (immissione con tastiera) |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome |Nessun limite  |
|Voce (ingresso vocale) |Nome  <br/> Cognome  <br/> Nome + Cognome  <br/> Cognome + Nome  | 80.000 utenti |

> [!NOTE]
> Se si utilizza Chiamata per nome con il riconoscimento vocale, ma l'elenco Active Directory dell'organizzazione è più grande di 80.000 utenti e non hai limitato l'ambito di Chiamata per nome utilizzando la funzione Ambito di chiamata, Chiamata per nome continuerà a funzionare per i chiamanti utilizzando la tastiera del telefono e gli input vocali saranno disponibili per tutti gli altri scenari. È possibile utilizzare la funzione Ambito di chiamata per limitare i nomi raggiungibili modificando l'ambito di Chiamata per nome per un particolare operatore automatico.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Chiamata per nome - Immissione con tastiera (DTMF)

Le persone che chiamano possono utilizzare Chiamata per nome per raggiungere gli utenti specificando il nome completo o parziale della persona che stanno cercando di raggiungere. Al momento dell'immissione del nome è possibile usare diversi formati.

Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando immettono il nome, verrà chiesto di terminare l'immissione da tastiera con il tasto #. Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Le persone possono cercare nomi nell'organizzazione utilizzando i seguenti formati di ricerca sulla tastiera del telefono.
  
|Formato del nome|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa  |Amos0Marble# |Amos Marble |
|Cognome + Nome |Completa |Marble0Amos#  |Amos Marble |
|Nome  |Completa   |Amos#   |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|Cognome |Completa |Marble#  |Premere 1 per Amos Marble  <br/> Premere 2 per Mary Marble |
|Nome o Cognome |Parziale |Mar# |Premere 1 per Mary Marble  <br/> Premere 2 per Mary Jones  <br/> Premere 3 per Amos Marcus |
|Nome + Cognome |Parziale |Amos0Mar # |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |
|Cognome + Nome |Parziale |Mar0Am# |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus |

Ci sono diversi caratteri speciali che vengono utilizzati per la ricerca di persone con la tastiera del telefono. Ad esempio, alla persona verrà chiesto di usare il tasto cancelletto (#), mentre il tasto zero (0) viene usato per uno spazio tra i nomi. Premendo il tasto asterisco (*) verrà ripetuto l'elenco dei nomi corrispondenti.
  
|Carattere speciale della tastiera del telefono|Cosa significa|
|:-----|:-----|
|#   |Carattere terminale quando si immette un nome. |
|0   |Spazio tra i nomi. |
|*    |Ripete l'elenco dei nomi corrispondenti. |

#### <a name="dial-by-name---name-recognition-with-speech"></a>Chiamata per nome - Riconoscimento vocale del nome

Gli utenti possono cercare altre persone nell'organizzazione con la voce (riconoscimento vocale). Possono anche raggiungere chiunque in Active Directory pronunciando il nome della persona che stanno cercando. L'uso di input vocali consente di riconoscere i nomi in vari formati, tra cui Nome, Cognome, Nome + Cognome o Cognome + Nome.
  
Puoi abilitare il riconoscimento vocale per un operatore automatico, ma l'immissione da tastiera del telefono (DTMF) non è disabilitata. L'ingresso da tastiera del telefono può essere utilizzato in qualsiasi momento anche se il riconoscimento vocale è abilitato per l'operatore automatico.
  
Come per l'immissione da tastiera del telefono, se vengono trovati più nomi, la persona che chiama sente un elenco di nomi tra cui selezionare.
  
I chiamanti possono pronunciare i nomi nei seguenti formati:
  
|Nome con riconoscimento vocale|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa |Amos Marble |Amos Marble |
|Cognome + Nome |Completa  |Marble Amos |Amos Marble |
|Nome |Completa |Amos |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones |
|Cognome |Completa |Marble |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble |

> [!NOTE]
> Possono essere necessario fino a 36 ore perché il nome di un nuovo utente sia elencato nella directory chiamata per nome con riconoscimento vocale a causa di un ritardo di replica di Active Directory.
  
### <a name="language-support"></a>Lingue supportate

Per la sintesi vocale usata con le richieste in uscita sono disponibili le lingue seguenti:
  
|A-E|E-J|K-Z|
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

L'input di riconoscimento vocale per gli operatori automatici è disponibile nelle seguenti lingue:
  
|A-F|F-Z|
|:-----|:-----|
|Cinese (ZH)  |Francese (FR)  |
|Inglese (AU)  |Tedesco (DE)  |
|Inglese (CA)  |Italiano (IT)  |
|Inglese (IN)  |Giapponese (JP)  |
|Inglese (UK)  |Portoghese (BR)  |
|Inglese (US)  |Spagnolo (ES)  |
|Francese (CA)   |Spagnolo (MX)  |

I seguenti comandi vocali sono disponibili nelle 14 lingue supportate per il riconoscimento vocale:
  
|Comando vocale| Corrisponde a |
|:-----|:-----|
|Sì | Premere 1 per Sì. |
|No | Premere 2 per No. |
|Ripeti |Ripete l'elenco di opzioni. Premere * sulla tastiera per ripetere l'elenco di opzioni. |
|Operatore | Premere 0 per "Operatore" |
|Menu principale  |Porta il chiamante al menu principale dell'operatore automatico. |
|Zero | Premere 0 (per impostazione predefinita, come "Operatore").|
|Uno | Premere 1. |
|Due | Premere 2. |
|Tre| Premere 3.|
|Quattro | Premere 4. |
|Cinque | Premere 5. |
|Sei  | Premere 6. |
|Sette | Premere 7.|
|Otto |Premere 8.|
|Nove  |Premere 9.|

### <a name="the-operator-option"></a>Opzione operatore

Facoltativamente, un operatore automatico può essere impostato per dare al chiamante una selezione per parlare con un operatore umano.
  
Il tasto 0 e il comando vocale "Operatore" indirizzano la chiamata all'operatore designato per impostazione predefinita. Questo è il caso per tutte le lingue supportate per il riconoscimento vocale. È anche possibile usare Imposta **opzioni di menu** per impostare un valore personalizzato per l'operatore.
  
L'operatore può essere impostato su:
  
- Un utente Microsoft Teams o un utente di Skype for Business Server VoIP aziendale abilitato.
- Un altro operatore automatico configurato per l'organizzazione.
- Una coda di chiamata in corso configurata nell'organizzazione. Per ulteriori informazioni sulle code di chiamata, vedi [Creare una coda di chiamata cloud.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>Orario di ufficio e gestione delle chiamate

L'orario di ufficio può essere impostato su ogni operatore automatico. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. L'orario di ufficio può essere impostato con interruzioni durante il giorno e tutti gli orari non impostati come orario di ufficio sono considerati fuori orario. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto diversi (facoltativi) per l'orario di ufficio e l'orario di uscita.
  
Ogni operatore automatico ha diverse possibili opzioni di gestione delle chiamate:
  
- La chiamata può disconnettersi dopo la riproduzione di un messaggio di saluto.
- È possibile anche:
  - Reindirizza la chiamata a  un utente Microsoft Teams con licenza Sistema telefonico VoIP aziendale o a cui è assegnato Un Piano per chiamate. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per farlo, scegli una **Persona nell'azienda** che riceverà le chiamate inoltrate direttamente alla segreteria telefonica.

  - Reindirizza la chiamata a una coda di chiamata. Per ulteriori informazioni sulle code di chiamata, vedi [Creare una coda di chiamata cloud.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - Reindirizza la chiamata a un altro operatore automatico.

Queste opzioni vengono espresse al chiamante dall'operatore automatico quando riproduce i prompt del menu. Ad esempio: "Premere 1 per i servizi commerciali, premere 2 per l'assistenza. Per parlare con l'operatore, premere 0 in qualsiasi momento".

### <a name="set-menu-options"></a>Impostare le opzioni di menu

Gli operatori automatici cloud consentono di creare messaggi di menu ("Premere 1 per le vendite, premere 2 per i servizi") e impostare le opzioni di menu per instradare le chiamate in base alle selezioni dell'utente. Le opzioni di menu per un operatore automatico consentono a un'organizzazione di offrire una serie di scelte che guidano i chiamanti verso la loro destinazione più velocemente, senza affidarsi a un operatore umano per gestire le chiamate in arrivo. I prompt del menu possono essere creati usando la sintesi vocale (prompt generati dal sistema) o caricando un file audio registrato. Il riconoscimento vocale accetta comandi vocali per la navigazione senza mani, ma i chiamanti possono anche utilizzare la tastiera del telefono per navigare nei menu.
  
I tasti da 0 a 9 possono essere assegnati ai tasti di composizione di un operatore automatico utilizzando l'interfaccia di amministrazione di Skype for Business. Possono essere create serie di opzioni di menu diverse per l'orario di ufficio e l'orario di chiusura, e si può attivare o disattivare Chiamata per nome nelle **Opzioni di menu**. I tasti possono essere mappati per trasferire le chiamate a:
  
- Un operatore, mappato al tasto 0 per impostazione predefinita. Tuttavia, può essere riassegnato a qualsiasi altro tasto o rimosso dal menu.
- Una coda di chiamata.
- Un altro operatore automatico. I menu multi-livello possono essere impostati puntando un'opzione di **menu** in un operatore automatico a un altro operatore automatico con un proprio set di Opzioni di menu, che è chiamato operatore automatico "nidificato".
- Un utente di Microsoft Teams **con** licenza Sistema telefonico abilitato VoIP aziendale o a cui è assegnato un Piano per chiamate. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per farlo, scegli una **Persona nell'azienda** che riceverà le chiamate inoltrate direttamente alla segreteria telefonica.
  
Il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale se è stato abilitato il riconoscimento vocale. Ad esempio, i chiamanti possono dire "Uno" per selezionare l'opzione di menu mappata al tasto 1, oppure possono dire "Vendite" per selezionare la stessa opzione di menu denominata "Vendite".
  
Per impostare un operatore automatico e le opzioni di menu, vai [a Imposta un operatore automatico Cloud.](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Assegnazione di numeri di telefono a un operatore automatico

Puoi assegnare un numero di servizio Microsoft, un numero di instradamento diretto o un numero ibrido all'account delle risorse collegate dell'operatore automatico (o a più account delle risorse se si desidera utilizzare più numeri di telefono). Per [altre informazioni, vedere Pianificare](direct-routing-plan.md) l'instradamento diretto.

Per assegnare un numero di servizio, devi ottenere o convertire i numeri di servizio esistenti a numero verde o a numero verde. Una volta scaricati i numeri di servizio a numero verde o a numero verde, vengono visualizzati nei numeri di telefono vocali dell'interfaccia di amministrazione di **Skype for**  >    >  Business. **Tipo di** numero elencato **come Servizio - Numero verde.** Per ottenere i numeri di servizio, consulta Recupero di numeri di telefono di servizio per [Skype for Business](/microsoftteams/getting-service-phone-numbers) e Microsoft Teams o, se vuoi trasferire e il numero di servizio esistente, consulta Trasferire numeri di telefono in [Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
  
> [!NOTE]
> Se non si è negli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft Teams per ottenere numeri di servizio. Vai [invece a Gestisci numeri di telefono](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per la tua organizzazione per sapere come fare.
  
## <a name="related-topics"></a>Argomenti correlati

[Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
