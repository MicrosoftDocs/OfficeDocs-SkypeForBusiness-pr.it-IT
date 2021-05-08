---
title: Amministratori Configurare le Skype for Business per singoli utenti
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Informazioni su come modificare le impostazioni Skype for Business per singoli utenti, ad esempio audio e videoconferenze, registrazione di chiamate e riunioni. '
ms.openlocfilehash: 0123f285101b8d7190dd7450ddb876a136de13ce
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237532"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> L Microsoft Teams di amministrazione ha sostituito l'Skype for Business di amministrazione (portale legacy). Tutte le impostazioni per la Skype for Business sono ora disponibili nell'Teams di amministrazione. È necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) di Amministratore globale o amministratore Skype for Business per gestire Skype for Business funzionalità di Teams di amministrazione. Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

Questo articolo spiega come gli amministratori configurano Skype for Business per un numero limitato di utenti. Per eseguire questa procedura in blocco, sono stati inclusi collegamenti ai Windows PowerShell cmdlet che è possibile usare.
  
Per consentire (o bloccare) a tutti gli utenti dell'azienda di comunicare con persone esterne, vedere:
  
- Consentire agli utenti di contattare utenti Skype for Business [esterni:](allow-users-to-contact-external-skype-for-business-users.md)è possibile consentire all'organizzazione di usare funzionalità avanzate di Skype for Business (condividere desktop, cercare utenti online e così via) per comunicare con persone in una specifica azienda attendibile (federata). L'articolo spiega anche come bloccare la comunicazione con domini specifici.
    
- [Consentire Skype for Business utenti di aggiungere Skype contatti](let-skype-for-business-users-add-skype-contacts.md). È possibile consentire all'organizzazione di usare Skype for Business per la ricerca e la messaggistica istantanea di persone che usano Skype, l'app gratuita.
    
## <a name="configure-general-settings-for-one-user"></a>Configurare le impostazioni generali per un utente
<a name="__toc325019204"> </a>

Per eseguire questa [procedura, è](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) necessario disporre delle autorizzazioni di amministratore.

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**
  
1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Scegli **Utenti**.
    
    ![Nell'Skype for Business di amministrazione scegliere Utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Scegliere gli utenti da modificare.
    
5. Nel riquadro destro, scegli **Modifica**.
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Nella pagina **Opzioni** generali selezionare o deselezionare la casella di controllo accanto alle caratteristiche da modificare e quindi scegliere **Salva.**
    
|**Opzione**|**Dettagli**|
|:-----|:-----|
|Audio e video HD  <br/> |Consentire a questa persona di registrare riunioni audio, riunioni audio e video o non consentire loro di pianificare riunioni (nessuna).  <br/> |
|Registrare conversazioni e riunioni  <br/> |Scegli cosa può registrare questa persona.  <br/> Questa opzione non è disponibile con Skype for Business Basic.  <br/> |
|Per la conformità, disattivare le caratteristiche non archiviate  <br/> | Scegliere questa opzione se si è tenuti per legge a conservare le informazioni archiviate elettronicamente. <br/>  Se si seleziona questa opzione, le funzionalità [](/exchange/security-and-compliance/in-place-and-litigation-holds) che non vengono acquisite quando è configurato un blocco sul posto nell'interfaccia di amministrazione Exchange locale. Disattiva le caratteristiche seguenti: <br/>  Trasferimento di file tramite messaggistica istantanea <br/>  Pagine condivise di OneNote <br/>  Annotazioni di PowerPoint <br/> |
   
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [Configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="block-external-communications"></a>Bloccare le comunicazioni esterne
<a name="__toc325019206"> </a>

Dopo aver [Skype for Business](let-skype-for-business-users-add-skype-contacts.md) utenti di aggiungere Skype contatti per tutti gli utenti dell'azienda, è possibile bloccare in modo selettivo le comunicazioni esterne per utenti specifici usando questa procedura.
  
1. Scegliere **Utenti**, selezionare gli utenti di cui si vogliono disabilitare le impostazioni e quindi scegliere **Modifica** ![ modifica ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .
    
2. Scegliere **Comunicazioni esterne** e quindi deselezionare le opzioni appropriate:
    
   - **Utenti Skype for Business** esterni: deselezionare questa casella se non si vuole che l'utente sia in grado di comunicare con Skype for Business utenti nei domini federati.
    
   - **Utenti Skype** esterni: deselezionare questa casella se non si vuole che l'utente sia in grado di comunicare con le persone che usano l'app freeSkype.
    
3. Fare clic su **Salva**.
    
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [Configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Modificare le impostazioni dei servizi di audioconferenza per un utente
<a name="__toc314837483"> </a>

1. Scegliere **Utenti**, selezionare l'utente di cui si desidera modificare le impostazioni di audioconferenza e quindi scegliere **Modifica** ![ modifica ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .
    
2. Scegliere **Audioconferenza,** selezionare il provider di servizi di audioconferenza, digitare o modificare le informazioni richieste e quindi fare clic su **Salva.**
    
|**Impostazioni delle audioconferenze**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegliere il provider nell'elenco.  <br/> |
|**Numero a pagamento** (obbligatorio) <br/> |Per un provider di servizi di audioconferenza di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri come si vuole che vengano visualizzati nelle convocazioni di riunione Skype for Business e Microsoft Teams riunione.  <br/> |
|**Numero verde** <br/> |Per un provider di servizi di audioconferenza di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri come si vuole che vengano visualizzati nelle convocazioni di riunione Skype for Business e Microsoft Teams riunione.  <br/> |
|**ID conferenza e PIN** (obbligatorio) <br/> |Il PIN del partecipante, o codice conferenza, usato per partecipare alle riunioni pianificate da questo utente e fornite da un provider di servizi di audioconferenza di terze parti. Se l'utente usa Microsoft come provider di servizi di audioconferenza, non sarà necessario.  <br/> |
   
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [Impostare i numeri di telefono inclusi in Inviti](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurare il computer per [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Argomenti correlati 

[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
  
