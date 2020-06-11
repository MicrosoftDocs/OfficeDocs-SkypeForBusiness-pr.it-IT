---
title: Opzioni di posta elettronica durante la modifica delle impostazioni del audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: "Informazioni su come abilitare o disabilitare Skype dall'invio di messaggi di posta elettronica agli utenti in caso di impostazioni come le modifiche ai pin o le modifiche dei numeri di conferenza predefiniti in Microsoft teams. "
ms.openlocfilehash: 36c7e9dce17de1e6f9bbf8b812d62ddd91bc6ffe
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691602"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni di conferenza audio cambiano in Microsoft Teams

Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza. In alcuni casi, tuttavia, è possibile ridurre il numero di messaggi di posta elettronica inviati agli utenti di Microsoft teams. In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.
  
Se si disabilita l'invio di messaggi di posta elettronica, i messaggi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi di posta elettronica per quando gli utenti sono abilitati o disabilitati per i servizi di audioconferenza, quando il PIN viene reimpostato e quando viene modificato l'ID conferenza e il numero di telefono delle conferenze
  
Ecco un esempio di messaggio di posta elettronica inviato agli utenti quando sono abilitati per i servizi di audioconferenza:
  
![Esempio di messaggio di posta elettronica per i servizi di audioconferenza](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>I messaggi di posta elettronica quando vengono inviati agli utenti?

- Ci sono diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per i servizi di audioconferenza:
    
  - Quando una licenza di **Audioconferenza** viene loro assegnata.
    
  - Quando si reimposta manualmente il PIN per i servizi di audioconferenza dell'utente.
    
  - Quando reimposti manualmente l'ID conferenza dell'utente.
    
  - Quando la licenza di **Audioconferenza** viene loro rimossa.
    
  - Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **nessuno**.
    
  - Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti

Puoi usare Microsoft teams o Windows PowerShell per abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti.

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

1. Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Bridge conferenza**riunioni. 

2. Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**. 

3. Nel riquadro **Impostazioni Bridge** abilitare o disabilitare **Invia automaticamente i messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di accesso**esterno.

4. Fare clic su **Salva**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Uso di Windows PowerShell**
  
Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .

    
## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.
    
  
## <a name="related-topics"></a>Argomenti correlati

[Messaggi di posta elettronica inviati agli utenti quando cambiano le impostazioni dei servizi di audioconferenza](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


