---
title: Attivare o disattivare gli annunci di entrata e di uscita per le riunioni di Teams.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
- seo-marvel-apr2020
description: Informazioni per gli amministratori su come attivare o disattivare gli annunci di entrata e di uscita per le riunioni di Microsoft Teams.
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372205"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Attivare o disattivare gli annunci di entrata e di uscita per le riunioni di Microsoft Teams.

Quando viene impostata Audioconferenza in Microsoft 365 o Office 365, si ottieni un bridge di audioconferenza. Un bridge di audioconferenza può contenere uno o più numeri di telefono che le persone utilizzano per partecipare a una riunione Microsoft Teams.
  
Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono. Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza. Viene assegnato un PIN all’organizzatore della riunione di Microsoft Teams, che permette di avviare la riunione se i partecipanti non possono farlo tramite l'app di Microsoft Teams. È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Impostazione delle opzioni di partecipazione alla riunione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**

Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.

1. Accedere all'interfaccia di amministrazione.

2. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

3. Nella parte superiore della pagina **Bridge di conferenza** fare clic su **Impostazioni bridge**.

4. Nel riquadro **Impostazioni bridge**, abilitare o disabilitare **Notifiche di entrata e di uscita per le riunioni**. Questa opzione è selezionata per impostazione predefinita. Se si deseleziona l’opzione, gli utenti che partecipano alla riunione non verranno avvisati quando un utente entra o esce dalla riunione.

5. Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.

   > [!NOTE]
   > Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti che hanno eseguito l'accesso tramite telefono. Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams.

6. Se si è scelto **Nomi o numeri di telefono**, abilitare o disabilitare **Chiedere ai chiamanti di registrarne il nome prima di partecipare alla riunione**.

7. Fare clic su **Salva**.

## <a name="want-to-know-more-about-windows-powershell"></a>Per altre informazioni su Windows PowerShell

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](https://go.microsoft.com/fwlink/?LinkId=525142)

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Argomenti correlati

[Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
