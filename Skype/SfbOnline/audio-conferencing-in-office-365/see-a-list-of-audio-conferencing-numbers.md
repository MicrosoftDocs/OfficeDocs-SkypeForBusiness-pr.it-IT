---
title: Visualizzare un elenco di numeri di conferenza Audio Skype Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come cercare i numeri di conferenza telefonica all'interno di Skype Business online. "
ms.openlocfilehash: 84d6f4d1d1d1358a62ec8d0eb2334c92c416adea
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490596"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Visualizzare un elenco di numeri di conferenza Audio Skype Business online

> [!NOTE]
> Per informazioni sui numeri di conferenza Audio in Teams Microsoft, vedere [visualizzare un elenco di numeri di conferenza Audio nel team di Microsoft](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Quando configurare conferenze Audio per Skype per gli utenti aziendali, è possibile visualizzare i numeri di telefono che vengono rese disponibili per le conferenze audio. In questo elenco avrà tutti i numeri di telefono di audioconferenza che sono disponibili nell'organizzazione.
  
 **Cerchi prezzi?** Vedere [prezzi per le conferenze Audio](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Non esiste una risorsa che contenga un elenco di tutti i numeri con accesso esterno per Audioconferenza.** Se si sta cercando di verificare se sono disponibili i numeri di telefono di accesso esterno nell'area o paese/area geografica, andare a **Skype per Business admin center** > **vocale** > **I numeri di telefono**, fare clic su **Aggiungi**e quindi fare clic su nuovo servizio ** Numeri**. Utilizza gli elenchi per **paese/area geografica**, **stato/regione**, e **città** per filtrare la ricerca. Inoltre, se sta cercando numeri verdi assistenza, **numero verde** selezionare dal **paese** elenco.
  
Se esiste un solo numero all'interno dell'organizzazione, verrà utilizzato come il numero predefinito per tutti gli utenti. Quando sono disponibili più numeri di telefono, è possibile selezionare il numero di telefono predefinito per ogni utente. Questo numero predefinito verrà inclusa in Skype per inviti alle riunioni di Business.
  
È possibile visualizzare [impostare telefono invita numeri inclusi in](set-the-phone-numbers-included-on-invites.md) per modificare il numero di telefono di accesso esterno per un singolo utente.
  
> [!NOTE]
> Nazionali numeri dedicati alla propria organizzazione e sono le uniche che possono essere impostate come un numero di telefono predefinito. Tuttavia, internazionali numeri di accesso possono essere condivisi tra più organizzazioni. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Per visualizzare i numeri di telefono di accesso esterno alle audioconferenze

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **bridging Microsoft**e quindi:
    
  - È possibile visualizzare i numeri di telefono disponibili per le conferenze audio.
    
  - È inoltre possibile visualizzare il percorso e le lingue principale e secondarie che verranno utilizzate per le conferenze audio l'operatore automatico.
    
> [!NOTE]
> È possibile accedere ai **servizi di conferenza Audio** > **utenti** e selezionare le proprietà dell'utente per modificare l'impostazione predefinita dei numeri scegliendo un nuovo numero dall'elenco dei numeri disponibili nell'organizzazione. Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) .
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
