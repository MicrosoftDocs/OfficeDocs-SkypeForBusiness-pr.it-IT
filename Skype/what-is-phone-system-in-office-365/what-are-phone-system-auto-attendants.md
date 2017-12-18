---
title: "Quali sono gli operatori automatici di sistema telefonico?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
description: "Learn what Phone System (Cloud PBX) auto attendents are and how to use them. "
---

# Quali sono gli operatori automatici di sistema telefonico?

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
Sistema telefonico in Office 365 gli operatori automatici di possono essere usati per creare un sistema di menu per l'organizzazione che consente ai chiamanti interni ed esterni spostarsi da un sistema di menu per individuare e inserire o trasferire le chiamate per gli utenti della società o reparti all'interno dell'organizzazione.
  
Quando si chiamano persone, viene visualizzata con una serie di istruzioni vocali che consentono di effettuare una chiamata a un utente o individuare un utente all'interno dell'organizzazione e quindi effettuare una chiamata a tale utente. Un operatore automatico è una serie di istruzioni vocali o un file audio riprodotto anziché un operatore umano quando chiamano un'organizzazione. Un operatore automatico consente ai chiamanti spostarsi all'interno del sistema di menu, effettuare chiamate, o individuare utenti utilizzando una tastiera del telefono (DTMF) o vocali input riconoscimento vocale.
  
Per impostare un operatore automatico per il sistema telefonico in Office 365 passare [Impostare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).
  
Un operatore automatico di sistema telefonico è le caratteristiche seguenti:
  
- Può fornire messaggi di saluto informativi o aziendali.
    
- Può offrire menu aziendali personalizzati. Puoi personalizzare questi menu per disporre di più di un livello.
    
- Fornisce ricerca nella directory che consente agli utenti che accedono tramite telefono per ricerche nella directory dell'organizzazione per un nome.
    
- In questo modo chi chiama per raggiungere o uscire da un messaggio per un utente all'interno dell'organizzazione.
    
## Guida introduttiva

Per iniziare a utilizzare gli operatori automatici, è importante ricordare quanto segue.
  
