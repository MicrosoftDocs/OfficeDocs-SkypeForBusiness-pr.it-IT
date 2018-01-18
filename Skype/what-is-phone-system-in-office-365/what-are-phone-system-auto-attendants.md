---
title: Che cosa sono gli operatori automatici di sistema telefonico?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Informazioni su come utilizzarle e quali sono gli operatori automatici di sistema telefonico in (Cloud PBX). '
ms.openlocfilehash: 4208e152661cb322aaea804c185dd09be86b606d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="what-are-phone-system-auto-attendants"></a>Che cosa sono gli operatori automatici di sistema telefonico?

Il sistema telefonico in Office 365 gli operatori automatici possono essere utilizzati per creare un sistema di menu per l'organizzazione che consente ai chiamanti interni ed esterni spostarsi in un sistema di menu per individuare ed effettuare o trasferire le chiamate per gli utenti della società o reparti all'interno dell'organizzazione.
  
Quando si chiama persone, sono disponibili con una serie di istruzioni vocali che consentono di effettuare una chiamata a un utente oppure individuare un utente all'interno dell'organizzazione e quindi effettuare una chiamata a tale utente. Un operatore automatico è una serie di istruzioni vocali o un file audio riprodotto anziché un operatore per le chiamate a un'organizzazione. Un operatore automatico consente ai chiamanti spostarsi all'interno del sistema di menu, effettuare chiamate, o individuare gli utenti utilizzando una tastiera del telefono (multifrequenza DTMF) o segreteria telefonica gli input utilizzando il riconoscimento vocale. 
  
Per configurare un operatore automatico per il sistema telefonico in Office 365, vedere [configurare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).
  
Un operatore automatico di sistema telefonico presenta le caratteristiche seguenti:
  
- Può fornire messaggi di saluto informativi o aziendali.
    
- Può offrire menu aziendali personalizzati. Puoi personalizzare questi menu per disporre di più di un livello.
    
- Vengono forniti ricerca nella directory che consente agli utenti che chiamano di ricerca nella directory dell'organizzazione per un nome.
    
- Consente un utente che chiama il numero di raggiungere o lasciare un messaggio di una persona all'interno dell'organizzazione.
    
## <a name="getting-started"></a>Guida introduttiva

Per iniziare a utilizzare gli operatori automatici, è importante ricordare quanto segue.
  
