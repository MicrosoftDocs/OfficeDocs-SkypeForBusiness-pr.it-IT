---
title: Che cosa sono gli operatori automatici di cloud?
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
ms.openlocfilehash: e9d6da8a73333218990611bd287a852683d52f9c
ms.sourcegitcommit: 2fab6105dfc4c225de8c09ab79d9c2c273a3e4f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/10/2020
ms.locfileid: "41004771"
---
# <a name="what-are-cloud-auto-attendants"></a>Che cosa sono gli operatori automatici di cloud?

Sistema telefonico in Office 365 fornisce gli operatori automatici, che possono essere usati per consentire ai chiamanti esterni e interni di spostarsi in un sistema di menu per individuare e inserire o trasferire chiamate a utenti o reparti dell'organizzazione.
  
Un operatore automatico è il più delle volte un nodo in un sistema, dando a un chiamante una serie di richieste vocali o di file audio che sente al posto di un operatore umano. Quando gli utenti chiamano un numero associato a un operatore automatico, le loro scelte possono reindirizzare la chiamata a un utente o individuare qualcuno nell'organizzazione e quindi connettersi a tale utente. Possono esprimere le proprie scelte e interagire con il sistema di menu usando la tastiera del telefono (DTMF) o il riconoscimento vocale. Le scelte effettuate possono anche reindirizzare la chiamata a un altro operatore automatico o a una coda di chiamata.
  
Per configurare un operatore automatico per il sistema telefonico in Office 365, vedere [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).
  
Un operatore automatico cloud ha le caratteristiche seguenti:
  
- Può fornire messaggi di saluto informativi o aziendali.
- Può offrire menu aziendali personalizzati. Puoi personalizzare questi menu per disporre di più di un livello.
- Fornisce la ricerca nella directory che consente alle persone che chiamano per cercare un nome nella directory dell'organizzazione.
- Consente a un utente che chiama di raggiungere o di uscire da un messaggio per una persona dell'organizzazione.
- Supporta più lingue per le richieste, la sintesi vocale e il riconoscimento vocale.
- Supporta l'impostazione di festività e orari di ufficio.
- Supporta il trasferimento della chiamata a un operatore, ad altri utenti, alle code di chiamata e agli operatori automatici.
- Supporta la segreteria telefonica condivisa per i chiamanti per l'uscita di un messaggio per un'organizzazione.

> [!NOTE]
> Questo articolo si applica sia a Microsoft teams che a Skype for business online.

## <a name="getting-started"></a>Introduzione

Per iniziare a utilizzare gli operatori automatici, è importante ricordare quanto segue.

- Per avere un account di risorse associato, è necessario un operatore automatico. Per informazioni dettagliate sugli account delle risorse, vedere [gestire gli account delle risorse in teams](manage-resource-accounts.md) . <!-- You can either use an existing resource account or create a new resource account as you set up your auto attendant. -->
- Quando si assegna un numero di telefono a un operatore automatico, in senso stretto lo si assegna all'account delle risorse associato all'operatore automatico. In questo modo è possibile accedere a più numeri di telefono a un operatore automatico. Il più delle volte, un account di risorse utilizzerà la licenza per gli utenti virtuali del sistema telefonico senza costi. Questa licenza offre funzionalità di sistema telefonico per i numeri di telefono a livello di organizzazione e consente di creare operatori automatici e code di chiamata.

> [!NOTE]
> I numeri di servizio di routing diretto per l'operatore automatico e le code di chiamata sono supportati solo per gli utenti di Microsoft teams e gli agenti di chiamata.

   > [!TIP]
   > Per reindirizzare le chiamate a un operatore o a un'opzione di menu che è un utente online con una licenza di **sistema telefonico** , è necessario abilitare il proprio account per VoIP aziendale o assegnare loro piani di chiamata. Vedere [assegnare le licenze di Microsoft teams](assign-teams-licenses.md). Puoi anche utilizzare Windows PowerShell. Ad esempio, esegui:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ottenere e usare i numeri di servizio gratuiti per gli operatori automatici, è necessario configurare i crediti per le comunicazioni. Per eseguire questa operazione, vedere informazioni sui crediti per le [comunicazioni](what-are-communications-credits.md) e [configurare i crediti per le comunicazioni per l'organizzazione](set-up-communications-credits-for-your-organization.md).

    > [!IMPORTANT]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati agli operatori automatici, ma solo numeri di telefono di servizio a pagamento o numeri verdi.

