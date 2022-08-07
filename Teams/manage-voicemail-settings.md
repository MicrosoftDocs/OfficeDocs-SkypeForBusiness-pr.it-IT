---
title: Gestire le impostazioni di Cloud Voicemail
author: crowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Gestire le impostazioni della segreteria telefonica per gli utenti.
ms.openlocfilehash: 7aa2fdf84f38cb9977b3a4156b28a96b98bbd9d7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269601"
---
# <a name="manage-cloud-voicemail-settings-for-users"></a>Gestire le impostazioni di Cloud Voicemail per gli utenti

Le impostazioni della segreteria telefonica consentono di configurare le impostazioni della segreteria telefonica per singoli utenti.

Prima di configurare le impostazioni della segreteria telefonica per gli utenti, leggere [Configurare Cloud Voicemail](set-up-phone-system-voicemail.md). Per informazioni sull'impostazione dei criteri per gruppi di utenti, vedere [Gestire i criteri della segreteria telefonica](manage-voicemail-policies.md).

Le impostazioni predefinite per Cloud Voicemail sono:

- La segreteria telefonica è abilitata.
- La lingua del prompt è impostata sulla lingua preferita dell'utente.
- Il messaggio di saluto fuori sede è disabilitato.
- Il messaggio di saluto Fuori sede, quando le risposte automatiche sono impostate in Outlook, viene disabilitato.
- Il messaggio di saluto Fuori sede, quando il calendario di Outlook viene visualizzato fuori sede, è disabilitato.
- La condivisione dei dati della segreteria telefonica e della trascrizione con il servizio per la formazione e il miglioramento delle finalità di accuratezza è disabilitata.
- La regola di risposta alle chiamate è impostata su Segreteria telefonica normale.
- La sovrascrittura predefinita del messaggio di saluto non è impostata.
- La sovrascrittura predefinita del messaggio di saluto Fuori sede non è impostata.
- L'obiettivo di trasferimento non è impostato.


Per gestire Cloud Voicemail funzionalità per gli utenti, è possibile usare l'interfaccia di amministrazione di Teams o PowerShell. Si noti che gli utenti finali possono anche configurare queste impostazioni nel client di Teams accedendo a **Impostazioni -chiamate > -> Configura segreteria telefonica.**

## <a name="use-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams

Nell'interfaccia di amministrazione di Teams:

1.  Nel riquadro di spostamento sinistro passare a **Utenti > Gestisci utenti** e selezionare l'utente.

2.  Nella pagina dei dettagli dell'utente passare alla scheda **Segreteria telefonica** .

3.  Modificare le impostazioni.

4.  Selezionare **Salva**.


## <a name="use-powershell"></a>Usare PowerShell

È anche possibile usare PowerShell per gestire le impostazioni della segreteria telefonica nel modo seguente:

- Per gestire le impostazioni di Cloud Voicemail per singoli utenti, utilizza il cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). 

- Per visualizzare le impostazioni, utilizzare il cmdlet [Get-CsOnlineVoicemailUserSettings](/powershell/module/skype/get-csonlinevoicemailusersettings) .

- Puoi disabilitare Cloud Voicemail per un utente utilizzando il cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) e impostando il parametro VoicemailEnabled su $false. 

## <a name="voicemail-settings"></a>Impostazioni della segreteria telefonica

- **Casella vocale abilitata**: questa impostazione controlla se Cloud Voicemail è abilitato per l'utente. Se le impostazioni sono false, Cloud Voicemail servizio non sarà disponibile per l'utente e non registrerà un messaggio vocale per l'utente.

- **Lingua prompt**: questa impostazione specifica la lingua usata per i prompt nella Cloud Voicemail. Per altre informazioni, vedere [Cambiare la lingua predefinita per i saluti e i messaggi di posta elettronica](change-the-default-language-for-greetings-and-emails.md).

- **Impostazioni del messaggio** di saluto: Cloud Voicemail è in grado di riprodurre un messaggio di saluto specifico per quando l'utente è in ufficio e per quando l'utente è fuori sede. Entrambi i saluti possono essere registrati dall'utente o un saluto di sintesi vocale può essere utilizzato.

  - **Sovrascrivi messaggio di saluto predefinito** - specifica il messaggio di saluto di sintesi vocale che verrà riprodotto nel caso in cui l'utente non abbia registrato un messaggio di saluto.

  - **Oof Greeting Enabled** - specifica se il messaggio di saluto fuori sede viene riprodotto nello scenario di deposito della segreteria telefonica, indipendentemente dalle impostazioni di Outlook.

  - **Oof Greeting Follow Automatic Replies Abilitato** - specifica se riprodurre il messaggio di saluto Fuori sede nello scenario di deposito della segreteria telefonica quando l'utente imposta risposte automatiche in Outlook.

  - **Oof Greeting Follow Calendar Abilitato** - specifica se riprodurre il messaggio di saluto fuori sede nello scenario di deposito della segreteria telefonica quando l'utente imposta fuori sede nel calendario.

  - **Sovrascrittura predefinita del messaggio** di saluto : specifica il messaggio di saluto di sintesi vocale che verrà riprodotto nel caso in cui l'utente sia fuori sede e non abbia registrato un messaggio di saluto fuori sede.

- **Regola di risposta alle** chiamate: questa impostazione specifica la regola di risposta alle chiamate. La regola può essere:
  - Il servizio rifiuta la chiamata senza messaggio.
  - Viene riprodotto solo il saluto pertinente (normale o fuori sede).
  - Il saluto pertinente (normale o fuori sede) viene riprodotto e il chiamante viene trasferito all'utente o al numero di telefono specificato.
  -  Viene riprodotto il messaggio di saluto pertinente (normale o fuori sede) e il chiamante può lasciare un messaggio vocale.
  - Il saluto pertinente (normale o fuori sede) viene riprodotto, il chiamante può lasciare un messaggio vocale ed è autorizzato a premere 0 per essere trasferito all'utente o al numero di telefono specificato.

- **Condividere i dati per i miglioramenti del servizio** : specifica se i dati della segreteria telefonica e della trascrizione vengono condivisi con il servizio per la formazione e per migliorare l'accuratezza. Se impostato su false, i dati della segreteria telefonica non verranno condivisi, indipendentemente dalla scelta dell'utente.

- **Trasferimento chiamata** : specifica l'utente o il numero di telefono a cui il chiamante viene trasferito.


