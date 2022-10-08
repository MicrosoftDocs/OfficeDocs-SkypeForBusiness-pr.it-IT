---
title: Controllo di amministrazione tenant per il riconoscimento vocale (profilo vocale) in Teams Rooms
author: dstrome
ms.author: dstrome
ms.reviewer: parisataheri
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni sul controllo dell'amministrazione tenant per il riconoscimento vocale (profilo vocale) nelle sale riunioni di Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7b74ecb85f6081533f5139b6f8f083b8958d47f
ms.sourcegitcommit: 31fe510550ac1f5f8e53b2395014cb909a6eb723
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2022
ms.locfileid: "68350749"
---
# <a name="manage-voice-recognition-technology-controls-for-an-intelligent-speaker"></a>Gestire i controlli della tecnologia di riconoscimento vocale per un altoparlante intelligente

Un altoparlante intelligente usa le informazioni del profilo vocale per riconoscere chi ha detto cosa nella trascrizione in tempo reale. Quando una sala riunioni di Microsoft Teams Rooms per Windows è dotata di un altoparlante intelligente, durante la riunione è possibile usare la trascrizione in tempo reale. Questo articolo spiega in che modo un amministratore tenant controlla la profilatura vocale usata per il riconoscimento vocale per generare la trascrizione in tempo reale. Puoi controllare in quale misura l'organizzazione usa il riconoscimento vocale e le seguenti funzionalità:

- Modificare il nome del relatore nelle trascrizioni.
- Cambiare l'altoparlante di una singola espressione nella trascrizione o cambiare l'altoparlante in tutte le frasi nella trascrizione (ma non nelle trascrizioni future).
- Modificare l'identificazione del relatore per le persone elencate nella riunione.
- Rimuovere l'identificazione di una o più espressioni identificate come tale altoparlante, in ogni trascrizione.

## <a name="review-intelligent-speaker-requirements"></a>Rivedere i requisiti degli altoparlanti intelligenti

Un altoparlante intelligente include uno speciale array di sette microfoni. Il sistema usa le informazioni del profilo vocale per identificare le voci di un massimo di 10 persone nelle sale riunioni.

I requisiti degli altoparlanti intelligenti sono i seguenti:

- La sala riunioni deve avere un massimo di 10 persone presenti di persona.
- La sala riunioni ha un collegamento di caricamento di almeno 7 Mbps.

Sono supportati altoparlanti intelligenti Epos, Sennheiser e Yealink.

> [!NOTE]
> L'altoparlante intelligente è disponibile in tutti i paesi e le aree geografiche. Per un elenco delle impostazioni locali attualmente supportate per la registrazione biometrica e la trascrizione in riunione, vedere [Impostazioni locali supportate](#supported-locales) .

## <a name="set-up-an-intelligent-speaker"></a>Configurare un altoparlante intelligente

Un altoparlante intelligente si connette direttamente tramite USB alla console Teams Rooms.

> [!NOTE]
> Un altoparlante intelligente Yealink **deve** essere utilizzato con una console Yealink.

> [!NOTE]
> Non è supportare un altoparlante intelligente connesso a Logitech Surface Pro Microsoft Teams Rooms. Esiste un problema noto a causa del quale Teams Rooms non riesce a riconoscere l'altoparlante intelligente tramite il dock.

Un altoparlante intelligente deve essere posizionato a una distanza di almeno 20 cm dalle pareti e da oggetti di grandi dimensioni, come i portatili. Se il cavo USB dell'altoparlante intelligente non è abbastanza lungo per la configurazione, usa i extender dei cavi.

1. Accedi alla console come amministratore.
2. Impostare le impostazioni del dispositivo di Teams in modo che corrispondano al microfono e all'altoparlante dell'altoparlante dell'altoparlante intelligente.
   È possibile farlo anche tramite il portale TAC invece che tramite la console della sala.

   Il diagramma mostra come l'altoparlante intelligente è connesso al dispositivo se il dispositivo include una casella dati.

   ![Configurazione dell'altoparlante intelligente con l'altoparlante, la casella alimentazione e dati. Una linea passa alla porta USB della console, mentre l'altra passa all'alimentazione.](../media/intelligent-speakers1.png)

   Il diagramma mostra come l'altoparlante intelligente è connesso al dispositivo se il dispositivo non include una casella dati.

   ![Configurazione dell'altoparlante intelligente con l'altoparlante che si connette direttamente alla console.](../media/intelligent-speakers2.png)

> [!NOTE]
> I dispositivi EPOS e Yealink devono avere il prefisso "EPOS" o "Yealink" e devono contenere "UAC2_RENDER" nel nome del relatore e "UAC2_TEAMS" nel nome del microfono. Se non trovi i nomi di microfono e altoparlanti nel menu a discesa, riavvia il dispositivo altoparlante intelligente.

## <a name="enable-an-intelligent-speaker-user-recognition"></a>Abilitare il riconoscimento utente di un altoparlante intelligente