- Un sistema di operatore automatico completo coinvolgerà in genere più operatori automatici e può richiedere solo un singolo numero di telefono assegnato per l'operatore automatico di primo livello o di entrata. Gli altri operatori automatici o le code di chiamata nel sistema completo necessitano solo di un numero di telefono se si vuole specificare più punti di ingresso nel sistema.
- È possibile applicare più di un numero di telefono a un operatore automatico associando più account di risorse a un operatore automatico.
  
## <a name="feature-overview"></a>Panoramica delle caratteristiche

### <a name="searching-for-users"></a>Ricerca di utenti

Chiamata per nome è una caratteristica di un operatore automatico noto anche come ricerca directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte del tastierino telefonico (DTMF) per immettere un nome completo o parziale nella directory della società, individuare la persona e quindi fare in modo che venga trasferita la chiamata. Gli utenti che desiderano avere individuato e raggiunto tramite chiamata in base **al nome non devono avere un numero di telefono o avere piani di chiamata assegnati, ma devono avere una licenza per il sistema telefonico se sono utenti online o VoIP aziendale abilitato per gli utenti di Skype for Business Server**. Il comando componi per nome sarà anche in grado di trovare e trasferire le chiamate agli utenti di Microsoft teams ospitati in paesi o aree geografiche diverse per organizzazioni multinazionali. In base ai prerequisiti implicati, è possibile abilitare esplicitamente la chiamata per nome in un operatore automatico.

Dial by Extension è una caratteristica di un operatore automatico che fa anche parte della ricerca nella directory. Consente alle persone che chiamano l'operatore automatico di usare la voce (riconoscimento vocale) o le risposte della tastiera del telefono (DTMF) per immettere l'estensione del telefono dell'utente che sta provando a raggiungere e quindi la chiamata viene trasferita. Gli utenti che desiderano avere individuato e raggiunto tramite dial by Extension **non devono avere un numero di telefono o avere piani di chiamata assegnati, ma devono avere una licenza per il sistema telefonico se sono utenti online o VoIP aziendale abilitato per gli utenti di Skype for Business Server**. Sarà inoltre necessario disporre di un piano di chiamata configurato in modo appropriato per gli utenti. Dial by Extension sarà anche in grado di trovare e trasferire le chiamate agli utenti di Microsoft teams ospitati in paesi o aree geografiche diverse per organizzazioni multinazionali. In base ai prerequisiti in questione, è possibile abilitare esplicitamente dial by Extension in un operatore automatico.

#### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Il numero di utenti di Active Directory per nome e dial by Extension può essere supportato quando un chiamante cerca una persona specifica. Un chiamante può immettere nomi parziali o completi (nome + cognome e cognome + nome), ma richiede il numero di interno completo. Le dimensioni massime degli elenchi di nomi che un singolo operatore automatico può supportare con il riconoscimento vocale sono gli utenti di 80.000.
  
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

#### <a name="dial-by-name---name-recognition-with-speech"></a>Chiamata per nome - Riconoscimento vocale del nome

Gli utenti possono cercare altri utenti nella propria organizzazione con la propria voce (riconoscimento vocale). Possono anche raggiungere chiunque in Active Directory dicendo il nome della persona che sta tentando di individuare. L'uso di input vocali può riconoscere i nomi in diversi formati, tra cui nome, cognome, nome + cognome o cognome + nome.
  
È possibile abilitare il riconoscimento vocale per un operatore automatico, ma la voce del tastierino telefonico (DTMF) non è disabilitata. La voce della tastiera del telefono può essere usata in qualsiasi momento anche se il riconoscimento vocale è abilitato per l'operatore automatico.
  
