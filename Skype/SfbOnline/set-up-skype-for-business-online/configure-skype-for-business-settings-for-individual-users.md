---
title: Gli amministratori configurano le impostazioni di Skype for Business per singoli utenti
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
description: 'Scopri come modificare le impostazioni di Skype for Business per singoli utenti, ad esempio le conferenze audio e video, la registrazione di chiamate e riunioni. '
ms.openlocfilehash: cf54637bda51a7994121035b3db1585213c56c00
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753421"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti

> [!IMPORTANT]
> L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for Business (portale legacy). Tutte le impostazioni per la gestione di Skype for Business sono ora disponibili nell'interfaccia di amministrazione di Teams. Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Teams, è necessario disporre del ruolo di amministratore di [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) come amministratore globale o amministratore di Skype for Business. Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).

Questo articolo spiega come gli amministratori configurano Skype for Business per un piccolo numero di utenti. Per eseguire questi passaggi in blocco, sono stati inclusi collegamenti ai cmdlet di Windows PowerShell che è possibile usare.
  
Per consentire (o bloccare) tutti gli utenti dell'azienda di comunicare con persone esterne, vedere:
  
- Consenti agli utenti di contattare utenti [Skype for Business](allow-users-to-contact-external-skype-for-business-users.md)esterni: puoi consentire alla tua organizzazione di utilizzare le funzionalità avanzate di Skype for Business (condivisione desktop, ricerca di utenti online e così via) per comunicare con persone in una specifica azienda attendibile (federata). L'articolo spiega anche come bloccare le comunicazioni con domini specifici.
    
- [Consentire agli utenti di Skype for Business di aggiungere contatti Skype.](let-skype-for-business-users-add-skype-contacts.md) Puoi consentire alla tua organizzazione di usare Skype for Business per cercare persone che usano Skype e immediare persone che usano l'app gratuita.
    
## <a name="configure-general-settings-for-one-user"></a>Configurare le impostazioni generali per un utente
<a name="__toc325019204"> </a>

Per eseguire questa [procedura, è](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) necessario avere le autorizzazioni di amministratore.

![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**
  
1. Accedere con l'account aziendale o dell'istituto di istruzione.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Scegli **Utenti**.
    
    ![Nell'interfaccia di amministrazione di Skype for Business scegli Utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Scegliere gli utenti da modificare.
    
5. Nel riquadro destro, scegli **Modifica**.
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Nella pagina **Opzioni** generali selezionare o deselezionare la casella di controllo accanto alle caratteristiche da modificare e quindi scegliere **Salva.**
    
|**Opzione**|**Dettagli**|
|:-----|:-----|
|Audio e video HD  <br/> |Consentire a questa persona di registrare riunioni audio, riunioni audio e video o di non consentire di pianificare riunioni (nessuna).  <br/> |
|Registrare conversazioni e riunioni  <br/> |Scegliere cosa è consentito registrare a questa persona.  <br/> Questa opzione non è disponibile con Skype for Business Basic.  <br/> |
|Per conformità, disattivare le funzionalità non archiviate  <br/> | Scegliere questa opzione se è necessario per legge conservare le informazioni archiviate elettronicamente. <br/>  Se si seleziona questa opzione, vengono disattivate [](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) le funzionalità non acquisite quando nell'interfaccia di amministrazione di Exchange è configurato un blocco sul posto. Vengono disattivate le caratteristiche seguenti: <br/>  Trasferimento di file tramite messaggistica istantanea <br/>  Pagine condivise di OneNote <br/>  Annotazioni di PowerPoint <br/> |
   
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [Configurare il computer per Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="block-external-communications"></a>Bloccare le comunicazioni esterne
<a name="__toc325019206"> </a>

Dopo aver [consenti agli utenti di Skype for Business](let-skype-for-business-users-add-skype-contacts.md) di aggiungere contatti Skype per tutti gli utenti dell'azienda, puoi bloccare in modo selettivo le comunicazioni esterne per persone specifiche con questa procedura.
  
1. Scegliere **Utenti,** selezionare gli utenti di cui si vogliono disabilitare le impostazioni e quindi scegliere  ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) Modifica.
    
2. Scegliere **Comunicazioni esterne** e quindi deselezionare le opzioni appropriate:
    
   - **Utenti Skype for Business** esterni: deselezionare questa casella se non si vuole che l'utente possa comunicare con utenti Skype for Business in domini federati.
    
   - **Utenti Skype esterni:** deseleziona questa casella se non desideri che l'utente possa comunicare con persone che usano l'app freeSkype.
    
3. Fare clic su **Salva**.
    
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [Configurare il computer per Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Modificare le impostazioni di audioconferenza per un utente
<a name="__toc314837483"> </a>

1. Scegli **Utenti,** seleziona l'utente di cui vuoi modificare le impostazioni per i servizi di audioconferenza, quindi scegli  ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) Modifica.
    
2. Scegli **Audioconferenza,** seleziona il provider di servizi di audioconferenza, digita o modifica le informazioni richieste, quindi fai clic su **Salva.**
    
|**Impostazioni delle audioconferenze**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegliere il provider nell'elenco.  <br/> |
|**Numero a pagamento** (obbligatorio) <br/> |Per un provider di servizi di audioconferenza di terze parti, questi sono i numeri ricevuti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri nel modo in cui si vuole che vengano visualizzati nelle convocazioni riunione di Skype for Business e Microsoft Teams.  <br/> |
|**Numero verde** <br/> |Per un provider di servizi di audioconferenza di terze parti, questi sono i numeri ricevuti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri nel modo in cui si vuole che vengano visualizzati nelle convocazioni riunione di Skype for Business e Microsoft Teams.  <br/> |
|**ID conferenza e PIN** (obbligatorio) <br/> |IL PIN del partecipante, o codice conferenza, utilizzato per partecipare alle riunioni pianificate da questo utente e fornite da un provider di servizi di audioconferenza di terze parti. Se l'utente utilizza Microsoft come provider di servizi di audioconferenza, questa operazione non sarà necessaria.  <br/> |
   
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [Impostare i numeri di telefono inclusi nell'invito](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurare il computer per [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Argomenti correlati 

[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
  
 
