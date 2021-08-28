---
title: Visualizzare un elenco di numeri per Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: "Informazioni su come cercare i numeri di conferenza telefonica con accesso esterno all'interno di Skype for Business online. "
ms.openlocfilehash: 3be641b2a5c4b626f414d1a8ae8ee1b16adc7146
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586034"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Visualizzare un elenco di numeri per Audioconferenza in Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Per informazioni sui numeri per Audioconferenza in Microsoft Teams, consulta [Visualizzare un elenco di numeri per Audioconferenza in Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams) .

Quando imposti un'Audioconferenza per gli utenti di Skype for Business, è possibile visualizzare i numeri di telefono disponibili per Audioconferenza. Questo elenco conterrà tutti i numeri di telefono per Audioconferenza disponibili per l'organizzazione.
  
 **Stai cercando i prezzi?** Vedere [Prezzi per le audioconferenze](https://products.office.com/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Non esiste una risorsa che contenga un elenco di tutti i numeri con accesso esterno per Audioconferenza.** Se si sta cercando di verificare se sono disponibili numeri di telefono per l'accesso esterno nella propria area geografica o paese/area geografica, passare **all'interfaccia** di amministrazione di Skype for Business  >  **Numeri**  >  **vocali Telefono**,  fare clic su Aggiungi e quindi su Nuovi numeri di servizio . Utilizza gli elenchi per **paese/area geografica**, **stato/regione**, e **città** per filtrare la ricerca. Inoltre, se si cercano numeri di servizio gratuiti, selezionare **Numero verde** nell'elenco **Stato/Area** geografica.
  
Se è disponibile un solo numero di telefono all'interno dell'organizzazione, questo verrà utilizzato come numero predefinito per tutti gli utenti. Quando sono disponibili più numeri di telefono, è possibile selezionare il numero di telefono predefinito per ogni utente. Questo numero predefinito verrà incluso negli inviti alle riunioni di Skype for Business.
  
È possibile consultare [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md) per modificare il numero di telefono di accesso esterno per un singolo utente.
  
> [!NOTE]
> I numeri nazionali di accesso esterno sono dedicati all'organizzazione e sono gli unici che possono essere impostati come numero di telefono predefinito. Tuttavia, i numeri internazionali di accesso esterno possono essere condivisi tra più organizzazioni. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Per visualizzare i numeri di telefono per Audioconferenza

1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Passare all'interfaccia di amministrazione > **Skype for Business**.
    
3. **Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Bridge Microsoft **per audioconferenze**  >  e quindi:
    
   - È possibile visualizzare i numeri di telefono disponibili per le audioconferenze.
    
   - È anche possibile visualizzare la posizione e le lingue principale e secondaria che verranno usate dall'operatore automatico di audioconferenza.
    
> [!NOTE]
> È possibile passare a **Utenti di audioconferenza** e selezionare le proprietà dell'utente per modificare il numero predefinito scegliendo un nuovo numero nell'elenco dei numeri disponibili  >   nell'organizzazione. Vedere [Impostare i numeri di telefono inclusi per gli inviti.](set-the-phone-numbers-included-on-invites.md) 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile usare il cmdlet [Get-CsOnlineDialInConferencingServiceNumber.](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber)
    
- Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare. Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:
    
  - [Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per gestire Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare audioconferenze in Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
