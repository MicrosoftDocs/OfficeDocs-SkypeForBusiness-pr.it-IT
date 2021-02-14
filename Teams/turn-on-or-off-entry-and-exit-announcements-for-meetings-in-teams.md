---
title: Attivare o disattivare gli annunci di tipo Entrata e Uscita per le riunioni in Teams
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
description: L'amministratore può scoprire come attivare o disattivare gli annunci di tipo Entrata e Uscita in una riunione di Microsoft Teams.
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372205"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Attivare o disattivare gli annunci di tipo Entrata e Uscita per le riunioni in Microsoft Teams

Quando si configurano le audioconferenze in Microsoft 365 o Office 365, si ottiene un bridge di audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono che le persone useranno per accedere a una riunione di Microsoft Teams.
  
Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono. Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza. Il PIN viene assegnato a un organizzatore di una riunione di Microsoft Teams e consente di avviare una riunione se non è possibile avviare la riunione con l'app Microsoft Teams. È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Impostazione delle opzioni di partecipazione alla riunione

![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**

Per apportare queste modifiche, è necessario essere un amministratore dei servizi di Teams. Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) e leggere come ottenere i ruoli di amministratore e le autorizzazioni.

1. Accedere all'interfaccia di amministrazione.

2. Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.**

3. Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.**

4. Nel riquadro **Impostazioni bridge abilitare o** disabilitare le notifiche di accesso e uscita da una **riunione.** Questa opzione è selezionata per impostazione predefinita. Se la deseleziona, gli utenti che hanno già partecipato alla riunione non verranno avvisati quando qualcuno entra o esce dalla riunione.

5. Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.

   > [!NOTE]
   > Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti con accesso esterno. Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams.

6. Se scegli Nomi **o numeri di telefono,** abilita o disabilita Chiedi ai chiamanti di **registrare il proprio nome prima di partecipare alla riunione.**

7. Fare clic su **Salva**.

## <a name="want-to-know-more-about-windows-powershell"></a>Per saperne di più su Windows PowerShell

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:

- [Perché è necessario usare PowerShell di Microsoft 365 o Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)
  
## <a name="related-topics"></a>Argomenti correlati

[Domande ricorrenti sulle audioconferenze](audio-conferencing-common-questions.md)
