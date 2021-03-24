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
description: Informazioni sugli operatori automatici cloud e su come usarli per consentire ai chiamanti di spostarsi in un sistema di menu per individuare e effettuare o trasferire chiamate a utenti o reparti.
ms.openlocfilehash: c8e5b3f608200036b8c9b9ed5338c558464b32d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100962"
---
# <a name="what-are-cloud-auto-attendants"></a>Cosa sono gli operatori automatici cloud?

Sistema telefonico fornisce operatori automatici, che possono essere usati per consentire ai chiamanti esterni e interni di spostarsi in un sistema di menu per individuare e effettuare o trasferire chiamate a utenti o reparti dell'organizzazione.
  
Un operatore automatico è il più delle volte un nodo in un sistema, fornendo a un chiamante una serie di prompt vocali o file audio che sentono al posto di un operatore umano. Quando le persone chiamano un numero associato a un operatore automatico, le loro scelte possono reindirizzare la chiamata a un utente o individuare qualcuno nell'organizzazione e quindi connettersi a tale utente. Possono esprimere le proprie scelte e interagire con il sistema di menu usando una tastiera del telefono (DTMF) o il riconoscimento vocale. Le scelte effettuate possono anche reindirizzare la chiamata a un altro operatore automatico o a una coda di chiamata.
  
Per configurare un operatore automatico per Sistema telefonico, passare [a Configurare un operatore automatico cloud.](create-a-phone-system-auto-attendant.md)
  
Un operatore automatico cloud ha le caratteristiche seguenti:
  
- Può fornire messaggi di saluto informativi o aziendali.
- Può offrire menu aziendali personalizzati. Puoi personalizzare questi menu per disporre di più di un livello.
- Fornisce una ricerca nella directory che consente alle persone che chiamano di cercare un nome nella directory dell'organizzazione.
- Consente a un utente che chiama di raggiungere o lasciare un messaggio per una persona dell'organizzazione.
- Supporta più lingue per le richieste, la sintesi vocale e il riconoscimento vocale.
- Supporta la specifica di festività e orari di ufficio.
- Supporta il trasferimento delle chiamate a un operatore, ad altri utenti, alle code di chiamata e agli operatori automatici.
- Supporta la segreteria telefonica condivisa per consentire ai chiamanti di lasciare un messaggio per un'organizzazione.

> [!NOTE]
> Questo articolo si applica sia a Microsoft Teams che a Skype for Business online.

## <a name="getting-started"></a>Introduzione

Per iniziare a utilizzare gli operatori automatici, è importante ricordare quanto segue.

- Un operatore automatico deve avere un account di risorsa associato. Per [informazioni dettagliate sugli account delle risorse,](manage-resource-accounts.md) vedere Gestire gli account delle risorse in Teams. <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Quando si assegna un numero di telefono a un operatore automatico, in senso stretto lo si assegna all'account della risorsa associato a tale operatore automatico. In questo modo è possibile fare in modo che più numeri di telefono accedono a un operatore automatico. Il più delle volte, un account delle risorse userà la licenza utente virtuale sistema telefonico a costo zero. Questa licenza fornisce funzionalità sistema telefonico ai numeri di telefono a livello aziendale e consente di creare operatori automatici e code di chiamata.

> [!NOTE]
> I numeri di servizio Instradamento diretto per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti di Microsoft Teams e gli agenti di chiamata.

   > [!TIP]
   > Per reindirizzare le chiamate a un operatore  o a un'opzione di menu che è un utente online con una licenza sistema telefonico, è necessario abilitare il proprio account per VoIP aziendale o assegnare piani di chiamata. Vedere [Assegnare licenze per i componenti aggiuntivi di Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md) Puoi anche utilizzare Windows PowerShell. Ad esempio, esegui:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ottenere e usare numeri di servizio gratuiti per gli operatori automatici, è necessario configurare Crediti comunicazioni. A questo scopo, vedere [Che cosa sono i crediti comunicazioni?](what-are-communications-credits.md) e Configurare i crediti comunicazioni per [l'organizzazione.](set-up-communications-credits-for-your-organization.md)

    > [!IMPORTANT]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati agli operatori automatici, ma solo numeri di telefono di servizio a pagamento o numeri verdi.

