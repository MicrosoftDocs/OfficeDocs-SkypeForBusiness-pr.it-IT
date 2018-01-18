---
title: Spostamento di provider di servizi di conferenza audio di un utente a Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Modificare il Skype per gli utenti aziendali dal provider di terze parti audioconferenza (ACP) a un provider di conferenze telefoniche con Microsoft. '
ms.openlocfilehash: 79697299ce2c3e3fa398150cd300e305ef0c672a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a>Spostamento di provider di servizi di conferenza audio di un utente a Microsoft

Per utilizzare audioconferenze con accesso esterno in Office 365 con Skype per le aziende e Teams Microsoft, è necessario impostare gli utenti dell'organizzazione necessita di una licenza di **Audioconferenza** assegnata a loro e i provider di servizi di conferenza audio a Microsoft. Per ulteriori informazioni sulla gestione delle licenze e sul costo, vedere [prova o acquisto audioconferenza in Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a>Per spostare il provider di conferenza audio di un utente a Microsoft

Se una licenza di **Accesso esterno alle audioconferenze** è assegnata a un utente che non dispone di un provider, provider dell'utente viene automaticamente impostato su Microsoft e non è necessario eseguire altre operazioni. Se l'utente dispone già di un provider di servizi di conferenza audio, è necessario modificare provider dell'utente a Microsoft dopo l'assegnazione di una licenza di **Audioconferenza** .
  
Per configurare Microsoft come provider di audioconferenza per un utente che dispone di una licenza di **Audioconferenza** assegnati ma utilizza un altro provider di servizi di conferenza audio, eseguire questa operazione:
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. In **Skype per interfaccia di amministrazione di Business**, passare a **conferenze Audio**.
    
4. Se viene visualizzata un'intestazione di notifica che indica che non vi sono utenti che dispongono di un' **Audioconferenza** licenza assegnata ma non dispone di Microsoft impostato come i provider di servizi di conferenza audio sono ancora stati, fare clic **qui per spostarli**. Se non viene visualizzata l'intestazione, in **Skype per Business admin center** fare clic su **utenti**e quindi selezionare il filtro **utenti pronti a conferenze Audio** .
    
5. Selezionare gli utenti da spostare e quindi nel riquadro azioni fare clic su **Modifica**.
    
6. Selezionare **Microsoft** nell'elenco **nome del Provider** .
    
    > [!NOTE]
    > Quando il provider di servizi di conferenza audio di un utente viene modificato in Microsoft, le informazioni di accesso esterno alle audioconferenze dell'utente verranno modificato. Se è necessario conservare tali informazioni, visitare registrarlo in un punto qualsiasi prima di modificare il provider di uno degli utenti. 
  
7. Fare clic su **Salva**.
    
## <a name="what-else-should-i-know"></a>Quali altre informazioni sono necessarie?

- Se si seleziona l'utente nell'elenco, è possibile visualizzare le informazioni di audioconferenza predefinito dell'utente, ma non sarà in grado di visualizzare il PIN per conferenze audio. È possibile reimpostare il PIN di un utente per conferenze audio facendo clic su **Reimposta**.
    
- Se si desidera modificare le impostazioni di conferenza audio di un utente, si può selezionare l'utente dall'elenco e quindi fare clic su **Modifica** e apportare le modifiche desiderate nella pagina delle **proprietà** . 
    
## <a name="related-topics"></a>Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)
  

