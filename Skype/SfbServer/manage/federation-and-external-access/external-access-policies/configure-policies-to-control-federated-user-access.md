---
title: Configurare i criteri per controllare l'accesso degli utenti federati
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Quando si configurano criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti dei domini federati. '
ms.openlocfilehash: 2b7976492fe4f789c2f3130fb51deaaef44af701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817306"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configurazione dei criteri per il controllo dell'accesso degli utenti federati in Skype for Business Server

Quando si configurano criteri per supportare le comunicazioni con partner federati, i criteri si applicano agli utenti dei domini federati. È possibile configurare uno o più criteri di accesso utente esterno per controllare se gli utenti dei domini federati possono collaborare con gli utenti di Skype for Business Server. Per controllare l'accesso utente federato, è possibile configurare criteri a livello globale, di sito e di utente. Le impostazioni dei criteri di Skype for Business Server applicate a un livello di criteri possono sovrascrivere le impostazioni applicate a un altro livello di criteri. La precedenza dei criteri di Skype for Business Server è la seguente: i criteri utente (maggiore influenza) sostituiscono i criteri sito e i criteri sito sostituiscono i criteri globali (minore influenza). Ciò significa che maggiore è la prossimità dell'impostazione criteri all'oggetto su cui influiscono i criteri, maggiore è l'influenza su tale oggetto.


> [!NOTE]  
> È possibile configurare criteri per il controllo dell'accesso degli utenti federati anche se non è stata abilitata la federazione per l'organizzazione. I criteri configurati, tuttavia, verranno applicati solo dopo aver abilitato la federazione per l'organizzazione. Per informazioni dettagliate sull'abilitazione della Federazione, vedere [abilitare o disabilitare l'accesso degli utenti remoti](../access-edge/enable-or-disable-remote-user-access.md).  Inoltre, se si specifica un criterio utente per controllare l'accesso degli utenti federati, il criterio si applica solo agli utenti abilitati per Skype for Business Server e configurati per l'utilizzo del criterio.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Per configurare criteri per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.

3.  Sulla barra di spostamento sinistra fare clic su **Accesso utente esterno** e quindi su **Criteri di accesso esterno**.

4.  Nella pagina **Criteri di accesso esterno** eseguire una delle operazioni seguenti:
    
      - Per configurare i criteri globali per il supporto dell'accesso degli utenti federati, fare clic sui criteri globali, su **Modifica** e quindi su **Mostra dettagli**.
    
      - Per creare nuovi criteri di sito, fare clic su **Nuovo** e quindi su **Criteri sito**. In **Seleziona un sito** fare clic sul sito appropriato nell'elenco e quindi fare clic su **OK**.
    
      - Per creare nuovi criteri utente, fare clic su **Nuovo** e quindi su **Criteri utente**. In **Nuovi criteri di accesso esterno** creare un nome univoco nel campo **Nome** che indichi lo scopo dei criteri, ad esempio **AbilitaUtentiFederati** per criteri utente che abilitano le comunicazioni per gli utenti di domini federati.
    
      - Per modificare criteri esistenti, fare clic sui criteri appropriati indicati nella tabella, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.

5.  (Facoltativo) Se si desidera aggiungere o modificare una descrizione, specificare le informazioni per i criteri in **Descrizione**.

6.  Eseguire una delle operazioni seguenti:
    
      - Per abilitare l'accesso degli utenti federati per i criteri, selezionare la casella di controllo **Abilita comunicazioni con utenti federati**.
    
      - Per disabilitare l'accesso degli utenti federati per i criteri, deselezionare la casella di controllo **Abilita comunicazioni con utenti federati**.

7.  Fare clic su **Commit**.

Per consentire l'accesso degli utenti federati, è inoltre necessario abilitare il supporto per la federazione nell'organizzazione. Per ulteriori informazioni, vedere [abilitare o disabilitare la Federazione e la connettività per la messaggistica istantanea pubblica](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Se si tratta di criteri utente è inoltre necessario applicarli agli utenti ai quali si desidera consentire di collaborare con utenti federati. Per ulteriori informazioni, vedere [assegnare un criterio di accesso utente esterno](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per configurare un criterio esistente utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Avviare Skype for busines Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for Business Server** e quindi su **Skype for Business Server Management Shell**.

3.  Digitare quanto segue in Skype for Business Server Management Shell:
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Il parametro "EnablePublicCloudAudioVideoAccess" non dispone di una selezione corrispondente nel pannello di controllo di Skype for Business Server


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per creare un nuovo criterio utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Skype for Business Server** e quindi fare clic su **Skype for Business Server Management Shell**.

3.  Digitare quanto segue in Skype for Business Server Management Shell:
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Ecco un esempio di creazione di nuovi criteri sito:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Per eliminare o reimpostare un criterio utilizzando Windows PowerShell per supportare l'accesso da parte di utenti di domini federati

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Digitare quanto segue in Skype for Business Server Management Shell
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Ecco un esempio di reimpostazione dei criteri globali. È possibile rimuovere impostazioni dai criteri globali, ma non è possibile eliminarli:
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Per rimuovere criteri sito, digitare:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Elimina i criteri sito Redmond. Per eliminare criteri utenti denominati UserEAPPolicy, digitare:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Vedere anche


[Abilitare o disabilitare la federazione e la connettività per la messaggistica istantanea pubblica](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Assegnare criteri di accesso per gli utenti esterni](assign-an-external-user-access-policy.md)

[Gestire i domini federati SIP per l'organizzazione](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Gestire i provider federati SIP per l'organizzazione](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