I dati del profilo vocale possono essere usati in qualsiasi riunione con un altoparlante intelligente. Per informazioni sulle impostazioni della riunione, vedere Criteri [per le riunioni di Teams](../meetings-policies-recording-and-transcription.md#transcription) e cmdlet per [le riunioni di PowerShell](/powershell/module/skype/set-csteamsmeetingpolicy) .

I dati del profilo vocale dell'utente vengono creati quando il criterio è impostato per distinguere o quando un utente invitato non partecipa alla riunione entra durante la riunione. I dati del profilo vocale verranno ignorati alla fine della riunione.

Di seguito sono elencati i criteri necessari per impostare un altoparlante intelligente e il riconoscimento utente.

|Criterio|Descrizione|Valori e comportamento|
|-|-|-|
|enrollUserOverride|Da usare per impostare l'acquisizione o la registrazione del profilo vocale nelle impostazioni di Teams per un tenant. |**Disattiva**<br><ul><li> Gli utenti che non hanno mai effettuato la registrazione non possono visualizzare, registrare o ripetere la registrazione.<li>Il punto di ingresso al flusso di registrazione verrà nascosto.<li>Se gli utenti selezionano un collegamento alla pagina di registrazione, vedranno un messaggio che indica che questa funzionalità non è abilitata per l'organizzazione.  <li>Gli utenti iscritti possono visualizzare e rimuovere il proprio profilo vocale nelle impostazioni di Teams. Dopo aver rimosso il profilo vocale, non potrà visualizzare, accedere o completare il flusso di registrazione.</li></ul><br>**Abilitato**<br><ul><li> Gli utenti possono visualizzare, accedere e completare il flusso di registrazione.<li>Il punto di ingresso verrà visualizzato nella pagina delle impostazioni di Teams nella scheda **Riconoscimento** .</li></ul>|
|roomAttributeUserOverride|Controllare l'identificazione utente basata su voce nelle sale riunioni. Questa impostazione è obbligatoria per Teams Rooms account.| **Disattivato**<br><ul><li>Il dispositivo Teams Rooms non invierà larghezza di banda per il risparmio di flussi audio dalla sala. <li>Gli utenti delle sale riunioni non verranno attribuiti o distinti e le loro firme vocali non verranno recuperate o usate affatto.<li>Gli utenti della sala riunioni sono sconosciuti.</li></ul> <br>**Attributo**<br><ul><li>Gli utenti delle chat room verranno attribuiti in base allo stato di registrazione.<li>Gli utenti registrati vengono visualizzati con il proprio nome nella trascrizione.  <li>Gli utenti non iscritti vengono visualizzati come Altoparlante \<n>.<li>Il dispositivo Teams Rooms invierà sette flussi audio dalla stanza.</ul> <br>**Distinguere**<br> <ul><li>Gli utenti delle sale saranno distinti e separati come altoparlante 1, altoparlante 2, .... relatore \<n> nella trascrizione.</li><li>Indipendentemente dallo stato di registrazione dell'utente, il suo nome non verrà visualizzato nella trascrizione.</li><li>Il dispositivo Teams Rooms invierà sette flussi audio dalla stanza.</li></ul>
|AllowTranscription|Obbligatorio per gli account utente e per le chat room di Teams.|**Vero** e **Falso**|
||||

Nell'interfaccia di amministrazione di Teams impostare il criterio **di trascrizione** . Le impostazioni sono **disattivate** per impostazione predefinita.

![interfaccia di amministrazione con i criteri riunione evidenziati e l'opzione Consenti trascrizione selezionata.](../media/allow-transcription1.png)
  
> [!NOTE]
> Dopo l'assegnazione dei criteri, l'applicazione dei criteri può richiedere fino a 48 ore. Per rendere i criteri più applicati prima, è necessario disconnettersi e accedere di nuovo.

## <a name="frequently-asked-questions-faq"></a>Domande frequenti (FAQ)

**Dove vengono archiviati i dati del profilo vocale?**

I dati del profilo vocale vengono archiviati in Office 365 cloud con contenuto dell'utente.

**Che cos'è la sequenza temporale e i criteri di conservazione?**

I criteri di conservazione generali sono indicati nella [panoramica sulla conservazione dei dati](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview). Inoltre, i dati del profilo vocale di un utente verranno eliminati dopo 1 anno se l'utente non è invitato a partecipare a riunioni con un altoparlante intelligente entro tale periodo di 1 anno. I dati non vengono usati nelle riunioni per i dipendenti esistenti. Se un dipendente ha lasciato l'azienda, i dati del profilo vocale sono considerati contenuti utente e vengono trattati come tali in base ai criteri di conservazione dei dati Office 365 descritti nella [panoramica sulla conservazione dei](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) dati.

**I dati del profilo vocale vengono utilizzati in tutti i servizi Microsoft?**

No, i dati del profilo vocale vengono utilizzati solo per lo scopo per cui l'utente ha fornito il consenso. Microsoft non utilizzerà i dati del profilo vocale se non negli scenari di riconoscimento vocale di Teams.

Ad esempio, Microsoft non userà i dati nelle situazioni seguenti:

**I dati del profilo vocale vengono usati quando si partecipa a una riunione in un'altra organizzazione?**

Non solo nelle riunioni organizzate da un utente dell'organizzazione.

**Come posso esportare il mio profilo vocale?**

L'amministratore IT può esportare i dati audio in qualsiasi momento.

## <a name="supported-locales"></a>Impostazioni locali supportate

Le impostazioni locali di registrazione e trascrizione in riunione seguenti sono supportate in tutti i paesi e le aree geografiche.

### <a name="enrollment-locales"></a>Impostazioni locali di registrazione

Gli utenti finali possono registrare la propria voce per il riconoscimento nelle impostazioni locali seguenti:

|**Lingua**|**Paese/area geografica**|**ID impostazioni cultura**|
|:-----|:-----|:-----|
|Arabo  <br/> |Arabia Saudita <br/> |ar-SA  <br/> |
|Cinese  <br/> |Cina <br/> |zh-CN  <br/> |
|Cinese  <br/> |Taiwan <br/> |zh-TW  <br/> |
|Danese  <br/> |Danimarca <br/> |da-DK  <br/> |
|Olandese  <br/> |Paesi Bassi <br/> |nl-NL  <br/> |
|Inglese  <br/> |Australia <br/> |en-AU  <br/> |
|Inglese  <br/> |Canada  <br/> |en-CA <br/> |
|Inglese  <br/> |India  <br/> |en-IN  <br/> |
|Inglese  <br/> |Nuova Zelanda  <br/> |en-NZ  <br/> |
|Inglese  <br/> |Regno Unito  <br/> |en-GB  <br/> |
|Inglese  <br/> |Stati Uniti  <br/> |en-US  <br/> |
|Finlandese  <br/> |Finlandia  <br/> |fi-FI  <br/> |
|Francese  <br/> |Canada <br/> |fr-CA  <br/> |
|Francese  <br/> |Francia <br/> |fr-FR  <br/> |
|Italiano  <br/> |Italia <br/> |it-IT  <br/> |
|Giapponese  <br/> |Giappone <br/> |ja-JP  <br/> |
|Norvegese  <br/> |Norvegia <br/> |nb-NO  <br/> |
|Polacco  <br/> |Polonia <br/> |pl-PL  <br/> |
|Portoghese      <br/> |Brasile <br/> |pt-BR  <br/> |
|Russo  <br/> |Russia <br/> |ru-RU  <br/> |
|Svedese  <br/> |Svezia <br/> |sv-SE  <br/> |
|Spagnolo  <br/> |Messico  <br/> |es-MX  <br/> |
|Spagnolo  <br/> |Spagna  <br/> |es-ES  <br/> |

### <a name="in-meeting-transcription-locales"></a>Impostazioni locali della trascrizione durante la riunione

Quando un utente finale si iscrive, la sua voce può essere riconosciuta durante le riunioni e identificata nella trascrizione quando la riunione è impostata su una delle impostazioni locali seguenti:

|**Lingua**|**Paese/area geografica**|**ID impostazioni cultura**|
|:-----|:-----|:-----|
|Cinese (semplificato)  <br/> |Cina  <br/> |zh-CN  <br/> |
|Inglese  <br/> |Australia <br/> |en-AU  <br/> |
|Inglese  <br/> |Canada  <br/> |en-CA <br/> |
|Inglese  <br/> |India  <br/> |en-IN  <br/> |
|Inglese  <br/> |Nuova Zelanda  <br/> |en-NZ  <br/> |
|Inglese  <br/> |Regno Unito  <br/> |en-GB  <br/> |
|Inglese  <br/> |Stati Uniti  <br/> |en-US  <br/> |
|Francese  <br/> |Canada  <br/> |fr-CA  <br/> |
|Francese  <br/> |Francia  <br/> |fr-FR  <br/> |
|Tedesco  <br/> |Germania  <br/> |de-DE  <br/> |
|Italiano  <br/> |Italia  <br/> | it-IT <br/> |
|Giapponese  <br/> |Giappone  <br/> |ja-JP  <br/> |
|Coreano  <br/> |Corea  <br/> |ko-KR  <br/> |
|Portoghese  <br/> |Brasile  <br/> |pt-BR  <br/> |
|Spagnolo  <br/> |Messico  <br/> |es-MX  <br/> |
|Spagnolo  <br/> |Spagna  <br/> |es-ES  <br/> |

## <a name="related-topics"></a>Argomenti correlati

[Articolo del supporto: Usare gli altoparlanti intelligenti per identificare i partecipanti in sala](https://support.microsoft.com/office/use-teams-intelligent-speakers-to-identify-in-room-participants-in-meeting-transcription-a075d6c0-30b3-44b9-b218-556a87fadc00)