Come per l'immissione della tastiera del telefono, se vengono trovati più nomi, la persona che chiama sente un elenco di nomi da cui selezionare.
  
I chiamanti possono pronunciare i nomi nei formati seguenti:
  
|Nome con il riconoscimento vocale|Tipo di ricerca|Esempio|Risultato della ricerca|
|:-----|:-----|:-----|:-----|
|Nome + Cognome |Completa |Amos Marble |Amos Marble |
|Cognome + Nome |Completa  |Marble Amos |Amos Marble |
|FirstName |Completa |Amos |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones |
|LastName |Completa |Marble |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble |

> [!NOTE]
> Per un nuovo utente possono essere necessarie fino a 36 ore per avere il nome elencato nella directory per il nome della chiamata tramite il riconoscimento vocale a causa del ritardo di replica di Active Directory.
  
### <a name="language-support"></a>Supporto per le lingue

Le lingue seguenti sono disponibili per la sintesi vocale usata con le istruzioni in uscita:
  
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

L'input di riconoscimento vocale per gli operatori automatici è disponibile nelle lingue seguenti:
  
|||
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
|Ripeti |Ripete l'elenco di opzioni. Premere * sul tastierino per ripetere l'elenco di opzioni. |
|Operatore | Premere 0 per "operator" |
|Menu principale  |Porta il chiamante al menu principale dell'operatore automatico. |
|Zero | Premere 0 (per impostazione predefinita, uguale a "operator").|
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

Un operatore automatico può essere impostato facoltativamente per consentire a un chiamante una selezione di parlare con un operatore umano.
  
Il tasto 0 e il comando vocale "operator" indirizzano la chiamata all'operatore designato per impostazione predefinita. Questo è il caso di tutte le lingue supportate per il riconoscimento vocale. Puoi anche usare le **Opzioni di menu imposta** per impostare un valore personalizzato per l'operatore.
  
L'operatore può essere impostato su:
  
- Un utente di Microsoft teams o un utente di Skype for Business Server abilitato per VoIP aziendale.
- Un altro operatore automatico configurato per l'organizzazione.
- Una coda di chiamata in corso configurata nell'organizzazione. Per altre informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

### <a name="business-hours-and-call-handling"></a>Orario di ufficio e gestione delle chiamate

Gli orari di ufficio possono essere impostati in ogni operatore automatico. Se l'orario di ufficio non è impostato, tutti i giorni e tutte le ore del giorno sono considerati orario di ufficio perché il programma 24/7 è impostato come predefinito. Gli orari di ufficio possono essere impostati con interruzioni nel tempo durante il giorno e tutte le ore che non sono impostate come orari di ufficio sono considerate after-hours. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto diversi (facoltativi) per le ore lavorative e le ore successive.
  
Ogni operatore automatico ha diverse possibili opzioni di gestione delle chiamate:
  