- L'organizzazione deve disporre (almeno) una licenza Enterprise E3 plus **Sistema telefonico** o una licenza Enterprise E5. Il numero di licenze utente **Sistema telefonico** assegnati impatti il numero del servizio di numeri che è disponibile da utilizzare per gli operatori automatici. Il numero di operatori automatici, che è possibile avere dipende le licenze numeri **Sistema telefonico** e **Audioconferenza** che sono assegnate all'interno dell'organizzazione. Per ulteriori informazioni sulle licenze, visitare [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Per reindirizzare le chiamate a un operatore o un'opzione di menu è un utente in linea con una licenza di **Sistema telefonico** , sarà necessario abilitati per Enterprise Voice o assegnarvi prevede la chiamata. Vedere[Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). È inoltre possibile utilizzare Windows PowerShell. Ad esempio eseguire:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per ottenere e utilizzare numeri verdi assistenza per il operatori automatici, è necessario impostare i titoli di coda di comunicazioni. A tale scopo, vedere [che cosa sono i titoli di coda Communications?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) e [impostare i titoli di coda di comunicazione per l'organizzazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati agli operatori automatici, ma solo numeri di telefono di servizio a pagamento o numeri verdi. 
  
## <a name="feature-overview"></a>Panoramica delle funzionalità

### <a name="dial-by-name"></a>Chiamata per nome

Accesso esterno in base al nome è una funzionalità di un operatore automatico è noto come ricerca nella directory. Consente di chiamare l'operatore automatico di utilizzare vocale (riconoscimento vocale) o il tastierino numerico del telefono (multifrequenza DTMF) per immettere un nome completo o parziale eseguire ricerche nella directory aziendale, individuare la persona, e quindi trasferire la chiamata a tali persone. Se si dispone di Skype per gli utenti aziendali Online, **non è necessari disporre di un numero di telefono o dispone prevede la chiamata a essi assegnate, ma devono avere una licenza di sistema telefonico** affinché possano essere raggiungibili durante la ricerca con accesso esterno in base al nome. Accesso esterno in base al nome anche sarà in grado di trovare e trasferire le chiamate a Skype per Business Online gli utenti sono ospitati in diversi paesi o aree per le organizzazioni con più nazionali.
  
> [!CAUTION]
> Distribuzioni in locale di utenti di Lync Server 2010 non sarà disponibile nella directory quando un utente cerca di essi. 
  
### <a name="maximum-directory-size"></a>Dimensione massima dell'elenco

Non esiste alcun limite dimensioni Active Directory per il quale telefonica in base al nome è supportata quando si utilizza il tastierino numerico del telefono per la ricerca per l'immissione parziali o completi nomi (FirstName, LastName e inoltre LastName + FirstName). Dimensioni dell'elenco limite massimo di caratteri che un operatore automatico singolo può supportare tramite il riconoscimento nome con il riconoscimento vocale sono tuttavia 80.000 utenti.
  
||||
|:-----|:-----|:-----|
|**Tipo di ingresso** <br/> |**Formato di ricerca** <br/> |**Numero massimo di utenti di un'organizzazione** <br/> |
|DTMF (immissione con tastiera)  <br/> |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome  <br/> |Nessun limite fisso  <br/> |
|Voce (ingresso vocale)  <br/> |FirstName  <br/> LastName  <br/> Nome + Cognome  <br/> Cognome + Nome  <br/> |80.000 utenti  <br/> |
   
> [!NOTE]
> Se si utilizza connessione in base al nome con il riconoscimento vocale è maggiore di 80.000 utenti riconoscimento, ma Active Directory dell'organizzazione e non solo l'ambito della connessione in base al nome di utilizzo della funzionalità ambito del Dial, accesso esterno in base al nome continuerà a funzionare per i chiamanti utilizzando una tastiera del telefono , e gli input vocali sarà disponibili per tutti gli altri scenari. È possibile utilizzare la funzionalità di ambito del Dial di circoscrivere i nomi siano raggiungibili modificando l'ambito della connessione in base al nome di un operatore automatico specifico. 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Chiamata per nome - Immissione con tastiera (DTMF)

Utenti effettuano è possono utilizzare connessioni in base al nome di raggiungere gli utenti specificando il nome completo o parziale della persona che sta tentando di contattare. Sono state che esistono diversi formati che possono essere utilizzati quando viene immesso il nome.
  
Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando inseriscono il nome, verrà chiesto di concludere l'immissione da tastiera con il tasto # (cancelletto). Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Le persone possono cercare nomi nell'organizzazione utilizzando i seguenti formati di ricerca sulla tastiera del telefono.
  
|||||
|:-----|:-----|:-----|:-----|
|**Formato del nome** <br/> |**Tipo di ricerca** <br/> |**Esempio** <br/> |**Risultato della ricerca** <br/> |
|Nome + Cognome  <br/> |Completa  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Cognome + Nome  <br/> |Completa  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |Completa  <br/> |Amos#  <br/> |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus  <br/> |
|LastName  <br/> |Completa  <br/> |Marble#  <br/> |Premere 1 per Amos Marble  <br/> Premere 2 per Mary Marble  <br/> |
|Nome o Cognome  <br/> |Parziale  <br/> |Mar#  <br/> |Premere 1 per Mary Marble  <br/> Premere 2 per Mary Jones  <br/> Premere 3 per Amos Marcus  <br/> |
|Nome + Cognome  <br/> |Parziale  <br/> |Mar0Amos#  <br/> |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus  <br/> |
|Cognome + Nome  <br/> |Parziale  <br/> |Mar0Am#  <br/> |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus  <br/> |
   
Esistono diversi caratteri speciali che vengono utilizzati durante la ricerca di utenti che utilizzano una tastiera del telefono. Ad esempio, la persona verrà richiesto di utilizzare il tasto cancelletto (#), mentre il tasto pari a zero (0) viene utilizzato per uno spazio tra i nomi. Premendo il tasto asterisco (*) ripeterà l'elenco dei nomi di persona corrispondenti.
  
|||
|:-----|:-----|
|**Carattere speciale della tastiera del telefono** <br/> |**Cosa significa** <br/> |
|# (cancelletto)  <br/> |Carattere terminale quando si immette un nome.  <br/> |
|0 (zero)  <br/> |Spazio tra i nomi.  <br/> |
|* (asterisco)  <br/> |Ripete l'elenco dei nomi corrispondenti.  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>Chiamata per nome - Riconoscimento vocale del nome

Gli utenti possono eseguire ricerche per altri utenti dell'organizzazione utilizzando vocale (riconoscimento vocale). Possono inoltre raggiungere tutti gli utenti in Active Directory dell'azienda pronunciando il nome della persona che sta tentando di individuare. Mediante gli input vocali in grado di riconoscere i nomi in formati diversi, tra cui FirstName, LastName, FirstName, LastName o LastName + FirstName.
  
Quando si attiva il riconoscimento vocale per un operatore automatico, voce tastierino telefono (multifrequenza DTMF) sarà disabilitato, in modo che consente di entrambi i tipi di input. Voce tastierino telefono non può essere disattivata e può essere utilizzato in qualsiasi momento, anche se il riconoscimento vocale è stato attivato l'operatore automatico.
  
Come avviene per l'immissione da tastiera, se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Il chiamante può pronunciare i nomi nei seguenti formati.
  
|||||
|:-----|:-----|:-----|:-----|
|**Nome con il riconoscimento vocale** <br/> |**Tipo di ricerca** <br/> |**Esempio** <br/> |**Risultato della ricerca** <br/> |
|Nome + Cognome  <br/> |Completa  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Cognome + Nome  <br/> |Completa  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|FirstName  <br/> |Completa  <br/> |Amos  <br/> |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones  <br/> |
|LastName  <br/> |Completa  <br/> |Marble  <br/> |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble  <br/> |
   
> [!NOTE]
> Potrebbe richiedere fino a 36 ore a un nuovo utente del proprio nome elencati nella directory di accesso esterno in base al nome con il riconoscimento vocale. 
  
### <a name="language-support"></a>Lingue supportate

Sono disponibili le seguenti lingue per il sintetizzatore vocale.
  
||||
|:-----|:-----|:-----|
|Arabo (EG)  <br/> |Inglese (NZ)  <br/> |Coreano (KO)  <br/> |
|Cinese (HK)  <br/> |Inglese (UK)  <br/> |Norvegese (NO)  <br/> |
|Cinese (TW)  <br/> |Inglese (US)  <br/> |Polacco (PL)  <br/> |
|Cinese (ZH)  <br/> |Finlandese (FI)  <br/> |Portoghese (BR)  <br/> |
|Danese (DA)  <br/> |Francese (CA)  <br/> |Portoghese (PT)  <br/> |
|Olandese (NL)  <br/> |Francese (FR)  <br/> |Russo (RU)  <br/> |
|Inglese (AU)  <br/> |Tedesco (DE)  <br/> |Spagnolo (ES)  <br/> |
|Inglese (CA)  <br/> |Italiano (IT)  <br/> |Spagnolo (MX)  <br/> |
|Inglese (IN)  <br/> |Giapponese (JP)  <br/> |Svedese (SV)  <br/> |
   
Il riconoscimento vocale per gli operatori automatici è disponibile nelle seguenti lingue.
  
|||
|:-----|:-----|
|Cinese (ZH)  <br/> |Francese (FR)  <br/> |
|Inglese (AU)  <br/> |Tedesco (DE)  <br/> |
|Inglese (CA)  <br/> |Italiano (IT)  <br/> |
|Inglese (IN)  <br/> |Giapponese (JP)  <br/> |
|Inglese (UK)  <br/> |Portoghese (BR)  <br/> |
|Inglese (US)  <br/> |Spagnolo (ES)  <br/> |
|Francese (CA)  <br/> |Spagnolo (MX)  <br/> |
   
I seguenti comandi vocali sono disponibili nelle quattordici (14) lingue supportate per il riconoscimento vocale.
  
|||
|:-----|:-----|
|**Comando vocale** <br/> |**Significato** <br/> |
|Sì  <br/> |Sì - corrisponde a premere 1 per Sì.  <br/> |
|No  <br/> |No - corrisponde a premere 2 per No.  <br/> |
|Ripeti  <br/> |Ripete l'elenco di opzioni - corrisponde a premere * per ripetere l'elenco di opzioni.  <br/> |
|Operatore  <br/> |Chiama operatore - corrisponde a premere 0 per "Operatore".  <br/> |
|Menu principale  <br/> |Porta il chiamante al menu principale dell'operatore automatico.  <br/> |
|Zero  <br/> |Corrisponde a premere 0 (per impostazione predefinita, ha la stessa funzione di "Operatore").  <br/> |
|Uno  <br/> |Corrisponde a premere 1.  <br/> |
|Due  <br/> |Corrisponde a premere 2.  <br/> |
|Tre  <br/> |Corrisponde a premere 3.  <br/> |
|Quattro  <br/> |Corrisponde a premere 4.  <br/> |
|Cinque  <br/> |Corrisponde a premere 5.  <br/> |
|Sei  <br/> |Corrisponde a premere 6.  <br/> |
|Sette  <br/> |Corrisponde a premere 7.  <br/> |
|Otto  <br/> |Corrisponde a premere 8.  <br/> |
|Nove  <br/> |Corrisponde a premere 9.  <br/> |
   
### <a name="using-the-operator-option"></a>Uso dell'opzione operatore

Usare l'opzione operatore di un operatore automatico è un'impostazione facoltativa che dà al chiamante la possibilità di parlare con una persona dal vivo.
  
Il tasto 0 e il comando vocale "Operatore" (in tutte le lingue supportate per il riconoscimento vocale) sono assegnati alla funzione operatore per impostazione predefinita.
  
> [!NOTE]
> È possibile impostare il pulsante che viene eseguito per l' **operatore** in una chiave diversa utilizzando **Le opzioni di Menu**. 
  
Puoi impostare la funzione Operatore a una delle persone seguenti.
  
- Skype per utenti Business Online che dispone di un **Sistema telefonico** licenza che sia abilitato per Enterprise Voice o piani di chiamata assegnate loro. È possibile configurarlo in modo che la persona chiamata in può essere inviata alla segreteria telefonica. A tale scopo, selezionare una **persona nell'azienda** e impostare le chiamate della persona a essere automaticamente inoltrata direttamente alla segreteria telefonica.
    
    > [!NOTE]
    > Gli utenti ospitati in locale con Lync Server 2010 non può essere utilizzato come operatore di. 
  
- Un altro operatore automatico configurato per l'organizzazione.
    
- Qualsiasi coda di chiamata esistente in cui è installato nell'organizzazione. Per ulteriori informazioni sulle code di chiamata, vedere [creare una coda di chiamata di sistema telefonico](create-a-phone-system-call-queue.md).
    
### <a name="business-hours-and-call-handling"></a>Orario di ufficio e gestione delle chiamate

Orari d'ufficio vengono impostati su ogni operatore automatico. Orario di ufficio non è impostata, tutti i giorni e tutte le ore della giornata vengono considerate orari d'ufficio perché una pianificazione 24/7 per impostazione predefinita. Orari d'ufficio possono essere impostate con interruzioni di tempo durante il giorno e tutte le ore in cui non sono impostate come orari d'ufficio sono considerati fuori orario d'ufficio. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e diversi messaggi di saluto (che sono facoltative) ed entrambi può essere impostati per l'orario di ufficio e fuori orario d'ufficio.
  
Ogni operatore automatico con le opzioni di gestione delle chiamate che possono essere impostate:
  
- È possibile far scollegare la chiamata dopo il saluto.
    
- È possibile anche:
    
  - Reindirizzare la chiamata a un Skype per utenti Business Online che dispone di una licenza di **Sistema telefonico** che sia abilitato per Enterprise Voice o piani di chiamata assegnate loro. È possibile configurarlo in modo che la persona chiamata in può essere inviata alla segreteria telefonica. A tale scopo, selezionare una **persona nell'azienda** e impostare le chiamate della persona a essere automaticamente inoltrata direttamente alla segreteria telefonica.
    
    > [!NOTE]
    > Gli utenti ospitati in locale con Lync Server 2010 non sono supportati. 
  
  - Reindirizzare la chiamata a una coda di chiamata. Per ulteriori informazioni sulle code di chiamata, vedere [creare una coda di chiamata di sistema telefonico](create-a-phone-system-call-queue.md).
    
  - Reindirizzare la chiamata a un altro operatore automatico che sono state impostate.
    
- Creare opzioni di menu e riprodurre un messaggio menu per il chiamante. Ad esempio: "Premere 1 per i servizi commerciali, premere 2 per l'assistenza. Per parlare con l'operatore, premere 0 in qualsiasi momento".
    
### <a name="menu-options"></a>Opzioni di menu

Gli operatori automatici di sistema Phone consentono di creare menu prompt ("premere 1 per le vendite, premere 2 per i servizi") e impostare le opzioni di menu per instradare le chiamate basate l'utente seleziona. Impostazione di opzioni di menu per un operatore automatico consente alle organizzazioni di fornire indicazioni interattiva per ottenere la persona per la propria destinazione più veloce, senza l'utilizzo di un operatore per gestire le chiamate in arrivo. Menu richieste possono essere create utilizzando la sintesi vocale (generato dal sistema richieste) o caricare un file audio è stato registrato. Riconoscimento vocale utilizza comandi vocali per l'esplorazione invisibile all'utente, ma utenti effettuano possono inoltre utilizzare la tastiera del telefono per spostarsi menu.
  
Tasti da 0 a 9 assegnabili a **Opzioni di Menu** in un operatore automatico con la Skype per interfaccia di amministrazione di Business. È possibile creare diversi set di opzioni del menu di orari d'ufficio e dopo le ore ed è possibile abilitare o disabilitare l'accesso esterno in base al nome nelle **Opzioni di Menu**. Per trasferire le chiamate a, è possono eseguire il mapping chiavi:
  
- Un operatore, che viene mappato alla chiave 0 per impostazione predefinita. Tuttavia, può essere nuovamente assegnato a qualsiasi altra chiave, o rimosso dal menu.
    
- Una coda di chiamata.
    
- Operatore automatico di un'altra. Menu a più livelli possono impostare indirizzando un' **Opzione di Menu** in un operatore all'operatore automatico di un'altra con il proprio set di opzioni di Menu, viene chiamato un operatore automatico "annidati".
    
- Skype per utenti Business Online che dispone di un **Sistema telefonico** licenza che sia abilitato per Enterprise Voice o piani di chiamata assegnate loro. È possibile configurarlo in modo che la persona chiamata in può essere inviata alla segreteria telefonica. A tale scopo, selezionare una **persona nell'azienda** e impostare le chiamate della persona a essere automaticamente inoltrata direttamente alla segreteria telefonica.
    
    > [!NOTE]
    > Gli utenti ospitati in locale con Lync Server 2010 non può essere utilizzato **Dal Menu opzioni**. 
  
Il nome di ogni opzione di menu diventa una parola chiave di riconoscimento vocale se è stato abilitato il riconoscimento vocale. Ad esempio, i chiamanti possono pronunciare "One" per selezionare l'opzione di menu mappato al tasto 1 o semplicemente possono pronunciare "Sales" per selezionare la stessa opzione di menu denominata "Sales".
  
Per configurare un operatore automatico e le opzioni di menu, vedere [configurare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>Ottenere numeri di servizio per un operatore automatico

Prima di poter creare e configurare i operatori automatici, è necessario ottenere o trasferire un numero a tariffa esistente o un servizio verde numeri. Una volta che viene visualizzato il numero a tariffa o numeri verdi servizio, che verranno visualizzati nella **Skype per Business admin center** > **vocale** > **numeri di telefono**e **tipo di numero** elencato verrà indicato come **servizio - numero verde **. Per ottenere i numeri di servizio, vedere [Getting numeri di telefono del servizio per Skype per le aziende e team di Microsoft](getting-service-phone-numbers.md) o, se si desidera trasferimento e il numero di servizio esistente, vedere [trasferire i numeri di telefono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se si è fuori degli Stati Uniti, è possibile utilizzare Skype per interfaccia di amministrazione di Business per ottenere i numeri di servizio. Passare invece [Gestisci i numeri di telefono per l'organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) per informazioni su come eseguire questa operazione.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Modificare l'ID chiamante dell'utente sia il numero di telefono della coda di chiamata

È possibile proteggere l'identità dell'utente modificando l'ID chiamante per le chiamate in uscita a una coda di chiamata in realtà mediante la creazione di un criterio utilizzando il cmdlet **New-CallingLineIdentity** .
  
A tale scopo, eseguire:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Quindi applicare il criterio per utente utilizzando il cmdlet **Grant-CallingLineIdentity** . A tale scopo, eseguire:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

È possibile ottenere ulteriori informazioni su come apportare modifiche alle impostazioni di ID chiamante all'interno dell'organizzazione [come ID chiamante utilizzare all'interno dell'organizzazione](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="related-topics"></a>Argomenti correlati
[Ecco cosa viene visualizzato con sistema telefonico in Office 365](here-s-what-you-get-with-phone-system.md)

[Ottenere numeri di telefono del servizio per Skype per le aziende e Teams Microsoft](getting-service-phone-numbers.md)

[Disponibilità paese e alle aree per le conferenze Audio e la chiamata dei piani](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)