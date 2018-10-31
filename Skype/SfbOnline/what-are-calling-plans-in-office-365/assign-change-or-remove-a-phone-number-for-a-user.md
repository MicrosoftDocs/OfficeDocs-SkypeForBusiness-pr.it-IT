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
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Informazioni su come assegnare, modificare o rimuovere un numero di telefono per utenti di Skype for Business in modo che le aziende e i clienti esterni li possano chiamare.
ms.openlocfilehash: a522e4fd6cbd41c34b2547ab6be0f7590de0a8b3
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23860592"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Assegnare, modificare o rimuovere il numero di telefono di un utente

Quando imposti i piani di chiamata in Office 365, assegni i numeri di telefono ai tuoi utenti. 

Nel client di Microsoft Teams, il numero di telefono assegnato verrà elencato quando si fa clic su **Chiama**.

![Numero di telefono dell'utente visualizzato in Microsoft Teams.](../images/teams-phone-number.png)

Nel client di Skype for Business, il numero di telefono assegnato verrà elencato nella casella **Telefono ufficio** e non può essere modificato da un utente.
  
![Il numero di telefono Ufficio è ombreggiato.](../images/5212fa64-b55c-4398-9709-a334f3ffa749.png)
  
> [!IMPORTANT]
> Se un utente desidera [modificare il proprio numero di telefono per Skype for Business](https://support.office.com/article/20e03cc1-c023-4e5d-bafd-064ddb59ed5e) e il numero di telefono nell'app Skype for Business non può essere modificato o è ombreggiato, ciò significa che gli amministratori lo hanno già impostato per l'utente e non può essere modificato da quest'ultimo.
  


Quando imposti la possibilità per gli utenti di effettuare e ricevere chiamate telefoniche, è necessario innanzitutto utilizzare l'interfaccia di amministrazione di Skype for Business e assegnare un numero di telefono, ma è possibile modificarlo o rimuoverlo se necessario.
  
Per informazioni su come ottenere Piani di chiamata in Office 365 e il relativo costo, consulta [Licenze per componenti aggiuntivi per Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
> [!NOTE]
> Un modo per verificare se un utente dispone di una licenza assegnata è andando su **Interfaccia di amministrazione di Skype for Business** > **Voce** > **Utenti Voce** e selezionare l'utente. Se viene assegnata una licenza, verrà notificata in **Licenza assegnata**. Puoi anche utilizzare l'interfaccia di amministrazione di Office 365. 
  
 ## <a name="assign-a-phone-number-to-a-user"></a>Assegnare un numero di telefono a un utente
 
![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**
 
1. Accedi a Office 365 con l'account aziendale o scolastico.
    
2. Vai su **interefaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business**.
    
3. Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.**** > ****
   > [!NOTE]
 Per visualizzare l'opzione **Voce** nella barra di navigazione sinistra dell'interfaccia di amministrazione di Skype for Business, è necessario acquistare almeno una **licenza Enterprise E5**, una licenza per il componente aggiuntivo **Sistema telefonico** o una licenza per il componente aggiuntivo **Audioconferenza**.
 
   
    
4. Nella pagina **Utenti vocali**, individua e seleziona l'utente o gli utenti a cui vuoi assegnare un numero di telefono.
    
5. Nel riquadro Azione, seleziona **Assegna numero**.
    
6. Nella pagina **Assegna numero** nella lista **Seleziona il numero da assegnare**, scegli il numero di telefono per l'utente.
    
    > [!TIP]
    > Se non riesci a visualizzare nessun numero di telefono nell'elenco, devi prima [Ottenere numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md). Oppure, utilizzando la pagina **Interfaccia di amminstrazione Skype per Business** > **Voce** > **Numeri di telefono**, fai clic su **Aggiungi** e quindi fai clic su **Nuovi numeri utente**. 
  
7. Per assegnare o modificare l'indirizzo di emergenza associato, vai su **Selezionare luogo di emergenza approvato**, seleziona il luogo dall'elenco oppure, se hai molti luoghi definiti, immetti il nome della città nella casella di ricerca e fai clic su **Cerca**.
    
8. Una volta selezionato il numero di telefono e il luogo di emergenza, fai clic su **Salva**.
    
    > [!NOTE]
    > A causa della latenza tra Office 365 e Skype for Business Online, talvolta sono necessarie fino a 24 ore per abilitare gli utenti. Se dopo 24 ore il numero di telefono non è assegnato correttamente, per favore [Contatta il supporto per i prodotti per aziende - Guida amministratore](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Siamo qui per aiutarti! 
  


 ## <a name="change-a-phone-number-for-a-user"></a>Modificare un numero di telefono di un utente
 
![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**
 
1. Accedi a Office 365 con l'account aziendale o scolastico.
    
2. Vai su **interefaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business**.
    
3. Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.**** > ****
    
4. Nella pagina ** Utenti vocali** , individua e seleziona l'utente o gli utenti a cui vuoi assegnare un numero di telefono.
    
5. Nel riquadro Azioni, su **Numero assegnato**, fai clic su **Cambia**. 
    
6. Nella pagina **Assegna numero**, fai clic su **Modifica numero**.
    
7. Nella pagina **Assegna numero** su **Seleziona numero da assegnare**, utilizza l'elenco per selezionare il nuovo numero di telefono. 
    
8. Per modificare l'indirizzo di emergenza associato, fai clic su **Modifica luogo**e quindi su **Modifica l'indirizzo di emergenza**, selezionando il percorso dall'elenco oppure, se hai molti luoghi definiti, immetti il nome della città nella casella di ricerca e fai clic su **Cerca**.
    
9. Fai clic su **Salva**.
    


 ## <a name="remove-a-phone-number-from-a-user"></a>Rimozione di un numero di telefono da un utente
 
![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**
 
1. Accedi a Office 365 con l'account aziendale o scolastico.
    
2. Vai su **interefaccia di amministrazione di Office 365** > **Interfacce di amministrazione** > **Skype for Business**.
    
3. Nella barra di navigazione sinistra fai clic su VoceUtenti Voce.**** > ****
    
4. Nella pagina **Utenti voce**, individua e seleziona l'utente o gli utenti a cui vuoi rimuovere un numero di telefono.
    
5. Nel riquadro Azioni, su **Numero assegnato**, fai clic su **Rimuovi**. 
    
6. Nella pagina **Vuoi rimuovere il numero assegnato selezionato?** fai clic su **Sì**.
    

## <a name="related-topics"></a>Argomenti correlati
[Cos'è la convalida dell'indirizzo?](what-is-address-validation.md)

[Gestire i numeri di telefono per la propria organizzazione](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termini e condizioni per le chiamate al numero di emergenza](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 