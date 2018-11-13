---
title: Gli amministratori configurare Skype per le impostazioni di Business per singoli utenti
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Informazioni su come modificare Skype per le impostazioni di Business per singoli utenti, ad esempio: conferenze Audio e video, la registrazione delle chiamate e riunioni. '
ms.openlocfilehash: f99c99fc291a2df71a3e47448e3cc8fcf01e371f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295144"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a>Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti

In questo articolo viene illustrato come gli amministratori configurare Skype for Business per un numero limitato di utenti. Per eseguire la procedura seguente in blocco, è stata inclusa collegamenti a è possibile utilizzare i cmdlet di Windows PowerShell.
  
Per consentire o bloccare tutti gli utenti nell'organizzazione di comunicare con utenti esterni, vedere:
  
- [Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](allow-users-to-contact-external-skype-for-business-users.md): È possibile consentire all'organizzazione di utilizzare avanzate Skype per le funzionalità di Business (condivisione desktop, interfaccia per chi è in linea, ecc) comunicare con persone in una determinata attendibili business (federati). L'articolo viene inoltre illustrato come bloccare la comunicazione con i domini specifici.
    
- [Consentire Skype per gli utenti aziendali di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md). È possibile consentire l'organizzazione utilizza Skype per cercare di lavoro e utenti di messaggistica immediata che utilizzano Skype, gratuitamente l'app.
    
## <a name="configure-general-settings-for-one-user"></a>Configurare le impostazioni generali per un utente
<a name="__toc325019204"> </a>

È necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire la procedura seguente.

![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**
  
1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Scegli **Interfaccia di amministrazione** > **Skype for Business**.
    
3. Scegli **Utenti**.
    
    ![Skype per interfaccia di amministrazione di Business, scegliere utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. Scegliere gli utenti che si desidera modificare.
    
5. Nel riquadro destro, scegli **Modifica**.
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Nella pagina Opzioni **Generale** , selezionare o deselezionare la casella di controllo accanto alle funzionalità che si desidera modificare e quindi fare clic su **Salva**.
    
|**Opzione**|**Dettagli**|
|:-----|:-----|
|Audio e video HD  <br/> |Consentire questa persona di registrare le riunioni audio, audio e video alle riunioni o non consentire loro di pianificare qualsiasi meeetings (nessuno).  <br/> |
|Registrare conversazioni e riunioni  <br/> |Scegliere quali questa persona è consentita registrare.  <br/> Questa opzione non è disponibile con Skype per Business Basic.  <br/> |
|Per motivi di conformità, disattivare le funzionalità non archiviate  <br/> | Scegliere questa opzione se si è obbligate per legge a conservare le informazioni archiviate in formato elettronico. <br/>  Se si seleziona questa opzione viene disattivata la funzionalità che non sono state acquisite in presenza di un' [Archiviazione sul posto](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurato nell'interfaccia di amministrazione di Exchange. Disattiva le funzionalità seguenti: <br/>  Trasferimento di file tramite messaggistica istantanea <br/>  Pagine condivise di OneNote <br/>  Annotazioni di PowerPoint <br/> |
   
Per configurare queste impostazioni in blocco, utilizzare PowerShell. Vedere [gestione dei criteri in Skype Business online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).
  
## <a name="block-external-communications"></a>Blocca comunicazioni esterne
<a name="__toc325019206"> </a>

Dopo aver [Skype consente agli utenti aziendali aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) per tutti gli utenti della società, è possibile bloccare in modo selettivo comunicazioni esterne per specifici utenti attenendosi alla procedura seguente.
  
1. Selezione **utenti**, selezionare gli utenti il cui si desidera disabilitare le impostazioni e quindi fare clic su **Modifica** ![modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Scegliere **comunicazioni esterne**e quindi deselezionare le opzioni desiderate:
    
   - **Skype esterna per gli utenti aziendali**: deselezionare questa casella se non si desidera che l'utente di comunicare con Skype per utenti Business nei domini federati.
    
   - **Gli utenti esterni Skype**: deselezionare questa casella se non si desidera che l'utente di comunicare con persone che utilizzano l'app freeSkype.
    
3. Fai clic su **Salva**.
    
Per configurare queste impostazioni in blocco, utilizzare PowerShell. Vedere [gestione delle comunicazioni in Skype Business online con organizzazioni e agli utenti esterni](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a>Modificare le impostazioni di conferenza per un utente
<a name="__toc314837483"> </a>

1. Selezione **utenti**, selezionare l'utente di cui si desidera per modificare, le impostazioni di audioconferenza e quindi fare clic su **Modifica** ![modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
2. Scegliere **servizi di conferenza Audio**, selezionare il provider di servizi di conferenza audio, digitare o modificare le informazioni richieste e quindi fare clic su **Salva**.
    
|**Impostazioni delle audioconferenze**|**Descrizione**|
|:-----|:-----|
|**Nome del provider** <br/> |Scegliere il provider dall'elenco.  <br/> |
|**Numero a pagamento** (obbligatorio) <br/> |Per un'AUDIOCONFERENZA di terze parti, questi numeri di telefono sono forniti dal provider di servizi di conferenza audio. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione.  <br/> |
|**Numero verde** <br/> |Per un'AUDIOCONFERENZA di terze parti, questi numeri di telefono sono forniti dal provider di servizi di conferenza audio. Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza. Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione.  <br/> |
|**ID conferenza e PIN** (obbligatorio) <br/> |Il partecipante PIN o conferenza codice, utilizzato per partecipare a riunioni pianificate dall'utente e vengono fornite da un provider di servizi di conferenza audio di terze parti. Se l'utente sta utilizzando Microsoft come provider di servizi di conferenza audio, questo non sarà necessario.  <br/> |
   
Per configurare queste impostazioni in blocco, utilizzare PowerShell. Vedere [impostare telefono numeri incluso nel invita](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a>Argomenti correlati 

[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 