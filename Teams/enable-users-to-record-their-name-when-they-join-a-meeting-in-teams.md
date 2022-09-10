---
title: Consentire agli utenti di registrare il proprio nome per una riunione
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: Informazioni su come abilitare o disabilitare l'opzione che consente agli utenti di registrare i propri nomi quando accedono a una riunione in Microsoft Teams.
ms.openlocfilehash: 8d626437d1e7dd04ce8b4f91428bfe22cc3aeb43
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641727"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a>Consentire agli utenti di registrare il proprio nome quando accedono a una riunione in Microsoft Teams

Durante la configurazione delle audioconferenze in Microsoft 365 o Office 365, riceverai numeri di telefono e un bridge per audioconferenze. Un bridge di conferenza può contenere uno o più numeri di telefono che possono essere un numero di telefono dedicato o condiviso.
  
Il bridge di conferenza risponde alla chiamata di un utente che sta eseguendo l'accesso a una riunione con il telefono. Il bridge risponde con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, richiedere ai chiamanti di registrare il proprio nome e configurare le opzioni di sicurezza del PIN per gli organizzatori della riunione. I PIN sono assegnati a un organizzatore della riunione per consentire l'avvio della stessa. Puoi comunque configurarla in modo tale che non sia richiesto il PIN per l'avvio.

## <a name="set-whether-callers-should-record-their-name"></a>Impostare se i chiamanti devono registrare il proprio nome

Usando l'interfaccia di amministrazione di Microsoft Teams:

1. Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.

2. Nella parte superiore della pagina **Conference Bridge** fare clic su **Impostazioni bridge**.

3. Abilitare o disabilitare **le notifiche di accesso e uscita da una riunione**.

4. Se si abilitano le notifiche, scegliere **Nomi o numeri di telefono** in **Tipo di annuncio entrata/uscita** e quindi attivare **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare a una riunione.**

5. Fare clic su **Salva**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a>Vuoi saperne di più su Windows PowerShell?

Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:

- [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Modi migliori per gestire Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).