- Un sistema di operatore automatico completo in genere coinvolge più operatori automatici.
- È possibile applicare più numeri di telefono agli operatori automatici entry-level.
- Gli operatori automatici non entry level o le code di chiamata nel sistema completo avranno bisogno di un numero di telefono solo se effettuano chiamate PSTN in uscita.
  
## <a name="feature-overview"></a>Panoramica delle funzionalità

### <a name="searching-for-users"></a>Ricerca di utenti

Chiama per nome è una caratteristica di un operatore automatico noto anche come ricerca nella directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte del tastierino del telefono (DTMF) per immettere un nome completo o parziale per cercare nell'elenco aziendale, individuare la persona e quindi trasferire la chiamata. Gli utenti che desideri trovare e raggiungere usando Chiama per nome non devono avere un numero di telefono o avere piani di chiamata assegnati, ma devono avere una licenza Sistema telefonico se sono utenti online o VoIP aziendale abilitati per gli utenti di **Skype for Business Server.** La chiamata per nome sarà anche in grado di trovare e trasferire chiamate a utenti di Microsoft Teams ospitati in diversi paesi o aree geografiche per organizzazioni multi-nazionali. Dati i prerequisiti necessari, è possibile abilitare in modo esplicito La chiamata in base al nome in un operatore automatico.

Chiama per interno è una caratteristica di un operatore automatico che fa anche parte della ricerca nella directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte del tastierino del telefono (DTMF) per immettere l'estensione del telefono dell'utente che sta cercando di raggiungere e quindi trasferire la chiamata. Gli utenti che desideri trovare e raggiungere usando Chiama per interno non devono avere un numero di telefono o avere piani di chiamata assegnati, ma devono avere una licenza Sistema telefonico se sono utenti online o VoIP aziendale abilitati per gli utenti di **Skype for Business Server.** Sarà anche necessario disporre di un piano di chiamata configurato in modo appropriato per gli utenti. La chiamata per interno sarà anche in grado di trovare e trasferire chiamate a utenti di Microsoft Teams ospitati in diversi paesi o aree geografiche per organizzazioni multi-nazionali. Dati i prerequisiti necessari, è possibile abilitare esplicitamente La chiamata per interno in un operatore automatico.

#### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Non ci sono limiti al numero di utenti di Active Directory che possono eseguire chiamate per nome e chiamate per interno quando un chiamante cerca una persona specifica. Un chiamante può immettere nomi parziali o completi (Nome + Cognome e anche Cognome + Nome), ma richiede il numero di interno completo. La dimensione massima dell'elenco dei nomi che un singolo operatore automatico può supportare con il riconoscimento vocale è di 80.000 utenti.
  
|Tipo di ingresso|Formato di ricerca|Numero massimo di utenti di un'organizzazione|
|:-----|:-----|:-----|
|DTMF (immissione con tastiera) |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome |Nessun limite  |
|Voce (ingresso vocale) |Nome  <br/> Cognome  <br/> Nome + Cognome  <br/> Cognome + Nome  | 80.000 utenti |

> [!NOTE]
> Se si usa Chiama per nome con il riconoscimento vocale, ma Active Directory dell'organizzazione è più grande di 80.000 utenti e non è stato limitato l'ambito di Chiamata per nome usando la funzionalità Ambito di chiamata, La chiamata per nome continuerà a funzionare per i chiamanti usando un tastierino del telefono e gli input vocali saranno disponibili per tutti gli altri scenari. È possibile utilizzare la funzione Ambito di chiamata per limitare i nomi raggiungibili modificando l'ambito di Chiamata per nome per un particolare operatore automatico.
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Chiamata per nome - Immissione con tastiera (DTMF)

Le persone che chiamano possono usare Chiama per nome per raggiungere gli utenti specificando il nome completo o parziale della persona che stanno cercando di raggiungere. Quando si digita il nome, è possibile usare diversi formati.

Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando immettono il nome, gli verrà chiesto di terminare l'immissione del tastierino con il tasto #. Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
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

Gli utenti possono cercare altri utenti nell'organizzazione con la voce (riconoscimento vocale). Possono anche raggiungere chiunque in Active Directory pronunciando il nome della persona che stanno cercando di individuare. L'uso di input vocali consente di riconoscere i nomi in vari formati, tra cui Nome, Cognome, Nome + Cognome o Cognome + Nome.
  
