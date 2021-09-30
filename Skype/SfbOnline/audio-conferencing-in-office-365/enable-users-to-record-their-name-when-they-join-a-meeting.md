---
title: Consentire agli utenti di registrare il proprio nome quando aderiscono a una riunione in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Scopri come abilitare o disabilitare se gli utenti possono registrare i loro nomi quando aderiscono a una riunione in Skype for Business online.
ms.openlocfilehash: 6f1c6c5d582665f411eaa17b76e7c1922ee9e468
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012950"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Consentire agli utenti di registrare il proprio nome quando aderiscono a una riunione in Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Se desideri consentire agli utenti di registrare i nomi su Teams, consulta [Consentire agli utenti di registrare il proprio nome quando partecipano a una riunione su Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Quando si configurano le audioconferenze in Microsoft 365 o Office 365, si riceveranno i numeri di telefono e il cosiddetto bridge di audioconferenza. Un bridge di conferenza può contenere uno o più numeri di telefono che possono essere un numero di telefono dedicato o condiviso.
  
Il bridge di conferenza risponde alla chiamata di un utente che sta eseguendo l'accesso a una riunione con il telefono. Il bridge risponde con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, richiedere ai chiamanti di registrare il proprio nome e configurare le opzioni di sicurezza del PIN per gli organizzatori della riunione. I PIN sono assegnati a un organizzatore della riunione per consentire l'avvio della stessa. Puoi comunque configurarla in modo tale che non sia richiesto il PIN per l'avvio.

## <a name="set-whether-callers-should-record-their-name"></a>Impostare se i chiamanti devono registrare il proprio nome
    
1. **Nell'interfaccia di amministrazione di Skype for Business,** nel riquadro di spostamento sinistro, vai a Impostazioni bridge Microsoft per   >  **audioconferenze.**
    
2. In **Esperienza di partecipazione alla riunione** vedere la casella di controllo Abilita l'attivazione delle notifiche di entrata e uscita dalla **riunione.**
    
   - Ai chiamanti **selezionati** viene chiesto di registrare il proprio nome prima di accedere alla riunione. Questa opzione è selezionata per impostazione predefinita.
    
   - Ai chiamanti **deselezionati** non viene chiesto di registrare il proprio nome prima di accedere alla riunione.
    
3. Dopo aver apportato le modifiche, fai clic su **Salva**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile usare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShell riguarda la gestione degli utenti e le operazioni consentite agli utenti. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti: 
    
  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft all'indirizzo Scaricare e installare [il modulo di PowerShell di Teams.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
