---
title: Assegnazione di terze parti come provider di servizi di conferenza audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Informazioni su come configurare di terze parti come provider di servizi di conferenza telefonica con Skype per le aziende. '
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a>Assegnazione di terze parti come provider di servizi di conferenza audio

Un provider di servizi di conferenza audio fornisce di *ponte conferenza*. Bridge conferenza fornisce il numero di telefono di accesso esterno, pin e gli ID conferenza per le riunioni creati. È sufficiente assegnare un provider di servizi di conferenza audio a coloro che desidera programmare o lead Skype per le riunioni aziendali o Microsoft Teams.
  
> [!NOTE]
> Per Microsoft Teams, un utente non può utilizzare un provider di servizi di conferenza audio di terze parti, devono utilizzare audioconferenze con accesso esterno in Office 365, che imposta il provider di servizi di conferenza audio a Microsoft. 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a>Passaggi da eseguire prima di poter assegnare un provider di servizi di conferenza audio di terze parti

1. A seconda del piano di Office 365, potrebbe essere necessario acquistare le licenze di componente aggiuntivo **Per conferenze Audio** per gli utenti dell'organizzazione che desiderano programmare o lead Skype per Business o Microsoft Teams riunioni tramite servizi di conferenza Audio. Per ulteriori informazioni, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
2. Se è stato acquistato licenze di componente aggiuntivo **Per conferenze Audio** , assegnarli a utenti all'interno dell'organizzazione che desiderano programmare o condurre riunioni che utilizzano i servizi di conferenza Audio. Vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
    > [!NOTE]
    > Se si assegna una licenza di **Audioconferenza** a un utente **AFTER** assegnarle un provider di servizi di conferenza audio di terze parti, tale persona viene automaticamente impostata su invece utilizzare Microsoft come i provider di servizi di conferenza audio! In questo caso, è necessario rimuovere Microsoft come provider di servizi di conferenza audio prima di poter assegnare un provider di servizi di conferenza audio di terze parti a loro.
  