- L'organizzazione deve avere (almeno) una licenza Enterprise E3 più **Sistema telefonico** o una licenza E5 Enterprise. Il numero di licenze utente **Sistema telefonico** assegnati impatto il numero del servizio di numeri che è disponibile da utilizzare per gli operatori automatici. Il numero di operatori automatici che è possibile creare dipende licenze **Sistema telefonico** e **Conferenze Audio** numerare assegnato all'interno dell'organizzazione. Per ulteriori informazioni sulle licenze, passare[Skype for Business e Teams Microsoft componente aggiuntivo per le licenze](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Per reindirizzare le chiamate a un operatore o un'opzione di menu che è un utente in linea con una licenza di **Sistema telefonico**, sarà necessario abilitarle per Enterprise Voice o assegnarvi chiamata plan di messaggistica unificata. Vedere [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). È anche possibile utilizzare Windows PowerShell. Ad esempio eseguire:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Per accedere e utilizzare numeri verdi assistenza per gli operatori automatici, è necessario configurare le comunicazioni crediti. Per eseguire questa operazione, vedere [Cosa sono i Crediti comunicazioni?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) e[Configurare i Crediti comunicazioni per la propria organizzazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > I numeri di telefono di utenti (abbonati) non possono essere assegnati agli operatori automatici, ma solo numeri di telefono di servizio a pagamento o numeri verdi. 
  
## Panoramica delle funzionalità

### Chiamata per nome

Connessione in base al nome è una funzionalità di un operatore automatico noto come ricerca nella directory. In questo modo le persone che accedono tramite telefono per l'operatore automatico di utilizzare vocali (riconoscimento vocale) o la tastiera del telefono (DTMF) per immettere un nome completo o parziale ricerche nella directory aziendale, individuare la persona e quindi hanno trasferire la chiamata a tali. Se si dispone di Skype per Business Online gli utenti, **non è necessari disporre di un numero di telefono o hanno la chiamata plan di messaggistica unificata loro assegnate, ma devono avere una licenza di **Sistema telefonico**** per garantirne la raggiungibile quando eseguono una ricerca con accesso esterno per nome. Anche saranno in grado di individuare e trasferire le chiamate ad Skype per Business Online utenti sono ospitati in paesi diversi per le organizzazioni multinazionali Dial in base al nome.
  
> [!CAUTION]
> Distribuzioni locali di utenti di Lync Server 2010 non elencate nella directory quando un utente cerca. 
  
### Dimensione massima dell'elenco

Nessun limite è la dimensione di Active Directory per il quale connessione in base al nome è supportato quando si usa la tastiera del telefono per eseguire una ricerca per l'immissione di nomi completi o parziali (nome, cognome e anche cognome + nome). Tuttavia, le dimensioni di elenco limite massimo di caratteri che un operatore automatico singola supportino utilizzo del riconoscimento nome con il riconoscimento vocale sono 80.000 utenti.
  
||||
|:-----|:-----|:-----|
|**Tipo di ingresso** <br/> |**Formato di ricerca** <br/> |**Numero massimo di utenti di un'organizzazione** <br/> |
|DTMF (immissione con tastiera)  <br/> |Parziale  <br/> Nome + Cognome  <br/> Cognome + Nome  <br/> |Nessun limite fisso  <br/> |
|Voce (ingresso vocale)  <br/> |Nome  <br/> Cognome  <br/> Nome + Cognome  <br/> Cognome + Nome  <br/> |80.000 utenti  <br/> |
   
> [!NOTE]
> Se si utilizza una connessione in base al nome con il riconoscimento vocale è maggiore di 80.000 utenti riconoscimento ma Active Directory dell'organizzazione e non sia stato limitato l'ambito della connessione per nome utilizzando funzionalità di connessione ambito, connessione in base al nome continuerà a funzionare per i chiamanti con una tastiera del telefono , e gli input vocali sarà disponibili per tutti gli altri scenari. È possibile utilizzare la funzionalità di connessione ambito per limitare i nomi raggiungibili modificando l'ambito della connessione in base al nome di un operatore automatico specifico. 
  
### Chiamata per nome - Immissione con tastiera (DTMF)

Utenti effettuano è possono utilizzare connessioni in base al nome di raggiungere gli utenti specificando sia il nome completo o parziale della persona che sta tentando di raggiungere. Il vantaggio è che ci sono diversi formati che possono essere utilizzati quando si immette il nome.
  
Durante la ricerca nell'elenco dell'organizzazione, le persone possono usare il tasto '0' (zero) per indicare uno spazio tra il nome e cognome o viceversa. Quando inseriscono il nome, verrà chiesto di concludere l'immissione da tastiera con il tasto # (cancelletto). Ad esempio: "Dopo aver immesso il nome della persona che state cercando di raggiungere, premete #". Se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Le persone possono cercare nomi nell'organizzazione utilizzando i seguenti formati di ricerca sulla tastiera del telefono.
  
|||||
|:-----|:-----|:-----|:-----|
|**Formato del nome** <br/> |**Tipo di ricerca** <br/> |**Esempio** <br/> |**Risultato della ricerca** <br/> |
|Nome + Cognome  <br/> |Completa  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Cognome + Nome  <br/> |Completa  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|Nome  <br/> |Completa  <br/> |Amos#  <br/> |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus  <br/> |
|Cognome  <br/> |Completa  <br/> |Marble#  <br/> |Premere 1 per Amos Marble  <br/> Premere 2 per Mary Marble  <br/> |
|Nome o Cognome  <br/> |Parziale  <br/> |Mar#  <br/> |Premere 1 per Mary Marble  <br/> Premere 2 per Mary Jones  <br/> Premere 3 per Amos Marcus  <br/> |
|Nome + Cognome  <br/> |Parziale  <br/> |Mar0Amos#  <br/> |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus  <br/> |
|Cognome + Nome  <br/> |Parziale  <br/> |Mar0Am#  <br/> |Premere 1 per Amos Marble  <br/> Premere 2 per Amos Marcus  <br/> |
   
Esistono diversi caratteri speciali che vengono utilizzati durante la ricerca di persone che usano una tastiera del telefono. Ad esempio, la persona verrà chiesto di usare il tasto cancelletto (#), mentre zero (0) usata per uno spazio tra i nomi. Premere il tasto asterisco (*) ripeterà l'elenco dei nomi alla persona che sta corrispondenti.
  
|||
|:-----|:-----|
|**Carattere speciale della tastiera del telefono** <br/> |**Cosa significa** <br/> |
|# (cancelletto)  <br/> |Carattere terminale quando si immette un nome.  <br/> |
|0 (zero)  <br/> |Spazio tra i nomi.  <br/> |
|* (asterisco)  <br/> |Ripete l'elenco dei nomi corrispondenti.  <br/> |
   
### Chiamata per nome - Riconoscimento vocale del nome

Persone possono cercare altri utenti dell'organizzazione tramite vocali (riconoscimento vocale). Possono inoltre raggiungere tutti gli utenti Active Directory della società, in cui viene indicato il nome della persona che si desidera individuare. Usare gli input vocali può riconoscere nomi in diversi formati, tra cui nome, cognome, nome, cognome oppure cognome + nome.
  
Quando si abilita il riconoscimento vocale per un operatore automatico, voce tastierino del telefono (DTMF) non è possibile disabilitato, in modo che possono essere utilizzati entrambi i tipi di input. Voce tastierino del telefono non può essere disabilitata e può essere utilizzato in qualsiasi momento, anche se il riconoscimento vocale è attivato per l'operatore automatico.
  
Come avviene per l'immissione da tastiera, se vengono trovati più nomi, al chiamante verrà dato un elenco di nomi tra cui scegliere.
  
Il chiamante può pronunciare i nomi nei seguenti formati.
  
|||||
|:-----|:-----|:-----|:-----|
|**Assegnare un nome con il riconoscimento vocale** <br/> |**Tipo di ricerca** <br/> |**Esempio** <br/> |**Risultato della ricerca** <br/> |
|Nome + Cognome  <br/> |Completa  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Cognome + Nome  <br/> |Completa  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|Nome  <br/> |Completa  <br/> |Amos  <br/> |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Amos Jones  <br/> |
|Cognome  <br/> |Completa  <br/> |Marble  <br/> |Premere o pronunciare 1 per Amos Marble  <br/> Premere o pronunciare 2 per Ben Marble  <br/> |
   
> [!NOTE]
> Potrebbe richiedere fino a 36 ore per un nuovo utente per il proprio nome visualizzato nell'elenco per telefono in base al nome con il riconoscimento vocale. 
  
### Lingue supportate

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
   
### Uso dell'opzione operatore

Usare l'opzione operatore di un operatore automatico è un'impostazione facoltativa che dà al chiamante la possibilità di parlare con una persona dal vivo.
  
Il tasto 0 e il comando vocale "Operatore" (in tutte le lingue supportate per il riconoscimento vocale) sono assegnati alla funzione operatore per impostazione predefinita.
  
> [!NOTE]
> È possibile impostare il pulsante che viene inserito come **operatore** per una chiave diversa utilizzando **Le opzioni del Menu**. 
  
Puoi impostare la funzione Operatore a una delle persone seguenti.
  
- Skype for Business Online utente che dispone di un **Sistema telefonico** licenza che è abilitato Enterprise Voice o la chiamata plan di messaggistica unificata assegnata a. È possibile impostare il in modo che la persona chiamata in può essere inviata alla segreteria telefonica. Per eseguire questa operazione, selezionare una **persona dell'azienda** e impostare le chiamate per inoltrare automaticamente direttamente alla segreteria telefonica della persona.
    
    > [!NOTE]
    > Gli utenti ospitati locale tramite Lync Server 2010 non può essere utilizzato come operatore. 
  
- Un altro operatore automatico configurato per l'organizzazione.
    
- Qualsiasi coda chiamata esistente che ha configurato all'interno dell'organizzazione. Per ulteriori informazioni su chiamata code, vedere [Creare una coda di chiamata sistema telefonico](create-a-phone-system-call-queue.md).
    
### Orario di ufficio e gestione delle chiamate

Orario di lavoro sono impostate su ogni operatore automatico. Se non è impostata orario di ufficio, tutti i giorni e tutte le ore nella casella giorno sono considerate orario di ufficio perché una pianificazione di 24/7 per impostazione predefinita. Orario di lavoro possono essere impostate con interruzioni nel tempo durante il giorno e tutte le ore che non sono impostate come orario di ufficio sono considerate installazioni. È possibile impostare diverse opzioni di gestione delle chiamate in arrivo e messaggi di saluto diversi (che sono facoltativi) ed entrambe possono essere impostati per orario di ufficio e installazioni.
  
Ogni operatore automatico è le opzioni di gestione delle chiamate che è possono impostare:
  
- È possibile far scollegare la chiamata dopo il saluto.
    
- È possibile anche:
    
  - Reindirizzare la chiamata a Skype for Business Online utente che dispone di una licenza di **Sistema telefonico** che è abilitato Enterprise Voice o la chiamata plan di messaggistica unificata assegnata a. È possibile impostare il in modo che la persona chiamata in può essere inviata alla segreteria telefonica. Per eseguire questa operazione, selezionare una **persona dell'azienda** e impostare le chiamate per inoltrare automaticamente direttamente alla segreteria telefonica della persona.
    
    > [!NOTE]
    > Gli utenti ospitati locale tramite Lync Server 2010 non sono supportati. 
  
  - Reindirizzare la chiamata a una coda di chiamata. Per ulteriori informazioni su chiamata code, vedere [Creare una coda di chiamata sistema telefonico](create-a-phone-system-call-queue.md).
    
  - Inoltrare la chiamata a un altro operatore automatico impostato.
    
- Creare opzioni di menu e riprodurre un messaggio menu per il chiamante. Ad esempio: "Premere 1 per i servizi commerciali, premere 2 per l'assistenza. Per parlare con l'operatore, premere 0 in qualsiasi momento".
    
### Opzioni di menu

Operatori automatici di sistema telefonico consentono di creare menu prompt ("premere 1 per le vendite, premere 2 per i servizi") e impostare le opzioni di menu per instradare le chiamate in base alla selezione. Impostazione delle opzioni di menu per un operatore automatico consente alle organizzazioni di fornire linee guida interattiva per ottenere la persona alla relativa destinazione più veloce, senza utilizzare un operatore per gestire le chiamate in arrivo. Prompt dei menu possono essere create mediante la funzione sintesi vocale da testo (generato dal sistema istruzioni) o per caricare un file audio è stato registrato. Riconoscimento vocale utilizza comandi vocali per gli spostamenti auricolare, ma utenti effettuano inoltre possono utilizzare il tastierino del telefono per esplorare i menu.
  
Tasti da 0 a 9 possono essere assegnati alle **Opzioni di Menu** in un operatore automatico di utilizzo di Skype per Business admin center. Set diversi di opzioni di menu possono essere create per orario di ufficio e dopo le ore ed è possibile abilitare o disabilitare Dial in base al nome nelle **Opzioni del Menu**. Per trasferire le chiamate a, è possono eseguire il mapping tasti:
  
- Un operatore, che sia associato alla chiave 0 per impostazione predefinita. Tuttavia, può essere nuovamente assegnata a un tasto, o rimosso dal menu di scelta.
    
- Una coda di chiamata.
    
- Un altro operatore automatico. Menu multilivello possono essere configurati, scegliendo un altro operatore automatico con un proprio gruppo di opzioni del Menu che viene definito un operatore automatico "annidate" un' **Opzione di Menu** di operatore uno automatico.
    
- Skype for Business Online utente che dispone di un **Sistema telefonico** licenza che è abilitato Enterprise Voice o la chiamata plan di messaggistica unificata assegnata a. È possibile impostare il in modo che la persona chiamata in può essere inviata alla segreteria telefonica. Per eseguire questa operazione, selezionare una **persona dell'azienda** e impostare le chiamate per inoltrare automaticamente direttamente alla segreteria telefonica della persona.
    
    > [!NOTE]
    > Gli utenti ospitati locale tramite Lync Server 2010 non può essere usato in **Opzioni del Menu**. 
  
Il nome di ogni opzione di menu diventa una parola chiave riconoscimento vocale, se è stato attivato il riconoscimento vocale. Ad esempio, i chiamanti pronunciare "Uno" per selezionare l'opzione di menu mappato al tasto 1 o si possono semplicemente dice "Vendite" per selezionare l'opzione di menu stesso denominata "Vendite".
  
Per configurare un operatore automatico e le opzioni di menu, vai [Impostare un operatore automatico di sistema telefonico](set-up-a-phone-system-auto-attendant.md).
  
### Ottenere numeri di servizio per un operatore automatico

Prima di creare e configurare i operatori automatici, sarà necessario ottenere o trasferire un esistente a pagamento o un servizio gratuito numeri. Una volta che viene visualizzato il numero verde o numeri di telefono di servizio gratuito, verrà visualizzato in **Skype for Business admin center** > **vocali** > **numeri di telefono** e verrà **tipo numero** elencato sarà elencato tra i **servizi-verde**. Per ottenere i numeri di servizio, vedere [Recupero di numeri di telefono di servizio Skype for Business](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md) o, se si desidera trasferire e il numero di servizio esistente, vedere[Trasferire i numeri di telefono a Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Se si è fuori dagli Stati Uniti, è possibile utilizzare Skype for Business admin center per ottenere numeri di servizio. Passare [Gestire i numeri di telefono per la propria organizzazione](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) invece per informazioni su come eseguire questa operazione.
  
## Modificare l'ID chiamante dell'utente per diventare un numero di telefono di una chiamata coda

È possibile proteggere identità dell'utente modificando il loro ID chiamante per le chiamate in uscita a una coda di chiamata invece mediante la creazione di un criterio utilizzando il cmdlet **New-CallingLineIdentity**.
  
A tale scopo, eseguire:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Quindi applicare i criteri per l'utente utilizzando il cmdlet **Grant-CallingLineIdentity**. A tale scopo, eseguire:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

È possibile ottenere altre informazioni su come modificare le impostazioni di ID chiamante nell'organizzazione [Come usare l'ID chiamante nella tua organizzazione](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Argomenti correlati

[Ecco cosa viene visualizzato con sistema telefonico in Office 365](here-s-what-you-get-with-phone-system-in-office-365.md)
  
[Configurare la chiamata plan di messaggistica unificata](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

