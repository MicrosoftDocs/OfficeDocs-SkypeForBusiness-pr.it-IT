---
title: Assegnare, modificare o rimuovere il numero di telefono di un utente
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Informazioni su come assegnare, modificare o rimuovere un numero di telefono per utenti di Skype for Business in modo che le aziende e i clienti esterni li possano chiamare.
ms.openlocfilehash: 40c067657132781d29b8f20a3738d6d28ce36331
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374659"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Assegnare, modificare o rimuovere il numero di telefono di un utente

Quando è impostata la chiamata dei piani di Office 365, si assegnano i numeri di telefono per gli utenti. 

Nel client di Microsoft Teams, il numero di telefono assegnato verrà elencato quando si fa clic su **Chiama**.

![Numero di telefono dell'utente visualizzato in Microsoft Teams.](../images/teams-phone-number.png)

Nel client di Skype for Business, il numero di telefono assegnato verrà elencato nella casella **Telefono ufficio** e non può essere modificato da un utente.
  
![Il numero di telefono Ufficio è ombreggiato.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> Se un utente desidera [modificare il proprio numero di telefono per Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) e il numero di telefono nell'app Skype for Business non può essere modificato o è ombreggiato, ciò significa che gli amministratori lo hanno già impostato per l'utente e non può essere modificato da quest'ultimo.
  


Quando imposti la possibilità per gli utenti di effettuare e ricevere chiamate telefoniche, è necessario innanzitutto utilizzare l'interfaccia di amministrazione di Skype for Business e assegnare un numero di telefono, ma è possibile modificarlo o rimuoverlo se necessario.
  
Per informazioni su come ottenere Piani di chiamata in Office 365 e il relativo costo, consulta [Licenze per componenti aggiuntivi per Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
> [!NOTE]
> One way to see whether a user has a license assigned is by going to **Skype for Business admin center** > **Voice** > **Voice users** and selecting the user. If a license is assigned, it will be noted under **Assigned license**. You also can use the Office 365 admin center. 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>Assegnare un numero di telefono a un utente
 
![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
 
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **team di Microsoft e Skype per Business Admin Center** > **portale Legacy**.
    
3. Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.**** > ****
   > [!NOTE]
   > Per poter visualizzare l'opzione **vocale** nel riquadro di spostamento sinistra in Skype per interfaccia di amministrazione di Business, è necessario acquistare una licenza di componente aggiuntivo **Per conferenze Audio** , una licenza di componente aggiuntivo di **Sistema telefonico** o almeno una **licenza Enterprise E5**.
 
   
    
4. Nella pagina **Utenti vocali**, individua e seleziona l'utente o gli utenti a cui vuoi assegnare un numero di telefono.
    
5. Seleziona **Assegna numero**.
    
6. Nella pagina **assegnazione numero** nell'elenco **selezionare numero da assegnare** , selezionare il numero di telefono dell'utente.
    
    > [!TIP]
    > Se non viene visualizzata dei numeri di telefono elencati, è necessario [ottenere numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md) prima. Oppure, utilizzando la pagina **Interfaccia di amminstrazione Skype per Business** > **Voce** > **Numeri di telefono**, fai clic su **Aggiungi** e quindi fai clic su **Nuovi numeri utente**. 
  
7. Per assegnare o modificare l'indirizzo di emergenza associato, vai su **Selezionare luogo di emergenza approvato**, seleziona il luogo dall'elenco oppure, se hai molti luoghi definiti, immetti il nome della città nella casella di ricerca e fai clic su **Cerca**.
    
8. Una volta selezionato il numero di telefono e il luogo di emergenza, fai clic su **Salva**.
    
    > [!NOTE]
    > Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for users to be enabled. If after 24 hours, if the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). We're here to help! 
  


 ## <a name="change-a-phone-number-for-a-user"></a>Modificare un numero di telefono di un utente
 
![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
 
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **team di Microsoft e Skype per Business Admin Center** > **portale Legacy**.
    
3. Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.**** > ****
    
4. Nella pagina **utenti dei servizi vocali** , individuare e selezionare l'utente o gli utenti che si desidera modificare un numero di telefono per.
    
5. Nel riquadro azioni, in **numero assegnato**, fare clic su **Cambia**. 
    
6. Nella pagina **Assegna numero**, fai clic su **Modifica numero**.
    
7. Nella pagina **assegnazione numero** nella casella **selezionare numero da assegnare**, utilizzare l'elenco per selezionare il nuovo numero di telefono. 
    
8. Per modificare l'indirizzo di emergenza associato, fai clic su **Modifica luogo**e quindi su **Modifica l'indirizzo di emergenza**, selezionando il percorso dall'elenco oppure, se hai molti luoghi definiti, immetti il nome della città nella casella di ricerca e fai clic su **Cerca**.
    
9. Fai clic su **Salva**.
    


 ## <a name="remove-a-phone-number-from-a-user"></a>Rimozione di un numero di telefono da un utente
 
![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
 
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Vai al **team di Microsoft e Skype per Business Admin Center** > **portale Legacy**.
    
3. Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.**** > ****
    
4. Nella pagina **utenti dei servizi vocali** , individuare e selezionare l'utente o gli utenti che si desidera rimuovere il numero di telefono.
    
5. Nel riquadro azioni, in **numero assegnato**, fare clic su **Rimuovi**. 
    
6. Nella pagina **Vuoi rimuovere il numero assegnato selezionato?** fai clic su **Sì**.
    

## <a name="related-topics"></a>Argomenti correlati
[Cos'è la convalida dell'indirizzo?](what-is-address-validation.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 