- La chiamata può essere disconnessa dopo la riproduzione di un saluto.
- È possibile anche:
  - Reindirizza la chiamata a un utente di Microsoft teams che dispone di una licenza per il **sistema telefonico** con funzionalità VoIP aziendale o con piani di chiamata assegnati. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per farlo, scegli una **Persona nell'azienda** che riceverà le chiamate inoltrate direttamente alla segreteria telefonica.

  - Reindirizzare la chiamata a una coda di chiamata. Per altre informazioni sulle code di chiamata, vedere [creare una coda di chiamata cloud](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

  - Reindirizza la chiamata a un altro operatore automatico.

Queste opzioni vengono espresse al chiamante dall'operatore automatico quando riproduce le richieste di menu. Ad esempio: "Premere 1 per i servizi commerciali, premere 2 per l'assistenza. Per parlare con l'operatore, premere 0 in qualsiasi momento".

### <a name="set-menu-options"></a>Impostare le opzioni del menu

Gli operatori automatici cloud consentono di creare prompt dei menu ("premere 1 per le vendite, premere 2 per i servizi") e configurare le opzioni del menu per instradare le chiamate in base alle selezioni degli utenti. Le opzioni di menu per un operatore automatico consentono a un'organizzazione di specificare una serie di scelte che guidano i chiamanti a destinazione più rapidamente, senza affidarsi a un operatore umano per gestire le chiamate in arrivo. Le richieste di menu possono essere create usando la sintesi vocale (prompt generati dal sistema) o caricando un file audio registrato. Il riconoscimento vocale accetta i comandi vocali per la navigazione senza mani, ma le persone che chiamano possono anche usare la tastiera del telefono per spostarsi tra i menu.
  
I tasti da 0 a 9 possono essere assegnati a tasti di scelta rapida in un operatore automatico usando l'interfaccia di amministrazione di Skype for business. Possono essere create serie di opzioni di menu diverse per l'orario di ufficio e l'orario di chiusura, e si può attivare o disattivare Chiamata per nome nelle **Opzioni di menu**. I tasti possono essere mappati per trasferire le chiamate a:
  
- Un operatore, mappato al tasto 0 per impostazione predefinita. Tuttavia, può essere riassegnato a qualsiasi altro tasto o rimosso dal menu.
- Una coda di chiamata.
- Un altro operatore automatico. I menu multilivello possono essere configurati puntando un' **opzione di menu** in un operatore automatico a un altro operatore automatico con il proprio set di opzioni di menu, che si chiama operatore automatico "annidato".
- Un utente di Microsoft teams che dispone di una licenza di **sistema telefonico** con VoIP aziendale o con piani di chiamata assegnati. Puoi impostarla in modo che la persona che chiama possa essere passata alla segreteria telefonica. Per farlo, scegli una **Persona nell'azienda** che riceverà le chiamate inoltrate direttamente alla segreteria telefonica.
  
Il nome di ogni opzione del menu diventa una parola chiave per il riconoscimento vocale se il riconoscimento vocale è stato abilitato. Ad esempio, i chiamanti possono pronunciare "uno" per selezionare l'opzione di menu mappata con il tasto 1 oppure dire "vendite" per selezionare la stessa opzione di menu denominata "Sales".
  
Per configurare un operatore automatico e le opzioni di menu, [impostare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).
  
### <a name="assigning-phone-numbers-for-an-auto-attendant"></a>Assegnazione di numeri di telefono per un operatore automatico

È possibile assegnare un numero di servizio Microsoft, un numero di routing diretto o un numero ibrido all'account della risorsa collegata dell'operatore automatico (o a più account di risorse se si desidera più di un numero di telefono). Vedere [pianificare il routing diretto](direct-routing-plan.md) per ulteriori dettagli.

Per assegnare un numero di servizio, è necessario ottenere o trasferire i numeri di servizio a pagamento o a pedaggio esistenti. Una volta ottenuto il pedaggio o i numeri di telefono del servizio gratuito, questi vengono visualizzati nei**numeri di telefono**della**voce** > dell'interfaccia di >  **amministrazione di Skype for business**. Il **tipo di numero** è elencato come **servizio a pagamento gratuito**. Per ottenere i numeri di servizio, vedere [recupero di numeri di telefono per Skype for business e Microsoft teams](/microsoftteams/getting-service-phone-numbers) oppure, se si vuole trasferire e numero di servizio esistente, vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).
  
> [!NOTE]
> Se si è al di fuori degli Stati Uniti, non è possibile usare l'interfaccia di amministrazione di Microsoft teams per ottenere i numeri di servizio. È invece necessario [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per vedere come eseguire questa operazione.
  
## <a name="related-topics"></a>Argomenti correlati

[Ecco cosa offre il Sistema telefonico in Office 365](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di servizio per Skype for Business e Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Disponibilità di Audioconferenza e Piani per chiamate per paese e area geografica](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[Esempio per piccole imprese - Impostare un operatore automatico](/microsoftteams/tutorial-org-aa)