3. Trova un provider di servizi di conferenza audio di terze parti a [Individuare Microsoft](https://go.microsoft.com/fwlink/?LinkId=797530). Contattarli e Scopri come realizzare gli obiettivi impostare con loro.
    
    Si sono disponibili:
    
  - **Numeri di accesso (numero verde)** e numeri verdi, se disponibile.
    
  - **ID conferenza** utilizzati per ogni persona che pianifica le riunioni. Alcuni audioconferenza chiama tali passcode di conferenza.
    
    > [!NOTE]
    > Se è stato fatto iniziale impostata per un'AUDIOCONFERENZA di terze parti ma adesso è necessario apportare modifiche, nella parte inferiore della pagina **Microsoft Bridge** **fare clic qui per configurare un provider di servizi di conferenza audio di terze parti**. 
  
    > [!NOTE]
    > Quando si abilita una persona per le conferenze audio e assegna loro un provider di servizi di conferenza audio di terze parti, i numeri di audio e gli ID conferenza (passcode) vengono aggiunte automaticamente qualsiasi **nuova** Skype per le riunioni Online Business creati.
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a>Come assegnare a un provider di servizi di conferenza audio di terze parti a un utente

1. **Skype per interfaccia di amministrazione di Business**, scegliere **utenti**. Selezionare l'utente dall'elenco e fare clic su **Modifica** nel riquadro azioni.
    
2. Nella pagina proprietà dell'utente, fare clic su **servizi di conferenza Audio** e immettere le informazioni:
    
  - **Nome del provider** Nell'elenco, selezionare il provider di terze parti.
    
  - **Numero verde predefinito** È richiesto.
    
  - **Numero verde predefinito** Ciò non necessari.
    
  - **ID conferenza** Viene fornito dal provider di servizi di conferenza audio.
    
3. Fare clic su **Salva**.
    
4. Inviare il PIN è stato ricevuto dal provider di servizi di conferenza audio ogni contatto. Il PIN potrebbe essere necessario chiamare l'organizzatore della conferenza telefonica o coordinatore.
    
    > [!NOTE]
    > Quando si utilizza un provider di servizi di conferenza audio di terze parti, non vi è un modo visualizzare o impostare i pin per conto degli organizzatori di riunioni. 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a>Come assegnare a un provider di servizi di conferenza audio di terze parti a molte persone alla stessa ora

1. **Skype per interfaccia di amministrazione di Business**, scegliere **audioconferenze** > **bridge di Microsoft**. Nella parte inferiore della pagina, fare clic sul collegamento di **Se si desidera configurare un provider di servizi di conferenza audio di terze parti in realtà, fare clic qui**.
    
    > [!NOTE]
    > Se è stato fatto iniziale impostata per un'AUDIOCONFERENZA di terze parti ma adesso è necessario apportare modifiche, nella parte inferiore della pagina **Microsoft Bridge** , **fare clic qui per configurare un provider di servizi di conferenza audio di terze parti**. 
  
2. Nella pagina **Configura una terza parte del provider di servizi di conferenza audio** , in **utenti importazione ed esportazione**, fare clic su **Esportazione guidata**e quindi seguire la procedura **guidata utenti di esportazione**. Al termine, è necessario un file in cui sono elencate le persone che si desidera impostare per le conferenze audio.
    
3. Inviare il file creato al provider di servizi di conferenza audio di terze parti. Verrà aggiungono informazioni sulle conferenze audio per gli utenti elencati nel file e quindi restituisce il file a un utente.
    
4. Verificare che il file restituito abbia le informazioni corrette in essa contenuti. È stata ascoltare di istanze di cui non tutti i contatti presenti nel file caso è possibile ottenere le informazioni corrette.
    
5. Nella **pagina provider di audioconferenza di terze parti Configure**, in **agli utenti di importazione ed esportazione**, fare clic su **Importazione guidata**e quindi seguire le istruzioni della **procedura guidata Importa utenti**
    
6. Inviare il PIN è stato ricevuto dal provider di servizi di conferenza audio ogni contatto. Il PIN potrebbe essere necessario chiamare l'organizzatore della conferenza telefonica o coordinatore.
    
    > [!NOTE]
    > Quando si utilizza un provider di servizi di conferenza audio di terze parti, non vi è un modo visualizzare o impostare i pin per conto degli organizzatori di riunioni. 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a>Quando utilizzare un provider di servizi di conferenza audio di terze parti

In caso di un paese o regione in audioconferenze con accesso esterno in Office 365 non è disponibile, la qualità del servizio non è grande a causa della posizione o si dispone di un contratto esistente con un provider di servizi di conferenza audio di terze parti, è consigliabile utilizzare un audio di terze parti provider di servizi di conferenza. In caso contrario, è consigliabile utilizzare Microsoft come provider di servizi di conferenza audio.
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a>Automatizzare l'assegnazione il provider di servizi di conferenza audio di terze parti tramite Windows PowerShell

- Per risparmiare tempo o automatizzare questa operazione, è possibile utilizzare il cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) .
    
    > [!NOTE]
    > Per modificare il provider di audio da Microsoft a un provider di servizi di conferenza audio di terze parti, è necessario rimuovere Microsoft come provider di servizi di conferenza audio. A tale scopo, utilizzare il cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .
  
- Per ulteriori informazioni sull'uso di Windows PowerShell, consulta [Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038).
    
## <a name="what-else-do-i-need-to-know"></a>Altre informazioni utili

Una persona all'interno dell'organizzazione può utilizzare solo un provider di servizi di conferenza audio. Per modificare il provider di servizi di conferenza audio di una persona a Microsoft, vedere [Microsoft assegnare come provider di servizi di conferenza audio](assign-microsoft-as-the-audio-conferencing-provider.md)o [lo spostamento di provider di servizi di conferenza audio di un utente a Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) .
  
## <a name="related-topics"></a>Argomenti correlati

[Configurare le audioconferenze per Skype for Business e Microsoft Teams](set-up-audio-conferencing.md)
  
[Configurare Skype for Business online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