È possibile abilitare il riconoscimento vocale per un operatore automatico, ma la voce del tastierino del telefono (DTMF) non è disabilitata. L'immissione del tastierino del telefono può essere usata in qualsiasi momento, anche se il riconoscimento vocale è abilitato sull'operatore automatico.
  
Come per la voce del tastierino del telefono, se vengono trovati più nomi, la persona che chiama sente un elenco di nomi tra cui selezionare.
  
I chiamanti possono pronunciare nomi nei formati seguenti:
  
|Nome con riconoscimento vocale|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa |Amos Marble |Amos Marble |
|Cognome + Nome |Completa  |Marble Amos |Amos Marble |
|Nome |Completa |Amos |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones |
|Cognome |Completa |Marble |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble |

> [!NOTE]
> Il nome di un nuovo utente potrebbe richiedere fino a 36 ore per essere elencato nella directory per Chiamata per nome con riconoscimento vocale a causa di un ritardo nella replica di Active Directory.
  
### <a name="language-support"></a>Supporto della lingua

Le lingue seguenti sono disponibili per la sintesi vocale usata con le richieste in uscita:
  
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

L'input di riconoscimento vocale per gli operatori automatici è disponibile nelle lingue seguenti:
  
|A-F|F-Z|
|:-----|:-----|
|Cinese (ZH)  |Francese (FR)  |
|Inglese (AU)  |Tedesco (DE)  |
|Inglese (CA)  |Italiano (IT)  |
|Inglese (IN)  |Giapponese (JP)  |
|Inglese (UK)  |Portoghese (BR)  |
|Inglese (US)  |Spagnolo (ES)  |
|Francese (CA)   |Spagnolo (MX)  |

I comandi vocali seguenti sono disponibili nelle 14 lingue supportate per il riconoscimento vocale:
  
|Comando vocale| Corrisponde a |
|:-----|:-----|
|Sì | Premere 1 per Sì. |
|No | Premere 2 per No. |
|Ripeti |Ripete l'elenco di opzioni. Premere * sul tastierino numerico per ripetere l'elenco di opzioni. |
|Operatore | Premere 0 per "Operatore" |
|Menu principale  |Porta il chiamante al menu principale dell'operatore automatico. |
|Zero | Premere 0 (per impostazione predefinita, uguale a "Operatore").|
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

Facoltativamente, un operatore automatico può essere impostato in modo da offrire a un chiamante una selezione per parlare con un operatore umano.
  
Il tasto 0 e il comando vocale "Operatore" indirizzano la chiamata all'operatore designato per impostazione predefinita. Questo è il caso per tutte le lingue supportate per il riconoscimento vocale. È anche possibile usare **Imposta opzioni del menu** per impostare un valore personalizzato per l'operatore.
  
L'operatore può essere impostato su:
  
- Un utente di Microsoft Teams o un utente di Skype for Business Server VoIP aziendale abilitato.
- Un altro operatore automatico configurato per l'organizzazione.
- Una coda di chiamata in corso configurata nell'organizzazione. Per altre informazioni sulle code di chiamata, vedere [Creare una coda di chiamata cloud.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

### <a name="business-hours-and-call-handling"></a>Orario di ufficio e gestione delle chiamate

È possibile impostare l'orario di ufficio per ogni operatore automatico. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. L'orario di ufficio può essere impostato con interruzioni di orario durante il giorno e tutte le ore non impostate come ore lavorative vengono considerate dopo l'orario. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e diversi messaggi di saluto (facoltativi) per l'orario di ufficio e le ore successive.
  
Ogni operatore automatico ha diverse opzioni di gestione delle chiamate possibili:
  
