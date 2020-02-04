---
title: Gli amministratori configurano le impostazioni di Skype for business per singoli utenti
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
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Informazioni su come modificare le impostazioni di Skype for business per singoli utenti, ad esempio: conferenze audio e video, registrazione di chiamate e riunioni. '
ms.openlocfilehash: a384acdadb6ca4df621d45abdde4157df2029619
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706511"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti

Questo articolo spiega in che modo gli amministratori configurano Skype for business per un numero limitato di utenti. Per eseguire questa procedura in blocco, sono stati inclusi collegamenti ai cmdlet di Windows PowerShell che è possibile usare.
  
Per consentire (o bloccare) tutti gli utenti dell'azienda di comunicare con persone esterne, vedere:
  
- [Consentire agli utenti di contattare utenti Skype for business esterni](allow-users-to-contact-external-skype-for-business-users.md): è possibile consentire all'organizzazione di usare le funzionalità avanzate di Skype for business (condivisione di desktop, cercare chi è online e così via) per comunicare con persone in una specifica azienda attendibile (federata). L'articolo spiega anche come bloccare la comunicazione con domini specifici.
    
- [Consentire agli utenti di Skype for business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md). Puoi consentire all'organizzazione di usare Skype for business per cercare e inviare messaggi istantanei agli utenti che usano Skype, l'app gratuita.
    
## <a name="configure-general-settings-for-one-user"></a>Configurare le impostazioni generali per un utente
<a name="__toc325019204"> </a>

Per eseguire questa procedura, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .

![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Scegli **Utenti**.
    
    ![Nell'interfaccia di amministrazione di Skype for Business Scegli utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Scegliere gli utenti che si desidera modificare.
    
5. Nel riquadro destro, scegli **Modifica**.
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Nella pagina Opzioni **generali** selezionare o deselezionare la casella di controllo accanto alle funzionalità che si desidera modificare e quindi scegliere **Salva**.
    
|**Opzione**|**Dettagli**|
|:-----|:-----|
|Audio e video HD  <br/> |Consentire a questa persona di registrare riunioni audio, riunioni audio e video o non consentire loro di programmare riunioni (nessuna).  <br/> |
|Registrare conversazioni e riunioni  <br/> |Scegliere ciò che questa persona può registrare.  <br/> Questa opzione non è disponibile con Skype for Business Basic.  <br/> |
|Per la conformità, disattivare le funzionalità non archiviate  <br/> | Scegliere questa opzione se si è legalmente tenuti a conservare le informazioni archiviate elettronicamente. <br/>  Se si seleziona questa opzione, vengono disattivate le funzionalità non acquisite quando si dispone di un [blocco sul posto](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) nell'interfaccia di amministrazione di Exchange. Vengono disattivate le caratteristiche seguenti: <br/>  Trasferimento di file tramite messaggistica istantanea <br/>  Pagine condivise di OneNote <br/>  Annotazioni di PowerPoint <br/> |
   
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="block-external-communications"></a>Bloccare le comunicazioni esterne
<a name="__toc325019206"> </a>

Dopo aver [lasciato gli utenti di Skype for business ad aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) per tutti i membri della società, è possibile bloccare selettivamente le comunicazioni esterne per individui specifici con questi passaggi.
  
1. Scegliere **utenti**, selezionare gli utenti di cui si vogliono disabilitare le impostazioni e quindi scegliere **modifica** ![modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Scegliere **comunicazioni esterne**e quindi deselezionare le opzioni appropriate:
    
   - **Utenti Skype for business esterni**: deselezionare questa casella se non si vuole che l'utente possa comunicare con gli utenti di Skype for business nei domini federati.
    
   - **Utenti Skype esterni**: deselezionare questa casella se non si vuole che l'utente possa comunicare con utenti che usano l'app freeSkype.
    
3. Fai clic su **Salva**.
    
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Modificare le impostazioni dei servizi di audioconferenza per un utente
<a name="__toc314837483"> </a>

1. Scegliere **utenti**, selezionare l'utente di cui si desidera modificare le impostazioni di conferenza audio da usare e **** ![quindi scegliere](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)modifica modifica.
    
2. Scegliere **audioconferenza**, selezionare il proprio provider di servizi di audioconferenza, digitare o modificare le informazioni richieste e quindi fare clic su **Salva**.
    
|**Impostazioni delle audioconferenze**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegliere il provider dall'elenco.  <br/> |
|**Numero a pagamento** (obbligatorio) <br/> |Per gli ACP di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri che si desidera vengano visualizzati in richieste di riunione di Skype for business e Microsoft teams.  <br/> |
|**Numero verde** <br/> |Per gli ACP di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri che si desidera vengano visualizzati in richieste di riunione di Skype for business e Microsoft teams.  <br/> |
|**ID conferenza e pin** (obbligatorio) <br/> |Il PIN partecipante o il codice conferenza usato per partecipare alle riunioni pianificate da questo utente e fornite da un provider di servizi di audioconferenza di terze parti. Se l'utente usa Microsoft come provider di servizi di audioconferenza, non sarà necessario.  <br/> |
   
Per configurare queste impostazioni in blocco, usare PowerShell. Vedere [impostare i numeri di telefono inclusi in invita](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Argomenti correlati 

[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
  
 
