---
title: E-mail inviate automaticamente agli utenti in caso di modifica delle impostazioni
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Informazioni sulle informazioni che vengono inviate automaticamente agli utenti tramite posta elettronica quando le impostazioni dei servizi di conferenza telefonica con accesso esterno cambiano in Microsoft Teams. '
ms.openlocfilehash: 81faefb3bfe2fd6c93584c5a9f48fd99a6040c99
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055476"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Messaggi di posta elettronica inviati agli utenti quando le impostazioni cambiano in Microsoft Teams

I messaggi di posta elettronica vengono inviati automaticamente agli utenti che sono [abilitati per le audioconferenze](set-up-audio-conferencing-in-teams.md) tramite Microsoft come provider di servizi di audioconferenza.

Per impostazione predefinita, sono disponibili quattro tipi di posta elettronica inviata agli utenti abilitati per le audioconferenze. Tuttavia, se desideri limitare il numero di messaggi di posta elettronica inviati agli utenti, puoi disabilitare l'opzione. Le audioconferenze Microsoft 365 o Office 365 invieranno posta elettronica ai messaggi di posta elettronica degli utenti quando:

- **Viene assegnata loro una licenza di Audioconferenza o quando cambi il provider di audioconferenza e passi a Microsoft.**

     Questo messaggio di posta elettronica include l'ID conferenza, il numero di telefono predefinito per le riunioni, il PIN per le audioconferenze dell'utente e le istruzioni e il collegamento per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online che consente di aggiornare riunioni esistenti per l'utente. Vedere [Assegnare Microsoft Teams licenze per i componenti aggiuntivi](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) o [Assegnare Microsoft come provider di servizi di audioconferenza.](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)

    > [!NOTE]
    > Se l'organizzazione è stata abilitata per gli ID conferenza dinamici, tutte le riunioni dell'utente pianificate avranno ID conferenza univoci. È possibile impostare [gli ID audioconferenza dinamici all'interno dell'organizzazione](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).

    Di seguito è riportato un esempio di questo messaggio di posta elettronica:

     ![Skype for Business Verifica licenza.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Per altre informazioni sulle licenze, vedere Microsoft Teams [licenze per i componenti aggiuntivi.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

- **L'ID conferenza o il numero di telefono per le conferenze predefinito di un utente cambia.**

    Questo messaggio di posta elettronica contiene l'ID conferenza, il numero di telefono di conferenza predefinito, le istruzioni e il collegamento per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online che consente di aggiornare riunioni esistenti per l'utente. Tuttavia, questo messaggio di posta elettronica non include il PIN per l'audioconferenza dell'utente. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

    Di seguito è riportato un esempio di questo messaggio di posta elettronica:

     ![Le informazioni sulle conferenze telefoniche sono state modificate.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Viene reimpostato il PIN di audioconferenza di un utente.**

    Questo messaggio di posta elettronica contiene il PIN di audioconferenza dell'organizzatore, l'ID conferenza esistente e il numero di telefono di conferenza predefinito per l'utente. Vedere [Reimpostare il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin-in-teams.md)

     Di seguito è riportato un esempio di questo messaggio di posta elettronica:

     ![PIN di conferenza telefonica modificato.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **Una licenza dell'utente è stata rimossa o quando il provider di servizi di audioconferenza viene modificato da Microsoft a altri provider o nessuno.**

    Questo problema si verifica quando la licenza **di audioconferenza** viene rimossa da un utente o quando si imposta il provider di servizi di audioconferenza **su Nessuno**.

    Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

    Di seguito è riportato un esempio di questo messaggio di posta elettronica:

     ![Conferenza telefonica disattivata.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Apportare modifiche ai messaggi di posta elettronica inviati

È possibile apportare modifiche al messaggio di posta elettronica che viene inviato automaticamente agli utenti. Per impostazione predefinita, il mittente dei messaggi di posta elettronica Microsoft 365 o Office 365, ma è possibile modificare il nome visualizzato usando Windows PowerShell. Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se non vuoi che la posta elettronica venga inviata a loro?

Quando disattivi l'invio di messaggi di posta elettronica agli utenti, la posta elettronica non verrà inviata anche quando un utente riceve una licenza. In questo caso, l'ID conferenza, il numero di telefono per conferenze predefinito e, soprattutto, il PIN di audioconferenza non verranno inviati all'utente. In questo caso, devi informare l'utente inviandogli un messaggio di posta elettronica separato o chiamandolo.

Per impostazione predefinita, i messaggi di posta elettronica verranno inviati agli utenti, ma se si vuole impedire loro di ricevere posta elettronica per le audioconferenze, è possibile usare Microsoft Teams o Windows PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.**

3. Nel riquadro **Impostazioni bridge** abilitare o disabilitare Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di accesso **remoto cambiano.**

4. Fare clic su **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Uso di Windows PowerShell

È anche possibile usare il modulo Microsoft Teams PowerShell ed eseguire:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

È possibile usare [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.

Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più sulle Windows PowerShell?

Per impostazione predefinita, il mittente dei messaggi di posta elettronica Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell.

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Modi migliori per gestire Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Argomenti correlati

[Abilitare o disabilitare l'invio di messaggi di posta elettronica in caso di modifica delle impostazioni di audioconferenza](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