- La chiamata può disconnettersi dopo la riproduzione di un messaggio di saluto.
- È possibile anche:
  - Reindirizzare la chiamata a un  utente di Microsoft Teams che ha una licenza sistema telefonico abilitata VoIP aziendale o a cui sono assegnati piani per chiamate. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per farlo, scegli una **Persona nell'azienda** che riceverà le chiamate inoltrate direttamente alla segreteria telefonica.

  - Reindirizzare la chiamata a una coda di chiamata. Per altre informazioni sulle code di chiamata, vedere [Creare una coda di chiamata cloud.](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

  - Reindirizzare la chiamata a un altro operatore automatico.

Queste opzioni vengono espresse al chiamante dall'operatore automatico quando riproduce le istruzioni del menu. Ad esempio: "Premere 1 per i servizi commerciali, premere 2 per l'assistenza. Per parlare con l'operatore, premere 0 in qualsiasi momento".

### <a name="set-menu-options"></a>Impostare le opzioni del menu

Gli operatori automatici cloud consentono di creare istruzioni di menu ("Premere 1 per Vendite, Premere 2 per i servizi") e configurare le opzioni di menu per instradare le chiamate in base alle selezioni degli utenti. Le opzioni di menu per un operatore automatico consentono a un'organizzazione di fornire una serie di opzioni che guidano i chiamanti verso la destinazione più velocemente, senza affidarsi a un operatore umano per gestire le chiamate in arrivo. Le richieste di menu possono essere create usando la sintesi vocale (prompt generati dal sistema) o caricando un file audio registrato. Il riconoscimento vocale accetta i comandi vocali per la navigazione senza mani, ma le persone che chiamano possono anche usare il tastierino del telefono per spostarsi tra i menu.
  
I tasti da 0 a 9 possono essere assegnati ai tasti di composizione in un operatore automatico usando l'interfaccia di amministrazione di Skype for Business. Possono essere create serie di opzioni di menu diverse per l'orario di ufficio e l'orario di chiusura, e si può attivare o disattivare Chiamata per nome nelle **Opzioni di menu**. I tasti possono essere mappati per trasferire le chiamate a:
  
- Un operatore, mappato al tasto 0 per impostazione predefinita. Tuttavia, può essere riassegnato a qualsiasi altro tasto o rimosso dal menu.
- Una coda di chiamata.
- Un altro operatore automatico. È possibile configurare i menu a più livelli puntando un'opzione **di menu** in un operatore automatico a un altro operatore automatico con un proprio set di opzioni di menu, denominato operatore automatico "annidato".
- Un utente di Microsoft Teams con **una** licenza sistema telefonico abilitata VoIP aziendale o con Piani di chiamata assegnati. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per farlo, scegli una **Persona nell'azienda** che riceverà le chiamate inoltrate direttamente alla segreteria telefonica.
  
Il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale se il riconoscimento vocale è stato abilitato. Ad esempio, i chiamanti possono pronunciare "Uno" per selezionare l'opzione di menu mappata al tasto 1 oppure pronunciare "Vendite" per selezionare la stessa opzione di menu denominata "Vendite".
  
Per configurare un operatore automatico e le opzioni del menu, vai [a Configurare un operatore automatico cloud.](create-a-phone-system-auto-attendant.md)
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Assegnazione di numeri di telefono a un operatore automatico

È possibile assegnare un numero di servizio Microsoft, un numero di instradamento diretto o un numero ibrido all'account delle risorse collegate dell'operatore automatico (o a più account delle risorse se si desiderano più numeri di telefono). Per [altre informazioni, vedere Pianificare il routing](direct-routing-plan.md) diretto.

Per assegnare un numero di servizio, è necessario ottenere o convertire i numeri di servizio a pedaggio o a numero verde esistenti. Una volta che si ottengono i numeri di telefono a numero verde o a numero verde, questi vengono visualizzati nell'interfaccia di amministrazione di **Skype for Business** Numeri  >  **di** telefono  >  **vocali.** **Tipo di** numero è **elencato come Servizio - Numero verde**. Per ottenere i numeri di servizio, vedere Ottenere i numeri di telefono di servizio per [Skype for Business](./getting-service-phone-numbers.md) e Microsoft Teams oppure, se si vuole trasferire e il numero di servizio esistente, vedere Trasferire numeri di telefono in [Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
  
> [!NOTE]
> Se ci si trova al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft Teams per ottenere i numeri di servizio. Vai [a Gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per vedere come farlo.
  
## <a name="related-topics"></a>Argomenti correlati

[Vantaggi offerti dal Sistema telefonico](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](./getting-service-phone-numbers.md)

[Disponibilità di Audioconferenza e Piani per chiamate per Paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)