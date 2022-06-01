---
title: Modificare le impostazioni per un bridge per audioconferenza
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Modifica le impostazioni del bridge per i servizi di audioconferenza, incluse le notifiche di accesso e uscita, riproduci nomi o numeri di telefono, toni e chiedi ai chiamanti di registrare il proprio nome.
ms.openlocfilehash: 48925c30d9ac42c76b6f00d8416d767c6e0ab14d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823045"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Modificare le impostazioni per un bridge per audioconferenza

Quando configuti Audioconferenza in Microsoft 365 o Office 365, riceverai i numeri di telefono per gli utenti da un bridge di audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono. Questi numeri di telefono vengono utilizzati quando i chiamanti accedono a una riunione tramite telefono. Il numero di telefono è incluso nella parte inferiore dell'invito alla riunione Skype for Business o Microsoft Teams.
  
Il bridge di conferenza risponde a una chiamata e richiede al chiamante i comandi vocali utilizzando un operatore automatico riunione e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN. I PIN vengono assegnati agli organizzatori della riunione per consentire loro di avviare una riunione quando non usano un Skype for Business o un'app Microsoft Teams.

  > [!IMPORTANT]
  > Il PIN è necessario per l'organizzatore della riunione solo quando un utente dell'app Skype for Business o Microsoft Teams non ha già avviato la riunione. Se tutti gli utenti accedono alla riunione, il PIN è necessario perché l'organizzatore della riunione avvii la riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>Utilizzo dell'interfaccia di amministrazione di Microsoft Teams.

1. Nel riquadro di spostamento sinistro passare a **Ponti conferenza** **riunioni** > .

2. Nella parte superiore della pagina **Bridge conferenza** fare clic su **Impostazioni bridge**.

3. Nel riquadro **Impostazioni bridge** seleziona:
   - **Notifiche di entrata e uscita da una riunione** Se si disattiva questa opzione, gli utenti che hanno già eseguito l'accesso alla riunione non riceveranno una notifica quando qualcuno entra o esce dalla riunione.

     Quando si attivano **le notifiche di entrata e uscita da una riunione**, è possibile selezionare queste opzioni:

   - **Nomi o numeri di telefono** Quando gli utenti accedono a una riunione tramite telefono, il loro numero di telefono viene riprodotto quando accedono alla riunione.

   - **Toni** Quando gli utenti accedono a una riunione, viene riprodotto un tono audio quando accedono alla riunione.

   - **Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Se si disattiva questa opzione, ai chiamanti non verrà chiesto di registrare il proprio nome prima di partecipare a una riunione.

4. Per impostare la lunghezza del PIN per le riunioni, seleziona il numero di cifre desiderato per il PIN nell'elenco **Lunghezza PIN** .

5. Per specificare se inviare posta elettronica agli utenti, abilitare o disabilitare **l'invio automatico di messaggi di posta elettronica agli utenti in caso di modifica della configurazione dei servizi di audioconferenza**.
    Per altre informazioni, vedere [Messaggi di posta elettronica inviati automaticamente agli utenti quando le impostazioni di Audioconferenza cambiano in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) o [Messaggi di posta elettronica inviati agli utenti quando le impostazioni cambiano in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change).

6. Fare clic su **Salva**.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questo processo, puoi utilizzare il cmdlet [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) .

- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell offre molti vantaggi in fatto di velocità, semplicità e produttività rispetto all'uso della interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:

  - [Introduzione a Windows Powershell e Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Uso di Windows PowerShell per gestire Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1)
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare Audioconferenza per Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurare Audioconferenza per Skype for Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
