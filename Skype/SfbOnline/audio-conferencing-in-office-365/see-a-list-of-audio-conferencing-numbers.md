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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come cercare i numeri di conferenza telefonica con accesso esterno all'interno di Skype for Business online. "
ms.openlocfilehash: 118b929f16f0c6edf5c512ddc9b94529a34a8860
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861150"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Visualizzare un elenco di numeri per Audioconferenza in Skype for Business online

> [!NOTE]
> Per informazioni sui numeri per Audioconferenza in Microsoft Teams, consulta [Visualizzare un elenco di numeri per Audioconferenza in Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams) .

Quando imposti un'Audioconferenza per gli utenti di Skype for Business, è possibile visualizzare i numeri di telefono disponibili per Audioconferenza. Questo elenco conterrà tutti i numeri di telefono per Audioconferenza disponibili per l'organizzazione.
  
 **Stai cercando i prezzi?** Consulta [Prezzi per Audioconferenza](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Non esiste una risorsa che contenga un elenco di tutti i numeri con accesso esterno per Audioconferenza.** Per scoprire se nel tuo paese/area geografica sono disponibili dei numeri di telefono con accesso esterno, vai all'**Interfaccia di amministrazione di Skype for Business** > **Voce** > **Numeri di telefono**, fai clic su **Aggiungi** e quindi fai clic su **Nuovi numeri di servizio**. Utilizza gli elenchi per **paese/area geografica**, **stato/regione**, e **città** per filtrare la ricerca. Inoltre, se stai cercando dei numeri di servizio gratuiti, seleziona **Numero verde** dall’elenco **Stato/regione**.
  
Se è disponibile un solo numero di telefono all'interno dell'organizzazione, questo verrà utilizzato come numero predefinito per tutti gli utenti. Quando sono disponibili più numeri di telefono, è possibile selezionare il numero di telefono predefinito per ogni utente. Questo numero predefinito verrà incluso negli inviti alle riunioni di Skype for Business.
  
È possibile consultare [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md) per modificare il numero di telefono di accesso esterno per un singolo utente.
  
> [!NOTE]
> I numeri nazionali di accesso esterno sono dedicati all'organizzazione e sono gli unici che possono essere impostati come numero di telefono predefinito. Tuttavia, i numeri internazionali di accesso esterno possono essere condivisi tra più organizzazioni. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>Per visualizzare i numeri di telefono per Audioconferenza

1. Accedi a Office 365 con l'account aziendale o scolastico.
    
2. Passa all' **Interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nell'**Interfaccia di amministrazione di Skype for Business**, nella barra di navigazione sinistra, vai su **Audioconferenza** > **Ponte Microsoft** e in seguito:
    
  - È possibile visualizzare i numeri di telefono disponibili per Audioconferenza.
    
  - È inoltre possibile visualizzare la posizione e le lingue principale e secondaria che verranno utilizzate dall'operatore automatico di Audioconferenza.
    
> [!NOTE]
> Puoi andare su **Audioconferenza** > **Utenti** e selezionare le proprietà dell'utente per modificare il numero predefinito scegliendo un nuovo numero dall'elenco di numeri disponibili nella tua organizzazione. Consulta [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Vuoi sapere come gestire queste operazioni con Windows PowerShell?

- Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691).
    
- Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:
    
  - [Sei motivi per utilizzare Windows PowerShell per gestire Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Modi migliori per gestire Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:
    
  - [Introduzione a Windows Powershell e Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Uso di Windows PowerShell per gestire Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Argomenti correlati

[Provare o acquistare le audioconferenze in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
